<!-- Source: https://app.notion.com/p/41c9a9b48b7a816a9283d8878f359bb0?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🛠️ 05 — ACADIVA Platform Architecture, Operations, Integrations & Infrastructure

This manual covers the shared technical foundation: application architecture, school tenancy, security, hosting, storage, domains, internal Operations, external integrations, communications infrastructure and cost governance. It is the reference for cross-cutting infrastructure decisions; use the core system map and implementation blueprint alongside it.

<b>Preservation rule:</b> the full source sections are reproduced below. Their original requirements, examples, rationale, checklists and open questions are retained. This curated page changes navigation and grouping, not product decisions.

---

## 14. Non-functional requirements

- Strong authentication and role-based authorisation.
- Server-side tenant isolation on every data access path.
- Secure handling of student and parent information.
- Audit logs for sensitive record changes.
- Encryption in transit and appropriate encryption at rest.
- Regular backups and tested restoration.
- Reliable result and payment transaction handling.
- Responsive mobile and desktop interfaces.
- Accessible, clear user interface and language.
- Export and portability of school-owned records.
- Defined retention, deletion and account closure processes.
- Monitoring, error reporting and support procedures.

---

## 29. Security, privacy, resilience and school data protection

<b>Status:</b> Mandatory product and operating requirements. Security must be designed into the architecture from the beginning, not added after schools start storing sensitive records.

### 29.1 Security objective

ACADIVA will store valuable school operational records, including student identities, parent contacts, academic results, attendance, fee accounts, receipts, staff records and school documents. A compromise could disrupt a school's operations and expose children and families to harm.

The objective is to protect confidentiality, integrity and availability: only authorised people can see data, records cannot be secretly altered, and schools can continue or recover after technical failure.

No software can honestly promise to be impossible to hack. ACADIVA must reduce the likelihood and impact of attacks, detect suspicious activity and have a tested recovery plan.

### 29.2 Tenant isolation

- Every school-owned record must be associated with a school tenant.
- Tenant identity must be derived and validated server-side from authenticated membership, not trusted from a client-supplied school ID.
- Enforce row-level security on every exposed table containing tenant data.
- Apply least-privilege policies for reads, inserts, updates and deletes.
- Test that one school cannot access another school's students, parents, payments, documents, staff, announcements, reports or audit records.
- Prevent insecure direct object reference attacks by checking ownership and permission on every resource request.
- Tenant switching must revalidate membership and permissions.
- Use separate platform administration permissions for cross-tenant support; a school administrator must not become a platform-wide administrator.
- Views, RPC functions, storage buckets and background jobs must preserve tenant boundaries; do not assume that protecting the underlying tables automatically protects every access path.

### 29.3 Authentication and account protection

- Use secure authentication, verified email/phone processes and safe account recovery.
- Offer multi-factor authentication for privileged accounts, especially proprietors, principals, bursars and platform administrators.
- Use short-lived access tokens and secure refresh/session handling.
- Support session revocation when staff leave, devices are lost or accounts are compromised.
- Apply rate limits and progressive protections against login guessing and OTP abuse.
- Never use user-editable profile metadata as a source of role or permission authority.
- Google sign-in is an authentication method, not proof that a person is a teacher, parent or school administrator.
- Require school invitation or verified membership before granting school access.

### 29.4 Role and permission controls

- Enforce permissions in database policies and trusted server-side services.
- Use least privilege by default.
- Separate sensitive finance, result approval, staff management, parent linking, school configuration and platform administration permissions.
- Require explicit authorisation for high-impact actions.
- Record changes to roles, permissions, parent-child links, teacher assignments, fee structures and payment records.
- Require stronger authentication or re-confirmation for sensitive operations where appropriate.
- Never trust a hidden menu or disabled button as the only security control.

### 29.5 Application and API security

- Keep payment secret keys, database service-role keys and other secrets on trusted servers only.
- Never expose privileged keys in browser or mobile application code.
- Validate all inputs on the server; use parameterised database operations.
- Protect against injection, cross-site scripting, cross-site request forgery where applicable, broken access control, insecure file uploads and abuse of public endpoints.
- Apply request-size limits, rate limiting, bot protection and secure HTTP/TLS configuration.
- Use secure headers and restrictive content-security policies where applicable.
- Keep dependencies updated, pin versions and scan for known vulnerabilities.
- Separate development, staging and production environments and credentials.
- Review code and security changes before deployment; avoid direct unreviewed production changes.

### 29.6 Payment security and financial integrity

- ACADIVA must not store card numbers, CVV values or raw card credentials.
- Use the payment provider's hosted or tokenised payment experience.
- Initialise transactions from a trusted backend, not by trusting a client-supplied amount.
- Verify payment events using the provider's current signature-verification requirements.
- Verify transaction reference, status, amount, currency and intended school/student/invoice mapping server-side.
- Use idempotency and unique provider references to prevent duplicate credits.
- Do not treat a redirect or client success message as proof of payment.
- Keep gateway events and internal ledger entries linked and auditable.
- Separate pending, confirmed, reversed, refunded and disputed states.
- Restrict payment corrections and refunds to authorised staff with recorded reasons.
- Reconcile gateway reports and school settlement records.
- Alert on unusual payment activity, repeated failures, mismatched amounts and duplicate references.

### 29.7 Data encryption, files and secrets

- Use TLS for data in transit.
- Use encryption at rest through the hosting/database/storage provider and encrypt especially sensitive exports or backups where appropriate.
- Store credentials and API keys in managed secrets, not source code or client bundles.
- Restrict access to storage buckets; student documents and result files must not be publicly readable by guessable URLs.
- Use short-lived signed download links and verify the requesting user's school membership and permission.
- Validate uploaded file type and size, scan uploads where feasible, and prevent executable or malicious files from being served.
- Minimise the amount of sensitive information included in logs and notifications.

### 29.8 Backups, disaster recovery and continuity

- Maintain automated database backups and separate protected backups of critical files.
- Keep backups separate from the production account or environment where feasible, so a compromised production account cannot trivially destroy every recovery copy.
- Define recovery point objective (RPO) and recovery time objective (RTO) before onboarding schools at scale.
- Test restoration regularly, not merely whether a backup job reports success.
- Test recovery of one school tenant without exposing another tenant's records.
- Preserve documents and attachments in a separately monitored backup process.
- Maintain a documented incident and disaster-recovery procedure.
- Monitor uptime, database capacity, storage, failed jobs and backup status.
- Provide a school-level export and recovery process.

### 29.9 Audit logs and monitoring

Maintain protected audit records for important events, including:

- Successful and failed sign-ins.
- Session revocation and account recovery.
- Role and permission changes.
- Student and parent record changes.
- Parent-child linking and unlinking.
- Teacher assignment changes.
- Results approval and publication.
- Fee creation and modification.
- Payments, reversals, refunds and adjustments.
- Financial exports and sensitive document access.
- Announcement creation and bulk sends.
- Platform administrator access to school data.

Logs should record actor, school tenant, action, affected record, timestamp and relevant outcome without unnecessarily copying sensitive content. Financial and security audit history should be append-only or tamper-evident, with access restricted.

### 29.10 Privacy and Nigerian regulatory obligations

ACADIVA must be designed for compliance with the Nigeria Data Protection Act 2023 and applicable NDPC guidance. Schools and ACADIVA may have different controller/processor responsibilities depending on the actual service arrangement and processing activity. This must be documented contractually and reviewed by a qualified Nigerian data protection professional.

The NDPC's published guidance identifies education-sector processing among the categories relevant to designation as a data controller or processor of major importance. ACADIVA must obtain legal advice on its own registration, audit, DPO and other obligations as its operations and customer base develop.

Requirements include:

- Clear privacy notices and documented purposes for processing.
- Data minimisation and retention rules.
- Secure handling of children's information.
- Appropriate school data-processing agreements.
- Procedures for data access, correction, deletion and other applicable data-subject rights.
- Breach detection, response and required notifications.
- Vendor and subprocessor due diligence.
- Appropriate safeguards for international data transfers.
- Staff confidentiality and security training.

### 29.11 Vendor and infrastructure due diligence

Evaluate database, hosting, storage, payment, email, SMS and analytics providers for security controls, data location, access management, incident response, backups, retention, contractual terms and subprocessor transparency.

A provider's security certification does not make ACADIVA automatically secure. ACADIVA remains responsible for correct configuration, application security, access controls and incident response.

### 29.12 Security testing before onboarding schools

- Test tenant isolation using at least two separate school tenants.
- Test parent access to only verified linked children.
- Test teacher access to only assigned classes and permitted records.
- Test finance permissions for teachers, administrators, bursars and principals.
- Test attempts to alter IDs, school IDs, invoice IDs and payment references.
- Test duplicate and forged payment webhooks.
- Test malicious file uploads and unauthorised document downloads.
- Test account recovery, session revocation and privileged account MFA.
- Test backups and tenant-specific recovery.
- Conduct independent security review and penetration testing before significant scale or handling of high-risk data.
- Track vulnerabilities, fixes, retests and security incidents.

### 29.13 Security principle and customer trust

Schools should remain with ACADIVA because it is reliable, useful, secure, continuously improving and difficult to replace operationally—not because their records are held hostage.

ACADIVA should support complete school data export in usable formats, clear ownership and access terms, and an orderly exit process. Strong retention should come from dependable service, trustworthy records, integrations, staff familiarity, parent adoption, useful reporting, support and operational continuity.

A school should be able to trust ACADIVA with its records because the platform protects them and makes them useful—not because the school is unable to leave.

---

## 38. Free-tier-first infrastructure and financial model — 15 November 2026

### 38.1 Purpose and status

This section records the current working financial model for ACADIVA and the agreed direction to begin with free or low-cost infrastructure where technically responsible, then upgrade when measured usage, reliability, security, backup or customer commitments require it.

<b>Status:</b> Planning model. Pricing, costs, staffing capacity and usage assumptions are not yet validated through live school deployments or binding vendor quotations. Do not present the scenarios as guaranteed margins, forecasts or net profit.

The model separates:

- Subscription revenue from one-time onboarding revenue.
- Recurring operating costs from one-time implementation costs.
- Technology costs from the people and field operations required to deliver the service.
- ACADIVA subscription charges from school-funded SMS and payment-processing costs.

### 38.2 Infrastructure strategy: free-tier-first, not free-tier-at-all-costs

<b>Working direction:</b> Use free plans for development, internal testing and carefully controlled early pilots. Continue using free infrastructure for production only while actual usage, security, backup, recovery and reliability requirements remain safely within the provider's limits.

A shared multi-tenant architecture is essential. ACADIVA should not create a separate Supabase project for every school. Use one shared production project with strict tenant isolation and row-level security, plus a separate staging environment where plan limits permit. Never put real school data into staging unnecessarily.

Current provider-plan facts checked on 15 November 2026:

- Supabase Free currently lists 500 MB database size per project, 1 GB file storage, 5 GB egress, 50,000 monthly active users, 500,000 Edge Function invocations and 2 million Realtime messages.
- Supabase Free projects may pause after seven days of low activity.
- Supabase Free does not include automatic backups. Manual backup procedures are required; paid plans provide additional backup capabilities.
- Supabase currently limits the number of active free projects in an organisation/account context. This is not a per-school allowance.
- Netlify Free currently provides a monthly credit allowance with a hard usage limit; reaching the limit can pause the site. Paid plans provide higher allowances.

Provider limits and prices can change. Recheck official pricing and documentation before launch, before committing to a school contract and whenever usage approaches a limit.

Official references:

- Supabase pricing: [https://supabase.com/pricing](https://supabase.com/pricing)
- Supabase billing and plan limits: [https://supabase.com/docs/guides/platform/billing-on-supabase](https://supabase.com/docs/guides/platform/billing-on-supabase)
- Supabase free-project pausing: [https://supabase.com/docs/guides/platform/free-project-pausing](https://supabase.com/docs/guides/platform/free-project-pausing)
- Supabase Free backup FAQ: [https://supabase.com/kb/faqs/platform/free-plan-backups](https://supabase.com/kb/faqs/platform/free-plan-backups)
- Supabase backup documentation: [https://supabase.com/docs/guides/platform/backups](https://supabase.com/docs/guides/platform/backups)
- Netlify pricing: [https://www.netlify.com/pricing/](https://www.netlify.com/pricing/)

<b>Important distinction:</b> The fact that a few schools may fit within free quotas does not prove that the setup is production-safe. The decision must account for database size, storage, egress, concurrent usage, uptime, backups, restore testing, support obligations and the impact of an outage on schools.

### 38.3 Storage assumptions and student photographs

Student photographs should be stored in object storage, not as binary data inside database rows. Use private storage buckets, access controls and appropriately sized images.

A planning target of approximately 100 KB per compressed student image may be achievable for a small, appropriately cropped JPEG/WebP image, but the final size must preserve recognisability and be tested on real devices. Do not reduce image quality blindly.

Illustrative photo-only storage:

- 2,610 students × 100 KB ≈ 261 MB.
- 5,000 students × 100 KB ≈ 500 MB.
- 10,000 students × 100 KB ≈ 1 GB.

These calculations exclude other uploaded files, duplicate/replacement images, documents, thumbnails, backups and data transfer. Photo storage alone is therefore not a reliable way to estimate total storage needs.

Track actual database size, file storage, egress, request volume and growth per active student and per school. Set an internal warning at 70% of a relevant quota; this is a management alert threshold, not a provider-imposed limit.

### 38.4 Staged infrastructure and upgrade policy

The following are review milestones, not hard technical limits:

| Stage | Working approach | Required checks |
| --- | --- | --- |
| Development and internal testing | Free plans where possible | No critical production dependency; test data only |
| First controlled pilot | Free-tier-first | Independent backups, tested restore, access controls, monitoring and a recovery plan |
| 2–10 schools | Remain on free plans only if measured usage and operational requirements allow | Quotas, latency, support incidents, backup success, restore time and school-calendar inactivity |
| 10–25 schools | Formal infrastructure review | Load tests, growth trends, support burden, recovery objectives and contractual requirements |
| 25–50 schools | Prepare a paid production budget if required by measured demand or reliability needs | Paid database/hosting, backups, monitoring, security and capacity planning |
| 50+ schools | Operate with a production-grade infrastructure and support plan | Documented capacity, recovery, security, monitoring and service commitments |

Upgrade sooner if any of the following applies:

- A provider quota or performance limit is approaching.
- The school contract requires reliability, backup or support capabilities not available on the free plan.
- Backup and restore cannot be demonstrated adequately.
- A project pause or outage would create unacceptable operational risk.
- Performance, concurrent usage or storage growth becomes unreliable.
- A security or compliance requirement cannot be met on the current plan.

Do not wait for a quota to be exhausted before planning an upgrade. Keep a current export and recovery procedure, and test restoration rather than assuming a backup is usable.

### 38.5 Subscription pricing assumptions

The current working monthly subscription tiers remain:

| Tier | Active enrolled students | Monthly subscription |
| --- | --- | --- |
| Free | 0–50 | ₦0 |
| Launch | 51–150 | ₦30,000 |
| Standard | 151–300 | ₦45,000 |
| Growth | 301–600 | ₦75,000 |
| Pro | 601–1,000 | ₦120,000 |
| Enterprise | Above 1,000 or multi-branch | Custom quote |

Pricing principles:

- Charge by active enrolled student band, not by staff login.
- School-wide role access should be included within the plan.
- The free tier must have genuine but deliberately limited functionality and support boundaries.
- SMS, extensive historical data entry, custom migration and repeated on-site visits must not become unlimited obligations under a low monthly subscription.
- Monthly billing is the default working assumption. Term prepayment should reflect the value of multiple monthly payments, not accidentally charge one monthly fee for an entire term.
- These prices are hypotheses. Test actual willingness to pay, school budgets, competing alternatives and the value delivered before treating them as final.

### 38.6 Revenue scenarios

These are arithmetic scenarios using the pricing assumptions above, not sales forecasts.

| Scenario | School mix / assumption | Monthly recurring revenue |
| --- | --- | --- |
| 1 school | 1 Launch school | ₦30,000 |
| 5 schools | 5 Launch schools | ₦150,000 |
| 10 schools | Mixed example below | ₦495,000 |
| 50 schools | Assumed average subscription ₦45,000 | ₦2,250,000 |
| 100 schools | Assumed average subscription ₦45,000 | ₦4,500,000 |
| 500 schools | Assumed average subscription ₦45,000 | ₦22,500,000 |

Ten-school mixed example:

- 4 Launch schools × ₦30,000 = ₦120,000.
- 4 Standard schools × ₦45,000 = ₦180,000.
- 1 Growth school × ₦75,000 = ₦75,000.
- 1 Pro school × ₦120,000 = ₦120,000.
- <b>Total: 10 schools, 2,610 enrolled students and ₦495,000 monthly recurring revenue.</b>

The 50-, 100- and 500-school scenarios assume an average subscription of ₦45,000. Actual revenue will depend on the mix of school sizes, discounts, free accounts, churn, collections and payment timing.

### 38.7 Illustrative monthly operating-cost model

The ranges below are planning allowances, not confirmed supplier quotations, validated salary benchmarks or final budgets. They assume free-tier-first infrastructure where possible and increasing people/support costs as the customer base grows.

| Cost category | 1 school | 10 schools | 50 schools | 100 schools |
| --- | --- | --- | --- | --- |
| Hosting and database | ₦0–5k | ₦0–25k | ₦40–100k | ₦80–180k |
| Backups, email and security | ₦3–7k | ₦5–15k | ₦15–30k | ₦25–50k |
| Support and customer success | ₦0–10k\* | ₦100–150k | ₦300–450k | ₦600–900k |
| Sales and field visits | ₦5–15k | ₦40–80k | ₦200–350k | ₦350–600k |
| Administration and tools | ₦2–5k | ₦10–20k | ₦40–70k | ₦70–120k |
| Product engineering and maintenance | Founder time\* | ₦150–300k | ₦300–500k | ₦500–800k |
| <b>Illustrative monthly total</b> | <b>₦10–37k plus founder time</b> | <b>₦305–590k</b> | <b>₦895k–₦1.5m</b> | <b>₦1.625m–₦2.65m</b> |

\*At one school, the model assumes the founder handles most support and engineering. Founder time is not economically free; it must be costed when assessing a sustainable business. The table does not fully allocate founder compensation in the one-school case.

The cost ranges need refinement using actual hosting usage, staff pay, travel frequency, support hours, email/SMS volumes, payment volume and engineering workload. Avoid treating the low end as the expected outcome.

### 38.8 Indicative operating contribution

The following subtracts the illustrative operating-cost ranges from the revenue scenarios. It is an operating contribution estimate, not net profit or founder take-home pay.

| Schools | Monthly revenue | Illustrative monthly cost | Indicative contribution |
| --- | --- | --- | --- |
| 1 | ₦30k | ₦10–37k plus founder time | -₦7k to ₦20k before founder time |
| 10 | ₦495k | ₦305–590k | -₦95k to ₦190k |
| 50 | ₦2.25m | ₦895k–₦1.5m | ₦750k–₦1.355m |
| 100 | ₦4.5m | ₦1.625m–₦2.65m | ₦1.85m–₦2.875m |

These estimates do not yet fully price tax, legal and compliance work, insurance, security audits, refunds, chargebacks, bad debt, churn, financing costs, major one-off development, app-store costs, all founder compensation or every payment-gateway charge. They must not be described as net profit.

The ten-school scenario is particularly sensitive: depending on support, engineering and sales costs, it could be loss-making or produce a modest positive contribution. Ten customers do not automatically mean a profitable business.

### 38.9 One-time onboarding and digitisation economics

Onboarding is separate from the monthly subscription. It may involve collecting and cleaning data, configuring classes and subjects, setting up teachers and permissions, importing student records, configuring grading and fees, linking parents, training staff and supporting go-live.

Illustrative direct-cost allowances:

| School size | Indicative direct onboarding cost |
| --- | --- |
| 50–150 students | ₦15,000–₦30,000 |
| 151–300 students | ₦25,000–₦45,000 |
| 301–600 students | ₦40,000–₦75,000 |
| 601–1,000 students | ₦60,000–₦120,000 |

These are internal planning estimates, not customer prices or verified labour/travel quotations. Measure the actual hours and expenses for each pilot.

Working commercial approach:

- Include a clearly defined standard setup in the subscription or a modest one-time onboarding package.
- Quote extensive historical data entry, complex data cleaning, large-scale paper digitisation and repeated on-site training separately.
- Give the school a clear scope before work begins.
- Record onboarding hours, travel, data volume, errors and rework.
- Build reusable import templates, validation reports, duplicate detection, bulk class allocation, staff invitations and training guides to reduce future delivery cost.

### 38.10 SMS and payment-processing policy

<b>SMS and email</b>

- Do not offer unlimited SMS under the base subscription.
- Use a visible school-funded prepaid allowance or bill usage transparently.
- Illustrative SMS planning example: 5,000 message segments × ₦6.30 = ₦31,500 cost. An illustrative ₦7.50 sell rate would produce ₦37,500 in charges before any support, tax or other overhead.
- These unit prices are placeholders only. Confirm the provider, message segmentation, sender-ID fees, delivery rules and current rates before setting a customer price.
- Push notifications and email may reduce SMS dependence, but delivery and user reach must be tested.

<b>School-fee payments</b>

- Keep ACADIVA's subscription revenue separate from school tuition and fee collections.
- Prefer direct settlement by the payment provider to the school's own bank account, subject to provider capability and the agreed contract.
- Do not casually hold or pool school funds.
- Clearly disclose who bears gateway fees, how refunds and disputes are handled, and how transactions are reconciled.
- Do not absorb tuition-processing fees without modelling the transaction size, fee cap, payment frequency and resulting margin.
- Confirm current provider pricing and terms before launch; the earlier Paystack estimate of 1.5% + ₦100 subject to a cap was a planning assumption and must be rechecked.

### 38.11 Unit economics that must be measured

For each school, capture:

- Monthly subscription revenue actually collected.
- Variable infrastructure and storage cost.
- SMS, email and payment-related cost attributable to the school.
- Support hours and cost to serve.
- Onboarding hours, travel and direct setup cost.
- Customer acquisition cost, including field time and sales expenses.
- Renewal, churn, failed payment and collection rates.
- Product usage by role and workflow completion.
- Gross margin and monthly contribution after direct service costs.

Three essential operating questions:

1. What does it cost to onboard one school?
2. What does it cost to serve one school each month?
3. How many schools can one trained implementation/support person manage without service quality declining?

Illustrative payback example: if a school produces ₦45,000 monthly subscription revenue and costs ₦10,000 per month to serve directly, its monthly contribution before central overhead is ₦35,000. If acquisition and onboarding together cost ₦70,000, simple payback is approximately two months, assuming the school pays on time and remains subscribed. This is an example, not a measured ACADIVA result.

### 38.12 Financial controls and next validation steps

Before using this model for investor materials, hiring commitments or binding customer prices:

- [ ] Obtain current written quotes for hosting, backups, email, SMS, payment processing and monitoring.
- [ ] Measure actual database, storage, egress and usage from a representative pilot.
- [ ] Run a backup and restore test and record recovery time.
- [ ] Record the real time required to onboard a school by size.
- [ ] Track weekly support hours and field-visit expenses.
- [ ] Validate the subscription tiers with proprietors and test willingness to pay.
- [ ] Define what each tier includes and excludes, including support and data migration.
- [ ] Model monthly and termly cash collection, late payment and churn.
- [ ] Add taxes, legal/compliance, security, refunds and founder compensation to a fully loaded budget.
- [ ] Review the model after the first pilot and again after 5 and 10 paying schools.

<b>Decision principle:</b> Keep infrastructure costs low where safe, but do not confuse free hosting with a free business. The largest early costs may be implementation, support, sales and product development. ACADIVA should scale only when the service can be delivered reliably and the contribution per school supports the people and operations required.

---

## 39. Technology infrastructure, engineering controls and design direction — 15 November 2026

### 39.1 Purpose, scope and status

This section defines the working technology and delivery blueprint for building ACADIVA. It consolidates the required accounts, software services, architecture, infrastructure environments, integrations, security controls, engineering workflow, UI/UX direction and design research process.

ACADIVA is a conventional software product. The initial product does not require AI features, an OpenAI API, a Gemini API, model hosting, vector databases, AI agents or AI-specific infrastructure. ChatGPT Plus is an engineering and planning tool used by the founder; it is not a runtime dependency of the ACADIVA application.

<b>Core rule:</b> No feature is considered independently complete. Every requirement must be connected to its approved design, user role, workflow, database entities, backend operations, frontend screens, integrations, permissions, tests and documentation. This is the control against features being connected to the wrong data, role, module or external service.

Distinguish the following statuses throughout this section:

- <b>Working direction:</b> currently preferred architecture or approach, subject to technical validation.
- <b>Required capability:</b> ACADIVA needs this capability, but the vendor may still be selected.
- <b>Candidate:</b> a provider or tool to evaluate, not a purchase commitment.
- <b>Later phase:</b> required only when the corresponding feature or distribution channel is introduced.
- <b>Open decision:</b> must be validated before implementation or launch.

### 39.2 Product and engineering principles

1. Build one coherent, modular, multi-tenant school operating system, not disconnected mini-applications.
2. Use one authoritative source for each type of data. Do not duplicate business rules in web, mobile and database layers.
3. Enforce school and role permissions on the server and in PostgreSQL Row Level Security; hiding a button is not security.
4. Every external integration must have a documented owner, purpose, data contract, credentials, failure behaviour, monitoring and test.
5. Every feature must have acceptance criteria and automated or documented manual tests.
6. Work in small reviewed changes on Git branches. Do not allow uncontrolled direct changes to production.
7. Keep development, staging and production separate. Never use real children's records in ordinary development or test fixtures.
8. Use free plans where responsible, but never sacrifice backup, security, recovery or school commitments just to remain free.
9. Design mobile and web experiences around actual school tasks. Reuse the same backend contracts and business rules.
10. Prefer simple, maintainable technology over adding tools because they are fashionable.

### 39.3 Architecture overview

<b>Working architecture:</b> multi-tenant modular application with a shared PostgreSQL database, shared backend services and role-specific web/mobile experiences.

Logical flow:

- Users access ACADIVA through the public website, a school's branded subdomain, responsive web application or supported mobile application.
- DNS and hosting route the request to the correct deployed application.
- The application resolves the school context from a verified school slug/subdomain and the authenticated user's membership. Never trust a client-supplied school ID without server-side membership and permission checks.
- Supabase Auth establishes identity. ACADIVA's own records establish school membership, role, assignments and permissions.
- Application services and database policies enforce business rules and tenant isolation.
- PostgreSQL stores structured records. Supabase Storage stores private files and images.
- Background/queued jobs process notifications, scheduled reminders, imports, exports and other work that should not block a user request.
- External services handle payment processing, SMS, email and push delivery where configured.
- Sentry monitors application errors and performance. PostHog measures product usage and workflow completion. Hosting and database provider dashboards monitor infrastructure.
- GitHub holds source code, version history, review and automated checks. Netlify deploys the approved web build. Figma holds design source files. Notion holds the product and delivery blueprint.

<b>Logical architecture layers:</b>

1. Presentation: Next.js web app and Expo/React Native mobile app.
2. Design system: shared tokens, components, typography, interaction patterns and accessibility rules.
3. Application layer: feature modules, workflows, validation, permissions and orchestration.
4. Backend/data access: server-side services, Supabase client access under RLS, database functions and Edge Functions where appropriate.
5. Data: PostgreSQL, private object storage, audit history and migration history.
6. Integrations: Google OAuth, payment gateway, SMS, email and push notifications.
7. Operations: CI/CD, monitoring, analytics, backups, security, incident handling and support.

### 39.4 Technology and account register

The following is the master inventory. It does not mean every account must be paid for or activated on day one.

| Category | Tool / provider | Responsibility | Status / timing |
| --- | --- | --- | --- |
| AI engineering assistant | ChatGPT Plus | Product reasoning, architecture assistance, coding support, review and documentation | Required working tool; not an app dependency |
| Coding agent | OpenAI Codex | Repository-aware implementation, code changes, debugging and review | Use through eligible Plus access; usage limits apply |
| Source control | GitHub | Private repositories, branches, commits, pull requests, issues and project tracking | Required |
| Web framework | Next.js + React | Web application and server-rendered routes where appropriate | Working direction |
| Language | TypeScript | Shared types and compile-time checks | Required |
| Web styling | Tailwind CSS and design tokens | Consistent responsive styling | Working direction |
| Mobile framework | Expo + React Native | Android and iOS mobile experiences | Working direction; build when mobile phase starts |
| Database | Supabase PostgreSQL | Structured multi-school records | Working direction |
| Authentication | Supabase Auth | Identity, sessions, password flows and OAuth integration | Working direction |
| Authorisation | PostgreSQL RLS + server-side checks | School and role access enforcement | Required |
| Object storage | Supabase Storage initially | Student images, documents and generated files | Working direction |
| Web hosting | Netlify initially | Web builds, previews, production deployment and domain connection | Preferred because of existing familiarity; validate against Vercel before final commitment |
| Alternative hosting | Vercel | Alternative Next.js hosting and deployment | Candidate, not a second production host by default |
| DNS / edge security | Cloudflare | DNS, domain security and possible WAF/edge controls | Candidate / recommended to evaluate |
| Domain registrar | Reputable registrar | Domain ownership, renewals and DNS control | Required; vendor open |
| Design | Figma | Research boards, wireframes, components, high-fidelity screens and prototypes | Required |
| Product documentation | Existing ACADIVA Notion blueprint | Product source of truth, decisions, requirements and delivery records | Required; update existing page, do not duplicate |
| Error monitoring | Sentry | Frontend/backend/mobile errors, stack traces, releases and performance tracing | Required before pilot; include from early development |
| Product analytics | PostHog | Feature usage, funnels, activation and workflow completion | Recommended; distinct from error monitoring |
| Uptime monitoring | Better Stack or UptimeRobot | External availability checks and incident notification | Candidate; choose one initially |
| Session replay | PostHog replay or Sentry Replay, subject to privacy review | Reproduce interface issues | Optional; do not record sensitive student/parent information |
| Transactional email delivery | Resend | Verification, recovery, invitations, admissions, receipts and school notifications | Preferred provider to evaluate; detailed integration requirements in Section 48 |
| SMS delivery | Termii or Africa's Talking | Nigerian SMS, OTPs and transactional notifications | Provider selection open; verify current pricing and sender-ID rules |
| Payments | Paystack initially; Flutterwave as alternative | Checkout, payment verification, refunds and settlement integration | Candidate / preferred to evaluate |
| Push notifications | Expo Notifications initially | Mobile push delivery | Later, with mobile app |
| Web automated tests | Playwright | Browser end-to-end tests | Recommended |
| Unit/integration tests | Vitest and React Testing Library, or equivalent | Business logic and component tests | Required capability; exact stack to confirm |
| Mobile tests | Expo-compatible testing plus Maestro or Detox evaluation | Mobile interaction and regression tests | Later mobile phase |
| CI/CD | GitHub Actions | Automated lint, type checks, tests, build and deployment gates | Required |
| Dependency security | Dependabot and GitHub security tooling | Vulnerability alerts and dependency updates | Enable where available |
| Static analysis | ESLint, TypeScript and CodeQL where available | Code quality and security checks | Required capabilities |
| Secret management | Hosting environment variables and secure password manager | Protect credentials and production secrets | Required |
| Password manager | Bitwarden or 1Password | Secure storage and controlled sharing of account credentials | Recommended |
| Database backups | Supabase backup capability plus independent encrypted backup process | Recovery from data loss | Required before real school data |
| File backup | Independent backup/retention strategy for critical uploaded files | Recovery of student and school documents | Required before live use |
| PDF/document generation | Server-side PDF/document generation library | Receipts, report cards, invoices and letters | Required when those modules launch |
| Data import/export | Validated CSV/XLSX import and export tools | School onboarding and data portability | Required |
| Support/ticketing | Notion or a lightweight ticketing tool initially | Track school issues, ownership and resolution | Required operational process; dedicated provider later if volume warrants |
| App distribution | Google Play Console and Apple Developer Program | Publish mobile apps | Later, if native app distribution is approved |
| Browser/device testing | Real Android/iOS devices and browser testing; BrowserStack as optional service | Device and browser compatibility | Real devices required; paid testing service optional |

<b>Avoid unnecessary duplication:</b> Do not pay for Netlify and Vercel to host the same production web app. Do not run Sentry and another error tracker for the same events without a defined reason. Do not run both PostHog and GA by default. Do not introduce multiple SMS or email vendors before failover or volume justifies them.

### 39.5 Sentry and PostHog — distinct responsibilities

Sentry is explicitly included in the ACADIVA technology inventory and must not be omitted from the architecture.

<b>Sentry — error and performance monitoring</b>

- Capture frontend exceptions and failed interactions.
- Capture backend and server-side errors.
- Capture mobile crashes and exceptions when mobile is introduced.
- Associate errors with release versions and deployment commits.
- Capture stack traces and useful diagnostic context.
- Monitor performance traces and slow transactions where configured.
- Alert the engineering owner about critical errors.
- Group duplicate errors and track regressions.
- Apply privacy filtering and avoid sending student names, phone numbers, result details, payment credentials or other sensitive payloads.

<b>PostHog — product analytics</b>

- Measure school onboarding and activation.
- Measure role-based feature adoption.
- Understand where teachers abandon attendance or mark-entry workflows.
- Measure parent account activation and portal usage.
- Measure fee invoice and payment workflow completion.
- Compare product usage before and after interface changes.
- Use privacy-conscious event properties and avoid unnecessary personal data.

Sentry answers: “What broke, where, and why?” PostHog answers: “How are people using the product and where do they get stuck?” They complement one another; neither replaces automated tests or infrastructure monitoring.

### 39.6 Hosting, domains and environment topology

<b>Domain requirements</b>

- Register and renew the chosen primary ACADIVA domain.
- Keep domain ownership and billing under founder/company-controlled accounts.
- Configure DNS records and HTTPS.
- Configure wildcard subdomain routing for school spaces if the chosen host supports the required setup.
- Verify school slug uniqueness and reserved names.
- Prevent school subdomain takeover, impersonation and unauthorised custom-domain changes.
- Document domain renewal, registrar recovery and DNS access.
- Consider Cloudflare for DNS and edge security; it is not a substitute for application authentication or database RLS.

<b>Proposed environment topology</b>

- Local development: developer's machine, test data and local environment variables.
- GitHub preview/branch builds: isolated review of proposed web changes.
- Staging: separate application configuration and separate test database/project where plan and budget permit.
- Production: live application and live school data, with tightly restricted credentials and deployment permissions.

Do not assume the free Supabase project allowance will support every desired environment indefinitely. Plan the staging and production project count deliberately. A staging environment must never be connected accidentally to production data or production payment credentials.

<b>Deployment controls</b>

- Changes are committed to feature branches.
- Pull requests run linting, type checks, unit tests and build checks.
- Required checks must pass before merging.
- Preview deployment is reviewed.
- Approved changes are merged to the production branch.
- Production deployment is monitored.
- Rollback procedure and responsible person are documented.
- Database migrations are version-controlled and reviewed separately from application code.
- Destructive migrations require explicit review, backups and a recovery plan.

### 39.7 Supabase and database infrastructure rules

- Use a shared multi-tenant PostgreSQL database rather than a separate database project for every school.
- Every school-owned record must be related to a school/tenant identifier, directly or through a validated parent relationship.
- Use stable primary keys and foreign-key constraints.
- Use database constraints for critical invariants; do not rely only on frontend validation.
- Enforce RLS for all tables exposed to client access.
- Create explicit policies for select, insert, update and delete operations.
- Test both allowed and denied access paths for every role.
- Never expose service-role keys or privileged secrets to browser or mobile clients.
- Use server-side functions for privileged actions and verify the authenticated actor, school membership and permissions.
- Use private storage buckets and signed access where appropriate.
- Do not store image or document binary data inside ordinary relational rows.
- Maintain migration files and schema documentation.
- Use transactions for multi-record operations that must succeed or fail together.
- Maintain audit history for sensitive changes.
- Use soft deletion or controlled archival where historical academic/financial records must remain traceable.
- Define retention, export and deletion policies before launch.
- Measure database size, storage, egress, connections, request volume and query performance.
- Implement backup and restore tests. A backup that has not been restored successfully is not a proven recovery process.

<b>Core data domains to model:</b> schools, campuses, school settings, academic sessions, terms, users, school memberships, roles, permissions, staff, teacher assignments, students, guardians, guardian-student relationships, admissions, enrolments, classes, arms, subjects, timetables, attendance, assessments, grading schemes, marks, results, fee categories, fee structures, invoices, invoice items, payments, payment attempts, refunds, receipts, notifications, templates, message deliveries, documents, audit events, imports, exports and support/implementation records.

The final relational schema, constraints, indexes, data ownership and retention rules must be designed before module implementation. This list is a domain inventory, not a completed schema.

### 39.8 Authentication, identity and permission architecture

- Supabase Auth is the identity provider in the proposed stack.
- Google OAuth is an additional sign-in method, not a school-role assignment mechanism.
- Email/password login and account recovery should be supported where appropriate.
- Phone number may be used for parent contact, verification or recovery after the exact policy is designed.
- A user may have more than one school membership only if the product explicitly supports it.
- A user may have different roles in different schools; roles must be scoped to the school membership.
- Principal, proprietor, bursar, registrar, administrator, teacher, parent and student permissions must be explicit.
- Teacher access must depend on school, class, subject and academic assignment where relevant.
- Parent access must depend on a verified guardian-child relationship.
- Student access must be restricted to the student's own permitted information.
- Privileged actions such as publishing results, changing payment status, exporting bulk data and modifying permissions must have additional controls and audit records.
- Account suspension, staff departure, role changes and school transfers must revoke or update access promptly.
- Consider MFA for privileged administrative roles.
- Use invitation expiry, rate limits and secure account recovery.

### 39.9 Integration register and connection contracts

Every integration must have a dedicated entry in the integration register with:

- Integration ID and name.
- Business purpose and owning module.
- Provider and account owner.
- Environment-specific credentials.
- Data sent and received.
- Authentication and webhook verification method.
- Trigger and expected response.
- Timeout, retry and duplicate-handling behaviour.
- Failure queue and manual recovery method.
- Rate limits and cost model.
- Privacy and retention requirements.
- Monitoring and alert rules.
- Sandbox/test procedure.
- Acceptance tests and production approval.

<b>Initial integration contracts</b>

| Integration | Connects to | Required controls |
| --- | --- | --- |
| Google OAuth | Login and account identity | Verified OAuth configuration, redirect URLs, state/nonce handling, account-linking rules and environment separation |
| Paystack | ACADIVA finance module | Server-side transaction verification, signed webhook validation, idempotency, reconciliation, refund handling and school settlement rules |
| SMS provider | Notification service | Approved sender ID, consent/preferences, message templates, queue, delivery reports, retry policy, DND handling and spend limits |
| Email provider | Notification service | Verified sending domain, SPF/DKIM/DMARC, templates, suppression/bounce handling, delivery logs and retry policy |
| Sentry | Web, backend and mobile releases | Release tagging, environment tagging, privacy scrubbing, issue ownership and alerts |
| PostHog | Product workflows | Approved event taxonomy, privacy review, no unnecessary sensitive student data and retention rules |
| Cloudflare/DNS | Domain and web edge | DNS ownership, HTTPS, access control and documented rollback |
| Expo push | Mobile notification workflows | Device token lifecycle, user preferences, permission state and delivery failure handling |
| Storage | Student/document workflows | Private access, file type/size validation, malware/security review where appropriate and signed URLs |
| Backup destination | Database and file recovery | Encryption, access restrictions, retention, backup verification and restore tests |

External webhooks must be treated as untrusted input until signatures and payloads are verified. Webhook processing must be idempotent so repeated delivery cannot duplicate payments, receipts or notifications.

### 39.10 Notification and messaging architecture

Create one central notification module used by admissions, finance, attendance, academics, announcements and account management.

Required capabilities:

- Event-triggered notifications.
- Scheduled notifications.
- Template management and versioning.
- Recipient resolution by school, class, guardian relationship and role.
- SMS, email and later push channels.
- School-level channel settings and sender identity.
- Parent/staff preferences and consent controls.
- Queueing and background processing.
- Retry with bounded backoff.
- Idempotency and duplicate prevention.
- Delivery receipts and status history.
- Failed-message review and manual retry.
- Per-school usage, quota and billing reports.
- Quiet hours and school-defined communication policies where relevant.
- Message preview and approval for bulk announcements.
- Audit record of who initiated a bulk message.

Do not send SMS synchronously inside a teacher's save operation. Save the business event, queue the message and report delivery status separately. A failed message must not undo an otherwise valid attendance record or payment.

### 39.11 Payments and wallet-inspired finance experience

<b>Payment processing architecture</b>

- ACADIVA subscription billing is separate from school fee collection.
- School fee payments should settle to the school's configured account through the payment provider's supported arrangement.
- ACADIVA should not casually hold, pool or operate as custodian of school funds.
- The backend creates and stores an invoice/payment intent and a unique reference.
- The payment provider processes checkout.
- The backend verifies payment status independently through server-side verification and signed webhooks.
- The system records payment attempts separately from confirmed payments.
- Reconciliation links confirmed provider transactions to the correct school, invoice and student.
- Duplicate webhook delivery must not duplicate a payment.
- Refunds, reversals, chargebacks and failed transactions need explicit states and audit history.
- Receipts are generated only from verified payment records.
- Cash/bank-transfer payments entered manually by staff must be labelled as manually recorded and verified according to school controls; never present an unverified entry as provider-confirmed.

<b>Visual direction for finance</b><br />The user specifically wants an exceptionally polished, simple payment experience inspired by Apple Wallet and Apple Pay presentation, including dark/black wallet or ID-card visual elements. Treat this as visual inspiration, not permission to copy Apple's interface, logos, card artwork or proprietary assets.

Proposed ACADIVA direction:

- A clean finance home with clear available, billed, paid and outstanding figures.
- Elegant dark/black digital fee-card or school-payment pass as a distinctive visual component.
- Restrained gradients, subtle depth, precise typography and carefully controlled glass effects.
- A clear payment sheet with amount, student, fee purpose, school identity, reference and payment method.
- A readable transaction timeline with status, date, amount and receipt.
- Strong separation between pending, successful, failed, refunded and manually recorded transactions.
- Payment confirmation must be unmistakable and accessible; colour alone must not convey status.
- Avoid decorative clutter, confusing card stacks, fake balances, imitation bank accounts or implying ACADIVA holds funds.
- Design for both parent mobile screens and finance/admin web screens.
- Use the chosen payment provider's approved checkout/SDK components where required; the ACADIVA visual layer must not interfere with payment security or provider rules.

Apple Pay is not assumed to be a required Nigerian payment rail. The initial payment methods and provider support must be validated for Nigerian schools and parents. The design can be Wallet-inspired without promising Apple Pay integration.

### 39.12 UI/UX and brand design specification

<b>User's stated visual preferences</b>

- Premium, minimal, highly considered visual design.
- Strong preference for glassmorphism / restrained morphism rather than generic flat dashboard templates.
- Brand palette should use a considered gradient system.
- Bold, confident, editorial typography inspired by the visual confidence of Apple's advertising.
- Simple interfaces with excellent hierarchy and generous spacing.
- Avoid clutter, excessive cards, dense dashboards, unnecessary decoration and generic AI-generated design patterns.
- Use light surfaces as the overall product foundation. Dark/black elements may be used deliberately in finance cards, identity passes and selected feature moments.
- The product must feel like a carefully art-directed software brand, not a collection of template screens.

<b>Design principles</b>

1. Simplicity before decoration: every screen has one clear primary task.
2. Strong hierarchy: bold headlines and numbers where useful, concise labels and restrained secondary text.
3. Generous whitespace and consistent spacing.
4. Glassmorphism used selectively for overlays, floating controls, navigation accents and special cards; not as a blanket treatment for every panel.
5. Maintain contrast, legibility and accessibility. Blur, transparency and gradients must never reduce readability.
6. Gradients are part of the brand language, not a background on every component.
7. Use a limited palette with semantic colours for success, warning, error and neutral states.
8. Build a coherent component system; do not style each module independently.
9. Use realistic school data in prototypes, not generic placeholder charts that imply nonexistent capabilities.
10. Every visual component must have responsive, loading, empty, error, disabled and permission states.
11. Avoid overly rounded everything, excessive shadows, floating blobs, random gradient glows, excessive icons and overused glass cards.
12. Avoid dense dashboards. Prioritise the actions and information relevant to each role.

<b>Typography direction</b>

- Use bold, confident display typography for key page headings and high-value numbers.
- Use a highly legible, neutral text family for tables, forms and dense school information.
- Evaluate system typography and licensed/available families. A platform-native system stack can use the native Apple system font on Apple devices; use a consistent cross-platform alternative such as Inter or Geist where appropriate. Do not assume Apple's proprietary font files can be redistributed.
- Establish a scale for display, page title, section title, body, label, caption and numeric data.
- Test long Nigerian names, school names, currency amounts, dates and narrow mobile screens.

<b>Brand palette process</b>

- Explore a primary brand gradient and a restrained set of supporting colours.
- Define exact HEX/RGB tokens only after visual exploration and contrast checks.
- Define light surfaces, elevated surfaces, text hierarchy, borders, focus rings and semantic states.
- Define black/dark finance-card treatment as a product-specific surface, not a second unrelated brand.
- Test colour contrast and colour-blind accessibility.
- Do not choose final brand colours by guessing in code.

<b>Component design system</b><br />Create reusable specifications and Figma components for:

- Buttons and button states.
- Text inputs, password inputs, search and select fields.
- Date pickers and time pickers.
- Navigation, sidebars, tabs and breadcrumbs.
- Cards and summary surfaces.
- Tables, filters, sorting and pagination.
- Student identity rows and profile headers.
- Avatars and school logos.
- Status badges and alerts.
- Dialogs, drawers, popovers and confirmation flows.
- Forms, validation and error messages.
- Charts and financial summaries.
- File upload and document preview.
- Toasts and notification centre.
- Payment sheets, transaction cards and receipts.
- Empty, loading, skeleton, offline, syncing and failed states.
- Mobile bottom navigation and responsive menus.

### 39.13 Design research and inspiration banks

Do not rely on generic AI-generated dashboard concepts as the source of truth. Research existing high-quality interfaces and document what is being learned from each reference.

<b>Research sources to evaluate</b>

- Mobbin — real product screens and user flows.
- Refero — web and app interface references.
- Screenlane — mobile and web interface patterns.
- SaaSFrame — SaaS interface and landing-page references.
- Page Flows — end-to-end product flows.
- Dribbble and Behance — visual exploration only; do not assume a beautiful concept is a usable product.
- Apple Human Interface Guidelines — hierarchy, interaction, typography and platform conventions.
- Material Design — accessibility, interaction and component behaviour.
- Radix UI and shadcn/ui — accessible, reusable web component patterns; use as implementation foundations only where they fit the approved visual system.

<b>Research rules</b>

- Save reference screenshots/links and annotate exactly what is useful: navigation, spacing, typography, payment flow, hierarchy, transitions or information density.
- Do not copy a whole product or use protected brand assets.
- Distinguish visual inspiration from interaction conventions and actual implementation requirements.
- Review real finance/payment flows separately from generic dashboards.
- Create a reference board for the overall brand, web dashboard, teacher mobile experience, parent portal and payment experience.
- Compare at least several strong references before finalising a major screen pattern.
- Record why a pattern was selected and what was deliberately rejected.

### 39.14 Complete UI/UX deliverables before full implementation

1. Brand exploration board and approved direction.
2. Brand palette and gradient specification.
3. Typography and type scale.
4. Spacing, radius, shadow, border and blur tokens.
5. Iconography and illustration rules.
6. Figma component library.
7. Web information architecture.
8. Mobile information architecture.
9. Full role and permission matrix.
10. Complete screen inventory with unique screen IDs.
11. Workflow maps for critical school tasks.
12. Low-fidelity wireframes.
13. High-fidelity designs for every approved first-release screen.
14. Interactive prototype for the critical workflows.
15. Responsive and breakpoint specifications.
16. Accessibility and contrast review.
17. Loading, empty, error, offline and syncing states.
18. Finance and wallet-inspired payment design system.
19. Design-to-development handoff notes and component mapping.
20. Design QA checklist for comparing implementation against approved Figma screens.

Design is not complete when a dashboard screenshot looks attractive. It is complete when all required role workflows and states are specified and can be implemented consistently.

### 39.15 Lovable decision

<b>Current recommendation: Lovable is not required for ACADIVA's primary development workflow.</b>

Reasoning:

- The preferred route is a controlled codebase using GitHub, TypeScript, Next.js, Supabase and Codex.
- Figma should be the design source of truth.
- Codex can work directly against the repository, existing architecture, tests and engineering rules.
- Introducing Lovable as another primary app generator may create a second source of code, duplicated implementation and architectural inconsistency.
- The project needs carefully controlled multi-tenant security, finance logic, migrations and permissions. A fast generated prototype is not a substitute for those foundations.

Lovable may be evaluated later for a disposable concept prototype or a specific experiment if it demonstrably saves time and the output can be reviewed and incorporated cleanly. It should not independently own the production codebase or become a required subscription at this stage.

No Lovable subscription is approved or required by this blueprint.

### 39.16 Engineering repository and documentation structure

Proposed repository structure (subject to refinement during project bootstrap):

- apps/web — Next.js web application.
- apps/mobile — Expo/React Native mobile application when started.
- packages/ui — shared web components and design tokens where practical.
- packages/types — shared domain types.
- packages/validation — shared validation schemas.
- packages/config — linting, TypeScript and formatting configuration.
- supabase/migrations — version-controlled database migrations.
- supabase/functions — server-side functions.
- tests/unit — unit tests.
- tests/integration — integration tests.
- tests/e2e — browser end-to-end tests.
- docs — technical specifications and runbooks.

Required project documentation:

- [AGENTS.md](http://AGENTS.md) — project-wide instructions for Codex and coding agents.
- [README.md](http://README.md) — setup, run and contribution instructions.
- PRODUCT\_[REQUIREMENTS.md](http://REQUIREMENTS.md) — approved product scope and feature requirements.
- SYSTEM\_[ARCHITECTURE.md](http://ARCHITECTURE.md) — system components and data flow.
- DATABASE\_[SCHEMA.md](http://SCHEMA.md) — entities, relationships, constraints and tenant ownership.
- PERMISSIONS\_[MATRIX.md](http://MATRIX.md) — role, action and resource permissions.
- INTEGRATION\_[REGISTER.md](http://REGISTER.md) — providers, credentials by environment, contracts and failure behaviour.
- DESIGN\_[SYSTEM.md](http://SYSTEM.md) — tokens, components and design rules.
- TEST\_[STRATEGY.md](http://STRATEGY.md) — test levels, environments and acceptance rules.
- [SECURITY.md](http://SECURITY.md) — security controls and threat considerations.
- BACKUP\_AND\_[RECOVERY.md](http://RECOVERY.md) — backup schedule, restore steps and recovery objectives.
- DEPLOYMENT\_[RUNBOOK.md](http://RUNBOOK.md) — release, rollback and environment configuration.
- INCIDENT\_[RESPONSE.md](http://RESPONSE.md) — severity, ownership, communication and recovery.
- DATA\_RETENTION\_AND\_[EXPORT.md](http://EXPORT.md) — school data ownership, portability, retention and offboarding.
- [CHANGELOG.md](http://CHANGELOG.md) — meaningful release history.

### 39.17 Feature traceability and anti-mistake control

Every feature must receive a unique requirement ID, for example MYE-ACAD-014.

Each requirement record must contain:

- Requirement ID and title.
- Business problem and user outcome.
- User roles and permissions.
- Parent module and related screens.
- Workflow and state transitions.
- Database entities and relationships.
- API/server actions and validation.
- External integration dependencies.
- Security and privacy requirements.
- Failure, retry and recovery behaviour.
- Analytics and monitoring events where appropriate.
- Unit, integration and end-to-end tests.
- Acceptance criteria.
- Documentation and support implications.
- Status, reviewer and release version.

<b>Example: teacher submits assessment marks</b>

Dependencies:

- Authenticated user and active school membership.
- Teacher role and explicit teaching assignment.
- Academic session and term.
- Class and class arm.
- Subject assignment.
- Student enrolment in that class and session.
- Assessment configuration and maximum mark.
- Grading rules and submission window.

Connected modules:

- Teacher workspace.
- Class/subject management.
- Student academic record.
- Assessment and result calculation.
- Approval/publication workflow.
- Audit history.
- Parent/student result visibility only after publication.

Required tests:

- Teacher cannot submit for a school they do not belong to.
- Teacher cannot submit for an unassigned class or subject.
- Student must be enrolled in the selected class/session.
- Mark cannot exceed the configured maximum or violate grading rules.
- Duplicate submissions are handled safely.
- A submitted or published result cannot be silently overwritten.
- Corrections follow the configured authorisation process.
- Audit history records the actor, time and change.
- Parent sees only their linked child's published result.

Apply this traceability approach to every module, not only academics.

### 39.18 Testing and quality gates

<b>Code-level checks</b>

- Formatting and linting.
- Type checking.
- Unit tests for business rules.
- Integration tests for database and service interactions.
- Migration validation.
- Dependency and secret scanning.
- Build checks.

<b>Product-level tests</b>

- Role-based access tests.
- Cross-school tenant isolation tests.
- Parent-child relationship tests.
- Student historical record tests.
- Fee calculation and invoice tests.
- Payment webhook and reconciliation tests.
- Duplicate event and notification tests.
- Import validation and duplicate detection.
- Export accuracy tests.
- Offline sync and conflict tests when offline features are introduced.
- Accessibility and responsive-layout tests.
- Browser and real-device regression tests.

<b>Release gates</b>

- No critical or high-severity unresolved security issue.
- All required tests pass.
- Database migrations reviewed.
- Backup/recovery readiness confirmed for the release risk.
- Sentry release and alerting configured.
- Sensitive data excluded from analytics/error payloads.
- Approved Figma design checked against the implementation.
- Rollback plan available.
- Pilot/school acceptance criteria met before general release.

### 39.19 Privacy, security and child-data safeguards

ACADIVA handles children's personal data and sensitive school and financial records. Security and privacy must be designed into the system.

Required work:

- Assess obligations under the Nigeria Data Protection Act and applicable NDPC guidance.
- Define school and ACADIVA responsibilities contractually, including controller/processor roles where applicable.
- Publish clear privacy notices and data-processing terms.
- Define lawful purpose, data minimisation, access, retention and deletion.
- Establish guardian and child-data handling rules.
- Restrict staff access to the minimum required for their duties.
- Keep student photos and documents private by default.
- Protect exports and bulk downloads.
- Use TLS/HTTPS and secure secret management.
- Avoid logging passwords, tokens, payment credentials or sensitive student data.
- Review Sentry and PostHog data capture and redact sensitive fields.
- Define incident response, breach escalation and school notification processes.
- Provide school data export and secure offboarding.
- Test restore and business continuity.
- Arrange an independent security review before scaling to significant live school usage.

Legal interpretation and compliance sign-off must be validated with an appropriately qualified Nigerian data-protection professional; this technical blueprint is not a legal opinion.

### 39.20 Backup, recovery and business continuity

- Define database backup frequency and retention based on school data criticality.
- Maintain an independent encrypted backup copy where feasible.
- Define file/object backup and recovery separately from database backup.
- Restrict backup credentials and access.
- Monitor backup job success and failures.
- Test full and partial restore.
- Record recovery time and maximum acceptable data loss objectives.
- Document what happens if Supabase, Netlify, DNS, SMS, email or the payment provider is unavailable.
- Provide manual fallback procedures for critical school operations.
- Keep deployment rollback and database rollback strategies distinct; database changes may not be safely reversible by simply reverting application code.
- Never promise an uptime or recovery commitment that the infrastructure and operating team cannot support.

### 39.21 Operational tools and support processes

- Maintain an issue register with severity, school, module, owner, evidence and resolution.
- Separate product bugs from school configuration problems, training needs and third-party outages.
- Use Sentry issue links and release information when diagnosing errors.
- Use PostHog workflow evidence to identify usability problems without exposing personal data.
- Track provider incidents and failed integrations.
- Maintain school onboarding checklists and configuration records.
- Record support response and resolution times.
- Maintain internal runbooks for common problems.
- Provide clear school-facing status communication during incidents.
- Keep a change log for features, fixes and known limitations.

### 39.22 Phased procurement and implementation

<b>Phase 0 — Design and foundation</b>

- Finalise product requirements and module map.
- Complete UI/UX research and Figma design system.
- Confirm domain and hosting direction.
- Create GitHub repository and engineering rules.
- Design database and tenant isolation.
- Configure development/staging/production strategy.
- Configure Sentry from the beginning of application development.
- Configure automated code checks and baseline tests.

<b>Phase 1 — Core school foundation</b>

- School registration and school identity.
- School subdomain resolution.
- Authentication and Google OAuth.
- School memberships, roles and permissions.
- Audit logging.
- Student, guardian, staff and academic structure.
- Core admin and proprietor workspaces.

<b>Phase 2 — Daily school operations</b>

- Admissions and student records.
- Classes, arms, subjects and teacher assignments.
- Attendance and timetable.
- Assessment, grading and result workflows.
- Reports, exports and historical records.

<b>Phase 3 — Finance</b>

- Fee structures, invoices and payment records.
- Paystack sandbox and live integration after verification.
- Receipts and reconciliation.
- Wallet-inspired parent payment experience.
- Finance dashboard and audit controls.

<b>Phase 4 — Communication</b>

- Email provider integration.
- SMS provider integration.
- Notification templates and queues.
- Parent announcements and PTA communications.
- Delivery logs, quotas and cost controls.

<b>Phase 5 — Mobile and offline</b>

- Expo/React Native application.
- Teacher and parent mobile workflows.
- Push notifications.
- Offline attendance and marks.
- Secure local cache, sync, duplicate prevention and conflict resolution.
- App-store distribution when approved.

<b>Phase 6 — Scale and advanced operations</b>

- Advanced monitoring and operational reporting.
- Additional school modules.
- Multi-campus and enterprise capabilities.
- Infrastructure capacity review and paid upgrades when justified.
- Formal security review, recovery exercise and service commitments.

The sequence is provisional; validate it against school research, dependencies and pilot priorities.

### 39.23 Procurement and account-security rules

- Create accounts using a controlled founder/company email address.
- Use multi-factor authentication on GitHub, domain registrar, hosting, Supabase, Figma, Notion, payment provider and messaging provider.
- Use a password manager; do not store secrets in Notion, source code or chat.
- Enable recovery codes and keep them securely.
- Ensure the founder/company owns the domain, GitHub organisation, production database, hosting and payment accounts.
- Use least-privilege team access.
- Keep development and production credentials separate.
- Rotate secrets after suspected exposure and when access is removed.
- Document billing owner, renewal date, plan, usage limit and cancellation/recovery process for each paid service.
- Do not purchase subscriptions until the phase needs them and the free/low-cost alternative has been assessed.
- Review vendor terms, data location, subprocessors, export and deletion options before putting real school data into a service.

### 39.24 Explicit decision: Lovable

<b>Current recommendation: Lovable is not required for ACADIVA's primary development workflow.</b>

The preferred toolchain is Figma for design, GitHub for source control, Codex/ChatGPT Plus for engineering assistance, Supabase for backend/data, and Netlify as the initial web-hosting candidate.

Lovable may be tested for a disposable concept prototype only if it offers a specific advantage. It must not become a second production source of truth or generate an unreviewed parallel codebase.

No Lovable subscription is approved or required at this stage.

### 39.25 Open decisions that must be resolved

- Final ACADIVA domain and registrar.
- Final choice between Netlify and Vercel after a small deployment validation.
- Whether Cloudflare manages DNS and which security features are appropriate.
- Exact Supabase project/environment plan and backup destination.
- Final SMS provider after Nigerian route, sender-ID, DND and price tests.
- Final transactional email provider.
- Final payment provider and school settlement model.
- Exact Sentry plan, event volume and privacy configuration.
- PostHog deployment/hosting and privacy configuration.
- Uptime monitoring provider.
- Final web/mobile monorepo structure and shared package boundaries.
- Final grading, approval and result correction rules.
- Final school role/permission matrix.
- Mobile app packaging and app-store release strategy.
- Exact offline scope and conflict-resolution policy.
- Data retention, deletion and school offboarding rules.
- Legal and data-protection review.
- Actual vendor quotations and projected monthly cost.

### 39.26 Guiding principle

ACADIVA must be designed as one connected, documented and testable system. A tool is not included because it is popular; it is included because a defined product or operational requirement needs it. A feature is not complete because its screen exists; it is complete when the right users can use it, the right records are changed, the wrong users are denied, integrations behave safely, errors are observable and acceptance tests pass.

The desired visual experience is premium, simple, editorial and distinctive: confident typography, a considered gradient identity, restrained glassmorphism, exceptional spacing, accessible information hierarchy and a particularly polished wallet-inspired finance experience. The product must avoid generic AI-generated dashboard styling and must be designed from researched references, complete workflows and a consistent component system.

The objective is not to buy every tool immediately. It is to establish the full architecture now, procure only what each development phase needs, and keep every component connected to the correct part of ACADIVA.

---

## 45. ACADIVA Operations — Founder Master Control, CTO Governance and Centralised School Onboarding — 15 November 2026

### 45.1 Purpose and product decision

ACADIVA will include an internal operations workspace called <b>ACADIVA Operations</b> as part of the main ACADIVA website and product ecosystem. It is designed for the ACADIVA company team, not for school employees or parents. It has its own protected route group, navigation, access policies and interface, but it belongs to the same main product and shared application architecture. Its purpose is to let a small startup onboard and support schools even when the school does not have the time, confidence or capacity to configure the system itself.

ACADIVA Operations is an operational control centre, not merely an analytics dashboard. Authorised internal staff can configure school workspaces, onboard users, import student records, assist school staff and resolve operational issues across multiple schools.

The school-facing ACADIVA application remains the authoritative school operating system. ACADIVA Operations performs permitted administrative actions against those same authoritative records; it must not create shadow copies of school data.

### 45.2 Three levels of authority

1. <b>Founder Master Control:</b> founder-only authority over internal employee access, CTO approval, suspension/revocation, company-wide operational policy and emergency access controls.
2. <b>CTO Master Operations:</b> cross-school operations access granted only after explicit founder approval. The CTO can onboard and support schools within assigned internal permissions.
3. <b>School workspaces:</b> school-owned operational spaces used by proprietors, principals, administrators, bursars, teachers and parents under school-specific permissions.

The CTO is an internal ACADIVA employee role, not a school role. CTO permissions must not be confused with proprietor, principal or school administrator permissions.

### 45.3 CTO registration, founder approval and account security

The CTO registration process is:

1. A prospective CTO opens the internal registration page and submits their name, work email and required identity/employment details.
2. The system creates a pending registration request. Pending applicants cannot access school data or the CTO dashboard.
3. ACADIVA sends an approval notification and a single-use, time-limited approval OTP to the founder-controlled email address configured for this purpose. The initial designated address is [<b>adebimpe476@gmail.com</b>](mailto:adebimpe476@gmail.com).
4. The founder signs in to Founder Master Control, reviews the request and explicitly approves or rejects it. The email OTP confirms the approval action; it does not replace founder authentication or act as a shared login credential.
5. The CTO separately verifies their own email, establishes their own credentials and configures MFA.
6. Only after founder approval and the CTO's own verification/security setup does the account become active.

Security rules:

- Only the founder can approve, suspend or revoke CTO accounts.
- A CTO cannot approve another CTO, create founder-level accounts or alter founder recovery settings.
- Founder approval challenges are separate from the CTO's login and email-verification codes.
- The founder's email is an approval/alert destination, not a shared password, shared login or universal authentication channel.
- Approval challenges must expire, be single-use and be rate-limited.
- Require MFA for CTO access; support secure recovery and session revocation.
- Founder Master Control must provide an emergency suspension action that invalidates active CTO sessions.
- Record registration, approval/rejection, authentication events, MFA changes, suspension and revocation in an immutable audit history.
- The founder's own account needs strong MFA and a recovery route independent of CTO access.

The designated email is a configuration value, not a hard-coded address embedded throughout the application. It can be changed only by the founder through a protected process.

### 45.4 Founder Master Control

Founder Master Control should provide:

- Pending CTO registrations and approval/rejection controls.
- Active, suspended and revoked internal accounts.
- Immediate CTO suspension/revocation and session invalidation.
- Company-wide school directory and operational overview.
- School activation policy and exceptions requiring founder review.
- Internal role/permission management.
- Privileged-access and audit-log review.
- Security alerts and emergency incident controls.
- Configuration of the founder notification/approval email.
- A record of founder decisions and changes.

The founder account is the ultimate authority for internal ACADIVA access. This does not mean the founder should casually bypass school ownership, privacy, approval or audit requirements.

### 45.5 CTO Master Operations dashboard

The CTO dashboard should be work-oriented and include:

- Overview of total schools, active/pending/suspended schools and onboarding progress.
- Searchable school directory with filters and school status.
- School switcher to move between school workspaces without repeated sign-in.
- Pending school approvals and school verification tasks.
- Onboarding queue and incomplete setup tasks.
- User onboarding queue and bulk-import status.
- Operational exceptions, support requests and failed synchronisation/import jobs.
- Recent privileged actions and audit activity.
- Access to school configuration and permitted user/record management.

When operating inside a school, show a persistent banner such as <b>ACADIVA Internal Access — Operating on behalf of \[School Name\]</b>. The active school and current privilege context must always be obvious.

### 45.6 School approval and activation

Keep these states distinct:

- <b>Registered:</b> a school account/request exists.
- <b>Verification pending:</b> school identity, authority or required details need checking.
- <b>Verified:</b> required checks have been completed.
- <b>Approved:</b> ACADIVA has authorised the school to use the service.
- <b>Active:</b> the school workspace is enabled.
- <b>Setup in progress:</b> initial configuration/onboarding is incomplete.
- <b>Ready for use:</b> required configuration and representative checks are complete.
- <b>Suspended/closed:</b> access is restricted under a documented policy.

An authorised CTO may approve and activate a school under company policy. Founder-configured rules may reserve specified school categories, exceptions or high-risk cases for founder approval. Auto-approval must never silently bypass identity checks, consent, required school details or security controls.

### 45.7 Centralised school onboarding

The CTO should be able to perform initial setup for a school, including:

- Create/configure school profile, logo, address, contact details and school subdomain.
- Configure academic sessions, terms, levels, classes and arms.
- Configure subjects, grading rules and assessment components.
- Configure fee categories and school fee structures.
- Create proprietor, principal, vice-principal, administrator, registrar, bursar and other staff profiles.
- Create teacher accounts and assign approved classes/subjects.
- Create student Applicant profiles and convert accepted/enrolled students without duplicate records.
- Create/link parent or guardian accounts to the correct children.
- Import student/staff lists from CSV/XLSX with column mapping, preview, validation, duplicate checks and error reports.
- Configure initial timetable and other agreed school settings.
- Track missing information, unresolved exceptions and school sign-off.

Bulk imports must be staged. The CTO reviews the preview and validation errors before committing. Failed or partial imports must be recoverable and safe to retry without creating duplicate accounts or student records.

The school remains responsible for the truth and authority of the data it supplies. A school representative must review and confirm critical records and settings before the workspace is treated as ready for normal use.

### 45.8 Acting on behalf of school staff

ACADIVA Operations may provide a controlled <b>Act on Behalf</b> capability so the CTO can help a school employee complete an operational task. This is not silent impersonation.

Required controls:

- Select the school and the specific employee/role being assisted.
- State the reason for intervention.
- Grant only the minimum required action permissions and only for the required duration.
- Display a persistent banner that the CTO is acting through an authorised delegated session.
- Record the CTO as the actual actor and the represented employee separately.
- Log each action, affected record, timestamp, reason and school.
- Automatically expire the delegated session and allow immediate termination.
- Never make an action appear to have been personally performed by a teacher, bursar or principal when it was performed by the CTO.

For high-risk actions—publishing results, confirming or altering financial records, issuing official transcripts, changing sensitive student information or making irreversible decisions—the school-authorised approver remains responsible unless a separately documented emergency policy explicitly allows intervention. Operational convenience is not a reason to remove school accountability.

### 45.9 Permissions, privacy and audit

The CTO has broad operational capability, but access must still be purpose-limited and accountable.

- Internal employee identity and permissions are separate from school user identities and roles.
- Enforce school tenant isolation in server-side authorisation and database policies, including Supabase Row Level Security where applicable.
- Never rely on hiding interface controls as the security boundary.
- CTO access to student, guardian and financial records must be limited to operational need.
- Log sensitive record views, edits, imports, exports, deletions, permission changes and delegated actions.
- Restrict bulk export/download and require a recorded reason where appropriate.
- Never expose passwords, OTPs, authentication tokens or raw credentials to CTOs.
- Respect school data ownership, consent, retention, correction and offboarding requirements.
- Revoke internal access immediately when employment or authorisation ends.
- Test cross-tenant access, privilege escalation, expired delegated sessions, revoked accounts and bulk-operation recovery.

### 45.10 Application and data architecture

ACADIVA Operations and school-facing workspaces are distinct protected areas within the main ACADIVA website and product ecosystem. They share the core identity, data model and backend services where appropriate, but internal operations has its own role boundary, protected routes, navigation and privileged server-side actions. Internal and school identities/permissions must remain distinct even when a person is authorised for more than one context. Internal operations must use controlled server-side functions and scoped permissions.

Do not give the CTO browser session or application code unrestricted database/service-role credentials. Privileged actions must pass through auditable server-side operations. The internal application must not bypass normal validation, business rules, tenant boundaries or authoritative record workflows.

The school-facing application remains the source of truth for school records. Dashboards in both applications are views over those records, not independently editable duplicates.

### 45.11 Initial release requirements

Build the following in the initial ACADIVA Operations release:

- Separate internal operations login and workspace.
- Founder Master Control with founder-only CTO approval, suspension and revocation.
- CTO registration request, founder notification/approval, separate CTO email verification and MFA.
- School directory, school switcher and clear active-school context.
- School approval/activation and onboarding progress.
- Create and onboard school leadership, staff, teachers, students and guardians.
- CSV/XLSX import with preview, validation, duplicate detection and safe commit.
- Configure academic structure, teacher assignments and essential school settings.
- Controlled delegated assistance with visible attribution, reason, expiry and audit trail.
- Cross-school tenant isolation and privileged-access audit logging.

Later, based on operational volume and team size:

- Separate sales/onboarding/support employee roles with narrower permissions.
- Advanced support ticketing and operational analytics.
- More granular approval policies and maker-checker workflows.
- Automated onboarding templates and repeatable school setup playbooks.

### 45.12 Acceptance criteria

- A prospective CTO cannot access ACADIVA Operations before founder approval.
- Only the founder can approve or revoke CTO access.
- The founder receives the approval request at the configured address; the CTO's own authentication codes remain separate.
- A CTO must complete their own email verification and MFA.
- A suspended/revoked CTO immediately loses access, including active sessions.
- The CTO can find a school and switch context without confusing internal and school identities.
- A school can be onboarded from setup through leadership, staff, teacher, student and guardian records.
- Bulk import previews errors and duplicates before commit and can be safely retried.
- A CTO's delegated action is attributed to the CTO, not falsely to the represented staff member.
- Delegated access expires and leaves a complete audit trail.
- A CTO cannot access another school's records outside the authorised operations workflow.
- A parent/guardian remains limited to linked children; teachers remain limited to assigned classes/subjects.
- High-risk school actions retain the required school-authorised approval.
- Founder can review privileged activity and immediately suspend internal access.
- School records created through ACADIVA Operations appear in the correct school workspace from the same authoritative data source.

### 45.13 Open decisions to validate before implementation

- Whether the internal title shown in the product should be CTO only or a broader Operations Admin title, while preserving the requested founder-controlled approval model.
- Whether the founder approval challenge should use email OTP, a signed one-time approval link, or both. Prefer phishing-resistant MFA for founder login and a separate one-time approval confirmation.
- Whether future sales/onboarding employees need limited versions of the same tools.
- Which school actions require school representative confirmation before go-live and which can be completed under a signed onboarding mandate.
- Legal, privacy and contractual wording for ACADIVA staff access to school and child records.

### 45.14 Relationship to the master checklist

Section 40 has been extended with <b>Section Z — ACADIVA Operations</b>, containing dedicated implementation and acceptance checks for founder authority, CTO registration and approval, school onboarding, bulk imports, delegated actions, tenant isolation, audit logging and emergency access revocation.

Section 45 defines the product and governance requirements; Section 40Z is the execution checklist. Both must be used. A dashboard mockup or working login alone does not count as completion.

---

## 48. ACADIVA Integration and External Service Register — 15 November 2026

### 48.1 Why this register exists

ACADIVA cannot be planned only as screens, roles and database tables. Every real workflow depends on infrastructure and external services. This section records the capabilities ACADIVA needs, the current preferred/candidate providers, what each provider does, what it does not do, and the decisions still requiring validation.

A provider appearing here does not mean an account has been purchased, connected or production-approved. Vendor selection, pricing, free-tier limits, legal terms, security, data location, support and integration testing must be checked before launch.

### 48.2 Communication architecture — separate channels, one event record

ACADIVA uses three complementary communication layers:

1. <b>Transactional email — Resend (preferred candidate):</b> outbound application-generated emails such as account invitations, email verification, password reset, admission updates, receipts, report publication notices and selected school communications.
2. <b>SMS — Nigerian SMS provider (Termii / Africa's Talking candidates):</b> concise, important messages to parents and staff, particularly where parents may not open an app or have mobile data. Provider, sender ID, pricing, delivery receipts and regulatory requirements must be validated.
3. <b>In-app notification centre:</b> persistent notices, unread state and message history inside each authorised workspace/parent portal.

The channels must be connected to one authoritative ACADIVA event/announcement, with separate delivery attempts and states. An email or SMS delivery failure must not erase the school notice or falsely mark the underlying action complete.

Push notifications may be added when a native mobile app exists; they are not a substitute for SMS for parents who do not open the app.

### 48.3 Resend — transactional email service

<b>Decision:</b> Explicitly include Resend in the ACADIVA integration plan as the preferred transactional email provider to evaluate and integrate for outbound system email. It is not merely an optional generic mention in a technology table.

Expected ACADIVA use cases:

- Email verification and account activation.
- Password reset and account recovery messages.
- Founder-approved CTO access/approval notifications and security alerts (without sending passwords or reusable secrets).
- Staff invitations and role/assignment notifications.
- Parent admission application confirmation, status updates and admission offers.
- Payment receipts and finance notifications where the parent has an email address and the school enables email.
- Result/report-card publication notifications, without exposing private results in the email body by default.
- PTA invitations, school announcements and selected reminders.
- Operational alerts to authorised ACADIVA employees.

Implementation requirements:

- Use a verified ACADIVA sending domain or appropriately configured sending subdomain; protect existing domain email records and do not change MX records casually.
- Configure and verify SPF, DKIM and DMARC according to Resend's current domain instructions.
- Use server-side API calls only. Keep API keys in environment secrets; never expose them in browser/mobile code, source control or client logs.
- Use domain-scoped sending keys where supported and separate development/staging/production credentials.
- Create reusable branded templates. React Email is the preferred template-authoring option to evaluate because it supports component-based, previewable email templates and can render HTML and plain text. It is a template tool, not a delivery provider.
- Maintain a consistent ACADIVA/school identity, accessible layouts, plain-text alternatives and mobile-friendly rendering. Test Gmail, Outlook, Apple Mail and other relevant clients.
- Store an internal notification/event ID and Resend message ID, recipient, template/version, school, trigger, timestamp and delivery state.
- Process provider delivery, bounce, complaint and failure webhooks securely; verify webhook signatures, handle duplicate events idempotently and retain only the delivery metadata/content needed for support and compliance.
- Implement suppression and bounce handling. Do not repeatedly send to invalid addresses or continue sending after a complaint/unsubscribe where applicable.
- Use queues/retries with limits and backoff. Avoid duplicate emails when a workflow is retried.
- Email content should not expose sensitive student data, grades, full financial details or private documents unnecessarily. Prefer authenticated portal links for sensitive records.
- Monitor delivery, bounce/complaint rates, provider errors, quotas and cost. Set alerts before limits affect school operations.

<b>Important boundary:</b> Resend is an outbound transactional email API. It is not a normal staff mailbox/hosted inbox service. ACADIVA may separately need a human email-hosting provider for addresses such as support@, admissions@ or accounts@. That is a separate vendor and decision. Inbound email processing or email-triggered automation is not required for the initial release unless a separately approved workflow needs it.

### 48.4 SMS service

Required capability: send SMS to verified/appropriately authorised guardian and staff phone numbers in Nigeria.

Candidates to evaluate: Termii and Africa's Talking; do not assume either is selected until current local coverage, pricing, sender ID registration, delivery receipts, support and API terms are checked.

Required features:

- School-specific sender identity where approved and supported.
- Message templates with school name and clear wording.
- Recipient selection based on verified guardian links and school policy.
- SMS length/encoding and multipart cost awareness.
- Delivery status where provider supports it.
- Failed-message visibility, bounded retry and duplicate suppression.
- Per-school usage and cost tracking, budget/low-balance alerts and agreed billing treatment.
- Consent/preferences, opt-out and sender compliance appropriate to message type and local regulation.
- No sensitive report-card details or private financial data in plain SMS.
- Secure short-lived or authenticated links for actions requiring portal access.

SMS is not guaranteed to work without all connectivity: the parent needs cellular coverage and the provider needs a working route. Its key advantage is that the parent does not need mobile data or to open the ACADIVA app to receive a text.

### 48.5 Payments

Required capability: accept/verify supported electronic school-fee payments, record references, receive signed provider webhooks, reconcile settlements, process permitted refunds/reversals and report provider charges.

Candidates: Paystack as the first provider to evaluate; Flutterwave as an alternative or later additional provider if a real school/business case justifies it.

Requirements:

- Confirm the correct school merchant/settlement arrangement and account ownership.
- Do not pool or hold school funds by default.
- Verify transactions server-side and via provider webhooks; never trust a browser redirect as proof of payment.
- Make webhook handling idempotent and reconcile provider transaction IDs to ACADIVA payment records.
- Separate initiated, pending, successful/settled, failed, reversed and refunded states.
- Track gateway fees, net settlement, unmatched items and reconciliation differences.
- Keep manual cash/bank entries distinct from provider-confirmed payments.
- Do not store card numbers, CVV or raw payment credentials in ACADIVA.
- Confirm provider availability, school onboarding/KYC requirements, transaction fees, settlement times, refund support and dispute handling before launch.

### 48.6 Identity, access and account recovery

Preferred direction: Supabase Auth for user identity, sessions, password recovery and supported OAuth such as Google sign-in, with ACADIVA's own school memberships, roles, assignments and server-side permissions.

Requirements:

- Email/phone verification appropriate to the login method.
- Secure invitation acceptance and account linking.
- Password reset and recovery that does not expose whether sensitive accounts exist unnecessarily.
- MFA for founder and privileged internal accounts; additional staff MFA policy to be defined.
- Session revocation on suspension, role removal and account compromise.
- Safe handling of changed/lost phone numbers and inaccessible email accounts.
- Audit events for invitations, role changes, recovery and privileged actions.
- Parent identity and guardian-child linking must not rely on knowing a student's name or admission number alone.

Google sign-in is an authentication method, not a notification channel.

### 48.7 Database, storage, files and exports

Preferred direction: Supabase PostgreSQL and Supabase Storage initially.

Requirements:

- PostgreSQL is the authoritative store for structured school records and financial/academic relationships.
- RLS and server-side checks enforce tenant isolation.
- Private storage buckets and signed, expiring links protect student photos, admission documents, report cards and other private files.
- Define file size/type limits, upload validation, malware/scanning strategy where appropriate, retention, access logs and deletion/erasure workflows.
- Optimise images and thumbnails; do not store unnecessarily large originals for routine display.
- Generate PDFs and exports through controlled server-side processes with permission checks, version metadata and audit logs.
- Provide school data export and offboarding capability in documented formats.
- Backups must be independent of ordinary user storage and include a tested restore process. Free-tier provider availability must not be treated as a backup strategy.

### 48.8 Hosting, domains and delivery pipeline

Working direction:

- Netlify as the initial web hosting/deployment candidate, subject to framework compatibility, usage limits, cost and operational review.
- Cloudflare as DNS and potential edge-security/WAF provider candidate.
- A reputable registrar owns the domain registration; the company must control registrar access, renewal and recovery.
- GitHub stores source code, review history and CI workflow.
- Separate development, staging and production environments; staging must not contain real children's data by default.

Requirements:

- Automated checks and preview deployment before production.
- Protected production deployment and controlled environment secrets.
- Custom school subdomains routed to the correct tenant using server-verified school context.
- HTTPS, secure headers, DNS ownership protection and renewal alerts.
- Database migrations, rollback/forward-fix procedures and release notes.
- Uptime monitoring and incident alerts.
- Avoid choosing two production hosting providers without a specific architecture reason.

### 48.9 Monitoring, analytics, support and operational reliability

Preferred/candidate capabilities:

- Sentry for application errors and performance diagnostics.
- PostHog for product usage, activation and workflow completion; configure privacy controls and exclude sensitive student/guardian data from event payloads.
- One uptime monitor, such as Better Stack or UptimeRobot, selected after reviewing free limits and alert channels.
- A support/issue workflow for school-reported problems, internal assignment, status, response and resolution history. This can begin as a simple internal tool/workspace before purchasing a separate helpdesk product.

Requirements:

- Track school onboarding completion and first successful attendance/results/finance workflows.
- Monitor failed imports, stuck notification jobs, failed webhooks, payment reconciliation exceptions, database/storage quota and backup status.
- Define incident severity, owner, escalation, school communication and recovery procedures.
- Do not use session replay on sensitive screens unless the privacy review confirms safe masking and lawful use.
- Keep operational audit logs distinct from analytics events.

### 48.10 Later integrations, not day-one dependencies

- Expo push notifications when the mobile app is released.
- WhatsApp Business API only if schools demonstrate a need and provider cost, template approval, opt-in and policy requirements are viable.
- Advanced bank feeds or automated reconciliation if provider access and demand justify it.
- Dedicated human mailbox hosting for ACADIVA departments if required; separate from Resend.
- Helpdesk/ticketing provider if internal support volume outgrows the basic operations workflow.
- E-signature, identity/document verification, accounting exports or government integrations only after requirements are validated.

### 48.11 Provider decision register

| Capability | Current direction | Status |
| --- | --- | --- |
| Transactional email | Resend | Preferred provider to evaluate; explicitly included |
| Email templates | React Email | Preferred authoring option to evaluate; not a delivery provider |
| SMS | Termii / Africa's Talking | Candidates; compare Nigerian coverage, sender IDs, cost and delivery |
| Payments | Paystack; Flutterwave alternative | Candidates; validate settlement, KYC, fees and webhook behaviour |
| Authentication | Supabase Auth | Working direction |
| Database | Supabase PostgreSQL | Working direction |
| File storage | Supabase Storage | Working direction; private buckets and retention rules required |
| Web hosting | Netlify | Initial candidate; validate plan limits and framework support |
| DNS / edge security | Cloudflare | Candidate / recommended to evaluate |
| Source control / CI | GitHub | Required |
| Design | Figma | Required |
| Product documentation | Existing ACADIVA Notion blueprint | Required |
| Error monitoring | Sentry | Required before pilot |
| Product analytics | PostHog | Recommended with privacy controls |
| Uptime monitoring | Better Stack / UptimeRobot | Choose one |
| PDF generation | Server-side PDF generation capability | Required; library/vendor to select during technical design |
| Backup and restore | Independent backup plus tested restore process | Required; provider/implementation to validate |
| Staff email inboxes | Separate hosted mailbox provider if needed | Open decision; Resend does not provide this |
| Push notifications | Expo Notifications | Later, when native app exists |
| Customer support | Basic internal support workflow first | Required capability; dedicated vendor later if justified |

### 48.12 Integration governance and acceptance

Every integration must have:

- Named business purpose and owner.
- Provider, account owner and billing responsibility.
- Development/staging/production credentials stored securely.
- Data sent and received, lawful basis and retention.
- Authentication/signature verification and permission model.
- Timeout, retry, idempotency and duplicate handling.
- Failure state, alerting, manual fallback and reconciliation.
- Cost model, quota and usage alerts.
- Test environment/test cases and production acceptance criteria.
- Exit/migration plan so ACADIVA is not unnecessarily locked to one provider.

The system must not claim that an email, SMS, payment or file operation succeeded until the provider/server has returned the relevant result. Delivery is not the same as reading; payment initiation is not settlement; a saved record is not an approved record.

### 48.13 Open decisions

Before production, validate current Resend pricing/limits, sending-domain setup and webhook events; Nigerian SMS provider pricing, sender-ID registration and delivery coverage; Paystack/Flutterwave merchant and settlement requirements; Supabase backup/restore and storage limits; Netlify usage limits; Cloudflare DNS/security configuration; staff mailbox provider; PDF-generation library; and the support workflow.

No API keys, passwords, webhook secrets or payment credentials belong in the Notion blueprint or source code. Store secrets only in the approved secret-management/environment configuration and rotate compromised credentials.

### AC. Integration and external-service checklist

- [ ] AC01. Resend is explicitly listed as the preferred transactional email provider to evaluate for ACADIVA. (Core)
- [ ] AC02. Distinguish Resend transactional sending from staff mailbox hosting and inbound email processing. (Core)
- [ ] AC03. Define email event triggers: verification, recovery, invitations, admission, receipts, result notices and selected announcements. (Core)
- [ ] AC04. Configure a verified sending domain/subdomain and SPF, DKIM and DMARC according to current provider instructions. (Pilot)
- [ ] AC05. Keep Resend API keys server-side, scoped and separated by environment. (Core)
- [ ] AC06. Build reusable branded email templates with plain-text alternatives and client testing; evaluate React Email. (Core)
- [ ] AC07. Record internal event ID, provider message ID, recipient, template version and delivery status. (Core)
- [ ] AC08. Verify provider webhooks, handle duplicate events idempotently and process bounces/complaints safely. (Core)
- [ ] AC09. Implement email queueing, bounded retry, duplicate suppression and failure monitoring. (Core)
- [ ] AC10. Define email content rules to prevent exposing sensitive student, academic or financial data. (Core)
- [ ] AC11. Evaluate BulkSMS Nigeria as the initial SMS provider candidate and compare it with Termii and Africa's Talking for Nigerian coverage, pricing, sender ID approval, delivery receipts, API reliability, sandbox support and terms. (Pilot)
- [ ] AC12. Implement SMS usage/cost budgets, recipient rules, opt-out/preferences, delivery tracking and duplicate suppression. (Core)
- [ ] AC13. Connect email, SMS and in-app messages to one authoritative notification/event record. (Core)
- [ ] AC14. Evaluate Paystack and Flutterwave for school settlement, KYC, fees, refunds, webhooks and reconciliation. (Pilot)
- [ ] AC15. Verify all payments server-side and reconcile provider transaction IDs idempotently. (Core)
- [ ] AC16. Define authentication, account recovery, MFA and session revocation flows. (Core)
- [ ] AC17. Define private file storage, signed links, upload validation, retention and export. (Core)
- [ ] AC18. Establish independent backups and perform a documented restore test before onboarding real schools. (Core)
- [ ] AC19. Validate hosting, DNS, custom subdomains, HTTPS, environment secrets and deployment rollback. (Core)
- [ ] AC20. Configure Sentry, PostHog privacy controls and one uptime monitor. (Pilot)
- [ ] AC21. Define PDF generation and secure export service for report cards, receipts and student records. (Core)
- [ ] AC22. Define a support issue workflow for school onboarding, questions, incidents and resolutions. (Pilot)
- [ ] AC23. Assign a purpose, owner, cost model, data contract, failure behaviour and exit plan to every external integration. (Core)
- [ ] AC24. Test provider outage, webhook replay, delayed delivery, duplicate event, quota exhaustion and credential rotation. (Core)

---

## Section 49 — ACADIVA Finance: Zero-Additional-Service-Cost Strategy, Architecture Boundaries and Phased Delivery — 15 November 2026

### 49.1 Context and objective

The financial operating system is intended to become a major differentiator for ACADIVA. However, the product is being developed under a strict cost constraint. The founder does not want to purchase accounting software, subscribe to additional finance APIs or introduce paid infrastructure merely to build the initial finance capability.

<b>Decision:</b> Design and build the school-specific financial operating system inside ACADIVA using the existing application stack and open-source libraries wherever practical. Do not add a paid accounting platform, paid bank-feed provider or dedicated finance SaaS dependency to the initial release.

This is a zero-additional-service-cost strategy within available free-tier limits, not a claim that operating a production system is permanently cost-free. Existing hosting/database limits, payment gateway charges, SMS charges, domain costs, backup requirements and future usage may still create costs. Never hide these costs or assume a provider's free tier is unlimited.

### 49.2 Existing stack first

Use the existing ACADIVA technology direction rather than introducing another vendor solely for finance:

- Supabase PostgreSQL for structured financial records, relationships, constraints and transaction history, subject to free-tier limits and production-readiness checks.
- Existing Next.js application and server-side logic for finance workflows, validation, permissions and reports.
- Existing authentication and school membership model for role-scoped access.
- Open-source charting and table components already selected for ACADIVA where suitable; do not add a second UI kit or paid charting product.
- Server-side PDF and CSV generation using an appropriate open-source library selected during implementation.
- Supabase Storage only where supporting documents are required, using private storage, access controls and sensible size/retention limits.

Do not expose database service-role credentials or payment secrets in the browser. All sensitive financial mutations and provider verification must run through trusted server-side operations.

### 49.3 Capabilities to build internally before considering paid services

The initial ACADIVA finance experience should implement these capabilities inside the product:

1. School fee categories and fee schedules.
2. Student bills/invoices and itemised statements.
3. Instalment schedules, partial payments and outstanding balances.
4. Approved discounts, scholarships, waivers and concessions.
5. Manual cash and bank-transfer payment recording.
6. Explicit payment verification and correction workflows.
7. Payment allocation to the correct student, invoice and fee item.
8. Receipts and printable/exportable statements.
9. Expense recording, supporting evidence and approval rules.
10. Basic budgets and budget-versus-actual reporting, introduced after the core transaction model.
11. Financial summaries and term-based reports.
12. CSV import of bank statements and assisted reconciliation.
13. Financial term-close review and carry-forward of approved outstanding balances.
14. Audit history, role-based access and exception queues.

These are application capabilities, not separate paid services. They still require engineering, testing and ongoing maintenance.

### 49.4 Manual payment verification as the initial operating model

For the first release, schools may record cash and direct bank-transfer payments manually. ACADIVA must clearly distinguish an entry that has merely been recorded from money that has been verified as received.

Required controls:

- Record the student, payer where known, amount, date, payment method, reference and staff member entering the payment.
- Record verification separately, including verifier, time, evidence/reference and any required reason.
- Apply school-configured separation of duties where practical; the person entering a payment should not automatically be treated as its independent verifier.
- A screenshot or parent-provided transfer alert is supporting evidence only; it is not proof that funds reached the school's account.
- Only verified/settled payments count as confirmed collections and reduce confirmed outstanding balances according to the school's policy.
- Pending or unverified records remain visible as exceptions and must not silently create confirmed receipts or confirmed income.
- Corrections, reversals and refunds must retain the original transaction and create linked audit records.

Online payment gateway integration remains a later optional route. If enabled, the server must verify provider events and reconcile provider references idempotently. Payment initiation or a browser success page alone is not proof of settlement. Gateway charges are usage-based and must be disclosed separately; do not describe gateway processing as free.

### 49.5 CSV-based bank reconciliation before paid bank integrations

Initial bank reconciliation should not depend on direct bank APIs or paid bank-feed aggregators.

Proposed workflow:

1. An authorised finance user downloads a bank statement from the school's own bank using the bank's normal facilities.
2. The user uploads a supported CSV file to ACADIVA.
3. ACADIVA validates the file, displays the detected columns and asks the user to map date, amount, description/reference and debit/credit fields where necessary.
4. ACADIVA previews rows, flags invalid data and identifies possible duplicate imports before committing.
5. The system proposes matches against recorded school payments using available evidence such as amount, reference and date.
6. Each row is classified as matched, unmatched, possible duplicate, amount mismatch or requiring manual review.
7. An authorised finance user reviews and confirms matches or records an explanation for exceptions.
8. The imported statement batch, source filename, import actor, import time, row-level outcomes and reconciliation decisions are retained for audit.

Matching suggestions must never silently verify a payment. A human-authorised confirmation is required unless a later, explicitly approved and tested rule permits a narrowly defined automatic match. Imports must be idempotent or detect repeat uploads to prevent duplicate transactions.

The initial CSV approach is a practical manual workflow, not a claim of live bank connectivity or a replacement for a bank's official statement.

### 49.6 Financial integrity is non-negotiable even when spend is constrained

Reducing vendor spend must not weaken financial correctness. The following are minimum engineering requirements:

- A single authoritative financial record system per school; dashboards and parent statements are derived views, not independently editable balances.
- Tenant isolation and server-side permission checks on every read and write.
- Stable references and relationships between invoices, payments, allocations, adjustments, refunds, reversals, expenses and reconciliation batches.
- Database constraints and transaction-safe server operations to prevent partial or duplicated financial updates.
- Idempotency/deduplication for imports, payment events and retries.
- No silent hard deletion or overwriting of issued bills, verified payments, receipts or historical records.
- Corrections through linked adjustment, reversal, refund or reallocation entries, with actor, timestamp and reason.
- Explicit separation of recorded, pending, verified/settled, failed, reversed, refunded and disputed states as appropriate to each payment method.
- Approval thresholds and separation of duties for sensitive actions.
- Audit records for payment entry/verification, invoice changes, discounts, waivers, refunds, expense approvals, exports and reconciliation decisions.
- Secure handling of bank statement files and supporting documents, with restricted access and retention rules.
- Financial reports must distinguish billed amounts, verified collections, unverified entries, outstanding balances, expenses and actual available cash evidence. Gross collections must never be labelled profit.

### 49.7 Accounting model — decision still required before implementation

Section 47.2 already establishes a financial ledger as the authoritative basis for balances and reporting. However, the exact accounting model has not yet been fully decided.

Before implementation, technical/product design must determine whether the internal ledger will use a full double-entry journal from the first release or a simpler transaction subledger with a clearly defined path to double-entry accounting. This is an open design decision, not an already-approved commitment.

Whichever model is selected must support traceable source transactions, allocations, reversals, adjustments, reconciliation and reproducible balances. Do not implement balances as manually editable numbers or scatter independent balance calculations across dashboards.

The first release is a school-specific finance operations system. It is not represented as a full statutory accounting, tax filing, payroll or banking product. If schools require statutory accounting exports or a complete general ledger beyond the agreed scope, evaluate a later export/integration path rather than expanding the first release indiscriminately.

### 49.8 Cost boundaries and upgrade triggers

No additional paid finance service is approved for the initial build.

The following remain deferred unless a demonstrated requirement justifies their cost:

- Paid accounting software or accounting APIs.
- Direct bank feeds and automated bank account connections.
- Paid bank-statement aggregation.
- Automated payroll integrations.
- Advanced treasury, lending or school-wallet services.
- Paid financial analytics products.
- Automated payment gateway integration before the pilot requires it.
- Paid SMS for every routine financial event.

Do not treat transaction fees as software subscriptions: payment providers may charge per successful transaction or according to their current terms. SMS is also usage-based. Both require school-facing cost disclosure and budget controls.

Upgrade decisions must be based on measured limits, reliability, security, backup/restore needs, transaction volume and actual school demand—not on arbitrary feature ambition or school count alone.

<b>Backup qualification:</b> a free database tier is not automatically a safe backup strategy. Before real schools rely on ACADIVA's financial records, define an independent backup/export process, protect exported data, test restoration and confirm recovery objectives. If the available free arrangement cannot provide an acceptable and tested recovery path, the product must not pretend otherwise; the necessary backup cost must be assessed before production onboarding.

### 49.9 Phased delivery

| Stage | Scope | External finance-service spend |
| --- | --- | --- |
| 1. Core fees and payments | Fee setup, bills, student statements, manual payment entry, verification, allocations, receipts and balances | No additional finance service planned |
| 2. Expense controls | Expense records, evidence, approval thresholds and basic budgets | No additional finance service planned |
| 3. Reconciliation | CSV statement import, duplicate detection, suggested matching, human review and exception reporting | No paid bank integration planned |
| 4. Management finance | Collections, overdue balances, expenses, term comparisons, exports and financial close | No paid analytics service planned |
| 5. Optional integrations | Online payment gateway, SMS notifications, bank feeds or accounting exports if justified | Usage/provider costs may apply; approval required |

Build sequence must be validated against the shared product architecture and the first pilot school's actual finance workflow. The table is a staged roadmap, not a promise that all stages will be delivered before the first pilot.

### 49.10 Acceptance tests before finance pilot

The finance module is not ready for real school use until tests demonstrate at minimum:

- A bill is generated from an approved fee schedule and remains historically traceable after a later fee change.
- Partial payments produce the correct remaining balance.
- A payment entered but not verified does not count as confirmed collection or silently reduce the confirmed balance.
- Verification records the authorised verifier and supporting reference.
- A payment cannot be accidentally allocated to the wrong sibling or tenant.
- Repeated CSV import does not create duplicate statement transactions.
- Reconciliation suggestions do not verify payments without authorised confirmation.
- Reversals, refunds and reallocations preserve the original transaction and audit history.
- Expense approvals enforce the school's configured authority limits.
- Parent, bursar, principal and proprietor views show consistent server-confirmed balances within their permissions.
- An unauthorised user cannot read or alter another school's financial records, including by direct API requests.
- Backup restoration is tested and documented before real financial records are entrusted to the system.

### 49.11 Checklist 40AD — Finance cost-control and implementation checklist

- [ ] AD01. Keep the initial finance implementation inside the existing ACADIVA stack; do not purchase a separate accounting platform for the first release. (Core)
- [ ] AD02. Record every proposed finance vendor/API as optional until a validated requirement and cost-benefit decision exists. (Core)
- [ ] AD03. Implement fee categories, fee schedules, invoices and itemised student statements internally. (Core)
- [ ] AD04. Support instalments, partial payments, approved concessions and correct payment allocation. (Core)
- [ ] AD05. Implement manual cash/bank payment entry with separate recorded and verified states. (Core)
- [ ] AD06. Ensure unverified payments do not count as confirmed collections or silently reduce confirmed balances. (Core)
- [ ] AD07. Preserve issued bills, receipts and successful transactions through linked adjustments/reversals rather than silent deletion. (Core)
- [ ] AD08. Generate receipts, statements and finance reports using existing/open-source server-side capabilities. (Core)
- [ ] AD09. Implement expenses, supporting evidence and configurable approval thresholds without a paid expense-management vendor. (Pilot)
- [ ] AD10. Design and validate the ledger/accounting model before implementing production balance logic; explicitly decide whether double-entry is required from launch. (Core)
- [ ] AD11. Implement CSV bank-statement upload, column mapping, preview, validation and safe duplicate detection. (Pilot)
- [ ] AD12. Provide reconciliation suggestions and exception queues; never silently verify a payment solely because a CSV row appears to match. (Pilot)
- [ ] AD13. Track bank/provider reconciliation batches and row-level decisions with actor, date, source and audit history. (Pilot)
- [ ] AD14. Derive dashboards and parent balances from authoritative server-side financial records. (Core)
- [ ] AD15. Enforce tenant isolation, server-side permissions, transaction safety, idempotency and audit on all finance operations. (Core)
- [ ] AD16. Separate billed, collected/verified, unverified, outstanding, expenses and cash-position metrics; never label gross collections as profit. (Core)
- [ ] AD17. Define school-facing payment gateway and SMS cost disclosure before enabling usage-based services. (Core)
- [ ] AD18. Confirm backup, restore and recovery arrangements are acceptable and tested before a live finance pilot, even if this requires a separately assessed infrastructure cost. (Core)
- [ ] AD19. Test partial payments, duplicate imports, wrong-student allocation, reversal, refund, permission denial and cross-tenant isolation. (Core)
- [ ] AD20. Release finance progressively and use pilot evidence before adding paid bank feeds, accounting integrations, payroll or advanced finance products. (Core)

### 49.12 Relationship to existing decisions

Section 49 supplements Section 47.2's school financial operating system and Section 48's integration register. It does not remove or weaken their finance requirements. It establishes the cost boundary and a practical initial delivery method.

Where this section defers a paid integration, the underlying business requirement may remain on the roadmap. Where it introduces CSV-based reconciliation and manual verification, these are the initial operating choices pending pilot evidence. The open accounting-model decision in 49.7 must be resolved before production implementation.

Section 40AB remains the existing finance and lifecycle master checklist. Section 40AD adds the cost-control and implementation checks; neither checklist proves that code has been implemented or tested.

---

## 50-A — Provider-Independent SMS Architecture and BulkSMS Nigeria Integration — 16 November 2026 (originally numbered Section 50)

<b>Stable record ID:</b> 50-A. Original content is retained; this identifier resolves the duplicate original section number.

### 50.1 Purpose

SMS is a core parent-communication channel for ACADIVA, especially for attendance, urgent notices and time-sensitive school updates. The product must support SMS across multiple schools without requiring each school to create and configure its own SMS-provider account during initial onboarding.

This section converts the SMS requirement already recorded in Sections 47 and 48 into an explicit technical architecture and build checklist. It supplements the existing Notification Engine and integration register; it does not replace them.

### 50.2 Decision and provider strategy

<b>Initial provider candidate: BulkSMS Nigeria.</b> It provides an API and a sandbox environment suitable for integration testing. It is the first provider to implement against, subject to a short technical and commercial validation before production use.

<b>Architecture decision: provider-independent SMS service.</b> ACADIVA must not hard-code BulkSMS-specific behaviour throughout the application. Implement a shared SMS service/provider adapter so a second provider can be added or substituted without rewriting attendance, finance, admissions or notification workflows.

- Initial adapter: BulkSMS Nigeria.
- Future adapters: Termii, Africa's Talking or another provider only after coverage, pricing, sender-ID, delivery and terms have been assessed.
- Do not integrate multiple live providers at launch merely for theoretical redundancy.
- Keep the provider selection configurable server-side by environment; school-level provider selection is not required for the first release.
- ACADIVA initially manages the provider account centrally. Schools should not need their own BulkSMS API accounts to use ACADIVA SMS.

### 50.3 High-level architecture and event flow

1. A school action or system event occurs, such as a student being marked absent, a fee reminder becoming due or an urgent announcement being approved.
2. The application creates one authoritative notification event containing the school/tenant, event type, recipient, approved message/template, priority and source record.
3. The Notification Engine checks the school's channel settings, recipient contact/consent/preferences, message rules and available SMS allowance.
4. The SMS service creates a queued delivery job and passes it through the provider-independent adapter.
5. The BulkSMS Nigeria adapter sends the request from a trusted server-side environment using the configured API credential.
6. The provider response and message reference are stored against the internal notification/delivery record.
7. Delivery receipts or status callbacks update the delivery record through a verified, idempotent webhook handler.
8. The school can view sent, delivered, failed, pending and suppressed messages, together with usage and cost information.
9. Failed messages follow bounded retry and exception rules; retries must not create duplicate messages.

SMS must remain one channel in the shared Notification Engine alongside in-app notifications and email. A school event should not create separate, conflicting versions of the underlying notification in each channel.

### 50.4 Provider account, API and environment configuration

- ACADIVA operates one centrally managed BulkSMS Nigeria account for the initial rollout.
- Generate and configure the provider API token in the BulkSMS account.
- Store credentials only in server-side environment secrets; never expose them in browser code, mobile bundles, public repositories, logs or client-visible configuration.
- Separate development/test and production credentials and endpoints where the provider supports them.
- Use the BulkSMS sandbox endpoint for integration testing. Sandbox tests must not send real SMS or deduct wallet funds.
- Confirm the current production endpoint, API version, authentication method, request schema, rate limits and error codes against the provider's current official documentation during implementation. Do not assume older examples use the same authentication format as the current API.
- Configure an approved sender ID. A proposed name such as SCHOOLOS must not be assumed available until provider/network registration and approval are confirmed.
- Store provider configuration centrally and support credential rotation without code changes.
- Do not put API tokens in school settings or ask individual schools to paste provider secrets into their portals.

### 50.5 School-level SMS wallet, metering and pricing rules

SMS is a metered, usage-based service. ACADIVA must track each school's consumption even though the initial provider account is centralised.

<b>Previously agreed commercial rule:</b>

- Include a limited first-time activation SMS allowance as part of school onboarding.
- After activation, routine SMS usage is paid for by the school through an SMS credits/wallet mechanism.
- Essential security messages must be protected and must not be casually blocked by routine-message balance exhaustion.
- Keep the actual provider cost separate from the price charged to the school. Any ACADIVA margin must be explicit in the pricing model and visible in internal unit-economics reporting.

Implementation requirements:

- Maintain a school-level SMS ledger/usage account, not just a single global provider balance.
- Record message units/segments, destination, category, event, provider, provider cost where available, school charge, status and timestamp.
- Deduct or reserve school credits consistently and safely; prevent concurrent sends from overspending the same balance.
- Show the school its available credits, usage history, failed messages and applicable rate.
- Define how schools purchase/top up credits and how credit adjustments/refunds are audited before enabling paid production sending.
- Distinguish the central BulkSMS wallet balance from each school's ACADIVA SMS balance. The central provider wallet is funded by ACADIVA; school-level credits are ACADIVA's internal accounting and entitlement layer.
- Support school-specific budgets, low-balance warnings and configurable spending limits.
- Do not silently send unlimited routine SMS when a school's allowance is exhausted.
- Define the exact activation allowance, security-message policy, school selling price, provider-cost basis, margin and tax treatment before charging schools. These amounts are not yet fixed in this section.
- Account for SMS segmentation: a long message may consume more than one billable SMS unit. Estimate and display usage using the provider's actual segment rules rather than assuming every message costs one unit.

<b>Security-message protection:</b> define a small, explicit set of essential account/security messages (for example, password or account security verification where SMS is the approved channel). These must have a protected policy separate from routine school announcements and marketing. The system must still enforce abuse prevention, rate limits, valid recipient checks and audit logging. The exact free/protected allowance and who bears its cost must be finalised before production billing.

### 50.6 Message types and controls

Initial supported use cases should include:

- Student marked absent / attendance alert.
- Important attendance summaries where enabled by the school.
- Fee due and overdue reminders.
- Payment confirmation or receipt notification.
- School-wide or class-specific announcements.
- Urgent school closure, safety or schedule notices.
- Admission/application status updates where SMS is enabled.
- Essential account/security messages under the protected policy.

Controls:

- Allow authorised school users to select all eligible parents, a class/arm, a filtered group, or an individual recipient according to their role.
- Preview the recipient count, message content and estimated SMS units/cost before sending a bulk message.
- Prevent duplicate sends for the same event, recipient and template/version within the configured deduplication window.
- Use approved, reusable templates for automated messages and safe variable substitution.
- Validate phone-number format and normalise Nigerian numbers consistently.
- Respect school-level channel settings, recipient preferences and applicable consent/opt-out requirements.
- Restrict who can send school-wide or high-volume messages; keep an audit trail of sender, approval, recipients/count, message and time.
- Do not include sensitive student, academic or financial details in message previews, logs or content beyond what is necessary for the intended notification.
- Support language and sender identity configuration only where the provider and school configuration permit it.

### 50.7 Delivery, reliability and observability

- Store an internal notification ID and a separate provider message ID.
- Track queued, submitted, sent, delivered, failed, expired and suppressed states where the provider exposes them.
- Implement signed/verified callback handling where supported; validate the provider's webhook authentication method before trusting callbacks.
- Process callbacks idempotently so duplicate provider events do not duplicate state changes or usage deductions.
- Use bounded retries with backoff for transient failures; do not retry permanent errors indefinitely.
- Distinguish provider acceptance from confirmed delivery. A successful API response is not proof that the recipient received the message.
- Record provider error codes and a safe, non-sensitive failure explanation.
- Provide operational alerts for provider outage, rejected credentials, sender-ID problems, low central provider balance, abnormal failure rates and exhausted quotas.
- Provide a school-facing delivery log and a platform-operator view across schools.
- Define retention and access controls for message content, recipient numbers and delivery metadata.
- Test provider outage, delayed receipts, duplicate callbacks, rate limits, invalid numbers, DND/network restrictions, insufficient provider balance and credential rotation.

### 50.8 Cost-conscious delivery plan

The first implementation should stay within the existing ACADIVA stack and use the BulkSMS sandbox without purchasing SMS credits.

1. Build the provider-independent interface, internal notification/delivery records and sandbox adapter.
2. Test API requests, validation, error handling and callbacks in sandbox.
3. Complete school-level metering and wallet accounting before enabling paid routine messages.
4. Confirm sender-ID approval, current live pricing, taxes/fees, provider terms and delivery performance.
5. Only then fund the central provider wallet and run a tightly limited live test with authorised recipients.
6. Expand gradually after measuring real delivery, per-school consumption, support burden and gross margin.

Do not buy credits merely to complete development. A real SMS balance is needed only for live delivery testing and production use.

### 50.9 Acceptance criteria

The SMS integration is not production-ready until:

- A test notification can be sent through the sandbox without delivering a real SMS or deducting provider funds.
- Provider credentials are inaccessible from the client and are not exposed in logs or source control.
- A school event creates one authoritative notification record and can fan out to enabled channels without duplicate underlying events.
- The BulkSMS adapter can be replaced by a mock or another provider adapter without changing business workflows.
- Every delivery is attributable to the correct school, recipient, event and provider message reference.
- Duplicate jobs and duplicate callbacks do not cause duplicate sends or duplicate credit deductions.
- Provider acceptance and recipient delivery are represented as different states.
- School-level usage is accurately metered, including multi-segment messages.
- Routine messages are blocked or held according to policy when school credits are insufficient; essential security messages follow their separately approved protected policy.
- Concurrent sends cannot overspend a school's available SMS credits.
- School and platform operators can inspect appropriate delivery, failure, usage and cost records.
- Tenant isolation prevents one school from viewing another school's recipients, messages, wallet or usage.
- Sender ID, live pricing, taxes/fees, DND/network behaviour and provider terms are confirmed before production rollout.
- Failure, retry, outage, callback replay and credential rotation tests pass.

### 50.10 Build checklist 40AE — SMS provider integration and school messaging

<b>Architecture and provider</b>

- [ ] AE01. Add SMS as a channel in the shared ACADIVA Notification Engine, using one authoritative notification event and delivery records. (Core)
- [ ] AE02. Define a provider-independent SMS interface/adapter so provider-specific API logic is isolated. (Core)
- [ ] AE03. Implement BulkSMS Nigeria as the first provider adapter, subject to technical and commercial validation. (Pilot)
- [ ] AE04. Keep provider selection and credentials server-side and configurable by environment; do not expose secrets to schools or clients. (Core)
- [ ] AE05. Confirm current BulkSMS API version, production/sandbox endpoints, authentication, payload, limits and error handling from official documentation. (Pilot)
- [ ] AE06. Register and verify an approved ACADIVA sender ID before live sending. (Pilot)
- [ ] AE07. Keep Termii, Africa's Talking or other providers as evaluated future adapters, not mandatory launch dependencies. (Later)

<b>Notification workflows</b>

- [ ] AE08. Connect attendance, absence, fee, payment, announcement, admissions and approved security events to SMS templates. (Core)
- [ ] AE09. Build reusable templates, variable validation, recipient selection, preview and estimated segment/cost display. (Core)
- [ ] AE10. Implement phone-number normalisation, recipient eligibility, school permissions, consent/preferences and applicable opt-out controls. (Core)
- [ ] AE11. Add bulk-send approval/role controls, audit logs and duplicate-send suppression. (Core)
- [ ] AE12. Support queued sending, bounded retries, backoff and safe handling of transient/permanent failures. (Core)

<b>Provider operations and delivery</b>

- [ ] AE13. Configure the BulkSMS sandbox and prove end-to-end test sending without real delivery or wallet deduction. (Pilot)
- [ ] AE14. Implement verified provider callbacks/webhooks and idempotent delivery-status updates. (Core)
- [ ] AE15. Store internal and provider message IDs, status history, timestamps and safe error codes. (Core)
- [ ] AE16. Build school-facing delivery history and platform-level provider/operations monitoring. (Core)
- [ ] AE17. Add alerts for provider outage, invalid credentials, low provider balance, delivery failures and quota exhaustion. (Pilot)
- [ ] AE18. Test DND/network restrictions, invalid numbers, rate limits, delayed receipts, callback replay, retries and credential rotation. (Core)

<b>School credits, costs and safeguards</b>

- [ ] AE19. Build a school-level SMS usage ledger and credit/wallet balance separate from the central provider wallet. (Core)
- [ ] AE20. Implement safe credit reservation/deduction, concurrency protection, low-balance warnings and school spending limits. (Core)
- [ ] AE21. Include the agreed first-time activation SMS allowance and define its exact limit before onboarding. (Core)
- [ ] AE22. Require schools to fund routine SMS credits after the activation allowance is consumed. (Core)
- [ ] AE23. Define and implement the protected essential-security-message policy, abuse limits and cost responsibility. (Core)
- [ ] AE24. Track provider cost, school charge, segment count, taxes/fees where applicable and ACADIVA gross margin separately. (Core)
- [ ] AE25. Confirm provider rates and school-facing pricing/margin before enabling live paid sending; do not hard-code unverified rates. (Pilot)
- [ ] AE26. Prevent routine bulk sending when the school's credits or configured budget are insufficient; never silently permit unlimited usage. (Core)

<b>Release and verification</b>

- [ ] AE27. Complete sandbox integration and all acceptance tests before funding a live provider wallet. (Pilot)
- [ ] AE28. Verify tenant isolation for messages, recipients, delivery logs, balances and usage reports. (Core)
- [ ] AE29. Run a limited live test only after sender approval, pricing review and authorised recipient consent. (Pilot)
- [ ] AE30. Measure actual delivery, failures, per-school consumption, provider costs and support load before wider rollout. (Pilot)

### 50.11 Relationship to earlier decisions

- Section 47 establishes the SMS-first parent communication direction and the school-level SMS metering principle.
- Section 48 maintains the external-service integration register and requires every integration to have a purpose, cost model, data contract, failure behaviour and exit plan.
- Section 40AC contains the broader integration checklist; AC11 has been updated to include BulkSMS Nigeria as the initial candidate alongside Termii and Africa's Talking.
- Section 50 and checklist 40AE make the provider architecture, API setup, sandbox, delivery lifecycle, wallet controls and acceptance tests explicit.
- This section does not claim that BulkSMS has been connected or that any SMS has been sent. It records the approved build direction and the work still required.

---

## Section 61 — ACADIVA Infrastructure Cost Management, Free-Tier-First Deployment and Upgrade Policy

<b>Decision status:</b> Agreed operating policy. ACADIVA will begin with free plans and trials wherever suitable, measure actual usage and limitations, and move to paid plans only when a demonstrated capacity, capability, commercial-use, security, reliability or compliance requirement justifies the expense. This is not a commitment to remain free indefinitely.

### 61.1 Core financial principle

ACADIVA must be engineered for economical operation as a commercial product. Infrastructure cost is a product requirement and an ongoing operating metric, not an afterthought.

The governing principle is:

<b>Start free where appropriate. Measure before upgrading. Optimise before paying more. Pay when production requirements genuinely demand it.</b>

A free plan is a starting point for learning and controlled testing, not an excuse to compromise real school records, backups, security, availability or contractual obligations.

Do not purchase capacity for hypothetical scale. Equally, do not wait for a preventable outage or data-loss incident before paying for a necessary production safeguard.

### 61.2 Free-first service policy

For each provider, use the free plan or trial first where the provider's terms permit ACADIVA's intended use.

- Domain: purchase the required primary domain and renew annually. Avoid buying multiple domains without a business reason.
- DNS and basic security: start with Cloudflare's free capabilities where suitable.
- Application hosting: begin with a suitable free development/deployment allowance. Vercel, Netlify and Cloudflare are candidates, not interchangeable guarantees. Validate framework compatibility, commercial-use terms, execution limits and deployment workflow before choosing.
- Database and authentication: begin with Supabase Free for development and controlled testing. Measure database size, egress, active users, function use and operational constraints.
- Media/object storage: start within available free allowances; keep large files outside PostgreSQL and compare object-storage costs and egress.
- Email: begin within a suitable free allowance; rate-limit and monitor sending. Email is not assumed to be unlimited or cost-free.
- SMS: do not use routine SMS OTP for every login. Retain phone-plus-password and supported OAuth/passkey routes; use SMS only for justified verification or recovery events.
- Analytics and error monitoring: use free allowances or existing capabilities first. Avoid overlapping paid tools.
- Payments: account for transaction fees when payment processing is activated; do not assume that a gateway's lack of monthly subscription means payment processing is free.
- AI, maps, video and other metered APIs: keep disabled, capped or out of the initial release until a validated feature requires them.

Free trials must be tracked with their end dates and post-trial pricing. Do not enter a trial that silently converts to a paid subscription without recording the renewal date, cancellation method and expected charge.

### 61.3 Provider selection and architecture boundaries

Provider choice must balance total cost, compatibility, reliability, developer effort, portability and operational complexity. The cheapest headline plan is not automatically the cheapest solution to maintain.

<b>Application hosting</b>

- ACADIVA's application is based on Next.js and includes conventional application screens as well as browser-rendered visual experiences.
- Vercel is a strong candidate for the simplest native Next.js deployment workflow.
- Cloudflare is a strong candidate for DNS, CDN, security and object storage; Cloudflare Workers may also host the application if the required Next.js features and deployment path are proven compatible.
- Netlify remains an alternative if its framework support, pricing and operational workflow are favourable.
- Do not deploy the same production application across several hosts without a clear resilience or migration requirement.
- Do not choose Cloudflare solely because it is cheap. Do not choose Vercel solely because it is convenient. Test the actual ACADIVA build and server-side requirements.
- Three.js, React Three Fiber (R3F), GSAP/ScrollTrigger, Rive and browser-side shaders execute primarily on the user's device. They do not inherently require a specialised graphics server. Hosting must deliver application code and assets efficiently; user-device performance must be tested separately.
- The hosting decision must not narrow or quietly remove ACADIVA's approved creative technology direction in Section 59. The architecture must preserve the ability to use:
  - Three.js and React Three Fiber for interactive 3D scenes, spatial interfaces and immersive learning/public experiences.
  - GSAP and ScrollTrigger for precise cinematic sequences and scroll-driven storytelling.
  - Rive for interactive, stateful illustrations and interface animations.
  - Theatre.js where timeline-based creative direction and sequencing justify it.
  - PixiJS selectively for performant 2D canvas experiences.
  - GLSL/OGL shaders selectively for custom visual effects.
  - WebGPU/TSL as progressive enhancement when browser/device support and measured value justify it; retain WebGL/fallback paths where appropriate.
  - Spline as an optional authoring workflow for suitable 3D assets, not a mandatory runtime dependency.
- These technologies are principally front-end rendering and asset-delivery concerns, not reasons by themselves to purchase a specialised server or GPU hosting. The server still handles Next.js rendering where used, authentication, authorisation, database access, APIs, uploads and background tasks. Heavy graphics should be delivered as optimised static assets/CDN content wherever possible.
- Hosting evaluation must test the actual Next.js features and server-side routes alongside the graphics build. A provider that serves static Three.js assets well may still be unsuitable for required Next.js server functionality; evaluate both independently.
- Do not force all visual libraries onto every page. Keep clear ownership boundaries between animation systems, load only the required library/scene per experience, split bundles, lazy-load scenes, compress models and textures, cache immutable assets, and provide reduced-motion, keyboard-accessible and low-graphics fallbacks.
- Test on lower-end Android phones, older iPhones, ordinary mobile networks and desktop browsers. Establish performance budgets for initial page weight, JavaScript, 3D model/texture size, frame rate and time-to-interactive. Do not let a cinematic landing page slow down attendance, finance, timetable or result workflows.
- Heavy 3D assets should be lazy-loaded, compressed, cached and excluded from ordinary school dashboard routes unless required.

<b>Database and media</b>

- Supabase/PostgreSQL is the structured source of truth for school, student, guardian, academic, attendance and financial records.
- Do not store large images, video or document binaries in database rows. Use object storage and retain authorised metadata/references in PostgreSQL.
- Use one shared multi-tenant application/database architecture by default, with strict tenant isolation. Do not create a separate hosting project or database for each school by default.
- Separate development, staging and production environments when real school data is introduced. Do not treat a developer's free test project as a permanent production environment without assessing backups, pausing, support and recovery constraints.

### 61.4 Upgrade gates: when ACADIVA pays

An upgrade is justified when at least one of the following is true and the proposed plan solves it:

1. A hard usage limit is reached or projected to be reached before the next review.
2. The free plan's terms do not permit the intended commercial production use.
3. Production data requires backup, point-in-time recovery, support or uptime capabilities not available on the free plan.
4. A required feature, framework capability, custom domain, execution limit or security control is unavailable on the free plan.
5. Actual usage creates repeated performance, reliability or delivery problems that cannot be reasonably fixed through optimisation.
6. The expected cost of continued workarounds, engineering complexity or service disruption exceeds the paid-plan cost.
7. A customer contract, data-protection obligation or operational risk assessment requires a paid capability.

Before upgrading:

- Identify the exact limit or requirement.
- Capture current usage and recent trend.
- Check whether caching, compression, query optimisation, retention rules, image resizing or code changes solve the issue.
- Compare the next plan's included allowances, overage rates, billing cycle and cancellation terms.
- Estimate the new monthly and annual cost in USD and NGN using the actual payment conversion rate and any applicable taxes/fees.
- Record who approved the upgrade and when it should be reviewed again.
- Set alerts, budgets or usage caps where the provider supports them.

Never upgrade simply because ACADIVA has reached a round student-count milestone. Two thousand students do not automatically require a particular paid tier; workload, active usage, file sizes, traffic patterns, reliability requirements and school distribution determine consumption.

### 61.5 Vercel-specific caution

Vercel's free/Hobby allowance may be useful for development, prototypes and permitted testing, but ACADIVA must verify the current plan's commercial-use terms before relying on it for a commercial production service. Do not assume a free plan is commercially permitted merely because deployment succeeds.

Vercel usage resources are separate. Monitor at least:

- Data transfer/bandwidth.
- Builds and build execution.
- Function invocations, execution duration and resource limits.
- Image optimisation and image delivery.
- Any metered add-ons or usage-based charges.

A build allowance being exhausted is not the same as bandwidth being exhausted. Diagnose the specific resource before changing plans. If the free plan is not suitable for ACADIVA's commercial production use, use it only where permitted and select an appropriate production plan or alternative host before launch.

### 61.6 Supabase-specific caution

Begin with Supabase Free for development and controlled pilots where appropriate. Do not upgrade merely because the product may eventually contain thousands of student records.

Measure:

- PostgreSQL database size and growth rate.
- Cached and uncached egress.
- Storage usage and file traffic.
- Monthly active users.
- Edge Function invocations and execution.
- Database performance, query load and connection use.
- Backup availability, retention and restore requirements.
- Project pausing and other free-plan operational restrictions.

Textual school records are generally much smaller than photographs, scans and videos. Design efficient relational tables, indexes, pagination and queries. Keep media in object storage.

For production containing real school records, make a deliberate backup and recovery decision. If the free plan cannot meet the required backup, availability or recovery standard, move to a suitable paid plan or implement another verified solution before relying on it. Test restoration; the existence of a backup setting is not proof that recovery works.

### 61.7 Usage monitoring and monthly cost review

Maintain a lightweight infrastructure cost register. Review it monthly and before any major school onboarding or feature launch.

Track, per provider and where possible per school:

- Plan and billing status (free, trial, paid).
- Trial end and renewal dates.
- Included usage allowance and actual usage.
- Usage trend and estimated date of reaching a limit.
- Overage pricing and unexpected charges.
- Database storage and egress.
- Object storage, operation count and delivered bytes.
- Hosting bandwidth, builds and function usage.
- Email and SMS volume and delivery failures.
- Payment processing fees.
- Backup status and last successful restore test.
- Current monthly cost in provider currency and NGN.
- Cost per active school, per active user and per student.
- Optimisation action, upgrade decision and approval.

Set alerts at sensible thresholds before limits are reached (for example, 50%, 75% and 90% where supported). Alert thresholds are monitoring defaults to configure, not provider guarantees. Prevent surprise bills by disabling unnecessary metered features, setting spending limits where available and reviewing billing dashboards.

### 61.8 Cost optimisation requirements

Optimise before buying more capacity:

- Compress and resize uploaded images at ingestion; generate appropriate thumbnails and responsive variants.
- Set file-size/type limits and retention rules for uploads.
- Cache static assets and public school website content.
- Lazy-load 3D scenes, animation libraries and heavy routes.
- Keep everyday dashboards lightweight; do not load cinematic graphics into routine attendance, finance or result screens.
- Use pagination, selective field retrieval, indexes and efficient database queries.
- Avoid repeated polling and duplicate API requests; use appropriate caching and event-driven updates.
- Batch non-urgent notifications and avoid duplicate email/SMS sends.
- Store media outside the relational database.
- Define fair-use storage and upload limits by subscription tier; do not promise unlimited media on low-cost plans.
- Avoid multiple tools that perform the same analytics, monitoring, hosting or notification function.
- Archive or delete data only under an approved retention policy; never remove school records simply to reduce a bill.

### 61.9 Provider portability and exit planning

Keep ACADIVA able to change providers without rebuilding its core product:

- Own the domain and DNS configuration.
- Keep source code in the ACADIVA-controlled Git repository.
- Use standard Next.js/React patterns where practical; isolate provider-specific code behind clear adapters.
- Keep payment-provider integration behind a provider-independent interface.
- Keep school identity, tenant membership and core business records in ACADIVA's own data model rather than provider-specific metadata alone.
- Maintain documented database migrations and export procedures.
- Keep media metadata and storage paths abstracted so object storage can be migrated.
- Document environment variables, secrets, deployment steps, DNS changes and recovery procedures securely.
- Test exports and restoration before depending on a provider exit plan.

Portability is a risk-control measure, not a reason to build abstractions for every hypothetical provider on day one.

### 61.10 Planning model for a 2,000-student deployment

Any 2,000-student cost estimate is a scenario, not a quotation, guaranteed capacity statement or fixed budget. It must be recalculated from the actual school configuration and measured usage.

The model must distinguish:

- One school with 2,000 students from multiple schools whose combined enrolment is 2,000.
- Registered accounts from monthly active users.
- Students from guardians, teachers, administrators and other staff.
- Ordinary text/database activity from file downloads, image traffic and video.
- Public marketing/immersive website traffic from authenticated school-workspace traffic.
- Development/staging usage from production usage.
- Included plan allowances from overages and optional services.

For initial scenario modelling, test at least:

- 2,000 students in one school.
- 2,000 students distributed across several schools.
- Low, normal and high monthly active-user rates.
- Routine text/result/attendance usage.
- Report-card PDF downloads and document uploads.
- High image/media usage.
- Admissions/result-publication peaks and concurrent activity.

A prior illustrative estimate of roughly USD \$30–\$45 monthly for selected paid hosting/database combinations, and approximately ₦45,000–₦67,500 at an assumed ₦1,500/USD, is retained only as an example of base subscription arithmetic. It is not a validated total cost for 2,000 students. It excludes or may not fully capture taxes, FX/payment charges, overages, email/SMS, support, backups beyond included allowances, monitoring and actual workload. The assumed exchange rate is not a live quotation. Recalculate from current provider pricing and actual usage before making a financial commitment.

The earlier suggested ₦70,000–₦80,000 monthly target is a provisional planning allowance, not a commitment, price promise or evidence that the platform will fit within it. Replace it with measured costs during the pilot and production rollout.

### 61.11 Cost ownership and school economics

Infrastructure is shared across the multi-tenant platform by default. Do not multiply the full platform bill by the number of schools. Attribute costs to schools only where a defensible usage metric exists, such as unusually high file storage or media delivery.

Review:

- Total monthly platform infrastructure cost.
- Cost per active school.
- Cost per enrolled student and per monthly active user.
- Marginal cost of onboarding another school.
- Storage and bandwidth consumption by school.
- Revenue contribution and support effort by school.

Pricing must cover infrastructure together with support, development, customer acquisition, payment fees, taxes and other operating costs. Do not set school prices using hosting cost alone. Consider reasonable storage/media allowances and fair-use rules in school plans.

### 61.12 Launch and review checklist

Before pilot:

- [ ] Confirm each provider's current free-plan terms and commercial-use eligibility.
- [ ] Record trial start/end dates and any auto-renewal.
- [ ] Test the actual Next.js build and required server-side features on the chosen host.
- [ ] Test 3D/animation loading and performance on lower-end Android devices and ordinary mobile networks.
- [ ] Configure usage dashboards and alerts.
- [ ] Separate development/staging from production data.
- [ ] Confirm tenant isolation and access controls.
- [ ] Define backup, export and restore procedures.
- [ ] Set file-size, image and media limits.
- [ ] Record baseline usage and expected pilot workload.

Before production:

- [ ] Confirm the production plan permits commercial use.
- [ ] Confirm backups, recovery, security and availability meet the school's data requirements.
- [ ] Load-test realistic concurrent workflows.
- [ ] Review all recurring subscriptions and metered APIs.
- [ ] Document the monthly cost and the person responsible for reviewing it.
- [ ] Confirm that billing alerts and spending controls are active.

Monthly:

- [ ] Review provider bills and usage.
- [ ] Compare actual use with plan allowances and forecasts.
- [ ] Investigate unexpected spikes.
- [ ] Optimise before upgrading.
- [ ] Record each paid upgrade, rationale, date and next review.
- [ ] Recalculate cost per school and per student.

### 61.13 Decision summary

The agreed ACADIVA policy is free-tier-first, measured and commercially responsible. Start with free plans/trials where permitted, learn their actual limits, and pay only when a specific usage, commercial, reliability, security or compliance requirement justifies it. Do not confuse a free development environment with production readiness. Do not select Cloudflare, Vercel, Netlify or any other provider on price alone. Select the simplest technically sound option, monitor it, optimise it and retain a practical migration path.

This section supplements Sections 38, 39, 48, 49 and 60. It does not replace their detailed architecture or financial decisions. If actual provider terms or measured usage contradict an earlier estimate, update the estimate with a dated evidence-based change note while preserving the historical record.

<mention url="https://app.notion.com/p/41c9a9b48b7a814e96e4f5e4cbef2920">00 — ACADIVA Core Operating Model, Master Requirements & System Architecture</mention>

<mention url="https://app.notion.com/p/41c9a9b48b7a8115b27ce9fcd65320a0">01 — ACADIVA Master Execution Checklist, Governance & Build Gates</mention>

<mention url="https://app.notion.com/p/41c9a9b48b7a8197b133d5f5a18b628d">02 — ACADIVA Product Strategy, Market & Commercial Model</mention>

<mention url="https://app.notion.com/p/41c9a9b48b7a81b4aed8f94986dc1ecb">03 — ACADIVA Core Modules, Roles, Teaching & School Workflows</mention>

<mention url="https://app.notion.com/p/41c9a9b48b7a81539c55f74d01885bc1">04 — ACADIVA Admissions, Student Records, Guardian Identity & Finance</mention>
