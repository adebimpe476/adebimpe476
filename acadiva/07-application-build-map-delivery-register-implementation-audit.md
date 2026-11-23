<!-- Source: https://app.notion.com/p/41c9a9b48b7a814db204d631c1a7df64?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🛠️ 07 — ACADIVA Application Build Map, Delivery Register & Implementation Audit

This is the operational build map for the ACADIVA application. It connects the product vision and requirements to the actual software being implemented.

The builder must use this page to answer:

- What parts of ACADIVA are we yet to build?
- What remains in the app specifically?
- What is implemented, partially implemented, untested, accepted, blocked or deferred?
- What should be built next, and why?
- Which requirements, screens, roles, APIs, data entities and other surfaces will a change affect?
- Does the running application match the approved product intent?

This is not a second product vision document. It is the bridge between product intent and implementation evidence.

## 1. Source-of-truth hierarchy

Before proposing or implementing work, consult these documents in order:

1. <b>Section 60 — Broad Product Operating Model:</b> what ACADIVA is and how the whole ecosystem operates.
2. <b>Section 36 — Master Product Requirements:</b> what the product must do.
3. <b>Section 46 — Product Architecture and System Map:</b> how product surfaces and systems relate.
4. <b>Section 56 — System Architecture and Implementation Blueprint:</b> how the software should be engineered.
5. <b>Section 40 — Master Execution Checklist:</b> what must be checked and accepted.
6. <b>This document — Application Build Map and Delivery Register:</b> what is actually built, what remains, and what evidence supports the status.
7. Relevant specialist manuals and approved decision records.

If these sources conflict, do not silently choose one. Record the conflict, identify the decision owner, explain the consequences and request or make an explicit documented decision within the authority already granted. Preserve the previous rationale.

## 2. Critical distinction: planned, built and accepted

Every feature must have exactly one current delivery status:

| Status | Meaning | Evidence required |
| --- | --- | --- |
| Not started | No implementation has begun | Confirmed scope and dependency review |
| In progress | Work is actively being implemented | Branch/commit, working notes or preview |
| Implemented — untested | Code or UI exists, but the workflow has not passed tests | Commit/build/preview reference |
| Testing / fixes required | Tests have exposed issues or acceptance is incomplete | Test cases and defect list |
| Tested and accepted | End-to-end behaviour meets acceptance criteria | Test evidence, environment, date and reviewer |
| Blocked | Work cannot proceed because of a named dependency, decision or defect | Blocker, impact and next action |
| Deferred / out of release | Intentionally excluded from the current release | Rationale and target phase/review trigger |
| Needs rework | Existing implementation materially fails requirements or architecture | Gap description and affected evidence |

Do not use “done”, “complete”, “built” or a checked box as a substitute for tested acceptance. A screen rendering is not proof that its data, permissions, save behaviour, error states or downstream workflows work.

<b>Initial status rule:</b> Existing implementation status has not been established by this document. Until the repository, deployed application and tests are audited, items must be labelled <b>Not yet audited</b> in the working tracker. Do not falsely classify them as not built or completed.

## 3. Application surfaces — the app is a complete product, not just a dashboard

ACADIVA must be treated as a connected ecosystem of application surfaces. Some may share one Next.js application, deployment, database or design system, but they remain distinct product experiences with their own access rules and acceptance criteria.

### 3.1 Public ACADIVA website

- Main product/marketing website and product information.
- School discovery, enquiry, demo request and onboarding entry points where approved.
- Public pricing and plan information only when commercially approved.
- Contact, support, legal, privacy and trust information.
- Clear transition from public pages into authenticated experiences.

### 3.2 School public websites and school subdomains

- Each participating school can have a branded public-facing website or portal.
- School identity, branding, contact details, approved announcements, calendar and public information.
- School-specific routes/subdomains, safe slug reservation and custom-domain capability only when supported.
- Public content must be separated from private student, guardian, finance and staff data.
- School website publishing and content permissions must be controlled by school roles.

### 3.3 Authenticated school application

- School-specific tenant context.
- Authentication, invitations, membership, role selection and secure account recovery.
- Role-based navigation and dashboards.
- Student, staff, guardian, academic, attendance, assessment, finance and communication workflows.
- School settings, session/term setup, imports, exports and audit history.
- Mobile-first responsive behaviour across supported devices.

### 3.4 Role-specific workspaces

These are different experiences over shared underlying records, not unrelated apps and not merely one dashboard with different labels:

- Proprietor / owner.
- Principal and vice-principal.
- School administrator / secretary.
- Registrar / admissions.
- Bursar / accountant / finance.
- Teacher.
- Parent / guardian.
- Student, if enabled for a release.
- School ICT administrator / setup operator, with narrowly scoped permissions.

One person may hold multiple explicitly granted roles. The interface, API and database must all enforce the effective permissions. Hiding a button is not authorisation.

### 3.5 ACADIVA internal Founder Master Control and CTO / Operations

This is the internal ACADIVA company control plane, not the school administrator dashboard.

- Manage schools, tenants, subscriptions/entitlements and platform-level configuration.
- Monitor onboarding, usage, system health, support cases and operational exceptions.
- Manage platform-wide feature flags and controlled rollouts.
- Review audit/security events and integration health.
- Support approved school-level assistance without casually exposing private records.
- Provide internal staff access, MFA, least privilege and audit trails.
- Clearly separate founder/CTO operational powers from school-owned academic and financial authority.

### 3.6 Shared infrastructure and cross-surface services

- Identity and session management.
- Tenant resolution and tenant-scoped authorisation.
- Shared database and data access layer.
- File/media storage and access control.
- Notifications and communication delivery.
- Payment gateway and financial event processing.
- Email/SMS providers.
- Audit logging and operational monitoring.
- Analytics and reporting.
- Domain, DNS, routing and deployment configuration.
- Backups, recovery, retention and data export.

A shared service change must trigger impact analysis across every dependent surface.

## 4. Application architecture and implementation boundaries

### 4.1 Primary application framework

Next.js with React is the primary application framework for the web product. It owns application routing, server/client rendering decisions, layouts, server-side operations, API integration and the main web experience.

### 4.2 Creative and interactive technology

Three.js / React Three Fiber, GSAP, Rive and other motion/3D tools are supporting technologies for specific experiences. They are not replacements for Next.js or React. Use them only where the experience materially benefits, and define a fallback, performance budget, accessibility behaviour and mobile-device strategy.

### 4.3 Architecture rules

- Prefer a coherent, maintainable application over premature microservices.
- Keep business rules out of purely visual components.
- Validate all important inputs on the server.
- Enforce tenant boundaries at the database and server layers.
- Use explicit role and permission checks for every protected operation.
- Keep secrets server-side; never expose provider keys in browser code.
- Make financial and academic records auditable.
- Use idempotency and verified provider events for payment workflows.
- Design file access as private by default, with short-lived authorised access where needed.
- Document migrations, environment variables, deployment and rollback procedures.
- Avoid unnecessary paid services; cost-saving choices must not compromise data integrity, security or recovery.

The exact hosting, database, authentication, storage, email/SMS and payment-provider choices must follow the approved architecture manual and current verified implementation. Do not infer a service is configured merely because it is mentioned in a proposal.

## 5. Functional build map

Use the IDs below as stable requirement/build references. Add detailed sub-items in the tracker rather than deleting or renumbering these domains.

### APP-01 — Foundation, repository and delivery pipeline

- Repository structure, branch conventions and protected main branch.
- Local development and reproducible setup.
- Environment separation: development, preview/staging and production.
- Build, lint, type-check and automated test pipeline.
- Deployment and rollback process.
- Secret and environment-variable management.
- Error reporting, logs and release identification.

Acceptance: another authorised developer can set up the project from documentation, run checks, deploy a controlled release and roll back without undocumented manual steps.

### APP-02 — Design system and application shell

- Typography, colour, spacing, responsive breakpoints and reusable components.
- Navigation, sidebars, headers, page layouts, dialogs, forms and tables.
- Loading, empty, error, success and permission-denied states.
- Keyboard accessibility, focus states, readable contrast and reduced-motion support.
- Consistent mobile/tablet/desktop behaviour.

Acceptance: common components behave consistently and every major screen has responsive, accessible states—not just a static mock-up.

### APP-03 — Identity, authentication and account lifecycle

- Sign-up/invitation and account activation.
- Login, logout, password reset and secure recovery.
- Supported identity providers and account linking.
- Session expiry, revocation and device/session management.
- MFA for internal privileged accounts and other required roles.
- Suspended, disabled and exited-user behaviour.

Acceptance: authentication works end-to-end and account lifecycle changes immediately affect access.

### APP-04 — School creation, tenancy and onboarding

- Create school organisation and unique tenant identity.
- School profile, logo, type, address and contacts.
- School slug/subdomain allocation and collision protection.
- Session, term, calendar, class, arm and grading configuration.
- Setup progress, invitations and onboarding checklist.
- Import preview, validation, duplicate detection and error reporting.
- School data export and offboarding.

Acceptance: two test schools can be onboarded and operated without any cross-tenant data leakage.

### APP-05 — Membership, roles and permissions

- School memberships and explicit role assignment.
- Multiple roles per user with permission intersection/precedence rules.
- Role-specific navigation and dashboard entry points.
- Server-side permission enforcement and database policies.
- Invitation acceptance, expiry, revocation and staff exit.
- Permission audit and access-denied handling.

Acceptance: negative tests prove a user cannot read or modify records outside their school, role, assigned class, linked child or authorised function.

### APP-06 — School public website and publishing

- Public school profile and branded pages.
- Public announcements, events, contact and approved information.
- Content editor/publishing permissions and preview.
- School subdomain routing and domain verification where enabled.
- Public/private content separation and safe media handling.

Acceptance: public routes expose only approved content; private school records remain inaccessible without authentication and authorisation.

### APP-07 — Proprietor workspace

- Enrolment and admission overview.
- Fee billed, collected, outstanding and overdue summaries.
- Attendance and academic progress indicators.
- Staff and operational overview.
- Pending approvals and exceptions.
- Drill-down to authorised source records.
- Last-updated and incomplete-data indicators.

Acceptance: dashboard totals reconcile to underlying records and respect proprietor permissions.

### APP-08 — Principal and vice-principal workspace

- Daily attendance completion and exceptions.
- Timetable, lessons and school calendar.
- Assessment/result submission progress and review.
- Staff/class/subject oversight.
- Admissions and student movement requiring action.
- Notices, approvals and operational follow-up.

Acceptance: principal actions follow school policy, approvals and audit requirements; vice-principal permissions remain configurable.

### APP-09 — Administrator, secretary and registrar workspace

- Student and staff directory operations.
- Admissions pipeline and applicant records.
- Admission number generation and class/arm placement.
- Guardian linking and duplicate detection.
- Student transfers, withdrawals and history.
- School calendar, notices, settings and authorised exports.
- Bulk import and bulk actions with confirmation/audit.

Acceptance: records can be created, corrected and moved through their lifecycle without losing history or creating uncontrolled duplicates.

### APP-10 — Student records and guardian identity

- Student profile, unique school identifier and enrolment status.
- Academic session/class history.
- Guardian relationships and verification.
- Emergency contact and pickup data where enabled.
- Document and photo handling with privacy controls.
- Transfer, withdrawal, graduation and archival.
- Controlled merge of duplicate records.

Acceptance: one guardian can be linked to multiple children, and one child can have only explicitly authorised guardian relationships; access is tested against real relationship rules.

### APP-11 — Teacher workspace and timetable

- Assigned classes, arms and subjects.
- Today's and weekly timetable.
- Class lists and permitted student profiles.
- Daily task list and pending work.
- Teacher-specific notices and schedule changes.

Acceptance: teachers see only their assignments and permitted records; timetable changes propagate correctly to relevant users.

### APP-12 — Attendance

- Class register and attendance session creation.
- Mark all present with review and exception editing.
- Individual status changes and school-approved statuses.
- Unsaved, saving, saved, syncing and failed states.
- Corrections with reasons and audit trail.
- Attendance summaries and exception reporting.
- Offline/draft behaviour only if explicitly included in the release.

Acceptance: attendance can be marked, saved, corrected and reported without silent omissions or cross-class access.

### APP-13 — Assessment, marks and report cards

- Assessment configuration, maximum marks and weighting.
- Teacher mark entry, drafts and validation.
- Missing/out-of-range mark detection.
- Submission, review, correction and approval.
- School grading configuration.
- Result calculation, publication and report-card generation.
- Historical results and controlled amendment audit.

Acceptance: calculations match approved grading rules and a result cannot be published before required approvals.

### APP-14 — Finance and fee administration

- Fee categories, schedules and student invoices.
- Discounts, scholarships, concessions and instalments where enabled.
- Payment recording and payment allocation.
- Online payment initiation and verified confirmation.
- Pending, failed, successful, reversed and refunded states.
- Receipts, statements, outstanding balances and reconciliation.
- Financial ledger, approvals and immutable audit history.

Acceptance: every balance reconciles to invoice and ledger entries; no browser redirect alone can mark a payment successful.

### APP-15 — Parent and guardian portal

- Secure guardian login and linked-child selector.
- Child profile, attendance and published results.
- Invoices, balances, payment and receipts.
- Notices, events and school calendar.
- Notification preferences and approved contact/update requests.

Acceptance: a guardian sees only linked children and only information approved for guardian access.

### APP-16 — Communication and notifications

- In-app notifications and notification preferences.
- Email and SMS integrations where configured.
- Templates, delivery status, retries and failure visibility.
- Consent, opt-out and quiet-hour rules where required.
- Event-triggered notifications with deduplication.
- Delivery audit and provider cost monitoring.

Acceptance: failed or duplicated messages are visible and do not corrupt the underlying school workflow.

### APP-17 — School operations and extended modules

- Staff/HR, leave and payroll-related workflows if approved.
- Library, transport, clubs, events and visitor management.
- Welfare, safeguarding and incident workflows with highly restricted access.
- Operational tasks and approvals.
- Advanced analytics and multi-campus reporting.

These are not automatically first-release commitments. Each requires validated demand, a release decision, privacy review and capacity assessment.

### APP-18 — Internal ACADIVA Operations / Founder Master Control

- Internal staff identity and MFA.
- School/tenant directory and platform-level status.
- Onboarding and subscription/entitlement oversight.
- Support and operational case management.
- Feature flags and staged rollout.
- Integration and system health.
- Audit/security events and privileged access review.
- Controlled support access with reason, scope, expiry and audit trail.

Acceptance: internal operations can manage the platform without becoming an unrestricted backdoor into school data.

### APP-19 — Reporting, analytics and exports

- School dashboards and role-authorised reports.
- Consistent metric definitions and time periods.
- Drill-down to source data.
- CSV/PDF export where approved.
- Export permissions and audit history.
- Platform-level operational metrics with tenant privacy.

Acceptance: reports reconcile to source records, identify stale/incomplete data and cannot leak other tenants' information.

### APP-20 — Security, privacy, reliability and performance

- Threat modelling and access-control testing.
- Tenant isolation and object-level authorisation.
- Secure handling of student and guardian personal data.
- Audit logging, backups, recovery and retention.
- Dependency and secret management.
- Rate limiting, abuse protection and secure uploads.
- Performance budgets for core routes and mobile devices.
- Error boundaries, monitoring and incident response.

Acceptance: security, privacy, recovery and performance gates pass before production release; these are not optional polish tasks.

### APP-21 — Release, support and continuous improvement

- Release notes and change log.
- Feature flags and staged rollout.
- Pilot-school feedback and issue triage.
- Support procedures and escalation.
- Usage and adoption instrumentation with privacy safeguards.
- Regression testing and release sign-off.
- Rollback and incident communication.

Acceptance: a release can be traced to its code, requirements, tests, known issues and approval.

## 6. Release planning rules

The following is a planning framework, not a claim that these releases have already been approved or implemented.

### Foundation release

- APP-01 to APP-05.
- APP-02 design system and application shell.
- Minimum secure public website and authenticated school entry.
- Tenant isolation, identity, roles and school setup must work before sensitive workflows are added.

### Core school operations release

- APP-07 to APP-13.
- Essential administrator, teacher and principal workflows.
- Student records, attendance, timetable, assessment and result approval.

### Parent and finance release

- APP-14 and APP-15.
- Financial integrity, guardian relationships, online payment verification and receipts.

### Public web and platform operations release

- APP-06 and APP-18.
- School public sites/subdomains and ACADIVA internal operations control plane.

### Communications, reporting and extended capabilities

- APP-16, APP-17, APP-19 and selected APP-20/21 enhancements.
- Roll out only after core operations are stable and school demand is validated.

Security, privacy, tenant isolation, backups, monitoring and testing are cross-cutting requirements from the first release. They must not be postponed to a later phase.

## 7. The live delivery register — mandatory fields

Maintain one row per build item in the project tracker or a structured database. Do not rely on this narrative page alone for day-to-day status.

Required fields:

- Stable ID (APP-xx / feature ID).
- Feature or workflow name.
- Product surface and user role(s).
- Requirement source and exact section/reference.
- Release / priority.
- Delivery status from the approved status list.
- Implementation evidence: repository, file/route, pull request or commit.
- Environment and deployed preview/production URL where applicable.
- Acceptance criteria and test evidence.
- Dependencies and affected shared services.
- Risks, open decisions and blockers.
- Owner.
- Last verified date and verifier.
- Next concrete action.

If a database is not yet available, keep a clearly dated table in this page or the execution manual. Do not create competing status lists in several documents. The single delivery register is authoritative; the master checklist links to it.

## 8. Required builder answers and queries

When asked any of these questions, the builder must query the current delivery register and verify evidence where available.

### “What are we yet to build?”

Return:

1. Not-started items grouped by release and application surface.
2. In-progress items.
3. Implemented but untested items.
4. Blocked items and exact blockers.
5. Deferred items, clearly separated from required work.
6. The next recommended build sequence with dependencies and rationale.

Do not mix future roadmap items with current-release obligations.

### “What is left to build in the app?”

Filter to application build items and include:

- Screens/routes/workspaces.
- End-to-end user workflows.
- Backend/API/business logic.
- Data model and migrations.
- Permissions/security.
- Integrations.
- Responsive states/accessibility.
- Tests, deployment and monitoring.

A frontend screen without working backend behaviour is not a completed feature.

### “What have we completed?”

List only items in <b>Tested and accepted</b>, with acceptance evidence and date. Separately list implemented-but-untested items.

### “What should we build next?”

Prioritise in this order:

1. Security, data integrity, tenant isolation and release blockers.
2. Dependencies that unlock multiple workflows.
3. Core school operations and high-frequency user tasks.
4. Financial/guardian workflows with appropriate integrity controls.
5. Pilot feedback and validated school needs.
6. Later modules and visual enhancements.

Explain trade-offs and what the proposed work will affect.

### “Does the app match the blueprint?”

Run a traceability check:

- Requirement → design → route/screen → API/service → data model → permission → test → deployed evidence.
- Identify missing links, drift, stale decisions and duplicated implementations.
- Report pass, partial, fail or not verified for each area.
- Recommend corrections before expanding scope.

## 9. Mandatory build loop — the product taste test

Every meaningful feature must pass the following cycle, repeatedly during implementation:

1. <b>Re-read intent:</b> identify the relevant product operating model, requirement, architecture and workflow.
2. <b>Define the slice:</b> specify the user, role, surface, problem, acceptance criteria and release.
3. <b>Map impact:</b> identify routes, components, APIs, tables, policies, integrations, notifications, reports and other affected surfaces.
4. <b>Challenge the proposal:</b> state benefits, drawbacks, risks, cost, complexity, alternatives and what could break.
5. <b>Build a small vertical slice:</b> deliver a real end-to-end path rather than a disconnected mock screen.
6. <b>Taste-test during the build:</b> compare the working result with the original requirement and real user workflow. Stop when drift appears.
7. <b>Test the full chain:</b> happy path, validation, empty state, failure state, permission denial, tenant isolation, mobile layout and regression.
8. <b>Inspect connected surfaces:</b> verify public ACADIVA website, school websites/subdomains, all affected role workspaces and internal Operations where relevant.
9. <b>Accept or reject:</b> only mark accepted when evidence meets the criteria.
10. <b>Update the register and documentation:</b> record status, evidence, decisions, defects and next action.

Do not build a feature merely because it is easy or visually impressive. Do not keep adding features while core workflows remain broken.

## 10. Cross-surface impact checklist

Before changing shared infrastructure or a central data entity, check all applicable surfaces:

- Public ACADIVA website.
- School public websites and custom/subdomains.
- Authenticated school application.
- Proprietor workspace.
- Principal/vice-principal workspace.
- Administrator/registrar workspace.
- Bursar/finance workspace.
- Teacher workspace.
- Parent/guardian portal.
- Student experience if enabled.
- School ICT/setup operator.
- Founder Master Control.
- ACADIVA CTO/Operations.
- APIs, background jobs, notifications, analytics and integrations.
- Database policies, storage permissions, DNS/routing and deployment.

A surface can be marked not applicable only with a short reason.

## 11. Non-negotiable integrity rules

- Never invent implementation status, test results, repository paths or deployment evidence.
- Never equate a design mock-up with a working feature.
- Never equate a successful build command with a successful user workflow.
- Never mark an item accepted without evidence.
- Never silently remove requirements to make the tracker look complete.
- Never treat a proposal or future idea as an approved release commitment.
- Never make a broad architectural change without impact analysis and a recorded decision.
- Never allow school tenant data to be accessed through another tenant's routes, IDs, files or APIs.
- Never expose internal ACADIVA privileges through school administrator roles.
- Keep the original chronological source material intact; update the active manual and delivery register.

## 12. First required action: implementation baseline audit

Before answering with a definitive list of what is built or yet to build, perform a baseline audit of the actual project:

1. Identify the canonical repository and active production/preview deployment.
2. Inspect the current branch, commit, project structure, routes, components, API/server actions and database migrations.
3. Inspect authentication, tenancy, role/permission policies, storage and integrations.
4. Run the available lint, type-check, build and automated tests.
5. Open and exercise the actual app on supported viewport sizes.
6. Map each implemented route/workflow to APP-01 through APP-21 and the relevant master requirement.
7. Test the end-to-end workflows and negative permission/tenant cases.
8. Record each item as evidenced, partially evidenced, unverified, missing or blocked.
9. Produce the initial gap report and recommended build order.
10. Update the delivery register with repository/commit, preview URL, test evidence and audit date.

If repository or deployment access is unavailable, say exactly what could not be inspected and do not claim a completed baseline audit.

## 13. Current audit state

<b>Baseline implementation audit: Not yet performed in this document.</b>

No APP domain is certified as complete by the creation of this map. The current application, repository, deployed environment, tests and live workflows must be inspected before the builder can provide a reliable “built versus remaining” answer.

The first deliverable from the audit is a dated implementation inventory, not another feature brainstorm.
