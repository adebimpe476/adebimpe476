<!-- Source: https://app.notion.com/p/41c9a9b48b7a8115b27ce9fcd65320a0?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🧪 01 — ACADIVA Master Execution Checklist, Governance & Build Gates

## Live application build status

The feature checklist below defines requirements, not implementation status. Use the single authoritative delivery register and implementation audit in <mention url="https://app.notion.com/p/41c9a9b48b7a814db204d631c1a7df64">07 — ACADIVA Application Build Map, Delivery Register & Implementation Audit</mention> to determine what is built, untested, blocked or still required. Never check an item merely because a screen or mock-up exists; require end-to-end acceptance evidence.

This is the execution-control manual. It defines the mandatory review before work, the school/company authority boundaries, the master checklist and feature-level design/build gates. It must be consulted before every meaningful implementation. The cooking-style taste-test loop in the parent master index applies throughout the build, not just at final QA.

<b>Preservation rule:</b> the full source sections are reproduced below. Their original requirements, examples, rationale, checklists and open questions are retained. This curated page changes navigation and grouping, not product decisions.

---

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

---

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

---

## 50-C — ACADIVA Product Principles, Deliberate Engineering, Design Quality, Scale and Pre-Build Review (originally numbered Section 50)

<b>Stable record ID:</b> 50-C. Original content is retained; this identifier resolves the duplicate original section number.

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

---

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
