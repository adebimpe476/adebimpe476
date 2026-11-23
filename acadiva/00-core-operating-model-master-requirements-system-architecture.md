<!-- Source: https://app.notion.com/p/41c9a9b48b7a814e96e4f5e4cbef2920?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🧭 00 — ACADIVA Core Operating Model, Master Requirements & System Architecture

This is the reorganised <b>core product and system reference</b> for ACADIVA. It brings the five founder-designated governing documents into one deliberate reading order. The original source sections remain preserved on the parent master page; this page is the curated working copy and does not replace the historical record.

## Required reading order

1. <b>Section 60 — Broad Product Operating Model:</b> understand how schools and the platform operate in real life.
2. <b>Section 36 — Master Product Requirements:</b> translate that operating model into explicit product scope, roles, workflows and acceptance requirements.
3. <b>Section 46 — Product Architecture and System Map:</b> understand the connected workspaces, identities, authoritative records and cross-module data flows.
4. <b>Section 56 — System Architecture and Implementation Blueprint:</b> translate the system map into data, security, integrations, dependencies, build order and acceptance scenarios.

These documents must be reviewed together before any meaningful feature or architecture build. They are deliberately not merged into one generic summary because each has a distinct job.

## Permanent reminder

For every build, compare the implementation against this core reference, the Master Execution Checklist (Section 40), the governance/build gates (Sections 55 and 50-C), and the relevant specialist requirements. Reassess during implementation, not only at the end. A feature is not complete merely because its screen exists.

---

## Section 60 — ACADIVA Product Operating Model, Multi-School Architecture, Role Workflows, School Operations, Finance and Cost-Conscious Identity

<b>Status:</b> Consolidated product direction and recommended architecture. This section supplements, rather than replaces, Sections 36–59. Existing decisions in Sections 41, 42, 43, 46, 47, 49, 53, 54, 55 and 56 remain authoritative where already confirmed. New recommendations are identified below; school-policy assumptions requiring validation remain open.

### 60.1 Product operating principle

ACADIVA is a school operating system and connected learning-support ecosystem, not a fully digital replacement for classroom teaching or paper-based school practices. It must support the real operating cycle of Nigerian schools, preserve paper workflows where they remain appropriate, and digitise the records, coordination, calculations, communication and oversight that benefit from a shared system.

The product is organised around three connected layers:

1. School operating system: administration, admissions, student records, academics, staff, finance, communications and school services.
2. Learning support: academic progress, assessments, learning resources and optional interactive learning experiences. Physical classroom teaching, written homework and written examinations remain fully supported.
3. Shared education infrastructure: identity, tenant isolation, records, integrations, audit, reporting, school websites and platform operations.

Do not create isolated feature silos. Every module must connect to the authoritative student, school, academic, staff and financial records.

### 60.2 End-to-end school operating lifecycle

The default school lifecycle is:

1. School onboarding and configuration: create the tenant, verify school identity, configure branding, campuses, academic calendar, levels, classes, arms, subjects, departments, staff roles, fee policies and public website.
2. Admissions: parent or applicant submits an application through the school's public application link; registrar reviews it; school requests clarification, offers admission, waitlists or rejects according to school policy.
3. Enrolment: accepted applicant becomes an official student record; guardian relationships are verified; student is assigned to a session, class and arm; required documents are recorded; applicable invoice is generated.
4. Term preparation: configure term dates, timetable, teacher and subject assignments, class lists, fee invoices, examination calendar, events and notices.
5. Daily school operations: teachers access their timetable, record attendance and assessments, teach and manage assigned classes; administrators handle records, staff, parent enquiries and school operations.
6. Finance: invoices are issued; parents pay through enabled channels; payments are verified; receipts are issued; accounts are updated; collections are reconciled and exceptions investigated.
7. Assessment and examinations: school schedules assessments; students complete classroom and written examinations; teachers enter marks; authorised staff review and approve results; report cards are generated and released.
8. Term closure: lock/finalise approved results, preserve attendance and finance records, reconcile transactions, publish permitted reports and close the term.
9. New term/session: open the next academic period, re-enrol continuing students, process promotions and exceptions, create new invoices, allocate teachers and publish updated timetables.
10. Student exit: record graduation, transfer, withdrawal or other exit status; preserve academic and financial history; produce authorised exports and transfer documents.

The lifecycle must support exceptions, corrections, late admissions, class changes, staff changes, interrupted payments and reopened terms through permissioned, audited actions. Never silently overwrite historical records.

### 60.3 Multi-school and school website architecture

<b>Recommended architecture:</b> one ACADIVA application and shared platform infrastructure, serving many independently isolated school tenants. Do not create a separate codebase, deployment or database for every school by default.

Each school receives:

- A school-specific workspace and branded public website.
- A school subdomain, for example <code>schoolname.acadiva.ng</code>, with optional custom-domain support according to plan and technical readiness.
- Its own logo, permitted colour tokens, school information, contact details, admissions link, news, events, facilities and gallery.
- Independent staff, parent and student relationships; academic records; timetables; fee structures; transactions; announcements; documents and configuration.
- School-controlled roles and permissions within platform-wide security boundaries.

<b>Website template decision:</b> build a shared, configurable school website system, not one rigid page and not separately coded websites. Provide approved templates/layouts and reusable sections. Schools can configure content, branding and permitted page sections through a controlled editor. Standard plan includes branded template and core pages; enhanced plans may offer more layouts and sections; custom domains and advanced options may be plan-dependent. Do not permit arbitrary school-supplied scripts or code injection.

Public website content is separated from private school workspace data. Public pages must not expose student records, parent details, staff-private information or internal financial data.

<b>Tenant model:</b>

- Every school-owned record carries an immutable tenant/school ownership key.
- Resolve tenant context from a verified school domain/workspace and authenticated membership; never trust a client-supplied school ID alone.
- Enforce tenant isolation at database, API/service and storage layers. Use PostgreSQL row-level security where appropriate plus server-side authorisation; RLS is not a substitute for correct server checks.
- School files use tenant-scoped paths and private access policies.
- Platform Operations can perform authorised support actions through audited, least-privilege access; routine platform staff must not have unrestricted access to student records.
- Shared services include identity, application code, notification dispatch, payment orchestration, reporting infrastructure, storage controls, backups and monitoring. Tenant-specific records and configuration remain logically isolated.
- Support a school group with multiple campuses/branches. A group owner may receive consolidated reporting; branch staff see only assigned branches unless explicitly authorised. A single-campus school should not be forced to manage a branch hierarchy.
- Branch-level settings may inherit group defaults but must support explicitly authorised local overrides.
- Design indexes, partitioning/archival strategy, rate limits, background jobs and observability for growth. Do not claim a fixed concurrency capacity until load-tested.

### 60.4 Academic structure and progression

Use a configurable academic hierarchy:

- School year/session, e.g. 2026/2027.
- Terms within the session, normally first, second and third, configurable by school.
- School levels/stages: nursery/early years, primary, junior secondary and senior secondary, where applicable.
- Classes/grades: configurable names such as Primary 1–6, JSS1–3 and SS1–3.
- Arms/streams: A, B, C or school-defined labels.
- Subjects and curriculum allocations by level, class and arm.
- Subject/administrative departments where relevant.
- Teacher assignments, class teachers, subject teachers and timetable slots.

Academic structures must be configurable without allowing a school to accidentally invalidate historical records. Class and subject names may differ between schools.

Promotion is a deliberate, authorised end-of-session process, not an automatic consequence of term closure. Support promote, repeat, graduate/complete, transfer, withdraw and hold/pending decision. Support bulk promotion with individual exceptions and an approval/confirmation step. Preserve each student's historical session, class, arm, subjects, results, attendance and report cards. A student moving from SS1 to SS2 must retain the SS1 history.

Grading scales, assessment components, weights, pass rules and result layouts should be configurable by authorised school roles using validated templates. Preserve the exact rules/version used to calculate historical results.

### 60.5 Parent and guardian experience

Retain Section 53's confirmed direction: one guardian identity can be linked to multiple verified children, including children at different ACADIVA schools. A child can have multiple authorised guardians, each with their own account and explicitly assigned permissions.

Parent workspace requirements:

- One sign-in and a family overview, with a clear switcher for each child and school.
- Per-child results, attendance, report cards, invoices, payment history, receipts, notices, calendar and relevant school communication.
- A parent can access only children for whom the school has verified a guardian relationship.
- Never link children based only on matching names, phone numbers or email addresses without a school-controlled verification process.
- A guardian's permissions can differ by child and school. Support view-only, academic access, financial access, admissions/contact authority and other narrowly defined permissions.
- Provide secure account recovery and a process for phone-number changes, guardian disputes and revoked access.
- A guardian account can be prepared during school onboarding and activated later, consistent with Section 54.

Parent-child linking, guardian approval and access revocation must be auditable. Do not disclose one guardian's private account information to another guardian.

### 60.6 Teacher experience

Retain Section 41's simplified teacher experience and Section 40's role checklist. Teacher workflow should be focused on the teacher's assigned responsibilities:

1. Sign in and see today's timetable, classes, subjects and upcoming tasks.
2. Open an assigned class and mark attendance using a fast, minimal workflow.
3. Access class lists and relevant student information permitted for teaching.
4. View or prepare lesson plans and teaching resources where enabled.
5. Record continuous assessment and examination marks.
6. Save drafts, submit results for review and respond to authorised corrections.
7. Receive school/class announcements, timetable changes and relevant notices.
8. View workload, teaching assignments and deadlines.

Teachers see only assigned classes/subjects and other records explicitly granted to them. Teachers cannot unilaterally change official student placement, approved grading rules or published results. Result edits after approval require authorised reopening, reason capture and audit history. A teacher may hold multiple roles in a small school without receiving blanket access.

### 60.7 Student access and paper-first learning

<b>Confirmed product direction from this decision:</b> ACADIVA must not require every student to own or use a smartphone. Do not make a parent's phone the compulsory student device. Do not force digital homework submission or fully computer-based examinations.

Default school model:

- Classroom teaching remains physical.
- Homework and assignments may be written in exercise books and submitted physically.
- Written examinations remain supported; ACADIVA records schedules, marks, grading and results rather than requiring all examinations to be CBT.
- Teachers enter assessment/examination marks into ACADIVA.
- Report cards can be viewed digitally by authorised guardians and printed by the school.
- Digital learning materials and interactive experiences are optional supplements.
- No student is disadvantaged for not having a device or personal login.

Student accounts are optional and school-enabled, with age-appropriate controls and parent/school authorisation. Younger pupils should not need independent accounts. Older students may be given restricted access to their timetable, notices, results and approved learning resources. Student access must not expose finance, guardian data, other students' records or unrestricted messaging. Paper registers, score sheets, examination records and report-card printing remain supported.

### 60.8 School management and operational modules

Build the school workspace around role-specific permissions and a coherent daily operating model.

<b>Core operational modules:</b>

- Governance and configuration: school profile, calendar, academic setup, branches, departments, users, roles, policies, approvals and audit trail.
- Admissions and student records: applications, offers, enrolment, biodata, guardian relationships, documents, class allocation, promotion, transfers and exits.
- Academic administration: classes, arms, subjects, curriculum mapping, teacher allocation, timetable, attendance, assessments, examinations, results and report cards.
- Human resources: staff profiles, employment records, roles, departments, teaching assignments, attendance, leave, staff documents and payroll records.
- Finance: fee setup, invoices, collections, receipts, refunds/credits, expenses, reconciliation, reporting and audit history.
- Communication: school-wide and class-specific announcements, circulars, events, parent notices and controlled communication channels.

<b>Phased operational modules:</b>

- Facilities and assets: classrooms, furniture, equipment, asset register, stock/inventory, issue/return, maintenance requests, suppliers and purchase orders.
- Student welfare and safeguarding: discipline, commendations, incident reports, counselling referrals, emergency contacts and restricted health/safeguarding records. Access must be tightly limited and logged.
- School services: library catalogue and borrowing, transport routes, vehicles, drivers, student transport assignments, clubs, extracurricular activities, events and visitor management.
- Institutional intelligence: enrolment, retention, attendance, academic performance, fee collection, staff workload and branch comparisons.

Do not place every module in the first release. Core records, admissions, academics, finance, parent access and daily teacher workflows take priority. Add operational modules based on validated school demand and delivery capacity.

Role templates should include proprietor, principal/head teacher, vice principal, registrar, bursar, accountant, HR officer, teacher, librarian, transport officer, parent/guardian and optional student. Schools can assign multiple roles to one person and grant narrowly scoped additional permissions. No role should automatically receive access to all student, finance, HR or safeguarding information.

### 60.9 Financial operating model

Retain Sections 47 and 49: use a free-tier-first, cost-conscious staged implementation while preserving accounting integrity. The school owns fee policies and authorises adjustments. ACADIVA maintains the authoritative financial ledger and audit history.

<b>Billing and collection flow:</b>

1. School configures fee categories and amounts, including tuition, development levy, examination fees, books/materials, uniforms, transport, boarding and other school-defined charges.
2. ACADIVA creates a student/term invoice with line items, due date, total and status.
3. Parent pays using a school-enabled channel: online gateway, supported transfer flow or another approved method.
4. ACADIVA verifies payment server-side through gateway confirmation/webhook or a controlled manual reconciliation process.
5. A confirmed payment creates a receipt, updates the invoice and student account, updates collection reports and stores the provider/reference details.
6. Bursar/accountant reconciles gateway settlements, bank credits, manual entries, refunds and exceptions.

A screenshot or parent-entered claim is not proof of payment. Manual transfer entries must remain pending until verified by an authorised staff member against bank/provider evidence. Webhook processing must be idempotent; duplicate events must not create duplicate receipts or ledger entries.

<b>Full-payment policy:</b> full payment of the billed amount is the default. Instalments are not the default and may be enabled only where a school explicitly configures an instalment policy. The system must nevertheless represent partial payments and outstanding balances accurately when they occur; it must not falsify a full-payment status.

<b>Discounts, scholarships, waivers and refunds:</b>

- A scholarship/discount/waiver approved before payment is a separately recorded adjustment with reason, authoriser, amount, effective invoice and audit history.
- A refund after payment is a separate, traceable transaction linked to the original payment and invoice. It requires an authorised approval and records amount, reason, destination/status and provider reference where applicable.
- A school may issue a credit against a future invoice instead of returning cash. Credits must be recorded separately and applied transparently.
- Never edit or delete a completed payment to simulate a refund or discount.
- Define approval thresholds and separation of duties for fee changes, refunds, write-offs and expense approvals.
- Preserve immutable financial event history and produce an audit trail.

<b>Payment-provider architecture:</b> build a provider-independent payment orchestration layer. Paystack may be evaluated as an initial integration; Flutterwave and other providers remain alternatives until a documented comparison is completed. ACADIVA owns invoices, student accounts, receipts, refunds, credits, reconciliation and ledger integrity. The provider processes payment and reports transaction/settlement events. Compare fees, settlement timelines, supported methods, refund behaviour, webhook reliability, dispute handling and business requirements before selecting the initial provider. Do not bind the financial data model to one gateway.

<b>Cost-conscious phasing:</b> begin with internal fee records, receipts, authorised manual verification and CSV reconciliation where necessary. Add online payment integration when the provider and operating costs are justified. Do not add paid services or complex accounting subscriptions without a demonstrated need.

### 60.10 Cost-conscious authentication and identity architecture

<b>Decision:</b> phone number is the primary user identifier/contact and a supported login identifier, especially for Nigerian parents and guardians. It is not a requirement to send an SMS OTP every time a user signs in. Phone number as identity must be distinguished from the authentication method.

<b>Do not use routine SMS OTP as the default login flow.</b> Repeated OTP messages create avoidable recurring costs, delivery delays and user friction. SMS OTP is reserved for limited verification/recovery events where the risk justifies the cost.

<b>Recommended sign-in choices:</b>

1. Phone number + password: primary practical option for users who want to sign in with their phone number. Password is securely hashed; never stored in plaintext.
2. Continue with Google: optional OAuth sign-in for users who prefer it. Link the Google identity to the existing ACADIVA account only after a safe account-linking check; do not create duplicate accounts for the same person.
3. Continue with email magic link: optional passwordless route for users with reliable email access. Email link delivery still has a cost and must be rate-limited; it is not required for every user.
4. Passkeys/device biometrics: evaluate as a progressive enhancement when supported by the chosen authentication stack and target devices. A passkey can reduce password friction without an SMS per login; provide recovery alternatives.

Phone number is the primary contact and account lookup identifier, but each person should have an immutable internal user ID. Email is optional and can be linked as an additional sign-in/recovery method. A school-issued username or staff identifier may be supported as an additional lookup route where useful, but must resolve to the same user identity and permissions.

<b>Session strategy:</b>

- After successful authentication, issue a secure session and refresh it safely; do not ask for a new OTP on every page visit or routine return.
- Remember trusted personal devices according to security policy; let users view and revoke active sessions/devices.
- Provide explicit sign-out and account-switching. On shared school/family devices, do not silently persist sensitive sessions indefinitely; support shorter session lifetimes, inactivity lock and clear logout.
- Use secure, HttpOnly, SameSite cookies for web sessions where applicable; protect against CSRF and session theft. Never place long-lived secrets in local storage.
- Apply rate limits, credential-stuffing protection, password hashing, breach-aware password policy, audit logs and suspicious-login detection.
- Do not make security depend only on SMS possession.

<b>When to use SMS OTP or another step-up challenge:</b>

- Initial phone-number verification when a phone number is first added or claimed, if the school/user context requires proof of possession.
- Changing the primary phone number.
- Account recovery when no safer verified recovery method is available.
- A suspicious sign-in or high-risk account action where a step-up check is justified.
- Other exceptional cases required by risk policy.

Do not send SMS OTP for every login, every dashboard navigation, every routine session refresh or ordinary low-risk activity. Where a step-up challenge is needed, use the least costly secure method available: an existing trusted session, passkey, Google re-authentication, email recovery link or one-time recovery code where appropriate; SMS is a fallback where phone possession must be verified.

<b>First-time activation and account recovery:</b>

- School onboarding prepares guardian/staff relationships and sends an invitation or activation link through an approved channel.
- Users set a password or connect Google/passkey during activation. Phone verification is performed only when needed to verify ownership, not repeatedly.
- If the school has a guardian phone number but no email, the parent can activate with phone plus password after a controlled one-time verification/assisted process.
- Recovery options should prioritise verified email, passkey or recovery codes where available. For users without these, use a controlled school-assisted identity verification workflow and a one-time phone verification only when necessary.
- Changing a phone number must require stronger verification and audit. School staff must not be able to take over a parent's account merely by editing the student's contact record.
- Account linking must avoid duplicate identities and must never merge accounts based solely on a matching display name.

<b>Authentication cost controls:</b>

- Prefer password-based sessions, Google OAuth and passkeys over repeated SMS.
- Treat email magic links as an optional method, not a free service; monitor sending volume, bounce rate and provider cost.
- Rate-limit login, password reset, magic-link and verification requests; add resend cooldowns and abuse protection.
- Avoid sending an OTP to every guardian whenever they open the app.
- Track authentication cost per active user and per school, SMS volume, email volume, failed deliveries, recovery frequency and suspicious activity.
- Compare provider pricing and capabilities before finalising the authentication implementation. Keep the application identity model provider-independent enough to change providers without rewriting school/guardian relationships.

### 60.11 Security, privacy and reliability requirements

- Enforce tenant isolation in database queries, server-side services, file access, exports, search and background jobs.
- Apply least privilege and role/record-level permissions; sensitive health, safeguarding, finance, HR and guardian records require narrower access.
- Record audit events for sensitive reads where appropriate, edits, exports, role changes, result approvals, fee changes, refunds, account recovery and platform support access.
- Protect child and guardian information; define consent, retention, correction, export and deletion processes in line with applicable Nigerian data-protection requirements.
- Maintain encrypted transport, appropriate encryption at rest, secure secrets management and regular dependency/security review.
- Back up database and files; define recovery objectives, restore procedures and test restores rather than assuming backups work.
- Monitor failed jobs, payment webhook errors, notification delivery, authentication abuse, tenant-boundary violations and service health.
- Design offline-tolerant teacher workflows where justified, with explicit sync state and conflict handling. Never silently overwrite newer authoritative records.
- Load-test realistic school workloads, especially admission periods, result publication and simultaneous fee/payment activity. Do not claim a scale limit without measured evidence.

### 60.12 Delivery priorities

<b>Foundation / core release:</b>

- Tenant and identity foundations, school setup, role permissions and audit.
- School website template and admissions application journey.
- Student records, guardian relationships and bulk onboarding.
- Academic sessions, terms, levels, classes, arms, subjects and teacher assignments.
- Teacher timetable and attendance.
- Assessment, written examination score entry, approval and report cards.
- Parent workspace with multiple children/schools and controlled permissions.
- Fee invoices, payment recording, receipts and reconciliation.
- Announcements and essential notifications.
- Backups, security tests, exports and operational monitoring.

<b>Subsequent phases:</b>

- Provider-integrated online payments and advanced reconciliation.
- Staff leave/payroll enhancements.
- Inventory, procurement, facilities and maintenance.
- Library, transport, visitor management and extracurricular activities.
- Student optional accounts and richer learning resources.
- Advanced analytics, AI-assisted learning support and interactive 3D learning environments.
- Enhanced school website layouts, custom domains and advanced group/branch reporting.

Feature sequencing must continue to follow Sections 55, 56, 57 and 58: inspect the blueprint, define workflow and acceptance criteria, research design references, approve design, plan technical changes, implement a complete vertical slice, test connected roles and record evidence.

### 60.13 Open validation items

The following are recommendations requiring validation with representative Nigerian schools; they are not falsely recorded as universal school rules:

- Common variations in term calendars, grading scales, assessment weights, promotion rules and class naming.
- Which staff roles and approval chains are typical in small, medium and larger schools.
- Which operational modules (transport, library, inventory, payroll, discipline) are essential to pilot schools.
- Parent communication preferences and realistic email/SMS use.
- Whether a school group needs group-level billing, central HR or cross-branch student transfers.
- Payment-provider selection after fee, settlement and reliability comparison.
- Authentication provider capabilities, exact pricing, passkey support and account-recovery design against the chosen stack.
- Exact retention periods, safeguarding workflows and data-protection obligations reviewed for the operating context.

Do not block the core architecture on optional future modules. Validate policy variations through school interviews and pilot workflows, then configure them rather than hardcoding one school's practices into ACADIVA.

### 60.14 Relationship to earlier decisions

- Section 40 remains the comprehensive role-by-role and module-by-module execution checklist.
- Section 41 remains authoritative for simplified parent-owned student access, teacher workflow boundaries, timetables, minimal attendance, announcements and optional homework.
- Section 42 remains authoritative for one source of truth and cross-dashboard consistency.
- Sections 43 and 54 remain authoritative for admissions and school-led onboarding.
- Section 46 remains the connected workspace and shared data architecture foundation.
- Section 47 remains the latest school finance and academic term lifecycle decision record.
- Section 49 remains the free-tier-first finance delivery strategy.
- Section 53 remains authoritative for parent identity, multi-child access and guardian relationships.
- Section 55 remains authoritative for operations governance and school-level configuration.
- Section 56 remains authoritative for the connected system architecture and implementation blueprint.
- Sections 57–59 remain authoritative for design research, implementation gates and creative technology architecture.

Section 60 consolidates and extends these decisions. If a conflict is found, preserve the earlier record and add a dated decision/change note; do not silently delete or rewrite historical decisions.

---

## 36. ACADIVA master product requirements and operating model

<b>Status:</b> Consolidated product requirements baseline, added 15 November 2026. This section organises the product scope into one coherent operating model. It supplements Sections 1–35; it does not delete or invalidate earlier material. Where an older proposal conflicts with a confirmed decision below, this section is the current reference and the earlier wording remains as decision history.

### 36.1 Product principle

ACADIVA is a school operating system for Nigerian schools. It connects the complete school lifecycle: public discovery and admissions, student records, academic organisation, teaching, attendance, assessment, results, parent engagement, school fees, finance, staff administration, communication, documents and management reporting.

The product must work for a small school with a proprietor, principal and a few teachers as well as a larger school with separate departments and finance staff. It must not assume that every school has a large administrative team, a dedicated accountant, a full-time ICT officer or reliable access to laptops.

Core principles:

- One authoritative student record, reused across every relevant module.
- Role-specific workspaces rather than one generic dashboard.
- Configurable school rules for grading, attendance, billing, approvals and school structure.
- Strong privacy, school-level tenant isolation and least-privilege access.
- Every consequential financial, academic and administrative change is traceable.
- Important records can be printed or exported without forcing users to re-enter information.
- Mobile-friendly workflows for teachers and parents, with full administrative capability on desktop/tablet and responsive mobile.
- Build a coherent foundation first; release advanced modules progressively.

### 36.2 Product user roles and workspaces

The role model is permission-based. A user may hold more than one role in a small school, but access must be granted explicitly and actions must be attributed to the individual account.

| Role | Primary workspace and responsibilities |
| --- | --- |
| Proprietor / Owner | Executive oversight, financial visibility, school performance, staff and high-impact approvals |
| Principal / Headteacher | School operations, academics, staff supervision, attendance, results and communication |
| Vice Principal / Deputy | Delegated academic or administrative oversight |
| Bursar / Finance Officer | Fee structures, billing, collections, payment plans, receipts, expenses and reconciliation |
| Accountant | Financial review, reporting, reconciliation and authorised accounting records |
| Admissions Officer / Registrar | Enquiries, applications, admissions, enrolment and student records |
| School Administrator / Secretary | Daily records, correspondence, documents, notices, calendar and administrative support |
| Teacher / Class Teacher | Assigned classes, attendance, assessments, marks, results, timetable and authorised student information |
| Head of Department / Academic Lead | Subject/department oversight, assessment review and delegated result approvals |
| Parent / Guardian | Only linked children's academic, attendance, fee and school communication records |
| Student | Age-appropriate timetable, assignments, approved results, learning resources and notices |
| ICT / School System Administrator | School user setup, access, configuration, devices and technical administration |
| ACADIVA Platform Support | Restricted support access with explicit authorisation, reason, audit trail and time-bound access where feasible |

Role combinations are permitted (for example, proprietor and principal). Do not create duplicate identities merely because one person has multiple responsibilities. Sensitive permissions such as approving refunds, changing published marks, confirming manual payments and exporting sensitive data should be separable from general role membership.

### 36.3 School setup and academic structure

Each school configures its own identity and operating model:

- School name, logo, address, phone, email, public profile and branding.
- Education levels: nursery/early years, primary, junior secondary, senior secondary or school-defined equivalents.
- Academic sessions, terms, holidays, resumption and closing dates.
- Class groups, arms/streams, departments and class capacity.
- Subjects and subject combinations.
- School days, lesson periods, break periods and rooms.
- Grading scales, assessment components, weightings and result remarks.
- Attendance statuses and notification policies.
- Fee categories, fee schedules, billing rules and approval thresholds.
- Staff roles, permissions and delegated approval chains.
- Branches/campuses if enabled by the subscription and implementation.
- School document identity: letterhead, report-card format, receipt format, signatures and authorised stamp assets.

ACADIVA must provide useful Nigerian school templates while allowing each school to customise its structure. No one class naming convention, grading scale, term calendar or fee structure should be hard-coded as universal.

### 36.4 Admissions, enrolment and student lifecycle

The admissions workspace supports the journey from enquiry to an active student.

1. Record an enquiry or receive an online application.
2. Capture applicant and parent/guardian details.
3. Record previous school, class applied for and relevant application information.
4. Collect required documents.
5. Track application status and review notes.
6. Record entrance assessment/interview where the school uses one.
7. Approve, reject, waitlist or request further information.
8. Generate an admission offer/letter.
9. On acceptance, create or match the authoritative student record.
10. Assign a unique admission number, academic session, class and stream.
11. Link and verify parent/guardian accounts.
12. Capture emergency contacts and school-required records.
13. Generate the initial fee bill where applicable.
14. Activate the student in class lists, attendance, timetable and academic workflows.

Student lifecycle statuses should include configurable equivalents of applicant, admitted, active, promoted, transferred, withdrawn, suspended, graduated and archived. A student leaving school must not cause their historical academic or financial records to be deleted. Duplicate detection and controlled merging are required.

Student profile data may include biodata, photograph, admission number, class history, guardian relationships, contact details, documents, attendance, results, fee account, achievements and authorised notes. Medical/emergency details are sensitive and must be visible only to authorised staff.

### 36.5 Teacher workspace

The teacher dashboard should answer: what classes do I teach, what do I have today, what needs action and how are my students doing?

Teacher home:

- Today's timetable and next lesson.
- Assigned classes and subjects.
- Number of students in assigned classes.
- Attendance awaiting submission.
- Assessments and marks awaiting completion.
- Results awaiting submission or correction.
- School notices and upcoming events.
- Important birthdays and reminders for assigned students, subject to school policy.

My Classes:

- Class and stream list.
- Subject assignment and class-teacher responsibility.
- Student roster with photograph, name and admission number.
- Class timetable and room.
- Student attendance overview.
- Assessment and result overview.
- Birthday calendar/list.
- Relevant teacher notes and authorised student information.

Attendance:

- Record daily school attendance for assigned classes where delegated.
- Support present, absent, late, excused and school-authorised activity/away statuses.
- Bulk mark all present, then adjust exceptions.
- Add reason or note where appropriate.
- Record lesson-level attendance separately from whole-school daily attendance.
- Submit attendance and retain a timestamp and responsible user.
- Corrections require permission, reason and audit history.
- Prevent attendance on non-school days or school closure dates unless an authorised exception is recorded.

Assessment and marks:

- Support continuous assessment, class tests, assignments, projects, practicals, mid-term tests and examinations.
- Assessment structure and maximum scores are school-configurable.
- Teacher enters scores in a class mark sheet, with autosave/draft handling and clear submission status.
- Validate scores against maximum values and flag missing, duplicate or anomalous entries.
- Calculate totals, weighted scores, percentages, grades and remarks according to school rules.
- Provide subject average, class average, highest/lowest score, pass/fail counts and performance distribution.
- Identify missing marks and students who did not sit an assessment; do not silently treat missing as zero.
- Flag students who are failing or whose performance is declining.
- Allow teacher intervention notes and follow-up tracking with appropriate privacy.

Result workflow:

- Teacher prepares and submits.
- Reviewer/HOD step is available where configured.
- Principal or designated academic approver authorises publication.
- Published results become parent/student-visible according to school policy.
- Published results are locked; corrections require a reason, permission and retained before/after values.
- No teacher may silently edit an already published result.

Teacher timetable:

- Daily and weekly views, class, subject, period, room and free periods.
- Examination duties and approved substitutions where enabled.
- Prevent teacher, class and room timetable conflicts.
- Changes must notify affected teachers and, where appropriate, students/parents.

Student performance view:

- Scores and trend over time for assigned subjects/classes.
- Attendance patterns.
- Incomplete assessments.
- Students at risk and recorded interventions.
- Birthday reminders and approved student profile information.
- Teachers do not automatically receive access to family financial balances or unrelated confidential records.

### 36.6 Attendance system and parent attendance experience

Attendance is a shared school record with distinct daily and lesson-level concepts.

- Daily attendance records whether a student attended school.
- Lesson attendance records whether a student attended a particular class/period.
- Staff attendance is a separate record type.
- Attendance statuses, school days and thresholds are configurable.
- Late arrival should include time where the school needs it.
- Excused absence should be distinct from unexcused absence.
- Corrections must preserve the original value, new value, actor, time and reason.
- School closure, holidays, weekends and approved school activities must be excluded from ordinary absence calculations.

Parent attendance views:

- Today's attendance status.
- Immediate absence alert, if enabled by the school.
- Weekly attendance summary (for example, attended 5 of 5 scheduled school days).
- Monthly attendance report.
- Present, absent, late and excused day counts.
- Exact dates of absence and late arrival.
- Attendance percentage and downloadable PDF report.

Example weekly message: “Dear Parent, \[Student Name\] attended school on all 5 scheduled school days this week. Thank you for supporting your child's education. — \[School Name\].”

Notifications must use actual submitted attendance records, not assumptions. Schools configure SMS, email and in-app channels, timing and costs. Delivery status and failed messages should be visible to authorised administrators. Do not send a “perfect attendance” message when attendance is incomplete or the school has not confirmed the relevant records.

### 36.7 Assessment, grading, result processing and academic progression

<b>Confirmed product direction:</b> Use standard Nigerian-school-oriented grading and assessment templates with full school-level customisation.

- Provide reusable templates for common assessment structures.
- Schools can configure component names, maximum scores, weightings, grade bands, remarks, pass thresholds and subject-specific rules.
- Support percentage and average calculations as standard.
- Support GPA/grade-point calculations only where a school explicitly configures them; do not impose university-style CGPA on nursery, primary or secondary schools.
- Provide explicit passed/failed labels and accessible visual indicators. Red may indicate failed/at-risk and green passed, but colour must never be the only indicator.
- School-configured ranking/position display; ranking may be disabled.
- Separate missing, absent, exempt and zero-score states.
- Generate subject reports, class summaries, student report cards and historical comparisons.
- Support result approval chains configured by the school (teacher → HOD/reviewer → principal, or a simpler authorised workflow).
- Promotion is a separate end-of-session decision. The system may recommend progression based on school rules but must not automatically demote or promote a student without the configured authorised review.
- Retain a complete academic history when students change class, repeat, transfer or graduate.

### 36.8 Parent and guardian workspace

Parent access must be verified and restricted to linked children. A parent may have multiple children in one school and should be able to switch between child profiles.

Parent home:

- Child name, photograph, class and school identity.
- Today's attendance.
- Recent academic progress.
- Outstanding fees and next due date.
- Recent school notices.
- Upcoming PTA meetings, excursions and events.
- Important actions requiring parent response.

Academic:

- Approved test, continuous assessment and examination scores.
- Subject totals, percentages, grades and remarks.
- Current and previous term report cards.
- Teacher feedback and areas for improvement.
- Timetable, homework, assignments and examination dates where enabled.
- Awards, achievements and relevant conduct feedback.

Finance:

- Fees billed, paid and outstanding.
- Itemised fee statement.
- Full or approved instalment schedule.
- Parent requests for alternative payment arrangements and their status.
- Payment history, receipts, refunds and concessions.
- Ability to pay one child or multiple linked children's selected bills in a combined checkout, with each payment allocation separately recorded.
- Never expose another family's or another child's financial details.

Attendance:

- Immediate absence notification where enabled.
- Weekly and monthly summaries.
- Attendance history and dates absent/late.
- Downloadable attendance PDF.

Communication and school life:

- School-wide and class-specific announcements.
- PTA meeting date, time, venue/link, agenda, RSVP and reminders.
- Excursion details and digital consent/permission forms.
- Sports day, events, resumption dates, holidays and school closure notices.
- Examination timetables, book/uniform requirements and school circulars.
- Parent-to-school and permitted parent-to-teacher communication through official channels.
- Appointment requests, complaints and acknowledgement/status tracking.
- Notification preferences and communication history.

For younger pupils, access should be parent-managed. Student accounts are optional and age/level appropriate.

### 36.9 Student workspace

Where the school enables student accounts, provide age-appropriate access to:

- Personal timetable and subjects.
- Homework and assignments.
- Examination schedule.
- Approved results and report cards.
- Learning resources shared by teachers.
- School notices and calendar.
- Achievements and awards.
- Relevant submission status.

Younger children should not be forced to maintain independent accounts. Access and features should be configurable by school level and age.

### 36.10 Principal and proprietor management workspace

Provide distinct role-aware management views. The proprietor needs executive and financial oversight; the principal needs operational and academic control. Schools may delegate selected views and approvals.

Executive overview:

- Total active students and enrolment by section/class.
- New admissions, transfers and withdrawals.
- Total teachers and staff.
- Today's student and staff attendance.
- Absent and late students.
- Classes and timetable overview.
- Academic performance and result publication status.
- Total billed, collected and outstanding fees.
- Pending payment-plan requests and financial exceptions.
- Upcoming events and school notices.
- Pending approvals and operational alerts.

School structure:

- Early years/nursery, primary, junior secondary, senior secondary and custom sections.
- Classes, streams, capacity and enrolment.
- Class teachers and subject teachers.
- Subjects and departments.
- Class and teacher timetables.
- Attendance and performance by class.

Academic oversight:

- Overall and section-level averages.
- Class and subject averages.
- Pass/fail counts and rates.
- Students at academic risk.
- Missing assessments and marks.
- Teachers with outstanding result submissions.
- Term-on-term comparisons.
- Approval and publication controls.

Attendance oversight:

- School-wide and class-level daily attendance.
- Present, absent, late and excused counts.
- Repeated absence alerts.
- Monthly trends.
- Staff attendance if enabled.

Staff oversight:

- Staff directory, roles and departments.
- Teaching assignments and workload.
- Staff attendance and leave.
- Qualifications and employment documents.
- Performance review records where enabled.
- Restricted salary and employment information.

Operations and approvals:

- Admissions awaiting decision.
- Results awaiting review/approval.
- Payment-plan requests.
- Fee discounts/waivers.
- Refund requests.
- Manual payment verification.
- Attendance corrections.
- Timetable changes.
- Expense approvals.
- Staff leave requests.
- Important document approvals.

Dashboard cards and metrics must be actionable: clicking a count opens the relevant filtered records. Data must be current and show its date/time context.

### 36.11 Bursar, accountant and finance workspace

Finance is a dedicated workspace, not a small dashboard widget.

Fee configuration and billing:

- Configure fee categories, descriptions, amounts and due dates.
- Apply fees by session, term, class, student or approved group.
- Support mandatory/optional, recurring/one-time and individual charges.
- Support mid-term admissions and prorated/custom bills where school policy allows.
- Publish bills in bulk or individually.
- Record authorised discounts, scholarships, concessions and waivers.
- Preserve original charge and record adjustments separately.

Collections:

- Full and partial payments.
- Online card, bank transfer, USSD and virtual account methods where supported by the selected provider.
- Offline cash and direct bank transfer recording.
- Unique payment references and receipts.
- Pending, successful, failed, expired, reversed, refunded and under-review statuses.
- Parent-facing and internal transaction histories.
- Provider charges and settlement references.

Payment plans:

- School-defined full payment or instalment schedules.
- Custom number of instalments and due dates.
- Amount/percentage validation; instalments must reconcile to the bill.
- Parent may request an alternative arrangement with proposed amounts/dates and optional explanation.
- Request remains pending until authorised school review.
- Authorised bursar/principal can approve, reject, request clarification or propose a revised schedule according to school permissions.
- A pending request does not silently replace the original schedule.
- Approved schedule changes preserve all prior successful payments and history.

Reconciliation:

- Compare ACADIVA transaction records with payment-provider records and actual school bank settlements.
- Identify unmatched, duplicate, delayed, reversed or discrepant transactions.
- Record provider fees, net settlement, settlement batch/reference and date.
- Support CSV/XLSX upload or export where appropriate.
- Manual verification must record evidence, verifier, date and reason.
- A payment screenshot alone is not proof of a successful bank transfer.

Financial overview and reporting:

- Amount billed, amount collected, amount outstanding and overdue amount as separate metrics.
- Collections by class, student, fee category, term, date and payment method.
- Defaulters/outstanding balance lists restricted to authorised finance users.
- Partial payments, discounts, refunds and reversals.
- Daily, weekly, monthly and termly collection reports.
- Student statements and class fee statements.
- Provider settlement and reconciliation reports.
- Expenses and income reports.
- No public ranking or disclosure of students with unpaid fees.

Expenses:

- Categories such as salaries, utilities, facilities, academic materials, transport, administration and other school-defined expenses.
- Record title, category, amount, date, supplier/payee, payment method, attachment/receipt and recorder.
- Optional approval thresholds and second-person approval.
- Expense history and exportable reports.
- Initial product scope is finance administration and reporting, not a claim to replace full statutory accounting or payroll software.

Refunds and corrections:

- Refund request, reason, amount, original transaction and approval.
- Full and partial refunds where provider supports them.
- Record refund processing status and provider reference.
- Adjustments must not overwrite the original transaction or bill.
- Duplicate payments and wrong allocations require a traceable correction process.
- No ordinary user can delete a successful payment.

Funds flow:

- Default architecture is direct settlement to the school's designated account through a suitable licensed payment provider, subject to provider capability and legal/commercial confirmation.
- ACADIVA records bills, transactions, allocations, receipts and reconciliation; it should not casually hold or pool school funds.
- Provider selection must consider settlement reliability, webhook security, fees, refunds, reconciliation and API quality.
- ACADIVA must not store raw card details.

### 36.12 Admissions officer / registrar workspace

The registrar manages:

- Enquiries and applicant pipeline.
- Online and manually entered applications.
- Parent/guardian information.
- Previous school and class applied for.
- Application documents and completeness.
- Entrance test/interview records where used.
- Admission decision and offer letters.
- Accepted applicant conversion to student.
- Admission numbers and class placement.
- Parent linking and verification.
- Initial fee billing handoff.
- Transfer, withdrawal and graduation processing.
- Duplicate student detection and record corrections.

The registrar should not automatically have authority to approve discounts, refunds or financial write-offs.

### 36.13 School administration and secretary workspace

The secretary/admin workspace includes:

- Student and staff directory access as permitted.
- Official correspondence and circulars.
- Document creation and archive.
- School calendar and event administration.
- PTA meeting notices and RSVP records.
- Excursion forms and parent consent.
- Visitor register where enabled.
- Meeting schedules and minutes.
- School policy and template library.
- Admission and student document follow-up.
- Staff and parent contact directory.
- Administrative task tracking.

### 36.14 Staff management and HR

- Staff profile, photograph and unique staff identifier.
- Contact details and emergency contact.
- Role, department and employment status.
- Qualifications, certificates and uploaded documents.
- Teaching assignments, classes and subjects.
- Timetable and workload.
- Staff attendance and lateness.
- Leave application, approval and history.
- Onboarding and exit checklist.
- Performance review records.
- Salary and payroll records only for authorised finance/management users.
- Staff announcements and document access.
- Deactivate access promptly when employment ends while preserving audit history.

### 36.15 Communication, notifications and messaging

Provide one school-controlled communication centre with:

- School-wide announcements.
- Section/class-specific announcements.
- Parent, teacher, student and staff targeting.
- Scheduled and urgent notices.
- PTA invitations, event reminders and excursion information.
- Payment reminders and receipts.
- Attendance alerts and summaries.
- Result publication notifications.
- Homework and examination reminders.
- Direct parent-school communication.
- Complaint and enquiry tracking.
- Message history and delivery status.

Channels may include in-app, email, SMS and push notifications. Channel availability and costs must be transparent. SMS should use a school-funded allowance or usage-based billing; do not promise unlimited messages. Delivery failure must be visible. Critical messages may need retry/escalation rules. Respect consent, privacy and communication preferences.

### 36.16 Timetable and school calendar

Timetable:

- School-wide, class, teacher and room views.
- Daily and weekly timetable.
- Subjects, periods, duration, room and assigned teacher.
- Free periods and approved substitutions.
- Examination timetable and invigilation duties.
- Conflict detection for teacher, class and room.
- Change history and notifications to affected users.

Calendar:

- Academic session and term dates.
- Resumption and closing.
- Holidays and school closures.
- PTA meetings.
- Excursions, sports days and school events.
- Examination dates.
- Staff events and deadlines.
- Parent-facing and internal event visibility controls.

### 36.17 Document generation, printing and exports

<b>Confirmed product direction:</b> Printable and downloadable records are a core platform capability, not an afterthought.

Supported formats:

- PDF for official, printable and shareable documents.
- CSV for portable data exchange.
- XLSX for spreadsheet analysis and administrative work.

PDF generation:

- School logo, identity and configurable letterhead.
- Consistent typography and page layout.
- Page numbers and document date.
- Academic session/term where relevant.
- Authorised signature/stamp fields where appropriate.
- Print-friendly spacing and repeated table headers.
- Bulk generation for class or school batches.
- Preview before generation.
- Permission checks and audit logs for sensitive exports.

Documents and reports should include:

- Admission letters and offers.
- Student ID cards and staff ID cards.
- Class lists and student directories.
- Attendance registers and student attendance reports.
- Weekly/monthly attendance summaries.
- Timetables and examination schedules.
- Assessment mark sheets and result summaries.
- Individual report cards and bulk report-card packs.
- Academic transcripts and transfer/withdrawal letters.
- Fee invoices, student statements and receipts.
- Class collection, outstanding fee and reconciliation reports.
- Expense reports.
- Staff lists and authorised staff records.
- PTA invitations, circulars and announcements.
- Excursion consent forms.
- Certificates and awards.
- Meeting agendas/minutes and school calendar.

Export rules:

- CSV/XLSX exports should include clear headings, stable identifiers and consistent date/amount formats.
- Apply the same tenant and role permissions to exports as to on-screen data.
- Sensitive exports should be logged with actor, time, filters and record scope.
- Bulk report cards should be generated in one operation for selected students/class/term.
- Exports must respect selected filters and clearly state the reporting period.
- Do not expose confidential medical, financial or guardian data in general-purpose class exports.

### 36.18 School public website and subdomain

<b>Confirmed product direction:</b> Treat the school website as an optional add-on/activation, not a mandatory component of every subscription at launch.

Possible capabilities:

- Branded school landing page.
- School history, description and education levels.
- Location and contact details.
- Admissions information and enquiry form.
- News, announcements and approved gallery.
- School events and calendar highlights.
- Secure links to parent and staff portals.
- School-specific subdomain.
- Custom domain support as a separately scoped capability if commercially justified.

The public website must be separated from private school records and portals. Publishing content requires school-authorised approval.

### 36.19 Additional school operations and expansion modules

Include in the long-term architecture, but validate and phase before building:

- Transport routes, vehicles, drivers, assigned students and pickup information.
- Library catalogue, borrowing, returns and overdue records.
- Inventory, supplies, equipment and stock movement.
- Asset register and maintenance.
- Visitor register.
- Restricted school health/emergency records.
- Behaviour, conduct, incident and safeguarding records with strong permissions.
- Homework, assignment submissions and learning resources.
- Online examinations and computer-based testing.
- Substitute teacher scheduling.
- Staff leave management.
- Parent feedback and complaints.
- Multi-campus and group-school consolidated reporting.
- AI-assisted drafting, summarisation and data retrieval with human review.

AI must not autonomously make consequential decisions about student admissions, discipline, grading, promotion or safeguarding.

### 36.20 ACADIVA subscription administration

Keep ACADIVA's SaaS subscription separate from school-collected student fees.

School subscription area:

- Current plan and active-student count.
- Monthly/termly billing arrangement.
- Next renewal date.
- Subscription invoices and receipts.
- Payment history and status.
- Upgrade/downgrade information.
- Grace period and service notices.
- Optional add-ons such as school website, subject to final packaging.

Do not charge parents for access to their children's records. Keep subscription revenue, school fee collections and provider settlement records separate.

### 36.21 Shared platform services and technical requirements

Shared services:

- Identity and authentication.
- Role and permission service.
- School tenant context and isolation.
- Student/guardian relationship service.
- Notification and delivery log.
- Document/PDF generation.
- CSV/XLSX export.
- Audit log.
- Search.
- File storage and retention.
- Billing/payment ledger.
- Reporting and analytics.
- Import and migration.
- Backup and recovery.

Security and reliability:

- Every school-owned record carries tenant context.
- Enforce tenant isolation and permissions on the server/database, not only in UI.
- Use database row-level security where supported and test cross-tenant access.
- Parents see only verified linked children.
- Teachers see assigned classes and approved student information.
- Restrict finance, HR, medical and safeguarding information.
- Use secure authentication and account recovery; support phone and email verification.
- Do not store raw payment card data.
- Verify payment provider webhooks server-side and validate signatures.
- Make payment event processing idempotent.
- Keep immutable financial transaction history and append-only audit events for sensitive changes.
- Use encrypted transport, secure file access, backups and tested restoration.
- Use staging data that contains no live student personal information.
- Support data export and school offboarding under a documented retention/deletion policy.
- Maintain monitoring, incident response and operational alerts.

### 36.22 Reporting and analytics catalogue

School leaders:

- Enrolment by session, term, section and class.
- Admissions, transfers, withdrawals and graduation.
- Student and staff attendance.
- Academic performance by subject, class, section and term.
- Pass/fail and at-risk student summaries.
- Result submission and approval status.
- Staff workload and leave where enabled.

Finance:

- Fees billed, collected, outstanding and overdue.
- Collections by student, class, fee category, term, date and payment method.
- Partial payments and payment-plan status.
- Discounts, concessions, refunds and reversals.
- Provider fees and settlements.
- Reconciliation exceptions.
- Expenses by category and period.
- Income/expense summary.

Operations:

- Timetable and room usage.
- Event and calendar records.
- Communication delivery and acknowledgements.
- Document completeness.
- Admissions pipeline.
- Inventory/library/transport reports when those modules are enabled.

All reports must show date range, filters, data freshness and the meaning of each metric. Billed amounts, cash collected, provider settlement and outstanding balances must never be conflated.

### 36.23 Release priorities

<b>Foundation — required before module rollout</b>

- Tenant and school setup.
- Authentication, roles and permissions.
- Academic sessions, terms, classes and subjects.
- Authoritative student and guardian records.
- Staff records and teacher assignments.
- Audit foundation, document storage and import capability.

<b>Release 1 — core school operations</b>

- Admissions and enrolment.
- Teacher workspace and class lists.
- Daily attendance.
- Timetable.
- Assessment and marks.
- Configurable grading and result approval.
- PDF report cards and essential class/academic exports.

<b>Release 2 — parent and finance workflows</b>

- Parent portal and linked-child access.
- Approved results and attendance visibility.
- Fee structures, billing and statements.
- School-defined instalments and parent requests for approval.
- Payment-provider integration and verified bank-transfer workflow.
- Receipts and payment history.
- Attendance and school-notice notifications.
- Basic collections reporting and reconciliation.

<b>Release 3 — management and administration</b>

- Proprietor/principal dashboards.
- Bursar finance workspace and advanced reports.
- Discounts, refunds and adjustments.
- Expenses and approvals.
- Staff/HR administration.
- Document centre and bulk PDF/CSV/XLSX exports.
- PTA, events, excursions and consent workflows.
- Communication delivery reporting.

<b>Release 4 — expansion</b>

- Optional school website/subdomain.
- Advanced reconciliation and analytics.
- Multi-campus management.
- Transport, library, inventory and asset modules.
- Homework, learning resources and online assessments.
- Integrations and advanced AI assistance.

This is a proposed release sequence, not a promise that every listed feature will ship in a particular timeframe. Priorities should be validated with pilot schools and actual usage.

### 36.24 Confirmed product decisions from the 15 November 2026 review

| Area | Current decision |
| --- | --- |
| Payment instalments | School-defined plans plus flexible parent requests requiring school approval |
| Finance architecture | Direct settlement to the school's designated account through a suitable provider is the default target; ACADIVA records and reconciles |
| Academic grading | Standard Nigerian-school-oriented templates plus full school customisation |
| Attendance responsibility | Both class teachers and designated attendance officers can record attendance, according to school configuration |
| Result approval | School-configurable approval chain |
| Parent login | Both phone and email, with secure verification and account recovery |
| School website | Optional add-on/activation, not mandatory for every school at launch |
| Reporting/exports | PDF, CSV and XLSX are core capabilities |
| Parent payment experience | Multi-child view and combined checkout are required design goals, with separate correct allocation per child/bill |
| Finance history | No silent deletion or overwriting of successful transactions; adjustments/refunds remain traceable |

### 36.25 Open questions and validation requirements

These are intentionally unresolved; do not treat them as confirmed:

- Final payment provider and settlement product after technical, fee, legal and commercial review.
- Whether gateway fees are absorbed by the school, passed through transparently or handled by another agreed arrangement.
- Exact SMS provider, pricing, message allowance and notification defaults.
- Default Nigerian grading templates and any state/education-level-specific requirements to validate.
- Whether lesson-level attendance is enabled by default or optional per school.
- Exact approval thresholds for refunds, discounts, expenses and manual payments.
- Parent identity verification and custody/guardian dispute handling.
- Student account rules by age and school level.
- Website add-on packaging, domain costs and custom-domain support.
- Data retention, school offboarding and legal/privacy compliance requirements.
- Which advanced operations modules pilot schools are willing to pay for.
- Actual support, migration and onboarding scope for each subscription tier.

### 36.26 Product acceptance principles

A module is not ready merely because a screen exists. It must meet the following:

- The end-to-end workflow works for its intended roles.
- Permission and tenant-isolation tests pass.
- Records are accurate and recoverable.
- Errors, pending states and corrections are handled explicitly.
- Relevant reports and exports match the underlying records.
- Mobile and desktop workflows are usable for the intended user.
- Notifications reflect actual system events and show delivery status.
- Audit history exists for sensitive actions.
- The school can understand what is complete, pending, failed or awaiting approval.
- Pilot users can complete the workflow without relying on the ACADIVA founder to perform hidden manual steps.

---

## 46. ACADIVA as One Connected Product — Workspace Architecture, Shared Data, System Map and Build Sequence — 15 November 2026

### 46.1 Product architecture decision

ACADIVA is one connected product ecosystem delivered through the main ACADIVA website. It is not a collection of unrelated applications that happen to share a logo or database.

The product contains multiple protected workspaces, each designed around a user's role and responsibilities:

- Founder Master Control.
- CTO / ACADIVA Operations.
- Proprietor workspace.
- Principal and vice-principal workspace.
- School administrator / registrar workspace.
- Bursar / finance workspace.
- Teacher workspace.
- Parent / guardian portal.
- Public school website and admissions experience where enabled.

Each workspace has its own navigation, landing page, permitted actions and information density. A user should not see a confusing universal dashboard full of tools they do not need.

ACADIVA Operations is part of the main ACADIVA website and product architecture. It is a protected internal workspace with its own route group and permission boundary. It is not a disconnected second product. A distinct subdomain or deployment may be considered later if security or operational evidence justifies it, but it is not a prerequisite.

### 46.2 One system, connected workspaces

All workspaces must operate on the same authoritative records and agreed business rules. They are different views and controlled ways of interacting with the same school organisation data.

Examples:

- A student is admitted and enrolled once. The same student record is used by the registrar, class register, teacher mark sheet, bursar, principal, proprietor and linked parent portal according to permissions.
- A guardian is linked to the correct child/children once. The parent portal uses that relationship; it must not create a second copy of the student.
- A teacher is created once, assigned to the appropriate school and given approved class/subject assignments. The teacher workspace, timetable and principal's staffing view use those assignments.
- A timetable is maintained as the authoritative schedule. Changes flow to affected teacher and class views.
- A teacher submits attendance once. The authorised principal, proprietor, administrator and linked parent views reflect the saved record according to school policy.
- A teacher submits marks once. Review, approval and publication states control what appears in internal academic views and the parent portal.
- A verified payment updates the authoritative finance ledger and the relevant authorised summaries. An unverified entry must not appear as confirmed revenue.
- A principal sends one authoritative announcement. In-app delivery and any external email/SMS delivery attempts are tracked separately.

A dashboard is a role-specific view over authoritative data, not a separate editable database.

### 46.3 Identity, organisation, school and membership model

Before building individual screens, define the shared identity and organisation model.

At minimum, distinguish:

- <b>Person/account:</b> the authenticated human identity.
- <b>Internal ACADIVA membership:</b> the person's authorised employment/access relationship with ACADIVA, such as founder or CTO.
- <b>School organisation:</b> the customer organisation that owns/operates a school workspace.
- <b>School/campus:</b> a school site or branch under an organisation, if multi-campus is enabled.
- <b>School membership:</b> a person's relationship to a particular school.
- <b>Role assignment:</b> the role(s) a person is authorised to hold within that context.
- <b>Class/subject assignment:</b> the specific teaching responsibilities assigned to a teacher.
- <b>Guardian-child relationship:</b> the verified relationship that grants a parent/guardian access to a child's permitted information.

Internal ACADIVA authority and school authority are separate. A CTO may have authorised internal operational access across schools, but that does not turn the CTO into the proprietor, principal or teacher of those schools. A person may hold multiple roles only through explicit, auditable assignments.

Do not assume every person has one global role. A teacher may work at more than one school, a school employee may hold more than one approved role, and an internal ACADIVA employee may also have a separate school membership if explicitly authorised. Context switching must never silently merge those permissions.

### 46.4 Shared data model and authoritative records

Define canonical entities and relationships before implementing modules. The initial data model should cover, at minimum:

- ACADIVA internal accounts, employee memberships, founder/CTO permissions and privileged audit events.
- School organisations, schools/campuses, subscriptions and school configuration.
- School memberships, role assignments, invitations and account status.
- Sessions, terms, levels, classes, arms, subjects, rooms where needed and timetable entries.
- Staff/teacher profiles and teacher-class-subject assignments.
- Student profiles, applicant records, enrolments, class history and student status.
- Guardian profiles, verified guardian-child links and contact preferences.
- Admissions applications, submitted documents, review decisions and conversion into student records.
- Attendance registers, attendance entries, submission metadata and correction history.
- Assessment definitions, mark entries, grading rules, review decisions, published results and report-card/transcript versions.
- Fee structures, invoices, payment records, verification/reconciliation states, receipts and adjustments.
- Announcements, in-app notifications, channel delivery attempts and read/delivery states.
- Files/documents, access policies, exports, consent/retention metadata and audit records.

The same real-world entity must not be duplicated just because multiple roles need to view it. Use stable identifiers and explicit relationships. Define which module owns each record and which modules are allowed to read or update it.

### 46.5 Cross-workspace permissions and data visibility

Create a complete permission matrix before UI implementation. For each role, specify:

- Which school(s) and campus(es) the user can access.
- Which records the user can view, create, edit, submit, approve, publish, export or delete.
- Which actions require a second authorised person or school representative.
- Which information is hidden, masked or unavailable.
- Which actions require a reason and audit event.
- Whether access is temporary, delegated or permanent.

Apply least privilege. Parents see only linked children; teachers see only assigned classes/subjects and necessary student details; bursars access financial information required for their role; principals and proprietors have their respective authorised scopes; internal ACADIVA staff use scoped and audited operational access.

### 46.6 Workflow and state architecture

Map each important business workflow from its initiating action to its final state and downstream views.

For every workflow, define:

1. The authorised actor and starting context.
2. The authoritative record being created or changed.
3. Validation and business rules.
4. Whether the action is draft, submitted, approved, published or final.
5. Which role can review, reject, correct or reverse it.
6. Which other workspaces are updated after successful server commit.
7. Which notifications are triggered and under what policy.
8. The audit events and evidence retained.
9. Offline, retry, duplicate and conflict behaviour where relevant.

Do not make a saved draft look approved. Do not make a pending payment look verified. Do not publish results merely because marks have been entered. Do not update other users' confirmed views until the server accepts the authoritative change.

### 46.7 Shared design system and screen architecture

Design one coherent design system used by all workspaces. Role-specific screens may differ in layout and information density, but must share consistent components, language, interaction rules and visual identity.

The design process must include:

- Design research using established UI/UX inspiration sources and real product patterns.
- Information architecture and role-based navigation maps.
- Full screen inventory by workspace and workflow.
- User flows and low-fidelity wireframes before detailed visual design.
- Approved visual direction, tokens, typography, spacing, colour, gradients, glass surfaces, iconography, component states and responsive rules.
- Reusable components for tables, forms, registers, mark sheets, financial summaries, notices, dialogs, filters, import previews and status indicators.
- Loading, empty, error, offline, pending-sync, permission-denied and success states.
- Accessibility, contrast, keyboard use, mobile touch targets and readable data density.
- Light mode as the primary design direction and a deliberately designed dark mode.
- Responsive web layouts for management/admin and practical mobile-first workflows for teachers and parents.

Do not make every role's home screen a variation of one generic dashboard. Design around the real tasks of that role. Avoid clutter and avoid adding cards or metrics that do not support a decision or action.

### 46.8 Build order — foundations before feature screens

The recommended construction sequence is:

<b>Stage 1 — Product definition and system mapping</b>

- Confirm initial-release scope and what is explicitly excluded/deferred.
- Map all roles, workspaces, navigation and end-to-end journeys.
- Create the role-permission matrix and tenant/organisation model.
- Define the canonical data model and authoritative record ownership.
- Define workflow states, cross-workspace update rules and audit requirements.

<b>Stage 2 — Design and technical foundations</b>

- For every first-release feature, complete and record reference research from Mobbin, Dribbble, Behance, Awwwards, Refero and Design Spells; document relevant references and any source with no applicable example.
- Complete information architecture, screen inventory, workflow maps and wireframes.
- Create original ACADIVA screen designs and interaction-state specifications; complete design review and approval before implementing each feature. A general design-system approval does not waive the feature-level reference and screen approval gate.
- Approve the shared design system and responsive component library, keeping brand tokens configurable until the founder approves the identity.
- Establish codebase structure, environments, database migrations, testing and deployment workflow.
- Establish identity, authentication, school tenancy, memberships, role assignments, permissions and audit foundation.
- Exit evidence: approved design research register, screen inventory, responsive designs, component mapping, interaction-state coverage and implementation-ready handoff for the first vertical slice.

<b>Stage 3 — School and people foundation</b>

- Build school setup and configuration.
- Build staff, teacher, student, applicant and guardian records.
- Build admissions, guardian linking, class/subject configuration and teacher assignment.
- Build timetable and school calendar essentials.

<b>Stage 4 — Core daily school workflows</b>

- Build attendance.
- Build assessment mark entry, validation, review, approval and publication.
- Build report cards and Student Record Passport outputs.
- Build fees, invoices, payment recording, verification and receipts.
- Build the parent/guardian portal and in-app announcements.

<b>Stage 5 — Internal ACADIVA Operations</b>

- Build Founder Master Control and CTO approval/security.
- Build school directory, school switcher and school approval/activation.
- Build centralised onboarding and bulk imports.
- Build controlled delegated assistance, privileged audit and emergency revocation.
- Integrate internal operations with the same authoritative school records and permissions foundation.

<b>Stage 6 — Integration, reliability and pilot</b>

- Complete notifications and required external integrations.
- Test role-specific end-to-end journeys and cross-workspace data consistency.
- Test tenant isolation, security, audit, backups, recovery, import retry and synchronisation.
- Pilot with real schools, observe actual workflows and remove friction before adding optional modules.

The exact implementation order may be adjusted where a dependency requires it, but do not start by building isolated dashboards or decorative screens before the underlying identities, records, permissions and workflows are defined.

### 46.9 Requirement-to-implementation traceability

Every feature must have a traceable chain:

<b>Problem → user/role → workflow → screen → data entity → permission → backend operation → integration/event → test → acceptance evidence.</b>

A feature is not ready for development until its user, purpose, scope, data source, authority, dependencies and acceptance criteria are understood. A feature is not complete when its screen merely looks finished; it must work end to end and update all authorised connected workspaces correctly.

Maintain a single requirement register with unique IDs and statuses. Link the master blueprint, checklist, screen inventory, database schema, API/backend specification, test cases and implementation issues to those IDs. This prevents the design, code and documentation from drifting apart.

### 46.10 Decisions and items still to validate

- The exact route structure and whether a future subdomain is justified for ACADIVA Operations.
- The final organisation-versus-school-versus-campus hierarchy for customers with multiple branches.
- Whether one person can hold memberships in multiple school organisations in the first release or whether this is deferred.
- Final authentication provider and account-linking rules.
- Final data schema and backend service boundaries after technical review.
- The precise first pilot school workflows and which configurable options are genuinely needed.
- Which screens require a native mobile app later versus responsive web being sufficient.

### 46.11 Master checklist connection

Section 40 now includes <b>Section AA — Connected system architecture, workspace integration and build order</b>, with 26 checklist items covering the shared product model, roles, data relationships, permissions, workflows, design system, screen inventory, integrations, implementation sequence and end-to-end validation.

Section 46 is the architecture and build-sequence decision record. Section 40AA is the execution checklist. Section 45 defines the internal operations workspace and CTO governance. Section 40Z is its implementation checklist.

---

## Section 56 — ACADIVA Connected System Architecture, Shared Data Model, Integration Map and Implementation Blueprint

<b>Purpose:</b> Convert the agreed product direction into an implementation-ready architecture. This section explains how workspaces and modules share data, which records are authoritative, how permissions and school separation work, what depends on what, and the order in which to build and test. This is a planning baseline, not evidence that software has been implemented.

<b>Related sections:</b> Read with Sections 36, 39, 40, 42–49 and 53–55. Section 56 connects those requirements technically; it does not silently approve open vendor, pricing, legal or policy decisions.

### 56.1 Reconciliation rules for older and newer requirements

The blueprint has grown through discovery, so older sections may describe proposals later narrowed or deferred. Apply this precedence:

1. A later, explicitly confirmed user decision takes precedence over an earlier proposal.
2. A later specialised decision section takes precedence within its subject.
3. Sections 36 and 42 are consolidated product references; Sections 39 and 40 are architecture/checklist references.
4. Sections 45–55 and this Section 56 add later governance, workflow and technical detail.
5. Older ideas remain historical context, not automatic launch requirements.

Known conflicts to reconcile:

- <b>Finance scope:</b> older broad descriptions mention expenses, payroll and salary processing. Current launch scope is school fees, billing, payment recording, receipts, balances and reconciliation. Teacher salary/payroll is deferred.
- <b>Two separate financial systems:</b> school-fee collection and ACADIVA subscription billing have separate invoices, transactions and ledgers. A parent payment must never settle a school's ACADIVA subscription; a school's ACADIVA subscription payment must never create a student fee payment.
- <b>Parent identity:</b> one guardian account can link to multiple verified children, including children in different classes. Do not create one parent login per child. Student accounts are optional and restricted by age/policy.
- <b>Onboarding:</b> both school-led bulk onboarding and parent-submitted applications/registration are supported. An application is not automatically an enrolled student; admission approval and placement govern conversion.
- <b>Results:</b> complete subject outcomes are required before publication. Teachers can publish their own complete subject results without routine principal approval. Post-publication corrections are controlled and audited.
- <b>Attendance:</b> teachers record attendance; corrections are not casual edits. Genuine corrections require an authorised, traceable exception process.
- <b>Roles:</b> ACADIVA Platform Administrator is distinct from a school's School Administrator. Central Operations is at [operations.acadiva.ng](http://operations.acadiva.ng); school configuration belongs to the tenant workspace.
- <b>Deferred scope:</b> CBT, payroll, advanced private messaging and extended ERP modules must not delay the core launch.
- <b>Pricing:</b> latest working direction is \$1 per active student per term, invoiced to the school in one bulk invoice. Local currency conversion, tax and final terms remain to be validated. Older pricing drafts are not binding.
- <b>Technology:</b> Supabase/PostgreSQL, Netlify, Expo/React Native and PostHog are candidate directions, not proof of final approval. Recheck current repository state, provider terms, costs, limits and security before implementation.

If a conflict cannot be resolved by these rules, record an open decision and stop the affected implementation rather than guessing.

### 56.2 One product, distinct workspaces, shared authoritative records

ACADIVA should behave as one connected product. Workspaces are role-aware experiences over shared authoritative records, not isolated databases that copy data between themselves.

| Workspace / surface | Main users | Responsibilities | Connected records |
| --- | --- | --- | --- |
| [acadiva.ng](http://acadiva.ng) | Public visitors, schools, parents and staff | Product information, school registration, common login entry | Tenant, application, identity and routing |
| [operations.acadiva.ng](http://operations.acadiva.ng) | ACADIVA central Operations | School verification, tenant lifecycle, subscription, support and platform health | Tenant, verification, subscription, support and audit |
| School public website | Public visitors and prospective families | School identity, pages, gallery, achievements, admissions and published notices | Published school profile/content |
| School management workspace | Proprietor, School Administrator, Principal, Registrar, Bursar and teachers | Administration, academics, student records, fees and communication | Tenant-scoped school records |
| Parent workspace | Verified guardians | Linked children, results, attendance, fees, receipts and notices | Guardian relationship, student, academic, finance and notification records |
| Student workspace (optional) | Eligible students | Own permitted timetable, results and school information | Student identity and explicitly permitted records |

A person may have different roles in different schools. Permission checks must use the active tenant and the user's membership or verified relationship in that tenant, not merely the global account.

### 56.3 Connected system map and dependencies

- <b>Identity and access</b> is the entry point for protected workspaces. It connects global identity to school membership, staff roles, guardian relationships and optional student accounts.
- <b>Tenant and school configuration</b> is foundational. It owns school identity, subdomain, branding, academic calendar, classes, subjects, grading policy, fee configuration, notification preferences and website settings.
- <b>Admissions and student lifecycle:</b> public application or school bulk import → validation → duplicate review → application/student record → admission decision → class placement → guardian relationship → active enrolment. Accepted applicant data is reused, not retyped.
- <b>Academic structure</b> defines session, term, classes, arms, subjects and assignments. It drives class registers, teacher dashboards, attendance, timetables, score entry and report cards.
- <b>Attendance</b> uses the official class register and records outcomes against a student, class, date and school. It feeds teacher views, parent alerts, attendance summaries and report-card totals.
- <b>Assessment and results</b> use official enrolment and school grading policy. Score entry → completeness checks → subject publication → report-card aggregation → parent/student visibility.
- <b>Finance</b> uses student enrolment, fee schedules, invoices and payment allocations. Invoice → payment attempt/manual record → server verification/reconciliation → ledger allocation → student balance → parent/bursar/principal views and receipt.
- <b>Timetable</b> uses classes, subjects, staff assignments, rooms, periods and teacher availability. A validated timetable feeds teacher/class/parent/student views and schedule notifications.
- <b>Communication</b> consumes events from other modules: attendance alert, result published, fee due, payment confirmed, timetable changed or school announcement → audience resolution → channel delivery → delivery history.
- <b>Documents and school website</b> consume approved school identity and published content. Branding feeds public pages and future documents; private student/finance data never flows to public pages.
- <b>Operations and subscription</b> govern tenant lifecycle. Subscription state controls defined access and renewal operations; it does not become the source of academic or school-fee truth.

### 56.4 Proposed authoritative data model

Use a relational model with explicit identifiers and relationships. Exact SQL types, indexes, constraints and table names must be finalised only after inspecting the current repository and database.

| Domain | Core entities | Relationship / invariant |
| --- | --- | --- |
| Platform | schools/tenants, school\_domains, tenant\_status, school\_verifications | One tenant owns its school data; domain unique; lifecycle audited |
| Identity | user\_accounts, sessions, school\_memberships, role\_definitions, permissions, membership\_roles | One global identity may have multiple tenant memberships |
| Guardians | guardian\_profiles, student\_guardian\_links, guardian\_verification\_events | Many-to-many; relationship, verification state, authority and timestamps recorded |
| Students | student\_profiles, student\_identifiers, student\_status\_history, student\_documents | One authoritative profile per school identity; identifiers unique in defined scope |
| Admissions | admission\_applications, application\_documents, admission\_decisions, application\_events | Application converts once; preserve source application and decision history |
| Academic setup | academic\_sessions, academic\_terms, education\_levels, classes, class\_arms, subjects, class\_subjects | Tenant-scoped; historical structures disabled/archived, not destructively deleted |
| Enrolment | student\_enrolments, class\_placements, promotion\_events, transfers | Time-bounded placements preserve previous sessions and classes |
| Staff/teaching | staff\_profiles, teacher\_assignments, staff\_subject\_assignments | Assignments connect staff, class/arm, subject and effective dates |
| Attendance | attendance\_sessions, attendance\_records, attendance\_correction\_requests | Defined register uniqueness; correction is audited |
| Assessment | grading\_policies, grade\_bands, assessment\_components, assessments, score\_records, result\_publications, result\_amendments | Scores reference correct assessment and student enrolment |
| Reports | report\_card\_snapshots, report\_card\_items, issued\_documents | Issued output preserves the policy/branding/data version used |
| Timetable | school\_periods, rooms, timetable\_versions, timetable\_slots, teacher\_availability | Hard conflicts are enforced; published versions retained |
| Finance | fee\_schedules, fee\_items, student\_invoices, payment\_transactions, payment\_allocations, receipts, reconciliation\_records | Ledger authoritative; transactions distinct from allocations |
| Communication | announcements, audience\_rules, notification\_jobs, notification\_recipients, delivery\_attempts, notification\_preferences | Resolve audience at send time; deduplicate guardians |
| Website/content | website\_themes, website\_pages, media\_assets, gallery\_items, achievements, published\_announcements | Public content explicitly published; private records excluded |
| Operations | platform\_subscriptions, subscription\_invoices, subscription\_payments, support\_tickets, operational\_actions, audit\_logs | Separate ACADIVA commercial ledger |
| System | idempotency\_keys, background\_jobs, webhook\_events, import\_batches, import\_row\_errors, data\_export\_jobs | Retries safe; imports/webhooks traceable; exports permission-checked |

<b>Non-negotiable modelling rules:</b>

- Every tenant-owned row must carry or inherit an enforceable tenant boundary. Never rely on a UI filter or a user-supplied school ID.
- Use immutable internal IDs. Admission numbers, phone numbers, email addresses and subdomains are attributes, not primary keys.
- Normalise phone numbers where possible; do not assume one phone number uniquely identifies one guardian or one child.
- A parent phone number is a contact/matching input, not proof of guardianship and never a password.
- Separate global identity, tenant membership and guardian-to-student relationship.
- Separate student profile, enrolment, class placement and academic history. A class change must not overwrite history.
- Use effective dates/session references for class, subject, staff and policy assignments.
- Separate payment transactions from allocations. Pending/failed attempts do not increase paid balances.
- Preserve provider webhook events and idempotency keys so duplicate callbacks cannot duplicate payments or messages.
- Keep published result snapshots and issued documents reproducible. Later policy/logo changes must not rewrite issued report cards or receipts.
- Prefer archive/disable/withdrawn states over hard deletion where records depend on an entity.
- Define retention and deletion rules with legal review, especially for children's records.

### 56.5 Tenant isolation and permission enforcement

Security must be enforced at multiple layers:

1. Authenticate the global user.
2. Resolve the requested tenant from trusted hostname/server-side routing.
3. Confirm active membership or verified guardian/student relationship in that tenant.
4. Resolve effective permissions for the requested action and record.
5. Enforce tenant scope and row-level policies in the database.
6. Validate the operation again server-side before writing.
7. Record sensitive actions in the audit log.

Minimum boundaries:

- A school member cannot access another school's records by changing a URL, request body, identifier or API parameter.
- A parent sees only students connected through verified, active guardian relationships and only permitted fields.
- Access to one child must not reveal another child's profile, class list or financial records.
- Teachers see only assigned classes/subjects and authorised student fields.
- Bursars manage finance but cannot edit scores or publish results.
- Teachers cannot change core biodata, grading policy, fee schedules or another teacher's assignments without explicit delegated permission.
- Central Operations access is least-privilege and purpose-limited. Support access to school records must be authorised, reasoned and audited.
- Privileged accounts should use strong authentication and MFA where supported.
- Service-role credentials and provider secrets remain server-side, never in web/mobile bundles.
- Public routes expose only deliberately published content.
- Exports, PDFs, search, notifications, background jobs and webhooks enforce the same tenant and permission checks as screens.

### 56.6 Cross-module event and data-flow contracts

Modules communicate through documented application services/events, not by allowing one screen to manipulate another module's tables directly.

| Trigger | Authoritative operation | Downstream effects | Safety requirement |
| --- | --- | --- | --- |
| School approved | Operations changes tenant lifecycle | School workspace and setup checklist become available | Authorised actor and audit reason |
| Branding updated | New tenant branding version saved | Website theme and future document templates update | Preview; issued documents unchanged |
| Applicant submitted | Application saved | Registrar queue and acknowledgement | Validation, spam/rate protection and duplicate review |
| Applicant accepted | Admission decision recorded | Reuse data for student, enrolment and guardian link | Idempotent conversion |
| Student placed | Enrolment/class placement saved | Register, teacher roster, subject mapping, timetable and billing eligibility | Validate class/session and preserve history |
| Guardian verified | Guardian-student link activated | Parent dashboard gains permitted child | Verification event; revocation supported |
| Teacher assignment changed | Assignment version saved | Teacher dashboard, score/attendance access and timetable validation | Effective dates; revoke stale access |
| Attendance submitted | Attendance records committed | Summaries and eligible parent alerts | Unique constraints; offline recovery |
| Grading policy changed | New policy version saved | Future assessments use correct policy | Do not silently recalculate published results |
| Subject results published | Completeness passes and publication recorded | Parent/student result view, report card and notification | Atomic publication and audit |
| Result amended | Authorised amendment saved | Corrected result and downstream report state update | Reason required; retain prior value |
| Invoice issued | Student invoice saved | Parent balance, bursar ledger and reminders | Correct student/session/term |
| Payment confirmed | Server verifies evidence and posts transaction | Allocation, balance, receipt and finance dashboards | Idempotency and reconciliation |
| Timetable published | Conflict-free version marked published | Relevant workspace views update | Versioned publication |
| Announcement scheduled | Audience rule saved and recipients resolved | Notification jobs queued | Consent/preferences, deduplication and rate limits |
| Subscription expires | Operations lifecycle changes | Renewal notices and defined restrictions | Preserve records and export path |
| School exits | Authorised closure workflow begins | Export, retention and access-closure tasks | Verify authority and legal retention |

<b>Consistency principle:</b> the database commit is the source of truth. A dashboard, toast, payment redirect or notification must not claim success before the authoritative operation succeeds. If downstream delivery fails, preserve the committed record and retry safely.

### 56.7 Screen and workflow architecture

Design screens around user tasks and permissions, not database tables. Every important screen needs loading, empty, success, validation-error, permission-denied, offline/retry and partial-failure states where applicable.

<b>Public and central entry</b>

- ACADIVA home and product information.
- School registration form and submission confirmation.
- School public website and distinct login entry.
- Common login/OTP recovery and tenant resolution.
- Operations dashboard: verification queue, tenant status, subscription, support and platform health.

<b>School setup</b>

- Setup progress with save-and-resume.
- School identity/branding editor and preview.
- Academic calendar/session/term setup.
- Education levels, classes, arms and subjects.
- Grading and assessment configuration.
- Staff invitations and permission review.
- Student import with validation preview, duplicate resolution and rejected-row report.
- Guardian matching and activation status.
- Final readiness checklist.

<b>School leadership</b>

- Proprietor overview: enrolment, attendance, academic progress and fee summaries.
- Principal dashboard: academic completion, attendance exceptions, admissions and staff tasks.
- Registrar admissions pipeline and student records.
- School Administrator configuration.
- Bursar fee setup, invoices, payment recording, receipts and reconciliation.

<b>Teacher</b>

- Assigned classes and subjects.
- Class register and whole-class attendance.
- Score entry with draft/autosave state, validation and automatic calculation.
- Completeness checklist and subject-result publication.
- Assigned timetable and permitted student information.

<b>Parent/guardian</b>

- One account and child switcher for multiple verified children.
- Child overview with current class/session.
- Results/report cards.
- Attendance and absence alerts.
- Fees, paid/outstanding/partial status, transactions and receipts.
- Announcements and support/contact path.

<b>Student (optional/later)</b>

- Own permitted timetable, results and notices only.
- Age-appropriate access; no guardian financial details unless explicitly permitted by policy and law.

### 56.8 Technical architecture boundaries and candidate stack

These are candidate directions from prior planning and must be checked against the current repository, usage, provider terms and budget before implementation:

- <b>Database:</b> PostgreSQL as relational source of truth.
- <b>Authentication/data:</b> Supabase Auth/Postgres/RLS are candidates. RLS must be designed and tested per tenant/role; server-side checks remain mandatory.
- <b>Backend operations:</b> trusted server-side functions/services for privileged actions, payment verification, webhooks, imports, exports, notifications and tenant lifecycle.
- <b>Web hosting:</b> Netlify is a candidate, subject to routing, server execution, security headers and workload needs.
- <b>Mobile:</b> Expo/React Native is a candidate. Reuse business rules/API contracts; do not duplicate sensitive logic in clients.
- <b>Analytics:</b> PostHog is a candidate. Never send student names, phone numbers, results, financial details or sensitive child data as analytics properties.
- <b>Email:</b> Resend is a candidate subject to domain verification, deliverability and cost review.
- <b>SMS/WhatsApp/push:</b> provider selection remains open. Use an adapter so provider changes do not require rewriting school workflows.
- <b>Payments:</b> gateway integration remains separate from the internal ledger; verify server-side and reconcile.
- <b>Monitoring/backups:</b> select an affordable approach and test restoration rather than assuming backups work.

Do not introduce microservices, Kubernetes, Redis or paid infrastructure solely to appear scalable. Start with a modular, well-indexed application and add infrastructure only when measured workload justifies it.

### 56.9 Integration adapter and secrets policy

Each external provider sits behind an internal adapter. Product modules call an internal capability such as send message, verify payment or store media, not scattered provider-specific code.

Every integration record must state purpose/owner, provider/environment, credential names and secure storage location, callback endpoints and signature verification, data shared and legal basis, rate limits/quotas/pricing, retry/idempotency/reconciliation, monitoring/fallback and exit plan.

Never store credential values in source control, mobile bundles, public environment variables, screenshots or Notion. Notion may document secret names and storage locations, never secret values.

### 56.10 Reliability, offline behaviour and scaling

- Paginate growing lists and filter large datasets server-side.
- Index based on measured query patterns, especially tenant, student, session, term, class, date and transaction references.
- Do not load an entire school register or all historical results when one class/term is required.
- Use background jobs where appropriate for notifications, imports, exports, document generation and reconciliation.
- Use idempotency keys and unique constraints for payment callbacks, admission conversion, imports and repeated submissions.
- Store offline drafts only where safe; show whether data is local, queued or server-confirmed.
- Resolve offline conflicts explicitly; never silently overwrite newer server data with stale device data.
- Retry safely; retries must not duplicate payments, attendance records or messages.
- Optimise images and defer nonessential animation/media on low-bandwidth devices.
- A target such as 1,000 concurrent users is a test objective, not a guarantee from a proposed stack or free plan.
- Define performance budgets for login, dashboards, class registers, score entry, parent results and payment confirmation.
- Load-test representative datasets and concurrent activity before claiming scale; record bottlenecks and infrastructure costs.

### 56.11 Privacy, child safety and audit

Before pilot, complete a Nigeria-focused legal/privacy review, including the Nigeria Data Protection Act 2023, children's personal data, school controller/processor responsibilities, guardian verification, notices, consent where required, retention, data-subject requests, breach response and school contracts.

Minimum controls:

- Collect only data necessary for a stated school purpose.
- Explain what is collected, why, who can see it and retention periods.
- Restrict photographs, documents and sensitive notes to authorised users.
- Do not use student data for advertising or unrelated profiling.
- Never expose student lists, results, attendance or finance on public school websites.
- Log sensitive writes and privileged actions; log sensitive reads/exports where justified.
- Support account deactivation, guardian-link revocation, staff offboarding and session revocation.
- Define retention/deletion schedules before production; do not promise deletion where legal retention applies.
- Prepare an incident-response and breach-escalation process.

### 56.12 Build sequence and dependency gates

Build vertical slices: each stage should deliver a working end-to-end workflow. Do not build disconnected screens and connect them at the end.

| Stage | Build focus | Prerequisite | Exit evidence |
| --- | --- | --- | --- |
| 0 | Audit current repository, deployment, database, auth, domains, secrets and costs | Project access and current checklist | Inventory, baseline tests, threat/dependency review and rollback plan |
| 1 | Tenant resolution, identity, memberships, roles, permissions and audit foundation | Stage 0 approval | Cross-tenant and role-isolation tests pass |
| 2 | School registration, Operations verification, activation and secure owner invitation | Stage 1 | School safely registered, reviewed, activated and resumable |
| 3 | Branding, subdomain, academic calendar, classes, subjects and grading setup | Stage 2 | Setup checklist and non-destructive configuration tests pass |
| 4 | Admissions, bulk import, student profiles, enrolment, guardian matching and activation | Stages 1–3 | Conversion, retry, duplicate and guardian-access tests pass |
| 5 | Staff invitations, teaching assignments and permission boundaries | Stages 1–3 | Assigned-only access and reassignment revocation pass |
| 6 | Attendance, correction workflow and timetable constraints/publication | Stages 4–5 | Offline recovery, parent alerts and conflict tests pass |
| 7 | Assessments, score entry, completeness, publication, amendments and report cards | Stages 3–5 | End-to-end results and historical document reproducibility pass |
| 8 | Fee schedules, invoices, manual recording, ledger, receipts and reconciliation | Student/enrolment foundation | Balances reconcile; duplicate/failed payments do not corrupt ledger |
| 9 | Parent experience, announcements, notifications and preferences | Stages 4, 6, 7 and 8 | Guardian isolation, deduplication and delivery-failure tests pass |
| 10 | School website templates, publishing workflow, media and document engine | Stages 2–4 and document identity rules | Public/private separation and mobile website checks pass |
| 11 | Pilot hardening: security, load, backups, restore, support and onboarding | Launch-critical stages | Pilot evidence, issue closure, restore test and release approval |
| Later | CBT, payroll, advanced messaging, extended ERP and advanced analytics | Stable core and validated demand | Separate business case and release approval |

Parallel work is permitted only where interfaces and ownership are defined and integration tests exist. A stage is not complete because screens render; exit evidence must pass.

### 56.13 Minimum end-to-end acceptance scenarios

1. A school registers, Operations verifies it, an authorised owner activates access, and the correct subdomain opens the correct tenant.
2. A school disables classes it does not offer; historical records remain intact.
3. A parent submits an application; the registrar reviews it; acceptance converts it without duplicate biodata and places the student correctly.
4. A bulk import is retried after timeout; it creates no duplicate students or guardian links.
5. A parent with children in different classes sees all and only verified children under one account.
6. A teacher cannot access another class, school or student through a guessed identifier.
7. Whole-class attendance survives interrupted connectivity without silent loss or duplicate records.
8. Subject publication is blocked by unexplained blanks; approved explicit statuses follow school policy.
9. Published results appear only to authorised viewers; amendments preserve old values and reasons.
10. Timetable cannot double-book a teacher, class or room; unsatisfied constraints are shown.
11. A payment redirect says success but provider verification fails; ledger remains unpaid and reconciliation case is visible.
12. Duplicate valid payment webhooks create only one transaction/allocation.
13. Payment maps to the correct school, student, invoice and term; parent, bursar and principal balances agree.
14. Overlapping announcement audiences do not send duplicate messages to the same guardian.
15. Branding changes affect future documents but do not rewrite issued documents.
16. Subscription expiry applies defined restrictions without deleting records and preserves an export path.
17. Central support access outside an authorised grant is denied and auditable.
18. A backup is restored in a test environment and data integrity and tenant isolation are verified.

### 56.14 Required engineering artefacts before implementation

Before Stage 1 coding, prepare and review:

- Current repository/deployment inventory.
- System context and trust-boundary diagram.
- Entity-relationship diagram and data dictionary.
- Action-level role/permission matrix.
- Tenant-isolation and threat model.
- API/service contracts and event catalogue.
- Screen map and role-based navigation map.
- Migration, seed, rollback and recovery plan.
- Unit, integration, end-to-end, security, accessibility, mobile, offline and load-test strategy.
- Provider/integration register with cost and data-sharing review.
- Privacy/child-data review checklist.
- Release checklist, monitoring plan and operational runbooks.

Do not generate a production schema from the conceptual entity list without first auditing the repository and current database. If existing data/code exists, map it and plan safe migrations.

### 56.15 Open decisions and implementation blockers

Resolve at the relevant stage; do not guess:

- Current repository, database and deployment state; identify existing ACADIVA code/data to preserve.
- Final authentication/OTP provider and account recovery.
- School verification evidence, review authority and appeal process.
- Default permission matrix and authority for sensitive corrections.
- Admission form fields, required documents and custom fields.
- Duplicate student matching and human resolution of ambiguous matches.
- Grading models, rounding, absent/exempt treatment and promotion policy.
- Attendance correction authority, time window and locking policy.
- Position/ranking policy and whether schools may disable ranking.
- Fee discounts, waivers, refunds, credit notes and invoice rules.
- Payment provider/product, charges, settlement, webhooks and reconciliation.
- Subscription currency, local conversion, tax, grace period and suspension rules.
- SMS/email/WhatsApp/push providers, consent and opt-out.
- Hosting, storage, backup, monitoring and domain topology.
- Legal review and school contracts.
- Measured performance targets and infrastructure upgrade triggers.

### 56.16 Mandatory working method for every future action

This reinforces Section 55.11. Before every tool call or consequential build action:

1. Re-open the current master blueprint and relevant module checklist.
2. Confirm the current decision and identify newer/conflicting sections.
3. Inspect the current implementation/state before changing it.
4. Map affected workspaces, roles, records, events, integrations and downstream screens.
5. Define the smallest change, dependencies, acceptance tests, risks and rollback plan.
6. Make only the authorised change.
7. Test the full connected workflow and relevant negative/security cases.
8. Record what changed, test evidence, unresolved issues and next safe step.
9. Update the blueprint/checklist only after the result is known.

If the plan, repository state or required access cannot be inspected, stop and resolve that gap first. Never claim implementation, integration, security or reliability without evidence.

<b>Final architecture principle:</b> ACADIVA is one connected, tenant-isolated system with role-specific workspaces and one authoritative record for each business fact. Changes flow to authorised dependent modules through validated services/events while preserving privacy, history, auditability and recovery. Build and test connections as part of each vertical slice, not as a final integration phase.
