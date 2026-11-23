<!-- Source: https://app.notion.com/p/41c9a9b48b7a81d9a0cac9af71e89d01?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🎨 06 — ACADIVA Design, Experience & Creative Technology

This manual groups the complete interface and design direction, product principles for experience quality, reference research, design governance and the creative technology stack. Next.js remains the application framework; Three.js/R3F are selected browser-side graphics technologies within that application, not alternatives to Next.js.

<b>Preservation rule:</b> the full source sections are reproduced below. Their original requirements, examples, rationale, checklists and open questions are retained. This curated page changes navigation and grouping, not product decisions.

---

## 31. Complete UI/UX design and screen architecture

<b>Status:</b> Product-wide design requirement and agreed scope. Detailed visual direction, target device priority and design destination remain to be confirmed. This section defines what must be designed and how the design work should be carried out; it does not claim that screens have already been designed or implemented.

### 31.1 Design objective

ACADIVA must have a complete, coherent interface across the entire school operating system. Designing only a dashboard or a few attractive screens is not sufficient. The work must cover every major role, module, workflow, screen state, permission boundary and responsive layout.

The interface should feel like a credible, carefully designed professional software product used daily by real schools. It must not look like a generic AI-generated admin template or a collection of unrelated dashboard cards.

The design should make complex school operations understandable to proprietors, principals, administrators, teachers, bursars, parents and students with different levels of digital confidence.

### 31.2 Design principles

- Light-first interface using white and restrained neutral surfaces. A dark-first interface is not the intended direction.
- A disciplined visual identity with a considered accent palette; the final brand colours are not yet approved.
- Clear typography, hierarchy, spacing, alignment and consistent component behaviour.
- Functional information density: tables and records should be easy to scan without looking crowded.
- Charts should answer real school-management questions, not exist as decoration.
- Forms should be organised around the task being completed, with clear validation, helpful errors and confirmation for consequential actions.
- Navigation and terminology should remain consistent across modules.
- Role-specific workspaces should expose the tools each user needs without showing irrelevant or unauthorised information.
- Responsive behaviour must be deliberately designed for desktop, tablet and mobile rather than simply shrinking desktop screens.
- Accessibility, readable contrast, touch target sizes and low-friction use on ordinary devices must be considered.
- Empty, loading, success, error, offline, restricted-access and no-data states must be designed, not left as implementation afterthoughts.
- Use realistic school data and Nigerian school workflows in design examples. Avoid placeholder-heavy screens and invented metrics that make the product feel artificial.

### 31.3 Reference-led design research

Design decisions should be informed by real product interfaces and established UI/UX reference libraries. References are inputs for analysis, not templates to copy blindly.

Recommended research libraries:

- [SaaSFrame](https://www.saasframe.io/) — SaaS product pages, dashboards, onboarding and settings patterns.
- [Mobbin](https://mobbin.com/) — real application screens and end-to-end mobile/web flows.
- [Refero](https://refero.design/) — searchable web and mobile interface references.
- [Nicelydone](https://nicelydone.club/) — SaaS interface patterns and screen inspiration.
- [Page Flows](https://pageflows.com/) — user-flow recordings and interaction patterns.
- [Dribbble](https://dribbble.com/) — visual exploration only; concept shots must not be treated as proof of usable product UX.
- [SaaS UI](https://www.saasui.design/) — additional SaaS screen and component references.

For each major module, research relevant references for the actual task being designed. For example, finance should be informed by credible banking/accounting interfaces; records and administration by mature business software; parent experiences by clear consumer-facing portals; and timetable design by scheduling products. Record what is useful about each reference, what should be avoided, and how the pattern should be adapted to the school context.

Do not copy another product's branding or reproduce its screens wholesale. ACADIVA needs its own coherent design system.

### 31.4 Full screen and module inventory

The following is the minimum design inventory. It is a planning checklist, not a claim that every screen must appear in the first MVP release.

1. <b>Platform and school onboarding</b>
   - Platform landing and sign-in.
   - School registration and school profile setup.
   - Subdomain selection/assignment and branding.
   - Academic session, term, levels, classes, arms and subjects setup.
   - Grading and assessment configuration.
   - Initial data import, setup checklist and onboarding completion.
   - Subscription plan, billing and school activation.
2. <b>Proprietor workspace</b>
   - Proprietor dashboard and whole-school overview.
   - Enrolment, staff, attendance and academic summaries.
   - Fee collection, outstanding balances and financial overview.
   - School performance and management reports.
   - Branch comparison where multi-branch support is enabled.
   - Approvals, alerts and items requiring attention.
3. <b>Principal / head teacher workspace</b>
   - Principal dashboard.
   - Academic calendar and term overview.
   - Attendance and class oversight.
   - Teacher and subject assignment oversight.
   - Results submission, review and approval.
   - Timetable review and publication.
   - Announcements, events and PTA communication.
   - School reports and delegated approvals.
4. <b>Administration / registrar workspace</b>
   - Administration dashboard.
   - Student directory, student profile and record history.
   - Admissions enquiry and applicant pipeline.
   - New student registration and document handling.
   - Parent/guardian records and child-link verification.
   - Class, arm and session allocation.
   - Student promotion, transfer, withdrawal and graduation workflows.
   - Staff directory and authorised account invitations.
5. <b>Teacher workspace</b>
   - Teacher home/dashboard and daily schedule.
   - Assigned classes and subjects.
   - Class register and attendance entry.
   - Student lists and permitted student profiles.
   - Assessment setup where authorised.
   - Score entry, draft saving, submission and correction workflow.
   - Results and teacher remarks.
   - Lesson resources and approved learning materials where enabled.
   - Announcements and school notices.
   - Teacher profile, account and access settings.
6. <b>Parent / guardian portal</b>
   - Parent registration, invitation acceptance and secure sign-in.
   - Parent home and linked-child switcher.
   - Child profile and class information.
   - Results, report cards and academic history.
   - Attendance and relevant school updates.
   - Fee invoices, balances, payment history and receipts.
   - Announcements, PTA notices, events and reminders.
   - Parent contact details, notification preferences and support/enquiry route.
7. <b>Student experience</b>
   - Student sign-in and age-appropriate home.
   - Timetable and school calendar.
   - Results and permitted academic records.
   - Learning resources and assignments if enabled.
   - Announcements and school notices.
   - Profile and account settings with appropriate restrictions.
8. <b>Finance and fee management</b>
   - Finance dashboard.
   - Fee categories, fee structures and billing configuration.
   - Student fee accounts and ledger.
   - Payment entry and manual verification.
   - Online payment initiation and confirmation states when integrated.
   - Payment register with filters and class/school totals.
   - Receipts, refunds, reversals and adjustments.
   - Outstanding balances and reminders.
   - Expense register and basic budgets when released.
   - Collection, balance, expense and reconciliation reports.
   - Finance roles, approvals and audit history.
9. <b>Academic management</b>
   - Academic sessions and terms.
   - Levels, classes, arms, subjects and subject combinations.
   - Assessment components, grading scales and weightings.
   - Score entry and submission.
   - Result review, approval and publication.
   - Report-card preview, generation, printing and history.
   - Promotion review and confirmation.
   - Student performance insights and class/subject analysis.
10. <b>Teacher and staff management</b>
    - Staff directory and staff profile.
    - Staff ID and invitation/account status.
    - Role and permission assignment.
    - Teacher subject/class assignment.
    - Temporary substitutions and assignment history.
    - Staff attendance and leave where included.
    - Employment status, document records and offboarding.
    - Staff access audit.
11. <b>Timetable and scheduling</b>
    - Timetable configuration.
    - Periods, breaks, school days, rooms and labs.
    - Teacher availability and workload.
    - Class and teacher timetable views.
    - Timetable editor and conflict warnings.
    - Draft, validation, approval and publication.
    - Printable timetable and change history.
12. <b>Announcements and communications</b>
    - Announcement register.
    - Compose, preview and audience selection.
    - Class/arm, parent, teacher, staff and whole-school targeting.
    - Channel selection and scheduling.
    - Approval where configured.
    - Delivery status, retries and failure reporting.
    - Templates, notification preferences and communication history.
13. <b>Reports and analytics</b>
    - Enrolment and student status reports.
    - Attendance reports.
    - Academic performance reports.
    - Teacher/class/subject summaries.
    - Fee collection and outstanding reports.
    - Expense and budget summaries.
    - Communication delivery reports.
    - Export screens and export permissions.
    - Filters by session, term, class, arm and date range.
14. <b>School public profile and website</b>
    - Public school home page.
    - About, programmes/levels and facilities.
    - Admissions information and enquiry/application forms.
    - News, announcements and gallery.
    - Contact information and map/location where appropriate.
    - School branding and website content management.
15. <b>Platform owner / ACADIVA operations</b>
    - Platform overview and tenant directory.
    - School onboarding and tenant status.
    - Subscription and billing oversight.
    - Support and issue management.
    - Platform-level usage and infrastructure monitoring.
    - Provider/integration status.
    - Security events and controlled support access.
    - Platform configuration and audit history.
16. <b>Shared settings, account and security</b>
    - Sign-in, account recovery and invitation acceptance.
    - User profile and contact verification.
    - Password, sessions and multi-factor authentication where supported.
    - Role and permission management.
    - School identity and branding settings.
    - Academic and notification settings.
    - Subscription and billing settings.
    - Data export and school exit workflows.
    - Audit log and security activity.

### 31.5 Required screen states and interaction specifications

Every screen should be designed with the states that matter to its workflow. Depending on the screen, these include:

- Initial, loading and refreshing.
- Empty state for a new school or a module with no records.
- Populated state with realistic data.
- Search results, filters, sorting and pagination.
- Form validation and field-level errors.
- Save draft, submit, approve, reject and confirmation states.
- Success, failure, timeout and retry states.
- Permission denied and read-only states.
- Pending, verified, failed, reversed and disputed payment states where relevant.
- Scheduled, published, archived and cancelled announcement states.
- Offline or interrupted connection states for workflows that need resilience.
- Destructive-action confirmation and audit explanation.
- Mobile navigation, responsive tables and long-form record handling.

Each important interaction should have a written behaviour specification: what the user can do, what data changes, what permissions are checked, what confirmation is shown, what happens on failure and what is recorded in the audit trail.

### 31.6 Design system deliverables

Before producing screens at scale, establish a reusable design system containing:

- Colour tokens and semantic colours.
- Typography scale and text hierarchy.
- Spacing, grid, sizing and responsive breakpoints.
- Buttons, links, inputs, selects, checkboxes and date controls.
- Navigation, sidebars, headers, tabs and breadcrumbs.
- Cards, tables, filters, pagination and data summaries.
- Dialogs, drawers, popovers, alerts and toast messages.
- Badges and status indicators.
- Charts and data-visualisation rules.
- Empty states, loading skeletons and error patterns.
- Document and report layouts.
- Icon style and illustration rules.
- Accessibility and interaction guidance.

Components should be reusable across roles while allowing each role's workspace to expose different information and actions.

### 31.7 Design workflow and order of work

The design work should proceed in a controlled sequence:

1. Confirm the primary device strategy: desktop-first, mobile-first or deliberately designed for both.
2. Confirm the design destination: Figma, a working interactive prototype or both.
3. Confirm the visual direction and brand constraints.
4. Research real interface references by module and user task.
5. Map roles, permissions, navigation and end-to-end user journeys.
6. Complete the master screen inventory and prioritise MVP versus later releases.
7. Create the design system and shared components.
8. Design high-priority workflows in full, including all relevant states.
9. Extend the system to every remaining role and module.
10. Produce responsive layouts and interaction specifications.
11. Review consistency, usability, accessibility and permission boundaries.
12. Prepare implementation-ready handoff notes and update this product blueprint as decisions are made.

The first design tranche should cover the core daily workflows: school setup, proprietor/principal overview, student records, teacher workspace, attendance, results/report cards, parent portal, fee tracking/payments and announcements. Other modules remain in the full product design scope but can be sequenced after the MVP workflows.

### 31.8 Design governance and quality bar

- A dashboard concept is not a completed module. The full workflow behind each dashboard metric must be designed.
- No screen should expose information or actions that the signed-in role is not authorised to use.
- Finance, results, parent-child linking, teacher assignment and student status changes require explicit confirmation and appropriate audit behaviour.
- Do not invent data, fake metrics or pretend integrations exist in visual prototypes.
- Distinguish a clickable prototype from a production-ready feature.
- Review screens using realistic Nigerian school scenarios, including small schools with limited staff and larger schools with multiple classes and subject teachers.
- Test with actual school users before treating the design as validated.
- Keep design decisions and unresolved questions recorded in this blueprint.

### 31.9 Decisions still required

- [ ] Confirm whether the product should be designed desktop-first, mobile-first or equally for desktop, tablet and mobile.
- [ ] Confirm whether the working design destination is Figma, an interactive prototype or both.
- [ ] Confirm the preferred visual direction and final brand palette.
- [ ] Confirm which role and workflow should be designed first after the design system.
- [ ] Validate the screen inventory and MVP sequence with pilot schools.

---

## 50-B — ACADIVA: Product Principles, Differentiation, Experience, Scalability and Build-Quality Checklist (originally numbered Section 50)

<b>Stable record ID:</b> 50-B. Original content is retained; this identifier resolves the duplicate original section number.

<b>Recorded: 16 November 2026</b>

<b>Status:</b> Product direction agreed; detailed implementation choices remain subject to validation and technical design.

### 50.1 Brand and product identity

- The current product name is <b>ACADIVA</b>. Replace the previous working name ACADIVA in current-facing product documentation, navigation and new work. Preserve historical decisions and rationale where needed, but do not continue presenting ACADIVA as the current brand.
- ACADIVA is a connected school operating platform for Nigerian nursery, primary and secondary schools.
- ACADIVA must be original. Competitors are references for understanding customer expectations and proven workflows, not templates to copy blindly.
- Product ambition: study the original problem and execution, identify what works and what does not, understand why, then design a meaningfully better solution through stronger usability, workflow, reliability, clarity and thoughtful features.
- Avoid feature-count competition. A feature is valuable only when it solves a real school, parent, teacher or student problem better.

### 50.2 Competitive research and differentiation method

Use MySchoolReg as one reference for school-management feature coverage, including student records, CBT, admissions, fee collection, Paystack, report cards, parent access, timetables and student promotion. Do not assume every competitor claim is independently verified.

For every competitor feature or workflow:

1. Identify the user and the problem being solved.
2. Inspect the complete journey, not just the marketing description or screenshot.
3. Record strengths, friction, missing steps, accessibility issues and likely operational constraints.
4. Validate whether Nigerian schools actually need it and how they currently solve the problem.
5. Decide whether ACADIVA should adopt the capability, redesign it, simplify it, defer it or reject it.
6. Define ACADIVA's differentiated approach and measurable acceptance criteria.
7. Record the decision and rationale before implementation.

Maintain a competitor research register with: product, feature, user problem, observed workflow, strengths, weaknesses, evidence/source, ACADIVA opportunity, decision, validation status and review date. Never reproduce another product's branding, copy, layouts or distinctive expression.

### 50.3 Connected product architecture and website/login model

ACADIVA is one connected platform with three experiences:

1. <b>Central ACADIVA website — </b>[<b>acadiva.ng</b>](http://acadiva.ng)<b>:</b> product information, features, pricing, school registration, support, school discovery where appropriate, and central login.
2. <b>Individual school public websites — e.g. </b>[<b>greenfield.acadiva.ng</b>](http://greenfield.acadiva.ng)<b>:</b> each school's own identity, public information, admissions, news, announcements, achievements, gallery, contact details and a visible login entry.
3. <b>Private role-based school workspaces:</b> parent, student, teacher, school administrator, principal, proprietor, bursar and other authorised roles.

The school website login should be a standard part of each school's website, not an optional afterthought. On desktop, place it visibly beside the school identity/navigation; on mobile, keep it easy to reach beside the logo/menu without crowding the header.

A login from a school's website should retain the school context and lead to the correct school's portal. Central login at [acadiva.ng](http://acadiva.ng) should identify the user's authorised school memberships and roles. A person may be associated with more than one school; access must remain explicitly scoped to the selected school and verified relationships. Do not assume one email/phone automatically proves a parent-child relationship.

Use shared authentication and shared underlying platform services rather than building disconnected login systems for every school. Consider custom domains for schools as a planned capability, subject to DNS, certificate, routing and support design.

### 50.4 School website builder

Use a polished, mobile-first template system. Every school should receive a professional website without needing a developer. Schools should manage content from their ACADIVA workspace.

School-configurable content should include:

- Logo, school name, colours, contact details and location.
- School history, mission, vision, values and leadership.
- Education levels, classes/programmes and facilities.
- Gallery, school life, events, excursions and sports.
- News, announcements and achievements/awards.
- Admissions information, enquiry/application forms and relevant calls to action.

Provide preview-before-publish, draft/publish controls, image optimisation, safe media handling and shareable URLs for individual announcements, news and achievements. Start with a consistent high-quality template and controlled customisation; do not expose unrestricted layout editing before it is justified by user research.

### 50.5 Animation, interaction and visual experience standards

<b>Requirement:</b> ACADIVA must feel modern, responsive and alive, not static or boring. Animation is a deliberate design layer, not decoration added indiscriminately.

Use appropriate motion for:

- Page and section transitions.
- Scroll-based reveals where they aid orientation.
- Hero/media treatments and image galleries.
- Interactive cards, menus, tabs, filters and dropdowns.
- Dashboard charts, counters and progress indicators.
- Notifications, save/submit confirmations and status changes.
- Loading skeletons, progress states and empty states.
- Mobile navigation and touch feedback.

Rules:

- Motion must communicate hierarchy, state, continuity or feedback.
- Keep animations short, smooth and purposeful.
- Never block essential actions or delay content unnecessarily.
- Avoid excessive parallax, constant movement, flashing, distracting loops and motion that harms readability.
- Respect reduced-motion preferences and accessibility needs.
- Test on ordinary Android devices and iPhones, lower-powered devices and slower networks.
- Prefer performant browser-native/compositor-friendly techniques; avoid expensive effects on large lists or dashboards.
- Every animated interaction must have a clear non-animated/accessible state where appropriate.

### 50.6 Mobile-first and responsive requirements

- Design and test phone layouts as first-class experiences, not compressed desktop pages.
- Public school websites, central ACADIVA pages, login, parent/student/teacher/admin workspaces and all essential workflows must work on mobile.
- Use touch-friendly controls, readable type, sensible spacing and short forms.
- Make tables usable on small screens through responsive layouts, prioritised columns or accessible detail views.
- Support mobile CBT carefully, including screen-size and connection constraints.
- Make report cards, receipts and other documents easy to preview/download/share on phones.
- Optimise image/video delivery and avoid forcing large downloads.
- Verify layouts across common screen sizes, orientations, browsers and assistive settings.

### 50.7 Performance, reliability and growth requirements

<b>Design target:</b> support at least 1,000 concurrent active users as an initial load-test target and be architected to scale to 10,000+ daily users and substantially more schools. These are targets to prove through testing, not claims of current capacity or a guarantee that a particular architecture automatically achieves them.

Plan for:

- Multi-tenant architecture with strict school-level data isolation.
- Efficient database schema, indexes, query patterns and connection management.
- Server-side authorisation and tenant context on every protected request.
- Caching for suitable repeated reads, with explicit invalidation and freshness rules.
- CDN delivery for public assets and media.
- Image resizing/compression and appropriate video delivery/storage.
- Background jobs/queues for report generation, bulk imports, notifications, exports and other heavy tasks.
- Pagination, filtering and bounded queries; never load unbounded school-wide records into a page.
- Rate limiting, abuse protection and sensible request timeouts.
- Monitoring for errors, latency, database load, queue backlog, storage, availability and cost.
- Backups, tested restoration, disaster recovery and documented retention.
- Graceful degradation and clear user feedback when a dependency is unavailable.
- Capacity planning and cost monitoring before major growth or new modules.

Do not let a long-running task (for example, generating hundreds of report cards or importing a large class list) freeze unrelated users or block the entire application. Design workloads so simultaneous CBT sessions, parent result checks, fee confirmations and administrative work can coexist.

### 50.8 Load and resilience testing gates

Before launch and after major architecture changes, test realistic user journeys at staged concurrency levels: 100, 250, 500 and 1,000 concurrent users, then stress beyond the target to understand failure behaviour.

Include realistic combinations of:

- Login and session refresh.
- Parents checking results and balances.
- Teachers taking attendance and entering scores.
- Students taking CBT examinations.
- Administrators searching and updating records.
- Bulk student imports and report-card generation.
- Payment initiation and asynchronous payment confirmation.
- Public website and gallery traffic.

Measure response-time percentiles, error rates, throughput, database query/load, connection saturation, queue delay, memory/CPU, and recovery behaviour. Set explicit service-level objectives after baseline measurements. Test bottlenecks and fix root causes rather than hiding symptoms by increasing infrastructure blindly.

### 50.9 Security, privacy and correctness

- Enforce tenant isolation in backend policies and database access controls; never rely on hiding interface elements.
- Use least-privilege role-based access for every page, API, record, export and action.
- Verify parent/guardian relationships and student links through school-controlled workflows.
- Protect sensitive student and staff information; collect only what is needed.
- Use secure authentication, session handling, password reset, rate limits and appropriate account recovery.
- Validate and sanitise all user inputs and uploaded files.
- Protect payment flows with provider verification, idempotency and reconciliation; never trust a browser success message alone.
- Log sensitive actions and important record changes with actor, timestamp and relevant context.
- Define retention, correction, export, deletion and incident-response procedures.
- Test cross-tenant access attempts, privilege escalation, insecure direct object references and common web vulnerabilities.

### 50.10 Organised build method: think before every step

<b>Core principle:</b> build ACADIVA like a carefully engineered house. Before adding, changing or removing anything, understand what it touches, what it depends on and what could break.

No feature or change should move directly from idea to code without a short impact assessment.

For every task, answer:

1. <b>Purpose:</b> What exact user problem are we solving? Who experiences it?
2. <b>Scope:</b> What is included and explicitly excluded?
3. <b>Existing system:</b> What screens, modules, tables, APIs, roles, integrations and workflows already depend on this?
4. <b>Dependencies:</b> What must exist first? What else will depend on this change later?
5. <b>Data model:</b> Does it add, change, migrate or delete data? Is the source of truth clear?
6. <b>Permissions:</b> Who can view, create, edit, approve, export or delete it?
7. <b>Tenant isolation:</b> Can this expose or alter another school's data?
8. <b>Scale:</b> What happens with 10 records, 10,000 records and many schools using it simultaneously?
9. <b>Performance:</b> Does it add expensive queries, large payloads, repeated requests, blocking work or unnecessary rendering?
10. <b>Failure modes:</b> What happens if the network, database, payment provider, email/SMS provider or background job fails?
11. <b>Recovery:</b> Can the user retry safely? Is the action idempotent? Can data be restored or a release rolled back?
12. <b>Compatibility:</b> Does it break existing users, mobile layouts, older records, exports, integrations or bookmarked URLs?
13. <b>Security and privacy:</b> What new attack surface or sensitive data is introduced?
14. <b>Accessibility and usability:</b> Can the intended users understand and operate it on a phone and with assistive settings?
15. <b>Testing:</b> What unit, integration, end-to-end, permission, regression and load tests prove it works?
16. <b>Observability:</b> How will we know it is failing in production, and what useful diagnostic information will exist?
17. <b>Cost and operations:</b> What will it cost to run, support, store and maintain as usage grows?
18. <b>Documentation:</b> Which product, technical, API, database, support or onboarding documents must change?

If a critical question has no answer, pause and investigate before implementation. Record assumptions explicitly rather than silently treating them as facts.

### 50.11 Change-management and release discipline

- Inspect the current implementation and documentation before changing it; do not guess how existing code behaves.
- Map affected components, routes, tables, policies, jobs, integrations and users.
- Prefer small, reversible, focused changes over broad rewrites.
- Avoid duplicate sources of truth and duplicated business logic.
- Use reviewed database migrations; never make destructive production schema changes casually.
- Back up or define a recovery path before risky data changes.
- Use feature flags or staged rollout for high-risk changes where appropriate.
- Run relevant automated tests, manual critical-path checks and regression tests before release.
- Review logs and monitoring after deployment.
- Have a rollback or forward-fix plan.
- Update the changelog, technical notes and user-facing guidance.
- Do not mark work complete merely because code was written; completion requires evidence that acceptance criteria pass.

### 50.12 Definition of done for every feature

A feature is not complete until:

- Its user problem and acceptance criteria are clear.
- The expected workflow works from start to finish.
- Role permissions and tenant boundaries are tested.
- Mobile and desktop layouts are usable.
- Loading, empty, success, validation and error states are designed.
- Animation and reduced-motion behaviour are appropriate.
- Data is validated, consistent and recoverable.
- Performance is acceptable with realistic data volumes.
- Unit/integration/end-to-end tests appropriate to the risk pass.
- Existing critical workflows have no known regression.
- Logs/monitoring can reveal important failures.
- Documentation and support notes are updated.
- The release and rollback/recovery approach is understood.

### 50.13 Product scope to evaluate and prioritise

The feature inventory to plan, validate and phase includes:

- School, staff, student and parent records.
- Classes, subjects, sessions, terms and school configuration.
- Attendance and timetable management.
- Continuous assessment, examinations, grading, results and report cards.
- CBT question bank, timed tests, practice mode, automatic marking and proportionate anti-cheat controls.
- Fee structures, student billing, part-payments, payment recording, Paystack integration, receipts, balances and reconciliation.
- Admissions, application forms, applicant review, entrance tests, admission letters and conversion to student records.
- Parent, student, teacher, administrator, principal, proprietor and bursar workspaces.
- Announcements, notifications and communication history.
- School website, content manager, gallery, news, achievements, admissions pages and shareable content links.
- Analytics, exports, audit trails and platform operations.

This is a product inventory, not a promise to launch every module simultaneously. Prioritise by user value, dependency order, operational risk, implementation cost and validation evidence.

### 50.14 Planning and decision registers to maintain

Maintain these living registers and link them from the master blueprint:

- Product requirements and feature backlog.
- User roles, permissions and workflow map.
- Competitor research and differentiation register.
- UX/UI design system, responsive patterns and animation standards.
- Architecture decisions and system dependency map.
- Database schema, data dictionary and migration history.
- Integrations and provider decision register.
- Security, privacy and threat register.
- Performance budgets, load-test results and capacity assumptions.
- QA test plan, regression suite and known-bug register.
- Release/change log, rollback plans and incident register.
- Open questions, assumptions and decisions awaiting validation.

Every material decision should record its status (confirmed, proposed, assumption, rejected or open), rationale, date, impact and any superseded decision. Keep the documentation organised so developers and future contributors can find the current source of truth quickly.

### 50.15 Immediate next steps

- [ ] Update current-facing documentation and product language to ACADIVA.
- [ ] Consolidate this section into the current master requirements and checklist without deleting historical decisions.
- [ ] Create a competitor comparison register, starting with MySchoolReg and other relevant Nigerian school products.
- [ ] Map all user roles and end-to-end journeys across central ACADIVA, school websites and private portals.
- [ ] Produce a system architecture and dependency diagram before committing to implementation details.
- [ ] Define the first release boundary and the features deliberately deferred.
- [ ] Define design tokens, responsive breakpoints, motion principles and accessibility rules.
- [ ] Define multi-tenant data isolation and authentication flows.
- [ ] Define measurable performance budgets and a realistic 1,000-concurrent-user test plan.
- [ ] Establish automated tests, migration discipline, monitoring, backup and recovery before scaling.
- [ ] Use the 18-question pre-build assessment and feature definition-of-done checklist for every meaningful change.

<b>Operating rule:</b> organisation before implementation; understanding before modification; evidence before declaring success. The aim is to minimise defects and avoidable rework, not to promise software with zero bugs.

---

## Section 57 — ACADIVA Premium Design Standard, Mandatory Reference Research and Payment Experience

<b>Status:</b> Accepted design-governance direction from the founder. This section adds a mandatory design-research gate to Sections 39, 40, 42, 46 and 56. It does not select ACADIVA's brand colours, typography, logo or final visual identity; those remain separate decisions.

### 57.1 The design ambition

ACADIVA must feel like a carefully crafted, premium, world-class software product. The target is not merely a modern-looking school dashboard. Every interface should demonstrate deliberate product design: clear information hierarchy, excellent spacing, typography, alignment, proportion, visual rhythm, interaction states, transitions, responsive behaviour and thoughtful detail.

The founder's supplied Dribbble screenshots establish a quality reference for the payment experience: refined mobile screens, strong composition, legible financial information, polished payment-method selection, clear confirmation states and a cohesive end-to-end flow. They are inspiration for the level of craft, not a requirement to copy their colours, branding, layout or exact screens.

<b>Brand colours are deliberately undecided.</b> Do not infer or lock a brand palette from the supplied references. Design quality, layout and interaction principles must be assessed independently of colour.

### 57.2 Mandatory design-reference sources

The following six platforms are the required research sources for ACADIVA interface design:

1. [Mobbin](https://mobbin.com/) — real product flows, mobile/web interface patterns and interaction references.
2. [Dribbble](https://dribbble.com/) — visual concepts, composition, interface craft and high-fidelity design inspiration.
3. [Behance](https://www.behance.net/) — detailed case studies, end-to-end product design systems and project rationale.
4. [Awwwards](https://www.awwwards.com/) — high-quality web experiences, visual storytelling, motion and interaction inspiration.
5. [Refero](https://refero.design/) — curated product UI patterns and interface references.
6. [Design Spells](https://www.designspells.com/) — interaction, motion and visual-detail inspiration.

<b>Mandatory rule:</b> Before designing or materially redesigning any ACADIVA screen, page, workflow, component or interaction, research relevant examples from these sources. Do not proceed straight from a vague prompt or personal guess into a final interface.

The six sources form the approved research library. A source may have no relevant example for a particular feature; record that limitation honestly and continue research across the other approved sources. Do not invent a reference or claim to have reviewed a page that was not actually inspected.

### 57.3 Reference-research procedure — required before design

For each screen or connected flow:

1. Identify the user, role, task, device context and problem the screen must solve.
2. Search the six approved sources for relevant products, screens, components and complete flows.
3. Inspect the actual reference, not just its thumbnail. Where possible, review multiple states, screen sizes and the full user journey.
4. Save the source URL, platform, product/project name, screen or pattern observed, and the specific design lesson.
5. Compare references and identify what works, what does not, and what is unsuitable for ACADIVA's users or Nigerian school context.
6. Create an ACADIVA-specific design direction that combines useful patterns without copying a single source.
7. Check consistency with the shared design system, role permissions, data model, accessibility, mobile behaviour, performance and existing workflows.
8. Record the reference-to-design rationale in the design register before implementation.

A reference is evidence and inspiration, not an instruction. ACADIVA must adapt patterns to its own users, workflows, content, constraints and brand.

### 57.4 No-copying, originality and responsible use

- Do not copy another product's complete screen, proprietary assets, illustrations, logos, brand identity, written content or distinctive visual expression.
- Reuse general interaction conventions and common UI patterns where appropriate, while creating original ACADIVA layouts and components.
- Use only assets that ACADIVA owns, has permission to use, or can lawfully license.
- Keep attribution/source records for inspiration and licensed assets.
- Do not use a Dribbble concept as proof that a flow is usable or technically feasible. Validate the real workflow with ACADIVA requirements and users.
- Do not sacrifice clarity, accessibility, speed or reliability for visual novelty.

### 57.5 Payment experience — premium benchmark and complete connected journey

The payment experience is a flagship design-quality benchmark for ACADIVA. The supplied references show the level of visual polish expected, but ACADIVA's payment flow must be more complete, clearer and better suited to school-fee transactions.

Design the entire journey, not just a payment screen:

- Parent opens the correct child's fee account and can clearly identify the student, school, session, term and invoice.
- Parent sees the amount due, amount already paid, outstanding balance, any approved instalment arrangement and relevant due date.
- Parent selects an available payment method and sees the amount to be paid before proceeding.
- The system creates a secure payment attempt tied to the correct school, student, invoice and term.
- Parent receives an unmistakable processing/pending state while provider confirmation is awaited.
- A successful payment confirmation shows the verified amount, date, transaction reference and receipt access.
- A failed, cancelled, expired or pending payment has a clear explanation and safe next action.
- Duplicate taps, retries, delayed webhooks and repeated callbacks must not create duplicate ledger entries or duplicate receipts.
- The parent can return to the child's fee history and see the server-confirmed balance and transaction status.
- Bursar and authorised school leaders see the same authoritative transaction and ledger outcome, with role-appropriate detail.

Visual requirements include:

- A calm, uncluttered hierarchy that makes the amount and payment purpose immediately obvious.
- Clear distinction between amount due, amount being paid, amount paid and outstanding balance.
- Carefully designed payment-method cards, input fields, review steps, loading states, confirmation and error states.
- Strong mobile usability, accessible text and touch targets, clear focus and validation states.
- A polished receipt that follows ACADIVA's document branding rules.
- Consistent components and interaction patterns across parent, bursar and school-leadership workspaces.

<b>Financial integrity is non-negotiable:</b> visual success must never be shown as confirmed payment until the server has verified the provider's status. A redirect, screenshot or client-side response is not proof of settlement. The existing payment security, webhook, idempotency, reconciliation and audit requirements in Sections 48, 49 and 56 remain authoritative.

### 57.6 Shared design system and connected product consistency

ACADIVA is one connected product, not a collection of separately designed dashboards. Build and maintain a shared design system covering:

- Typography roles and hierarchy.
- Spacing scale, grid, alignment and responsive layout rules.
- Buttons, fields, selectors, tables, cards, dialogs, navigation and notifications.
- Status indicators, badges, empty states, loading states, errors and success states.
- Icons, illustrations, charts, document previews and media treatment.
- Motion, transitions, feedback and reduced-motion behaviour.
- Accessibility, contrast, readable type, keyboard/focus behaviour and touch-target standards.
- Responsive rules for small phones, larger phones, tablets and desktop.

Role-specific workspaces may have different information priorities, but shared components and interaction conventions should remain consistent. A payment status, student identity, result state or attendance state must not be represented differently in ways that confuse users across workspaces.

Brand tokens must remain configurable until the founder approves the ACADIVA identity. Do not hard-code a temporary colour choice throughout the application.

### 57.7 Motion and interaction quality

Animations and transitions should make the product feel responsive and refined, not slow or distracting.

- Use motion to explain state changes, navigation, hierarchy or feedback.
- Keep animations short and purposeful.
- Respect reduced-motion preferences.
- Avoid heavy effects that delay first render, block form completion or harm low-end devices.
- Provide immediate feedback for taps and submissions, while clearly distinguishing local interaction feedback from server-confirmed outcomes.
- Design and test loading, offline, retry, empty, validation, success, failure and permission-denied states—not only the ideal state.

### 57.8 Required design artefacts for every feature

Before a screen is approved for implementation, its design record must include:

- Feature and screen name.
- Intended user role and task.
- Relevant workflow and data dependencies.
- Reference links from the approved platforms, with platform and observed pattern.
- Short explanation of what is being adapted and why.
- ACADIVA wireframe or high-fidelity design.
- Desktop and mobile/responsive behaviour where relevant.
- Component and design-token mapping.
- Interaction and state inventory, including loading, empty, error, offline and success states.
- Accessibility and performance considerations.
- Review outcome and unresolved questions.

A screen with no inspected reference or no documented rationale is <b>not design-approved</b>.

### 57.9 Design review and acceptance gate

A design is ready for implementation only when it passes all applicable checks:

- [ ] Relevant reference research completed across the six approved platforms.
- [ ] Reference URLs and design rationale recorded.
- [ ] Original ACADIVA-specific solution created; no copied proprietary screen or asset.
- [ ] Correct user role, permissions and workflow represented.
- [ ] Connected data and downstream effects understood.
- [ ] Mobile-first layout checked at realistic phone sizes.
- [ ] Tablet/desktop behaviour defined where needed.
- [ ] All important interaction states designed.
- [ ] Accessibility, readability and reduced-motion considered.
- [ ] Performance appropriate for low-bandwidth and lower-powered devices.
- [ ] Consistent with the shared ACADIVA design system.
- [ ] Payment and other sensitive flows preserve security and data-integrity requirements.
- [ ] Design reviewed against the acceptance criteria before coding.

After implementation, compare the real interface with the approved design, test the actual workflow and record visual/functional defects. A design approval is not a release approval.

### 57.10 Connection to the existing ACADIVA blueprint and build gate

This section must be applied together with:

- <b>Section 39:</b> technology infrastructure, engineering controls and existing design direction.
- <b>Section 40:</b> master product, workflow, design and launch checklist.
- <b>Section 42:</b> one authoritative record and automatic cross-dashboard consistency.
- <b>Section 46:</b> connected workspaces, shared data and system map.
- <b>Section 48:</b> external service and integration register.
- <b>Section 49:</b> finance architecture and phased delivery.
- <b>Section 55:</b> governance and mandatory pre-tool/build gate.
- <b>Section 56:</b> connected architecture, data model, integration map, implementation blueprint and engineering artefacts.

This adds a design-research and design-approval gate to the existing engineering gate. It does not replace technical, security, privacy, accessibility, performance or user-acceptance testing.

### 57.11 Mandatory operating rule

<b>No ACADIVA design work should begin or be approved without reference research from the approved design-source library. No implementation should begin until the design has been documented, reviewed and connected to the relevant product workflow and master checklist.</b>

Before every design or implementation tool call, follow Section 55.11 and Section 56.16: reopen the current blueprint and relevant checklist, inspect current state, map dependencies and affected roles, define acceptance tests and risks, make the smallest safe change, test the connected workflow, and record evidence. The design-reference gate is an additional requirement, not an exception to this rule.

### 57.12 Open items — intentionally not decided here

- ACADIVA brand colours and full visual identity.
- Final typography and icon family.
- Final design tool and design-file organisation.
- Which reference products will inform each individual ACADIVA module.
- Final payment provider and supported payment methods.
- Whether a formal design review role will be assigned as the team grows.

These must be decided with evidence at the relevant stage. This section does not claim that any screens have already been researched, designed, implemented or tested.

---

## Section 59 — ACADIVA Visual Experience, Creative Technology Stack & Graphics Architecture

<b>Status:</b> Direction confirmed; implementation and final dependency versions remain subject to repository audit and technical validation.

<b>Visual direction:</b> Balanced — premium and highly usable everyday product interfaces, immersive public-facing experiences, and engaging interactive learning environments.

<b>Priority:</b> Visual creativity and quality. Performance, accessibility, mobile compatibility and maintainability remain mandatory engineering constraints, not reasons to make the product visually ordinary.

### 59.1 Experience principles

ACADIVA must deliver three related but distinct experiences:

1. <b>Public ACADIVA experience:</b> distinctive, polished and memorable; use cinematic storytelling, purposeful motion, selected 3D scenes, custom shader effects and expressive visual design.
2. <b>School operating experience:</b> premium, clear, efficient and responsive; dashboards, forms, tables, finance, records and administration must remain easy to use. Use motion to clarify state and feedback, not to obstruct work.
3. <b>Learning experience:</b> interactive, visual and engaging; use rich illustrations, simulations, 3D models, animated explanations and game-like interactions when they improve understanding.

The same design language must connect all three experiences. ACADIVA should be recognisable even without its logo.

### 59.2 Confirmed application and creative technology architecture

| Layer | Selected technology | Responsibility and boundary |
| --- | --- | --- |
| Application | <b>Next.js + React</b> | Main web application, routing, rendering, portals, school websites and shared interface architecture. |
| 3D rendering | <b>React Three Fiber + Three.js</b> | React-integrated 3D scenes, models, environments, camera control, lighting and interactive 3D learning experiences. |
| Advanced graphics | <b>WebGPU + TSL, selectively</b> | Advanced GPU rendering, procedural effects and computation only where the use case justifies it. Retain compatible fallbacks; do not make WebGPU a universal requirement. |
| Animation | <b>GSAP + ScrollTrigger</b> | Primary system for choreographed motion, timelines, scroll-linked storytelling, complex transitions and cinematic sequences. |
| Interactive animation | <b>Rive</b> | State-driven, interactive vector animation, onboarding, feedback, characters and responsive learning interactions. |
| Cinematic sequencing | <b>Theatre.js — optional / evaluate</b> | Candidate tool for visually authoring and sequencing complex 3D scenes, camera moves, object animation and lighting. Adopt only where it adds clear value alongside GSAP and the 3D stack. |
| 2D graphics | <b>PixiJS — where needed</b> | Specialised GPU-accelerated 2D scenes, particles, interactive diagrams and graphics-heavy learning experiences. Not required for ordinary UI. |
| Custom shaders | <b>GLSL / OGL</b> | Custom shader effects and lower-level WebGL control for distinctive backgrounds, transitions, distortions and procedural visuals. OGL is used only where its lightweight abstraction is useful. |
| 3D design workflow | <b>Spline</b> | Visual creation and prototyping of 3D assets/scenes for selected website and product experiences. It is an authoring workflow, not a required runtime dependency for every page. |

### 59.3 Ownership rules: avoid overlapping tools

- GSAP + ScrollTrigger is the primary system for complex timelines and scroll-driven motion.
- Rive owns self-contained interactive animations and state machines.
- React Three Fiber + Three.js owns interactive 3D rendering.
- Theatre.js remains optional and must not be added by default; evaluate it for scenes where visual timeline authoring materially improves the workflow.
- PixiJS is reserved for specialised 2D graphics, not routine cards, tables or dashboard components.
- GLSL/OGL is reserved for custom GPU effects that cannot be achieved cleanly with CSS or existing rendering tools.
- WebGPU/TSL is progressive enhancement for selected advanced experiences, not a baseline dependency.
- Spline is primarily an asset and scene authoring workflow.
- Do not animate the same component with multiple systems without a documented reason. Avoid adding libraries merely because they are available.

### 59.4 Design system requirements

Create a shared ACADIVA design system covering:

- Colour tokens, typography, spacing, radii, borders, shadows and elevation.
- Buttons, inputs, navigation, cards, dialogs, tables, charts, forms and notifications.
- Role-aware layouts for proprietors, principals, administrators, bursars, teachers, parents and students.
- Responsive rules and consistent component states.
- Motion principles, timing, easing, transitions and interaction feedback.
- Accessible contrast, keyboard navigation, focus states and reduced-motion behaviour.
- A light-first visual identity with white and soft neutral surfaces, forest green as a primary brand colour, restrained mint and blue accents, and readable dark text. Exact palette values remain design tokens to validate in the design phase.

### 59.5 Performance, mobile and accessibility controls

Visual ambition must not make ACADIVA unusable on ordinary smartphones or unreliable networks.

- Lazy-load 3D scenes, shader modules and large visual assets; do not load graphics runtimes on pages that do not use them.
- Use responsive assets, compressed textures/models and appropriate caching.
- Provide static or simplified fallbacks when WebGL/WebGPU or device capabilities are unavailable.
- Adapt scene complexity and effects to device capability; provide a Lite experience for constrained devices.
- Respect reduced-motion preferences and avoid essential information being conveyed only through animation.
- Keep school operations, forms, financial workflows and core navigation fast and functional without 3D.
- Profile actual devices and networks; do not assume performance from desktop development alone.
- Measure rendering performance, loading behaviour, memory use and battery impact during visual QA.

### 59.6 Implementation sequence

1. Establish the Next.js + React application foundation and shared design tokens/components.
2. Build the core role-based school interfaces with responsive, accessible layouts.
3. Introduce GSAP + ScrollTrigger for the public website and selected complex motion.
4. Add Rive for self-contained interactive animation and feedback.
5. Integrate React Three Fiber + Three.js for selected 3D scenes and learning modules.
6. Add GLSL/OGL effects selectively where custom shader work is justified.
7. Evaluate Theatre.js for complex cinematic scene authoring; document the decision before adding it as a dependency.
8. Introduce PixiJS only for specific graphics-heavy 2D use cases.
9. Evaluate WebGPU + TSL progressively, with fallbacks and device testing.
10. Use Spline in the 3D design workflow where it improves asset creation and iteration.

### 59.7 Design and engineering acceptance gate

Before a feature is considered complete, verify:

- It follows the ACADIVA design system and the intended experience category.
- Motion has a clear purpose and does not slow down routine tasks.
- The interface works responsively on mobile and desktop.
- Core content and actions remain usable when advanced graphics are unavailable.
- Reduced-motion and accessibility requirements are respected.
- Assets and graphics are lazy-loaded and appropriately optimised.
- No unnecessary overlapping animation or rendering dependencies have been introduced.
- Visual QA and functional QA both pass on representative devices.

### 59.8 Decision status and change control

The technology roles listed in Section 59.2 record the founder's chosen direction. Theatre.js is explicitly optional and subject to evaluation; WebGPU/TSL and PixiJS are selective; OGL is used only when justified; Spline is an authoring workflow. Exact versions, package configuration, browser support, hosting implications and final dependency choices must be checked against the actual repository before implementation.

Do not silently substitute or remove these technologies. Any proposed change must record the reason, trade-offs, compatibility implications and approval before implementation.

<b>Relationship to earlier documentation:</b> Section 59 supplements Section 39 (technology infrastructure and design direction), Section 57 (premium design standards and design governance), Section 58 (implementation-stage design research gate), and the relevant master execution checklists. It does not replace their security, product, accessibility or engineering requirements.
