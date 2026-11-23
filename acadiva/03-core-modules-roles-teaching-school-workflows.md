<!-- Source: https://app.notion.com/p/41c9a9b48b7a81b4aed8f94986dc1ecb?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🏫 03 — ACADIVA Core Modules, Roles, Teaching & School Workflows

This manual groups the core school modules and everyday role workflows: school structure, student and staff records, teaching, attendance, timetables, communication, role-based workspaces and cross-dashboard consistency. Use it to understand how a feature affects the rest of the school operating system.

<b>Preservation rule:</b> the full source sections are reproduced below. Their original requirements, examples, rationale, checklists and open questions are retained. This curated page changes navigation and grouping, not product decisions.

---

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

---

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

---

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

---

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

---

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

---

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

---

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

---

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

---

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

---

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

---

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

---

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
