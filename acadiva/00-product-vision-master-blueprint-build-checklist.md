<!-- Source: https://app.notion.com/p/4199a9b48b7a81b99900c70ca63a6605?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🏫 ACADIVA — Product Vision, Master Blueprint & Build Checklist

# REORGANISED BLUEPRINT — START HERE

<b>The original master blueprint has been preserved in full.</b> Its chronological content remains below as the historical source record. To stop the documentation from growing as an unstructured sequence of sections, the complete source material has now been reproduced in seven curated manuals under this page. Use these manuals as the active working structure; do not use the old chronological map below as the current navigation.

## The seven working manuals

1. <b>Core operating model, master requirements and system architecture</b> — the five principal documents in the correct reading order: Section 60 (broad product operating model), Section 36 (master product requirements), Section 46 (product architecture and system map), and Section 56 (system architecture and implementation blueprint).<br /><mention url="https://app.notion.com/p/41c9a9b48b7a814e96e4f5e4cbef2920">00 — ACADIVA Core Operating Model, Master Requirements & System Architecture</mention>
2. <b>Master execution checklist, governance and build gates</b> — Section 40 (master execution checklist), Section 55 (Founder/CTO/Operations and school administrator governance), Section 50-C (deliberate engineering and pre-build review), and Section 58 (feature-level design and delivery gate).<br /><mention url="https://app.notion.com/p/41c9a9b48b7a8115b27ce9fcd65320a0">01 — ACADIVA Master Execution Checklist, Governance & Build Gates</mention>
3. <b>Product strategy, market and commercial model</b> — vision, target schools, product principles, adoption, pilot, partnerships, investment and all pricing/business-model history and proposals.<br /><mention url="https://app.notion.com/p/41c9a9b48b7a8197b133d5f5a18b628d">02 — ACADIVA Product Strategy, Market & Commercial Model</mention>
4. <b>Core modules, roles, teaching and school workflows</b> — school setup, student/staff records, academic workflows, attendance, timetable, communication, role-based workspaces and cross-dashboard consistency.<br /><mention url="https://app.notion.com/p/41c9a9b48b7a81b4aed8f94986dc1ecb">03 — ACADIVA Core Modules, Roles, Teaching & School Workflows</mention>
5. <b>Admissions, student records, guardian identity and finance</b> — admissions, enrolment, student passport, guardian relationships, school-led onboarding, financial records, payments, receipts and term lifecycle.<br /><mention url="https://app.notion.com/p/41c9a9b48b7a81539c55f74d01885bc1">04 — ACADIVA Admissions, Student Records, Guardian Identity & Finance</mention>
6. <b>Platform architecture, operations, integrations and infrastructure</b> — application/runtime architecture, tenancy, security, Founder/CTO Operations, service integrations, SMS, hosting, storage, domains and infrastructure cost controls.<br /><mention url="https://app.notion.com/p/41c9a9b48b7a816a9283d8878f359bb0">05 — ACADIVA Platform Architecture, Operations, Integrations & Infrastructure</mention>
7. <b>Design, experience and creative technology</b> — screen architecture, design principles, competitive references, payment experience, design research, Next.js/Three.js hierarchy, animation, 3D and performance standards.<br /><mention url="https://app.notion.com/p/41c9a9b48b7a81d9a0cac9af71e89d01">06 — ACADIVA Design, Experience & Creative Technology</mention>

## Application build map and live delivery status

The application itself has a dedicated build map, functional inventory, release framework, implementation audit procedure and delivery-status rules. Use it to answer what is built, what remains, what is untested and what should be built next. No feature is complete without implementation and acceptance evidence.

<mention url="https://app.notion.com/p/41c9a9b48b7a814db204d631c1a7df64">07 — ACADIVA Application Build Map, Delivery Register & Implementation Audit</mention>

## Non-negotiable rule for every build

Before a meaningful build or change, review <b>Sections 60, 36, 46, 56 and 40</b> in that order, then Section 55 and the relevant specialist manual. During implementation, repeatedly perform the cooking-style taste test: compare the current result against requirements, workflows, roles, shared data, affected dashboards, websites/subdomains, internal Operations and infrastructure. Stop and correct drift before continuing. After implementation, run regression, security, tenant-isolation, mobile/performance and acceptance checks, then update the relevant documentation and checklist.

## Important architecture clarifications

- <b>Next.js + React is the primary web application framework.</b> It supports the central ACADIVA website, school public websites, login, private school workspaces and protected ACADIVA Operations routes.
- <b>Three.js and React Three Fiber are browser-side graphics technologies used inside selected Next.js experiences.</b> They do not replace Next.js or the school-management backend.
- <b>The internal ACADIVA CTO/Operations role is not the school administrator.</b> The internal CTO is a company-side role governed by Founder Master Control. A school administrator/setup operator acts only within the school's authority.
- <b>The central website, every school's public website/subdomain, role workspaces, Founder Master Control and ACADIVA Operations are all product surfaces.</b> They may share one application and infrastructure, but each must be deliberately routed, permissioned, tested and supported. Do not forget one because another is already built.

## Duplicate Section 50 identifiers

The original page had three separate sections numbered 50. The reorganised manuals assign stable references:

- <b>50-A:</b> Provider-independent SMS architecture and BulkSMS Nigeria integration.
- <b>50-B:</b> Product principles, differentiation, experience and scalability.
- <b>50-C:</b> Deliberate engineering, design quality, scale and pre-build review.

The original source page remains unchanged in its historical body; the curated manuals disambiguate these records.

---

<b>Section 40 — ACADIVA Master Product, Workflow, Design and Launch Checklist:</b> the comprehensive role-by-role and module-by-module execution checklist, including proprietor, principal, administrator, bursar, teacher, parent and student experiences; attendance and fee workflows; notifications and integrations; design system; infrastructure; quality gates; pilot; and future roadmap. Use this as the verification register alongside Section 39's technology and design architecture.

## Historical document map — pre-reorganisation snapshot (retained for traceability; no longer the active navigation)

This is the original chronological source record. It is retained in full. Use the reorganised child manuals linked at the top of this page for active navigation, source-of-truth guidance and build control.

### Historical navigation snapshot (retained; use the reorganised manuals above instead)

1. <b>Section 36 — Master product requirements and operating model:</b> the consolidated reference for product scope, user roles, workflows, permissions, exports, technical foundations, release priorities and confirmed decisions.
2. <b>Sections 1–34 — Product discovery and earlier working decisions:</b> retain the original vision, problem map, architecture discussions, feature proposals and earlier pricing drafts. Treat older proposals as history where Section 36 or a later dated decision records a newer choice.
3. <b>Section 35 — Current pricing and unit-economics proposal:</b> the latest pricing hypothesis, school-size assumptions, operating-cost model, 10-school scenario and validation plan. Prices remain provisional until validated with schools.
4. <b>Section 37 — Strategic revision:</b> the latest adoption strategy, proprietor experience, simplicity principles, mobile/offline direction, pilot and proof-led sales model, onboarding approach and cost framework. Where it records a newer direction, Section 37 supplements or supersedes earlier assumptions; Section 36 remains the detailed master requirements reference.
5. <b>Section 38 — Free-tier-first infrastructure and financial model:</b> the staged infrastructure strategy, free-plan constraints, illustrative school-scale revenue and cost scenarios, onboarding economics, upgrade triggers and financial assumptions. Figures are planning estimates, not verified quotations or forecasts.
6. <b>Section 39 — Technology infrastructure, engineering controls and design direction:</b> the full technology/tool inventory, infrastructure topology, integration register, engineering workflow, security/quality controls, UI/UX design direction, visual references, payment experience principles and decisions about tools such as Sentry and Lovable.
7. <b>Section 40 — Master product, workflow, design and launch checklist:</b> the numbered execution checklist across every role and product area.
8. <b>Section 41 — Simplification decisions, role boundaries and free/open-source stack:</b> the latest decisions on parent-owned student access, subtle birthdays, minimal attendance, shared live updates, timetables, announcements, optional homework and selected software licences. Section 41 overrides conflicting older requirements in Sections 36 and 40.
9. <b>Section 42 — Core product scope and automatic cross-dashboard data consistency:</b> the current core release boundary, one authoritative record, server-confirmed updates, role-specific dashboards and acceptance criteria.
10. <b>Section 43 — Online admissions, parent application links and student onboarding:</b> the end-to-end journey from a school's shareable application link through parent submission, school review, admission offer, final placement and conversion into the official student record.
11. <b>Section 44 — Student Record Passport, portable academic history and verified exports:</b> automatic Applicant profile creation, configurable admission approval, consolidated transcripts, attendance evidence, transfer records, secure sharing, document verification and student-record portability.
12. <b>Section 45 — ACADIVA Operations, Founder Master Control, CTO Governance and Centralised School Onboarding:</b> an internal protected workspace within the main ACADIVA website, founder-controlled CTO approval, cross-school operational access, onboarding on behalf of schools, delegated actions, school activation, security and audit requirements.
13. <b>Section 46 — ACADIVA as One Connected Product, Workspace Architecture, Shared Data, System Map and Build Sequence:</b> the connected role-based workspace model, shared identity and data foundations, permissions, authoritative records, design/screen architecture, cross-workspace workflows and recommended build order.
14. <b>Section 47 — School Finance, Academic Term Lifecycle, Student Lifecycle, SMS-First Parent Communication and Template-Led CTO Onboarding:</b> the revised financial operating system, end-of-term/new-term workflow, student status history, parent SMS strategy, reusable school templates, CTO school setup and non-destructive configuration rules. Section 47 is the latest decision record where it conflicts with older proposals.
15. <b>Section 48 — ACADIVA Integration and External Service Register:</b> the explicit provider/capability inventory and event flows for transactional email (Resend), SMS, payments, authentication, storage, hosting, DNS, monitoring, analytics, backups, exports, push and support. Distinguishes confirmed requirements from vendor candidates and open selections.
16. <b>Section 49 — ACADIVA Finance: Zero-Additional-Service-Cost Strategy, Architecture Boundaries and Phased Delivery:</b> the agreed free-tier-first approach for building the school financial operating system, using the existing stack and internal implementation, with manual verification and CSV reconciliation initially, while preserving essential accounting integrity, security and audit controls.
17. <b>Section 53 — ACADIVA Parent Identity, Multi-Child Access, Guardian Relationships and Student Login Policy:</b> one guardian account, phone-based OTP direction, multiple verified children and schools, multiple guardians per child, restricted student logins, tenant isolation and security tests.
18. <b>Section 54 — ACADIVA School-Led Student Onboarding, Guardian Account Preparation, Bulk Import and Parent Activation:</b> school-managed student registration, automatic matching of guardian contact records, pending parent accounts, verified activation, duplicate/conflict handling, invitations, late contact updates and safe bulk-import workflow.
19. <b>Section 55 — ACADIVA Governance, Operations Workspace, School Administrator/CTO, Master Checklist and Mandatory Build Gate:</b> central Operations governance, school-level configuration ownership, role boundaries, school setup, result completeness, timetable constraints and the mandatory pre-tool/build checklist.
20. <b>Section 56 — ACADIVA Connected System Architecture, Shared Data Model, Integration Map and Implementation Blueprint:</b> reconciled decisions, connected workspaces, authoritative data model, tenant security, cross-module events, technical boundaries, build sequence, acceptance tests and open implementation blockers.
21. <b>Section 57 — ACADIVA Premium Design Standard, Mandatory Reference Research and Payment Experience:</b> the required six-platform design research library, original-design and responsible-use rules, premium payment journey, shared design system, motion/accessibility/performance standards, design artefacts, review gate and connections to the engineering checklist.
22. <b>Section 58 — Implementation-Stage Design Research Gate and Feature-by-Feature Delivery Checklist:</b> converts design governance into a mandatory per-feature implementation sequence, adds master execution checklist 40AE, requires reference research and design approval before coding, and connects visual QA with end-to-end acceptance evidence.
23. <b>Section 59 — ACADIVA Visual Experience, Creative Technology Stack & Graphics Architecture:</b> records the balanced, visual-first direction and the selected application, 3D, animation, interactive graphics, shader, optional cinematic sequencing and 3D authoring technologies, with tool ownership, performance controls and implementation gates.
24. <b>Section 60 — ACADIVA Product Operating Model, Multi-School Architecture, Role Workflows, School Operations, Finance and Cost-Conscious Identity:</b> consolidates the end-to-end school lifecycle, school website template architecture, tenant/branch model, academic progression, parent/teacher/student rules, school operations, financial controls and phone-first authentication without routine SMS OTP.
25. <b>Section 61 — ACADIVA Infrastructure Cost Management, Free-Tier-First Deployment and Upgrade Policy:</b> records the agreed start-free approach, provider selection principles, usage monitoring, upgrade gates, production reliability exceptions, cost controls, portability and a measured monthly cost model.

### Documentation rule

- Preserve earlier content and its rationale.
- Add new material in dated, clearly titled sections.
- Do not silently overwrite a previous decision.
- When a decision changes, record the new decision, date, rationale and the older section it supersedes; retain the older text as history.
- Keep confirmed decisions distinct from proposals, assumptions and open questions.
- Use Section 36 as the current consolidated product reference, while retaining specialised sections (such as pricing) as their detailed source.

### Current product direction

ACADIVA is being designed as a complete school operating system for Nigerian schools, with role-specific workspaces for proprietors, principals, finance staff, registrars, administrators, teachers, parents and students. The system must connect student records, academics, attendance, fees, payments, communication, documents and school operations while maintaining strict school-level data separation.

> <b>Status:</b> Working product blueprint. <b>Name:</b> ACADIVA (working name; brand/domain clearance pending). <b>Initial market:</b> Independent and small-to-medium private schools in Nigeria. <b>Category:</b> Multi-tenant school management software.

## 1. Executive summary

ACADIVA is envisioned as an all-in-one digital operating system for schools. It connects administration, student records, academics, teachers, parents, fees, finance, communication and school operations.

It is not simply a school website or online result checker. It is intended to become the system a school uses to manage its everyday operations.

Each school receives its own branded portal and subdomain while using shared ACADIVA infrastructure. Each school's users and records must remain securely separated from every other school's data.

## 2. Vision and value proposition

<b>Vision:</b> Make organised, accessible digital school management available to schools of different sizes, starting in Nigeria.

<b>Core value proposition:</b> A school should be able to manage its administration, academics, finances and parent communication from one place.

<b>Value delivered</b>

- Reduce paperwork and repetitive manual administration.
- Improve the accuracy and availability of school records.
- Give proprietors better visibility and control.
- Help teachers manage academic work efficiently.
- Give parents convenient access to relevant information about their children.
- Improve fee tracking, accountability and communication.
- Give smaller schools practical digital infrastructure without building their own software.

## 3. Target customers and users

### Initial target customers

- Independent private nursery and kindergarten schools.
- Primary schools.
- Junior secondary schools.
- Senior secondary schools.
- Schools combining several levels, such as nursery through secondary.
- Potentially, school groups operating multiple branches.

The initial focus is small and medium-sized schools that rely heavily on paper records, spreadsheets, messaging apps or disconnected tools. This target-market hypothesis needs validation through school interviews.

### Main user roles

| User | Main needs |
| --- | --- |
| Proprietor / Owner | Whole-school oversight, finances, staff, enrolment and performance |
| Principal / Head teacher | Daily administration, academics, attendance and staff supervision |
| Administrator / Registrar | Admissions, student records, documents and communications |
| Teacher | Assigned classes, attendance, scores, results and student progress |
| Bursar / Accountant | Fees, payments, receipts, balances, expenses and financial reports |
| Parent / Guardian | Their children's results, attendance, fees, receipts and notices |
| Student | Age-appropriate learning information and school resources, if enabled |
| Platform administrator | Tenant support, platform configuration, security and subscriptions |

Permissions must be role-based. Teachers should not automatically see all financial records. Parents must only see records for children linked and verified by the school.

## 4. Problems ACADIVA solves

### 4.1 School administration and records

<b>Problems:</b> Student information is scattered across paper files, notebooks and spreadsheets; old records take time to retrieve; files can be lost or duplicated; admissions and enrolment are manual; transfers and withdrawals are hard to track; schools lack reliable enrolment overviews; academic sessions and class structures are inconsistently organised; staff repeatedly enter the same information; multi-branch schools lack consolidated oversight.

<b>ACADIVA capabilities:</b> Central student database, searchable profiles, digital admissions, enrolment management, student status history, academic session and term setup, class allocation, document storage and multi-branch oversight.

### 4.2 Teaching and academic administration

<b>Problems:</b> Teachers manually record attendance and scores; examination totals, averages and grades are calculated by hand; report cards take time; continuous assessment records are difficult to maintain; results are late or inconsistent; teachers struggle to manage multiple classes; performance trends are hard to identify; parents may only learn of academic difficulties at term end.

<b>ACADIVA capabilities:</b> Teacher dashboards, class and subject assignments, digital attendance, continuous assessment, examination records, configurable grading rules, automated calculations, result submission, report-card generation and performance history.

### 4.3 Parents and guardians

<b>Problems:</b> Parents visit school to collect results or ask for updates; they may not know attendance or progress during the term; fee balances and payment history are difficult to confirm; receipts get misplaced; announcements may not reach everyone; PTA meetings and events are missed; parents with multiple children deal with disconnected records.

<b>ACADIVA capabilities:</b> Parent portal, linked-child profiles, results, attendance, fee balances, payment history, downloadable receipts, announcements, event and PTA notices, and school enquiry channels.

### 4.4 Fees and financial management

<b>Problems:</b> Fee collection is tracked manually; unpaid and partial payments are hard to identify; fee categories are difficult to manage; balances may be inaccurate; receipts are lost or duplicated; reminders are manual; bank transfers are difficult to reconcile; proprietors lack timely income and expenditure reports; expenses and salary records are separate; collection accountability is weak.

<b>ACADIVA capabilities:</b> Configurable fee structures, student billing, payment recording, part-payment handling, balance calculation, receipts, reconciliation, reminders, expenses, payroll records, financial reports and audit trails.

Online payment gateway integration is a proposed later capability, subject to provider availability, fees, compliance and technical feasibility.

### 4.5 Communication and notifications

<b>Problems:</b> Schools rely on informal WhatsApp groups; important messages get buried; parents miss notices; teachers and parents lack organised communication history; PTA invitations are manual; urgent notices may not reach everyone; parent enquiries and complaints lack a consistent channel.

<b>ACADIVA capabilities:</b> School announcements, circulars, class-specific notices, direct parent communication, PTA invitations, event reminders, notification history and optional email/SMS/push channels. Delivery channels and costs need evaluation.

### 4.6 Staff and human resources

<b>Problems:</b> Staff details are in paper files; attendance and leave are manual; responsibilities and teaching assignments may be unclear; salary calculations and deductions are separate; performance records are inconsistent; onboarding and exit documents are hard to retrieve.

<b>ACADIVA capabilities:</b> Staff profiles, role assignments, attendance, leave requests, class/subject allocation, payroll records, deductions and staff history.

### 4.7 School operations and facilities

<b>Problems:</b> Calendars and event schedules are fragmented; examination schedules clash; classroom allocation is difficult; assets and inventory are poorly tracked; library borrowing records are unreliable; transport is managed manually; discipline and incident records are inconsistent.

<b>ACADIVA capabilities:</b> School calendar, events, examination scheduling, classroom allocation, asset register, inventory, library records, transport management and incident/discipline documentation. These are expansion opportunities, not all launch requirements.

### 4.8 Admissions and school growth

<b>Problems:</b> Prospective parents must visit for basic enquiries; applications are paper-based; applicant status is difficult to track; documents are misplaced; schools lack professional online presence and struggle to publish news and information.

<b>ACADIVA capabilities:</b> School profile and website, online enquiry forms, admission applications, applicant pipeline, document uploads, admission status updates, news and gallery.

### 4.9 Reporting, accountability and decision-making

<b>Problems:</b> Proprietors lack timely financial visibility; academic performance is difficult to compare across classes or terms; attendance patterns are hard to analyse; fee reports require manual compilation; record changes are not traceable; decisions rely on fragmented data.

<b>ACADIVA capabilities:</b> Academic, attendance and financial dashboards; term comparisons; collection reports; user activity logs; record change history; exports and management reports.

## 5. Product architecture and school tenancy model

### 5.1 Multi-tenant platform

ACADIVA should be one shared software platform serving many schools, with each school represented as a separate tenant.

Illustrative subdomains:

- [might.acadiva.ng](http://might.acadiva.ng)
- [brightfuture.acadiva.ng](http://brightfuture.acadiva.ng)
- [royalacademy.acadiva.ng](http://royalacademy.acadiva.ng)

These are examples only; final domain and subdomain conventions are not confirmed.

Each tenant has its own school identity, branding, administrators, staff, teachers, parents, students, academic sessions, classes, subjects, fee configuration, records, documents, reports and communications.

### 5.2 Data isolation and security requirements

Tenant separation is foundational.

- Every school-owned record must be associated with a school/tenant identifier.
- Every request must enforce tenant context on the server, not only in the interface.
- Database policies and backend authorisation must prevent cross-school access.
- A parent account can only access children explicitly linked and verified by the school.
- Role-based access applies to pages, data, exports and actions.
- Sensitive actions should be logged.
- Backups, retention, restoration and deletion procedures must be defined.
- Staff access should be revoked promptly when employment ends.
- Security testing must include attempts to access another school's records.

A shared database can support this model, but implementation must provide strong logical isolation. Final database and hosting architecture remains to be validated.

## 6. Product modules and detailed blueprint

### A. Platform and school setup

<b>Purpose:</b> Create and configure each school's digital environment.

- School registration and onboarding.
- School name, logo, address, contact details and branding.
- Subdomain assignment.
- School type and education levels.
- Academic session and term configuration.
- Grading and assessment configuration.
- School calendar and operating days.
- Branch setup, where applicable.
- Subscription plan and module settings.
- Initial data import and onboarding checklist.

### B. Administration dashboard

<b>Purpose:</b> Give authorised leaders a whole-school overview.

- Total students and enrolment by class.
- Staff count and attendance overview.
- Fee collection and outstanding balances.
- Attendance summaries.
- Academic submission status.
- Recent announcements and events.
- Tasks requiring administrator attention.
- Quick links to key modules.

Dashboard data must respect user permissions.

### C. Student information system

<b>Purpose:</b> Maintain the authoritative student record.

- Admission and student ID.
- Student biodata and photograph.
- Parent/guardian contacts and verified relationships.
- Class and arm allocation.
- Previous school and admission history.
- Uploaded documents.
- Attendance history.
- Academic results and report cards.
- Fee accounts and payment history.
- Student status: applicant, active, transferred, withdrawn, graduated or configured equivalent.
- Promotion and class history.
- Restricted emergency/medical information, with appropriate privacy controls.

### D. Admissions and enrolment

<b>Purpose:</b> Manage the journey from enquiry to enrolled student.

- Public admission enquiry form.
- Online application form.
- Applicant profile and document uploads.
- Application review and status tracking.
- Admission offer and acceptance records.
- Student record creation from accepted application.
- Class capacity and placement tracking.
- Admission communication templates.

### E. Academic structure

<b>Purpose:</b> Configure the school's academic organisation.

- Academic sessions and terms.
- Education levels and class groups.
- Class arms/streams.
- Subjects and subject combinations.
- Teacher-to-class and teacher-to-subject assignments.
- Grading scales and assessment weights.
- Promotion rules and academic history.
- School-specific report templates.

The system must support different Nigerian school structures and grading practices rather than assuming one universal format.

### F. Teacher workspace

<b>Purpose:</b> Give teachers a simple workspace for assigned duties.

- Teacher profile and assigned classes.
- Assigned subjects and class lists.
- Daily attendance entry.
- Continuous assessment entry.
- Examination score entry.
- Draft and submit results.
- Assignment and homework records (later phase).
- Student progress view for assigned classes.
- Notices from school management.

Teachers should only access classes and students they are authorised to manage.

### G. Attendance management

<b>Purpose:</b> Record and monitor attendance.

- Student attendance by class and date.
- Present, absent, late and excused status.
- Attendance correction with reason and audit record.
- Class and student attendance summaries.
- Parent visibility for relevant attendance.
- Configurable alerts for repeated absence.
- Staff attendance as a separate capability.

### H. Examinations, results and report cards

<b>Purpose:</b> Manage assessment from score entry to parent-facing report.

- Assessment components and weightings.
- Continuous assessment and examination scores.
- Configurable grading rules.
- Automatic totals, averages and grades.
- Validation for missing or out-of-range scores.
- Teacher submission and approval workflow.
- Result locking and controlled corrections.
- Report-card templates.
- Attendance and teacher comments where configured.
- Class and subject performance reports.
- Printable and downloadable results.
- Historical results across terms and sessions.

### I. Parent and guardian portal

<b>Purpose:</b> Give parents a secure view of their children's school information.

- Parent account and identity/contact verification.
- Link one parent to multiple children.
- View results and report cards.
- View attendance.
- View fee invoices, balances and payment history.
- Download receipts.
- Receive school and class announcements.
- View calendar and PTA notices.
- Submit enquiries or complaints.
- Manage notification preferences.

Parents must never be able to search or browse other families' records.

### J. Fees, billing and payments

<b>Purpose:</b> Make school fee administration accurate and transparent.

- Fee categories and schedules.
- Fees by class, student or configured group.
- Invoices and payment references.
- Full and partial payment recording.
- Discounts, waivers and adjustments with permissions.
- Outstanding balance calculation.
- Receipt generation and payment history.
- Bank transfer and cash payment recording.
- Gateway integration (later phase).
- Payment reconciliation and exception handling.
- Parent reminders.
- Collection summaries by class, term and date.

### K. Finance and accounting support

<b>Purpose:</b> Give school management a better view of money received and spent.

- Income records.
- Expense categories and entries.
- Expense evidence/attachments.
- Approval workflow for selected expenses.
- Cash/bank account records.
- Fee collection summaries.
- Income and expenditure reports.
- Payroll records and salary history.
- Deductions and allowances.
- Exportable reports.

Initial scope may be school finance administration and reporting rather than a full statutory accounting package. Requirements need validation with actual bursars/accountants.

### L. Staff and HR

<b>Purpose:</b> Organise staff records and employment administration.

- Staff profiles and documents.
- Department and role.
- Employment status and dates.
- Teacher qualifications and assigned subjects.
- Staff attendance.
- Leave requests and approvals.
- Payroll information and salary history.
- Staff performance records.
- Onboarding and exit checklist.

### M. Communication centre

<b>Purpose:</b> Provide an organised official channel for school communication.

- School-wide announcements.
- Class-specific announcements.
- Parent and staff notices.
- Circulars and document sharing.
- PTA invitations and reminders.
- Event notifications.
- Direct enquiries and complaint tracking.
- Email, SMS and push notification integrations, subject to cost and provider review.
- Delivery and communication history.

### N. Calendar and events

<b>Purpose:</b> Coordinate the school year and school activities.

- Academic calendar, term dates and holidays.
- PTA meetings.
- School events and activities.
- Examination dates.
- Parent-facing event information.
- Reminders and updates.

### O. School website and public profile

<b>Purpose:</b> Give each school a professional digital presence.

- Branded school landing page.
- School history and description.
- Education levels and programmes.
- Contact details and location.
- Admissions information and enquiry form.
- News and announcements.
- Gallery.
- Approved staff or leadership information.
- Links to secure parent and staff portals.

The public website and private management portal must have separate access boundaries.

### P. Reports and analytics

<b>Purpose:</b> Turn operational records into useful management information.

- Enrolment reports.
- Student movement reports.
- Attendance reports.
- Academic performance reports.
- Class and subject comparisons.
- Fee collection and outstanding balance reports.
- Expense and payroll summaries.
- Staff reports.
- PDF/CSV exports where appropriate.
- Filters by session, term, class, date and branch.

### Q. School operations (later expansion)

- Timetable and classroom scheduling.
- Transport routes and vehicle records.
- Library catalogue and borrowing.
- Inventory and supplies.
- School assets.
- Incident and discipline records.
- Homework and assignments.
- Online examinations.
- Learning resources and LMS features.

Prioritise only after customer discovery confirms demand.

### R. AI-assisted tools (later expansion)

- Draft parent announcements and circulars.
- Summarise academic reports for staff review.
- Identify patterns in attendance and performance.
- Assist with report comments.
- Extract structured information from uploaded documents, subject to review.
- Help administrators find information using natural language.

AI must assist authorised users, not autonomously make consequential decisions about students, discipline, admissions or progression. Human review and data safeguards are required.

## 7. Role-based access overview

| Capability | Proprietor | Principal/Admin | Teacher | Bursar | Parent |
| --- | --- | --- | --- | --- | --- |
| School-wide dashboard | Full | Configurable | No/limited | Finance view | No |
| Student records | Full | Manage | Assigned students | Limited billing details | Own children only |
| Attendance | Full | Manage | Assigned classes | No | Own children only |
| Scores and results | Full | Approve/manage | Assigned classes | No | Own children only |
| Fees and payments | Full | Configurable | No | Manage | Own children only |
| Expenses and payroll | Full | Configurable | No | Authorised | No |
| Staff records | Full | Manage | Own profile/limited | Payroll data as authorised | No |
| Announcements | Full | Manage | As authorised | As authorised | Relevant notices |
| School settings | Full | Limited | No | No | No |

This is an initial model. Exact permissions can be configurable while preserving tenant and privacy boundaries.

## 8. Key user journeys

### Journey 1 — A school joins ACADIVA

1. Proprietor or authorised representative registers the school.
2. School identity and contact details are entered.
3. School subdomain and branded portal are configured.
4. Academic session, terms, classes and subjects are created.
5. Staff accounts and permissions are added.
6. Student and parent records are imported or entered.
7. Fees and grading rules are configured.
8. Teachers and parents are invited.
9. School completes onboarding checks and begins using the system.

### Journey 2 — Teacher submits term results

1. Teacher signs in and sees assigned classes and subjects.
2. Teacher enters continuous assessment and examination scores.
3. System validates missing or invalid entries.
4. Teacher submits results.
5. Authorised reviewer checks and approves them.
6. Results are published to parent accounts.
7. Corrections after publication follow a controlled, logged process.

### Journey 3 — Parent checks a child's progress

1. Parent signs in and selects a linked child.
2. Parent views published results and attendance.
3. Parent reviews fee balance and payment history.
4. Parent downloads available receipts or report cards.
5. Parent receives relevant school notices.

### Journey 4 — Parent pays school fees

1. Parent views an invoice and outstanding balance.
2. Parent selects an available payment method.
3. Payment is completed or recorded by authorised school staff.
4. ACADIVA records the transaction and updates the balance after verification.
5. A receipt is issued.
6. Bursar can reconcile the payment and view it in reports.

Payment must not be marked successful based only on a browser redirect or unverified parent claim. Gateway confirmation and reconciliation rules must be defined.

### Journey 5 — Proprietor reviews school performance

1. Proprietor signs in.
2. Dashboard shows enrolment, attendance, academic and financial summaries.
3. Proprietor filters reports by term, class or branch.
4. Proprietor reviews trends and outstanding items.
5. Authorised reports can be exported.

## 9. Phased product roadmap

### Phase 1 — Minimum viable product

Build the smallest coherent system a real school can use for core operations:

- School registration and setup.
- Tenant and role management.
- Student database.
- Classes, subjects, sessions and terms.
- Teacher accounts and assignments.
- Student attendance.
- Assessment and examination score entry.
- Configurable grading and result calculation.
- Result approval and report cards.
- Parent portal.
- Fee configuration, payment recording and receipts.
- Basic announcements.
- Essential administrator dashboards and reports.

### Phase 2 — Operational depth

- Online payment gateway integration.
- Expense management.
- Payroll and staff management.
- Admissions workflow.
- School website builder.
- PTA and event management.
- Email/SMS/push notification options.
- Timetables and calendar improvements.
- Multi-branch reporting.
- Data import tools and stronger audit reporting.

### Phase 3 — Advanced school infrastructure

- Learning management and assignments.
- Online examinations.
- Library, transport, inventory and assets.
- Advanced academic and financial analytics.
- AI-assisted administration.
- Third-party integrations and APIs.
- Expanded group and multi-branch controls.

Priorities should be adjusted after interviews and pilots. This is a proposed sequence, not a committed delivery schedule.

## 10. Business model hypotheses

A subscription SaaS model is the initial commercial hypothesis.

Possible pricing dimensions:

- Number of active students.
- School size or tier.
- Included modules.
- Number of branches.
- Storage or communication usage.
- Optional onboarding and data migration.

Illustrative prices discussed for testing only, not validated market rates:

- Small school: ₦10,000/month.
- Medium school: ₦20,000/month.
- Larger school: ₦35,000+/month.

Potential additional revenue:

- School website setup or premium customisation.
- Data migration and onboarding.
- SMS or other paid communication usage.
- Premium modules.
- Additional storage or branch support.

Before fixing prices, interview proprietors and understand willingness to pay, current spending, school size, payment cycles and support expectations.

## 11. Differentiation and product principles

- <b>Simple:</b> Designed for staff who may not be highly technical.
- <b>Mobile-first:</b> Core workflows work well on phones and computers.
- <b>Affordable:</b> Practical for smaller private schools.
- <b>Connected:</b> Avoid separate tools for basic operations.
- <b>Configurable:</b> Support differences in school structure, terms, grading and fees.
- <b>Secure:</b> Enforce school, role and family data boundaries.
- <b>Reliable:</b> Protect records, provide backups and dependable critical workflows.
- <b>Locally relevant:</b> Reflect Nigerian school calendars, fee practices, school levels and payment realities.
- <b>Accessible:</b> Browser-based access; do not require every parent or teacher to install an app.

## 12. Risks and questions to validate

### Adoption risks

- Proprietors may prefer existing manual processes.
- Teachers may resist extra data entry.
- Some parents may have limited data access or digital confidence.
- Schools may need help migrating years of paper records.
- Internet connectivity may be unreliable.
- Schools may expect extensive training and ongoing support.

### Product and operational risks

- Cross-tenant data exposure.
- Incorrect grades or fee balances.
- Unauthorised changes to results or financial records.
- Data loss or poor backup recovery.
- Notification and payment provider costs.
- Scope becoming too broad before the core product is proven.
- Privacy and child-data protection obligations.

### School discovery questions

1. How does the school currently store student records?
2. How are attendance and results recorded?
3. Who calculates and approves report cards?
4. How are fees billed, paid, receipted and reconciled?
5. What information do parents request most often?
6. Which tools are currently used: paper, Excel, WhatsApp or existing software?
7. What are the most time-consuming administrative tasks?
8. Who would approve and pay for software?
9. How many students, teachers, classes and branches does the school have?
10. What would prevent adoption?
11. What is the school willing to pay, and how would it prefer to pay?
12. Would the school participate in a pilot and provide feedback?

## 13. Pilot and validation plan

Before building every module:

- Interview 5–10 proprietors or school administrators.
- Observe how at least 2–3 schools handle admissions, student records, attendance, results and fees.
- Identify the three most painful workflows.
- Select 2–3 pilot schools with different sizes or operating styles.
- Test core workflows with real users and permission boundaries.
- Measure time saved, errors reduced, parent usage and willingness to pay.
- Collect feedback from proprietors, teachers, bursars and parents.
- Revise scope before expanding.

### Suggested pilot success measures

- Time required to register and set up a school.
- Percentage of student records successfully migrated.
- Teacher attendance and result-submission completion.
- Time required to generate and publish report cards.
- Accuracy of fee balances and payment records.
- Parent account activation and repeat usage.
- Number of support requests and resolution time.
- Pilot-school willingness to continue on a paid plan.

Set targets after baseline measurements rather than inventing them in advance.

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

## 15. Naming and brand direction

<b>ACADIVA</b> is the preferred working name at this stage because it is simple, approachable and broad enough to cover administration, academics, finance and communication.

The name and domain have not been legally or commercially cleared in this document. Domain availability should be rechecked with a registrar or relevant registry before registration. ACADIVA should not be positioned as only a learning app; its scope is the operation of the whole school.

## 16. Current decisions, proposals and open items

### Direction established in the product discussion

- Build an all-in-one school management system.
- Start with Nigerian schools, especially local and independent private schools.
- Support nursery/kindergarten, primary, junior secondary and senior secondary contexts.
- Provide separate portals and permissions for school staff, teachers, parents and other roles.
- Give each school its own branded subdomain.
- Use shared platform infrastructure with strict separation of each school's data.
- Include student records, academics, fees, parent access and school communication in the product vision.

### Proposed, not yet validated

- Exact launch feature set and phase boundaries.
- Subscription tiers and example prices.
- Payment gateway and notification providers.
- Full HR, payroll, accounting, transport, library and inventory scope.
- AI capabilities.
- Final technical architecture and database design.
- Final domain, brand identity and legal clearance.

### Immediate next actions

- [ ] Interview school proprietors and administrators.
- [ ] Document current admissions, student records, attendance, results and fee workflows.
- [ ] Identify pilot schools.
- [ ] Confirm the MVP feature list.
- [ ] Define detailed user roles and permission matrix.
- [ ] Design tenant and data-isolation architecture.
- [ ] Map main screens and user journeys.
- [ ] Validate pricing and onboarding needs.
- [ ] Create a pilot implementation and feedback plan.

## Product summary

ACADIVA aims to become the digital operating system for schools — connecting the people, records, academic work, money and communication needed to run a school in one secure platform.

## 17. Student promotion and class progression

<b>Core requirement:</b> At the end of an academic session, students should normally move automatically to the next class. Teachers should not have to manually promote every student one by one.

### Automatic promotion workflow

1. The school closes the final term and confirms that all required results are submitted.
2. ACADIVA calculates each student's overall performance using the school's configured assessment weights and grading rules.
3. The system checks the student's result against the school's promotion benchmark and any configured subject-level requirements.
4. Students who meet the promotion criteria are placed on the proposed promotion list for the next class.
5. Students below the benchmark are flagged for review and are not automatically promoted.
6. The class teacher can recommend promotion or retention and must provide a reason for an exception.
7. The principal or authorised academic administrator reviews exceptions and approves the final promotion list.
8. Once approved, ACADIVA moves the students into the next academic session and class while preserving their previous class and result history.

### Promotion rules and safeguards

- Each school sets its own pass mark, overall promotion benchmark and any mandatory subject requirements.
- The system must not assume one national benchmark for every school.
- The benchmark may use an overall average, minimum subject grades, or a combination configured by the school.
- A student with incomplete or unapproved results must be flagged rather than promoted automatically.
- A student below the benchmark should be held for teacher/principal review, not silently moved forward.
- An authorised teacher may recommend an exception, but the decision and reason must be recorded; schools may require principal approval.
- Administrators can correct a promotion before finalisation, with an audit trail.
- Promotion should be run as a preview first. The school confirms the list before changes become final.
- Students in the final class of a school level should be marked as completed/graduated or transferred according to the school's setup, not assigned to a nonexistent next class.

### Example

If a school sets a promotion benchmark of 50%:

- Student with 68% and all required subjects passed: eligible for automatic promotion.
- Student with 42%: flagged for review and not automatically promoted.
- Student with missing examination scores: held as incomplete until the school resolves the result.

The 50% example is illustrative only. Every school configures its own rules.

## 18. Student performance intelligence and special features

ACADIVA should help schools identify students who are thriving, students who need support, and students whose attendance or performance is changing. The aim is early support and better teaching decisions, not labelling or shaming children.

### 18.1 High-performing students

- Identify students performing above the school's configured excellence threshold.
- Show subject strengths and consistent high performance across terms.
- Recognise class and subject top performers.
- Identify students who have improved significantly, not only those with the highest scores.
- Produce a school-approved excellence or merit list.
- Allow schools to record awards, commendations and academic distinctions.
- Track high performance over time to distinguish consistent performance from a one-term result.

### 18.2 Students who need academic support

- Flag students below the school's configured performance benchmark.
- Identify subjects where a student is consistently struggling.
- Compare current results with the student's previous terms to detect a decline.
- Highlight missing assessments or repeated low scores.
- Allow teachers to add observations, support plans and follow-up dates.
- Track whether performance improves after intervention.
- Generate a private class support list for authorised teachers and school leaders.

Use respectful labels such as <b>Needs academic support</b>, <b>At risk of falling behind</b>, or <b>Improvement required</b>. Avoid public rankings or labels that embarrass students.

### 18.3 Improvement and progress tracking

- Most improved students by term or session.
- Students showing consistent progress.
- Students whose performance has dropped significantly.
- Subject-level class trends to show where teaching support may be needed.
- Compare a student's current performance with their own previous performance, not only with classmates.

### 18.4 Attendance and engagement indicators

- Frequent absence or lateness.
- Sudden changes in attendance.
- Students with repeated missed assessments.
- A combined view of attendance and academic changes to help staff investigate possible barriers.
- Configurable alerts to the relevant teacher or administrator.

Attendance or a single test score should not automatically determine a student's promotion or trigger a disciplinary decision. Staff must review context.

### 18.5 School leadership insights

- Class performance overview.
- Subject performance heatmap.
- Number and percentage of students above, meeting or below configured benchmarks.
- Students requiring follow-up by class.
- Top improvement areas and recurring weak subjects.
- Attendance trends by class and term.
- Comparison across terms and academic sessions.
- Private downloadable reports for school leadership and authorised teachers.

### 18.6 Parent-facing progress

- Parents see their own child's results, attendance and teacher-approved progress notes.
- Parents can receive supportive alerts when a child needs attention.
- Parents can see improvement over time and practical next steps shared by the school.
- Internal teacher notes, safeguarding notes and confidential staff discussions must never appear in the parent portal by default.

## 19. Future plans and strategic expansion

The long-term ambition is for ACADIVA to become core digital infrastructure for schools, not just a results and fee application.

### Future product opportunities

- Full school websites and online admissions for every tenant.
- Learning management: homework, lesson materials, assignments and learning resources.
- Online tests and examinations with controlled assessment workflows.
- Timetable generation and class scheduling.
- Digital student identity cards and QR-based verification.
- Parent-teacher meeting booking.
- School transport, route and pickup updates.
- Library, inventory, assets and school store management.
- Alumni and former-student records.
- Multi-branch and school-group management.
- School-to-school transfer records, with consent and appropriate verification.
- Scholarships, bursaries and fee-support administration.
- School marketplace for approved educational services and supplies, if demand supports it.
- Integrations with payment providers, accounting tools and approved education services.
- AI-assisted summaries and early-warning insights, always subject to human review.
- Offline-friendly teacher workflows for unreliable internet, with safe synchronisation when connectivity returns.

### Geographic expansion

Start with a small number of Nigerian pilot schools. Improve the product around their real workflows before expanding to more states and other African markets. Local grading, academic calendars, privacy requirements, currencies and payment methods must be configurable for each market.

## 20. ACADIVA Teacher Device Programme — sponsorship concept

A future sponsorship programme could help participating schools adopt ACADIVA by providing teachers with low-cost devices for daily use.

<b>Concept:</b> A sponsor, foundation, education partner or corporate social responsibility programme funds devices for teachers at selected schools. Teachers use the devices to take attendance, enter scores, access class lists, submit results and communicate through ACADIVA.

### Why this could matter

- Reduces the need for every teacher to own a personal laptop or tablet.
- Makes digital attendance and result entry practical during the school day.
- Helps schools move away from paper-based workflows.
- Improves teacher onboarding and consistent use of the platform.
- Gives sponsors a measurable education-access and digital-inclusion programme.

### Proposed implementation

- Begin with a small sponsored pilot at one or two schools.
- Estimate the number of teachers and devices required per school.
- Select durable, affordable devices with adequate battery life and reliable Wi-Fi.
- Provide protective cases, chargers and basic device support.
- Configure devices for school use, with appropriate account security and restricted access.
- Train teachers and provide a simple device-use guide.
- Assign each device to a teacher or classroom and maintain an asset register.
- Define responsibility for damage, loss, repairs, replacement and end-of-school-year handover.
- Track adoption through active teacher accounts, attendance completion and result-submission rates.

### iPad versus lower-cost tablet

The original idea is to provide each teacher with an affordable iPad. This should remain an option if a sponsor can supply refurbished or bulk-purchased iPads. However, iPads may not be the lowest-cost way to equip every teacher. ACADIVA should compare refurbished iPads with reliable entry-level Android tablets before making a procurement decision. Device choice should be based on durability, battery life, security updates, app/browser compatibility, repairability and total cost of ownership.

### Sponsorship model

- Sponsor funds devices for a defined number of teachers or schools.
- ACADIVA supplies the software, onboarding and usage reporting.
- Schools commit to using the system and maintaining assigned devices.
- Sponsor receives an agreed impact report, without access to private student records.
- Devices remain subject to a written ownership and handover agreement.

This programme is a future adoption accelerator, not a requirement for the initial launch. ACADIVA must still work on teachers' existing smartphones and school computers.

## 21. Subscription structure and pricing hypotheses

### 21.1 Monthly or per-term billing?

<b>Recommendation: Offer both, but make per-term billing the preferred school-facing option and keep monthly billing available.</b>

Why:

- Nigerian schools commonly organise budgets and fee collection around academic terms.
- A termly invoice is familiar to proprietors and may be easier to approve as part of a school's term expenses.
- ACADIVA's infrastructure costs occur every month, so termly payment should be collected in advance.
- Monthly billing gives schools with tighter cash flow a lower upfront commitment.
- Annual payment can be offered later with a modest discount once retention and support costs are understood.

Suggested billing choices:

- Monthly: pay at the start of each month.
- Per term: pay three months in advance, with a small discount compared with three separate monthly payments.
- Annual: optional later, after the product has a proven renewal history.

Do not make the term plan three months of free usage after a school stops paying. Define renewal dates, grace periods, read-only access and data export rules clearly.

### 21.2 Proposed student-count tiers

The following are starting hypotheses for customer testing, not final prices.

| Active student count | Proposed plan | Monthly equivalent | Per-term price |
| --- | --- | --- | --- |
| 0–50 | Starter / Free | ₦0 | ₦0 |
| 51–100 | Basic | ₦10,000 | ₦27,000 |
| 101–250 | Growth | To validate | To validate |
| 251–500 | Standard | To validate | To validate |
| 501–1,000 | Plus | To validate | To validate |
| 1,001+ | Custom | Quoted | Quoted |

The 0–50 free tier should be deliberately limited, not an unlimited free version of every feature.

Possible free-tier limits:

- Core student records.
- Basic class and teacher setup.
- Attendance and results for a small school.
- Basic parent result access.
- Limited file storage.
- A defined number of staff accounts.
- No included SMS credits.
- No premium website customisation.
- No paid payment-gateway features or advanced analytics.
- Standard self-service support rather than intensive onboarding.

The school should be able to upgrade without losing records. The free tier is an acquisition strategy and should be reviewed if support or infrastructure costs become too high.

### 21.3 Cost assumptions for a 51–100 student school

A school with 100 students may have approximately 5–10 teachers, a few administrators and parents/guardians accessing the portal. The exact number of accounts and traffic depends on how many parents activate accounts and how often the system is used.

The database itself is unlikely to be the expensive part at this size. The main cost is keeping a reliable production service online, backing up data, storing uploaded files and supporting users.

<b>Important architecture assumption:</b> All schools should share one properly isolated multi-tenant Supabase project initially. Do not create a separate Supabase database project for every school; each additional project can add compute cost. Enforce tenant isolation with database policies and server-side permissions.

### 21.4 Current public infrastructure price references

Prices below are USD list prices observed during this planning exercise. They can change and do not include exchange-rate movement, taxes, bank/card charges, domain registration, SMS, payment processing, support labour or device costs.

| Service | Practical starting choice | Public list price | Planning note |
| --- | --- | --- | --- |
| Supabase | Free for development/pilot only | \$0 | 500 MB database, 1 GB file storage and 5 GB egress; projects can pause after inactivity and backups are limited |
| Supabase | Pro for production | From \$25/month | Includes 8 GB database disk, 100 GB file storage, 250 GB egress and daily backups; includes compute credits for one Micro instance |
| Netlify | Free hosting | \$0 | 300 usage credits/month; monitor production deploys, bandwidth and requests |
| Netlify | Personal | \$9/month | 1,000 monthly credits |
| Netlify | Pro | From \$20/month | Team features and higher included credits |
| Vercel | Hobby | \$0 | Personal/non-commercial use; not the plan to rely on for a commercial SaaS |
| Vercel | Pro | \$20/month | Commercial plan with \$20 included usage credit; usage and seats can affect total cost |

Official references:

- Supabase pricing: [https://supabase.com/pricing](https://supabase.com/pricing)
- Supabase billing and project compute: [https://supabase.com/docs/guides/platform/billing-on-supabase](https://supabase.com/docs/guides/platform/billing-on-supabase)
- Netlify pricing: [https://www.netlify.com/pricing/](https://www.netlify.com/pricing/)
- Vercel pricing: [https://vercel.com/pricing](https://vercel.com/pricing)

### 21.5 Lean infrastructure budget

<b>Recommended early production setup:</b> One shared Supabase Pro organisation/project for the multi-tenant application, with Netlify Free hosting initially, provided usage remains within its credit allowance and the team accepts its operational limits.

| Item | Monthly estimate |
| --- | --- |
| Supabase Pro | \$25 |
| Netlify Free | \$0 |
| Vercel | \$0 — not needed if Netlify is selected |
| Domain | Separate annual cost |
| SMS/email/payment fees | Usage-based; not included |
| Total base platform estimate | <b>About \$25/month</b> |

For comparison, choosing Vercel Pro instead of Netlify Free would make the base estimate about \$45/month before any additional usage. There is no need to pay for both Netlify Pro and Vercel Pro to host the same initial application. Choose one hosting provider.

For rough Nigerian budgeting only, using an illustrative planning exchange rate of ₦1,500 per US dollar:

- \$25/month ≈ ₦37,500/month.
- \$45/month ≈ ₦67,500/month.

This is a budgeting assumption, not a live FX quote. The actual naira debit will depend on the exchange rate, card/bank charges and applicable taxes.

### 21.6 Is ₦10,000/month viable for 51–100 students?

At the illustrative ₦1,500/USD planning rate:

- One school paying ₦10,000/month contributes about \$6.67/month.
- Four schools contribute ₦40,000/month, still only slightly above a \$25 base infrastructure bill before support and other costs.
- Ten schools contribute ₦100,000/month, approximately \$66.67 before expenses.
- Twenty schools contribute ₦200,000/month, approximately \$133.33 before expenses.

This is gross revenue, not profit. It excludes customer support, onboarding, backups beyond included quotas, file storage growth, communication, payment charges, taxes, domain renewals and the founder's time.

<b>Conclusion:</b> ₦10,000/month for 51–100 students is a plausible introductory price to test, but it is not comfortably profitable with only one or two paying schools. The business becomes more sustainable as multiple schools share the same platform infrastructure. Do not provision a separate paid database project for every school.

### 21.7 Cost-control rules

- Start with one shared multi-tenant production database, not one database project per school.
- Keep student photos and documents compressed and enforce file-size limits.
- Do not store unnecessary copies of videos or large media in the database.
- Use a single hosting provider at first.
- Keep free hosting only while its limits, terms and reliability are appropriate.
- Monitor database size, file storage, bandwidth, requests and backups monthly.
- Set spending alerts and caps where available.
- Avoid SMS as an unlimited included feature; sell message bundles or pass through usage costs.
- Do not add paid tools until a real school need justifies them.
- Keep a monthly per-school cost model and review it as active schools grow.

## 22. Decisions to confirm before launch

- [ ] Confirm whether 0–50 students is a permanent free tier or a limited pilot offer.
- [ ] Test ₦10,000/month and ₦27,000/term for 51–100 students with actual proprietors.
- [ ] Decide which features are included in the free plan.
- [ ] Confirm whether per-term billing is the default checkout option.
- [ ] Choose one production host: Netlify or Vercel.
- [ ] Confirm the shared Supabase multi-tenant architecture and tenant-isolation tests.
- [ ] Define the school's promotion benchmark and exception approval workflow.
- [ ] Decide which performance alerts appear to teachers, administrators and parents.
- [ ] Pilot student performance insights with teachers before exposing them to parents.
- [ ] Identify a potential sponsor and prepare a device pilot budget.
- [ ] Compare refurbished iPads with affordable Android tablets before procurement.

## 23. Parent notifications and school communication delivery

<b>Purpose:</b> Make ACADIVA the school's central, reliable communication system for parents, rather than relying entirely on manual WhatsApp messages or paper notices.

### 23.1 Notification channels

ACADIVA should support three complementary channels:

| Channel | Primary use | Initial priority |
| --- | --- | --- |
| In-app / parent portal | Routine updates, announcements, report availability, fee information and notification history | Core |
| Email | Formal, detailed and record-friendly communication, report availability, receipts, admission updates and PTA invitations | Core |
| SMS | Urgent or time-sensitive messages, and important alerts for parents who may not regularly access the portal or email | Later / usage-based |

The parent portal and email should form the foundation. SMS should be available for selected alerts and as a configurable fallback, because per-message charges can become significant across large schools.

Push notifications may be added when ACADIVA has native or installable app support and the technical approach is confirmed.

### 23.2 Example notification events

- An approved report card becomes available.
- A fee invoice is issued or a payment due date approaches.
- A payment is recorded and a receipt is available.
- A student is marked absent, subject to school-configured rules.
- A new school-wide or class-specific announcement is published.
- A PTA meeting, event or examination schedule is announced or changed.
- An admission application is received, updated or approved.
- An urgent school closure or safety-related notice is issued.

Schools should be able to choose which events trigger email, SMS or in-app notifications, subject to platform-level rules for critical messages.

### 23.3 Report-card notification workflow

When authorised school staff approve and publish results:

1. ACADIVA confirms that the result is approved and visible to the relevant parent.
2. It identifies the verified parent or guardian accounts linked to each student.
3. It creates an in-app notification for each eligible parent account.
4. It queues an individual email to each eligible recipient.
5. It includes a secure link to sign in and view or download the report; sensitive student results should not be exposed through public or guessable links.
6. It records the notification and email delivery outcome, including failures and retries.
7. It makes the report available in the parent portal regardless of whether the email is delivered.

Where one parent account is linked to multiple children, ACADIVA should preferably send one consolidated message listing the relevant children whose reports are ready, rather than sending several repetitive emails. Each child's report access must still be independently permission-checked.

### 23.4 Fee reminders and payment updates

ACADIVA should support configurable communication for:

- New fee invoices and fee schedules.
- Upcoming payment due dates.
- Outstanding balances and overdue fees.
- Part-payment acknowledgements.
- Successful payment confirmations.
- Receipt availability.
- Changes or corrections to a student's fee account.

Messages should show the school name, relevant fee description, amount and due date where appropriate, and direct parents to the authenticated portal for full details. Payment reminders must use the current verified balance and should not be sent for already settled or disputed items.

### 23.5 Bulk messaging to hundreds of parents

Bulk communication must be handled by a background queue, not by a teacher or administrator manually sending one message at a time.

For example, for a school with 500 parent recipients, ACADIVA should:

- Resolve recipients from verified parent-student relationships and the school's communication settings.
- Generate personalised messages individually.
- Queue messages in manageable batches and respect the email/SMS provider's rate limits.
- Retry temporary failures safely without creating duplicate notifications.
- Record queued, sent, delivered, bounced or failed status where the provider exposes those events.
- Show authorised school administrators a delivery summary and failed-recipient list.
- Keep a record of who initiated the campaign, its audience, content and time.

Never expose the recipient list to other parents. Do not use a single visible To/CC email containing hundreds of parent addresses. Use individual messages or a properly configured bulk transactional/campaign service.

### 23.6 Multiple children and duplicate-message handling

A parent may have more than one child enrolled in the same school. The system should group related routine updates where useful, such as a single email stating that reports are available for two or three linked children. It must not merge private records in a way that grants access to a child who is not verified as belonging to that parent.

Deduplication should prevent repeated messages caused by retries or repeated clicks. A notification should have a unique event/recipient identity so the same event is not sent twice unintentionally.

### 23.7 Parent notification preferences and school controls

- Parents can manage preferences for non-critical routine email notifications.
- Schools can configure the channels used for each event type.
- Critical or legally/operationally important school alerts may follow school policy and platform rules even when routine preferences are disabled.
- Parents can view a notification history in the portal.
- School administrators can review delivery status without seeing another school's data.
- Communication permissions must respect verified parent-student links and role-based access.
- ACADIVA should maintain consent, opt-out and suppression records where required by the chosen channel/provider and applicable rules.

### 23.8 Sender identity and email infrastructure

The proposed branded sender identity is [hello@edu.ng](mailto:hello@edu.ng), subject to confirming ownership and control of that domain. The product's final domain and sender-domain strategy remain to be confirmed.

Suggested role-based addresses, if the relevant domain is owned and configured:

- hello@... — general enquiries.
- notifications@... — automated parent and school updates.
- support@... — technical support.
- billing@... — ACADIVA subscription and billing communication.

ACADIVA should use a transactional email provider for automated messages rather than a personal Gmail account. Configure and verify SPF, DKIM and DMARC for the sending domain, monitor bounce and complaint rates, and keep transactional school messages separate from marketing campaigns.

The sender identity should make clear which school the message concerns, for example: “Bright Future Academy via ACADIVA”. A future option is a verified school-specific sender domain, but this should not be required for initial onboarding.

### 23.9 SMS provider and cost controls

SMS integration requires a suitable provider, sender-ID setup where supported, delivery-status handling, rate-limit management and a clear cost model. It may be technically straightforward to integrate, but availability, Nigerian network delivery, sender-ID approval, pricing and provider reliability must be checked before selecting one.

SMS should not be unlimited by default in low-cost school subscriptions. Options include school-funded message credits, prepaid bundles, usage-based billing or charging the school for messages beyond an included allowance. ACADIVA should show estimated or actual usage to authorised school administrators.

### 23.10 Privacy, security and audit requirements

- Never send one parent's personal or student information to another parent.
- Do not send sensitive results or personal records through unsecured public links.
- Authenticate and authorise access when a parent opens a report or invoice.
- Validate recipient identity and parent-student relationships before sending.
- Log message type, recipient, school, triggering event, initiating user, timestamps and delivery outcome.
- Restrict access to communication logs by role and tenant.
- Apply retention and deletion rules to message content and delivery metadata.
- Provide safe handling for bounced, invalid, opted-out or reassigned email addresses and phone numbers.

### 23.11 Initial implementation recommendation

For the first release, implement:

1. In-app notification records and a parent notification inbox.
2. Email notifications for report cards, fee invoices/reminders, receipts and important announcements.
3. A background email queue with retries, deduplication and delivery logs.
4. School-level templates and branding for messages.
5. Parent notification preferences for routine messages.
6. A basic administrator view of notification history and failures.

Add SMS after validating the provider, delivery reliability, sender-ID requirements and cost model. Keep the notification architecture channel-independent so SMS and push can be added without rebuilding the event system.

### 23.12 Decisions still to confirm

- [ ] Confirm the final sending domain and whether [hello@edu.ng](mailto:hello@edu.ng) is owned and available for use.
- [ ] Select an email provider and validate its Nigerian delivery, pricing and authentication requirements.
- [ ] Compare Nigerian SMS providers, sender-ID requirements, rates and delivery reporting.
- [ ] Decide which notifications are included in each school subscription and which are usage-based.
- [ ] Define which events are critical and whether SMS fallback is enabled.
- [ ] Confirm whether parents can opt out of each category of routine email.
- [ ] Define notification retention and school administrator access to delivery logs.

## 24. Teacher accounts, staff identity and class/subject assignments

<b>Purpose:</b> Give every teacher a secure, individual account and make the school—not the teacher or the platform—responsible for assigning teaching responsibilities.

### 24.1 Who creates and manages teacher assignments?

The principal, vice-principal/academic head or another school administrator explicitly authorised by the proprietor should manage teacher assignments. The exact permission should be configurable by each school.

Recommended responsibility split:

- Proprietor / school owner: appoints or approves senior staff and controls high-level access.
- Principal / academic head: oversees academic staffing, class allocation, subject allocation and timetable approval.
- Registrar / school administrator: creates staff records and manages invitations where authorised.
- Teacher: views assigned classes and subjects, records attendance and enters scores only for authorised classes/subjects.
- ACADIVA platform administrator: supports the platform but does not independently decide a school's academic staffing.

A school may delegate timetable preparation to a timetable officer or academic coordinator, while keeping final approval with the principal or designated school leader.

### 24.2 Permanent staff identity

Every staff member should receive a unique, system-generated Staff ID when their staff profile is created. Example: <code>MYE-BFA-0001</code> (illustrative format only).

The Staff ID is the stable internal identifier. It must not be the teacher's email address or phone number because either may change, be shared, become inaccessible or be reused.

Store separately:

- Staff ID.
- Full name and preferred display name.
- School/tenant identifier.
- Email address and verified status.
- Phone number and verified status.
- Employment status and dates.
- Role and permissions.
- Teaching qualifications and subjects, where supplied.
- Assigned classes, subjects and academic session.
- Account invitation and access status.

Staff IDs must be unique within the school or globally unique according to the final ID-generation design. They should not expose sensitive personal information.

### 24.3 Account invitation and sign-in

Recommended sign-in options:

- Continue with Google.
- Email and password.
- Secure account recovery.

Google sign-in should be convenient but not compulsory. The school creates or approves the staff profile and sends an invitation to the teacher's verified email address. Authentication proves control of the login account; it does not itself grant school access.

Before access is granted, ACADIVA must verify that the authenticated account is linked to an active staff profile in the correct school. A teacher must not gain access merely by signing in with any Google account.

If a teacher changes email address or phone number, the staff profile and Staff ID remain the same. The school should be able to update login credentials without creating a duplicate staff record. When employment ends, authorised staff should deactivate access while preserving the academic and audit history.

### 24.4 Teacher-to-class and teacher-to-subject assignment

Assignments should be made for a specific academic session and, where appropriate, term. The same teacher may teach multiple classes and multiple subjects. A class may have different teachers for each subject.

Example:

| Teacher | Class / stream | Subject |
| --- | --- | --- |
| Mr Ade | JSS 1A | Mathematics |
| Mr Ade | JSS 2B | Mathematics |
| Mrs Bello | JSS 1A | English Language |
| Mr James | SS 2 Science | Physics |

The assignment workflow:

1. The school creates its academic session, classes, arms/streams and subjects.
2. The school creates or imports staff profiles.
3. The principal or authorised academic administrator selects a teacher.
4. The administrator assigns one or more classes and subjects.
5. ACADIVA checks for missing or conflicting assignments and displays a confirmation summary.
6. The assignments become active after confirmation.
7. Teachers see their current teaching schedule, assigned class lists, attendance registers and result-entry responsibilities.
8. Changes are recorded with the user, date, reason and affected academic period.

The system should support class teachers/form teachers separately from subject teachers. A class teacher may have pastoral or administrative responsibility for a class without teaching every subject.

Teachers must only view and edit the records needed for their assigned responsibilities. A teacher's ability to enter results must be tied to an active class-subject assignment and the school's result-submission rules.

### 24.5 Assignment changes and continuity

- A teacher can be assigned to more than one class or subject.
- More than one teacher may share a subject or class responsibility if the school configures team teaching or split groups.
- Temporary substitutions should have start and end dates.
- A teacher transfer or departure should not erase historical assignments or submitted results.
- Changes after attendance or results have been entered must preserve the audit trail.
- ACADIVA should warn when a class has no assigned teacher for a required subject or a subject has no responsible teacher.

## 25. Timetable creation and conflict-free scheduling

<b>Purpose:</b> Help schools create practical class timetables, especially junior and senior secondary timetables where different subject teachers move between classes and one teacher may teach several streams.

### 25.1 Timetable model

The timetable must not assume that one teacher teaches an entire class for the whole day. It should schedule individual lessons by class/stream, subject, teacher, period and (where applicable) room.

A timetable entry should contain:

- Academic session and term.
- Day of week.
- Period and start/end time.
- Class and arm/stream (for example JSS 2A or SS 2 Science).
- Subject.
- Assigned teacher.
- Room or laboratory, if applicable.
- Lesson duration and weekly frequency.
- Any special group or split-class information.

### 25.2 School configuration

Before generating a timetable, an authorised administrator configures:

- School days and operating hours.
- Period count and period duration.
- Breaks, assembly, lunch and closing time.
- Class/stream structure.
- Subjects offered to each class.
- Required weekly periods for each subject.
- Teacher assignments and teacher availability.
- Rooms, laboratories and specialist facilities.
- Fixed activities and protected periods.
- Double periods or consecutive periods where a subject requires them.

Different schools must be able to use different period lengths, school days and timetable structures.

### 25.3 Automatic timetable generation

ACADIVA should provide an automatic timetable builder that attempts to schedule all required lessons while avoiding conflicts.

The scheduling engine should enforce these hard constraints:

- A teacher cannot be assigned to two classes in the same period.
- A class cannot have two lessons in the same period.
- A room or laboratory cannot be double-booked.
- A teacher can only be scheduled for subjects and classes they are authorised to teach.
- Lessons must fit within the school's configured operating hours.
- Required breaks and fixed activities must be respected.
- Weekly subject-period requirements should be met or clearly reported as unmet.

Soft preferences may include teacher preferred periods, balanced subject distribution, avoiding too many demanding subjects consecutively, room proximity and fair distribution of workload. Schools should be able to configure which preferences matter.

### 25.4 Review, explain and approve

The timetable generator should not silently publish a flawed timetable. It should:

1. Generate a proposed timetable.
2. Identify unresolved lessons and constraints that could not be satisfied.
3. Explain conflicts in plain language.
4. Allow an authorised timetable officer to adjust lessons manually.
5. Re-check the entire timetable after changes.
6. Show class, teacher and room timetable views.
7. Allow the principal or authorised academic head to approve and publish it.
8. Notify affected teachers and, where appropriate, parents/students when a published timetable changes.

A timetable should have draft, approved/published and archived states. Changes after publication should be versioned and auditable.

### 25.5 Views and exports

- Whole-school timetable.
- Individual class/stream timetable.
- Individual teacher timetable.
- Room and laboratory timetable.
- Printable PDF timetable.
- Parent/student timetable view where enabled.
- Downloadable or shareable timetable formats, subject to permissions.

### 25.6 Secondary-school examples and edge cases

ACADIVA must support JSS and SSS structures in which:

- Mathematics, English, sciences, arts and vocational subjects have different teachers.
- Teachers move between JSS 1A, JSS 1B, JSS 2 and senior classes.
- Science practicals require laboratories.
- Some subjects are taught to selected streams or option groups.
- Students in the same year may take different elective subject combinations.
- A teacher may teach a subject across several year groups.
- Some schools use double periods for practical or specialist lessons.

The data model should therefore support subject groups and elective combinations, not only a simple one-class/one-teacher arrangement.

### 25.7 Timetable MVP recommendation

For the first timetable release, build:

- Manual timetable entry and editing.
- Teacher, class and room conflict detection.
- Teacher and class timetable views.
- Printable PDF export.
- Draft and approval workflow.

Add automatic timetable generation after the school structure, subject requirements and conflict rules have been validated with real schools. A reliable conflict checker is more valuable initially than an automatic generator that produces unusable schedules.

## 26. Future investment, teacher device programme and adoption strategy

<b>Status:</b> Long-term strategic proposal, not a committed launch requirement or confirmed funding plan.

### 26.1 Strategic idea

ACADIVA may pursue grants, education-focused investors, corporate social responsibility (CSR) partners, foundations, device manufacturers and other sponsors to support school digitisation and teacher access to suitable devices.

One possible programme is to provide participating teachers with affordable tablets configured for ACADIVA and approved school work. This could reduce the device barrier for schools whose teachers do not have reliable smartphones or computers, improve adoption and make digital school administration more practical.

The programme should be treated as a potential adoption and access initiative—not a promise that every teacher will receive a device at launch.

### 26.2 Device programme design

A pilot could:

- Select a small number of partner schools.
- Identify teachers who genuinely lack suitable devices.
- Compare low-cost Android tablets with refurbished or entry-level iPads on total cost, durability, repairability, battery life, compatibility and availability.
- Procure devices, protective cases, chargers and any necessary connectivity.
- Configure devices with ACADIVA and approved school applications.
- Provide onboarding, training and technical support.
- Maintain a device asset register recording serial number, school, assigned staff member, condition and handover date.
- Define ownership, return, repair, loss, replacement and end-of-employment policies.
- Measure device usage, teacher adoption, attendance/result-entry completion and administrative time saved.

The device programme must not make ACADIVA unusable for teachers who bring their own phones or use school computers. The core product must remain responsive on ordinary Android phones, iPhones and desktop browsers.

### 26.3 Dedicated ACADIVA staff experience

The preferred concept is a low-cost, school-managed device with a simple staff-focused experience:

- ACADIVA opens directly or is easy to access.
- Teachers sign in using their own individual accounts.
- Access is restricted by the teacher's role and school assignments.
- School administrators can manage access and remove school data when a device is returned.
- Devices receive security updates and have screen locks.
- Personal data and personal accounts are not unnecessarily exposed to school administrators.

The preferred future concept is not a second general-purpose Android phone for teachers. It is a low-cost, school-use Android tablet configured as a restricted ACADIVA Teacher Pad. Teachers already have personal phones; the dedicated tablet should provide a consistent school-work terminal rather than duplicate personal entertainment or unrestricted phone use.\\n\\nThe intended experience is limited to:\\n\\n- ACADIVA Teacher Workspace.\\n- Playback of school-approved educational videos.\\n- A small allowlist of approved educational apps and resources.\\n- School documents and PDFs.\\n- Essential device controls such as Wi-Fi, brightness and volume, without unrestricted access to device settings.\\n\\nThe device should block games, social media, personal entertainment, unrestricted browsing, open Play Store access and unauthorised app installation. This should be enforced through genuine Android Enterprise fully managed / dedicated-device multi-app kiosk management, app allowlisting and controlled settings—not merely by hiding icons. The exact model must be checked for Android Enterprise compatibility and tested for configuration bypasses before procurement. Do not describe the device as tamper-proof.\\n\\nA planning target of approximately ₦100,000 per tablet has been proposed by the founder. This is an unvalidated target budget, not a confirmed supplier price or approved procurement commitment. Prioritise a pilot purchase and compatibility test before any bulk order.\\n\\nAvoid custom hardware or a proprietary Android operating system in the early stages; use a compatible off-the-shelf device with managed configuration. Teachers must still be able to use ACADIVA on their own phones and school computers, and a tablet must never be a condition of using the platform.

### 26.4 Investment and sponsorship proposition

Potential funding routes:

- Education technology and digital inclusion grants.
- CSR partnerships with banks, telecom operators and technology companies.
- Foundations supporting teacher development and school access.
- Strategic partnerships with tablet/device distributors.
- Angel investment and education-focused venture capital.
- School-paid device leasing or instalment programmes at a later stage.

A sponsor proposition should explain:

- The problem: teachers and schools may lack affordable digital tools.
- The intervention: devices, software access, onboarding and support.
- The measurable outcomes: teacher adoption, faster result processing, improved parent communication and reduced manual administration.
- The programme cost per teacher and per school.
- Device lifetime, repair and replacement assumptions.
- Safeguards protecting student information and school records.

Sponsor reporting should use aggregated programme metrics. Sponsors must not receive private student records or unrestricted access to school accounts.

### 26.5 Investment readiness and use of funds

If ACADIVA approaches investors, grants or sponsors, the funding plan should connect each requested amount to measurable milestones. Potential use-of-funds categories include:

- Product engineering and security.
- School onboarding and customer support.
- Data protection, legal and compliance work.
- Hosting, backups, monitoring and reliability.
- Teacher training and implementation.
- Pilot devices and device maintenance.
- School acquisition and partnerships.
- Research and product validation.

The company should validate demand and demonstrate usage before committing to large-scale device procurement. A pilot should establish whether device access materially increases teacher adoption and school retention compared with ordinary bring-your-own-device access.

### 26.6 Adoption proposition for school proprietors

A device programme could be a strong differentiator, especially for schools with limited technology budgets. However, it should not be marketed as guaranteed free tablets for every teacher until funding, eligibility, ownership and sustainability are secured.

The stronger long-term proposition is that ACADIVA helps a school digitise its operations and can potentially help it access the devices, training and support needed to make that transition. The school management system must deliver value on its own; device sponsorship should accelerate adoption rather than be the only reason a school subscribes.

### 26.7 Pilot success measures

- Percentage of assigned teachers who activate accounts.
- Weekly active teacher usage.
- Attendance records completed on time.
- Results submitted and approved on time.
- Parent account activation and notification engagement.
- Reduction in time spent preparing report cards and compiling records.
- Device uptime, repair rate and loss rate.
- School renewal and retention.
- Cost per activated teacher and cost per retained school.

### 26.8 Open decisions

- [ ] Decide which school role can create staff profiles and invite teachers.
- [ ] Decide whether Staff IDs are globally unique or unique within each school.
- [ ] Confirm Google sign-in and email/password as the initial authentication options.
- [ ] Define whether the principal, vice-principal or delegated academic administrator approves teacher assignments.
- [ ] Validate the timetable requirements with nursery/primary, JSS and SSS schools separately.
- [ ] Decide which timetable features belong in the first release.
- [ ] Run a small device pilot before proposing a large teacher tablet programme.
- [ ] Compare affordable Android tablets and iPads using total cost of ownership.
- [ ] Define whether sponsored devices are owned by the school, ACADIVA programme or another sponsor.
- [ ] Prepare a measurable grant/CSR/investment proposal only after pilot costs and outcomes are known.

## 27. Unified ACADIVA platform with role-specific workspaces

<b>Status:</b> Agreed product direction. ACADIVA will use one unified application and underlying platform, with separate role-specific experiences and permissions for each user type.

### 27.1 Core product decision

ACADIVA should not become a collection of disconnected applications for proprietors, principals, teachers, parents and students. It should be one platform with a shared school data model, shared identity and access infrastructure, and distinct workspaces tailored to each role.

The guiding principle is:

<b>One ACADIVA. Different workspaces. Role-based access.</b>

Users sign in through the same ACADIVA entry point (with school-specific branding and portal routing where appropriate). After authentication, ACADIVA identifies their active school membership, role and permissions, then opens the appropriate workspace.

The workspace is a user experience and navigation boundary—not a separate database or a security boundary by itself. Every data request must still enforce school tenant isolation and server-side authorisation.

### 27.2 Role-specific workspaces

| Workspace | Primary purpose | Typical capabilities |
| --- | --- | --- |
| Proprietor / Owner | Whole-school oversight and governance | School performance, enrolment, finances, fees, staff overview, reports, branches, subscriptions and high-level settings |
| Principal / Head teacher | School leadership and daily management | Academic oversight, staff supervision, attendance overview, results approval, timetable approval, announcements and school operations |
| Administrator / Registrar | Administrative execution | Admissions, student profiles, class lists, staff records where authorised, parent linking, documents, records and communications |
| Teacher | Teaching and student support | Assigned classes and subjects, personal timetable, attendance, assessments, score entry, result submission, class lists and authorised student progress |
| Bursar / Accountant | Financial administration | Fee structures, invoices, payment records, receipts, balances, expenses and financial reports according to permissions |
| Parent / Guardian | Information about linked children | Children's results, attendance, fees, receipts, announcements, timetable and school communication |
| Student | Age-appropriate student information | Personal timetable, learning resources, homework, assignments, results and notices where the school enables student access |
| Platform administrator | ACADIVA platform operations | Tenant provisioning, subscription support, platform configuration, technical support and security operations; no routine unrestricted access to school content |

A school may combine responsibilities in a small team. For example, the proprietor may also act as principal, or an administrator may handle registrar duties. ACADIVA should allow authorised users to hold more than one role without requiring duplicate accounts.

### 27.3 Authentication, school membership and permissions

Authentication and authorisation must remain separate.

1. A user signs in using an enabled method such as Google or email and password.
2. ACADIVA identifies the authenticated account.
3. ACADIVA checks the user's active membership in the relevant school tenant.
4. ACADIVA loads the roles and specific permissions granted by that school.
5. ACADIVA opens the appropriate workspace and limits available actions and records.
6. Every server-side request independently checks tenant membership, role and resource-level permission.

A successful Google login must never, by itself, grant access to a school. Parents must only access children whose parent/guardian relationship has been verified and linked by the school. Teachers must only access classes, subjects and student records within their authorised assignments. Financial records must be restricted to authorised financial and leadership roles.

### 27.4 Multiple roles and multiple schools

The same person may hold more than one role in a school, such as proprietor and principal, or teacher and class teacher. ACADIVA should present the functions they are authorised to perform without duplicating their identity or creating conflicting staff records.

A person may also have legitimate memberships in more than one school. The user should be able to select the active school context where necessary. Switching schools must switch the tenant context and permissions; it must never expose records from the previous school in the new context.

Parent accounts may be linked to more than one child and, where relevant, children attending different schools. Each child's access must remain separately verified and scoped to the relevant school.

### 27.5 Teacher Workspace — core product experience

The Teacher Workspace is a core part of ACADIVA, not an optional add-on or a separate application in the initial architecture.

It should be simpler and more task-focused than the proprietor or principal workspace. A teacher should immediately understand what they teach, where they need to be, which academic tasks are pending and which student records they are authorised to manage.

Recommended dashboard elements:

- Greeting, school identity and current academic session/term.
- Today's lessons and personal timetable.
- Assigned classes, arms/streams and subjects.
- Attendance tasks and recent attendance records.
- Pending continuous assessment and examination score entry.
- Results awaiting completion or submission.
- Class lists and authorised student profiles.
- School announcements and relevant notifications.
- Quick access to timetable, attendance, results and teaching resources.

The Teacher Workspace should work well on ordinary Android phones, iPhones, tablets and desktop browsers. A sponsored tablet must not be required to use ACADIVA.

### 27.6 Workspace navigation and interface principles

- Each role should see a focused home dashboard with the most relevant tasks and information.
- Navigation should hide functions the user cannot access; hiding a menu item is not a substitute for server-side permission checks.
- The same underlying record should be presented differently where roles have different responsibilities. For example, a teacher sees the students they teach, while a principal may see school-wide academic summaries.
- Users with multiple roles should have a clear and auditable way to switch workspace or role context.
- School branding should be consistent across the school's workspaces without compromising ACADIVA's shared platform identity.
- Interfaces should be responsive, accessible and usable by staff with varying levels of digital confidence.
- High-impact actions—publishing results, changing staff assignments, approving timetables, changing fee structures or deactivating accounts—should require the appropriate permission and leave an audit record.

### 27.7 Relationship to the teacher device programme

The teacher tablet initiative should support the Teacher Workspace rather than create a separate teacher product.

Devices may be configured to open ACADIVA quickly and provide a school-managed, staff-focused experience. Teachers still use their individual accounts and permissions. Device management must not replace identity checks or tenant-level authorisation.

The same Teacher Workspace must remain available on a teacher's own device. Schools should be able to adopt ACADIVA without buying tablets.

### 27.8 Recommended implementation sequence

1. Establish shared identity, school membership, tenant context and server-side role/permission enforcement.
2. Build the Proprietor and Principal experiences needed to configure and oversee the school.
3. Build the Administrator and Teacher workspaces, including staff assignments, attendance, results and timetable access.
4. Build the Parent workspace with verified parent-child linking and secure access to records.
5. Introduce the Student workspace when the relevant learning and student-facing features are ready.
6. Add permission configuration, multiple-role switching and multi-school membership with auditability.
7. Validate the experience with real schools and different user types before expanding the workspace feature set.

### 27.9 Product and security requirements

- One shared platform and tenant-aware data architecture; do not create a separate application or database for every role.
- Enforce tenant isolation in the database and server-side services.
- Apply least-privilege access by default.
- Use explicit permissions for sensitive operations rather than relying only on broad role names.
- Keep parent-child relationships school-verified and auditable.
- Preserve staff, student, financial and academic history when accounts or memberships are deactivated.
- Log sensitive actions and permission changes.
- Provide secure session handling and account recovery.
- Do not expose private student or school information to sponsors, device partners or other schools.
- Ensure workspace switching cannot be used to bypass tenant or role checks.

### 27.10 Decision record

<b>Agreed:</b> Option C — one ACADIVA application with separate experiences for Proprietor, Principal, Administrator, Teacher, Parent and Student, supported by role-based access and a shared underlying platform.

<b>Rationale:</b> This provides a consistent product and infrastructure while keeping each user's experience focused. It avoids the maintenance and data fragmentation of separate applications and supports schools where one person holds multiple responsibilities.

<b>Not implied by this decision:</b> Every role-specific feature must be built in the first release. Workspace structure is the product direction; implementation should still be phased according to the MVP and validated school needs.

## 28. School finance, fee collection, payment tracking and announcements

<b>Status:</b> Agreed product direction for the ACADIVA finance and communication modules. Initial scope is school fee administration, payment visibility, basic budgeting and school announcements—not a full accounting or payroll system.

### 28.1 Product objective

ACADIVA should give a school a reliable, current picture of what it has billed, what it has collected, who has paid, who has paid partially, who has not paid, and what remains outstanding.

The financial system should reduce manual reconciliation, fee-record disputes, forgotten reminders and uncertainty about the school's cash position.

The core promise is: an authorised school user can open a class, student or school-wide finance view and understand the position without manually combining notebooks, spreadsheets and bank alerts.

### 28.2 Scope boundary: what ACADIVA will and will not manage

Initial finance scope:

- School fee structures and fee categories.
- Student bills and invoices by session and term.
- Discounts, scholarships, waivers and approved adjustments.
- Individual student fee accounts and payment history.
- Payment recording, verification and allocation.
- Receipts and payment references.
- Class-level and school-wide collection summaries.
- Outstanding balances and overdue accounts.
- Basic income, expense and budget tracking.
- Financial reports and exports.
- Audit history for sensitive financial actions.

Explicitly outside the initial scope:

- Teacher and staff payroll.
- Salary calculations, pension, PAYE and other payroll deductions.
- Complex double-entry accounting.
- Tax filing and statutory financial statements.
- School lending, credit or rent-financing products.
- ACADIVA holding or pooling school fee money in its own bank account.

ACADIVA should solve the everyday fee and basic budget problems first. It should not claim to replace a professional accounting package.

### 28.3 Fee structures and billing

An authorised finance administrator should configure fees for each academic session and term. Fees may be assigned by class, arm, student or selected group.

Each fee item should support:

- Name and category, such as tuition, development levy, books, examination, PTA levy, transport or other school-defined charges.
- Amount and currency.
- Academic session and term.
- Applicable class, arm, student or group.
- Compulsory or optional status.
- Due date and payment schedule.
- Instalment eligibility.
- Discount, scholarship or waiver rules.
- Whether the fee is recurring or one-off.
- Whether it is visible to parents in the portal.

The system should calculate each student's actual amount due after approved discounts, waivers and adjustments. It must preserve the original billed amount and the reason, author and date of every change.

A school should be able to issue bills in bulk to a class, selected classes or the entire school, then review the billing preview before publishing.

### 28.4 Student financial account and ledger

Every student should have a financial account for each relevant session and term.

The account should show:

- Total fees billed.
- Discounts, scholarships and waivers.
- Total confirmed payments.
- Pending or unverified payments, shown separately.
- Refunds and reversals.
- Outstanding balance.
- Due dates and overdue status.
- Payment allocation across fee items.
- Receipts and transaction references.
- Full chronological history.

The ledger must preserve the history of financial events. A payment should not simply be deleted or silently overwritten. Corrections should be recorded as reversals, adjustments or reallocations with an authorised actor, timestamp and reason.

The system must support partial payments, instalments, overpayments, payments covering multiple fee items, sibling payments where correctly allocated, refunds, failed transactions, reversed transactions and disputed transfers.

A pending transfer or unverified cash entry must not be treated as confirmed collection. The system should distinguish billed, pending, confirmed, reversed/refunded and outstanding amounts.

### 28.5 Payment register and collection dashboard

The finance workspace should provide a searchable, filterable register of students and their payment positions.

Recommended columns:

| Student | Class/Arm | Amount billed | Confirmed paid | Outstanding | Status |
| --- | --- | --- | --- | --- | --- |
| Student A | Primary 1 | ₦65,000 | ₦65,000 | ₦0 | Paid |
| Student B | Primary 1 | ₦65,000 | ₦40,000 | ₦25,000 | Partial |
| Student C | Primary 1 | ₦65,000 | ₦0 | ₦65,000 | Unpaid |

The real interface must support search, class/arm filters, fee category, session, term, date range, payment method, due status, pagination and export to PDF or spreadsheet.

Summary cards should show paid, partially paid, unpaid, overdue and total billed amounts. Users should be able to drill down from school-wide totals to class totals and, where authorised, individual student accounts.

### 28.6 Class-level and school-wide financial visibility

ACADIVA should calculate class collection summaries automatically.

For example, an authorised user opening Primary 1 should see:

- Number of enrolled/billed students.
- Total amount billed to the class.
- Total confirmed collections.
- Total outstanding balance.
- Number fully paid.
- Number partially paid.
- Number unpaid.
- Collection percentage.
- Recent payment activity.

The same view should be available for other classes and the whole school, with comparisons across classes and terms.

Permissions must be configurable and least-privilege by default:

- Proprietor: school-wide financial overview and authorised detailed finance access.
- Principal: school-wide or delegated financial oversight according to school policy.
- Bursar/accountant: detailed bills, payments, reconciliation, receipts and reports.
- Administrator: only finance functions explicitly delegated.
- Teacher: no automatic access to family financial details. A school may grant a teacher access to class-level aggregate figures or selected payment-status information where there is a genuine operational need.
- Parent: only the bills, payments, receipts and balances of their verified linked child or children.
- Student: no financial access by default unless a school explicitly enables a limited age-appropriate view.

A user must never gain financial access merely by changing a URL, class ID or request parameter. Permissions must be enforced on the server and database, not only by hiding interface elements.

### 28.7 Payment recording and reconciliation

ACADIVA should support payment methods that schools already use:

- Bank transfer.
- Cash.
- POS.
- Online card or bank payment.
- USSD or other supported gateway methods.
- Other school-approved methods.

Manual payments should capture the amount, student, payer where known, date received, payment method, bank/reference details where available, recording staff member, verification state and receipt.

The system should support a pending verification workflow for transfers and other payments that cannot be confirmed automatically. Authorised finance staff can confirm or reject a pending entry with a reason.

Duplicate references and duplicate gateway events must not create duplicate credits. Daily or periodic reconciliation should compare ACADIVA's records with gateway settlements and school bank statements where available.

### 28.8 Payment gateway integrations and settlement model

Paystack is the preferred first provider to approach for a school-fee integration, with Flutterwave as a secondary provider to evaluate.

Paystack publicly offers a schools proposition and states a special Nigerian education-sector pricing arrangement: 0.7% capped at ₦1,500 for local card payments and a flat ₦300 for other local payment methods. This pricing and eligibility must be confirmed directly with Paystack before it is built into any school quotation. Paystack also advertises dedicated virtual accounts, subject to business eligibility and its terms.

Potential integration requirements:

- Hosted or tokenised checkout so ACADIVA does not store card details.
- Bank transfer, card and other supported payment methods.
- Transaction initialisation from a trusted server-side endpoint.
- Signed webhook verification.
- Server-side transaction verification, including amount, currency, reference and status.
- Idempotent processing so duplicate callbacks or webhook retries cannot credit a student twice.
- Refund, reversal, dispute and failed-payment handling.
- Parent payment reminders and finance notifications.
- Settlement reports and reconciliation.
- Clear mapping from gateway transaction to school, student, invoice and fee item.

Preferred settlement principle: school fees should settle directly to the school's own approved merchant/bank account wherever the provider's supported integration model allows. ACADIVA should not casually receive, pool, hold or redistribute school funds. Any platform/subaccount arrangement must be reviewed with the provider and appropriate legal/compliance advisers before implementation.

The payment gateway must be replaceable through a provider-independent internal payment interface. The fee ledger must remain ACADIVA's source of truth; it must not depend on one gateway's dashboard or database.

### 28.9 Immediate updates and real-time behaviour

When a payment is confirmed, ACADIVA should update the relevant student account, invoice balance, class collection summary, school-wide collection summary, receipt history and parent portal.

Use trusted server-side payment events and database transactions to update the ledger. The interface should refresh or receive a real-time update after the server confirms the change.

Do not mark a payment as successful merely because the parent returned to a success page, a browser callback fired, or a screenshot was uploaded. Gateway confirmation must be independently verified.

For manual bank transfers, the amount remains pending until an authorised school finance user confirms it or a supported bank/gateway integration confirms it.

### 28.10 Parent reminders and fee notifications

The system should support school-configurable reminders:

- Fee bill issued.
- Reminder before due date.
- Due-date reminder.
- Overdue reminder.
- Further escalation after a configured interval.
- Payment received and receipt issued.
- Balance updated after a payment or approved adjustment.

Channels may include parent portal/in-app notifications, email and optional SMS. SMS should be usage-based or funded by a school bundle rather than unlimited by default.

Before sending a reminder, ACADIVA must calculate the current verified balance and check for pending transfers, recent payments, discounts, waivers, disputes, refunds and account corrections. A reminder must not be sent for a settled account.

Messages should be individually addressed and must not expose other parents' contact details. Every attempted notification should have a record of recipient, event, channel, template, timestamp and delivery status where the provider makes it available.

An unpaid-balance flag must not automatically send a child home or make another consequential decision. ACADIVA can notify authorised staff and surface the school's policy, but decisions affecting a child's attendance require human review and appropriate school procedures. Payment delays, bank settlement delays and data-entry errors must be considered.

### 28.11 Basic school income, expense and budget tracking

ACADIVA should provide a simple financial overview without implementing payroll or full accounting.

Initial capability:

- Record other school income.
- Record operational expenses by school-defined category.
- Attach a receipt or supporting document where appropriate.
- Record date, amount, category, description, payee/vendor where relevant, payment method and staff member.
- Set simple budgets by term and expense category.
- Compare budgeted amount with actual recorded spending.
- Show total fee collections, other income, expenses and a basic operating position.
- Filter and export reports by session, term, date range and category.

Example categories may include utilities, electricity, water, rent, repairs, teaching materials, security, internet and transport.

The interface must distinguish money billed from money actually collected, and money collected from money available in the bank. Gateway fees, settlement timing, refunds, pending transfers and expenses affect the actual cash position.

This module is an operational cash and budget tracker, not a certified accounting ledger or statutory financial statement.

### 28.12 Financial reports

Recommended reports:

- Fee collection by school, class, arm, session and term.
- Paid, partially paid, unpaid and overdue student lists.
- Outstanding balance ageing.
- Payment history by student.
- Payment method breakdown.
- Daily, weekly and monthly collections.
- Discounts, scholarships and waivers.
- Refunds and reversals.
- Expense summary by category.
- Budget versus actual spending.
- Basic income and expenditure summary.
- Gateway settlement and reconciliation exceptions.

Reports must respect role permissions and should be exportable in suitable formats. Exports containing personal or financial information should be logged and access-controlled.

### 28.13 Announcements and communications register

ACADIVA should provide a dedicated Announcements & Communications workspace.

The announcement register should include:

| Field | Purpose |
| --- | --- |
| Title | Announcement title |
| Category | Academic, finance, event, emergency or general |
| Audience | All school, parents, teachers, students, selected classes or selected users |
| Channels | Portal, email, SMS or push where supported |
| Created by | Author |
| Created date | Creation timestamp |
| Publish time | Immediate or scheduled |
| Status | Draft, pending approval, scheduled, published or archived |
| Delivery summary | Sent, delivered, failed or unknown where provider data exists |
| Actions | View, edit, duplicate, cancel or archive |

Announcement creation should support title, message body, category, target audience, delivery channels, attachments, publish-now or schedule options, expiry date and optional principal approval.

Audience targeting must support all parents, selected classes/arms, selected students, all teachers, selected teachers, staff groups, students or the whole school.

The school should be able to preview the audience and message before sending. Large sends should use a queue, deduplication, rate limits, retries and delivery reporting. Parent email addresses must never be exposed in a shared To/CC list.

Distinguish announcements from automatic notifications. Announcements are messages deliberately published by the school, such as PTA meetings, school closures and examination timetables. Notifications are triggered by events, such as a result being approved, a payment being received or an attendance event.

### 28.14 Finance and communication MVP sequence

First release:

1. Fee categories and class/student billing.
2. Student fee accounts and a reliable payment ledger.
3. Manual payment entry and verification.
4. Payment register with class and school totals.
5. Receipts and payment history.
6. Outstanding balance and parent reminders.
7. Basic announcements register and publishing.
8. Basic collection and outstanding reports.
9. Role permissions and audit trail.

Next release:

- Paystack integration after provider approval and end-to-end testing.
- Optional Flutterwave integration.
- Automated transfer matching or dedicated virtual accounts where eligible.
- Expense recording and term budgets.
- Enhanced reconciliation and financial reports.
- SMS and additional communication channels.

Later:

- Deeper bank statement integrations.
- More advanced accounting integrations.
- Multi-branch consolidated finance.
- Advanced financial forecasting.

### 28.15 Open finance decisions

- [ ] Confirm the exact school roles that can view class totals and individual student payment status.
- [ ] Confirm whether a school may require principal approval for fee changes, discounts and waivers.
- [ ] Confirm the school's preferred policy for pending bank transfers and payment verification.
- [ ] Confirm how gateway charges are presented to parents or absorbed by schools.
- [ ] Discuss education-sector pricing, platform integration and school settlement architecture with Paystack.
- [ ] Evaluate Flutterwave as a second provider.
- [ ] Validate basic budget and expense categories with pilot schools.
- [ ] Validate reminder intervals and attendance-related fee policies with schools.
- [ ] Test payment reconciliation and duplicate-event handling before production launch.

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

## 30. Strategic collaboration and partnership map

<b>Status:</b> Target partner categories for research and outreach. No partnership is confirmed by inclusion in this list.

| Partner / organisation | Potential collaboration | Priority |
| --- | --- | --- |
| Paystack | School fee collections, payment API, education pricing, virtual accounts and platform integration discussion | High |
| Flutterwave | Alternative payment gateway and payment method coverage | High |
| Supabase | Database, authentication, storage and security infrastructure | Technical provider |
| Netlify | Web application hosting and deployment | Technical provider |
| Termii | OTPs, transactional SMS and parent reminders | High when SMS launches |
| Arkesel | Alternative SMS API and delivery reporting | Evaluate |
| Nigerian data protection professional / NDPC-recognised DPCO | Privacy review, data protection compliance and audit advice | High before scale |
| Independent cybersecurity firm | Security architecture review and penetration testing | Before significant scale |
| Tablet manufacturers and distributors | Future restricted Teacher Pad procurement, pilot devices and support | Future |
| Education foundations and CSR programmes | Teacher digitisation, school adoption and device pilot funding | Future |
| Banks and financial institutions | School collection workflows, settlement and possible statement integration | Later |
| School associations and proprietors' networks | Pilot access, feedback, trust and distribution | High |
| Teacher training organisations | Digital literacy, onboarding and teacher adoption | High |
| Email delivery provider | Transactional email, report cards, receipts and announcements | High |

Partnership outreach should distinguish a commercial integration, a vendor relationship, a pilot arrangement and a formal strategic partnership. Do not advertise any organisation as a partner until a written agreement or confirmed arrangement exists.

### 30.1 Paystack discussion points

Approach Paystack to discuss its school-specific proposition and whether ACADIVA can qualify for the education pricing arrangement. Confirm the exact fee schedule, applicable payment channels, eligibility, settlement arrangements, platform integration requirements, dedicated virtual account availability and any platform or subaccount model.

The preferred design is for each school to remain the owner/merchant of its fee collections and receive settlement into its approved account, where the provider supports this. ACADIVA should provide the software, payment mapping, records and reconciliation without unnecessarily becoming the custodian of school funds.

### 30.2 Partnership operating principles

- Keep the core ACADIVA product independent of any single vendor.
- Build replaceable payment, SMS and email integrations.
- Do not let a vendor access school or student data beyond the minimum required.
- Use written data-processing and service agreements where appropriate.
- Review vendor security and continuity.
- Keep a fallback for critical communication and payment workflows.
- Measure partner value through cost, reliability, delivery, support and school outcomes.

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

## 32. ACADIVA business model, revenue streams, school-wide licensing and messaging economics

<b>Status:</b> Product and commercial direction agreed for planning. Final prices, margins, provider rates and plan limits remain subject to validation with pilot schools and vendors.

### 32.1 Commercial principle

ACADIVA is a school-wide service purchased by the school, not a collection of individual teacher subscriptions. The school pays for the platform so its authorised proprietor, administrators, teachers, parents and (where enabled) students can use the relevant features.

The founder's commercial assumption is that a school paying teachers an average salary of approximately ₦50,000 per month should be able to budget for a useful school-management service that improves the work of the whole institution. This is a pricing hypothesis to validate with school owners; it is not a claim that every school has the same salary structure or ability to pay.

Teachers should not personally pay a subscription merely to perform duties assigned by their school. The school subscription should include the school's permitted teacher accounts and the parent accounts needed for its enrolled students, subject to fair-use and plan limits. ACADIVA may later offer optional personal teacher products with independent value, but those must not be required for ordinary school access.

### 32.2 Primary revenue: school subscriptions

The main recurring revenue should come from school subscriptions. Consider pricing by active enrolled student bands, with a minimum school subscription and clear included limits. This is easier to explain and scales more fairly than charging every teacher separately.

The plan should state:

- Maximum active students.
- Included teacher, admin and parent accounts.
- Included storage and document capacity.
- Included support and onboarding level.
- Included platform modules.
- Whether the public school website is included.
- Whether SMS credits are included or separately purchased.
- Any usage limits or paid add-ons.
- Billing period, renewal date, cancellation and data-export terms.

Evaluate monthly and per-term billing. Offer annual payment only if it improves cash flow and is attractive to schools. A per-term option fits school budgeting cycles; monthly billing lowers the entry barrier and provides predictable recurring revenue. The final plan should avoid charging a school twice for the same academic period and should explain how holidays, transfers and mid-term enrolment changes are handled.

An initial free tier for very small schools (the founder previously proposed 0–50 students) may help adoption, but must have strict limits on support, storage, SMS and costly add-ons. The boundary needs to be made unambiguous so a school with exactly 50 or 51 students is not confused. A free tier must not create unlimited human support or unlimited messaging costs.

### 32.3 Additional revenue streams

Subscription revenue should be the foundation, with optional add-ons that have clear value and transparent pricing.

| Revenue stream | Commercial model | Release priority |
| --- | --- | --- |
| School subscription | Monthly, per-term or annual school licence | Core |
| SMS credits | Prepaid wallet or metered usage with a disclosed margin | Early |
| Paid onboarding and data migration | One-time setup fee for schools needing hands-on assistance | Early, optional |
| Premium school website | Setup, custom domain and optional maintenance | Early/later |
| Online payment integration | Provider-approved platform fee or disclosed service charge only if contractually and legally permitted | After provider approval |
| Additional storage | Paid capacity above plan allowance | Later |
| Advanced analytics and reports | Higher subscription tier or optional module | Later |
| Admissions tools | Premium admissions workflows or agreed usage tier | Later |
| Multi-branch management | Higher-tier school/group subscription | Later |
| Training and support | Optional on-site training, implementation or premium support | Optional |
| Teacher Pad programme | Device margin, leasing/management fee or sponsored deployment model | Future |
| Third-party integrations | Premium connector or integration service where there is genuine incremental cost/value | Later |

Do not introduce advertising in sensitive school, student or parent experiences as an early revenue strategy. Do not sell student or parent data. Do not monetise access to children's personal information.

### 32.4 SMS and messaging economics

SMS is a variable cost and must not be advertised as unlimited unless the subscription price demonstrably covers the usage with a safe margin. The preferred design is a school-funded SMS wallet with transparent consumption.

The school is the customer responsible for operational SMS charges. Parents and teachers should not be individually billed by ACADIVA for school-directed messages.

#### First-time activation message

ACADIVA may fund one initial activation SMS for each newly invited user, subject to anti-abuse controls and a defined allowance. This is a customer-acquisition/onboarding cost borne by ACADIVA, not an unlimited lifetime free-message promise.

The activation SMS should contain:

- The school's name.
- A secure, expiring invitation or activation link, or a one-time setup code.
- A short instruction to activate the account.

Never send a permanent password in SMS. The recipient should create their own password or use an approved sign-in method such as Google. If an invitation is resent, the additional SMS is chargeable to the school's wallet or otherwise treated under the published invitation policy. Do not expose a password in a school-generated bulk spreadsheet.

#### Subsequent messages

Subsequent school-triggered SMS—fee reminders, announcements, timetable changes, result-ready alerts, OTPs and other notices—should be funded by the school through its SMS wallet or agreed messaging allowance.

The school should be able to:

- Buy prepaid SMS bundles.
- View its balance and transaction history.
- See message usage by category, class, recipient group and date.
- View sent, delivered, failed and unknown statuses where supported by the provider.
- Set low-balance alerts and authorised top-up permissions.
- Set per-campaign or daily sending limits.
- Choose which events are sent by SMS rather than in-app or email.
- Export a usage report and reconcile provider charges.

The wallet ledger should distinguish purchased credits, promotional credits, reserved credits, consumed messages, failed/refunded messages and manual adjustments. Failed delivery billing must follow the SMS provider's actual charging rules; do not automatically charge or refund based only on an assumed delivery status.

#### Channel priority

Use in-app notifications as the default low-cost channel wherever the user has an active account. Use email for routine notices and report-ready alerts where an address is available. Use SMS for time-sensitive or high-importance messages, users who are not active in the app, and cases where the school has selected SMS.

Avoid sending every announcement through every channel by default. Provide per-user preferences where appropriate and respect school policy and applicable consent/communication rules.

#### Security-message protection

Password recovery, account verification and security OTPs should not be silently disabled because the school's routine SMS wallet is empty. Define a controlled security-message reserve, rate limits, abuse detection and a fair usage policy. Where a security SMS cannot be sent, provide a safe alternative recovery channel without weakening authentication.

#### SMS pricing formula

Do not invent a selling price before obtaining current provider quotations and testing real message segments. The cost model should include:

- Provider charge per billable segment, destination and route.
- Multi-segment messages caused by length or character encoding.
- Taxes and provider surcharges where applicable.
- Delivery-report and API costs, if charged.
- Payment/top-up processing costs.
- Failed or retried message charging rules.
- ACADIVA support and operational overhead.
- A disclosed contribution margin.

The school-facing price should be calculated from the actual cost per billable segment plus an explicit sustainable margin. The wallet should display the price before purchase. Message length should be controlled so a long announcement does not unexpectedly consume several SMS credits per parent.

### 32.5 Email and in-app communications

Email and in-app notifications should be preferred for routine communications where appropriate. ACADIVA should use a verified transactional email provider and a dedicated sending domain/subdomain with correct SPF, DKIM and DMARC configuration.

The school should be able to send result-ready notices, receipts, fee reminders, PTA invitations and announcements without exposing recipients' email addresses to one another. Bulk delivery should use queues, throttling, retries, suppression handling and delivery logs.

Email should also be metered internally even if it is included in the subscription: monitor provider cost, bounce rate, complaint rate and volume by tenant. Define fair-use limits before offering unlimited bulk email.

### 32.6 Payment-related revenue

Payment processing is primarily a convenience and operational feature, not an assumption that ACADIVA can freely add a hidden charge to school fees.

The preferred initial arrangement is that a school's approved merchant account receives its own collections, with ACADIVA providing transaction initiation, allocation, receipts and reconciliation.

Potential future revenue may include:

- A provider-approved platform or integration fee.
- A disclosed software convenience fee, only where permitted by provider terms, applicable law and the school's agreement.
- A premium reconciliation or finance module.

Do not add an undisclosed percentage to a parent's school bill. Confirm who bears gateway fees, the exact permitted fee display, settlement model, refunds and disputes with the payment provider and legal advisers. Never assume ACADIVA can retain a share of school funds under a standard payment integration.

### 32.7 School-wide licensing and teacher access

The school subscription should cover the institution's authorised workforce and parent community within the agreed plan.

For example, if a school has 300 students, 20 teachers, 3 administrators and 300 parent/guardian accounts, the school buys the applicable school plan. The school does not need to buy 20 separate teacher subscriptions or ask each teacher to pay personally.

Plan limits should distinguish:

- Active enrolled students (primary pricing metric).
- Teacher and staff accounts.
- Parent/guardian accounts.
- Platform administrator accounts.
- Optional student logins.
- Storage and communication usage.

Do not charge per parent login in a way that discourages schools from inviting families. The value comes from broad adoption across the school. Prevent duplicate parent accounts where possible and support one verified guardian account linked to multiple children.

A teacher's normal access should remain available on their own phone, a school computer or a compatible school tablet. The future Teacher Pad is a school/funder-supported device programme, not a mandatory paid teacher subscription.

### 32.8 Ten-school pilot economics

The first commercial validation milestone is to secure 10 schools that agree to pilot or subscribe under clearly documented terms. Ten schools are a validation cohort, not proof of product-market fit or guaranteed recurring revenue.

Track for each school:

- Number of active students.
- Number of active teachers and administrators.
- Parent activation and monthly active usage.
- Fee records and payment reconciliation usage.
- SMS and email volume.
- Infrastructure and storage consumption.
- Support hours and onboarding cost.
- Subscription revenue and payment collection.
- Gross margin by school.
- Renewal intent, actual renewal and churn reasons.

The operating model should calculate:

Monthly recurring revenue = sum of active school subscription charges.

Variable cost per school = allocated database/hosting/storage cost + messaging costs + payment-related platform costs + support/onboarding costs that recur + other usage-based provider charges.

Contribution per school = subscription and add-on revenue attributable to the school minus its variable costs.

Contribution margin = total contribution divided by attributable revenue.

Do not use teacher salary as the basis for claiming a fixed affordable subscription without interviewing proprietors. Use the ₦50,000 average teacher salary assumption as a reference point for affordability conversations, then test proposed school prices against school enrolment, fee income, staff count, existing software spend and ability to pay.

Create a 10-school pilot spreadsheet with conservative, base and high-usage scenarios. SMS usage must be modelled separately because a school with frequent bulk messages can cost materially more than a school using email and in-app notices.

### 32.9 Commercial safeguards

- Publish clear plan inclusions and exclusions.
- Do not offer unlimited SMS without a cost-backed fair-use policy.
- Make top-ups, add-ons and any payment service charges transparent.
- Give schools invoices and receipts for their ACADIVA subscription and add-ons.
- Keep school fee collections separate from ACADIVA subscription revenue.
- Do not treat money collected on behalf of a school as ACADIVA revenue.
- Do not charge teachers personally for mandatory employer-provided platform access.
- Do not sell or use student/parent data for advertising.
- Maintain an orderly cancellation, export and transition process.
- Review plan prices against real infrastructure, messaging and support costs at least periodically.

### 32.10 Commercial decisions and validation checklist

- [ ] Confirm whether the free tier covers up to 50 active students and define the exact threshold.
- [ ] Decide the paid student bands and whether there is a minimum monthly subscription.
- [ ] Compare monthly, per-term and annual billing with actual school cash-flow preferences.
- [ ] Define included teacher, admin and parent accounts for each plan.
- [ ] Obtain current SMS rate cards from Termii and at least one alternative provider.
- [ ] Confirm how each provider bills Unicode, multi-segment, failed and international messages.
- [ ] Decide the first-time activation SMS allowance and abuse controls.
- [ ] Set up school SMS wallets, top-up and low-balance alerts.
- [ ] Define routine, transactional and security-message policies.
- [ ] Obtain email provider pricing and establish domain authentication.
- [ ] Confirm Paystack education pricing eligibility and permitted platform revenue arrangements.
- [ ] Interview at least 10 school proprietors about pricing and willingness to pay.
- [ ] Model gross margin under low, typical and high usage.
- [ ] Define onboarding, migration, training and support fees.
- [ ] Keep teacher access included in the school's licence; evaluate any optional personal teacher product separately.
- [ ] Validate the 10-school pilot before committing to expensive infrastructure or device procurement.

## 33. Previous subscription draft — superseded by Section 34

<b>Status:</b> Historical draft retained for decision history only. Do not use these term-led prices or financial figures. The revised monthly pricing and 10-school operating model in Section 34 supersedes this section.

### 33.1 Subscription pricing principles

ACADIVA should sell one school-wide licence. The school pays for the institution; its authorised teachers, administrators and linked parents receive access under that licence. Teachers must not pay personally for access required to perform their school duties.

The primary pricing metric should be active enrolled students. Do not price by teacher or parent login. This encourages broad adoption and makes the cost easier for proprietors to understand.

The primary billing option should be per academic term, because it aligns with the way many Nigerian schools budget. Monthly billing should remain available at a modest premium for schools that cannot pay a full term upfront. Annual prepayment may receive a discount.

### 33.2 Proposed launch plans

| Plan | Active student limit | Proposed price per term | Proposed monthly price | Intended school |
| --- | --- | --- | --- | --- |
| Free | Up to 50 | ₦0 | ₦0 | Very small schools testing the platform |
| Starter | 51–200 | ₦35,000 | ₦10,000 | Small schools |
| Growth | 201–500 | ₦65,000 | ₦18,000 | Growing schools |
| Pro | 501–1,000 | ₦110,000 | ₦30,000 | Larger schools |
| Enterprise | Above 1,000 or multiple branches | Custom | Custom | Large schools and school groups |

The monthly price is intentionally higher than the annualised per-term equivalent because it gives the school more flexible payment timing. At the proposed rates, paying monthly for 12 months costs about 14% more for Starter, 11% more for Growth and 9% more for Pro than paying for all three terms upfront. A school paying termly should receive a lower effective price.

For a school paying for all three terms, the proposed annual total before any discount is:

- Starter: ₦105,000.
- Growth: ₦195,000.
- Pro: ₦330,000.

A possible 10% annual prepayment discount would reduce those totals to ₦94,500, ₦175,500 and ₦297,000 respectively. Do not offer the discount until cash-flow and support economics are tested.

The free tier should have a firm ceiling of 50 active students. Schools above 50 must move to Starter. Free schools should receive core records and basic academic functionality, but limited storage, messaging, support and premium features. Do not allow free accounts to create unlimited SMS or human-support costs.

### 33.3 What each school subscription includes

All paid plans should include the normal school-wide licence:

- One proprietor/owner account, subject to school verification.
- Principal and authorised administrator accounts.
- Teacher accounts required by the school, within a fair-use policy.
- Parent/guardian accounts linked to enrolled students.
- Student records, class structures, attendance and academic records.
- Results, grading and standard report cards.
- Fee structures, payment records, balances and receipts.
- Announcements and standard parent communication tools.
- Standard dashboards and reports.
- Access through supported web and mobile experiences.

Do not charge separately for every teacher or parent. The plan may impose reasonable operational limits on staff seats, storage or bulk actions at very large scale, but normal school staffing and parent access should be included.

Potential tier differences should be based on genuine incremental value and cost: student capacity, storage, advanced analytics, custom website/domain, multi-branch controls, premium onboarding and priority support. Core safeguarding, security, data export and access to a school's own records must not be paywalled.

SMS credits are not included as unlimited usage. Each school funds its own SMS wallet. Routine SMS should stop when the wallet is empty, while in-app and email channels continue. Security and account-recovery messages need a protected allowance and safe fallback.

### 33.4 Optional charges and add-ons

- Basic self-service onboarding and standard help: included.
- Assisted spreadsheet migration or complex data cleanup: proposed one-time ₦15,000–₦50,000 depending on effort; quote after reviewing the school's data.
- On-site training: quote by location, number of staff and session length.
- Custom school website/domain: separate setup and renewal price after domain and hosting costs are known.
- SMS: prepaid school wallet, priced by billable message segment and disclosed before top-up.
- Advanced analytics, extra storage, multi-branch management and custom integrations: later add-ons or higher tiers.
- Payment gateway fees: shown transparently and assigned according to the provider agreement. Do not silently deduct them from school funds or add an undisclosed charge to parents.

### 33.5 Ten-school base-case assumptions

The first 10-school cohort is a financial validation exercise, not proof of product-market fit. The base-case mix assumes:

- 3 Starter schools at ₦35,000 per term.
- 5 Growth schools at ₦65,000 per term.
- 2 Pro schools at ₦110,000 per term.
- Three academic terms are billed in one school year.
- Subscription revenue is recognised across 12 months for planning, including school holiday periods when the platform still needs to operate.
- The school, not ACADIVA, pays for routine school-directed SMS through its wallet.
- The model assumes the platform is already operating and does not include the one-time cost of building the product.

Base-case subscription revenue:

- Per term: (3 × ₦35,000) + (5 × ₦65,000) + (2 × ₦110,000) = ₦650,000.
- Per academic year: ₦650,000 × 3 = ₦1,950,000.
- Average monthly recognised subscription revenue: ₦1,950,000 ÷ 12 = approximately ₦162,500.
- This is not the same as cash received every month: termly billing creates larger collections at the start of each term and quieter months between collections.

### 33.6 Estimated recurring monthly operating costs

The following is a planning budget for 10 schools, not vendor quotations:

| Cost item | Monthly planning allowance | Basis |
| --- | --- | --- |
| Supabase Pro | ₦40,000 | US$25/month with a conservative planning FX assumption of ₦1,600/US$; actual FX and usage may change |
| Hosting, domain allocation, monitoring, email and independent backup allowance | ₦20,000 | Budget reserve; actual architecture and vendor usage must be measured |
| Part-time customer support and onboarding allocation | ₦50,000 | Human support time for 10 schools |
| School visits, acquisition and field support | ₦20,000 | Modest pilot sales and travel allowance |
| General operating tools/admin | ₦10,000 | Basic operating allowance |
| Payment fees on ACADIVA subscription collections | Approximately ₦2,700 | Illustrative Paystack standard local rate applied to three annual term invoices and averaged over 12 months; actual method and eligibility may differ |
| New-user activation SMS reserve | ₦630 | Assumes 100 new or replacement users per month at an illustrative ₦6.30 per SMS segment |
| <b>Estimated monthly operating cost</b> | <b>Approximately ₦143,320</b> | Excludes founder salary, product development and tax |

The Supabase Pro public starting price is US$25/month and includes specified database, storage, egress and backup allowances; overages or additional projects can increase the bill. Netlify and other vendor charges must be checked against the actual deployment and usage. The ₦1,600/US$ conversion is a budgeting assumption, not a live exchange-rate claim.

The illustrative SMS unit cost uses a published Nigerian transactional/corporate SMS rate from Arkesel of around ₦6.30 per segment at smaller published top-up levels. Termii currently asks customers to obtain a current channel rate card, so ACADIVA must request a written quote before choosing a provider. Rates, taxes, DND routes, sender ID, Unicode and multi-segment billing can change the actual cost.

### 33.7 Payment gateway treatment

ACADIVA subscription collections are separate from school fee collections.

For planning, the model uses Paystack's published standard Nigeria local transaction fee of 1.5% + ₦100, subject to the published cap and channel-specific terms. The estimated base-case charge is approximately ₦10,750 per term across the 10 subscription invoices. With three billed terms per year, that is ₦32,250 per year, or approximately ₦2,688 per month when averaged over 12 months.

Paystack separately advertises discounted education-institution pricing for eligible school collections: 0.7% capped at ₦1,500 for local card payments and a flat ₦300 for other payment methods. This must not be assumed to apply automatically to ACADIVA's own subscription invoices. ACADIVA must confirm its eligibility and contractual position with Paystack.

Gateway fees on parents' school-fee payments are not treated as ACADIVA operating costs in this projection because the school collection belongs to the school and the fee allocation must be agreed with the provider and school. ACADIVA must not count school fee collections as its revenue.

### 33.8 Ten-school scenarios

The scenarios below assume three terms per school year and spread annual subscription revenue over 12 months. Costs are estimates and should be replaced with actual pilot usage data.

| Scenario | School mix | Revenue per term | Average monthly subscription revenue | Estimated monthly operating cost | Approximate monthly result |
| --- | --- | --- | --- | --- | --- |
| Low | 6 Starter, 4 Growth | ₦470,000 | ₦117,500 | ₦142,640 | <b>-₦25,140</b> |
| Base | 3 Starter, 5 Growth, 2 Pro | ₦650,000 | ₦162,500 | ₦143,320 | <b>+₦19,180</b> |
| High | 2 Starter, 5 Growth, 3 Pro | ₦725,000 | ₦181,250 | ₦158,600 | <b>+₦22,650</b> |

The high-usage scenario assumes higher support, infrastructure and acquisition costs because larger schools create more activity. The low scenario shows that 10 schools concentrated in the cheaper plans may not cover the operating cost of a professionally supported service.

The base-case annual subscription revenue is ₦1,950,000. Estimated annual operating cost at approximately ₦143,320 per month is approximately ₦1,719,840. The resulting annual operating surplus is approximately ₦230,160 before founder compensation, product development, taxes, legal/compliance costs, major security audits, capital expenditure and unexpected incidents.

This is a thin surplus, not a mature or comfortable profit margin. Ten schools are enough to test unit economics, not enough to support a large team or expensive infrastructure.

### 33.9 SMS wallet example — separate from subscription revenue

Illustrative base usage:

- 10 schools.
- 500 SMS segments per school per month.
- Total: 5,000 billable segments per month.
- Illustrative provider cost: 5,000 × ₦6.30 = ₦31,500.
- Illustrative school wallet selling price: 5,000 × ₦7.50 = ₦37,500.
- Illustrative gross contribution: ₦6,000 per month before payment fees, tax, support and failed-message adjustments.

The ₦7.50 selling price is a modelling example, not a final published rate. Set the real wallet price only after confirming provider quotations, tax, delivery billing and payment-top-up charges. SMS wallet funds should be accounted for as prepaid customer balances until messages are consumed; do not treat the entire top-up as earned profit on receipt.

### 33.10 First-time activation SMS cost

ACADIVA may fund one first-time activation SMS per newly invited user, subject to rate limits and anti-abuse controls. For illustration, 10 schools with 300 students each could involve approximately 3,000 guardian accounts plus 200 staff accounts: 3,200 initial activation messages.

At an illustrative ₦6.30 per segment, this is a one-time onboarding cost of approximately ₦20,160. It should be budgeted separately from the recurring monthly reserve. The actual number of guardians may be lower if one guardian account is linked to multiple children.

Activation messages must use expiring invitation links or one-time codes, never permanent passwords. Re-sends and subsequent school-driven messages are charged to the school's SMS wallet under the published policy.

### 33.11 What the projection does not include

The projection is not a full company profit-and-loss statement. It excludes:

- Founder salary and full-time staff salaries.
- Software development, design and engineering labour.
- Major new feature development.
- Legal advice, data-protection registration/assessment and compliance audits.
- Independent penetration testing and major security remediation.
- Tax and statutory obligations.
- Device procurement, Teacher Pad inventory and warranties.
- Large-scale data migration, custom integrations and extraordinary support incidents.
- Bad debt, refunds, churn and delayed school payments.
- Any substantial infrastructure overage or foreign-exchange shock.

The founder may initially perform product, sales and support work without drawing a full salary, but this must not be mistaken for a sustainable long-term cost structure. The model must later include a realistic founder/employee compensation line.

### 33.12 Decisions and validation before publishing prices

- [ ] Interview at least 10 school proprietors and test the proposed ₦35k / ₦65k / ₦110k per-term bands.
- [ ] Ask schools whether they prefer termly, monthly or annual billing and when they can pay.
- [ ] Confirm whether the free plan should remain up to 50 active students.
- [ ] Confirm the included teacher, staff and parent account policy for each tier.
- [ ] Obtain written SMS quotes from Termii and at least one alternative provider; compare actual billable segment, DND, sender ID, failed-send and webhook terms.
- [ ] Confirm current Paystack charges and whether ACADIVA qualifies for any education-platform pricing for its own subscriptions.
- [ ] Measure actual Supabase database, storage, egress, authentication and backup use with pilot schools.
- [ ] Measure real onboarding hours, support tickets and school-visit costs.
- [ ] Track termly cash collections separately from average monthly recognised revenue.
- [ ] Recalculate contribution margin for each school and each plan after the first 10-school pilot.
- [ ] Do not commit to unlimited SMS, unlimited support or a large fixed-cost team based on this projection.
- [ ] Revise pricing if the low-usage cohort is loss-making or if actual support costs are materially higher than assumed.

The commercial target is not merely to sign 10 schools. It is to prove that each school can be onboarded, supported, retained and served at a positive contribution margin without charging teachers individually or selling student data.

## 34. Revised monthly subscription pricing and 10-school operating model

<b>Status:</b> Historical pricing draft. Superseded by Section 35 (15 November 2026), which resets the entry paid price to ₦30,000/month and provides revised student bands, staffing assumptions and unit economics. Retain this section for decision history only; do not use its prices or projections as the current model.

### 34.1 Commercial decision: monthly school-wide subscription

ACADIVA should charge monthly by school, using active enrolled student count as the pricing band. The monthly subscription covers the whole school community: proprietor, principal, authorised administrators, teachers, parents/guardians linked to students and student accounts where enabled.

There must be no separate mandatory teacher subscription and no charge per parent login. The school pays for the institution. This is important because ACADIVA connects the school's whole operating community, not just the proprietor or the person entering results.

Monthly billing is the default because the service operates continuously throughout the month and schools pay staff monthly. A school should not pay a small amount once for a three-month term while ACADIVA provides continuous access, support, hosting, backups and updates for the entire period.

A termly prepayment option may be offered for cash-flow convenience, but it must equal three monthly subscriptions, less at most a modest prepayment discount. It must never turn the monthly price into the price for an entire three-month term.

### 34.2 Proposed monthly pricing bands

| Plan | Active enrolled students | Monthly subscription | Commercial purpose |
| --- | --- | --- | --- |
| Free | 0–50 | ₦0 | Entry point for very small schools and product adoption |
| Starter | 51–99 | ₦35,000 | Small schools |
| Standard | 100–200 | ₦50,000 | Core target segment |
| Growth | 201–500 | ₦75,000 | Larger primary/secondary schools |
| Pro | 501–1,000 | ₦120,000 | High-enrolment schools |
| Enterprise | Above 1,000 or multiple branches | Custom | School groups and complex institutions |

Boundary rule: a school with exactly 50 active students remains on Free; 51 students moves to Starter; 100 students moves to Standard; 201 students moves to Growth; 501 students moves to Pro.

The founder's initial pricing direction of Free up to 50, ₦35,000 for 51–99 and ₦50,000 for 100–200 is retained. The higher bands are proposed extensions that need separate validation.

### 34.3 Pricing psychology and market positioning

The Free plan is an acquisition route for very small schools, not the main commercial target. A 50-student ceiling naturally means many established schools will need a paid plan. However, Free must still be a genuine, usable entry plan; it must not be intentionally broken or misleading.

The paid value proposition is the complete school-wide system: records, admissions/enrolment, classes, teachers, attendance, timetable, grades/results, parent access, announcements, fees, payment tracking, receipts, finance overview and school reports. The plan is not simply a fee for a result checker.

At 100 students, ₦50,000/month is ₦500 per active student. At 200 students it is ₦250 per student. At 51 students, ₦35,000 is approximately ₦686 per student; at 99 students it is approximately ₦354 per student. The price per student falls as the school grows within a band, while ACADIVA still earns more from schools with larger operational demands.

Public competitor examples show a wide range rather than one universal market price. Akadaa lists a ₦25,000 monthly Starter plan for up to 500 students; Edunile lists ₦29,000/month for up to 150 students; Takadar publishes per-student monthly rates of ₦200, ₦400 and ₦600 depending on plan. These are competitor claims and not directly equivalent feature-for-feature. They show that ACADIVA's proposed ₦50,000 price for 100–200 students is a premium position that must be justified by the breadth, quality, onboarding and reliability of the full school-wide experience. Sources: [https://www.akadaa.com/pricing](https://www.akadaa.com/pricing) ; [https://edunile.com/pricing](https://edunile.com/pricing) ; [https://takadar.com/pricing/](https://takadar.com/pricing/)

Do not use deceptive decoy pricing. The free tier should help tiny schools start, while the paid tiers should make the value and cost of running a larger school clear. Show the monthly price prominently and explain the included users and features before checkout.

### 34.4 Billing options

- Default: monthly subscription, paid in advance.
- Optional term prepayment: three monthly payments combined, with a maximum proposed 5% discount if cash-flow benefits justify it.
- Optional annual prepayment: up to one month free (approximately 8.3% discount), only after retention and cash-flow have been validated.
- No ₦35,000 or ₦50,000 charge for an entire three-month term. At the proposed monthly prices, the undiscounted term equivalents are ₦105,000 for Starter and ₦150,000 for Standard.
- Define grace period, failed payment handling, renewal notices, suspension rules, read-only/export access and reinstatement clearly. Never delete school records because a subscription payment is late.
- Schools should be able to see invoices, renewal date, plan, student count and payment history.

### 34.5 What the subscription includes

Every paid plan includes school-wide access for:

- Proprietor/owner and principal.
- Authorised administrators and registrar.
- Teachers, including class teachers and subject teachers.
- Bursar/finance users with appropriate permissions.
- Parents/guardians linked and verified by the school.
- Student accounts where the school enables them.

Core modules included in the paid school licence:

- Student records, admissions and enrolment.
- Academic sessions, terms, classes, arms and subjects.
- Teacher records, class/subject assignments and timetable.
- Attendance and student progress.
- Assessment, grades, results and standard report cards.
- Parent/guardian portal and linked-child access.
- Announcements and in-app communication.
- Fee structures, payment records, balances and receipts.
- Standard dashboards and school-level reports.

SMS is not unlimited and is not included as an unlimited entitlement. Each school funds its own SMS wallet. Additional storage, bespoke integrations, premium website/domain work, complex migration and on-site training may be separately priced. Essential security, data protection, access to school records and data export must not be paywalled.

### 34.6 Infrastructure architecture for the 10-school model

The financial model assumes one shared, properly isolated multi-tenant ACADIVA production platform for all 10 schools. It does not assume a separate Supabase project/database for each school. Each school is isolated by tenant identity and server-enforced access controls, including Row Level Security. Separate databases per school would multiply infrastructure costs and are not required for the initial SaaS model.

Use:

- One Supabase Pro production project.
- One separate Supabase staging/test project, with no real student data.
- Netlify as the selected frontend hosting/deployment provider for this model.
- One primary ACADIVA domain with school-specific subdomains/wildcard routing, rather than purchasing a separate domain for every school.
- Independent backups outside the primary database provider, with scheduled restore tests.
- A transactional email provider with SPF, DKIM and DMARC configured.
- A monitoring/uptime/error-reporting allowance.
- SMS through a provider wallet, with costs charged to each school according to actual billable segments.

Do not pay for both Netlify and Vercel for the same production workload. Do not rely on a free hosting tier for a school-critical production service. The staging environment is important, but must be kept small and must never hold live student data.

### 34.7 Billing cycles: monthly versus annual versus usage-based

The vendor billing cycles are different from the ACADIVA school subscription cycle:

| Service | Expected billing pattern | ACADIVA treatment |
| --- | --- | --- |
| Supabase Pro | Monthly subscription plus possible usage/compute overages | Monthly infrastructure cost |
| Netlify Pro | Monthly plan credits; usage can consume credits and trigger additional charges if enabled | Monthly hosting cost plus usage reserve |
| Domain registration | Usually annual renewal | Set aside one-twelfth of annual renewal cost every month |
| Independent backup/storage | Usage-based or monthly, depending on provider | Monthly reserve and usage monitoring |
| Email delivery | Usually usage-based or monthly plan | Monthly reserve; monitor sends and bounces |
| SMS | Prepaid wallet / usage-based | School-funded wallet; ACADIVA funds only defined activation allowance |
| Payment gateway | Deducted per successful transaction | Variable collection cost |
| Monitoring/security tools | Monthly or usage-based depending on plan | Monthly reserve |

A vendor's annual domain renewal must not be treated as a surprise expense when it arrives. Keep a separate renewal reserve. Netlify's published plans use monthly credits that reset each billing cycle; usage can consume credits, so set alerts and keep a deliberate buffer. Supabase Pro starts at US\$25/month, includes US\$10 monthly compute credits for one default Micro project, and additional projects start at about US\$10/month. The current official pricing page should be checked before each infrastructure commitment.

Official references:

- Supabase pricing: [https://supabase.com/pricing](https://supabase.com/pricing)
- Supabase multiple-project billing: [https://supabase.com/docs/guides/platform/billing-faq](https://supabase.com/docs/guides/platform/billing-faq)
- Netlify pricing: [https://www.netlify.com/pricing/](https://www.netlify.com/pricing/)
- Netlify credit-based billing: [https://docs.netlify.com/manage/accounts-and-billing/billing/billing-for-credit-based-plans/](https://docs.netlify.com/manage/accounts-and-billing/billing/billing-for-credit-based-plans/)

### 34.8 Monthly backend and operating cost budget for 10 schools

This is a conservative planning budget, not a provider quote. Currency conversion assumes ₦1,600 per US dollar for planning only. The actual FX rate and provider invoices may differ.

| Cost item | Monthly reserve | Explanation |
| --- | --- | --- |
| Supabase production + staging | ₦56,000 | Approx. US\$35/month: Pro plan plus one additional default Micro project, using planning FX |
| Netlify Pro + usage buffer | ₦48,000 | Approx. US\$30/month: US\$20 base plan plus a US\$10 usage/credit reserve |
| Domain renewal reserve | ₦5,000 | ₦60,000/year planning allowance divided by 12; confirm actual registrar/domain pricing |
| Independent backup/storage | ₦10,000 | Separate backup copy and retention allowance; not a substitute for restore testing |
| Transactional email | ₦5,000 | Low-volume allowance; actual cost depends on provider and sends |
| Monitoring, uptime and security logs | ₦8,000 | Basic production monitoring and alerting reserve |
| <b>Infrastructure subtotal</b> | <b>₦132,000</b> | Backend, hosting, domain reserve, backup, email and monitoring |
| Customer support/onboarding allocation | ₦75,000 | Part-time support coverage and onboarding for the 10-school cohort |
| Sales, school visits and acquisition | ₦40,000 | Modest field visits, transport and acquisition activity |
| General administration/tools | ₦15,000 | Basic operating allowance |
| ACADIVA-funded first-time activation SMS reserve | ₦5,000 | Small recurring reserve; school-driven routine messages are not included |
| <b>Operating cost before gateway fees</b> | <b>₦267,000</b> | Excludes founder salary, engineering salary, taxes and legal/compliance costs |

Supabase official published Pro pricing is US\$25/month, with US\$10 monthly compute credits sufficient for one default Micro compute project; additional projects start at about US\$10/month. The estimate assumes production and a separate staging project. Supabase includes daily backups on Pro for seven days, but ACADIVA still needs an independent backup and restore plan.

Netlify currently lists Pro from US\$20/month with 3,000 monthly credits at the base tier. The extra US\$10 in this budget is a precautionary usage reserve, not a claim that every school requires it. Review actual credit consumption monthly and adjust the tier. If Netlify usage is comfortably below the base allowance, the reserve can remain unspent.

The domain reserve is a planning allowance, not a verified quote. The actual domain renewal, tax and registrar charge must be confirmed before purchase. One wildcard-capable domain arrangement should serve the school subdomains where supported; do not buy ten separate domains for ten schools unless a school chooses a custom domain.

### 34.9 Payment processing cost on ACADIVA subscriptions

Paystack's current published Nigeria local transaction rate is 1.5% + ₦100, capped at ₦2,000 per transaction. This model assumes each school pays its ACADIVA monthly invoice through Paystack. If schools pay by direct bank transfer and are reconciled manually, gateway fees may be avoided but staff reconciliation effort increases.

Illustrative fees:

- ₦35,000 subscription: ₦625.
- ₦50,000 subscription: ₦850.
- ₦75,000 subscription: ₦1,225.
- ₦120,000 subscription: ₦1,900.

Official reference: [https://paystack.com/pricing](https://paystack.com/pricing)

These are fees on ACADIVA subscription payments only. Fees on parents' payments to schools are separate and must be contractually allocated. School fee collections belong to the school and are never counted as ACADIVA subscription revenue.

### 34.10 Ten-school monthly revenue and profit model

Base-case school mix:

- 4 schools with 51–99 students at ₦35,000/month = ₦140,000.
- 5 schools with 100–200 students at ₦50,000/month = ₦250,000.
- 1 school with 201–500 students at ₦75,000/month = ₦75,000.

Total monthly recurring subscription revenue = ₦465,000.

Estimated monthly Paystack fees:

- 4 × ₦625 = ₦2,500.
- 5 × ₦850 = ₦4,250.
- 1 × ₦1,225 = ₦1,225.
- Total gateway fees = ₦7,975.

Estimated monthly cost:

- Operating budget before gateway fees = ₦267,000.
- Gateway fees = ₦7,975.
- Total estimated monthly cost = ₦274,975.

Estimated monthly operating surplus:

- ₦465,000 − ₦274,975 = ₦190,025.

This is an operating surplus before founder compensation, software engineering/product development salaries, tax, legal and data-protection compliance, major security testing, and unexpected costs. It is not the founder's take-home profit and must not be represented as fully net profit.

### 34.11 Alternative 10-school scenarios

| Scenario | School mix | Monthly subscription revenue | Estimated monthly total cost | Estimated operating surplus |
| --- | --- | --- | --- | --- |
| Low | 10 Starter schools (51–99 students) | ₦350,000 | ₦273,250 | ₦76,750 |
| Base | 4 Starter, 5 Standard, 1 Growth | ₦465,000 | ₦274,975 | ₦190,025 |
| Typical 100-student schools | 10 Standard schools | ₦500,000 | ₦275,500 | ₦224,500 |
| High | 2 Standard, 5 Growth, 3 Pro | ₦835,000 | Approx. ₦295,525 | Approx. ₦539,475 |

The high scenario includes an additional ₦15,000 usage/support allowance because larger schools may consume more storage, traffic and support time. Total cost is ₦267,000 base operating budget + ₦13,525 gateway fees + ₦15,000 added usage/support = ₦295,525. It remains an estimate and needs actual usage data.

The most relevant early target is not to maximise the number of free schools. It is to acquire schools with at least 50 students, especially the 100–200-student segment, while ensuring that the product genuinely delivers enough value to justify ₦50,000 every month.

### 34.12 Break-even interpretation

With the estimated ₦267,000 operating budget before transaction fees:

- Around 8 Starter schools at ₦35,000/month are needed to cover this cost, after illustrative payment fees.
- Around 6 Standard schools at ₦50,000/month are needed to cover this cost, after illustrative payment fees.

This is a simplified break-even guide, not a guarantee. Support and infrastructure costs may change with school size, usage and the number of active parents/teachers.

### 34.13 SMS economics

Routine school-directed SMS must be funded by each school's prepaid SMS wallet. For an illustrative 5,000 billable segments in a month, Arkesel currently lists transactional/corporate SMS at around ₦6.30 per segment at its ₦5,000 top-up level, with lower per-segment rates at higher top-up amounts. Rates may change and multi-part Unicode messages can consume multiple segments.

At 5,000 segments:

- Illustrative provider cost: 5,000 × ₦6.30 = ₦31,500.
- A hypothetical ₦7.50 school wallet selling rate would collect ₦37,500.
- Difference: ₦6,000 before payment fees, taxes, failed delivery treatment and administration.

This difference is not guaranteed profit. Confirm provider rates, route quality, DND rules, sender ID approval, message segmentation and delivery billing before publishing a wallet rate. Wallet top-ups remain a customer balance until consumed; do not book the whole top-up as earned revenue.

Arkesel published pricing: [https://arkesel.com/pricing/](https://arkesel.com/pricing/)

ACADIVA may fund one first-time activation message per invited user, with expiring activation link or one-time code, subject to abuse controls. It must never send permanent passwords by SMS. All later school-directed messages and re-sends are charged to the school's wallet. For a 10-school cohort, budget the one-time initial activation campaign separately from recurring monthly costs.

### 34.14 Reliability and payment safeguards

- Use a production hosting plan with a deliberate usage allowance; do not rely on a free-tier hard limit for the live school service.
- Configure billing alerts at 50%, 75% and 90% of monthly usage allowance where the provider supports them.
- Keep a dedicated card/account or funded payment method for vendor renewals; assign an internal owner to monitor billing.
- Maintain at least two months of core infrastructure costs as a reserve before onboarding many schools.
- Keep a separate annual domain-renewal reserve and calendar reminder.
- Keep the production database and staging database separate; never use real student data in staging.
- Maintain encrypted independent backups and perform restoration tests.
- Monitor Supabase database size, compute, egress, storage, auth usage and logs.
- Monitor Netlify credits, builds, bandwidth and add-on usage.
- Do not switch off spend caps without alerts and a clear owner.
- Keep school SMS balances separate from ACADIVA operating cash.
- If a vendor payment fails, alert the platform operator before service interruption; do not wait for a school to report an outage.

### 34.15 Costs excluded from the estimate

The estimate does not include:

- Founder salary or dividends.
- Full-time engineer, designer or product manager salaries.
- Major new feature development and technical debt reduction.
- Legal fees, data protection registration/assessment, DPO services or audits.
- Independent penetration tests and major remediation.
- Taxes, statutory filings and accounting services.
- Tablet procurement or Teacher Pad programme costs.
- Large custom migrations, integrations, on-site training or extraordinary support.
- Refunds, chargebacks, bad debt, churn and delayed subscription collections.
- Large traffic/storage/compute overages or currency shocks.

The operating surplus must therefore be called a pre-founder-pay operating surplus, not net profit. A sustainable company forecast must add a realistic engineering and founder compensation line.

### 34.16 Decisions to validate before publishing

- [ ] Confirm the exact student band boundaries: 0–50 free; 51–99 ₦35,000; 100–200 ₦50,000; 201–500 ₦75,000; 501–1,000 ₦120,000; above 1,000 custom.
- [ ] Interview at least 10–20 proprietors, especially schools with 50–200 students, and test willingness to pay monthly.
- [ ] Confirm whether the full set of modules is included in every paid plan or whether specific premium features belong in higher plans.
- [ ] Confirm how active student counts are measured and how transfers, withdrawals and mid-month enrolments affect billing.
- [ ] Test monthly versus termly prepayment preference; do not price a full term at one month's fee.
- [ ] Obtain current written SMS rates and payment terms from providers.
- [ ] Confirm actual Netlify credit consumption and Supabase usage in staging and production.
- [ ] Obtain real domain renewal quotes and set the annual reserve.
- [ ] Track support hours, school visits, email, storage, egress and parent/teacher activity for every pilot school.
- [ ] Recalculate the model after 30, 60 and 90 days of real use.
- [ ] Add founder/engineering compensation and taxes before claiming sustainable net profit.
- [ ] Keep the 10-school model as a validation cohort; scale only when retention and contribution margin are demonstrated.

The commercial goal is to build a school-wide system that schools are willing to pay for every month because it is part of their daily operations. The price must support reliable infrastructure, real support and continued product improvement without charging teachers individually or selling school/child data.

### 34.17 Pricing boundary and free-tier safeguards

The current proposed boundaries are 0–50 free, 51–99 at ₦35,000, and 100–200 at ₦50,000 per month. This creates a ₦15,000 price increase when a school moves from 99 to 100 students. Before launch, test whether that jump feels fair to proprietors. A possible smoother alternative is to introduce a bridge band (for example, 100–149 at an intermediate price and 150–200 at ₦50,000), but do not change the founder's proposed price without testing willingness to pay.

The free plan should be genuinely useful but self-service and tightly bounded:

- Up to 50 active enrolled students, with enrolment verified by the school.
- Core digital student records and a limited academic workflow.
- Limited storage and standard report templates.
- In-app notices only; no funded bulk SMS allowance.
- No unlimited human onboarding, data migration or on-site support.
- No advanced analytics, multi-branch features or custom school website.
- Clear upgrade prompt when enrolment exceeds 50 or the school needs paid-only capabilities.

Do not make the Free plan deliberately unreliable or misleading. Its purpose is to let very small schools adopt ACADIVA and later upgrade as they grow. Prevent misuse through active-enrolment checks, fair-use limits and transparent feature boundaries, not by hiding important terms.

## 35. ACADIVA launch pricing, school staffing assumptions and 10-school operating model — revised 15 November 2026

<b>Status:</b> Recommended launch model for validation, not a proven willingness-to-pay result. This section supersedes the pricing bands and 10-school revenue model in Section 34. The previous calculations remain as historical drafts only.

### 35.1 Commercial decision

Set the entry paid subscription at <b>₦30,000 per school per month</b>. Charge by the school's active enrolled-student population, not by the number of teacher, parent, student or administrator accounts. ACADIVA is a school-wide operating system: authorised users needed to operate the school should be included in the school licence.

The customer is the school. Do not charge teachers or parents individually to access the school's records. Do not make core security, access controls, audit history or data export premium add-ons.

### 35.2 Recommended launch pricing

| Plan | Active enrolled students | Monthly price |
| --- | --- | --- |
| Free | 0–50 | ₦0 |
| Launch | 51–150 | ₦30,000 |
| Standard | 151–300 | ₦45,000 |
| Growth | 301–600 | ₦75,000 |
| Pro | 601–1,000 | ₦120,000 |
| Enterprise | Above 1,000 or multiple branches | Custom |

All prices are monthly, per school, in Nigerian naira. The school may prepay three months at the full equivalent monthly price; do not sell three months of service for the price of one month. Any annual/prepayment discount should be modest, tested and separately stated.

The ₦30,000 Launch price is deliberately simple and accessible. It is close to Edunile's published ₦29,000 monthly price for up to 150 students. Other public Nigerian vendor pages show materially different packaging and billing periods, so these are market reference points, not proof that the products are equivalent:

- Edunile: ₦29,000/month for up to 150 students — [https://edunile.com/pricing](https://edunile.com/pricing)
- Eduzaas: displayed ₦32,083/month equivalent for 300 students, billed annually — [https://eduzaas.com/en-ng/pricing](https://eduzaas.com/en-ng/pricing)
- SchoolKit: ₦45,000 per term for up to 200 students — [https://schoolkit.ng/pricing](https://schoolkit.ng/pricing)
- Totalgrades: term-based prices by enrolment band — [https://www.totalgrades.com/pricing](https://www.totalgrades.com/pricing)

These comparisons suggest that ₦30,000/month is within the visible market range for a small school's entry subscription, but ACADIVA must demonstrate reliable operation, onboarding and useful workflows before treating this as validated pricing.

### 35.3 Price psychology and how to use it ethically

- <b>A clear entry anchor:</b> Show ₦30,000/month first. It gives a proprietor a simple starting point and avoids presenting the product as an expensive enterprise system.
- <b>A meaningful middle option:</b> Show Standard at ₦45,000 and explain the additional capacity, not just a larger student number. Do not manufacture a useless decoy plan.
- <b>Round naira prices:</b> Use ₦30,000, ₦45,000 and ₦75,000 rather than artificial ₦29,999 endings. School owners often pay by transfer and need clear quotations, invoices and receipts. Simplicity and trust matter more than a one-naira trick.
- <b>Sell the school-wide outcome:</b> Explain that the licence connects the proprietor, principal, admin office, bursar, teachers and parents, rather than comparing the fee with the cost of one login.
- <b>Make the monthly amount concrete:</b> ₦30,000/month is ₦1,000 per day when spread over a 30-day month. Use this only as a transparent comparison, not as a claim that the school pays daily.
- <b>Avoid surprise upgrades:</b> Publish student-count rules, notify the school before a tier change and apply changes at a clear renewal boundary. Never silently charge a higher amount mid-cycle.
- <b>Do not rely on psychology to hide poor value:</b> Price framing can help people understand a fair offer; it cannot replace product quality, proof and trust.

The pricing literature supports the relevance of reference prices and price thresholds in B2B decisions, but effects vary by context. ACADIVA should test the actual response with proprietors rather than assume that charm pricing, anchoring or a decoy tier will automatically increase conversion. Reference: [https://www.sciencedirect.com/science/article/abs/pii/S0019850115000371](https://www.sciencedirect.com/science/article/abs/pii/S0019850115000371) and [https://www.hslu.ch/-/media/campus/common/files/dokumente/w/ikm/ikm-impuls/2025/ikm-impuls-april-2025-preismanagement-frohmann/digital-pricing-a-guide-to-strategic-pricing-for-the-digital-economy.pdf/?sc\_lang=en](https://www.hslu.ch/-/media/campus/common/files/dokumente/w/ikm/ikm-impuls/2025/ikm-impuls-april-2025-preismanagement-frohmann/digital-pricing-a-guide-to-strategic-pricing-for-the-digital-economy.pdf/?sc_lang=en)

### 35.4 Student and staff population assumptions

Nigeria's 2024/2025 Federal Ministry of Education EMIS dashboard reports 39.8 million learners and 1.186 million teachers across reporting schools, a national learner–teacher ratio of 33.6. It reports 8.27 million learners in private schools. However, only 53.7% of schools were reported in the dashboard at the time accessed. These figures are national context, not a reliable average for a specific private school or a direct measure of ACADIVA's target segment: [https://emis.education.gov.ng/portal/](https://emis.education.gov.ng/portal/)

Use the following as <b>planning estimates for product capacity and sales conversations</b>, not official staffing rules. Actual staffing varies by school level, class size, subject structure, shift pattern and whether staff hold multiple roles.

| School size | Illustrative teachers | Leadership/admin/bursary staff | Likely operating shape |
| --- | --- | --- | --- |
| 51–150 students | 4–8 | 2–4 | Small nursery/primary or one compact school |
| 151–300 students | 8–15 | 3–5 | Several classes, class teachers and some subject teachers |
| 301–600 students | 15–30 | 4–7 | Larger primary or combined nursery/primary/JSS |
| 601–1,000 students | 30–50 | 6–10 | Multiple sections, more specialist teachers and office staff |

These ranges allow for roughly 20–30 students per teacher as a rough capacity-planning lens, but they are not a claim that every Nigerian private school follows that ratio. The national EMIS ratio of 33.6 is a useful broad reference only.

For ACADIVA account and infrastructure planning:

- Proprietor/owner: commonly 1–2 authorised accounts per school; the proprietor may also be the principal.
- Principal/head teacher: commonly 1–2 accounts; avoid double-counting if the owner holds this role.
- Admin/registrar/bursar: approximately 2–10 accounts depending on school size; some duties may be combined.
- Teachers: use the planning ranges above.
- Parents/guardians: allow at least one guardian account per student as a capacity scenario, but many families have siblings in the same school and some guardians may not activate accounts.
- Students: student accounts should be optional and age/level appropriate. Younger pupils do not all need independent logins.
- Platform support/admin: ACADIVA's internal team accounts are separate from the school's licensed user population.

A school with 150 students may therefore have roughly 4–8 teachers, 2–4 office/leadership users, and up to 150 guardian-linked records, plus optional student accounts. This is why pricing per login would be a poor fit.

### 35.5 Illustrative 10-school customer mix

This model deliberately uses a mix of sizes instead of pretending all ten schools are identical.

| School group | Number of schools | Assumed average enrolment each | Assumed teachers each | Monthly plan | Monthly revenue |
| --- | --- | --- | --- | --- | --- |
| Launch | 4 | 120 | 6 | ₦30,000 | ₦120,000 |
| Standard | 4 | 220 | 11 | ₦45,000 | ₦180,000 |
| Growth | 1 | 450 | 22 | ₦75,000 | ₦75,000 |
| Pro | 1 | 800 | 40 | ₦120,000 | ₦120,000 |
| <b>Total</b> | <b>10</b> | <b>2,610 students</b> | <b>106 teachers</b> |  | <b>₦495,000</b> |

Additional capacity assumptions for this cohort:

- Approximately 20–40 leadership, registrar, admin and bursary accounts across the ten schools; roles may overlap.
- Up to 2,610 guardian-linked accounts if each student has one guardian account. Actual unique parents may be lower due to siblings, and not all may activate.
- Student logins are optional and may add up to 2,610 accounts if enabled for every learner.
- Therefore, design and load-test for several thousand identities and records, but measure real monthly active users rather than assuming every invited account is active.

### 35.6 Monthly operating cost and 10-school calculation

Keep the previous conservative planning budget as the initial monthly operating reserve. It is a planning estimate, not a vendor quote or a guarantee that usage will never exceed it.

| Monthly cost item | Budget |
| --- | --- |
| Supabase production and separate staging capacity | ₦56,000 |
| Netlify production hosting and usage buffer | ₦48,000 |
| Domain annual renewal reserve | ₦5,000 |
| Independent backup/storage reserve | ₦10,000 |
| Transactional email | ₦5,000 |
| Monitoring, uptime and security logs | ₦8,000 |
| Customer support and onboarding allocation | ₦75,000 |
| Sales and school acquisition/visits | ₦40,000 |
| General administration/tools | ₦15,000 |
| ACADIVA-funded first-time activation SMS reserve | ₦5,000 |
| <b>Monthly operating budget before subscription gateway fees</b> | <b>₦267,000</b> |

Payment gateway estimate for ten successful monthly subscription charges uses Paystack's published Nigeria local fee of 1.5% + ₦100 per transaction, subject to the published cap and current terms: [https://paystack.com/pricing](https://paystack.com/pricing)

- Subscription revenue: ₦495,000.
- Percentage fee: 1.5% × ₦495,000 = ₦7,425.
- Ten transaction fixed fees: 10 × ₦100 = ₦1,000.
- Estimated subscription collection fees: ₦8,425.
- Monthly operating budget: ₦267,000.
- <b>Estimated total monthly operating cost: ₦275,425.</b>
- <b>Estimated monthly operating surplus: ₦219,575.</b>
- Annualised revenue at an unchanged ten-school mix: ₦5,940,000.
- Annualised operating cost: ₦3,305,100.
- Annualised operating surplus: ₦2,634,900.

This is a pre-founder-pay, pre-engineering-salary, pre-tax operating surplus. It is not net profit or founder take-home income. It excludes full-time engineering/product salaries, founder compensation, legal and compliance costs, major security audits, tax, major feature development, refunds, churn, bad debt, large overages and device costs.

### 35.7 What if all ten schools only pay the entry price?

This is the important downside check.

- Ten Launch schools × ₦30,000 = ₦300,000 monthly revenue.
- Estimated Paystack fees: 10 × (₦450 percentage fee + ₦100 fixed fee) = ₦5,500.
- Operating budget: ₦267,000.
- Total estimated monthly cost: ₦272,500.
- <b>Operating surplus: only ₦27,500/month before founder pay, engineering, tax and excluded costs.</b>

Therefore, ₦30,000 is a good entry price, but ACADIVA cannot build a sustainable business by relying only on ten small schools. It needs a healthy mix of larger schools, strong retention and careful control of support and infrastructure costs.

### 35.8 Break-even interpretation

With the current ₦267,000 operating budget and the estimated Paystack fee, approximate break-even is:

- 10 Launch schools at ₦30,000: slightly above the modelled operating break-even, but leaves almost no safety margin.
- 7 Standard schools at ₦45,000: approximately ₦315,000 gross revenue; estimated fees about ₦5,425; operating surplus around ₦42,575.
- 4 Growth schools at ₦75,000: ₦300,000 gross revenue; estimated fees about ₦4,900; operating surplus around ₦28,100.

These are simplified illustrations, not a promise that a small number of schools covers all future costs. The business should target at least 10 paying schools with a mixed enrolment profile and build a two-month reserve for essential infrastructure before expanding fixed payroll.

### 35.9 Infrastructure reliability and billing safeguards

The platform must not depend on a subscription payment being processed on the exact day a vendor renews. Build operational safeguards:

- Maintain a funded payment method for hosting and database vendors; do not rely on school collections arriving before vendor renewal.
- Maintain at least two months of essential infrastructure costs in a separate reserve. At the current ₦132,000 infrastructure subtotal, that minimum reserve is ₦264,000; increase it as usage grows.
- Use one shared multi-tenant production Supabase project with strict tenant isolation and one separate staging/test project. Never use live student data in staging.
- Use one production hosting provider and one clear deployment path; do not pay for duplicate Netlify and Vercel production hosting without a documented need.
- Set usage alerts at 50%, 75% and 90% for database size, compute, storage, egress, bandwidth, builds and provider credits.
- Back up independently and test restoration. A provider's backup feature is not a substitute for a tested recovery plan.
- Set a named operator and escalation path for failed payments, usage alerts, outages and renewals.
- Reforecast monthly using actual database, storage, bandwidth, email, SMS, support hours and school activity. The ₦56,000 Supabase and ₦48,000 Netlify figures are placeholders from the prior budget and must be replaced with actual plan/usage evidence before launch.

### 35.10 Subscription boundaries and fair billing rules

- Count active enrolled students, not applicants, alumni, withdrawn students or duplicate records.
- Publish what counts as active and let the school review its count before billing.
- Do not upgrade a school because of a one-day temporary spike. Use a defined review window and notify the school.
- Apply tier changes at the next renewal after notice, except where the school explicitly requests an immediate upgrade.
- Permit a reasonable grace band for small enrolment fluctuations; final threshold and duration must be tested with schools.
- Keep all authorised teacher, parent, student and school-admin access included in the school licence within fair-use and security limits.
- SMS, bulk WhatsApp and other paid delivery channels are usage-based and funded separately by the school; do not promise unlimited messages.
- Complex historical data migration, custom domains, multi-branch configurations and on-site training may be quoted separately, with the scope agreed in writing.
- Never charge parents through ACADIVA for access to their child's own records.

### 35.11 Validation plan before treating prices as final

- Interview 15–20 proprietors across school sizes, especially 50–300 enrolment.
- Test the exact ₦30,000, ₦45,000, ₦75,000 and ₦120,000 monthly offers; ask what they would actually approve and pay, not merely whether they like the idea.
- Ask what they currently spend on record keeping, result processing, fee tracking, communications, websites and administrative labour.
- Ask who controls the budget and whether the proprietor prefers monthly direct debit/transfer or termly prepayment.
- Run at least 3–5 real pilot schools through a complete academic workflow before making broad reliability claims.
- Track active students, invited and active users, support time, storage, egress, SMS usage, payment failures, retention and actual hosting bills per school.
- Recalculate the unit economics after 30, 60 and 90 days.
- Do not claim that 10 schools produce ₦219,575 net profit. It is the modelled operating surplus before the excluded costs listed above.

<b>Recommended decision:</b> Adopt ₦30,000/month as the entry paid price and use the bands in Section 35.2 as the launch pricing hypothesis. Keep it provisional until school interviews and paid pilots confirm willingness to pay and actual delivery cost.

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

## 37. Strategic revision — adoption, product experience, offline capability and school implementation (15 November 2026)

### 37.1 Why this revision exists

The earlier adoption-risk discussion identified reasons schools might refuse a new school-management system. This section records the founder's response and the resulting changes to ACADIVA's product and go-to-market direction.

The revised position is not that adoption will be automatic or that infrastructure and trust are irrelevant. It is that ACADIVA should be deliberately designed to remove the practical reasons for resistance: make daily work easier, make management visibility valuable, keep workflows simple, support unreliable connectivity, and remain present during implementation.

This section supplements the master requirements in Section 36 and supersedes earlier assumptions wherever this section records a more recent direction. Earlier material remains as product history.

### 37.2 Revised strategic thesis

ACADIVA should become the digital operating system of a school: the organised environment through which the school manages administration, student records, academics, attendance, finance, communication and essential operations.

The product must deliver visible value to the proprietor while being genuinely easy for every person expected to use it.

The core promise is not simply that records are digital. It is that the school can operate with less repetitive work, better access to reliable information, stronger accountability, faster communication and continuity of records over time.

Key value propositions:

- Records are searchable, accessible to authorised users and retained across academic sessions, subject to the school's retention policy.
- Digital records reduce dependence on fragile, scattered paper files; printable documents remain available when required.
- Teachers can complete attendance and assessment workflows efficiently.
- Parents can access relevant information about their own children without unnecessary school visits.
- Bursars can record and reconcile fees, while management can see collections and outstanding balances.
- Proprietors and principals can see operational progress and outstanding tasks without repeatedly requesting manual updates.
- Staff responsibilities and record changes become more transparent and traceable.
- Communication becomes organised and easier to retrieve.

Do not claim that digital records can never be lost or that ACADIVA guarantees permanent retention. Backups, recovery, retention, exports and continuity arrangements must support the promise.

### 37.3 Proprietor and management experience — make visibility a core product strength

The proprietor dashboard is a major buying and retention feature, not a generic analytics page.

The proprietor should be able to see, according to their permissions:

- Total active students and enrolment by class.
- New admissions and student movement.
- Fees billed, collections received, outstanding balances and collection trends.
- Payments received today, this week and this term.
- Attendance summaries and classes with incomplete attendance.
- Assessment and result submission status.
- Staff overview and relevant operational activity.
- Pending approvals, unresolved issues and tasks requiring attention.
- Relevant academic and school performance indicators.

The principal's workspace should focus on daily school operations and academic oversight. The proprietor's workspace should provide executive and financial oversight, with appropriate drill-down into supporting records.

<b>Accuracy and provenance are mandatory.</b> A dashboard must distinguish confirmed transactions from manually recorded cash payments, pending payments, expected fees and unverified entries. It must show when information was last updated and identify missing submissions. ACADIVA must never imply that it knows about an offline cash payment unless an authorised user records and verifies it.

Accountability requirements:

- Role-based responsibilities and permissions.
- Submission and approval states.
- Audit history for sensitive changes.
- Alerts for incomplete or overdue work.
- Clear identification of who submitted, approved or corrected a record.
- Fair and transparent correction processes; accountability must not become arbitrary staff surveillance.

Potential adoption implication: staff who are unfamiliar with transparent workflows may resist them. Onboarding must explain why records are visible, what each role can see and how corrections are handled.

### 37.4 Simplicity as an engineering requirement

Digital literacy should not be treated as a reason to exclude school staff. ACADIVA should assume users are familiar with everyday smartphone applications, while recognising that school administration tasks require accuracy and structured data entry.

The interface must make each person's assigned work obvious. Users should not have to understand the entire platform.

Design principles:

- Role-specific workspaces: users see the tools and information required for their responsibilities.
- Short, guided workflows for frequent actions.
- Minimal navigation and unnecessary data entry.
- Clear language familiar to Nigerian schools.
- Large, readable controls and accessible forms.
- Bulk actions where they reduce repetitive work without increasing error risk.
- Save-state feedback and clear error messages.
- Mobile-first teacher and parent workflows.
- Responsive management and administration workflows across desktop, tablet and mobile.
- No overloaded dashboards or menus; complexity should be organised by role and task.

Examples:

- A teacher opens ACADIVA, sees assigned classes, selects a class, marks attendance and submits.
- A teacher enters marks using a guided class/subject workflow with validation.
- A bursar sees outstanding bills, records a payment and issues a receipt.
- A proprietor sees the school's current position and the items requiring attention.

A screen is not considered simple merely because it looks minimal. Usability must be tested with real teachers, bursars, administrators and parents.

### 37.5 Connectivity and offline capability — revised product direction

<b>Current strategic direction: online-first, offline-capable, with automatic synchronisation.</b>

ACADIVA should not assume that every school has uninterrupted internet or electricity. At the same time, it should not treat connectivity as a reason to avoid digital workflows. Many school users already rely on mobile phones and internet services; the product should work well when connected and remain useful during temporary outages.

Offline support should be prioritised for workflows where a temporary loss of connection must not stop school work.

Initial offline-capable workflow candidates:

- View previously loaded and authorised class lists.
- Record and save attendance.
- Draft and save assessment marks.
- Draft announcements and selected forms.
- Access selected records that have been securely cached and are permitted for that user.

Actions that require a live connection or verified server response:

- Confirming online payments and settlement status.
- Sending SMS and email.
- Accessing live school-wide financial figures.
- Creating or changing permissions and other high-risk administrative settings.
- Actions requiring current server-side approval or authoritative conflict checks.

When connectivity returns, queued changes should synchronise automatically where safe. The interface must clearly show whether data is saved locally, waiting to sync, synchronised, failed or in conflict.

Offline engineering requirements:

- Secure encrypted local storage appropriate to the platform.
- Device/session access controls and local-data expiry or revocation strategy.
- Background and manual retry synchronisation.
- Idempotency and duplicate-submission prevention.
- Conflict detection and resolution where multiple users edit the same record.
- Server-side validation and authorisation on sync.
- Recovery from app closure, device restart and interrupted sync.
- Visible sync status and a way to retry failed changes.
- Audit records that identify the originating user and device/session where appropriate.
- Tests for poor connectivity, repeated retries and concurrent edits.

Do not promise that every module works offline. Build offline support progressively, starting with attendance and assessment workflows, then expand based on pilot evidence.

### 37.6 Mobile application direction

A mobile experience is strategically important, especially for teachers and parents. The product plan must include mobile applications alongside the responsive web platform.

Proposed role priorities:

- Teacher: assigned classes, attendance, marks, notices and essential student information.
- Parent/guardian: linked children, results, attendance, fee information, receipts and school notices.
- Management: approvals, dashboard summaries and operational visibility.
- School administration and bursary: responsive workflows, with desktop/tablet support for heavier data and reporting tasks.

The final packaging decision — one role-aware app or separate teacher and parent apps — remains open. Do not duplicate the entire web application in mobile form without validating the user experience, development cost, maintenance burden and app-store requirements.

The mobile architecture must be designed with offline storage and synchronisation in mind from the beginning. Offline capability added as an afterthought may require expensive rework.

### 37.7 Trust and customer success — high-touch school adoption

ACADIVA should not sell a subscription, issue login details and leave the school to figure everything out.

The proposed adoption model is practical, relationship-led implementation:

1. Select a suitable pilot school with an engaged decision-maker and staff willing to participate.
2. Understand its existing workflows and agree which processes will move into ACADIVA.
3. Organise and migrate agreed student, staff, class, subject and fee data.
4. Configure the school's academic structure, permissions, grading and billing.
5. Train the proprietor, principal, bursar, administrators and teachers according to their roles.
6. Support the school closely during the initial live-use period.
7. Observe actual use, resolve problems and simplify confusing workflows.
8. Measure operational outcomes and staff/parent adoption.
9. Obtain permission to document the school's experience and use it as a case study.
10. Convert the pilot into a sustainable paid relationship if the school sees value.

Pilot schools should be selected for genuine participation, not merely willingness to receive free software. A free pilot that is never used is not evidence of product-market fit.

The pilot must have baseline measurements and agreed success criteria. Potential measures include time to prepare results, attendance completion, fee-record accuracy, time to retrieve student records, parent activation and support required.

Trust foundations:

- School data remains the school's data.
- Clear export and offboarding arrangements.
- Reliable backup and tested recovery procedures.
- Clear user permissions and audit history.
- Transparent incident and support communication.
- A documented service-continuity plan.
- No unsupported claims about security, uptime or permanent storage.

### 37.8 Proof-led sales and market development

A real, well-supported pilot school should become ACADIVA's first evidence base.

With the school's permission, the case study may show:

- What the school used before ACADIVA.
- Which workflows were digitised.
- How long implementation took.
- Which staff roles actively use the system.
- Changes in time spent on administration.
- Attendance and result-submission completion.
- Fee visibility and reconciliation improvements.
- Parent engagement and feedback.
- What did not work and what ACADIVA changed.

Do not invent testimonials, savings or adoption numbers. Distinguish measured outcomes from staff opinions and founder observations.

Field representatives should act as trained school-operations consultants, not only flyer distributors. They should identify decision-makers, understand current workflows, demonstrate relevant use cases, record objections, explain implementation, arrange pilots and coordinate follow-up.

Initial market validation should continue alongside the pilot. The proposed discovery sample is 30 schools in Ibadan, segmented into 10 smaller, 10 growing and 10 established schools. Interview proprietors/principals and the people who actually perform admissions, teaching, attendance and finance tasks. Test willingness to pay and implementation constraints through behaviour and commitments, not only positive opinions.

### 37.9 Pricing and value justification

The current subscription pricing in Section 35 remains a provisional hypothesis, not a final market-validated price.

The founder's commercial position is that a school may reasonably pay for software that improves multiple school functions, rather than employing additional staff or continuing to absorb repetitive administrative work. The ₦30,000 entry paid tier is intended to be accessible relative to the breadth of value ACADIVA aims to provide.

However, price must be justified by actual value and delivery cost. A school's ability to pay a staff salary does not automatically prove it will pay the same amount for software.

Pricing validation must test:

- The proprietor's willingness and ability to pay.
- Which modules create sufficient value to justify the subscription.
- Whether the school prefers monthly or termly payment.
- What support is included.
- Whether migration and intensive on-site training require a separate fee.
- Whether the price leaves sufficient gross margin after support and infrastructure.

Do not make unlimited on-site visits, unlimited SMS or unlimited custom data migration part of a low monthly subscription without costing them.

### 37.10 Onboarding and service delivery must be designed as a repeatable operation

The cost of onboarding and supporting a school may exceed the direct cost of hosting its records. This is a major business risk and must be measured.

Proposed onboarding process:

- School readiness assessment.
- Data collection templates and import checklist.
- Data cleaning and validation.
- School configuration.
- Role and account setup.
- Staff training by role.
- Controlled go-live.
- Early-life support.
- Adoption review and handover to routine support.

Build reusable tools for Excel/CSV imports, validation reports, duplicate detection, bulk class allocation, staff invitations, training materials and school setup. Avoid making every onboarding a custom manual project.

Consider a one-time onboarding or digitisation fee for work beyond standard setup. The exact fee and included service levels remain open and must be tested with schools.

Physical presence is important during early pilots and selected implementation milestones. Long-term scale requires remote support, documented processes, training resources and a trained implementation/customer-success team.

### 37.11 Revised cost and unit-economics framework

ACADIVA must calculate the cost of serving a school, not only the subscription revenue.

Track costs in six categories:

1. Technology: hosting, database, storage, backups, security, monitoring and app distribution.
2. Product development: web, Android, iOS, offline sync, maintenance, testing and upgrades.
3. Communications: SMS, email, push delivery and support for delivery failures.
4. Payments: gateway fees, reconciliation, refunds, disputes and payment support.
5. Onboarding: data migration, configuration, training, travel and go-live assistance.
6. Customer success and sales: support hours, school visits, field representatives, training and retention.

Model the economics at 1, 10, 50 and 100 schools, using different school sizes and usage patterns. Include:

- Monthly recurring revenue by plan.
- Variable infrastructure and storage cost per school.
- Communication cost and who funds it.
- Payment processing cost and settlement model.
- One-time onboarding cost and revenue.
- Support hours and travel cost per school.
- Development and maintenance allocation.
- Gross margin per school and at each scale.
- Cash needed before subscriptions are collected.
- Churn and renewal sensitivity.

The existing Section 35 operating-cost estimates are planning assumptions, not verified vendor quotations or final unit economics. Revisit them as architecture, actual usage and vendor pricing become known.

Three operating questions must be answered before scaling the team:

- What does it cost to onboard one school?
- What does it cost to serve one school each month?
- How many schools can one trained implementation/support person manage without service quality falling?

### 37.12 Product and delivery priorities resulting from this revision

The full ACADIVA vision remains broad, but the first release must prove dependable daily use.

Priority changes and emphasis:

- Treat proprietor visibility, collections, outstanding fees and operational accountability as core buying-value workflows.
- Treat role-based simplicity as a foundational product requirement, not a later visual polish task.
- Include mobile application planning in the architecture and product roadmap.
- Design attendance and assessment data flows for offline capture and safe synchronisation from the start.
- Prioritise offline capability for attendance and marks before attempting offline support across every module.
- Build school onboarding, import and training processes as part of the product and operating model.
- Include adoption analytics and incomplete-work indicators so ACADIVA can identify schools and roles that are not using the system.
- Make exports, backups, recovery and school offboarding part of the trust proposition.
- Use one carefully selected pilot school to test complete end-to-end operations before broad rollout.
- Validate pricing and support boundaries against real school behaviour and delivery cost.

This revision does not authorise building every proposed feature immediately. Release sequencing should be adjusted through pilot evidence, technical feasibility and unit economics.

### 37.13 Pilot acceptance and evidence requirements

A pilot should not be declared successful because the school has accounts or because the proprietor likes the dashboard.

Minimum evidence to collect:

- Proprietor or authorised owner uses management dashboard during the pilot.
- Principal completes agreed operational workflows.
- Teachers independently complete attendance and assessment tasks.
- Bursar records payments and can reconcile the resulting records.
- Parent accounts are linked correctly and parents can access only their own children.
- Reports and receipts match the underlying records.
- Offline attendance/marks, where included in the pilot, synchronise without silent loss or duplication.
- Staff can perform routine tasks without ACADIVA personnel doing the work for them.
- The school can export agreed records.
- Support volume and onboarding effort are measured.
- The school provides structured feedback.
- A paid continuation decision is obtained; free usage alone is not proof of willingness to pay.

### 37.14 Open decisions and validation items

The following remain proposals or questions, not final decisions:

- Exact pilot-school selection criteria, pilot duration and whether the pilot is paid or subsidised.
- Which modules are included in the first pilot.
- Final offline scope and conflict-resolution rules.
- Whether teacher and parent experiences ship as separate mobile apps or one role-aware app.
- Android and iOS release sequence and device support policy.
- Data retention, local cache expiry and device-loss response.
- Exact onboarding packages and one-time fees.
- Included support hours, visit limits and service-level commitments.
- SMS allowance and billing model.
- Final subscription pricing after willingness-to-pay tests.
- Staffing model, field-sales compensation and support capacity.
- Case-study consent and use of school name, logo and performance data.
- Final technical architecture and actual monthly cost at different school counts.

### 37.15 Guiding principle

ACADIVA must not merely be more digital than a paper-based school. It must make the school's work easier, its records more dependable, its management more informed and its communication more organised.

The software, mobile experience, offline capability, onboarding service, field sales and customer support are parts of one product promise. The school should feel supported from the first demonstration through implementation and everyday use.

The ambition is large, but the proof must begin with one school that uses ACADIVA properly, sees measurable value and chooses to keep paying for it.

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

## 40. ACADIVA master product, workflow, design and launch checklist — 15 November 2026

### How to use this checklist

This is the master verification checklist for ACADIVA. It consolidates requirements and decisions from the available ACADIVA discussions, including the full product vision, role-based experiences, school operations, finance, communications, infrastructure, UI/UX, pilot and future roadmap.

- [ ] Not started
- [ ] In progress
- [ ] Implemented but not tested
- [ ] Tested and accepted
- [ ] Blocked / decision required
- [ ] Not applicable to this release

A checked item means evidence exists: an approved design, working implementation, test result, configuration record or signed-off operational procedure. A screen existing is not proof that the workflow works.

For each item, record owner, requirement ID, target release, dependencies, evidence link and last-reviewed date in the working project tracker. Do not mark an item complete based on intention.

<b>Scope labels:</b> Core = required for the initial useful school-management product; Pilot = needed for controlled school pilot; Later = planned after core validation; Future = strategic roadmap, not a launch promise.

### A. Product purpose, users and school setup

- [ ] A01. Define ACADIVA as a connected School Management Operating System, not merely a school website or result checker. (Core)
- [ ] A02. Document the problems solved: fragmented paper records, spreadsheets, manual attendance, manual results, fee notebooks, disconnected communication and poor management visibility. (Core)
- [ ] A03. Define measurable outcomes for schools: faster work, fewer record errors, better visibility, accountable processes and easier parent communication. (Pilot)
- [ ] A04. Define target initial customer: Nigerian nursery, primary, junior secondary and senior secondary private schools, especially small and growing schools. (Core)
- [ ] A05. Define the school onboarding and eligibility criteria for the first pilot. (Pilot)
- [ ] A06. Support creation of a school account and unique school identity. (Core)
- [ ] A07. Support school name, logo, address, contact details and school type. (Core)
- [ ] A08. Support school session, term, calendar, working days and holidays configuration. (Core)
- [ ] A09. Support school-specific grading, fee, attendance and report-card settings. (Core)
- [ ] A10. Support separate branded school portal/subdomain, with tenant isolation. (Core)
- [ ] A11. Reserve school subdomain names and prevent duplicate or impersonating slugs. (Core)
- [ ] A12. Support more than one campus/branch under one school organisation when enabled. (Later)
- [ ] A13. Provide school setup progress and identify incomplete configuration. (Core)
- [ ] A14. Provide school data import, validation and onboarding checklist. (Pilot)
- [ ] A15. Define school data ownership, export, offboarding and continuity commitments. (Core)

### B. Roles, accounts and access

- [ ] B01. Define proprietor/owner role and permissions. (Core)
- [ ] B02. Define principal role and permissions. (Core)
- [ ] B03. Define vice principal role and permissions. (Core)
- [ ] B04. Define school administrator/secretary role and permissions. (Core)
- [ ] B05. Define registrar/admissions officer role and permissions. (Core)
- [ ] B06. Define bursar/accountant role and permissions. (Core)
- [ ] B07. Define teacher role and permissions. (Core)
- [ ] B08. Define parent/guardian role and permissions. (Core)
- [ ] B09. Define student role and permissions where student accounts are enabled. (Later)
- [ ] B10. Define school ICT administrator role and permissions. (Core)
- [ ] B11. Support one person holding multiple approved roles without mixing permissions. (Core)
- [ ] B12. Support one user belonging to more than one school only through explicit school memberships. (Later)
- [ ] B13. Define invitation, acceptance, expiry and resend workflows. (Core)
- [ ] B14. Support Google sign-in and secure account linking. (Core)
- [ ] B15. Support email/password login and secure password reset. (Core)
- [ ] B16. Define phone-number verification and recovery policy. (Pilot)
- [ ] B17. Support account activation, suspension, deactivation and staff exit. (Core)
- [ ] B18. Revoke access promptly when staff membership or role is removed. (Core)
- [ ] B19. Require server-side authorisation and tenant-scoped database policies, not just hidden interface buttons. (Core)
- [ ] B20. Test that users cannot access another school's records by changing IDs or URLs. (Core)
- [ ] B21. Require MFA for internal ACADIVA Operations accounts and other high-privilege accounts; define rollout and recovery controls. (Core for internal operations; Pilot for school roles)
- [ ] B22. Provide session/device management and secure sign-out. (Pilot)

### C. Proprietor / owner experience

- [ ] C01. Create a dedicated proprietor dashboard, not a copy of the teacher or principal dashboard. (Core)
- [ ] C02. Show total enrolled students and enrolment changes. (Core)
- [ ] C03. Show new admissions, pending applications and admission conversion. (Core)
- [ ] C04. Show total fees billed for the selected period. (Core)
- [ ] C05. Show amount collected and outstanding balances. (Core)
- [ ] C06. Show payments received today, this week and this term. (Core)
- [ ] C07. Separate confirmed online payments from manually recorded payments. (Core)
- [ ] C08. Clearly label pending, failed, reversed, refunded and unverified transactions. (Core)
- [ ] C09. Show collection rate and outstanding fees by class/arm. (Core)
- [ ] C10. Show attendance overview and attendance concerns. (Core)
- [ ] C11. Show teacher attendance/result-submission status where configured. (Core)
- [ ] C12. Show classes with missing attendance or incomplete marks. (Core)
- [ ] C13. Show key staff and school operational summary. (Core)
- [ ] C14. Show pending approvals and tasks requiring proprietor attention. (Core)
- [ ] C15. Show trends across sessions/terms without misleading comparisons. (Later)
- [ ] C16. Allow drill-down from a summary figure to the underlying authorised records. (Core)
- [ ] C17. Show when dashboard data was last updated and whether any source data is incomplete. (Core)
- [ ] C18. Avoid presenting unrecorded cash as if the system knows it was received. (Core)
- [ ] C19. Restrict sensitive staff/student details to authorised access. (Core)
- [ ] C20. Provide a concise mobile-friendly proprietor view. (Pilot)

### D. Principal and vice-principal experience

- [ ] D01. Create a principal dashboard focused on daily school operations and academics. (Core)
- [ ] D02. Show today's attendance completion by class and teacher. (Core)
- [ ] D03. Show absent students and registers not yet submitted; do not make routine late-coming capture a core workflow. (Core)
- [ ] D04. Show classes/subjects with pending attendance. (Core)
- [ ] D05. Show timetable and today's lessons/events. (Core)
- [ ] D06. Show assessment and result submission progress. (Core)
- [ ] D07. Show classes with missing or incomplete marks. (Core)
- [ ] D08. Review/approve results before publication where school policy requires it. (Core)
- [ ] D09. Review attendance corrections and exceptional cases. (Core)
- [ ] D10. See teacher workload and assigned classes/subjects. (Core)
- [ ] D11. See admissions and student movement requiring action. (Core)
- [ ] D12. See important notices, meetings and upcoming school events. (Core)
- [ ] D13. Assign and follow up operational tasks. (Later)
- [ ] D14. Configure which principal actions require proprietor approval. (Core)
- [ ] D15. Provide vice-principal permissions that can be independently configured. (Core)

### E. Administrator, secretary and registrar experience

- [ ] E01. Create a role-specific admin workspace with clear navigation. (Core)
- [ ] E02. Register new students and update existing student records. (Core)
- [ ] E03. Manage admissions applications and applicant status. (Core)
- [ ] E04. Generate admission numbers using a configurable format. (Core)
- [ ] E05. Assign students to academic session, class and arm. (Core)
- [ ] E06. Link parents/guardians to the correct students. (Core)
- [ ] E07. Check for duplicate student records before creating a new record. (Core)
- [ ] E08. Upload and manage required student documents. (Pilot)
- [ ] E09. Manage student transfers, withdrawals and exits with history. (Core)
- [ ] E10. Manage staff directory and staff profile updates within permission limits. (Core)
- [ ] E11. Manage school calendar, holidays, events and notices. (Core)
- [ ] E12. Manage school settings and approved templates. (Core)
- [ ] E13. Generate class lists, student lists and authorised exports. (Core)
- [ ] E14. Provide bulk import with preview, validation and error report. (Core)
- [ ] E15. Provide bulk actions with confirmation and an audit trail. (Core)

### F. Bursar, accountant and finance administration

- [ ] F01. Create a finance workspace separate from general school administration. (Core)
- [ ] F02. Configure fee categories and charge descriptions. (Core)
- [ ] F03. Configure fees by class, arm, session, term or student where authorised. (Core)
- [ ] F04. Support optional charges, discounts, scholarships and approved concessions. (Pilot)
- [ ] F05. Generate invoices/statements for students. (Core)
- [ ] F06. Show each student's billed, paid, outstanding and overdue amount. (Core)
- [ ] F07. Record cash payments with date, amount, payer, reference and staff actor. (Core)
- [ ] F08. Record bank-transfer payments with reference and verification state. (Core)
- [ ] F09. Distinguish manually entered payments from provider-confirmed online payments. (Core)
- [ ] F10. Require appropriate approval/verification for manual payment entries. (Core)
- [ ] F11. Generate receipts only when payment status meets the school's defined confirmation rule. (Core)
- [ ] F12. Support partial payments and instalment schedules if enabled. (Core)
- [ ] F13. Support payment allocation across fee items and outstanding balances. (Core)
- [ ] F14. Support refunds, reversals, waivers and adjustments with reasons and approvals. (Pilot)
- [ ] F15. Maintain a payment ledger and immutable audit history. (Core)
- [ ] F16. Reconcile provider transactions with invoices and student accounts. (Core)
- [ ] F17. Show daily, weekly, termly and session collection summaries. (Core)
- [ ] F18. Export finance reports with role-based restrictions. (Core)
- [ ] F19. Prevent unauthorised editing or deletion of confirmed payment records. (Core)
- [ ] F20. Provide payment reminders for overdue fees, with configurable timing and channels. (Pilot)

### G. Teacher workspace and daily teaching workflow

- [ ] G01. Create a dedicated teacher dashboard showing only assigned work and permitted records. (Core)
- [ ] G02. Show teacher profile, department and assigned classes. (Core)
- [ ] G03. Show assigned subjects for each class/arm. (Core)
- [ ] G04. Show today's timetable and upcoming lessons. (Core)
- [ ] G05. Show weekly timetable. (Core)
- [ ] G06. Show class lists for each assigned class/subject. (Core)
- [ ] G07. Allow a teacher to open a class and immediately see the relevant actions. (Core)
- [ ] G08. Allow attendance marking from the class list. (Core)
- [ ] G09. Provide a safe “Mark all present” action, with a review step and ability to change exceptions. (Core)
- [ ] G10. Allow individual student status changes from present to absent, with an optional school-approved excused status only if required. (Core)
- [ ] G11. Show students not yet marked and prevent accidental silent omission. (Core)
- [ ] G12. Save attendance with clear saved/syncing/failed status. (Core)
- [ ] G13. Allow authorised correction of attendance with reason and audit history. (Core)
- [ ] G14. Allow teacher to enter assessment scores for assigned students and subjects. (Core)
- [ ] G15. Display maximum mark and assessment weighting clearly. (Core)
- [ ] G16. Validate marks and flag missing, duplicate or out-of-range entries. (Core)
- [ ] G17. Save drafts and resume incomplete mark entry. (Core)
- [ ] G18. Submit marks for review and show submission status. (Core)
- [ ] G19. Prevent teacher from changing another teacher's unassigned class/subject records. (Core)
- [ ] G20. Show feedback or returned corrections from principal/admin. (Core)
- [ ] G21. View permitted student academic history and learning concerns. (Pilot)
- [ ] G22. Show a subtle, non-blocking birthday reminder for an assigned student only on that student's birthday; no permanent birthday calendar or extra data entry. (Pilot)
- [ ] G23. View student notes/approved support information only where authorised. (Later)
- [ ] G24. Homework/classwork posting is optional future scope and must not appear as a required teacher task. (Future)
- [ ] G25. Share class announcements through approved channels. (Pilot)
- [ ] G26. View teacher's own attendance/leave records where enabled. (Later)
- [ ] G27. Access the workspace easily on a phone or tablet. (Core)
- [ ] G28. Support offline attendance and draft marks for previously authorised/cached classes, with safe sync. (Later)
- [ ] G29. Make common teacher actions achievable in a few clear steps. (Core)
- [ ] G30. Show teacher a task list: attendance due, marks due, timetable changes and notices. (Core)

### H. Parent and guardian portal

- [ ] H01. Create a parent/guardian dashboard with only their linked children's information. (Core)
- [ ] H02. Support one guardian linked to multiple children. (Core)
- [ ] H03. Show each child's name, class, arm and school identity. (Core)
- [ ] H04. Show attendance summary and authorised attendance details. (Core)
- [ ] H05. Show published results and report cards. (Core)
- [ ] H06. Show fee invoices, amount paid and outstanding balance. (Core)
- [ ] H07. Allow online payment through the configured provider. (Core)
- [ ] H08. Show payment history, confirmation and downloadable receipts. (Core)
- [ ] H09. Clearly distinguish pending payment from successful payment. (Core)
- [ ] H10. Show school announcements, notices and emergency messages. (Core)
- [ ] H11. Show PTA meetings, events and meeting details. (Pilot)
- [ ] H12. Show timetable and school calendar information where enabled. (Pilot)
- [ ] H13. Show homework/classwork when that module is introduced. (Later)
- [ ] H14. Provide secure contact/update request process for guardian details. (Pilot)
- [ ] H15. Provide notification preferences for in-app, email and SMS channels. (Pilot)
- [ ] H16. Ensure a guardian cannot access another family's student records. (Core)
- [ ] H17. Provide a simple mobile-first experience. (Core)
- [ ] H18. Provide access to school contact information and approved policies. (Pilot)

### I. Student records, profile and birthdays

- [ ] I01. Store unique student ID/admission number. (Core)
- [ ] I02. Store full name and preferred display name if used by school. (Core)
- [ ] I03. Store date of birth and calculate age accurately. (Core)
- [ ] I04. Store gender only where required for legitimate school administration. (Core)
- [ ] I05. Store class, arm, session and enrolment status. (Core)
- [ ] I06. Store guardian contacts and verified relationship. (Core)
- [ ] I07. Store emergency contact and authorised pickup information where required. (Pilot)
- [ ] I08. Store admission date and previous school details where supplied. (Pilot)
- [ ] I09. Store medical/emergency notes only with strict access controls and appropriate policy. (Later)
- [ ] I10. Store student photo as optional, compressed, private media; do not require large image files. (Pilot)
- [ ] I11. Provide student profile with academic, attendance and fee sections according to role. (Core)
- [ ] I12. Show upcoming birthdays by day/month and class list, without exposing unnecessary personal data. (Pilot)
- [ ] I13. Provide configurable birthday reminders/celebration notices if school enables them. (Later)
- [ ] I14. Maintain historical class/session progression. (Core)
- [ ] I15. Support transfer, withdrawal, graduation and archival status. (Core)
- [ ] I16. Prevent duplicate records and provide a controlled merge process. (Pilot)

### J. Classes, arms, subjects, staff assignment and timetable

- [ ] J01. Configure school levels: nursery, primary, JSS and SSS as applicable. (Core)
- [ ] J02. Configure class names and class arms (e.g. Primary 3A, Primary 3B). (Core)
- [ ] J03. Configure subjects per class/level. (Core)
- [ ] J04. Configure academic sessions and terms. (Core)
- [ ] J05. Assign teachers to classes. (Core)
- [ ] J06. Assign teachers to specific subjects and class arms. (Core)
- [ ] J07. Define who can create and change teacher assignments; authorised school admin/principal, not teachers themselves by default. (Core)
- [ ] J08. Allow principal/admin to review assignments before they become active. (Pilot)
- [ ] J09. Prevent timetable conflicts for teachers, classes and rooms where room scheduling is enabled. (Pilot)
- [ ] J10. Create weekly timetable by class. (Core)
- [ ] J11. Create teacher-specific timetable. (Core)
- [ ] J12. Show timetable changes and notify affected users. (Pilot)
- [ ] J13. Support breaks, assembly, activities and non-teaching periods. (Core)
- [ ] J14. Support printable timetable exports. (Core)
- [ ] J15. Support substitute teacher assignment and change history. (Later)

### K. Attendance and school-day management

- [ ] K01. Use daily class attendance as the initial default; do not build lesson-by-lesson attendance unless pilot evidence proves it is necessary. (Core)
- [ ] K02. Define the simple default statuses: present and absent; add excused only if the pilot school requires it. Routine late-coming is excluded from the teacher register. (Core)
- [ ] K03. Provide class register with student names and clear status controls. (Core)
- [ ] K04. Provide “Mark all present” then exception editing. (Core)
- [ ] K05. Show total students, present, absent and unmarked counts before submission; do not include a routine late-coming count. (Core)
- [ ] K06. Require confirmation before bulk attendance submission. (Core)
- [ ] K07. Prevent duplicate attendance records for the same student/date/period. (Core)
- [ ] K08. Identify repeated absences only where the school has a clear follow-up process; do not create late-coming analytics in the initial product. (Pilot)
- [ ] K09. Exclude late-arrival and early-departure capture from the initial product; reconsider a separate office-controlled exception only if pilot schools demonstrate a genuine requirement. (Future)
- [ ] K10. Record who took attendance and when. (Core)
- [ ] K11. Allow approved correction with reason and audit trail. (Core)
- [ ] K12. Show attendance completion dashboard to principal/admin. (Core)
- [ ] K13. Show relevant attendance to parents. (Core)
- [ ] K14. Generate attendance summaries and exports. (Core)
- [ ] K15. Support offline attendance entry and safe synchronisation in a later mobile release. (Later)

### L. Assessments, grading, results and report cards

- [ ] L01. Configure only the assessment components a school actually uses (initially tests/CA and examinations; assignment/practical scores are optional configured mark components, not a separate homework-management workflow). (Core)
- [ ] L02. Configure mark maximums and weights by school/level/subject. (Core)
- [ ] L03. Configure grading scales and grade descriptions. (Core)
- [ ] L04. Configure comments/remarks and teacher evaluation fields. (Core)
- [ ] L05. Enter and edit marks only within authorised assignment and submission windows. (Core)
- [ ] L06. Validate marks and calculate totals/averages correctly. (Core)
- [ ] L07. Support missing mark, absent-from-exam and exempt states without treating them as zero automatically. (Core)
- [ ] L08. Calculate grades using the configured school rules. (Core)
- [ ] L09. Calculate class position/ranking only if school policy enables it and rules are explicit. (Pilot)
- [ ] L10. Support teacher remarks and principal comments. (Core)
- [ ] L11. Provide result submission, review, correction and approval workflow. (Core)
- [ ] L12. Lock approved/published results against silent modification. (Core)
- [ ] L13. Publish results to parent/student portal only when authorised. (Core)
- [ ] L14. Generate report cards in branded A4 PDF format. (Core)
- [ ] L15. Include school logo, letterhead, colours, authorised signatures and stamp area. (Core)
- [ ] L16. Support print/download and controlled reprint history. (Core)
- [ ] L17. Maintain historical results across sessions and terms. (Core)
- [ ] L18. Generate consolidated transcripts and cumulative academic summaries with grading context and authorised issuance. (Core; see Section 44)
- [ ] L19. Identify excellent, weak, improving and declining performance patterns. (Pilot)
- [ ] L20. Identify subject-level strengths and weaknesses. (Pilot)
- [ ] L21. Identify attendance-related performance concerns. (Pilot)
- [ ] L22. Give teachers/principals useful performance intelligence without unsupported AI claims. (Pilot)
- [ ] L23. Support configurable benchmarks for progression decisions. (Pilot)

### M. Promotion, progression and student movement

- [ ] M01. Configure promotion rules at the end of each academic session. (Pilot)
- [ ] M02. Support automatic promotion for students meeting the school's configured rules. (Pilot)
- [ ] M03. Hold below-benchmark students for review rather than promoting automatically. (Pilot)
- [ ] M04. Allow authorised teacher/principal recommendation or exception with documented reason. (Pilot)
- [ ] M05. Require approval for exceptional promotion, repetition or other progression decision. (Pilot)
- [ ] M06. Preview proposed promotion list before committing changes. (Pilot)
- [ ] M07. Prevent duplicate or accidental promotion. (Pilot)
- [ ] M08. Preserve previous class and session history. (Core)
- [ ] M09. Produce promotion/repetition reports. (Pilot)
- [ ] M10. Support transfer between arms/classes with history and authorisation. (Core)

### N. Fees, payments and finance experience

- [ ] N01. Configure fees per session/term/class/student. (Core)
- [ ] N02. Generate fee invoices and statements. (Core)
- [ ] N03. Display all students with payment status in a clear register. (Core)
- [ ] N04. Show counts and totals for fully paid, partially paid, unpaid and overdue students. (Core)
- [ ] N05. Provide a “mark all paid” action only for a specific, verified batch/payment event, never as a blind bulk toggle. (Core)
- [ ] N06. For bulk payment import, validate each student, amount, reference and allocation before posting. (Core)
- [ ] N07. Show exceptions and unmatched payments before final confirmation. (Core)
- [ ] N08. Require confirmation and audit record for bulk updates. (Core)
- [ ] N09. Never let “all students paid” be inferred from a button press without evidence or a defined authorised manual attestation. (Core)
- [ ] N10. Show payment date, method, reference, amount and recording actor. (Core)
- [ ] N11. Support partial instalments and remaining balance. (Core)
- [ ] N12. Support approved discounts, scholarships and waivers. (Pilot)
- [ ] N13. Generate branded receipts and statements as A4/downloadable PDFs. (Core)
- [ ] N14. Integrate payment gateway checkout and server-side verification. (Pilot)
- [ ] N15. Handle duplicate webhooks and idempotency. (Pilot)
- [ ] N16. Reconcile provider reports with ACADIVA ledger. (Pilot)
- [ ] N17. Track failed, pending, reversed and refunded payments. (Pilot)
- [ ] N18. Provide payment reminders and school-defined due dates. (Pilot)
- [ ] N19. Provide school finance summaries and exports. (Core)
- [ ] N20. Keep ACADIVA subscription revenue separate from school fee collections. (Core)
- [ ] N21. Define school settlement arrangement and avoid ACADIVA holding school funds without an approved legal/payment model. (Core)
- [ ] N22. Create a premium wallet-inspired payment view with clear balance/invoice/receipt status, without implying ACADIVA is a bank or custodian. (Pilot)

### O. Communication, notifications and school calendar

- [ ] O01. Build a central in-app notification centre. (Core)
- [ ] O02. Support role-targeted notifications for teachers, parents, admins and management. (Core)
- [ ] O03. Support school-wide, class-specific and individual announcements. (Core)
- [ ] O04. Configure transactional email provider and verify sending domain. (Pilot)
- [ ] O05. Configure Google OAuth correctly for sign-in, including redirect URLs and environment separation. (Core)
- [ ] O06. Configure SMS provider, sender ID and Nigerian delivery routes. (Pilot)
- [ ] O07. Test SMS delivery, delivery reports, DND handling and cost controls. (Pilot)
- [ ] O08. Build message templates for invitations, admissions, fee reminders, receipts and announcements. (Pilot)
- [ ] O09. Support notification preferences and consent where applicable. (Pilot)
- [ ] O10. Queue notifications so message failure does not undo the underlying school action. (Core)
- [ ] O11. Retry failed messages safely and avoid duplicate sends. (Core)
- [ ] O12. Maintain message delivery history and failure status. (Pilot)
- [ ] O13. Support school calendar, holidays, term dates and events. (Core)
- [ ] O14. Support PTA meeting scheduling and parent notifications. (Pilot)
- [ ] O15. Support meeting invitations, agenda/details and follow-up notices. (Later)
- [ ] O16. Support birthday reminders/announcements only according to school preference and privacy settings. (Later)
- [ ] O17. Add push notifications when the mobile app is introduced. (Later)

### P. Admissions, school website and public-facing experience

- [ ] P01. Provide a public school profile/website with school-approved content. (Pilot)
- [ ] P02. Support branded school subdomain and public contact information. (Core)
- [ ] P03. Provide online enquiry/admission application form. (Later)
- [ ] P04. Route new applications to registrar/admin dashboard. (Later)
- [ ] P05. Track applicant status from enquiry to admission decision. (Later)
- [ ] P06. Generate admission letters using branded A4 PDF templates. (Later)
- [ ] P07. Allow school to publish approved announcements/events publicly if desired. (Later)
- [ ] P08. Ensure private student data never appears on public school pages. (Core)

### Q. Reports, documents and data portability

- [ ] Q01. Configure school branding once and reuse it across generated documents. (Core)
- [ ] Q02. Generate branded results/report cards. (Core)
- [ ] Q03. Generate branded receipts. (Core)
- [ ] Q04. Generate branded invoices/statements. (Core)
- [ ] Q05. Generate admission letters. (Later)
- [ ] Q06. Generate authorised transcripts and academic history documents. (Core; see Section 44)
- [ ] Q07. Generate attendance summaries. (Core)
- [ ] Q08. Generate class lists and student registers. (Core)
- [ ] Q09. Generate finance reports. (Core)
- [ ] Q10. Provide CSV/XLSX export with permission checks. (Core)
- [ ] Q11. Provide data import preview, validation and row-level error report. (Core)
- [ ] Q12. Preserve document generation/reprint history where it matters. (Pilot)
- [ ] Q13. Ensure exports are complete, correctly formatted and usable outside ACADIVA. (Core)

### R. Mobile, offline and device experience

- [ ] R01. Deliver responsive web experience for school management and administration. (Core)
- [ ] R02. Deliver a practical mobile experience for teachers and parents. (Core)
- [ ] R03. Decide one role-aware mobile app versus separate apps based on validated workflow needs. (Open decision)
- [ ] R04. Support Android and iOS strategy. (Core)
- [ ] R05. Evaluate affordable Android tablets for teacher use; iPads are not assumed to be necessary. (Pilot)
- [ ] R06. Cache previously authorised class lists securely. (Later)
- [ ] R07. Allow offline attendance entry for eligible cached classes. (Later)
- [ ] R08. Allow offline draft mark entry where safe. (Later)
- [ ] R09. Show offline, syncing, synced and failed states clearly. (Later)
- [ ] R10. Prevent duplicate records during retries and sync. (Later)
- [ ] R11. Detect conflicts and require controlled resolution where needed. (Later)
- [ ] R12. Revalidate permissions and data on the server during sync. (Later)
- [ ] R13. Expire or revoke cached data when access is removed. (Later)
- [ ] R14. Test app closure/restart and unreliable network recovery. (Later)
- [ ] R15. Define supported device sizes and minimum OS/browser versions. (Pilot)

### S. Design system, brand and visual quality

- [ ] S01. Complete reference research using UI/UX inspiration banks such as Mobbin, Refero, Screenlane, SaaSFrame and Page Flows. (Core)
- [ ] S02. Review Apple Human Interface Guidelines and other relevant design standards. (Core)
- [ ] S03. Build separate reference boards for brand, proprietor/admin dashboard, teacher mobile, parent portal and finance/payment. (Core)
- [ ] S04. Define ACADIVA brand personality and visual principles. (Core)
- [ ] S05. Explore a distinctive brand colour palette and gradient system. (Core)
- [ ] S06. Approve exact colour tokens only after contrast and usability testing. (Core)
- [ ] S07. Define light theme as a primary visual direction. (Core)
- [ ] S08. Define a considered dark theme, not merely invert all colours. (Pilot)
- [ ] S09. Define theme switching and persistence rules. (Pilot)
- [ ] S10. Define semantic colours for success, warning, error, pending and neutral states. (Core)
- [ ] S11. Define typography inspired by Apple's bold, confident advertising style without copying proprietary assets. (Core)
- [ ] S12. Test platform-native system typography and suitable cross-platform font alternatives. (Core)
- [ ] S13. Define type scale for display, page title, section title, body, label, caption and numeric data. (Core)
- [ ] S14. Define spacing, grid, radius, border, shadow, blur and elevation tokens. (Core)
- [ ] S15. Use glassmorphism selectively for overlays, navigation accents and special surfaces. (Core)
- [ ] S16. Avoid excessive glass panels that harm readability or make screens cumbersome. (Core)
- [ ] S17. Define iconography and illustration rules. (Core)
- [ ] S18. Build reusable Figma component library and variants. (Core)
- [ ] S19. Design responsive breakpoints and mobile navigation. (Core)
- [ ] S20. Design accessible focus, hover, pressed, disabled and error states. (Core)
- [ ] S21. Design empty, loading, skeleton, offline, syncing and failure states for every major workflow. (Core)
- [ ] S22. Design clean, low-clutter dashboards with clear task hierarchy. (Core)
- [ ] S23. Design finance experience with premium black/dark wallet-inspired card or ID-pass elements. (Pilot)
- [ ] S24. Design payment flow inspired by Apple Wallet/Apple Pay clarity, without copying Apple branding or implying Apple Pay availability. (Pilot)
- [ ] S25. Design transaction timeline and receipt states for pending, successful, failed and refunded payments. (Pilot)
- [ ] S26. Design A4 branded PDF templates and print styles. (Core)
- [ ] S27. Prototype critical workflows and test with actual school users. (Pilot)
- [ ] S28. Create design-to-development handoff and implementation QA checklist. (Core)
- [ ] S29. Review screens for realistic Nigerian names, class labels, currency, dates and long school names. (Core)
- [ ] S30. Reject generic AI-looking templates, decorative clutter and charts without real data meaning. (Core)

### T. Engineering, infrastructure and integration setup

- [ ] T01. Create founder/company-controlled domain registrar account and secure domain ownership. (Core)
- [ ] T02. Configure DNS, HTTPS and school subdomain routing. (Core)
- [ ] T03. Create private GitHub organisation/repository. (Core)
- [ ] T04. Configure branch protection and pull request reviews. (Core)
- [ ] T05. Configure ChatGPT Plus/Codex engineering workflow and repository instructions. (Core)
- [ ] T06. Configure TypeScript, Next.js and web project foundation. (Core)
- [ ] T07. Configure Expo/React Native project when mobile phase begins. (Later)
- [ ] T08. Configure Supabase PostgreSQL and Auth. (Core)
- [ ] T09. Design tenant-aware schema, foreign keys, indexes and constraints. (Core)
- [ ] T10. Implement and test RLS policies for every tenant-owned table. (Core)
- [ ] T11. Configure private Storage buckets and access rules. (Core)
- [ ] T12. Separate development, staging and production credentials and data. (Core)
- [ ] T13. Configure version-controlled database migrations. (Core)
- [ ] T14. Configure Netlify or the approved single production hosting provider. (Core)
- [ ] T15. Evaluate Cloudflare DNS/edge protection. (Pilot)
- [ ] T16. Configure Sentry for frontend, backend and later mobile error monitoring. (Core)
- [ ] T17. Configure Sentry release tracking, alert rules and privacy scrubbing. (Core)
- [ ] T18. Configure PostHog event taxonomy and product analytics. (Pilot)
- [ ] T19. Configure uptime monitoring and incident alerts. (Pilot)
- [ ] T20. Configure transactional email provider, domain authentication and templates. (Pilot)
- [ ] T21. Configure SMS provider, sender ID, templates and delivery reporting. (Pilot)
- [ ] T22. Configure payment provider sandbox and webhook verification. (Pilot)
- [ ] T23. Configure GitHub Actions for lint, type check, tests and build. (Core)
- [ ] T24. Configure dependency and secret scanning. (Core)
- [ ] T25. Configure encrypted database and file backup processes. (Core)
- [ ] T26. Perform a restore test and document results. (Core)
- [ ] T27. Configure environment variables securely; never commit secrets. (Core)
- [ ] T28. Configure audit logging and operational logs. (Core)
- [ ] T29. Configure notification queue, retry and idempotency controls. (Pilot)
- [ ] T30. Define deployment, rollback and incident runbooks. (Core)

### U. Quality, security, privacy and operational readiness

- [ ] U01. Maintain a requirement ID and traceability record for every feature. (Core)
- [ ] U02. Link each requirement to role, screen, workflow, data, permission, integration and test. (Core)
- [ ] U03. Write unit tests for calculations and business rules. (Core)
- [ ] U04. Write integration tests for database operations and external providers. (Core)
- [ ] U05. Write end-to-end tests for critical school workflows. (Core)
- [ ] U06. Test role permissions and cross-school isolation. (Core)
- [ ] U07. Test payment reconciliation and duplicate webhook handling. (Pilot)
- [ ] U08. Test bulk attendance and bulk payment safeguards. (Core)
- [ ] U09. Test imports, exports, PDF rendering and document accuracy. (Core)
- [ ] U10. Test mobile responsiveness and supported browsers/devices. (Core)
- [ ] U11. Review child-data privacy and Nigeria Data Protection Act/NDPC obligations with qualified advice. (Core)
- [ ] U12. Define data minimisation, retention, deletion and access procedures. (Core)
- [ ] U13. Restrict student images, documents, health notes and sensitive records. (Core)
- [ ] U14. Redact sensitive information from Sentry, PostHog and logs. (Core)
- [ ] U15. Define incident response and school notification procedure. (Core)
- [ ] U16. Define support ownership and escalation. (Pilot)
- [ ] U17. Define school data export and offboarding process. (Core)
- [ ] U18. Define backup retention and recovery objectives. (Core)
- [ ] U19. Monitor actual infrastructure usage and establish warning thresholds. (Core)
- [ ] U20. Review vendor pricing, limits, data handling and exit options before procurement. (Core)

### V. Pilot, onboarding, adoption and commercial readiness

- [ ] V01. Select pilot schools with engaged decision-makers and participating staff. (Pilot)
- [ ] V02. Observe current school workflows before configuring the product. (Pilot)
- [ ] V03. Record baseline time and error rates for selected tasks. (Pilot)
- [ ] V04. Agree which modules are included in the pilot. (Pilot)
- [ ] V05. Clean and migrate student, guardian, staff and academic data. (Pilot)
- [ ] V06. Configure classes, arms, subjects and teacher assignments with school approval. (Pilot)
- [ ] V07. Configure grading and fee rules with the school's authorised officers. (Pilot)
- [ ] V08. Train proprietor, principal, bursar, registrar, administrators and teachers by role. (Pilot)
- [ ] V09. Provide parent onboarding instructions and support. (Pilot)
- [ ] V10. Monitor real usage during the first live period. (Pilot)
- [ ] V11. Track attendance completion, result completion and fee-record accuracy. (Pilot)
- [ ] V12. Track parent activation and staff independence. (Pilot)
- [ ] V13. Track support requests, repeated confusion and workflow abandonment. (Pilot)
- [ ] V14. Measure time to prepare results and retrieve student records. (Pilot)
- [ ] V15. Collect school feedback and resolve usability problems. (Pilot)
- [ ] V16. Obtain permission before using school name, logo, data or results as a case study. (Pilot)
- [ ] V17. Define onboarding/digitisation fees and what is included. (Pilot)
- [ ] V18. Validate subscription pricing with actual school willingness to pay. (Pilot)
- [ ] V19. Track acquisition cost, onboarding cost and monthly cost to serve each school. (Pilot)
- [ ] V20. Define support response expectations that the team can realistically meet. (Pilot)

### W. Pricing, billing and infrastructure economics

- [ ] W01. Validate student-count pricing tiers with school interviews. (Pilot)
- [ ] W02. Define how active enrolled student count is measured. (Core)
- [ ] W03. Define upgrade/downgrade timing and treatment of mid-term enrolment changes. (Pilot)
- [ ] W04. Define monthly and termly billing rules. (Pilot)
- [ ] W05. Define free tier limits and upgrade path. (Pilot)
- [ ] W06. Define one-time onboarding/digitisation fee and scope. (Pilot)
- [ ] W07. Define SMS prepaid allowance and overage policy. (Pilot)
- [ ] W08. Keep payment gateway charges transparent and attributed correctly. (Core)
- [ ] W09. Track hosting, database, storage, egress, email and SMS consumption. (Core)
- [ ] W10. Track cost to serve each school and contribution margin. (Pilot)
- [ ] W11. Set infrastructure upgrade triggers based on usage, reliability and recovery needs. (Core)
- [ ] W12. Do not upgrade infrastructure solely because a school-count milestone was reached if measured usage does not require it; do not delay upgrades when reliability/security requires them. (Core)
- [ ] W13. Reassess free-tier suitability before relying on it for critical production school data. (Core)

### X. Future roadmap and optional modules

- [ ] X01. Homework and classwork management. (Future)
- [ ] X02. CBT and online examinations. (Future)
- [ ] X03. Library catalogue and borrowing. (Future)
- [ ] X04. School transport and route/vehicle management. (Future)
- [ ] X05. Inventory, assets and procurement. (Future)
- [ ] X06. Visitor register and school access log. (Future)
- [ ] X07. Staff HR, leave and payroll. (Future)
- [ ] X08. Student health/safeguarding records with strict access controls. (Future)
- [ ] X09. School announcements, newsletters and richer parent engagement. (Future)
- [ ] X10. Multi-campus management and consolidated reporting. (Future)
- [ ] X11. Advanced academic and attendance performance intelligence. (Future)
- [ ] X12. Teacher device sponsorship/affordable Android tablet programme. (Future)
- [ ] X13. School-branded public websites and expanded online admissions. (Future)
- [ ] X14. Additional integrations only when validated by school demand. (Future)

### Y. Final release acceptance

- [ ] Y01. Every Core requirement has an owner, design, implementation and acceptance evidence.
- [ ] Y02. Every critical workflow has been tested end to end by the correct role.
- [ ] Y03. School A cannot access School B's data, including through API, storage, exports or guessed identifiers.
- [ ] Y04. A teacher can complete attendance and mark submission without administrator assistance after training.
- [ ] Y05. A principal can identify missing attendance and results without manually checking every teacher.
- [ ] Y06. A bursar can reconcile a student's bill, payments and balance with a clear audit trail.
- [ ] Y07. A parent can securely view only their linked child/children and understand fees, attendance and published results.
- [ ] Y08. A proprietor can understand enrolment, collection, arrears, attendance and operational exceptions without misleading figures.
- [ ] Y09. Bulk actions such as “Mark all present” and payment imports have review, exception handling and confirmation.
- [ ] Y10. Email, Google OAuth, in-app notifications and SMS have been configured and tested for the release scope.
- [ ] Y11. Payment provider sandbox/live readiness, verification and reconciliation have been tested before accepting real payments.
- [ ] Y12. Sentry captures test errors and alerts the responsible owner.
- [ ] Y13. Backups and restore have been successfully tested.
- [ ] Y14. Approved Figma designs match the delivered screens and responsive states.
- [ ] Y15. Light and dark theme behaviour is tested for the screens included in the release.
- [ ] Y16. School data export and offboarding have been tested.
- [ ] Y17. Pilot schools have completed agreed acceptance criteria.
- [ ] Y18. Known limitations, support process and incident contact are documented.
- [ ] Y19. No critical security, privacy or data-integrity issue remains unresolved.
- [ ] Y20. Product owner signs off the release based on evidence, not visual completion alone.

### Z. ACADIVA Operations — Founder Master Control, CTO governance and school onboarding

- [ ] Z01. Build ACADIVA Operations as a separate internal application/workspace, distinct from school-facing ACADIVA. (Core)
- [ ] Z02. Create a Founder Master Control account with exclusive authority to approve, suspend and revoke CTO accounts. (Core)
- [ ] Z03. Ensure no CTO can approve another CTO, grant founder-level access or alter founder security settings. (Core)
- [ ] Z04. Provide a CTO registration request flow that collects identity and work email but grants no access while pending. (Core)
- [ ] Z05. Send the CTO approval notification and single-use, time-limited approval OTP to the founder-controlled email configured for ACADIVA (initially [adebimpe476@gmail.com](mailto:adebimpe476@gmail.com)); require the founder to confirm the decision in Founder Master Control. (Core)
- [ ] Z06. Require the founder to approve or reject each CTO request; record decision, actor and timestamp. (Core)
- [ ] Z07. Verify the CTO's own email separately and require a secure password plus MFA before activation. (Core)
- [ ] Z08. Do not use the founder's email inbox as a shared login, password-reset destination for the CTO, or universal login OTP channel. (Core)
- [ ] Z09. Provide founder controls to suspend/revoke CTO access immediately, invalidate active sessions and review recent activity. (Core)
- [ ] Z10. Provide an operations overview of all schools, school status, onboarding progress, user counts, pending approvals and operational exceptions. (Core)
- [ ] Z11. Provide a searchable school directory and fast school switcher without requiring repeated sign-out/sign-in. (Core)
- [ ] Z12. Clearly label the active school context and show a persistent internal-operations access indicator. (Core)
- [ ] Z13. Allow authorised CTOs to register, configure, activate and support schools according to company policy. (Core)
- [ ] Z14. Separate school registration, identity verification, approval, activation and setup-completion states. (Core)
- [ ] Z15. Support onboarding proprietors, principals, vice-principals, administrators, registrars, bursars, teachers, other staff and parent/guardian accounts. (Core)
- [ ] Z16. Support student Applicant/profile creation and enrolment conversion without duplicate student records. (Core)
- [ ] Z17. Support individual and bulk user/student onboarding with CSV/XLSX template, column mapping, preview, validation, duplicate detection and error report. (Core)
- [ ] Z18. Allow authorised operations staff to configure classes, arms, subjects, sessions, grading, fee structures and teacher assignments for a school. (Core)
- [ ] Z19. Provide an onboarding checklist and progress state per school, including missing information and outstanding school decisions. (Core)
- [ ] Z20. Ensure school representatives can review and confirm critical imported data and school-specific settings before go-live. (Core)
- [ ] Z21. Support controlled assistance and delegated actions on behalf of school staff without falsifying the identity of the person who performed the action. (Core)
- [ ] Z22. Require a reason, scoped permissions, visible delegated-session banner, expiry and audit trail for every act-on-behalf session. (Core)
- [ ] Z23. Preserve the CTO as the true actor for every delegated action and record the represented school/user separately. (Core)
- [ ] Z24. Require school-authorised approval for sensitive actions such as publishing results, confirming financial records, issuing official transcripts and changing high-risk records unless a documented emergency policy applies. (Core)
- [ ] Z25. Restrict CTO access to school data by operational need; log sensitive record views, exports, edits, imports and deletions. (Core)
- [ ] Z26. Enforce tenant isolation, server-side authorisation and database-level policies for internal operations; never rely on hidden UI controls alone. (Core)
- [ ] Z27. Prevent CTOs from viewing passwords, authentication secrets or raw credentials. (Core)
- [ ] Z28. Log CTO registration, founder approval, login/MFA events, school activation, role changes, delegated actions, exports and access revocation. (Core)
- [ ] Z29. Provide filters and export controls for audit review, with sensitive export permission and logging. (Pilot)
- [ ] Z30. Test cross-school access boundaries, privilege escalation, revoked sessions, expired delegation and bulk-import failure recovery. (Core)
- [ ] Z31. Ensure internal operations access does not bypass school consent, data protection, school ownership or retention rules. (Core)
- [ ] Z32. Define CTO operational permissions and any future support/sales/onboarding employee roles separately; do not make every employee a super-admin. (Pilot)
- [ ] Z33. Test the complete school onboarding journey from school approval through staff/student/guardian setup and first successful school use. (Core)
- [ ] Z34. Document founder account recovery, emergency lockout procedure, incident response and privileged-access review. (Core)

### AA. Connected system architecture, workspace integration and build order

- [ ] AA01. Define ACADIVA as one connected product ecosystem with role-specific protected workspaces, not disconnected mini-applications. (Core)
- [ ] AA02. Map all workspaces and user journeys: founder, CTO/internal operations, proprietor, principal, vice-principal, school administrator/registrar, bursar, teacher and parent/guardian. (Core)
- [ ] AA03. Define the main website route and navigation architecture, with a protected internal Operations area and separate school-role workspaces. (Core)
- [ ] AA04. Decide whether any workspace needs a distinct subdomain/deployment only after evaluating security, operations and user experience; do not split the product prematurely. (Core)
- [ ] AA05. Design one coherent identity model with explicit internal accounts, school memberships, guardian-child links and role assignments. (Core)
- [ ] AA06. Define the organisation/school tenancy model, including school ownership, optional branches/campuses and the relationship between a school organisation and its users. (Core)
- [ ] AA07. Define the canonical data model and relationships before building individual modules; prevent duplicate student, staff, class, guardian, payment and assessment records. (Core)
- [ ] AA08. Define the role-permission matrix and data visibility rules for every workspace and action. (Core)
- [ ] AA09. Define how internal ACADIVA staff access school records through scoped, audited operations rather than unrestricted database access. (Core)
- [ ] AA10. Define authoritative records and ownership for admissions, student profiles, guardian links, class placement, teacher assignments, timetable, attendance, assessments, results, invoices, payments and notifications. (Core)
- [ ] AA11. Define cross-module events and update rules so one successful change is reflected in all authorised views without duplicate editable copies. (Core)
- [ ] AA12. Define approval states and lifecycle transitions, including draft, submitted, under review, approved, published, rejected, corrected and archived where relevant. (Core)
- [ ] AA13. Define shared UI components, design tokens, responsive behaviour, navigation patterns, forms, tables, empty states, errors and loading/sync states across all workspaces. (Core)
- [ ] AA14. Produce a complete screen inventory and navigation map for every role before detailed screen implementation. (Core)
- [ ] AA15. Link every screen to its user role, workflow, data entities, permissions, API/backend operation and acceptance tests. (Core)
- [ ] AA16. Define the integration map for authentication/email verification, notifications, file storage, payments, exports, backups and monitoring. (Core)
- [ ] AA17. Define service boundaries and modular code organisation so admissions, academics, attendance, finance, communications and internal operations can evolve without becoming disconnected systems. (Core)
- [ ] AA18. Establish development, staging and production environments, migrations, seed data and release controls before production school data is onboarded. (Core)
- [ ] AA19. Build and test the shared foundation first: identity, organisation/school tenancy, memberships, roles, permissions, audit events and school configuration. (Core)
- [ ] AA20. Build the connected operational backbone next: student/guardian records, staff/class/subject assignments, admissions and timetable. (Core)
- [ ] AA21. Build the daily school workflows next: attendance, assessment entry, review/publication, fees/payment records and parent portal. (Core)
- [ ] AA22. Build ACADIVA Operations on the same foundation, including founder control, CTO governance, school onboarding and delegated support actions. (Core)
- [ ] AA23. Integrate in-app notifications and cross-workspace updates after the underlying records and event rules are defined. (Core)
- [ ] AA24. Test complete end-to-end journeys across roles, not just isolated screens or modules. (Core)
- [ ] AA25. Verify that a change in one workspace appears correctly in every authorised connected workspace, and nowhere else. (Core)
- [ ] AA26. Do not begin full-scale screen-by-screen implementation until product scope, role map, core workflows, data relationships, screen inventory and security boundaries have been reviewed and signed off. (Core)

### AB. Finance, academic lifecycle, student lifecycle, SMS and template-led school onboarding

- [ ] AB01. Define the school's financial ledger as the authoritative record for charges, payments, allocations, adjustments, refunds and balances. (Core)
- [ ] AB02. Support configurable fee items by session, term, class, student and approved group, including mandatory/optional and one-time/recurring charges. (Core)
- [ ] AB03. Support full and partial payments, instalments, discounts, scholarships, waivers and approved concessions without overwriting original charges. (Core)
- [ ] AB04. Distinguish pending, unverified, verified, failed, reversed and refunded payments; only verified/settled records count as confirmed collections under the school's reconciliation policy. (Core)
- [ ] AB05. Allocate every payment to the correct student, invoice and fee item; support correction/reallocation with reason and audit history. (Core)
- [ ] AB06. Support cash and bank-transfer recording with verifier, reference/evidence and approval rules; a screenshot alone is not proof of settlement. (Core)
- [ ] AB07. Reconcile gateway transactions, bank settlements, provider fees, refunds, reversals, duplicate and unmatched payments. (Pilot)
- [ ] AB08. Support expenses, payee/supplier, category, evidence, approvals and term-level financial reports without claiming to replace full statutory accounting. (Pilot)
- [ ] AB09. Provide student statements, outstanding balances, ageing/overdue views, collection summaries and printable/exportable reports restricted by role. (Core)
- [ ] AB10. Define term financial close, outstanding-balance carry-forward, approved adjustments and reopening/correction rules without deleting historical transactions. (Core)
- [ ] AB11. Define the academic session/term lifecycle from setup through in-term operation, close preparation, mark completion, result review, publication, promotion and next-term opening. (Core)
- [ ] AB12. Provide a term-close readiness view for missing marks, unsubmitted attendance, unresolved result reviews, pending corrections, report cards and financial reconciliation exceptions. (Core)
- [ ] AB13. Require authorised approval before results are published or a term is formally closed; retain a dated snapshot of the published academic record. (Core)
- [ ] AB14. Provide a reviewed promotion/rollover preview showing each student's proposed next class/status before committing changes. (Core)
- [ ] AB15. Support promoted, repeating, transferred, withdrawn, graduated and other approved student lifecycle transitions with effective date, reason, actor and history. (Core)
- [ ] AB16. Preserve historical class, session, guardian, academic and financial relationships when a student changes status or class. (Core)
- [ ] AB17. Prevent duplicate student creation during admissions, referral-link submission, imports, re-admission and school onboarding; use matching and human review where uncertain. (Core)
- [ ] AB18. Provide reusable Nigerian school templates for common education structures (for example nursery levels, primary classes and secondary classes), grading, terms and starter fee categories. (Core)
- [ ] AB19. Make templates editable per school; applying a template must preview changes and must not overwrite existing school data or historical records. (Core)
- [ ] AB20. Support adding, renaming, reordering, deactivating and archiving classes/arms; never hard-delete a class referenced by students, results, attendance or fees. (Core)
- [ ] AB21. Ensure archived/deactivated classes disappear from active selection and current school-facing views as appropriate while remaining available in authorised historical records and reports. (Core)
- [ ] AB22. Design the CTO dashboard around clear actions such as Create a school, Open/manage an existing school, Continue onboarding, Import records and Review exceptions. (Core)
- [ ] AB23. When creating a school, guide the CTO through school profile, education-level template, session/term, classes/arms, subjects, grading, fees, staff and initial data. (Core)
- [ ] AB24. When opening an existing school, show its configuration and onboarding state; allow authorised edits without re-creating the school or duplicating records. (Core)
- [ ] AB25. Support CTO-created/imported student records from school-authorised source data, including identity, date of birth, guardian links, admission/class status and available history. (Core)
- [ ] AB26. Keep age derived from date of birth and reference date; do not store age as an independent authoritative field. (Core)
- [ ] AB27. Academic marks remain the responsibility of assigned teachers or school-authorised academic staff; CTOs may assist with authorised migration/import but must preserve source, actor and approval. (Core)
- [ ] AB28. Provide a school-specific join/admission link. A successful parent submission creates one Applicant profile; configured auto-approval or principal approval controls admission, and accepted applicants convert into one student record without CTO re-entry. (Core)
- [ ] AB29. Distinguish application received, applicant profile created, admission approved, offer accepted, enrolled and class placed; do not silently treat an application as an enrolled student. (Core)
- [ ] AB30. Define SMS as a primary external parent-notification channel for important school messages; parents must not be required to open the app to receive essential notices. (Core)
- [ ] AB31. Use verified guardian phone numbers and appropriate lawful basis/consent, communication preferences and opt-out handling where applicable. (Core)
- [ ] AB32. Track SMS provider, message cost, sender identity, queued/sent/delivered/failed status where supported, retries, duplicate suppression and message history. (Core)
- [ ] AB33. Make school-funded or usage-based SMS costs visible; define budgets, quotas, low-balance alerts and rules for urgent messages. (Core)
- [ ] AB34. Keep in-app parent records available for detailed statements, report cards, documents and actions; use SMS for concise alerts, reminders, invitations and links. (Core)
- [ ] AB35. Test the complete journeys: new school from template to go-live; existing school from join link to enrolled student; end-of-term close and rollover; payment allocation and reconciliation; SMS delivery failure and retry. (Core)

### Important workflow design rules captured from the discussions

<b>Attendance — the simple workflow</b>

1. Teacher opens today's assigned class.
2. The correct enrolled class list appears automatically.
3. Teacher taps “Mark all present”.
4. Teacher changes only students who are absent (and excused only if enabled by school policy).
5. Screen displays totals and any unmarked students.
6. Teacher reviews and submits.
7. System saves the register, records who submitted it and shows success/sync state.
8. Principal dashboard updates; authorised parents see relevant attendance.
9. Corrections require permission and a reason.

<b>Fees — the safe workflow</b>

1. Bursar selects the relevant session, term, class and fee item.
2. ACADIVA displays each student's bill, payments and outstanding amount.
3. Confirmed gateway transactions are reconciled automatically.
4. Cash/bank payments are entered with evidence/reference and verification status.
5. Bulk imports are previewed student by student; unmatched or duplicate entries are flagged.
6. A bulk “mark paid” action is allowed only when it represents a specific verified batch or approved manual attestation.
7. The bursar reviews exceptions and confirms.
8. ACADIVA records the actor, time, source and audit trail; receipts are generated only under the confirmation rules.
9. Parent and proprietor views update from the same authoritative ledger.

<b>Teacher assignment — the controlled workflow</b>

1. School administrator/principal configures classes, arms and subjects.
2. Authorised administrator assigns teacher to class and subject.
3. System checks timetable conflicts and assignment validity.
4. Teacher sees only assigned classes and subjects.
5. Assignment changes are audited and immediately affect access.

<b>Results — the controlled workflow</b>

1. School configures assessments, marks, weights and grading rules.
2. Teacher enters marks for assigned subjects/classes.
3. System validates ranges and missing values.
4. Teacher submits.
5. Principal/authorised reviewer checks and returns or approves.
6. Approved results are published.
7. Corrections after publication require an authorised reason and audit trail.
8. Parent sees only published results for linked children.

### Governance note

This is deliberately a large checklist. It is a master scope and verification register, not a promise that every item belongs in the first launch. Core, Pilot, Later and Future labels protect the initial release from becoming impossibly large. The product owner must prioritise the first usable release after school workflow research, while retaining the rest as a traceable roadmap.

The checklist should be converted into a working project tracker with status, owner, priority, requirement ID, release, dependency and evidence fields. The Notion blueprint remains the narrative source of truth; the tracker is the execution view.

## 41. Product simplification decisions, role boundaries, live workflows and free/open-source technology baseline — 15 November 2026

### 41.1 Why this decision update exists

After reviewing the current consolidated product requirements (Section 36), strategic revision (Section 37), technology/design architecture (Section 39) and master checklist (Section 40), this update tightens the product around the founder's most important requirement: ACADIVA must be genuinely simple to use. It must not create unnecessary tasks for teachers or overwhelm users with features, dashboards and administrative steps.

This section is the latest decision record. Where it conflicts with older wording in Sections 36 or 40, this section takes precedence. Older wording remains as historical discovery, not as a requirement to build.

### 41.2 Student access model — parent/guardian is the default portal owner

<b>Decision: do not build a separate student dashboard or require student logins for the initial product.</b>

- The parent/guardian account is the primary portal for a child.
- A parent can have more than one linked child and switch between the children's profiles.
- Each child profile contains the authorised information relevant to that child: attendance, published results/report cards, timetable where enabled, fee invoices/balances/receipts and school notices.
- A parent sees only children linked to their verified guardian relationship.
- Teachers see only the students in classes/subjects assigned to them and only the student information needed for their work.
- Teachers do not browse the school's entire student population by default.
- Proprietors, principals and authorised administrators have wider school-level visibility according to their permissions.
- Student accounts are a possible future feature for older students, but must be justified by school demand, age-appropriate safeguards and a clear use case. They are not part of the initial scope.

The product should not create a student dashboard simply because other school platforms have one. The parent portal already gives the family the appropriate access.

### 41.3 Birthday experience — a quiet, contextual reminder

<b>Decision: birthdays are a small contextual moment, not a dashboard module.</b>

- On the student's birthday, show a small, non-blocking birthday notice to the parent/guardian on that child's portal.
- The teacher responsible for the student's class may see a small birthday pop-up/banner when opening the teacher workspace or relevant class on that date.
- Do not create a permanent birthday dashboard, birthday calendar task, birthday data-entry workflow or repeated notifications.
- Do not show the birthday to unrelated teachers or other parents.
- The reminder must not interrupt attendance, mark entry or another active task.
- Show it at most once per user/session/day as appropriate; allow dismissal.
- The source is the student's date of birth already stored in the student record. No extra birthday data entry is needed.
- If the school has an explicitly approved achievement/recognition programme, academic recognition may be shown as a separate, verified school award. Do not label a child “the most brilliant” by default or tie birthday visibility to academic ranking. This can disclose sensitive comparisons and create avoidable social pressure.

### 41.4 Attendance — remove unnecessary classroom administration

<b>Decision: the default teacher attendance workflow is present/absent, with an optional school-approved excused status. Routine late-coming capture is not part of the core teacher workflow.</b>

The teacher is not expected to stand at the classroom entrance operating a phone to record each late arrival. ACADIVA should not make this a routine teacher responsibility.

<b>Default workflow:</b>

1. Teacher opens the class assigned for the relevant school day.
2. ACADIVA loads the active class register.
3. Teacher taps <b>Mark all present</b>.
4. Teacher changes only the students who are absent (and, if enabled by school policy, excused).
5. The screen shows the total number of students, present count, absent count and any unmarked students.
6. Teacher reviews and submits once.
7. ACADIVA records the submitted register, actor and timestamp.
8. The saved record updates the authorised dashboards and parent view automatically.

<b>Rules:</b>

- Present is the default result of the bulk action, not a claim that the teacher has already submitted. The teacher must review and confirm.
- A register cannot be submitted while students remain unmarked unless the school explicitly permits a documented exception.
- The normal teacher register has no routine late-coming field or time-entry requirement.
- If a school later proves it needs late-arrival/early-departure records, consider a separate optional office/admin exception workflow. Do not burden every teacher or make it part of the default attendance screen.
- Corrections after submission require permission and a reason; retain before/after values, actor and time.
- Do not duplicate daily attendance and lesson attendance in the first release unless pilot schools demonstrate a genuine need. Daily school attendance is the initial default; lesson attendance remains a later configurable extension.

### 41.5 One attendance record, automatically reflected across ACADIVA

<b>Decision: teacher submits attendance once. All authorised views read from the same authoritative record.</b>

After the server successfully saves a class register:

- The teacher sees the saved state.
- The principal's attendance overview updates.
- The proprietor's school attendance summary updates.
- The relevant child's parent portal updates.
- The administrator's attendance register updates.
- Any configured absence alert is sent only according to the school's notification policy.

Use Supabase Realtime or a reliable refresh/invalidation strategy to update connected views. The database commit is authoritative: do not show an unconfirmed save as final. If a user is offline, show a clear local/sync-pending state and update other users' dashboards only after the server accepts the record.

The dashboards must not each store their own editable attendance copy. They are different views of the same attendance data. Aggregate figures should be derived from saved records and show a useful update time.

### 41.6 Teacher workspace — keep only what helps the teacher teach

The teacher home screen should be calm and task-focused. Its primary content is:

1. Today's timetable.
2. Assigned classes and subjects.
3. Attendance action for the relevant class/day.
4. Assessment/marks that need entry or submission.
5. School/principal notices relevant to the teacher.
6. A subtle birthday reminder for an assigned student, only on the birthday.

A teacher's class view should contain the class roster, the attendance action, subject/assessment actions and relevant student information. Do not turn it into a general-purpose student database.

<b>Remove from the default teacher attendance workflow:</b> late-coming capture, early-departure capture, long notes for every student, repeated confirmation screens and unnecessary status fields.

### 41.7 Timetable changes — update the source and affected views together

- The authorised principal or school administrator owns timetable creation and changes.
- A teacher cannot change their own official timetable unless separately authorised.
- When a timetable is changed and saved, the affected teacher's daily and weekly timetable must show the new class, subject, time and room automatically.
- Notify the affected teacher through the in-app notification centre.
- If the change affects a class/parents, the school may notify the relevant parent audience according to its policy.
- Keep a change history showing who changed the timetable, what changed and when.
- Avoid duplicate manual edits to a teacher-specific timetable. Teacher timetable is a view generated from the authoritative school timetable and teacher assignment.

### 41.8 Principal announcements and notifications

<b>Decision: build a simple in-app notification centre and an authorised announcement workflow.</b>

The principal (and other explicitly authorised roles) should be able to send a notice to a defined audience:

- All staff.
- Teachers only.
- Parents/guardians.
- A particular class/arm's parents.
- A selected group or individual recipient, where permitted.

Examples include a staff meeting, a school resumption reminder, a parent meeting, a timetable change or a school-wide notice.

<b>Recipient experience:</b>

- The notice appears in the recipient's notification inbox.
- An unread count/badge appears.
- Opening the notice shows its title, message, sender, audience context and date/time.
- The notice can link to the relevant timetable, event or school information.
- Connected users receive it promptly; users who were offline see it when they return.
- The sender can see delivery/recipient status at a practical level, without pretending that an in-app notice was read merely because it was delivered.

<b>Students and parents:</b> because students do not have independent accounts in the initial product, a student-directed announcement should normally be delivered to the linked parent/guardian account and labelled as concerning that child/class. Do not build a separate student notification inbox until student accounts are approved as a future feature.

<b>Scheduling:</b> allow authorised senders to schedule a notice for a selected date/time in the school's timezone (Africa/Lagos by default for Nigerian schools). Validate the date/time before scheduling. Do not assume an example such as “2am” is correct; the sender must review the scheduled time.

### 41.9 Email, Google sign-in, SMS, in-app and push are different things

Do not treat these as one integration.

- <b>Google sign-in (OAuth):</b> lets an authorised user sign in with Google. It is an authentication integration, not a notification channel.
- <b>In-app notifications:</b> stored in ACADIVA and displayed in the notification centre. This is a core ACADIVA feature.
- <b>Email:</b> external delivery for invitations, password/account messages, receipts and selected notices. Requires a sending provider and domain authentication.
- <b>SMS:</b> external telecom delivery for selected urgent or important messages. Every SMS has a real provider/carrier cost; there is no dependable unlimited free SMS service.
- <b>Push notifications:</b> browser/mobile device alerts. Add when the supported web/mobile experience and permission model are ready. Push is not a replacement for the in-app inbox.

The same announcement should have one authoritative ACADIVA record and separate delivery attempts for each selected channel. Email/SMS failure must not delete the in-app notice or undo the underlying timetable/announcement change. Record queued, sent, delivered (where provider reports it), failed and retried states accurately.

### 41.10 Homework and assignments — not required for the first release

<b>Decision: do not require teachers to create or record homework/assignments in the initial product.</b>

- Do not add an assignment-entry task to the teacher home screen by default.
- Do not make homework records a prerequisite for attendance, assessment, grading or result publication.
- Keep a future homework/classwork module on the roadmap only if pilot schools ask for it.
- This does not prevent a school from having an “assignment” as one assessment component in its grading configuration. If a school awards marks for assignments, teachers can enter the resulting score in the assessment mark sheet without maintaining a separate homework-management workflow.

### 41.11 Assessment, grading and results — one guided, polished workflow

This is a core product capability and should receive more design attention than optional modules.

<b>Teacher workflow:</b>

1. Select an assigned class.
2. Select an assigned subject.
3. Select the configured assessment/term component (for example CA, test or examination).
4. See a clean mark-entry sheet with student names, maximum score and input cells.
5. Enter scores with autosave/draft protection.
6. See missing scores and invalid values clearly.
7. Review a class completion count and submit for review.

<b>Design requirements:</b>

- Desktop/tablet: a clean, spreadsheet-like mark sheet with sticky student-name column, clear score columns, keyboard navigation and bulk paste/import only after validation.
- Mobile: a simplified responsive mark-entry experience that does not shrink a wide spreadsheet into unreadable text.
- Show one class and one subject at a time; do not place the entire school on one screen.
- Make the maximum score visible beside the input.
- Distinguish missing, absent-from-assessment, exempt and actual zero. Never silently turn a missing mark into zero.
- Validate ranges immediately and explain errors in plain language.
- Show draft/saved/submitted/reviewed/returned/published status.
- Let teachers resume a saved draft.
- Avoid decorative charts and unnecessary fields during mark entry.

<b>Calculation and approval:</b>

- School configures assessment components, maximum marks, weightings, grade bands and remarks.
- ACADIVA calculates totals, weighted scores, percentages and grades using the configured rules.
- Provide a result preview before submission/publication.
- The designated reviewer/principal checks and approves according to school policy.
- Published results are visible to linked parents.
- Corrections after publication require permission, a reason and before/after audit history.

<b>Report card design:</b>

- Premium, clean, school-branded A4 layout.
- Strong typographic hierarchy, clear subject/assessment rows, legible grade and teacher/principal remarks.
- Show session, term, class, student identity and school details.
- Avoid crowded layouts, arbitrary ranking or unconfigured metrics.
- Ensure print and PDF output match the approved design.

### 41.12 Interface organisation — simplicity is a release requirement

- A role sees a small, relevant navigation set, not every ACADIVA module.
- The most frequent action is visually obvious on the home screen.
- Each screen has one primary purpose and one clear primary action.
- Advanced settings stay in administration, not inside teacher workflows.
- Use progressive disclosure: show details when needed rather than displaying every field at once.
- Use consistent labels, status names, button positions and save feedback.
- Bulk actions must reduce work and include a review/exception step.
- Do not add a dashboard card, chart, calendar, workflow or notification merely because the database can support it.
- Every new feature must answer: whose problem does this solve, how often, what work does it remove, and what extra work does it create?
- Test the real task with a teacher/parent/admin before accepting the design.

### 41.13 Free and open-source technology selection

The aim is to use permissively licensed, free-to-use software libraries wherever practical, while avoiding a large self-hosting burden. “Open source” describes the software licence; it does not mean hosting, domain registration, email delivery, SMS, payment processing, backups or support are automatically free.

<b>Selected application stack (free/open-source software):</b>

| Layer | Selected tool | Use in ACADIVA | Licence / cost note |
| --- | --- | --- | --- |
| Web application | Next.js + React | Responsive web application and role-specific workspaces | Open-source software; no framework licence fee |
| Language | TypeScript | Safer application and API code | Open-source; no licence fee |
| Styling | Tailwind CSS | Design tokens and responsive styling | Open-source; no licence fee |
| UI component foundation | shadcn/ui with Radix UI primitives | Accessible forms, dialogs, menus, tabs, popovers and controls; copy components into our repository and customise them | MIT-licensed components; verify individual added components |
| Icons | Lucide | Consistent interface icons | Open-source; no icon subscription required |
| Data tables | TanStack Table | Student registers, attendance and marks tables | Open-source; build our own ACADIVA styling |
| Server/client data state | TanStack Query where needed | Cache, refresh and invalidate server data after attendance/result changes | Open-source |
| Forms | React Hook Form | Efficient form state and validation integration | Open-source |
| Validation | Zod | Shared input/schema validation | Open-source |
| Charts | Recharts, only for meaningful management analytics | Enrolment, collection and attendance charts | Open-source; charts are not mandatory on every dashboard |
| Date handling | date-fns | Dates, terms, birthdays and schedules | Open-source |
| Database | PostgreSQL | Authoritative relational school data | PostgreSQL licence; no database licence fee |
| Backend platform | Supabase open-source components | Auth, Postgres APIs, Realtime and Storage | Core software is open source; managed Supabase hosting is a separate hosted service with plan limits |
| Unit tests | Vitest | Business-rule and utility tests | Open-source |
| Component tests | React Testing Library | User-facing component behaviour | Open-source |
| Browser end-to-end tests | Playwright | Critical role-based workflows and regression tests | Apache-2.0 |
| Code lint/format | ESLint + Prettier | Consistent code quality | Open-source |
| Mobile framework (later) | Expo + React Native | Android/iOS teacher and parent experience if validated | Open-source framework; app-store accounts and build/hosting services may still cost |
| Mobile local database (later) | Expo SQLite | Secure local data/cache foundation for approved offline workflows | Open-source package; security and encryption design still required |

Reference repositories/documentation:

- [Next.js](https://github.com/vercel/next.js)
- [React](https://github.com/facebook/react)
- [TypeScript](https://github.com/microsoft/TypeScript)
- [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss)
- [shadcn/ui](https://github.com/shadcn-ui/ui)
- [Radix UI](https://github.com/radix-ui/primitives)
- [Lucide](https://github.com/lucide-icons/lucide)
- [TanStack Table](https://github.com/TanStack/table)
- [TanStack Query](https://github.com/TanStack/query)
- [React Hook Form](https://github.com/react-hook-form/react-hook-form)
- [Zod](https://github.com/colinhacks/zod)
- [Recharts](https://github.com/recharts/recharts)
- [date-fns](https://github.com/date-fns/date-fns)
- [PostgreSQL](https://www.postgresql.org/)
- [Supabase](https://github.com/supabase/supabase)
- [Vitest](https://github.com/vitest-dev/vitest)
- [React Testing Library](https://github.com/testing-library/react-testing-library)
- [Playwright](https://github.com/microsoft/playwright)
- [ESLint](https://github.com/eslint/eslint)
- [Prettier](https://github.com/prettier/prettier)
- [Expo](https://github.com/expo/expo)

<b>Operations and monitoring choices:</b>

| Need | Recommendation | Decision and caveat |
| --- | --- | --- |
| Error monitoring | Keep Sentry in the architecture for the early hosted phase; evaluate GlitchTip if strict open-source/self-hosted control becomes important | Sentry's main application uses the Functional Source License, which is not OSI-approved open source. Sentry SDKs have their own licences. GlitchTip is an open-source, Sentry-compatible alternative but self-hosting needs a server and maintenance. |
| Product analytics | PostHog Cloud free tier for limited early measurement, or defer analytics until real pilot usage | PostHog has an MIT-licensed self-hosted edition, but self-hosting still requires infrastructure and maintenance. Do not self-host it just to avoid a small cloud bill. |
| Uptime | Uptime Kuma if we have a server to run it; otherwise use a reputable hosted free monitor during the pilot | Uptime Kuma is MIT-licensed and free software, but it needs an always-on host. |
| Backups | PostgreSQL-native dump/restore tooling plus encrypted independent file backups | Tools are free; storage and reliable offsite retention may cost money. |
| Email server | Do not self-host Postal for the first release | Postal is open-source, but mail server operation, IP reputation, spam handling and deliverability are not free or simple. Use a reputable transactional email provider's free allowance initially, then budget for it. |
| SMS | Use a Nigerian SMS gateway only for messages that genuinely need SMS | SMS is a paid telecom delivery service; no open-source library can make carrier delivery free. |
| Google login | Google OAuth through Supabase Auth | The integration can be used without a Google software licence fee under Google's current terms, but Google is a proprietary external identity provider, not open-source software. |
| Payment | Paystack or another approved Nigerian payment provider | Payment processing is proprietary and transaction fees apply. No open-source code removes gateway/bank charges. |

<b>Important free-tier distinction:</b> Supabase, Netlify, Sentry, PostHog Cloud and other hosted products may offer free plans, but the hosted services are not the same thing as self-hosting their open-source components. Free plans have quotas, terms, possible pauses and no guarantee of permanent free production service. Keep the current free-tier-first strategy from Section 38, but do not treat provider plans as open-source software.

<b>Do not add to the initial stack without a demonstrated need:</b> a second UI kit, multiple chart libraries, multiple form libraries, a self-hosted email server, a separate notification SaaS, a second hosting platform, a complex microservice architecture or AI services. ACADIVA has no AI product features or AI API dependency.

### 41.14 What must now change in the master checklist

The following Section 40 items are superseded or narrowed by this decision:

- Student dashboard/student login is future-only, not initial release.
- Teacher birthday experience is a one-day, contextual reminder for assigned students, not a birthday calendar or ongoing task.
- Parent birthday experience is a subtle notice on the child's portal on the birthday.
- Routine late-coming and early-departure capture is removed from the default teacher attendance workflow.
- Attendance defaults to “Mark all present”, adjust absences/exceptions, review and submit.
- One saved attendance record updates all authorised dashboards automatically.
- Teacher timetable is derived from the authoritative timetable and updates when an authorised change is saved.
- Principal announcements appear in the in-app notification centre; child/student-directed notices go to parent/guardian accounts while student accounts are not enabled.
- Homework/assignment management is optional future scope, not a teacher obligation or a dependency for assessment/results.
- Assessment mark entry and report cards are elevated as core design priorities.
- The open-source stack above is the preferred free-software baseline; hosted vendors and delivery services are separately classified.

### 41.15 Acceptance tests for the simplified experience

- [ ] A teacher can open today's assigned class, mark all present, change only absent students and submit without entering late-coming data.
- [ ] After a successful attendance save, the teacher, principal, proprietor, admin and linked parent views reflect the same saved attendance.
- [ ] An unsaved or offline attendance change is visibly marked as pending and is not falsely shown as confirmed to other users.
- [ ] A parent can switch between linked children and sees only the relevant child's records.
- [ ] No student dashboard or student login is required to use the initial parent portal.
- [ ] A teacher sees a birthday reminder only for an assigned student and only on the relevant date; it does not interrupt attendance or marks.
- [ ] A parent sees a subtle birthday notice for their own child on the relevant date.
- [ ] An authorised timetable change updates the affected teacher timetable and creates an in-app notice.
- [ ] A principal can send a notice to all staff, teachers, parents or a selected class/arm; recipients see it in their in-app inbox.
- [ ] A child-directed notice is visible to the linked parent/guardian account in the initial release.
- [ ] Homework entry is not required for teacher attendance, assessment or result submission.
- [ ] A teacher can enter marks for one assigned class and subject using a clear, validated, saveable workflow.
- [ ] Missing, absent, exempt and zero marks are represented distinctly.
- [ ] A principal can review and publish results; parents see results only after publication.
- [ ] The selected software dependencies have been checked for licence, maintenance, security and commercial-use suitability before adoption.

### 41.16 Remaining decisions for the pilot

- Whether a school needs excused absence as a standard attendance option or only present/absent.
- Whether parent notifications should be sent for every absence or only according to school-defined rules.
- Whether timetable changes should notify parents automatically or only when they affect a class-wide schedule.
- Whether result approval requires a Head of Department step, principal step or school-configurable sequence.
- Whether the first mobile release is one role-aware app or separate parent/teacher apps.
- Whether GlitchTip is worth self-hosting or Sentry hosted free tier is simpler for the pilot.
- Which transactional email and Nigerian SMS provider offers the best deliverability and total cost at pilot scale.

These decisions should be resolved with pilot schools and recorded before implementation.

### 41.17 Typography and theme implementation details

- Use the native system font stack so Apple devices naturally render Apple's system San Francisco typeface without bundling or redistributing Apple's proprietary font files.
- Use a licensed open font such as Inter as a consistent cross-platform fallback where the system font is unavailable; retain a confident, editorial typographic hierarchy inspired by Apple's product advertising, without copying Apple's brand assets.
- Define design tokens for light and dark themes from the beginning. Light is the primary default direction; dark mode is a complete, intentionally designed alternative, not a mechanical colour inversion.
- Support system theme preference plus a manual user override, and remember the user's selection.
- Check text contrast, charts, forms, tables, status colours, dialogs, report cards and notifications in both themes.
- A finance/payment card may use a striking black surface as a deliberate component even while the rest of the application is in light mode. It must remain readable and must not imply that ACADIVA is a bank or stores money.
- Glassmorphism is a restrained surface treatment for selected cards, overlays or navigation accents. It must never reduce text contrast, obscure data or turn every panel into a translucent layer.

## 42. Core product scope and automatic cross-dashboard data consistency — 15 November 2026

### 42.1 Product scope principle

ACADIVA must prioritise the smallest set of features that solves essential, frequent school-management problems reliably. Do not add a feature merely because it is common in other school software or technically possible. Every proposed feature must answer: which real school problem does it solve, who uses it, how often, what manual work does it remove, and what complexity/support burden does it add?

Late-coming capture is explicitly excluded from the core product and normal teacher workflow. It must not reappear as a default attendance status, teacher task or dashboard metric. Keep optional/experimental ideas out of the primary navigation until validated by pilot schools.

### 42.2 Essential initial product modules

1. School setup and configuration: school profile, academic sessions/terms, classes/arms, subjects, grading rules, staff and role permissions.
2. Student records and admissions: student identity and guardian links, enrolment/class placement, essential contact and emergency information, record updates and authorised transfer/exit handling.
3. Role-based accounts and access: proprietor, principal, authorised school administrator/registrar, bursar and teachers; parent/guardian portal. No mandatory independent student account in the initial release.
4. Teacher/class assignment and timetable: assign teachers to classes/subjects; maintain a school timetable; update affected teacher and class views after authorised changes.
5. Daily attendance: simple present/absent register, bulk “Mark all present”, change exceptions, review and submit. No routine late-coming workflow.
6. Assessments and results: configurable assessment components and grading; guided mark entry; validation; draft/submitted/reviewed/published states; report cards.
7. Fees and payment records: fee structures/invoices, payment plans where approved, verified payment records, receipts, balances and reconciliation. Keep school subscription revenue separate from school fee collections.
8. Parent portal: switch between linked children; view authorised attendance, published results, timetable and fee information; receive relevant notices.
9. Announcements and in-app notifications: authorised role sends notices to defined audiences; recipient inbox and unread state.
10. Essential reports and exports: attendance summaries, student lists, fee balances/collections, assessment completion/results and report cards.
11. Audit, security and reliability: tenant isolation, role checks, change history for sensitive records, backups, recovery, error monitoring and support tools.

### 42.3 Features not required for the initial release

- Routine late-coming/early-departure recording.
- Mandatory student logins or independent student dashboards.
- Compulsory homework/assignment management.
- Library, transport, inventory, visitor management, school bus tracking and asset management.
- Complex behaviour points, gamification, social feeds or class chat.
- Unnecessary teacher performance scoring or surveillance dashboards.
- Multiple attendance systems (daily plus every lesson) without evidence that pilot schools need both.
- AI features, AI APIs, chatbots, automated grading or AI-generated reports.

These may be reconsidered only through explicit discovery and a documented decision. Their appearance in a long-term idea list is not approval to build them.

### 42.4 One authoritative record, role-specific views

<b>Core architecture decision:</b> each important school event is recorded once in its authoritative module. All authorised dashboards and portals read the same saved record or its correctly derived aggregate. No role should manually re-enter the same fact into a second dashboard.

Examples:

| Authoritative action | Internal views updated after successful save | External/parent visibility |
| --- | --- | --- |
| Teacher submits daily attendance | Teacher register; principal attendance view; proprietor attendance summary; administrator register | Linked parent sees their child's saved attendance according to school policy |
| Teacher saves a test/assessment score | Teacher mark sheet; assessment record; principal academic progress/review view; proprietor academic completion/overview | Parent sees score only when the relevant result/component is authorised for release or published under school policy |
| Teacher submits completed marks | Submission status and review queue; class/subject completion metrics; authorised management academic overview | No premature publication; parent sees approved/published result only |
| Principal approves/publishes results | Official result record; principal/proprietor academic summaries; publication status | Linked parent portal shows the published result/report card |
| Bursar records a cash/bank payment as received and verified | Student account ledger; bursar finance register; principal/proprietor finance summary; administrator view | Linked parent sees the verified payment, receipt and updated balance |
| Payment gateway confirms an online payment | Payment transaction and student ledger after server-side verification; finance summaries | Linked parent sees confirmed payment and receipt |
| Principal/admin changes timetable | Authoritative timetable and relevant class/teacher schedule views | Notify affected users; parent notice only when school policy says the change affects them |
| Principal sends announcement | Announcement record, sender view and delivery state | Selected recipients see it in their in-app inbox; offline recipients see it on next connection |

<b>Visibility and approval are separate from data consistency.</b> An assessment score can be saved once and immediately appear in internal dashboards as “draft”, “submitted” or “awaiting review”. That does not mean it should be exposed to parents before approval/publication. A payment marked as received but not verified must remain visibly unverified and must not be counted as confirmed revenue or silently reduce a confirmed balance.

### 42.5 What “immediately updates” means technically

- The server/database commit is the authoritative success event.
- After a successful commit, invalidate/refetch affected queries or use Supabase Realtime to refresh connected clients promptly.
- Dashboard totals and charts must be derived from the authoritative records, not separately editable copies.
- Show clear save states: saving, saved, failed, and offline/sync pending where applicable.
- Do not display an optimistic local update as confirmed to other users before server acceptance.
- If realtime delivery is unavailable, provide reliable refresh/revalidation so the UI converges to the latest server state.
- Handle duplicate submissions safely using idempotency or equivalent duplicate protection.
- Enforce tenant isolation, role and class/subject permissions on the server/database, not only by hiding buttons in the UI.
- Record who performed sensitive actions and when; preserve correction history.
- For published results, preserve the distinction between internal draft/submission/review and parent-visible publication.
- For financial records, distinguish pending, failed, received-unverified, verified, reversed/refunded and reconciled states as applicable.

### 42.6 Dashboard responsibilities — do not create duplicate data entry

- Teacher dashboard: today's timetable, assigned classes/subjects, attendance action, mark-entry/review tasks and relevant notices. No unrelated school-wide finance or student directory.
- Principal dashboard: school-day operations, attendance completion/absences, timetable, assessment submission/review progress, published results, staff notices and tasks requiring action.
- Proprietor dashboard: concise school-wide overview of enrolment, verified fee collection/outstanding balances, attendance, academic completion/results publication, admissions and key operational exceptions. Do not expose unnecessary individual student details on the landing screen.
- Administrator/registrar dashboard: admissions, student records, class placement, staff/class configuration and operational registers according to assigned permissions.
- Bursar dashboard: invoices, payment register, verification/reconciliation, receipts, balances and financial reports.
- Parent dashboard: linked children, each child's attendance, published results, timetable, fee invoices/payments/receipts and relevant announcements.

Every dashboard is a role-specific view of the same underlying school records. It is not a separate data-entry system.

### 42.7 Acceptance criteria for cross-dashboard consistency

- [ ] A teacher submits attendance once; all authorised internal dashboards reflect the saved record without manual re-entry.
- [ ] A linked parent sees the child's attendance after the record is saved, subject to configured parent visibility policy.
- [ ] A teacher saves an assessment score; authorised internal academic views reflect it with the correct draft/submitted status.
- [ ] Parents cannot see unpublished marks or draft results.
- [ ] Once results are approved and published, the linked parent portal displays the official result.
- [ ] A verified payment updates the student ledger, bursar register, proprietor financial totals and linked parent portal from one transaction record.
- [ ] An unverified cash/bank entry is not counted as confirmed collection.
- [ ] An authorised timetable edit updates the affected teacher's schedule from the authoritative timetable.
- [ ] A notice is stored once and appears in the selected recipients' in-app inbox; delivery state is not confused with read state.
- [ ] If the network fails, the user sees a pending/failed state and the system does not falsely report server confirmation.
- [ ] Duplicate taps/retries do not create duplicate attendance submissions, payment records or announcements.
- [ ] A user cannot view another school's records or records outside their authorised role/class/guardian relationship.

### 42.8 Scope control rule

Before a feature enters the Core or Pilot release, record: validated problem, intended role, frequency, workflow, data required, permission boundary, screen impact, integration impact, failure states, acceptance test, and what simpler alternative was considered. If the feature does not materially improve an essential workflow, defer or reject it. Keep the first release focused on reliable student records, attendance, timetable, assessments/results, fees, parent access, communication and management visibility.

## 43. Online admissions, parent application links and student onboarding — 15 November 2026

### 43.1 Product requirement and principle

Online application and admissions are a core ACADIVA capability, not a later cosmetic website feature. Each school must be able to receive applications through a shareable school-specific link. A parent should be able to complete an application on a phone without first visiting the school or creating a complicated account. The school retains authority over screening, admission decisions, class placement and activation of the official student record.

The workflow must avoid entering the same student's information twice. An application is the source record during admissions; when the school admits the applicant, ACADIVA converts or promotes that application into the authoritative student record while preserving its history and submitted documents.

### 43.2 School-specific application link

- Each school receives a public admissions page on its ACADIVA school subdomain, for example <code>schoolname.educat...</code> (final domain convention remains subject to domain decisions).
- The school can copy and share a stable admissions URL through WhatsApp, email, its website, social media, printed QR code or direct message.
- The link opens the school's own branded application page, clearly showing school identity, contact details, application instructions, available entry classes and whether applications are open.
- The school can configure whether applications are open, closed, or open for selected classes/academic sessions.
- Where the school wants a controlled intake, it can create a specific application link or intake campaign with a selected session, entry class, deadline and optional reference/source label. Do not make campaign management mandatory for a small school.
- The application page must be mobile-first, fast on modest connections, accessible and straightforward. Parents should not need to install an app.

### 43.3 Parent application journey

1. Parent opens the school's link.
2. Parent reads the admission information and selects the intended academic session and entry class, where the school has enabled those choices.
3. Parent enters the applicant's details and the parent/guardian's contact details.
4. Parent provides required previous-school and other admission information configured by the school.
5. Parent uploads only the documents the school requests. File types, size limits and upload progress must be clear.
6. Parent reviews the application, confirms the information is accurate and submits.
7. ACADIVA creates a unique application reference and shows a clear confirmation. Where contact verification is enabled, the parent verifies the phone number or email using an appropriate code/link.
8. Parent receives an application acknowledgement and can later check status through a secure reference-and-verification flow or a lightweight applicant portal. Do not expose an applicant's personal information through a guessable public URL.

The form should be divided into short, understandable steps with save-and-resume where practical. It should clearly identify required fields, allow correction before submission and explain why sensitive information is requested. Avoid asking for information the school does not actually need at application stage.

### 43.4 School-side admissions workspace

- New applications enter a dedicated admissions queue for authorised proprietor, principal, registrar or admissions staff.
- Staff can filter by intake/session, class applied for, submission date and status.
- Each application has a review page containing the submitted details, parent contacts, requested class, uploaded documents, application reference, submission timestamp and activity history.
- Authorised staff can add internal notes, request missing information, mark documents as checked, contact the parent and record a decision.
- Application statuses should be explicit and configurable only where necessary: Draft (parent-side, if supported), Submitted, Under review, More information required, Offered, Accepted, Waitlisted, Declined, Withdrawn and Converted to student.
- Status changes must record who changed the status and when. Internal notes must never be visible to parents.
- Staff must be able to assign an application to a reviewer where the school needs this, without making assignment a compulsory step for every school.
- Duplicate detection should flag likely matches using appropriate combinations of name, date of birth and guardian contact. It must not silently merge records or automatically reject an application.
- The school can export or print an application where operationally necessary, subject to permissions.

### 43.5 Admission decision, offer and parent response

- An authorised school decision-maker reviews the application and records the admission decision.
- The school can issue an admission offer showing the offered class/entry level, academic session, response deadline, conditions and any next steps configured by the school.
- The parent can accept or decline the offer through a secure link or applicant status page.
- The school can request additional documents or corrections before making a final decision.
- An offer is not the same as enrolment. The system must distinguish Offered, Parent accepted, Enrolment requirements pending and Fully enrolled/active.
- Where a school requires an admission fee or deposit, ACADIVA may record the required amount and payment status. Do not make payment a universal prerequisite or imply that an unverified transfer is paid.
- The school may admit a student without an online payment if its own policy allows it; authorised staff must be able to record the reason/status.

### 43.6 Class placement and conversion to the official student record

The school, not the parent, controls final placement. A parent may request a class/entry level, but that request is not a confirmed placement.

On admission, an authorised staff member must be able to:

- Confirm the academic session and actual class/arm placement.
- Check class capacity or any configured admission limit.
- Assign or confirm the official student identifier using the school's numbering rules.
- Confirm the student's start date and enrolment status.
- Link one or more verified parent/guardian accounts with the correct relationship and permissions.
- Review and map application fields into the student information record.
- Carry forward submitted documents and preserve the original application.
- Create the student's fee account or apply the appropriate fee structure only when authorised/configured.
- Generate the parent onboarding instructions and, where applicable, an invitation to the parent portal.

The conversion must not create a second student record if the applicant already exists. It must be an auditable transition from applicant to student, with the application reference retained on the student history. Rejected, withdrawn or waitlisted applications must not appear as active enrolled students or inflate enrolment dashboards.

### 43.7 Parent communication and status visibility

- The parent receives an acknowledgement after successful submission.
- The parent can see a safe, concise status such as Submitted, Under review, More information required, Offer made, Accepted or Not admitted.
- The school can send a request for additional information and the parent can provide the requested update without submitting a completely new application.
- The school can send an offer and onboarding instructions.
- Communications should be stored against the application record. In-app parent notifications apply once the parent account is linked; email/SMS delivery is a separate channel and may incur provider costs.
- Do not expose internal reviewer notes, other applicants, staff-only documents or private school decision discussions.
- Delivery failure must not erase the application or reverse a recorded admission decision.

### 43.8 Permissions and safeguarding

- Public visitors can only access the school's public admission information and submit an application.
- Parents can access only applications they submitted or are explicitly authorised to manage, after appropriate verification.
- Admissions staff can review applications within their assigned school and role.
- Only authorised decision-makers can issue or approve admission offers and convert applicants into active students.
- Only authorised staff can set final class/arm placement and student identifiers.
- Uploaded documents must be stored privately, with access checks on every retrieval; never expose predictable public file URLs.
- Apply tenant isolation to every application, document, status update and communication.
- Collect only necessary personal data, define retention/deletion handling for unsuccessful applicants and restrict access to sensitive child information.
- Keep an audit history for viewing or changing sensitive application data where appropriate.

### 43.9 Dashboards and authoritative data consistency

- A submitted application immediately appears in the authorised admissions queue after the server confirms it.
- The proprietor's dashboard can show application volume, offers, accepted offers and enrolled students as separate measures.
- The principal/registrar sees the operational admissions queue and pending decisions.
- The parent sees only their own application's status and messages.
- An applicant must not count as an enrolled student until the authorised conversion/enrolment step is completed.
- Once converted, the official student record becomes the shared source for class lists, teacher registers, attendance, assessments, fees and the parent portal.
- Any class/arm or guardian relationship correction must update the authoritative record and dependent views without requiring duplicate entry.
- Admissions reports should distinguish applications received, offers issued, offers accepted and students actually enrolled.

### 43.10 Essential screens and states

Parent-facing:

- School admissions landing page.
- Application form (short, step-based sections).
- Document upload and review.
- Submission confirmation and application reference.
- Secure application status / resume page.
- Additional-information request response.
- Admission offer and accept/decline screen.

School-facing:

- Admissions overview and queue.
- Application detail and document review.
- Reviewer notes and activity history.
- Request-more-information action.
- Offer creation and decision recording.
- Class/arm placement and student conversion.
- Admissions settings (open/close intake, sessions, classes, form fields, documents, deadlines).
- Admissions reports.

All screens require loading, empty, validation, upload progress, saved, submitted, network failure and permission-denied states. The design should remain calm and uncluttered; do not turn admissions into a large CRM that small schools must learn.

### 43.11 Initial release boundary

Core initial release:

- School-specific shareable admissions link.
- Configurable basic application form and required documents.
- Parent mobile application and submission confirmation.
- School admissions queue and application review.
- Status updates and request-for-more-information workflow.
- Authorised admission decision and offer/acceptance record.
- Final class/arm placement by school staff.
- Conversion into one authoritative student record without duplicate entry.
- Parent/guardian linking and onboarding.
- Admissions audit history and basic admissions reporting.

Defer unless pilot schools demonstrate need:

- Complex entrance-exam scheduling and scoring.
- Multi-stage interview pipelines.
- Application fees and payment gateway checkout.
- Advanced campaign attribution/marketing automation.
- Bulk admissions integrations with external examination bodies.
- Automated ranking or algorithmic admission decisions.

### 43.12 Acceptance tests

- [ ] A school administrator can activate admissions and copy a school-specific link without developer assistance.
- [ ] A parent can complete and submit an application on a mobile phone.
- [ ] The parent receives a unique reference and clear confirmation only after server acceptance.
- [ ] The application appears in the correct school's admissions queue and nowhere else.
- [ ] Authorised staff can review documents, add private notes and update status.
- [ ] A request for more information reaches the parent through the configured channel and the parent can respond against the same application.
- [ ] An authorised decision-maker can issue an offer and record the parent's response.
- [ ] The parent cannot change the school's final class/arm placement.
- [ ] An admitted applicant converts into one student record with the original application history and documents retained.
- [ ] A duplicate applicant is flagged for human review rather than silently duplicated or merged.
- [ ] Applicants who have not been admitted do not count as enrolled students and do not appear in teacher class lists.
- [ ] Once enrolled, the student appears in the appropriate class list and relevant parent portal through the same authoritative record.
- [ ] Parent, staff and school-tenant permissions prevent unauthorised access to applications and documents.
- [ ] Retrying submission after a network interruption does not create duplicate applications.
- [ ] Admissions totals distinguish applications, offers, accepted offers and actual enrolments.

### 43.13 Product decision and open questions

Confirmed product direction: online applications through school-specific shareable links, parent submission, school-controlled review/admission, school-controlled final placement, and conversion into the authoritative student record are required parts of ACADIVA.

Still to validate with pilot schools:

- Exact application fields and documents by school type and entry class.
- Whether parent status tracking uses a secure reference flow, a parent account, or both.
- Whether admission offers require a deposit and how schools handle cash/bank transfers.
- Whether schools need multiple application intakes or simple open/closed admissions.
- Whether a school wants to publish class vacancies/capacity.
- Data retention period for unsuccessful applications.

Do not let these open questions delay designing the complete core journey. Configure school-specific requirements rather than hardcoding one universal Nigerian admission form.

## 44. Student Record Passport, portable academic history and verified exports — 15 November 2026

### 44.1 Product principle

Every student should have one continuous, authoritative student record within each school using ACADIVA. The record must be exportable in useful, professional formats so that a family is not locked into one school's software or dependent on access to a former school's portal.

ACADIVA should provide a Student Record Passport: an organised, school-issued history of a student's identity, enrolment, academic performance, attendance and relevant school records. It should support school transfers and applications to institutions abroad. It is a record and evidence package, not a promise that every receiving institution, examination body, embassy or immigration authority will accept it as a substitute for its own required documents.

### 44.2 Automatic profile creation and admission modes

- A successfully submitted application can automatically create a student profile in Applicant status, without creating an active enrolment or counting the applicant as an enrolled student.
- Each school can choose its admissions policy: manual review, configured auto-approval, or hybrid review.
- Auto-approval must be an explicit school setting controlled by an authorised decision-maker. It must have clear eligibility rules, an effective date and an audit trail.
- Applications that fail required-field checks, have missing mandatory documents, trigger possible duplicate matches or fall outside configured eligibility rules should be held for human review rather than silently approved.
- Auto-approval must not silently determine final class/arm placement, mark fees as paid, verify identity documents or waive school requirements.
- A school may configure a successful auto-approval to move an applicant to an Offered or Accepted state, but the exact transition must be clear to the parent and school.
- The profile should retain the application reference and history. On actual enrolment, it becomes the student's authoritative school record; the system must not create a second student profile.
- Applicant, offered, accepted, enrolled, transferred, withdrawn and graduated statuses must remain distinct.

### 44.3 Student Record Passport contents

The Passport should be assembled from the authoritative student record and approved school records, with clearly labelled sections:

1. Student identity: full legal name as recorded by the school, school student ID, date of birth and other necessary identifying details. Sensitive identifiers should only be included when specifically required and authorised.
2. School and enrolment history: issuing school, campus where applicable, admission date, academic sessions attended, classes/arms, promotion history, and transfer/withdrawal/graduation dates where recorded.
3. Academic history: session, term, class, subjects, assessment components where relevant, scores, grades, totals and approved remarks.
4. Attendance history: school days in session, attendance recorded, present days, absent days, excused absences where used, and calculation method/percentage. Do not invent attendance for dates without reliable records.
5. Grading context: maximum marks, assessment weighting, grade boundaries, grading scale and any school-specific interpretation needed by a receiving institution.
6. Official school documents: approved report cards, transcripts, transfer letters and other documents the school has authorised for inclusion.
7. Issuance and verification: document reference, issue date, issuing school, authorised signatory and verification instructions.

Only data actually held and approved by the issuing school should appear. Missing or incomplete historical records must be identified as unavailable or not recorded, not fabricated or silently treated as zero.

### 44.4 Separate export products

ACADIVA should provide distinct exports for different real-world needs:

- Academic transcript: consolidated subject-level academic results across selected or all completed sessions/terms, with grading context and authorised approval.
- Student transfer record: relevant identity, enrolment/class history, academic results, attendance summary and school-issued transfer information for a receiving school.
- Complete student record: a broader authorised export of the student's profile, school history and relevant documents, with sensitive fields controlled by permissions and purpose.
- Term report card: the existing school-branded report for a single term; it remains distinct from the consolidated transcript.
- Data portability export: structured data for authorised transfer or reuse, with a clear data dictionary and file formats that preserve meaning.

The school should be able to choose a permitted date range, sessions/terms and document type. Where records are incomplete, the export must clearly show the coverage period and limitations.

### 44.5 Formats and usability

- Official human-readable PDF is the primary format for transcripts and transfer records. It should be printable, legible, school-branded and suitable for sharing with another school.
- CSV may be provided for structured tables such as grades, attendance summaries and enrolment history, with clear column names and a data dictionary. CSV is not a substitute for an authenticated official transcript.
- A structured machine-readable format such as JSON may be considered for system-to-system transfer when a real receiving integration or partner need is validated.
- The PDF should use consistent page numbering, student identifiers, academic periods, subject names, score maxima, grading legend and issue details. Avoid crowded layouts.
- Support an English-language export as the initial default. Additional languages or institution-specific formats should be based on validated demand.
- Do not automatically convert Nigerian grades into foreign grade equivalents or claim equivalence to another country's grading system. Preserve original scores and explain the issuing school's grading system.

### 44.6 Authenticity and document verification

- Every official transcript or transfer export must have a unique, non-guessable document reference.
- The document should identify the issuing school, issue date, authorised signatory and the scope/period covered.
- Where a school has configured it, include the authorised signatory's name/title and school stamp or approved signature image. ACADIVA must not fabricate a signature or imply approval that has not occurred.
- Include a QR code or verification URL that resolves to a minimal verification page.
- Verification should confirm whether the reference was issued by the named school, the document type, issue date and whether it remains valid or has been superseded/revoked. Do not reveal the full student record on a public verification page.
- Preserve the exact issued document or a tamper-evident representation of its contents, issue metadata and record version. A later correction must not silently rewrite a previously issued document.
- If a school corrects a record, authorised staff must record the reason and before/after values. The school can issue a corrected document with a new reference and mark the earlier issue as superseded or revoked, while preserving the audit history.
- Verification confirms document issuance and integrity; it does not guarantee that a receiving institution or government authority accepts the document for its particular purpose.

### 44.7 Consent, permissions and secure sharing

- Parents/guardians or the legally authorised requester should be able to request or download permitted records for a linked child, subject to school policy and applicable law.
- The school must be able to control which roles can generate, approve, issue and revoke official exports.
- A teacher must not independently issue an official consolidated transcript unless explicitly authorised.
- A parent may request a record, but official issuance may require school review and approval.
- Sharing with a receiving school should use a secure, purpose-limited link or controlled document delivery. Links should be non-guessable, revocable and optionally expire.
- Do not make a student's full academic history publicly searchable. Verification pages disclose only the minimum required information.
- Apply role-based access, tenant isolation, access logging, secure private document storage, retention rules and appropriate handling of child data.
- Where a student reaches the age at which they can exercise relevant rights independently under applicable law or policy, the product's consent and access model must accommodate that; do not assume a parent always has unrestricted authority.

### 44.8 Transfer workflow

1. Parent/guardian or authorised requester asks the school for a transfer record or transcript.
2. ACADIVA creates a request with the student, requested record type, recipient/purpose where supplied and request date.
3. Authorised school staff review the student's identity, academic history, attendance coverage, outstanding corrections and any required approvals.
4. The authorised school officer approves and issues the export.
5. ACADIVA generates the PDF and verification reference, records the issuer and document version, and makes it securely available to the requester or authorised recipient.
6. If the student is leaving, the school separately records the student's transfer/exit status and effective date. Issuing a transcript alone must not automatically withdraw the student.
7. The historical record remains preserved by the issuing school according to its retention obligations. The student's family should retain the issued document even after the school account or portal access changes.

A receiving school using ACADIVA may import structured information only through an authorised import workflow with human review. Imported historical grades and attendance must be labelled with their original issuing school and must not be represented as records created or verified by the receiving school.

### 44.9 International applications and attendance evidence

- Provide a consolidated transcript and attendance statement that can be understood by a school or institution outside Nigeria.
- Include the issuing school's name and contact details, academic calendar/session context, class/year level, subject names, score maxima, grading legend and attendance calculation method.
- Distinguish school days in session from days the student was expected to attend where the data supports that distinction.
- Clearly identify excused absences, unexcused absences and unrecorded periods where the school has reliable classifications. Do not infer reasons for absence.
- Preserve the original Nigerian marks and grades. Do not create unsupported GPA, foreign grade conversion, equivalence or credential evaluation.
- Allow an authorised school officer to attach a school letter or explanation where the receiving institution requests clarification.
- Make the PDF professional and easy to print, but do not claim it replaces external examination certificates, credential evaluations, notarisation, apostille, certified translations or other documents that a particular institution or authority may separately require.

### 44.10 Dashboard and lifecycle integration

- The Student Record Passport is a view/export of the authoritative student record, not a second database requiring separate data entry.
- Approved attendance and published/approved academic results flow into the relevant Passport sections.
- Corrections to source records follow permissions and audit rules; previously issued documents remain historically preserved.
- The parent portal should provide a clear way to request or download permitted reports and request official transcripts/transfer documents.
- The school administration workspace should show pending record requests, issued documents and any corrected/superseded documents.
- Student transfer/withdrawal should update the student's enrolment status and remove the student from active class workflows from the effective date, while preserving historical results, attendance, fees and documents according to retention rules.
- A transfer to another ACADIVA school must not expose the former school's records to the new school automatically. Sharing/import requires an authorised request and consent/authority checks.

### 44.11 Initial release requirements

Core capability:

- Automatically create an Applicant profile after a valid application submission.
- Preserve the same profile through admission and enrolment.
- Maintain structured session, term, class, subject, grade and attendance history.
- Generate a professional PDF term report and consolidated academic transcript.
- Generate an attendance summary with transparent date coverage and calculation.
- Include grading context and issuing-school details.
- Require authorised approval for official transcript/transfer issuance.
- Assign unique document references and provide a basic secure verification page/QR.
- Preserve issued versions and audit corrections.
- Provide secure parent download/request access and school-side issuance controls.

Later, subject to demand:

- Secure school-to-school transfer and structured record import.
- JSON/API-based portability and receiving-school integrations.
- Institution-specific export templates.
- Advanced multilingual or international document formats.
- Automated external credential-verification integrations, only where an authoritative provider exists.

### 44.12 Acceptance tests

- [ ] A valid parent application creates one Applicant profile, not an enrolled student.
- [ ] The school's configured manual, auto-approval or hybrid policy is followed and recorded.
- [ ] Auto-approval does not bypass configured exceptions or silently assign an unapproved class.
- [ ] On enrolment, the Applicant profile becomes the official student record without duplication.
- [ ] Authorised staff can generate a transcript covering selected or all available sessions and terms.
- [ ] Transcript grades include maximum scores and the issuing school's grading legend.
- [ ] Attendance exports state their date range, school days and calculation method, and do not invent missing records.
- [ ] A transfer record can be issued separately from a term report card.
- [ ] An official PDF has a unique reference and a verification mechanism.
- [ ] A person with the verification link cannot browse the student's entire profile.
- [ ] A correction does not silently alter an already issued document; corrected versions retain their own references and history.
- [ ] A parent can only request or access records for a child they are authorised to represent.
- [ ] An unauthorised teacher cannot issue an official transcript.
- [ ] A transfer/withdrawal removes the student from active class workflows while preserving authorised historical records.
- [ ] Imported historical records retain the identity of their original issuing school and are not misrepresented as receiving-school records.

### 44.13 Confirmed direction and validation points

Confirmed direction: every student should have a portable, exportable record; automatic Applicant profile creation should reduce duplicate data entry; schools may configure admission approval modes; official records must be professionally formatted, contextualised and verifiable.

Validate with pilot schools and parents:

- Which documents schools commonly issue for transfers and international applications.
- Which staff member is authorised to approve and sign transcripts.
- Whether parents can download standard reports immediately while official consolidated transcripts require approval.
- Retention periods and legal requirements for child records and unsuccessful applicants.
- Which receiving institutions require paper originals, certified copies or additional verification.

Do not promise universal international acceptance. ACADIVA's responsibility is to produce accurate, contextualised, verifiable records and make them securely portable.

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

## 47. School Finance, Academic Term Lifecycle, Student Lifecycle, SMS-First Parent Communication and Template-Led CTO Onboarding — 15 November 2026

<b>Status:</b> Current decision record based on the founder's product review on 15 November 2026. This section adds detail and corrects emphasis in the earlier blueprint. It does not remove the original history. Where this section conflicts with earlier proposals in Sections 36–46 or checklist items in Section 40, Section 47 is the latest product direction. Section 40AB is its execution checklist.

### 47.1 Purpose and guiding decisions

ACADIVA must make the real operating work of a school easier without making the software itself complicated. The system should do the difficult work of preserving records, applying rules, connecting workspaces and tracking changes. School users should see a small number of clear actions relevant to their responsibilities.

Confirmed direction:

- Strengthen school finance into a proper financial operating system, not merely a payment collection screen.
- Treat the end-of-term and new-term cycle as a first-class school workflow.
- Maintain a continuous student lifecycle and history.
- Do not add an elaborate separate teacher productivity/task-management system. Keep teacher interaction focused on the essential authorised actions already agreed: assigned classes, attendance and assessment/marks, with only necessary context.
- Use SMS as a primary way to reach parents for important information because parents should not have to open an app to receive every notice.
- Keep the parent portal for detailed records, report cards, invoices, receipts, documents and actions; it complements SMS rather than replacing it.
- ACADIVA employees, including CTOs, perform agreed school setup and migration work. Schools provide/confirm source information and approve critical records; they should not be expected to do all technical configuration themselves.
- Every school should start from an appropriate reusable template. Templates are starting configurations, not rigid structures.
- Existing records and configuration must be preserved. Deactivation, archiving and hiding from active views are preferred to destructive deletion.

### 47.2 School financial operating system

Finance is a core operational system for the school. Its purpose is to make every charge, payment, allocation, adjustment and balance understandable and traceable to the school, student, fee item and academic period.

#### 47.2.1 Fee setup and billing

Authorised school finance staff or administrators configure:

- Fee categories such as tuition, development levy, PTA levy, examination, books, uniforms, transport, meals and other school-defined charges.
- Whether a charge is mandatory or optional, recurring or one-time.
- Amount, currency, due date, applicable session/term, class, student or approved group.
- Different fee schedules for different classes or individual students where the school has a legitimate approved arrangement.
- Instalment schedules and due dates.
- Discounts, scholarships, sibling concessions, staff-child concessions and waivers, with reason, authority, effective period and audit history.

ACADIVA should generate a clear student bill/statement for the relevant term. The parent and authorised finance staff should be able to distinguish the original charge, approved discount/waiver, payments received, amount allocated and remaining balance.

Do not silently rewrite an issued bill when the school changes its fee schedule. Record an adjustment or revised bill with its reason, actor, date and relationship to the original.

#### 47.2.2 Payment recording and allocation

Support:

- Full and partial payments.
- Multiple payments against one invoice.
- A single payment allocated across multiple valid fee items where the school permits it.
- Cash, direct bank transfer and supported online payment methods.
- School-approved instalment plans.
- Overpayments, duplicate payments, unapplied credit and payment corrections.
- Refunds and reversals where applicable.

Every payment must have a unique internal reference and, where available, an external bank/provider reference. It must be allocated to the correct student and bill/fee item. A payment received for one sibling must never be silently allocated to another sibling.

Payment states must be explicit, for example: recorded/unverified, pending, verified/settled, failed, reversed, under review and refunded. The exact state model must reflect the payment method. An unverified manual entry must not be reported as confirmed money received or silently reduce the confirmed outstanding balance.

For cash and direct transfers, record who entered the payment, who verified it where a separate verifier is required, date, amount, reference/evidence and reason for any exception. A screenshot by itself is not proof that funds reached the school's account.

For online payments, use provider verification/webhooks and settlement reconciliation. ACADIVA should record school bills and payment events; the default design remains direct settlement to the school's designated account through an appropriate licensed provider. ACADIVA should not imply it is a bank or holds pooled school funds.

#### 47.2.3 Financial ledger and immutable history

The financial ledger is the authoritative source for balances and finance reporting. It should contain linked records for:

- Charges/invoices.
- Payment transactions.
- Payment allocations.
- Discounts, scholarships and waivers.
- Adjustments and credit notes.
- Refunds and reversals.
- Expenses and approvals.
- Provider fees and settlement records.
- Reconciliation exceptions.

Never hard-delete a successful payment, issued receipt or historical charge. Corrections should be represented by traceable reversing, adjusting or reallocating entries. Preserve before/after values, actor, timestamp, reason and approval where required.

A balance is derived from the valid financial entries and allocations, not independently typed into several dashboards. The same authoritative balance must appear in the bursar, authorised management and linked parent views, subject to permissions and server-confirmed updates.

#### 47.2.4 Expenses and management visibility

Include practical school expense recording, with categories such as salaries, utilities, maintenance, facilities, academic materials, transport and administration. Capture payee/supplier, amount, date, payment method, category, description and supporting document where available. Schools may configure approval thresholds and a second-person review for material expenses.

Provide clear reporting for:

- Amount billed.
- Amount collected and verified.
- Amount recorded but still unverified.
- Outstanding and overdue balances.
- Collections by term, class, student, fee item and payment method.
- Discounts, waivers, refunds and reversals.
- Expenses by category and period.
- Net cash/settlement position where supported by verified source data.
- Reconciliation exceptions and unmatched transactions.

Do not label gross collections as profit. Do not imply that these initial tools replace a complete statutory accounting package, tax system or payroll system.

#### 47.2.5 Financial term close

Financial close is related to, but separate from, academic result publication and academic term close.

At the end of a term, authorised finance staff should be able to review issued bills, verified payments, unverified entries, outstanding balances, unapplied credits, refunds, expenses and reconciliation exceptions. The school decides its policy for carrying outstanding balances into the next term. ACADIVA must preserve the original term and invoice relationship when balances are carried forward.

Closing a term must not erase outstanding debt, rewrite a historical receipt or prevent an authorised correction. Reopening or adjusting a closed period requires permission, reason and audit history.

### 47.3 End-of-term and new-term operating lifecycle

The academic session and term lifecycle must connect school setup, daily records, assessment, results, promotion, finance and the next term. ACADIVA should guide authorised school leaders through the work that must be completed without creating unnecessary tasks for teachers.

#### 47.3.1 Term setup

An authorised school administrator/principal configures:

- Academic session and term name.
- Start, end, resumption and closing dates.
- School days, holidays and closure dates.
- Classes, arms and subjects active for the term.
- Assessment components, maximum scores, weightings and grading rules.
- Teacher/class/subject assignments and timetable.
- Applicable fee schedules and due dates.
- Calendar events, examination dates and relevant parent notices.

The school may start from its saved configuration or a reusable template. Changes must be scoped to the intended term and must not silently alter historical terms.

#### 47.3.2 During the term

The normal workflows continue:

- Attendance is recorded once by an authorised person and reflected in permitted views.
- Teachers enter marks for their assigned classes/subjects when required.
- Finance staff record bills, payments, verification, allocations and expenses.
- School management publishes approved timetable changes and notices.
- Parents receive relevant messages through the configured channels, including SMS.
- Student status and class placement remain accurate.

Do not introduce a separate elaborate teacher task-management system. The teacher experience remains focused on the essential assigned actions and clear submission states.

#### 47.3.3 Term-close readiness

Before results are finalised, the principal or authorised academic lead should have a concise term-close overview showing exceptions requiring attention, such as:

- Missing or unsubmitted assessment marks.
- Invalid scores or missing assessment components.
- Results awaiting review or approval.
- Students whose status or class placement needs confirmation.
- Report cards not yet generated or checked.
- Attendance records that remain incomplete or disputed.
- Approved result corrections awaiting completion.

The finance workspace separately shows financial-close exceptions: unverified payments, unmatched settlements, unapplied credits, outstanding balances, refunds/reversals and expenses awaiting approval.

The system should show what is complete, incomplete, blocked or awaiting an authorised decision. It must not manufacture completion or silently convert missing marks into zero.

#### 47.3.4 Result review and publication

The school-configured academic approval chain applies. Teachers or authorised academic staff submit marks; designated reviewers check them; the authorised approver publishes results.

After publication:

- The published result/report card is a dated academic record.
- Parents can access only published results for their linked children.
- Any later correction requires permission, reason and a retained before/after history.
- A corrected publication creates a new traceable version; the prior version remains part of the audit history and is not silently overwritten.

#### 47.3.5 Promotion and new-term rollover

Before rollover, show a reviewable list of students and proposed outcomes:

- Promote to the next class/arm.
- Repeat the current class.
- Transfer out.
- Withdraw.
- Graduate or complete the final level.
- Remain pending because a school decision is outstanding.

An authorised school decision-maker reviews and confirms the changes. ACADIVA then creates the new class enrolment/history relationship while preserving prior classes, attendance, academic results and finance records. Do not move every student automatically based only on a score or a generic rule.

The new term should inherit approved reusable settings—such as classes, subjects, fee templates and timetable patterns—through a preview and confirmation process. The school must be able to change the new term without rewriting the old one.

#### 47.3.6 Term archive and reopening

A closed term remains readable to authorised users and available for reports, transcripts and audit. It is not deleted. If the school must correct a historical record, the action is permission-controlled, reasoned and versioned. Academic close, financial close and session completion must have distinct states so that one cannot accidentally imply the others are complete.

### 47.4 Student lifecycle management

ACADIVA must represent a student's relationship with the school over time, not just their current class.

The lifecycle should support appropriate states such as enquiry, applicant, admission offered, accepted, enrolled, active, promoted, repeating, on approved leave, transferred, withdrawn, graduated/completed and archived. Exact labels may be configurable where needed, but their meanings and permitted transitions must be clear.

Each transition records the effective date, actor, reason, source and relevant approval. A student who leaves the school remains in the historical record. A returning student should be matched to the existing identity where possible rather than created as a duplicate.

The system must preserve:

- Student identity and admission identifiers.
- Previous and current class/arm enrolments.
- Session and term history.
- Guardian relationships and authorised contact history.
- Attendance history.
- Assessment, result, report-card and promotion history.
- Fee invoices, payments, allocations and outstanding balances.
- Relevant documents and approved record corrections.

Changes to a student's name, date of birth or guardian relationship should update the authoritative profile with an audit trail; they must not create a new student. Age should be calculated from date of birth and the relevant date, not stored as an independently editable fact.

A student can have more than one authorised guardian. Parent/guardian access is based on verified relationships and explicit permissions, not merely possession of a phone number. The same guardian may be linked to multiple children. If a child moves between schools, each school's record ownership and access must be respected; one school must not see another school's private records without an authorised transfer process and lawful basis.

### 47.5 Parent communication — SMS-first for important notices

<b>Decision:</b> SMS is a primary external communication channel for important parent information. ACADIVA must not assume that parents will regularly open an app or keep push notifications enabled.

The parent portal remains valuable for detailed and persistent information: report cards, fee statements, receipts, attendance history, documents, notices and actions. SMS is the direct notification channel that brings parents' attention to important events and can direct them to the portal where more detail is needed.

Use cases may include:

- Admission application confirmation, status changes and offers.
- Important school announcements and resumption reminders.
- PTA meeting invitations and schedule changes.
- Urgent school closure or safety notices.
- Absence alerts where the school has enabled them and the attendance record is confirmed.
- Fee invoices, due-date reminders and payment confirmations.
- Result publication notifications.
- Event, examination and excursion reminders.

Messages should be concise, understandable and branded with the school identity/sender name where the provider and regulatory rules permit. Include a secure link or reference where the parent needs to take an action; do not put sensitive student results, detailed financial information or private records into plain SMS.

#### 47.5.1 Contact data and delivery safeguards

ACADIVA may use the guardian phone numbers already held in the school's records, but phone numbers must be accurate, appropriately collected and verified where practical. The school must establish and record the appropriate lawful basis, notices, preferences and consent where required. Provide a way to correct contact details and manage communication preferences. Respect applicable opt-out and sender-identification rules, especially for non-essential/promotional messages.

Support multiple authorised guardian contacts and school-configured recipient rules. Do not assume every guardian should receive every message. Sensitive communications may require a particular authorised contact or channel.

#### 47.5.2 SMS operations and cost control

SMS is not cost-free. The school or agreed subscription/usage arrangement must fund message delivery. Show estimated/actual usage, available allowance or balance, cost, provider status and low-balance alerts. Do not promise unlimited SMS under a plan until unit economics and provider terms support it.

Track message creation, audience, school, sender, timestamp, provider reference and delivery state where supported (queued, submitted, delivered, failed or unknown). Retry transient failures with limits, avoid duplicate messages, and expose failures to authorised school staff. Keep one authoritative announcement/notification record with separate delivery attempts across SMS, email and in-app channels.

SMS does not make the whole system offline: the provider still needs connectivity to submit messages and the parent's phone needs cellular coverage. Its advantage is that the parent does not need mobile data, a smartphone app or a portal login to receive a text.

### 47.6 School templates and configuration

Every school should be offered a starting template. ACADIVA should not force a school to build its academic structure from a blank screen.

Provide sensible Nigerian school templates for common structures, for example:

- Nursery / early years with configurable levels (such as Nursery 1, Nursery 2 and Nursery 3).
- Primary with configurable classes (for example Primary 1–5 or Primary 1–6, depending on the school).
- Junior secondary.
- Senior secondary.
- Combined nursery, primary and secondary structures.

These are examples, not universal assumptions. The school may use different naming conventions, class counts, arms, subjects, grading rules, terms and fee categories.

Templates may include starter class/arm structures, common subjects, sample grading configurations, term structure, fee-category suggestions and a basic calendar. They must be editable before activation and must not silently impose policies the school has not approved.

A school can save its own configuration as a reusable template for later sessions or branches, subject to permissions. Applying a template to an existing school must show a preview of what will be added, changed, deactivated or left untouched.

### 47.7 CTO / ACADIVA employee school setup experience

School onboarding is an important ACADIVA operational service. The founder/CEO and authorised ACADIVA employees visit or engage with schools, gather authorised source information and use the internal Operations workspace to configure the school. The CTO is not expected to ask the school to do all technical setup itself.

The CTO dashboard should be deliberately designed around a small number of obvious, high-value actions rather than a crowded collection of admin widgets.

Suggested primary actions:

1. <b>Create a school</b> — create and configure a new school's workspace.
2. <b>Open an existing school</b> — search/select a school and manage its authorised configuration and onboarding.
3. <b>Continue onboarding</b> — return to incomplete setup or migration work.
4. <b>Import records</b> — stage and validate student/staff data supplied by the school.
5. <b>Review exceptions</b> — resolve duplicate matches, missing fields, failed imports and decisions awaiting school approval.

The dashboard should show school status, onboarding progress, outstanding exceptions and recent operations. The user should always know whether they are in ACADIVA's internal workspace or operating within a selected school's context.

#### 47.7.1 Create a school flow

When the CTO chooses Create a school:

1. Capture and verify the school identity, authorised representative and contact details.
2. Select the school type/education levels.
3. Select an appropriate starter template or combined template.
4. Preview the proposed class structure and edit it for that school.
5. Configure the academic session and terms.
6. Configure subjects, grading and assessment components.
7. Configure fee categories and fee schedules, using school-approved information.
8. Configure school identity, logo, branding and subdomain.
9. Create authorised school leadership and staff accounts/invitations.
10. Add or import student and guardian records.
11. Review setup completeness and exceptions with the school representative.
12. Obtain school confirmation of critical information before marking the workspace ready for use.

The CTO may complete the technical configuration, but must not invent student data, fee policies, grading rules or school decisions. Source information and school approval must be retained where relevant.

#### 47.7.2 Open/manage an existing school flow

When the CTO chooses an existing school, the system opens its existing school record and configuration. It must not create another school, duplicate classes, recreate student records or overwrite existing settings.

The CTO can select a clear operation such as edit school profile, manage class structure, add a class, deactivate a class, adjust subjects, update an approved grading configuration, import students or continue onboarding. Each action should show the affected school and the consequences before saving.

#### 47.7.3 Class configuration and non-destructive changes

Example: a school currently has Primary 1 through Primary 5. An authorised administrator may add Primary 6, rename a class or stop using Primary 5. If Primary 5 has already been used by students or historical records, it must not be permanently deleted.

Instead, the authorised user can deactivate/archive it. The class should disappear from active class selection, new enrolment options and current school-facing lists where appropriate, but remain available in historical student records, past attendance, results, reports, exports and audit history. If the school has a public-facing website, inactive classes should not be presented as currently offered education levels.

A confirmation should explain whether the change affects active students, admissions, timetable, teacher assignments or fees. Existing student records must be reassigned through an explicit reviewed action if required; deactivating a class must not silently move students.

Apply the same non-destructive principle to subjects, fee categories, arms, staff accounts, school settings and other configuration used by historical records. Use archive/deactivate/supersede states instead of hard deletion except where a legally valid data-erasure process is required and has been separately designed.

#### 47.7.4 Student creation and migration

The CTO may create student profiles manually from school-authorised records or import them in bulk. A simple student record flow should capture the fields needed for the school's agreed setup, such as:

- Student's full name and school/admission identifier.
- Date of birth (age is calculated from this).
- Relevant demographic/contact fields required by the school.
- Parent/guardian name, verified phone number and relationship.
- Current admission/lifecycle status.
- Session, class and arm placement.
- Available previous school and academic history.
- Required documents and profile photograph where the school has an appropriate lawful basis.

The form should be short, grouped and progressively reveal optional fields. Do not overwhelm the CTO with every possible student field at once. Missing optional information should be visibly marked for later completion rather than invented.

Academic marks should ordinarily be entered by the assigned teacher or authorised academic staff through the mark-entry workflow. A CTO may assist with migration of historical grades only when the school supplies and authorises the source data. Such imports must preserve source, academic period, maximum score/grading context where known, importing employee, validation and school confirmation. CTOs must not invent marks or silently publish results on behalf of the school.

### 47.8 School join/referral links and automatic student profile creation

An existing school may share a school-specific admission/join link with prospective parents. The parent completes the mobile-friendly form and submits it directly into that school's admissions process.

On successful server acceptance:

- Create one Applicant profile linked to the application.
- Generate a unique application reference.
- Notify the parent through the configured channel, including SMS where enabled.
- Make the application visible in the correct school's admissions queue.
- Do not require a CTO to re-enter the applicant or student details.

Each school can configure its admission decision mode:

- <b>Principal/school approval:</b> the application creates an Applicant profile and awaits an authorised school decision.
- <b>Configured auto-approval:</b> eligible applications can proceed automatically under rules explicitly enabled by the school and recorded in the audit history.
- <b>Hybrid:</b> defined cases proceed automatically while exceptions require human review.

Auto-approval must not bypass required data, identity/guardian checks, capacity constraints or the school's stated admission policy. It must not silently decide a student's class, fee concession or other school-specific decision unless the school has explicitly configured and approved that rule.

Keep these states distinct: application submitted, Applicant profile created, under review, approved/offered, offer accepted, enrolled and placed in a class. Once the required admission decision and parent acceptance are complete, convert/match the Applicant into the authoritative student record and activate the relevant school relationships. The conversion must be idempotent: retries or repeated approvals must not create duplicate students. The CTO should only need to intervene when there is an exception, a data mismatch or a school-requested configuration task.

### 47.9 Simple experience, connected records and permission boundaries

These additions must preserve Section 46's one-product architecture:

- The school, student, guardian, class, term, invoice, payment and result are authoritative records, not separate copies per dashboard.
- CTO Operations, school management, finance, teacher and parent workspaces show permitted views of the same records.
- Every consequential change is validated and committed on the server before other workspaces show it as confirmed.
- Internal ACADIVA staff access remains scoped, purpose-limited, visible and audited.
- School representatives remain accountable for admission decisions, grades, fee policies and other official school decisions.
- A CTO can assist with setup and authorised migration without silently impersonating a school employee.
- Templates and deactivation must preserve historical records.
- SMS delivery attempts are linked to the authoritative school notice/event; SMS failure does not erase the notice.
- Parent-facing SMS must not disclose sensitive information to an unverified or unauthorised phone number.

### 47.10 Recommended initial release interpretation

The following should be treated as core design and implementation requirements for the first useful release, subject to pilot validation:

- Student lifecycle and non-destructive class/configuration history.
- Reusable school templates and template-led school setup.
- CTO create-school and open-existing-school workflows.
- Manual and staged bulk student migration with validation and duplicate detection.
- School-specific application/join link with Applicant profile creation and configured approval flow.
- Core financial ledger: fee setup, invoices, full/partial payments, allocations, verification, receipts, outstanding balances and basic reconciliation.
- Essential expense recording and term financial summary where feasible for the pilot.
- Academic term setup, close readiness, result approval/publication, promotion preview and next-term rollover.
- SMS for important parent notices with usage/cost visibility and delivery tracking.
- A simple teacher experience limited to essential assigned actions, not a new teacher task-management product.

Advanced accounting, automated bank-feed reconciliation, complex financial forecasting, bulk messaging campaigns and advanced multi-campus template inheritance may follow after real-school validation.

### 47.11 Open decisions and validation

The following remain to be decided through school discovery, provider review and technical design:

- Exact financial ledger/accounting model and whether any accounting export standard is needed.
- Payment provider, bank reconciliation method, settlement evidence and treatment of provider fees.
- School policies for carrying balances forward, term close and reopening closed periods.
- Which expenses require second-person approval and which finance roles can authorise adjustments/refunds.
- Exact starter templates and naming conventions for different Nigerian school types and states.
- Whether a template can be saved/shared across multiple schools under one owner, and who can approve that reuse.
- Required student fields and document retention for each school type.
- Exact join-link approval modes, eligibility rules, capacity checks and parent identity verification.
- SMS provider, sender ID registration, unit cost, message length/encoding, delivery receipts, retry policy and regulatory requirements.
- Default SMS events versus events each school can enable/disable.
- Which school actions may be completed under a CTO onboarding mandate and which require explicit school representative confirmation.
- Exact rules for class archival when active students remain assigned to the class.

### 47.12 Acceptance principle

ACADIVA is successful when a school can be configured without duplicate data entry; a parent can submit an application without a CTO re-entering it; a student can progress through the school without losing history; teachers can complete essential academic actions without navigating an oversized workspace; the bursar can explain every balance; the school can close one term and open the next with controlled review; and important parent messages can reach verified phone numbers without requiring parents to open the app.

The system must be tested with real school records and real role-based workflows before these requirements are considered complete.

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

## Section 50 — Provider-Independent SMS Architecture and BulkSMS Nigeria Integration — 16 November 2026

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

## Section 50 — ACADIVA: Product Principles, Differentiation, Experience, Scalability and Build-Quality Checklist

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

## Section 50 — ACADIVA Product Principles, Deliberate Engineering, Design Quality, Scale and Pre-Build Review

<b>Recorded: 16 November 2026</b>

<b>Purpose:</b> Make careful thinking, organisation, risk review and quality assurance mandatory before every product, design, database, infrastructure or code change. ACADIVA must be built deliberately, like a well-engineered building: understand the foundation, load, dependencies, future expansion, failure modes and maintenance consequences before adding or changing anything.

### 50.1 The governing principle: think before every step

No feature, screen, schema, integration, refactor, deployment or quick fix should begin with coding as the first action.

Before acting, the builder must understand:

- What are we building, and what user problem does it solve?
- Who will use it, in what role, on what device and under what conditions?
- How does it fit the existing product, architecture, data model and workflows?
- What already exists that should be reused rather than duplicated?
- What depends on this component, and what will this change affect?
- Can it support current needs and plausible future growth?
- What can fail, break, become slow, expose data or create confusing behaviour?
- How will errors be detected, recovered from and corrected?
- How will this be tested, verified and safely released?
- How will it be maintained, upgraded, migrated or rolled back?

<b>Working standard:</b> Think through the change repeatedly from product, user, design, engineering, security, data, performance, cost, accessibility and maintenance perspectives before implementation. The goal is to minimise avoidable bugs and imperfections, not to claim that software can ever be bug-free.

### 50.2 Mandatory pre-build / pre-change checklist

Do not start implementation until the relevant questions have been answered. If a material question is unknown, investigate it, record the uncertainty or ask for a decision instead of guessing.

- [ ] State the problem, intended outcome and measurable acceptance criteria.
- [ ] Identify affected users, roles, permissions and user journeys.
- [ ] Inspect the existing implementation, documentation, database schema, design system and related features first.
- [ ] Identify dependencies, shared components, integrations, routes, tables, jobs and other affected areas.
- [ ] Check whether an existing capability can be extended safely instead of creating a duplicate.
- [ ] Map the data flow: source of truth, reads, writes, validation, ownership, retention and audit requirements.
- [ ] Check tenant isolation and role permissions wherever school or user data is involved.
- [ ] Consider normal, empty, loading, success, error, retry, offline/slow-network and permission-denied states.
- [ ] Consider edge cases, invalid input, duplicate submissions, simultaneous actions and partial failures.
- [ ] Assess security, privacy, abuse, rate limits, secrets and sensitive-data exposure.
- [ ] Assess performance, query cost, storage, network payload, concurrency and background processing.
- [ ] Assess accessibility, mobile responsiveness, low-end devices and reduced-motion preferences.
- [ ] Assess animation impact: motion must be purposeful, smooth and non-blocking.
- [ ] Assess cost, vendor limits, free-tier quotas, lock-in and operational burden.
- [ ] Define tests and regression coverage before changing existing behaviour.
- [ ] Define migration, backup, rollback and recovery steps for risky changes.
- [ ] Review whether the change creates technical debt or makes future expansion harder.
- [ ] Document the decision, assumptions, risks and unresolved questions.
- [ ] Implement the smallest coherent change that meets the agreed outcome.
- [ ] Test in development/staging before production.
- [ ] Verify the actual user journey and inspect logs/monitoring after release.
- [ ] Update documentation and the checklist after learning something new.

### 50.3 Change-impact and safety rules

Treat the product as an interconnected system, not isolated screens.

Before changing a shared component, database table, authentication flow, permission, API, payment process, navigation structure or global style:

1. Identify every known consumer and dependent workflow.
2. Determine what must remain backward-compatible.
3. Check whether existing records need migration or backfill.
4. Plan how to handle partial deployment, retries and rollback.
5. Add or update regression tests.
6. Verify unaffected roles and features after the change.

Never make destructive database or content changes without a verified backup, migration plan and recovery path. Never solve one user's issue by weakening another user's security or changing a shared workflow without checking its impact.

### 50.4 Learn from competitors without becoming a copycat

Competitor products are research references, not blueprints to reproduce blindly.

MySchoolReg is one reference for understanding Nigerian school-management expectations. Its publicly presented feature areas include student records, score/assessment management, CBT, admissions and form sales, fee payments, receipts, report cards, parent access, timetables and student promotion.

For every reference feature:

- [ ] Understand the original problem it solves.
- [ ] Examine the complete user journey, not just the marketing description.
- [ ] Identify what works well and why.
- [ ] Identify friction, missing cases, limitations and opportunities to improve.
- [ ] Check whether the feature fits ACADIVA's target schools and product philosophy.
- [ ] Design an original, coherent ACADIVA experience.
- [ ] Validate with actual school owners, administrators, teachers, parents or students before treating assumptions as facts.

Do not copy branding, wording, visual identity, proprietary assets or implementation. The objective is to understand the category deeply and build a meaningfully better product through usability, reliability, thoughtful workflows and execution.

### 50.5 Product architecture: one central platform and individual school websites

The agreed product model has three connected experiences:

1. <b>Central ACADIVA website — </b>[<b>acadiva.ng</b>](http://acadiva.ng)<b> (proposed domain):</b> ACADIVA's main public site, product information, school registration and central login entry point.
2. <b>Individual school websites — for example, </b>[<b>greenfield.acadiva.ng</b>](http://greenfield.acadiva.ng)<b>:</b> each school's public-facing identity and content, including home, about, academics, gallery, news/announcements, achievements, admissions and contact information. The school website must include a visible Login action.
3. <b>Role-based school workspaces:</b> the private authenticated experience for proprietors, principals, school administrators, registrars, bursars, teachers, parents and students.

These are one connected platform, not separate products with disconnected accounts and data.

<b>Login and identity requirements</b>

- A user should have one ACADIVA identity and may be associated with more than one school.
- A login from a school's website should carry the intended school context into authentication.
- The platform must verify the user's membership and role server-side; never trust a school identifier supplied only by the browser.
- After authentication, route the user to the correct school and role workspace.
- If a user belongs to multiple schools, provide a safe school/workspace selector.
- Parents must only access children whose relationship has been verified by the relevant school.
- A central login at [acadiva.ng](http://acadiva.ng) must also support school selection or discovery without exposing private school data.
- A school's public website and its private portal must remain visually connected but clearly separated by permissions.

<b>School website template decision</b>

- Start with one excellent, mobile-first, reusable school website template.
- Each school can configure its logo, school name, colours, photos, text, contact details, gallery, achievements, announcements, events and admissions content.
- Keep the information architecture and core quality consistent while allowing controlled personalisation.
- Provide a website manager inside the school's authorised workspace.
- Allow schools to publish content and share direct public URLs, for example a specific achievement or admissions page.
- Consider custom domains and additional templates later, after the first template is validated.
- Do not force every school to commission a separately coded website.

### 50.6 Animation and interaction standard

ACADIVA should feel modern, polished and alive, not static or boring. Animation is a product-design requirement, but it must never compromise usability, accessibility, battery, responsiveness or performance.

Potential uses:

- Subtle page and section transitions.
- Scroll-triggered reveals used sparingly.
- Purposeful hero/media motion.
- Animated counters and data visualisations.
- Interactive galleries and image transitions.
- Smooth menus, dialogs, tabs and dropdowns.
- Clear feedback for saving, publishing, uploading, submitting and completing actions.
- Progress indicators and loading skeletons.
- Dashboard charts and status transitions.

Rules:

- Prefer lightweight CSS/native transitions and transform/opacity animation where appropriate.
- Avoid excessive animation, large motion effects, layout shifts and continuous decorative movement.
- Respect reduced-motion preferences and provide a usable reduced-motion experience.
- Never delay a critical action just to finish an animation.
- Test on ordinary Android phones, iPhones, low-end devices and slower networks.
- Keep animation behaviour consistent across public websites and private dashboards.
- Define reusable motion tokens and interaction patterns rather than implementing arbitrary effects on every screen.

### 50.7 Mobile-first and responsive standard

- Design and test phone experiences as a first-class interface, not a compressed desktop layout.
- Ensure parent, student and teacher tasks can be completed on mobile.
- Make navigation, login, forms, tables, uploads, payments, CBT and report downloads usable on small screens.
- Optimise images and media for mobile data and slower connections.
- Provide appropriate touch targets, readable typography and clear focus states.
- Support tablet and desktop layouts without breaking the mobile experience.
- Test key workflows across viewport sizes and supported browsers.

### 50.8 Scalability and reliability standard

ACADIVA must be architected for growth from the beginning. It should not work only for a few schools and require a fundamental rebuild when adoption increases.

<b>Planning targets (not claims of existing capacity):</b>

- Initial concurrency test target: 1,000 simultaneous active users.
- Growth planning target: 10,000+ daily active users, with capacity to increase beyond this.
- Long-term availability objective: 99.9%, subject to infrastructure, operational and budget decisions.

Clarify that concurrent users, daily active users, registered users and request throughput are different measures. Define realistic workload profiles before capacity claims.

Engineering requirements:

- Multi-tenant architecture with enforced tenant isolation on the server and database.
- Efficient indexes, query patterns, pagination and bounded data retrieval.
- Avoid N+1 queries and unbounded list endpoints.
- Caching for suitable read-heavy data, with correct invalidation.
- CDN and image optimisation for public websites and static assets.
- Background jobs/queues for report generation, bulk imports, notifications, media processing and other long-running tasks.
- Idempotent payment/webhook and job processing to prevent duplicate effects.
- Rate limits, concurrency limits, timeouts, retries with backoff and dead-letter/review handling where appropriate.
- Database connection management, monitoring, backups and tested restoration.
- Separate development, staging and production environments.
- Horizontal/vertical scaling options and documented upgrade triggers.
- Observability: structured logs, metrics, traces, error reporting and actionable alerts.
- Graceful degradation so a slow non-critical feature does not take down login or core school operations.
- Capacity and cost testing before expanding infrastructure.

<b>Performance validation</b>

- Load test staged levels such as 100, 250, 500 and 1,000 concurrent users.
- Test realistic mixed workloads: login, dashboard reads, attendance, result viewing, fee ledger, payment callbacks, uploads and CBT.
- Test spikes such as many parents checking results at once.
- Test bulk imports and report-card generation while normal users remain active.
- Stress test beyond the target to understand failure limits.
- Measure p50/p95/p99 latency, error rate, throughput, database saturation, queue delay and resource use.
- Set endpoint-specific service objectives and acceptable error budgets.
- Do not claim a user capacity until repeatable tests demonstrate it.

### 50.9 Security, privacy and data integrity

- Enforce role-based access and school-level data isolation in backend/database policies, not only frontend navigation.
- Test cross-tenant access attempts and privilege escalation.
- Use least privilege for staff and platform operators.
- Keep secrets and service-role credentials server-side.
- Validate and sanitise inputs; protect file uploads and exports.
- Rate-limit authentication, public forms, APIs and sensitive operations.
- Use secure session management, verification and account recovery.
- Maintain audit trails for sensitive financial, academic, identity and administrative changes.
- Use backups and test restoration, not merely assume backups work.
- Define data retention, export, correction and deletion procedures.
- Minimise sensitive student and family information; apply appropriate safeguards to children’s data.
- Review applicable Nigerian privacy and education-related requirements before launch.
- Do not expose private student records through public school websites, search engines, analytics or shareable links.

### 50.10 Quality assurance and release gates

No feature is complete merely because it appears to work once.

- [ ] Unit tests cover business rules and calculations.
- [ ] Integration tests cover database, APIs and external services.
- [ ] Role/permission tests cover every affected user type.
- [ ] Tenant-isolation tests prove one school cannot read or change another school's records.
- [ ] End-to-end tests cover the complete user journey.
- [ ] Regression tests cover existing workflows affected by the change.
- [ ] Mobile and responsive checks are complete.
- [ ] Accessibility and reduced-motion checks are complete.
- [ ] Loading, empty, error, retry and offline/slow-network states are handled.
- [ ] Duplicate submissions and concurrent updates are tested.
- [ ] Security and privacy checks are complete.
- [ ] Performance impact is measured.
- [ ] Database migrations and rollback/recovery steps are verified.
- [ ] Logs, monitoring and alerts are in place for critical paths.
- [ ] Documentation and user-facing help are updated.
- [ ] Staging acceptance is completed before production release.

For high-risk features such as payments, authentication, student records, permissions, results and bulk operations, require stronger review and explicit sign-off.

### 50.11 Organised build workflow

Every task should follow this sequence:

1. <b>Understand:</b> read the relevant product documentation and inspect the current implementation.
2. <b>Define:</b> describe the user problem, expected outcome and acceptance criteria.
3. <b>Map:</b> identify screens, roles, data, APIs, dependencies and affected modules.
4. <b>Risk-review:</b> examine failure modes, security, privacy, scale, performance, cost and reversibility.
5. <b>Plan:</b> choose the smallest safe implementation and define tests/migration/rollback.
6. <b>Design:</b> review the user journey and responsive states before coding.
7. <b>Build:</b> implement in small, reviewable changes.
8. <b>Verify:</b> run automated and manual tests, inspect regressions and measure performance.
9. <b>Release carefully:</b> stage, monitor, and roll back if critical checks fail.
10. <b>Document:</b> record what changed, why, test evidence, known limitations and follow-up work.

For substantial changes, produce a short implementation plan and obtain approval before modifying foundational architecture or data. Do not make speculative changes just because a coding assistant suggests them.

### 50.12 New product capability reference: competitor feature coverage

MySchoolReg is a reference for feature discovery, not an implementation specification. Areas to assess for ACADIVA include:

- Student records and bulk import.
- Score and assessment management.
- Online CBT, question banks and practice mode.
- Admissions, paid/free application forms and applicant tracking.
- Entrance examination grading and admission letters.
- Fee billing, online payments, receipts and bursary reconciliation.
- Report cards, class broadsheets and grading configuration.
- Parent and student portals.
- Timetable creation and conflict checking.
- Student promotion and repeat handling.
- School leadership tools and approval workflows.
- School website, news, announcements, achievements and gallery.

For each, document the user problem, minimum viable workflow, risks, differentiating improvement, dependencies, acceptance criteria and release phase before implementation. AI-generated questions, anti-cheat monitoring and automated timetable generation require careful validation, human oversight and clear limitations before being marketed as reliable.

### 50.13 Open questions to resolve deliberately

- Confirm final domain ownership and the exact central/subdomain routing strategy.
- Decide the authentication and school-context resolution design.
- Finalise which features are core launch scope versus later modules.
- Define realistic load-test workload profiles and response-time objectives.
- Select hosting, database, queue, storage and monitoring architecture based on measured requirements and total cost.
- Define the backup, disaster recovery and recovery-time/recovery-point objectives.
- Determine the first school website template and controlled customisation options.
- Validate feature priorities with real Nigerian schools.
- Establish pricing and infrastructure upgrade triggers from actual usage and cost data.

### 50.14 Permanent build rule

<b>Never build first and think later.</b>

Every decision must be made with the whole system in mind: the user, the school, the data, the architecture, the dependencies, the risks, the future, the cost, the performance and the maintenance burden. When unsure, stop and investigate. A slower, well-considered step is better than a fast change that creates fragile foundations.

## Section 51 — ACADIVA Student Fee Accounts, Payment Visibility, Installments, Receipts and Role-Based Finance Experience

<b>Status:</b> Product requirements captured from the 17 November 2026 discussion. The core requirements below are confirmed direction. Detailed interface design, exact teacher permissions, payment provider configuration and launch phasing remain to be decided. This section extends Sections 47–49; it does not silently replace their earlier decisions.

### 51.1 Product principle: one financial record, role-specific views

ACADIVA must treat school fees as a connected part of each student's school profile, not as a standalone payment page.

A fee obligation and every payment against it must be recorded once in the authoritative financial system. The same verified records should power the appropriate views for parents, students, teachers, principals, bursars and proprietors.

- A parent or guardian is the normal payer and should have a clear view of the amount due, amount paid, outstanding balance, payment history, installment schedule and receipts for each linked child.
- A teacher may need to know whether a student has cleared fees or has an outstanding balance for an operational reason. The default proposal is to expose a restricted status only, not amounts or transaction details. The school must explicitly configure and authorise any broader access.
- A principal should have an authorised overview of students who are unpaid, partially paid, fully paid, pending verification, overdue or paying by instalments, with filters and reports.
- A bursar/finance officer should have the detailed operational finance workspace, including amounts, allocations, payment references, reconciliation, adjustments and receipts.
- A proprietor should have the financial oversight and reports granted by the school's permission policy.
- A student may see an age-appropriate summary of their own fee status only if the school enables it. A student must not become the payer or gain access to a parent's payment method or other children's records.

No role should see financial information merely because it can see the student profile. Finance visibility and finance actions must be separately permissioned.

### 51.2 Student financial profile

Every enrolled student should have a Financial / Fees area connected to their main student record. It should show, according to the viewer's permission:

- Current academic session and term.
- Assigned fee plan and applicable fee items.
- Total amount billed.
- Total verified amount paid.
- Outstanding balance.
- Payment status.
- Installment plan and due dates, where applicable.
- Payment history and references.
- Pending payments awaiting provider confirmation or authorised manual verification.
- Waivers, scholarships, discounts, credits and approved adjustments.
- Refunds or reversals, where applicable.
- Receipts and downloadable/printable payment evidence.

The student record must not store a manually maintained balance that can drift away from the ledger. The displayed balance must be calculated from the authoritative fee charges, verified allocations, credits, waivers and reversals.

### 51.3 Parent / guardian payment workspace

The parent portal is the primary self-service payment experience.

A verified parent/guardian should be able to:

1. Sign in and see only the children linked and verified by the school.
2. Select a child and academic session/term.
3. See the fee summary: total billed, paid to date, outstanding balance and next installment due.
4. Open a breakdown of fee items where the school permits itemised visibility.
5. Pay the full outstanding amount or an allowed partial/installment amount.
6. Choose an available payment method provided by the school's configured payment setup.
7. See a clear payment-pending state while confirmation is outstanding.
8. See the updated balance only after ACADIVA has verified and recorded the payment.
9. Review payment history and retrieve receipts at any time.
10. Pay for more than one linked child without mixing the children's accounts or allocations.

The parent must be able to distinguish clearly between a payment initiated, a payment pending confirmation, a successful verified payment, a failed payment and a reversed/refunded payment. A browser redirect or screenshot is not proof of payment.

### 51.4 Payment summary and visual direction

The payment summary should feel like a modern digital wallet or payment card experience, inspired by the clarity of Apple Wallet without copying its branding or interface.

Potential information hierarchy to explore during design:

- Current fee account / term.
- Total amount billed.
- Amount paid.
- Remaining balance.
- Payment progress.
- Next due date or installment.
- Recent transactions.
- A clear Pay outstanding balance action.
- Receipt access.

The exact card layout, visual treatment, animation and payment flow are intentionally deferred to the design stage. The underlying data model and payment states must be implemented independently of the final visual design so the interface can evolve without rewriting financial logic.

### 51.5 Fee billing and fee structures

The school must be able to configure fee items and assign charges to the appropriate students, classes, levels or groups.

Examples may include tuition, development levy, examination fees, uniforms, books, transport, meals, boarding and other school-approved charges. These are examples, not mandatory universal fee categories.

Requirements:

- Configure fee items, amounts, descriptions, applicable session/term and due dates.
- Support different fee plans by class, level, student or approved category.
- Support optional charges and exemptions where the school requires them.
- Generate a student-specific fee statement/invoice from the configured charges.
- Preserve the original bill and record approved changes as auditable adjustments.
- Prevent duplicate billing for the same student, fee item and billing period unless an authorised correction or additional charge is recorded.
- Define how new admissions, transfers, withdrawals, promotions and mid-term enrolments affect billing.
- Support approved scholarships, discounts, waivers and credits with reasons, approver and timestamps.
- Clearly distinguish a charge from a payment and from an accounting adjustment.

### 51.6 Payment statuses and financial state model

The interface must not collapse all payment states into only Paid / Unpaid.

At minimum, support these distinct states:

- <b>Unpaid:</b> no verified payment has been allocated to the charge.
- <b>Partially paid:</b> some amount has been verified and allocated, but a balance remains.
- <b>Paid:</b> the full amount due has been settled or covered by approved credits/waivers.
- <b>Payment pending:</b> a payment attempt or transfer has been initiated but is not yet confirmed.
- <b>Overdue:</b> an outstanding amount has passed its configured due date.
- <b>Failed:</b> a payment attempt failed; this does not create a successful payment.
- <b>Reversed / refunded:</b> a previously recorded payment has been reversed or refunded, with the ledger and balance updated through a traceable reversal record.
- <b>Waived / credited:</b> an authorised waiver, scholarship or credit has reduced the amount due.

The system should calculate a student's overall term status from the underlying fee items and payment allocations. A student may have some fee items paid and others unpaid. The detailed view must preserve that distinction.

A pending payment must not reduce the official outstanding balance as though it were settled. The UI may show it separately as pending.

### 51.7 Partial payments and installment plans

Installment payments are a first-class requirement, not an exception handled manually.

- Schools can define whether partial payments are allowed.
- Schools can configure an installment schedule, due dates and amounts or percentages.
- The parent can see the full schedule, what has been paid, what remains and what is due next.
- The system must support irregular partial payments if the school allows them.
- Every payment must be allocated to the correct student, school, fee account and billing period.
- The system must define allocation rules when a parent pays less than the full balance or has several outstanding fee items.
- The bursar must be able to review and, where permitted, adjust allocations with a recorded reason and audit trail.
- Late or missed installments should be visible without erasing the student's payment history.
- A payment that exceeds the current balance must follow a defined policy: reject it, hold it for allocation, or record it as an unapplied credit. Never silently allocate it to another child or term.

### 51.8 Role-based payment visibility and permissions

The permission model must be explicit and configurable by the school within platform safety boundaries.

| Role | Default visibility | Restricted actions |
| --- | --- | --- |
| Parent / guardian | Full fee summary, amounts, balance, installment schedule, own linked children's payment history and receipts | Pay; retrieve receipts; view only verified linked children |
| Student | Own status only if enabled by school; no payment method or parent transaction details | No payment, allocation, adjustment or refund actions |
| Teacher | Proposed default: fee status indicator only when authorised (e.g. cleared / outstanding / restricted / not available) | No amount, transaction history, receipt, payment or adjustment access by default |
| Principal | School-level status overview and authorised reports; amounts only if explicitly granted | No payment-provider credentials; no unapproved ledger edits |
| Bursar / finance officer | Detailed billing, payments, allocations, balances, reconciliation and receipts | Adjustments/refunds only with assigned permission and audit trail |
| Proprietor | Financial oversight and reports according to school permissions | Sensitive actions remain separately permissioned |
| ACADIVA platform operations | Technical support access only under controlled, logged and justified procedures | No routine unrestricted browsing of school financial details |

Teacher visibility is an open policy decision. The safe starting point is status-only access, disabled unless the school grants it. Schools may have legitimate reasons to prevent teachers from seeing fee status altogether. ACADIVA must not assume that a teacher needs to know whether a child has paid before teaching or participating in school activities. Any use of payment status to restrict attendance, lessons, exams or access to services requires separate school policy and legal/ethical review; the software should not make that decision automatically.

Permissions must be enforced on the server and in database policies, not merely by hiding fields in the interface. Exports, search, notifications, APIs and reports must obey the same permissions.

### 51.9 Principal and management finance dashboard

The principal's authorised finance view should make school fee collection understandable at a glance.

It should support:

- Total amount billed for the selected period.
- Total verified amount collected.
- Total outstanding balance.
- Number of students fully paid.
- Number of students partially paid.
- Number of students with no payment.
- Number of students with pending payment confirmation.
- Number of overdue accounts.
- Students currently paying by installments.
- Filters by session, term, class, arm, fee item and payment status.
- Search for an individual student and open their permitted financial summary.
- Export of authorised summary/detail reports.
- A clear distinction between verified collections and pending payment attempts.

The dashboard must not count pending or failed transactions as collected revenue. Financial totals should reconcile to the underlying ledger and selected date/term filters.

### 51.10 Bursar and finance operations

The bursar workspace should provide the controls needed to manage the financial records reliably:

- Create and manage fee structures and billing runs.
- Review student invoices and outstanding balances.
- Record approved offline payments where the school accepts cash, bank transfer or other offline methods.
- Verify manual payments using a defined evidence and approval process.
- Reconcile online payment transactions against provider records and bank settlement reports.
- Allocate or reallocate payments with reason and audit history.
- Record discounts, scholarships, waivers, credits and approved adjustments.
- Handle failed, duplicate, disputed, reversed and refunded transactions.
- Generate student statements and receipts.
- Review collection reports and exception queues.
- Export records for accounting and audit purposes.

Manual payment entry must record the payment method, amount, date, reference/evidence where available, staff member who entered it and any required approver. It must never be represented as provider-verified online payment.

### 51.11 Online payment integration and provider boundary

The payment gateway is an external payment processor. ACADIVA remains responsible for fee billing, student mapping, payment allocation, balances, receipts, permissions and financial reporting.

Paystack remains a provider candidate discussed previously, not a final locked-in architecture or commercial agreement. The school/payment-account ownership model and provider eligibility must be confirmed before implementation.

The integration must:

- Create payment requests from an authenticated, server-authorised fee account.
- Use unique payment references and store the provider reference.
- Validate the expected school, student, parent, amount, currency and billing period.
- Verify provider events on the server using the provider's documented signature/authentication method.
- Treat verified server-to-server confirmation as authoritative, not a client-side success redirect.
- Process duplicate webhook deliveries idempotently.
- Handle delayed, out-of-order, failed, abandoned, reversed and refunded events.
- Keep payment attempts separate from confirmed ledger entries.
- Prevent one payment from being applied twice.
- Prevent a parent from changing the amount, student, school or invoice in the browser and having the backend accept it.
- Maintain provider reconciliation and exception handling.
- Keep secret keys and webhook secrets on the server only.
- Record provider outages and provide a safe retry/status-check path.

Dedicated virtual accounts, where supported and approved, are a possible transfer option. They must not be assumed to exist for every student or parent. Account assignment, consent, identity requirements, account limits, matching rules and reconciliation must be researched and explicitly designed before use.

ACADIVA should not hold pooled school funds or operate an ACADIVA wallet as part of this requirement. The preferred starting model remains direct settlement to each school's approved payment account, subject to provider confirmation and legal/compliance review. No teacher payroll or teacher payout feature is included in this school-fee scope.

### 51.12 Receipts, statements and proof of payment

A receipt must be a durable digital record generated from a verified payment, not a manually editable image or an independent document disconnected from the ledger.

Requirements:

- Generate a unique receipt number for each confirmed payment/receipt event.
- Include school identity, student name/ID, payer where appropriate, academic period, amount, date/time, payment method, transaction reference and fee allocation.
- Clearly label partial payments and show the remaining balance where appropriate.
- Allow parents and authorised finance staff to view, download and print the receipt.
- Allow parents to retrieve old receipts from the child's payment history.
- Provide a student fee statement showing charges, payments, credits/waivers and balance over a selected period.
- Support reprinting without creating a second payment or a second financial transaction.
- Define how corrected receipts, reversals and refunds are represented; never silently alter the historical receipt or erase the original payment evidence.
- Use a consistent printable layout that works on mobile and desktop and produces a legible PDF/print output.

A receipt proves that ACADIVA recorded a specific payment; its status must reflect whether that payment remains valid, has been reversed or refunded.

### 51.13 Notifications and communication

Subject to school settings, notification events may include:

- New bill issued.
- Upcoming installment due.
- Installment overdue.
- Payment initiated / awaiting confirmation.
- Payment confirmed.
- Payment failed.
- Receipt available.
- Approved waiver, credit or billing adjustment.
- Refund or reversal recorded.

Notifications must not disclose sensitive financial details to an unverified contact or the wrong guardian. The in-app financial record remains the source of truth; SMS/email/push messages are alerts, not the ledger.

### 51.14 Core data model to plan before coding

The final schema must be reviewed against the existing database before any migration. The following are conceptual entities, not an instruction to create duplicate tables if equivalent structures already exist:

- <b>Fee plans / fee items:</b> school-owned definitions, amounts, applicability and effective periods.
- <b>Student fee accounts:</b> the student's financial account within a school and academic period.
- <b>Invoices / fee charges:</b> the actual obligations issued to a student.
- <b>Installment schedules:</b> due dates and amounts associated with a charge or account.
- <b>Payment attempts:</b> initiated provider or manual payment attempts and their changing statuses.
- <b>Payments / financial ledger entries:</b> confirmed incoming amounts and traceable reversal/refund entries.
- <b>Payment allocations:</b> how a confirmed payment is applied to one or more student charges.
- <b>Credits / waivers / discounts:</b> authorised non-cash reductions, with reason and approval.
- <b>Receipts:</b> durable references to confirmed payment events and printable evidence.
- <b>Reconciliation records:</b> matching ACADIVA transactions to provider and bank settlement information.
- <b>Audit events:</b> who created, changed, approved, allocated, reversed or exported financial information and when.

Every school-owned financial record must be tenant-scoped. Every relevant record must link to the correct school and, where applicable, student, parent/payer, academic period, fee charge and provider reference. Use immutable or append-only financial history where practical: correct mistakes with reversal/adjustment entries rather than deleting or overwriting money movements.

The schema must support a parent paying for multiple children without merging their accounts, and a student having multiple fee items, installments and payments in one term.

### 51.15 Financial integrity, security and failure handling

Before implementation, explicitly design and test:

- Tenant isolation across schools for every financial query and action.
- Parent-to-child relationship verification and revocation.
- Role and field-level access control.
- Server-side amount calculation and invoice validation.
- Duplicate payment and webhook protection.
- Idempotency for payment confirmation, allocation and receipt generation.
- Concurrent payments against the same outstanding balance.
- Overpayment and underpayment handling.
- Payment received but webhook delayed or unavailable.
- Webhook delivered more than once or out of order.
- Provider reports and bank settlement not matching ACADIVA records.
- Manual entry mistakes and approval controls.
- Refunds, reversals, disputes and chargebacks.
- Backups, recovery and audit retention.
- Data minimisation for teacher and student views.
- Safe exports and protection of downloadable receipts/statements.
- Accessibility, mobile usability and slow-network behaviour.

Never delete a confirmed financial event to make a balance look correct. Preserve the audit trail and correct the account with an authorised adjustment or reversal.

### 51.16 Financial module acceptance checklist — coding gate

Do not mark the finance module complete until the relevant end-to-end checks pass.

<b>Billing and student account</b>

- [ ] School can configure fee items and billing periods.
- [ ] Correct fee plan is assigned to the correct student.
- [ ] Student financial profile shows accurate billed, paid and outstanding totals.
- [ ] Different fee items and academic periods remain distinguishable.
- [ ] Approved discounts, waivers and credits are traceable.
- [ ] Duplicate billing is prevented or safely controlled.

<b>Parent experience</b>

- [ ] Parent can only access verified linked children.
- [ ] Parent can view the correct fee summary and payment history for each child.
- [ ] Parent can pay the full balance or an allowed installment/partial amount.
- [ ] Parent can distinguish pending, successful, failed and reversed payments.
- [ ] Parent can retrieve and print historical receipts.
- [ ] A payment for one child cannot be accidentally applied to another child.

<b>Teacher and student permissions</b>

- [ ] Teacher financial status visibility is disabled by default unless explicitly granted.
- [ ] If enabled, teacher sees only the approved status fields.
- [ ] Teacher cannot retrieve amounts, payment history, receipts or make financial changes without separate permission.
- [ ] Student visibility is optional and limited to their own permitted summary.
- [ ] API, database, search, exports and notifications enforce the same access rules.

<b>Principal and bursar</b>

- [ ] Principal dashboard counts paid, partial, unpaid, pending and overdue accounts correctly.
- [ ] Principal reports exclude pending and failed payments from verified collections.
- [ ] Bursar can reconcile payments and identify exceptions.
- [ ] Manual payments are clearly distinguished from provider-confirmed payments.
- [ ] Adjustments and allocations require appropriate permissions and preserve audit history.

<b>Payment integration</b>

- [ ] Server validates school, student, invoice, amount and currency.
- [ ] Provider confirmation is verified server-side.
- [ ] Duplicate/out-of-order webhook events do not duplicate payments.
- [ ] Payment attempts do not become confirmed ledger entries prematurely.
- [ ] Failed, delayed, reversed and refunded transactions are handled.
- [ ] Provider outage and reconciliation exception paths are tested.

<b>Receipts and audit</b>

- [ ] Confirmed payment generates a unique retrievable receipt.
- [ ] Receipt can be downloaded and printed from mobile and desktop.
- [ ] Reprinting does not create a new payment.
- [ ] Refund/reversal status remains visible in the payment history.
- [ ] Audit history identifies the actor, action, time and reason for sensitive changes.

<b>Quality and release</b>

- [ ] Automated tests cover billing calculations, allocation, permissions and payment events.
- [ ] Integration tests cover provider callbacks and reconciliation.
- [ ] End-to-end tests cover parent payment through updated student, teacher (where enabled), principal and bursar views.
- [ ] Concurrency and duplicate-submission tests pass.
- [ ] Mobile, accessibility, slow-network and error-state checks pass.
- [ ] Migration, backup and rollback/recovery plan is reviewed.
- [ ] Financial totals reconcile against source ledger entries in test scenarios.
- [ ] Staged release and monitoring plan is documented.

### 51.17 Decisions still open — do not silently assume

1. <b>Teacher access:</b> Should teachers see no fee information, or a status-only indicator? The recommended safe default is no access until the school explicitly enables status-only visibility. Amounts and transaction details remain restricted by default.
2. <b>Student access:</b> Should students see their own fee status, or should fee information remain parent/guardian-only?
3. <b>Installment policy:</b> Can every school choose its own installment rules, minimum payment, due dates and late-payment policy?
4. <b>Payment account ownership:</b> Confirm the direct-to-school merchant account model and provider onboarding requirements.
5. <b>Payment methods:</b> Confirm which methods are enabled per school and whether dedicated virtual accounts are needed.
6. <b>Manual payments:</b> Define evidence and approval requirements for cash and bank-transfer entries.
7. <b>Overpayment:</b> Decide whether excess payments are rejected, held as unapplied credit or allocated by an authorised finance user.
8. <b>Receipt policy:</b> Confirm receipt numbering, school branding, correction and refund wording.
9. <b>Finance reports:</b> Confirm which management roles can view amounts, collection totals, exports and student-level detail.
10. <b>Release scope:</b> Decide which billing, manual payment, online payment, reconciliation and reporting capabilities are required for the first school pilot.

### 51.18 Build order and dependency gates

1. Map the existing student, parent, school, academic session and role tables; reuse existing authoritative records.
2. Finalise finance permissions and tenant isolation before exposing financial fields.
3. Design and review fee structures, charges, student accounts, ledger entries, allocations and audit history.
4. Implement billing and balance calculations with automated tests before payment gateway integration.
5. Implement manual payment recording and reconciliation controls, if included in the pilot.
6. Build parent fee views, installment handling and receipt generation.
7. Build restricted teacher status view only after a policy decision.
8. Build principal and bursar dashboards from the same authoritative records.
9. Integrate the selected payment provider with server-side verification, idempotency and exception handling.
10. Run end-to-end, security, concurrency, reconciliation and recovery tests before a school pilot.

The design of the payment card and wallet-like interface can proceed alongside product design, but it must not dictate or replace the underlying ledger, permission model or payment verification architecture.

### 51.19 Permanent financial rule

<b>A payment is not complete because a parent clicked Pay, uploaded a screenshot or saw a success message. It is complete only when ACADIVA has securely verified the payment, recorded it once, allocated it correctly and made the resulting balance and receipt available to the right people.</b>

## Section 52 — ACADIVA Pricing Model: \$1 per Active Student per Academic Term

<b>Status:</b> New pricing direction proposed by the founder on 17 November 2026. This section records the new model and its rationale. It supersedes the earlier free-student allowance and fixed student-band pricing proposals as the preferred pricing direction, but the final launch price, local currency collection method and billing rules still require validation.

### 52.1 Proposed pricing principle

The proposed ACADIVA subscription price is:

<quote color="green_bg">
<b>\$1 per active student, per academic term.</b>

The school pays according to the number of active, billable students registered for that term.
</quote>

The intent is to replace arbitrary school-size bands such as 0–50 students free and 51–100 students at a fixed fee. The price should scale proportionately with the school's enrolment and the value ACADIVA provides.

This is a per-student software subscription charged to the school. It is not a payment-processing fee, not a teacher fee and not automatically a separate charge imposed on parents.

### 52.2 Why this model is attractive

- Simple to explain: one student costs \$1 for one term.
- Proportional: a school with 80 students pays for 80; a school with 800 pays for 800.
- Predictable: the school can estimate its subscription from its enrolment.
- Scalable: revenue grows as schools onboard more students, without renegotiating arbitrary tiers.
- No artificial free-tier cliff: a school does not suddenly face a large fixed-price jump after crossing 50 students.
- Easier to compare across schools of different sizes.
- The school can assess the subscription as a small per-student operating cost and decide whether to absorb it or transparently include it in its own fee planning.

The earlier fixed tiers and free allowance remain documented as historical proposals, not the current preferred model.

### 52.3 Illustrative pricing examples

At the CBN NFEM reference rate reported for 16 November 2026 of approximately ₦1,360 per US dollar, the proposed \$1 per student is approximately ₦1,360 per student per term. This is an illustration only, not a fixed exchange-rate promise or a final naira price. [\[1\]](https://lagosxchange.com/)

| Active students | USD per term | Approximate NGN per term |
| --- | --- | --- |
| 25 | \$25 | ₦34,000 |
| 50 | \$50 | ₦68,000 |
| 80 | \$80 | ₦108,800 |
| 100 | \$100 | ₦136,000 |
| 150 | \$150 | ₦204,000 |
| 200 | \$200 | ₦272,000 |
| 300 | \$300 | ₦408,000 |
| 500 | \$500 | ₦680,000 |
| 1,000 | \$1,000 | ₦1,360,000 |

These examples use a rounded ₦1,360/\$ planning rate. Actual naira equivalents will change with the adopted pricing conversion policy.

### 52.4 Annual revenue model

Assuming three academic terms per year and no discounts, credits, unpaid invoices or churn:

- Annual subscription per active student: \$3.
- 100 students: \$300 per school per year.
- 300 students: \$900 per school per year.
- 500 students: \$1,500 per school per year.
- 1,000 students: \$3,000 per school per year.

Revenue is earned per billable student per term, not per login, teacher account or parent account. Staff, parents and student portal access should not each attract a separate user-seat charge under this model unless a later decision explicitly changes the policy.

### 52.5 How schools may account for the cost

The subscription is invoiced to the school. The school may choose to absorb the cost as an operating expense or transparently account for it in its broader fee planning.

ACADIVA should not automatically add a hidden surcharge to a parent's bill. If a school chooses to recover the cost through school fees, that is the school's disclosed fee decision. ACADIVA's own invoice to the school must remain clear and separate from the school's student fee ledger.

The school's decision to recover the subscription from parents does not make the parent an ACADIVA subscriber and does not change the fact that the school is ACADIVA's customer.

### 52.6 Define the billable student count before coding

The term invoice must use a documented, consistent student-count rule. The following is the recommended starting proposal:

- Count students with an active/enrolled status in the school's official student register for the billed academic term.
- Exclude applicants who have not been admitted/enrolled.
- Exclude withdrawn, transferred or graduated students where their status became effective before the agreed census date.
- Do not count parents, guardians, teachers, staff, duplicate student profiles or inactive historical records.
- Count each student once per school per term, even if the student has multiple parent/guardian accounts or changes class during the term.
- Define how mid-term admissions, withdrawals, transfers, refunds and corrections affect the bill.
- Freeze or snapshot the billable count on an agreed census date, and record the student list/count used to generate the invoice.
- Require an auditable adjustment if the count is corrected after invoicing.

The exact census date and mid-term proration/refund rules are open decisions. The system must not silently change a school's invoice whenever a student profile is edited.

### 52.7 Billing frequency and subscription lifecycle

The preferred billing cadence is per academic term, aligned with the school's three-term academic year.

The platform should support:

- A subscription invoice for each school and academic term.
- A recorded billable student count and unit price for that invoice.
- Invoice issue date, due date, billing period and status.
- Payment status and transaction history.
- Renewal into the next term.
- Grace period and overdue handling, defined by policy.
- School subscription status: trial/pilot, active, payment due, grace period, suspended or cancelled, as appropriate.
- Clear communication before any restriction or suspension.
- Continued access to export school records and financial/academic data according to the school's contract and data-retention obligations.

Do not automatically lock a school out or delete data because an invoice is overdue. Suspension rules, grace periods, read-only access, data export and restoration must be explicitly designed and communicated.

### 52.8 Currency and foreign-exchange policy

The dollar amount is the pricing reference proposed by the founder. ACADIVA's initial market is Nigeria, so the school-facing checkout and invoice should ideally be denominated in naira for clarity and local payment convenience.

Before implementation, choose one transparent conversion method:

- Publish a fixed naira price per student for a defined pricing period and review it periodically; or
- Calculate the naira equivalent at invoice creation using a documented reference rate and lock that amount for the invoice's validity.

The recommended launch approach is to publish a clear naira equivalent per student per term for a defined review period, rather than changing an existing school's bill every day with FX movements. The dollar reference can remain the internal pricing benchmark.

The pricing page, contract and invoice must state the applicable currency, unit price, student-count rule, billing period, taxes if applicable, due date and any review policy. Do not charge schools in USD by default without confirming the legal, banking, tax and commercial implications for Nigerian customers.

### 52.9 Pricing and infrastructure economics

The per-student model improves revenue alignment but does not by itself prove profitability. ACADIVA must measure actual cost to serve each school and each active student.

Cost modelling must include:

- Shared database and compute usage.
- Hosting, bandwidth, CDN and public school websites.
- Storage, backups and document/PDF generation.
- Transactional email, SMS and push notifications where used.
- Payment-provider fees, where ACADIVA or the school bears them.
- Monitoring, security and support.
- Onboarding, data import, training and customer success.
- Taxes, payment collection costs and foreign-exchange conversion costs.
- Engineering and maintenance capacity.

The earlier Section 38 operating-cost model and Section 35 tier scenarios were built around different pricing assumptions. They must be recalculated using the new per-student, per-term model before relying on their revenue, margin, school-count or break-even conclusions.

Create scenarios for small, medium and large schools and for 5, 10, 25, 50 and 100 schools. Include low-enrolment schools, inactive terms, late payments, infrastructure upgrades and support workload. Report gross revenue, direct variable costs, fixed operating costs, gross margin and operating surplus separately. Do not label revenue less a partial infrastructure estimate as net profit.

### 52.10 Commercial and product positioning

Suggested plain-language explanation:

“ACADIVA costs \$1 per active student per academic term. Your school's subscription scales with the number of students you manage on ACADIVA.”

For Nigerian school-facing materials, show the actual naira price applicable to the current pricing period rather than requiring proprietors to perform currency conversion.

Do not market the price as guaranteed to be affordable to every school without customer validation. Test it with proprietors across different school sizes and fee levels. Validate willingness to pay, perceived value, procurement approval, competitor alternatives and whether the school prefers to absorb or recover the software cost.

### 52.11 Pricing implementation requirements

The subscription and billing code must be separate from the student fee collection ledger described in Section 51.

Conceptual records to plan and reconcile with the existing schema:

- School subscription and plan reference.
- Pricing version and effective date.
- Academic term / billing period.
- Billable student-count snapshot and auditable student list.
- Unit price and currency.
- Generated subscription invoice and line items.
- Payment attempts and confirmed subscription payments.
- Discounts, credits, adjustments and refunds.
- Subscription status and grace-period dates.
- Audit history of count changes, pricing changes and manual overrides.

The system must preserve the exact price and count used for each issued invoice. A later pricing change must not rewrite historical invoices.

Do not confuse:

- A school's ACADIVA subscription invoice (money the school owes ACADIVA).
- A student's school-fee invoice (money a parent owes the school).
- A payment gateway transaction fee (money charged by the payment provider).

These are three separate financial relationships and must remain separate in the database, dashboards, receipts, reports and accounting exports.

### 52.12 Pricing acceptance checklist

- [ ] One unit price per active billable student per academic term is configurable.
- [ ] Pricing versions have effective dates and historical invoices remain unchanged.
- [ ] Billable student count follows a documented census rule.
- [ ] Applicants, staff, parents, duplicate profiles and inactive records are excluded.
- [ ] Mid-term admission/withdrawal and count corrections follow explicit rules.
- [ ] School subscription billing is separate from student school-fee billing.
- [ ] The school can see its student count, unit price, invoice total and billing period.
- [ ] Naira currency and FX conversion policy are explicit and stable for each invoice.
- [ ] Payment, overdue, grace, suspension, cancellation and restoration states are tested.
- [ ] Schools retain appropriate access to their data and exports under the agreed contract.
- [ ] Revenue and cost scenarios are recalculated against measured infrastructure and support costs.
- [ ] Pricing is validated with real schools before being presented as final.

### 52.13 Open decisions before final launch pricing

1. Confirm whether \$1 is the intended final list price or an initial pricing hypothesis to test.
2. Choose the naira price and FX review policy for Nigerian schools.
3. Define the student-count census date for each term.
4. Decide whether mid-term admissions are charged fully or prorated.
5. Decide whether withdrawals before/after the census date generate adjustments.
6. Define pilot/trial terms without creating a permanent free student band.
7. Set invoice due dates, grace period and non-destructive suspension rules.
8. Recalculate infrastructure economics and support costs using the new model.
9. Validate the price with proprietors across different school sizes.
10. Confirm applicable tax, invoicing and contract treatment with a qualified Nigerian adviser.

### 52.14 Decision summary

The founder's preferred pricing direction is now \$1 per active student per academic term, replacing the previous 0–50 free and fixed school-size bands as the preferred model for further validation. The principle is confirmed as the current direction; the final naira price, billing rules, FX policy, tax treatment and launch approval remain open.

[\[1\]](https://lagosxchange.com/)

## Section 53 — ACADIVA Parent Identity, Multi-Child Access, Guardian Relationships and Student Login Policy

<b>Date:</b> 17 November 2026<br /><b>Status:</b> Agreed product direction; detailed authentication, verification and implementation choices remain subject to technical design and testing.

### 53.1 Decision summary

ACADIVA will use a <b>single parent/guardian account that can securely access multiple linked children</b>, including children in different classes, education levels and different ACADIVA schools.

A parent should not need a separate username or login for every child. For example, one guardian may have one child in Primary 4 and another in KG 1. Both student records appear under the same verified parent account, while remaining separate records with separate academic, attendance, finance and communication data.

The same account model should support a guardian whose children attend different schools using ACADIVA. Each school's information remains isolated and is only shown when that guardian has been verified and authorised for the relevant child.

### 53.2 Parent login identifier and authentication

Preferred direction:

- Use the guardian's registered phone number as the primary login identifier.
- Verify access using a one-time passcode (OTP) sent to that registered number.
- After successful verification, open the guardian's parent workspace and show the children linked to that account.
- Design account recovery and phone-number-change processes before launch; a lost or changed phone number must not permanently strand a legitimate guardian or allow an unauthorised person to take over an account.
- Consider passkeys or other secure, convenient authentication methods later. Do not treat an SMS OTP alone as a complete security strategy for every sensitive action.
- Apply rate limits, abuse detection, session controls, secure recovery, and step-up verification for sensitive changes where appropriate.
- Do not use a phone number as the student's identity or as the only proof that a person is entitled to access a child.

The exact OTP provider, delivery channel fallback, session duration, and account recovery policy remain technical/product decisions.

### 53.3 One guardian account, multiple student records

The parent workspace should show a clear child switcher or child list. Each child must have an independent student record and school context.

Example:

- Child A — Primary 4 — School A.
- Child B — KG 1 — School A.
- Child C — Primary 1 — School B.

The guardian signs in once and selects a child to view the information available for that child at that school.

Each child's information remains independent, including:

- Student identity, admission number and class history.
- Attendance and timetable.
- Assessments, examination results and report cards.
- School-fee account, invoices, payments, balances and receipts.
- Announcements and school-specific communication.
- Documents and other information permitted to the guardian.

The interface must make the currently selected child and school unmistakable. Avoid combining different children's fee balances, results, attendance or messages into ambiguous totals. Any cross-child summary must clearly identify the child and school to which each item belongs.

### 53.4 Cross-school access

A guardian may use one ACADIVA account for children attending more than one ACADIVA school.

Requirements:

- The account can have authorised guardian relationships in multiple school tenants.
- The guardian must be verified separately for each child/school relationship.
- The user must be able to identify which school they are viewing.
- A school must not gain access to another school's records merely because the same guardian account is linked to both.
- Switching schools or children must change the active tenant and permissions on the server, not merely change the displayed interface.
- All queries, APIs, files, exports, notifications and financial records must enforce the relevant school and child permissions.
- If a child transfers schools, preserve the appropriate historical record and revoke or change access according to the school's authorised student lifecycle process and applicable retention rules.

This is a shared identity model, not shared school data. Cross-school convenience must never weaken tenant isolation.

### 53.5 Multiple guardians for one child

ACADIVA should support more than one authorised guardian for a student.

For example, a mother and father may each have their own ACADIVA account and both may be authorised to access the same child.

Requirements:

- Each adult has an individual account and their own authentication credentials.
- Each guardian-child relationship is separately recorded and verified.
- The school can manage and review guardian access under its policies and applicable legal requirements.
- A guardian must not be able to add themselves to a child simply by entering the child's name, admission number or other guessable detail.
- Revoking one guardian's access must not automatically revoke another authorised guardian's access.
- Any restrictions, custody-related instructions or sensitive access decisions must be handled through a controlled school process, with appropriate records and escalation; the platform must not assume that every listed parent has identical rights.

### 53.6 Guardian relationship and authorisation model

Keep three concepts separate:

1. <b>User account:</b> the person who authenticates to ACADIVA.
2. <b>Student record:</b> the authoritative school record for an individual child.
3. <b>Guardian relationship:</b> the verified, permission-bearing link between a user account and a student record.

The guardian relationship should record, as appropriate:

- School/tenant and student identifiers.
- Guardian user identifier.
- Relationship type (for example parent, legal guardian or other approved caregiver).
- Verification status, method, verifier and timestamps.
- Access status and any approved restrictions.
- Who created, approved, changed or revoked the relationship.
- Audit history for sensitive changes.

The exact data fields and verification workflow must be designed against the existing schema before implementation. Do not create duplicate student records merely because a child has two guardians or because a guardian has children in multiple schools.

### 53.7 Child and student login policy

A separate login for every child is <b>not</b> the default.

- Nursery, KG and younger primary pupils do not need individual accounts by default.
- Primary 4 pupils do not need a mandatory login simply because they have a student profile. An individual account may be considered for a clear educational use case, with age-appropriate safeguards and school approval.
- Older students, especially secondary-school students, may receive individual accounts for permitted learning resources, CBT, assignments, timetable or academic information.
- Student accounts must have their own restricted role and permissions.
- Student accounts must not expose parent-only financial information, guardian account settings, another student's information or other restricted records.
- A student's access should be configurable by school, age/level and enabled modules, and should be suspended or changed through the student lifecycle process.

The age/level threshold and exact student features are open decisions; do not hard-code an arbitrary universal age rule without product, safeguarding and legal review.

### 53.8 Parent experience and interface requirements

The parent workspace should provide:

- A clear list or switcher for all linked children.
- Child name, school, class and a suitable profile image or initials.
- A visible indication of the currently selected child and school.
- Separate navigation or clearly labelled sections for attendance, academics, fees, receipts and communication.
- A clear way to switch between children without signing out.
- A school switcher or equivalent context when a guardian has children at different schools.
- Useful empty states where a school has not enabled a module or has not yet published information.
- Mobile-first layouts that work well on ordinary phones.
- Accessible controls, readable text and clear loading, success, error and offline states.

Do not expose information just because it is visible in a parent interface. Every displayed item and every action must be authorised by the backend.

### 53.9 Security, privacy and data integrity requirements

- Enforce guardian-child permissions on the server and database, not only in frontend navigation.
- Enforce school/tenant isolation for every record and request.
- Test direct URL, API, export, file and notification access attempts across children and schools.
- Prevent account enumeration and unauthorised child linking.
- Verify guardian relationships through a school-controlled process before releasing private student information.
- Log relationship creation, approval, access changes and revocation.
- Use secure session handling, rate limits, recovery controls and appropriate verification for sensitive actions.
- Ensure notifications do not reveal sensitive information to an unverified or revoked recipient.
- When access is revoked, invalidate or re-check relevant sessions and permissions promptly.
- Avoid duplicate user or student records when a guardian is already known to ACADIVA or a child is already enrolled.
- Define privacy, retention, consent and safeguarding requirements with appropriate Nigerian legal advice before launch.

### 53.10 Required end-to-end and regression tests

- One guardian account can access two or more verified children in different classes, such as Primary 4 and KG 1.
- One guardian account can access verified children in different ACADIVA schools.
- A guardian cannot access an unlinked child by guessing a name, admission number, URL or identifier.
- Two independently authenticated guardians can access the same child when each relationship is authorised.
- Revoking one guardian does not remove another guardian's valid access.
- A guardian cannot see another child's results, fees, receipts, attendance or documents after switching children.
- A guardian cannot cross into another school tenant through a modified request, API call, file URL or export.
- Changing a phone number follows a secure verification and recovery process.
- OTP retries, expiry, abuse limits, delivery failure and account recovery behave safely.
- A child transfer, withdrawal or school change updates access without corrupting historical records.
- Student accounts cannot access parent-only information or another student's records.
- The full experience works on mobile and under slow or interrupted network conditions.

### 53.11 Open decisions before implementation

1. Select the OTP delivery provider and define fallback when SMS delivery fails.
2. Define secure account recovery and phone-number-change procedures.
3. Define the school's guardian verification workflow and acceptable evidence.
4. Define how schools handle disputed or restricted guardian access.
5. Decide which parent actions require step-up verification.
6. Define student-account eligibility and permitted features by school level.
7. Confirm notification privacy rules and consent/communication preferences.
8. Map this model to the existing authentication, student, school and role schema before any migration or code change.

### 53.12 Final product principle

<b>One guardian account. Multiple verified children. Multiple schools where authorised. One separate, protected student record per child.</b>

The login should be simple for families, while the underlying identity, relationship, permission and tenant architecture remains strict. Convenience must never come at the expense of student privacy or school data isolation.

## Section 54 — ACADIVA School-Led Student Onboarding, Guardian Account Preparation, Bulk Import and Parent Activation

<b>Date:</b> 17 November 2026<br /><b>Status:</b> Agreed product direction; exact import format, messaging provider, verification workflow and implementation details remain subject to technical design and testing.

### 54.1 Core decision

Student onboarding must be school-led, not dependent on every parent creating an account before the school can use ACADIVA.

The school should be able to register an entire student population in one organised onboarding exercise. ACADIVA creates the authoritative student records and records the supplied parent/guardian contact details. It prepares the appropriate guardian-account and relationship workflow. The parent activates access when ready by verifying control of their registered phone number.

<b>Principle:</b> The school creates student records and initiates guardian relationships; the guardian verifies their identity and the school-authorised relationship before private student information is released.

A student record must remain valid and usable by the school even when no guardian phone number is available or the guardian has not yet activated an account.

### 54.2 School onboarding workflow

1. The school administrator or authorised registrar opens student onboarding.
2. The school enters students individually or uploads a completed ACADIVA import template.
3. Each student record includes the required identity, admission, class and school information, plus available guardian contact details.
4. ACADIVA validates the data and presents an import preview before committing records.
5. ACADIVA creates or updates the student records without creating duplicate students.
6. Guardian contact details are stored separately from authenticated user accounts.
7. ACADIVA detects matching guardian phone numbers and identifies possible existing accounts or relationships. A matching number is a matching signal, not conclusive proof that all listed children belong to the same legal guardian.
8. The school reviews and confirms the guardian-child relationships according to its verification process.
9. Where no guardian account exists, ACADIVA prepares a pending activation/invitation record. Where an account already exists, ACADIVA can attach the newly approved relationship to that account.
10. ACADIVA sends an invitation when the required contact and delivery channel are available.
11. The guardian verifies the registered phone number and activates access. Only approved relationships become visible in the guardian workspace.

### 54.3 Student records, guardian contacts and user accounts must remain separate

ACADIVA must distinguish these records:

1. <b>Student record:</b> the school's authoritative record for an individual student, including admission number, class, school and academic history.
2. <b>Guardian contact:</b> contact information supplied to the school for a parent, legal guardian or approved caregiver. It can exist before the person has an ACADIVA login.
3. <b>User account:</b> the authenticated person who can sign in to ACADIVA.
4. <b>Guardian-child relationship:</b> the school-authorised, permission-bearing relationship connecting a user account to a student record.

Do not create an active login merely because a phone number appears in an import file. Do not treat an unverified contact as an authenticated user. Do not use a phone number as the student's identity or as sole proof of guardianship.

The implementation should avoid duplicate user accounts when a guardian already uses ACADIVA for another child or another school. Account matching, phone-number normalisation and relationship approval must be designed against the existing identity schema before implementation.

### 54.4 Phone-number matching and multiple children

When the same guardian phone number is entered for multiple students, ACADIVA should group those entries as a possible shared guardian contact and show the school the affected students.

Example:

| Student | Class | Guardian phone |
| --- | --- | --- |
| David | Primary 4 | Same registered number |
| Esther | KG 1 | Same registered number |
| Daniel | Primary 1 | Same registered number |

After the school has confirmed the relationships and the guardian has verified control of the number, the guardian can use one account to access all three children.

Important safeguards:

- Matching phone numbers must not automatically prove legal guardianship.
- Shared family phones, school-entered errors and numbers reused for unrelated contacts must be handled.
- Where the same number appears against unrelated or conflicting guardian details, flag the records for review rather than silently merging them.
- A guardian may have more than one phone number or contact method; the data model should allow this without creating duplicate student records.
- A child may have multiple separately authorised guardians, each with their own user account.
- A guardian may have children in different ACADIVA schools, with each school-child relationship authorised independently.

### 54.5 Parent account preparation and activation

The preferred direction is to prepare a pending activation for a guardian whose contact details have been supplied, rather than issuing a default password or pretending that the person has already activated an account.

Recommended flow:

1. The school records the guardian's phone number and name.
2. ACADIVA checks for an existing account using a safely normalised phone number.
3. If an existing account is found, ACADIVA prepares the new relationship for approval; it does not create another account.
4. If no account is found, ACADIVA creates a pending invitation/activation record associated with the guardian contact. It does not create a usable authenticated session.
5. The guardian receives an invitation explaining that the school has added or registered their child on ACADIVA.
6. The guardian enters or confirms the registered phone number and verifies it with a one-time passcode (OTP).
7. ACADIVA activates the user account or confirms access to the existing account, then grants access only to the approved child relationships.

Do not generate a shared/default password for parents. Do not use a child's date of birth, admission number or parent's phone number as a password. OTP delivery, expiry, resend limits, rate limits, account recovery and phone-number changes require explicit security design. Passkeys or an optional secure PIN may be considered later for convenience; neither should bypass guardian authorisation.

### 54.6 Parent invitation and communication

The invitation should be simple and understandable to parents who have never used ACADIVA.

It should explain:

- The name of the school.
- That the school has registered the child or children.
- That ACADIVA is the school's portal for authorised school information.
- The phone number to use for activation, with sensitive details masked where appropriate.
- How to verify the number and access the parent workspace.
- Where to get help if the number is wrong, shared, unavailable or not controlled by the intended guardian.

SMS is a proposed practical invitation channel for the initial Nigerian market, but the final provider, per-message cost, delivery reporting and fallback channel remain open decisions. Do not expose results, fee balances, receipts or other sensitive student information in an unverified invitation message.

Invitation states should be traceable, for example: not ready, pending, queued, sent, delivered where supported, activation pending, activated, failed or expired. The exact state model should reflect what the messaging provider can actually confirm; do not label a message delivered when only submission was confirmed.

### 54.7 Missing, incorrect or shared phone numbers

A missing guardian phone number must not block student onboarding.

- Create the student record and mark guardian contact details as incomplete.
- Allow an authorised school administrator to add or correct the contact later.
- Require the correction to be audited.
- Re-run account matching and relationship approval after the corrected contact is saved.
- Do not grant parent access until the intended guardian has verified the number and the school-authorised relationship is approved.

Where a phone is shared by several adults or used by unrelated families, the school must identify the intended guardian and approve the correct relationship. Phone verification proves control of the number at that time; it does not independently establish legal guardianship.

### 54.8 Bulk import requirements

Bulk import is the preferred route for onboarding large schools. Individual entry remains available for new admissions, corrections and missed records.

The import tool should provide:

- A downloadable ACADIVA spreadsheet template with clear field definitions and examples.
- Required and optional field indicators.
- Phone-number normalisation and validation without silently changing the underlying contact incorrectly.
- Duplicate student detection using school-scoped identifiers and carefully designed matching rules.
- Duplicate admission-number detection.
- Missing or invalid guardian contact warnings.
- Conflicting guardian details and shared-number warnings.
- Class, arm, academic session and term validation.
- A preview showing records to create, records to update and records needing correction.
- Row-level error messages that identify the problem and how to fix it.
- A confirmation step before records are committed.
- An import summary with successful, skipped, updated and failed rows.
- An import history showing who uploaded the file, when, the source file or batch reference, and the outcome.
- A safe correction/retry path that does not duplicate students or guardian relationships.

The system must not partially import a file in a way that leaves ambiguous or inconsistent relationships. Define whether imports are atomic or use staged batches with explicit per-row outcomes; whichever approach is chosen must be recoverable, auditable and clearly reported. Large imports should run through a background job where appropriate, with visible progress and safe retry behaviour.

### 54.9 Existing students, new admissions and ongoing changes

The same identity and relationship rules apply after the initial onboarding day.

For a new admission:

1. The school creates the student record from the accepted admission/application workflow.
2. The school records guardian details.
3. ACADIVA checks for existing guardian accounts.
4. The school authorises the guardian-child relationship.
5. ACADIVA prepares an invitation or adds the relationship to an existing account.
6. The guardian verifies and sees the new child without creating another login.

For corrections and lifecycle changes:

- Correcting a guardian phone number must not silently transfer account ownership.
- Changing a guardian requires an auditable relationship update and verification.
- Revoking one guardian must not revoke another guardian's independent access.
- Transferring or withdrawing a student must update current access while preserving records according to the student lifecycle and retention rules.
- Re-enrolling a student must not create a duplicate identity or erase historical academic records.
- Re-importing the same file must not create duplicate students, accounts, invitations or guardian relationships.

### 54.10 School administrator controls

Authorised school staff should be able to:

- View student records with missing guardian contacts.
- See which guardian relationships are awaiting school review.
- See whether a parent invitation is pending, sent, failed or activated, to the extent supported by delivery evidence.
- Correct contact information with an audit trail.
- Approve, reject, suspend or revoke guardian relationships according to school policy and permissions.
- Resend or reissue an invitation with abuse and rate controls.
- See which student records are linked to a guardian account, without exposing the guardian's private authentication credentials.
- Resolve duplicate student and guardian-contact warnings through a controlled process.

Teachers should not receive access to guardian account administration merely because they teach the student. Access must follow explicit role permissions.

### 54.11 Security, privacy and operational requirements

- Enforce all student and guardian permissions on the server and database, not only in the user interface.
- Enforce school/tenant isolation for every student, guardian relationship, request, file, export and notification.
- Prevent account enumeration through login, activation and recovery responses.
- Prevent unauthorised linking by guessing a child's name, admission number, date of birth or other student details.
- Do not treat phone-number equality as sufficient authorisation.
- Log import, account matching, relationship approval, invitation, activation, correction, suspension and revocation events.
- Protect import files and temporary copies; restrict access and define retention/deletion.
- Validate file type, size, row count and content; protect against malformed or malicious uploads and spreadsheet formula injection in exported files.
- Apply rate limits and abuse protection to OTP and invitation flows.
- Make imports, invitation jobs and relationship creation idempotent so retries do not duplicate records or actions.
- Handle SMS provider outages and network interruption without losing student data or misreporting activation.
- Define privacy, parental consent, safeguarding, retention and data-subject processes with appropriate Nigerian legal advice before launch.

### 54.12 Required end-to-end and regression tests

- A school can onboard a large student list without parents being present.
- A student can be created when guardian phone details are missing.
- Multiple children with one confirmed guardian can be accessed from one account.
- A Primary 4 child and a KG 1 child remain separate student records under the same guardian account.
- A guardian with an existing account is linked to a new child without creating a duplicate login.
- A guardian with children in two ACADIVA schools can access each only after the relevant school-child relationships are authorised.
- Two independently authenticated guardians can access the same child when each relationship is approved.
- A shared phone number or conflicting guardian details are flagged for review rather than automatically granting access.
- An unverified contact cannot access student records.
- A parent cannot link a child by guessing a name, admission number, URL or identifier.
- Invalid rows are clearly reported and do not corrupt valid student records.
- Re-uploading the same import does not create duplicates.
- Retrying a failed invitation or import does not create duplicate relationships or messages beyond the defined retry policy.
- Phone-number correction, recovery and guardian revocation follow controlled, audited workflows.
- Notifications do not disclose sensitive student information to an unverified or revoked contact.
- Imports and activation work safely on mobile and under slow or interrupted network conditions.

### 54.13 Open decisions before implementation

1. Final student-import template fields and required/optional rules.
2. Exact duplicate-student matching and conflict-resolution policy.
3. Guardian verification evidence and who at the school may approve it.
4. OTP/SMS provider, delivery cost, fallback channel and delivery-state support.
5. Account recovery and phone-number-change process.
6. Whether parents can optionally set a PIN or passkey after activation.
7. Invitation timing, expiry, resend rules and parent support process.
8. Import size limits, atomic versus staged processing and background-job design.
9. Data retention for import files, invitations and inactive guardian contacts.
10. Mapping the workflow to the existing authentication, student, school and guardian schema before any migration or code change.

### 54.14 Final operating principle

<b>School-led student onboarding. Parent-verified access. One guardian account for multiple authorised children. No default passwords. No child record blocked because a parent has not activated. No access granted solely because two records contain the same phone number.</b>

The school must be able to organise its student records first and invite families into ACADIVA gradually, without compromising student privacy, guardian authorisation or school data isolation.

## 55. ACADIVA Governance, Operations Workspace, School Administrator/CTO, Master Checklist and Mandatory Build Gate

<b>Decision record date:</b> 17 November 2026<br /><b>Status:</b> Consolidated planning update. Confirmed decisions are separated from recommendations and open implementation details. This section supplements Sections 36–54; it does not delete earlier history. Where older wording conflicts, this dated section is the latest decision record, while the specialised sections remain useful background.

### 55.1 Non-negotiable operating principle: re-read before every action

The user's final instruction is a mandatory project rule:

<b>Before every tool call, implementation step, code change, migration, deployment, integration, configuration change or build action, re-read the ACADIVA master plan and the relevant checklist.</b>

Do not rely on memory, a previous chat answer, a stale summary or only the most recent feature request.

For every action:

1. Re-open the current master blueprint and identify the latest applicable decisions.
2. Read the relevant module specification, role/permission rules, architecture constraints and checklist.
3. Identify dependencies and affected modules before acting.
4. Check whether the proposed action conflicts with a confirmed decision or creates a regression elsewhere.
5. State the intended change, expected result, risks and rollback/recovery approach where applicable.
6. Implement the smallest safe change.
7. Run relevant tests, including cross-role, cross-school, mobile, slow-network and failure-path tests as appropriate.
8. Update the checklist and documentation with what changed, what was tested, what remains open and any decision superseded.
9. Do not mark a task complete merely because code was written; completion requires evidence from tests or a verified operational outcome.

If the relevant plan/checklist cannot be accessed, stop and resolve that before making a consequential change. Never improvise around missing requirements.

### 55.2 ACADIVA central Operations workspace and URL

The central operations workspace is to be planned at:

[<b>operations.acadiva.ng</b>](http://operations.acadiva.ng)

This is the intended address for ACADIVA's internal operations workspace, subject to DNS, routing, security and domain configuration checks. It is not a school tenant subdomain and must not be exposed as a public school login destination.

The public ACADIVA platform remains the central entry point for school discovery, school registration and general sign-in. Individual schools receive their own tenant subdomains, for example [schoolname.acadiva.ng](http://schoolname.acadiva.ng). The exact public-domain routing and login experience must be designed consistently.

The Operations workspace is for authorised ACADIVA central personnel. It must have:

- Separate protected access and strong authentication.
- Explicit central staff roles and least-privilege permissions.
- MFA for privileged accounts where supported.
- Tenant-aware school search and support context.
- School verification and activation workflow.
- Subscription and payment confirmation records.
- School onboarding oversight and progress.
- Platform health, incident and support dashboards.
- Audit logs for every privileged action.
- Controlled delegated access to a school's environment.
- No unrestricted default access to children's private records.
- Emergency access that is time-limited, justified, logged and reviewed.
- Clear separation between central platform administration and school-level administration.

The Operations workspace must never be implemented as a hidden frontend route protected only by obscurity. Authorisation must be enforced server-side and at the database/service layer.

### 55.3 Central ACADIVA Platform Administrator / Operations team

This is the central platform role, not the school's local administrator.

Responsibilities:

- Review and verify school registration and representative authority.
- Approve, create and activate school tenants.
- Assign or approve school subdomains.
- Monitor school onboarding completion.
- Manage platform subscription status and record payment confirmation.
- Manage central platform configuration and integrations.
- Monitor application, database, storage, notification and payment-provider health.
- Investigate incidents and support requests.
- Manage platform-wide release controls and maintenance notices.
- Review audit trails and suspicious activity.
- Coordinate data export and school exit requests.
- Manage central support access under documented controls.

Central operations must not casually edit school academic records, student biodata, results, attendance or financial ledgers. Where support requires temporary access, record the purpose, authoriser, scope, start/end time and actions taken.

### 55.4 School Administrator (school-level CTO/setup operator)

The school-level role previously referred to as the school's CTO should be implemented as <b>School Administrator</b> in product terminology. “School CTO” may remain an informal working label during planning, but it must not be confused with ACADIVA's central technology leadership.

This role is a core member of the school operating model. The School Administrator is responsible for configuring and maintaining the school's ACADIVA environment, subject to the school's governance and delegated authority.

School Administrator responsibilities:

- Confirm school identity, address, contact details and branch information.
- Upload and maintain the official school logo.
- Configure school name, address, phone, email and approved brand colours.
- Preview and approve school branding across the website, portal and generated documents.
- Configure the school letterhead and document identity.
- Upload multiple school achievement photographs and gallery media.
- Configure school website template, pages, public information and announcements where authorised.
- Select the education levels the school actually operates.
- Load the relevant Nigerian school structure template, then remove unavailable levels/classes and add any required custom classes.
- Create class arms (for example Primary 4A and Primary 4B).
- Configure academic sessions, terms, dates and school calendar.
- Configure subjects and subject-to-class mappings.
- Configure the school's assessment structure and grading policy, including CA/exam weightings such as 30/70 or an approved alternative.
- Configure pass marks, grade bands and report-card rules in accordance with school policy.
- Import students and staff using validated bulk templates.
- Review import errors and duplicates before finalising.
- Invite staff and assign their initial roles.
- Assign or coordinate teacher class/subject allocations where this responsibility is delegated.
- Configure attendance, timetable and notification settings.
- Verify that key documents and school pages correctly reflect the school's identity.
- Complete the School Setup Checklist and record outstanding items.

The School Administrator should not be the only person who can perform every school operation. The proprietor and principal may be authorised to perform relevant configuration tasks. The system must support delegation without requiring the School Administrator to become a bottleneck.

### 55.5 Principal and school leadership

The Principal/Head Teacher is responsible for academic and day-to-day school leadership. The proprietor/owner retains ownership-level oversight. Their permissions may overlap where the school chooses, but the roles must remain distinguishable.

Principal capabilities should include:

- Review school setup and approve operational readiness.
- Create or manage classes and class arms where authorised.
- Configure or approve academic sessions and terms.
- Configure or approve subjects and teacher assignments.
- Set or approve grading benchmarks and assessment weights.
- Assign class teachers and subject teachers.
- Appoint the timetable coordinator/head of department or other responsible staff.
- Review attendance and academic completion dashboards.
- Publish school-level announcements.
- Manage admissions decisions and student placement.
- Approve sensitive student biodata corrections.
- Assign finance permissions to bursar/accounting staff.
- Review financial summaries without necessarily editing transactions.
- Review and resolve exceptions such as result amendments and attendance corrections.

Routine teacher work must not require principal approval each time. Sensitive configuration and corrections must be controlled and audited.

### 55.6 School Setup Checklist — mandatory for each new school

The checklist must be visible to the School Administrator and central Operations team, with progress and evidence/status. It should support save-and-resume and must not require completing every optional item before a school can continue.

<b>A. School identity and verification</b>

- [ ] Official school name confirmed and spelling checked.
- [ ] School representative and authority verified.
- [ ] School type and education levels selected.
- [ ] Physical address, state, LGA and contact details confirmed.
- [ ] School subdomain checked for uniqueness and assigned.
- [ ] School owner account established securely.
- [ ] Principal and initial administrator roles assigned.

<b>B. Brand and public website</b>

- [ ] Official logo uploaded in supported formats.
- [ ] Logo clarity, aspect ratio and transparent background checked.
- [ ] Favicon/app icon generated or uploaded.
- [ ] Brand colours selected with accessible contrast.
- [ ] School name and contact details confirmed.
- [ ] Letterhead configured and previewed.
- [ ] Report-card, receipt, admission-letter and official-document previews checked.
- [ ] Website template selected.
- [ ] Home, About, Academics, Admissions, Gallery, Achievements and Contact sections configured as applicable.
- [ ] Multiple achievement/gallery images uploaded and captions/alt text added.
- [ ] Image crop, mobile display, loading and animation checked.
- [ ] Public pages reviewed for accidental exposure of private information.
- [ ] School login entry is visible and routes to the correct tenant.

<b>C. Academic configuration</b>

- [ ] Academic session created using the school's year-to-year naming convention (for example 2025/2026).
- [ ] First, Second and Third terms configured, including dates.
- [ ] Relevant school-level template selected.
- [ ] Unavailable classes/levels removed or disabled without deleting historical records.
- [ ] Required custom levels/classes added.
- [ ] Class arms created.
- [ ] Subjects configured for each relevant class.
- [ ] CA/examination weighting confirmed (default proposal 30/70; school may configure another total of 100).
- [ ] Grade bands and pass benchmarks configured.
- [ ] Report-card fields and skills/behaviour assessment configured.
- [ ] Promotion and repetition rules reviewed.
- [ ] School calendar and examination dates configured.

<b>D. Staff and permissions</b>

- [ ] Proprietor/owner account verified.
- [ ] Principal/head teacher account invited and activated.
- [ ] School Administrator account invited and activated.
- [ ] Bursar/finance role assigned where applicable.
- [ ] Teachers imported or invited.
- [ ] Class teachers assigned.
- [ ] Subject teachers assigned.
- [ ] Staff permissions reviewed using the role matrix.
- [ ] No shared default passwords or unverified account access.
- [ ] Staff exit and access-revocation process understood.

<b>E. Student and guardian onboarding</b>

- [ ] Student import template downloaded.
- [ ] Required fields and validation explained.
- [ ] Student names separated into first name, middle name (optional) and surname/last name.
- [ ] Date of birth validated and age calculated automatically for display.
- [ ] At least one parent/guardian phone number captured where available; second contact optional.
- [ ] Student internal ID/admission number generated or validated.
- [ ] Class and arm placement confirmed.
- [ ] Duplicate/conflicting records reviewed.
- [ ] Guardian relationships handled using the approved verification workflow.
- [ ] Parent activation/invitation status checked.
- [ ] Unactivated parent accounts do not block school student records.
- [ ] Import summary and rejected-row report reviewed.

<b>F. Operational readiness</b>

- [ ] Attendance workflow tested with a sample class.
- [ ] Timetable constraints and assigned coordinator confirmed.
- [ ] Result entry and completeness rules tested.
- [ ] Report-card preview generated.
- [ ] Fee structure and student billing configuration checked.
- [ ] Payment and manual reconciliation workflow explained.
- [ ] Notification audiences and channels configured.
- [ ] SMS/email/push/WhatsApp provider status and costs reviewed where enabled.
- [ ] School administrator and principal complete a guided walkthrough.
- [ ] Mobile and low-bandwidth experience tested.
- [ ] Central Operations reviews mandatory setup evidence.
- [ ] School marked ready only after critical checks pass.

### 55.7 School configuration boundaries and non-destructive rules

- A school may disable classes or levels it does not offer. Do not physically delete historical classes that already have students, attendance, results or financial records.
- A school may add custom classes and class arms without breaking the standard template.
- Assessment weights must total 100 or follow an explicitly supported assessment model. A 30/70 split is a default, not a hard-coded universal rule.
- School grading benchmarks are centrally configured at school level and may be delegated to the Principal or authorised academic administrator. Individual teachers must not silently change the school's grading rules while entering scores.
- The School Administrator configures the environment; the Principal leads academic operations. Their capabilities can overlap through explicit delegation.
- Changes to school identity/branding must update reusable templates and future documents consistently. Previously issued documents must remain historically reproducible; changing a logo must not silently rewrite already-issued records.
- Changes to student names, date of birth and identity details must be restricted and audited. Teachers cannot directly edit core biodata. Corrections follow an authorised process.
- All setup steps must be resumable. A partially configured school must not be left in an unusable state.

### 55.8 Staff invitation, role assignment and responsibility matrix

The platform must support invitations and secure account activation. School administrators or principals can invite staff according to their authority. Invited staff verify their identity and activate their own account; no shared/default passwords.

| Role | Primary responsibility | Important boundaries |
| --- | --- | --- |
| ACADIVA Platform Administrator | Central tenants, verification, subscriptions, platform operations | No casual school-record editing |
| School Owner/Proprietor | Ownership, strategic oversight, school-level authority | May delegate operational work |
| School Administrator | School setup, branding, classes, subjects, staff and configuration | Does not automatically own every academic/financial decision |
| Principal/Head Teacher | Academic leadership, admissions, assignments, grading policy and school operations | Sensitive actions logged |
| Registrar/Admissions Officer | Applications, student records, placement and documents | No unrestricted finance or platform access |
| Bursar/Accountant | Fee schedules, payments, receipts and reconciliation | No academic result editing |
| Timetable Coordinator | Builds and maintains timetable | Cannot override hard scheduling conflicts silently |
| Class Teacher | Class attendance and assigned class responsibilities | No core biodata editing or unrestricted finance access |
| Subject Teacher | Assigned class/subject attendance and score entry | No grading-policy or unrelated student-record editing |
| Parent/Guardian | Verified access to linked children | Cannot access unrelated students |
| Student | Age-appropriate access to own permitted information | No access to other students' records |

A school may assign multiple roles to one staff member where appropriate. Permission combinations must be explicit and testable.

### 55.9 Academic result completeness and publication rule

Teachers should be able to publish their own completed subject results without routine principal approval.

Before publication, ACADIVA checks the official class register:

- Every registered student must have a valid score or an explicit outcome/status such as absent, exempted or another school-approved N/A reason.
- Blank/unaccounted entries block publication and identify the affected students.
- N/A must not be silently converted into zero.
- The teacher can save drafts and resume.
- Published results are locked against ordinary edits.
- Corrections after publication require an authorised, reasoned and audited amendment.
- Overall report cards become final when all required subject outcomes are complete under the school's rules.

### 55.10 Timetable configuration and scheduling ownership

The school chooses a timetable coordinator, such as a head teacher, principal or designated staff member. The School Administrator configures the underlying classes, subjects, staff and available rooms.

The timetable engine must enforce hard constraints:

- One teacher cannot teach two classes at the same time.
- One class cannot attend two lessons at the same time.
- One physical classroom cannot be assigned to two classes simultaneously.
- Teacher availability and school operating periods must be respected.

Soft constraints should improve timetable quality:

- Avoid excessive consecutive periods.
- Distribute subjects across the week.
- Reduce unnecessary gaps.
- Respect reasonable teacher preferences.

No external timetable API is required as a product assumption. Build and test an internal scheduling engine; evaluate specialist libraries only if they reduce complexity without compromising control. The system must explain unsatisfied constraints rather than silently generating an invalid timetable.

### 55.11 Mandatory pre-build / pre-tool-call checklist

This checklist applies to every future feature and technical action, not only the initial school setup.

<b>Before planning or coding</b>

- [ ] Re-read the master blueprint and latest decision sections.
- [ ] Re-read the relevant module checklist.
- [ ] Confirm whether the request is in current release, later release or out of scope.
- [ ] Identify all user roles affected.
- [ ] Identify all data entities and relationships affected.
- [ ] Identify tenant-isolation and privacy implications.
- [ ] Identify dependencies, integrations and external costs.
- [ ] Identify mobile, desktop and low-bandwidth implications.
- [ ] Identify accessibility and usability requirements.
- [ ] Identify animation/performance implications where relevant.
- [ ] Identify failure, retry, duplicate and recovery scenarios.
- [ ] Identify migration/backward-compatibility implications.
- [ ] Define acceptance criteria and tests before implementation.

<b>Before changing code, schema, settings or integrations</b>

- [ ] Confirm the current implementation and source of truth.
- [ ] Check existing code paths and shared components.
- [ ] Check whether the change affects other modules or roles.
- [ ] Review secrets, permissions, RLS and server-side validation.
- [ ] Plan migration, backup and rollback where applicable.
- [ ] Avoid unnecessary new services, APIs or paid tools.
- [ ] Never expose secret keys or privileged operations in client code.
- [ ] Ensure changes are idempotent where retries may occur.

<b>Before marking complete or deploying</b>

- [ ] Run relevant unit tests.
- [ ] Run integration tests.
- [ ] Run end-to-end tests for affected roles.
- [ ] Test cross-tenant isolation.
- [ ] Test unauthorised and boundary cases.
- [ ] Test empty, invalid, duplicate and incomplete data.
- [ ] Test interrupted network and provider failures where relevant.
- [ ] Test mobile layouts and key screen sizes.
- [ ] Check performance and query behaviour.
- [ ] Verify logs, monitoring and error reporting.
- [ ] Verify backup/rollback readiness for risky changes.
- [ ] Update documentation, checklist and decision log.
- [ ] Record evidence and unresolved issues.
- [ ] Only then mark the task complete.

### 55.12 Cross-module regression matrix

A feature is not complete merely because its own screen works. Test its effects on connected modules.

| Change area | Must also verify |
| --- | --- |
| School branding | Website, parent/teacher portals, PDFs, receipts, admission letters |
| Student profile | Guardian links, class register, attendance, results, fees, exports |
| Class structure | Student placement, subjects, teacher assignments, timetable, reports |
| Teacher assignment | Teacher dashboard, score entry, attendance, timetable and permissions |
| Assessment configuration | Score entry, grade calculation, result completeness and report cards |
| Attendance | Class register, parent alerts, attendance reports and report cards |
| Fee/payment record | Student balance, parent view, bursar ledger, receipts and principal dashboard |
| Admission conversion | Student ID, class placement, guardian relationship, billing and notifications |
| Announcement | Correct audience, duplicate prevention, delivery logs and privacy |
| Subscription status | School access, exports, retained records and renewal reminders |
| School exit | Data export, tenant access, retention and deletion obligations |

### 55.13 Release priorities and scope control

<b>Core launch priorities</b>

- Secure multi-tenant foundation and central Operations workspace.
- School registration, verification and guided School Administrator setup.
- Roles, invitations and permissions.
- Nigerian academic templates and custom school structures.
- Student records, bulk onboarding and guardian relationships.
- Attendance.
- Teacher assignments and timetable.
- Assessment, result entry, publication and report cards.
- Fee management, receipts and payment reconciliation.
- Parent portal and targeted announcements.
- Branded school websites and shared document engine.
- Backups, monitoring, privacy, security and tested recovery.

<b>Later / explicitly deferred</b>

- Full CBT and online examination delivery.
- Advanced AI question generation.
- Complex private messaging.
- Advanced HR/payroll and staff salary payments.
- Library, transport, inventory and other extended ERP modules.
- Full website design freedom and advanced custom-domain options.
- Advanced analytics and multi-branch consolidation beyond validated needs.

CBT must have an architectural place and roadmap entry, but it is not a launch selling point or a reason to delay the core product.

### 55.14 Open decisions to resolve before the relevant implementation

- Final verification evidence and review procedure for schools and representatives.
- Exact central Operations staff roles and emergency-access approval.
- Whether [operations.acadiva.ng](http://operations.acadiva.ng) is provisioned as a dedicated app, protected route or separate deployment; decide based on security and operational architecture.
- Final school subdomain reservation, naming and custom-domain policy.
- Exact School Administrator versus Principal delegation defaults.
- Final student import schema and duplicate resolution.
- Exact grading defaults and supported school-specific grading models.
- Timetable engine algorithm/library selection and realistic test dataset.
- Notification providers, WhatsApp Business Platform approval, SMS/email/push costs and consent/opt-out rules.
- Subscription invoice, payment confirmation, grace-period and export process.
- Legal review of children's data, privacy notices, retention, guardian verification and school contracts.
- Load-test targets, test profiles and scaling triggers.

### 55.15 Final product and engineering principle

ACADIVA must be easy for a school to operate and rigorous underneath. The School Administrator, Principal, teachers, bursar, parents and students are all essential parts of the equation. Their responsibilities, permissions and workflows must be designed together, not added as disconnected screens.

The system must preserve one authoritative record, enforce school separation, make routine work simple, protect sensitive changes, recover safely from failure and remain maintainable as usage grows.

<b>Never build first and ask what it affects afterwards. Read the plan, inspect the dependencies, check the risks, build carefully, test the whole connected workflow and update the checklist before moving to the next step.</b>

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

## Section 58 — Implementation-Stage Design Research Gate and Feature-by-Feature Delivery Checklist

<b>Status:</b> Mandatory implementation process. This section converts Section 57's design standard into an explicit execution requirement. It is connected to Section 40's master checklist, Section 46's build sequence, Section 55's pre-build governance and Section 56's vertical-slice implementation plan.

### 58.1 Where this sits in the implementation lifecycle

The required order for every feature or meaningful screen change is:

<b>Blueprint/checklist review → requirement and workflow definition → reference research → original ACADIVA design → design review/approval → technical implementation plan → coding → visual and functional QA → connected workflow tests → acceptance evidence → checklist update.</b>

Reference research is not a one-time exercise for the whole product. It is repeated for each feature and materially redesigned screen. A general design system and an approved dashboard do not automatically approve later features.

### 58.2 Mandatory feature-level design gate

Before coding a feature, the implementation owner must:

1. Reopen the current ACADIVA master blueprint and relevant checklist; confirm current decisions and release scope.
2. Define the user roles, user problem, workflow, data dependencies, permissions and expected outcome.
3. Research relevant examples on all six approved platforms: Mobbin, Dribbble, Behance, Awwwards, Refero and Design Spells. Record applicable references and honestly note when a source has no relevant example or cannot be accessed.
4. Inspect the actual reference screens or flows where accessible; do not treat a search thumbnail as a reviewed design.
5. Produce an original ACADIVA design adapted to the Nigerian school context, target users, devices, network conditions and product architecture.
6. Document screen layout, mobile and desktop behaviour, components, typography/spacing tokens, interaction states, validation, loading, empty, offline, error, success and permission-denied states.
7. Review accessibility, contrast, readability, touch targets, keyboard/focus behaviour, reduced motion and low-end-device performance.
8. Obtain design approval against the acceptance criteria before feature implementation begins.
9. Prepare the technical change plan: affected records, roles, APIs/services, events, integrations, migrations, security boundaries, tests, risks and rollback.
10. Implement the smallest complete vertical slice using the approved design and shared components.
11. Compare the implemented interface with the approved design and test all relevant roles and connected workflows.
12. Record defects, evidence, unresolved decisions and final checklist status. Do not mark complete until both visual and functional acceptance pass.

### 58.3 Master implementation checklist — 40AE

- [ ] AE01. Before each feature, reopen the latest master blueprint and the relevant module checklist. (Core)
- [ ] AE02. Confirm the feature's release scope, dependencies, current decisions and any conflicts with newer sections. (Core)
- [ ] AE03. Define user roles, tasks, workflow, data ownership, permissions and acceptance criteria before design. (Core)
- [ ] AE04. Complete feature-level reference research across Mobbin, Dribbble, Behance, Awwwards, Refero and Design Spells. (Core)
- [ ] AE05. Record actual reference URLs, platform, product/project, inspected screen/flow, design lesson and access limitations. (Core)
- [ ] AE06. Do not claim a reference was inspected if it was only seen in a thumbnail or was inaccessible. (Core)
- [ ] AE07. Create an original ACADIVA-specific design; do not copy proprietary screens, brand assets, illustrations or written content. (Core)
- [ ] AE08. Connect the design to the role, workflow, authoritative data, permissions and other affected workspaces. (Core)
- [ ] AE09. Specify mobile-first layouts and responsive behaviour for relevant phone, tablet and desktop sizes. (Core)
- [ ] AE10. Design all relevant loading, empty, validation, offline, retry, error, success and permission-denied states. (Core)
- [ ] AE11. Review accessibility, readable typography, contrast, focus/touch behaviour and reduced-motion needs. (Core)
- [ ] AE12. Review performance on low-bandwidth connections and lower-powered mobile devices. (Core)
- [ ] AE13. Obtain feature-level design approval before coding; a shared design-system approval alone is insufficient. (Core)
- [ ] AE14. Prepare the technical implementation plan, dependencies, migration/rollback and test strategy before changing code or data. (Core)
- [ ] AE15. Implement against the approved design using shared ACADIVA components and configurable brand tokens. (Core)
- [ ] AE16. Compare the implemented interface with the approved design and record visual differences. (Core)
- [ ] AE17. Test the feature end to end for every affected role and verify all connected dashboards and records. (Core)
- [ ] AE18. Test negative, boundary, duplicate, interrupted-network and unauthorised cases where relevant. (Core)
- [ ] AE19. Record test evidence, outstanding defects, unresolved decisions and next safe step. (Core)
- [ ] AE20. Mark the feature complete only after design, functional, security, accessibility and relevant regression acceptance pass. (Core)

### 58.4 Build-sequence enforcement

Section 56.12 Stage 2 is updated to require feature-level research, design approval and implementation-ready handoff. This gate also applies when later build stages introduce new screens or materially change existing screens. For example:

- School registration and onboarding: research and approve the registration and setup flows before coding them.
- Student and guardian onboarding: research and approve parent, school-admin and guardian activation flows before coding them.
- Attendance and results: research and approve teacher entry, validation, publication and parent views before coding them.
- Finance and payment: research and approve the complete parent-to-bursar payment journey before coding it.
- Timetable: research and approve timetable creation, conflict resolution and viewing experiences before coding them.
- School websites: research and approve public website templates and publishing experiences before coding them.
- Operations: research and approve central verification, school activation and support workflows before coding them.

### 58.5 Release and completion rule

A feature cannot be moved to implementation-ready status without its research record and approved design. It cannot be moved to completed status merely because code exists or the page renders. The approved design, implemented interface, connected workflow, permissions and test evidence must agree.

The founder may change or waive a design direction explicitly, but no developer or agent may silently bypass this gate. If a reference platform is unavailable, record the limitation and use the other accessible approved sources; never fabricate research evidence.

### 58.6 Relationship to existing blueprint

- Section 40AE is the execution checklist for this process.
- Section 46.8 defines the overall product build order.
- Section 56.12 defines the vertical-slice stages and exit evidence.
- Section 55.11 and Section 56.16 define the mandatory pre-tool and pre-build review.
- Section 57 defines the approved research sources, quality standard and design acceptance principles.

This section adds an implementation-stage control. It does not claim that any feature has been researched, designed, coded or tested yet.

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

<page url="https://app.notion.com/p/41c9a9b48b7a814e96e4f5e4cbef2920">
00 — ACADIVA Core Operating Model, Master Requirements & System Architecture
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a8115b27ce9fcd65320a0">
01 — ACADIVA Master Execution Checklist, Governance & Build Gates
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a8197b133d5f5a18b628d">
02 — ACADIVA Product Strategy, Market & Commercial Model
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a81b4aed8f94986dc1ecb">
03 — ACADIVA Core Modules, Roles, Teaching & School Workflows
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a81539c55f74d01885bc1">
04 — ACADIVA Admissions, Student Records, Guardian Identity & Finance
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a816a9283d8878f359bb0">
05 — ACADIVA Platform Architecture, Operations, Integrations & Infrastructure
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a81d9a0cac9af71e89d01">
06 — ACADIVA Design, Experience & Creative Technology
</page>

<page url="https://app.notion.com/p/41c9a9b48b7a814db204d631c1a7df64">
07 — ACADIVA Application Build Map, Delivery Register & Implementation Audit
</page>
