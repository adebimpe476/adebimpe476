<!-- Source: https://app.notion.com/p/41c9a9b48b7a81539c55f74d01885bc1?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🧾 04 — ACADIVA Admissions, Student Records, Guardian Identity & Finance

This manual groups the sensitive end-to-end workflows for admissions, enrolment, student record portability, parent/guardian relationships, school-led onboarding and finance. These flows must be assessed together because they share student identity, guardian links, school authority, financial records and audit requirements.

<b>Preservation rule:</b> the full source sections are reproduced below. Their original requirements, examples, rationale, checklists and open questions are retained. This curated page changes navigation and grouping, not product decisions.

---

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

---

## 43. Online admissions, parent application links and student onboarding — 15 November 2026

### 43.1 Product requirement and principle

Online application and admissions are a core ACADIVA capability, not a later cosmetic website feature. Each school must be able to receive applications through a shareable school-specific link. A parent should be able to complete an application on a phone without first visiting the school or creating a complicated account. The school retains authority over screening, admission decisions, class placement and activation of the official student record.

The workflow must avoid entering the same student's information twice. An application is the source record during admissions; when the school admits the applicant, ACADIVA converts or promotes that application into the authoritative student record while preserving its history and submitted documents.

### 43.2 School-specific application link

- Each school receives a public admissions page on its ACADIVA school subdomain, for example <code>schoolname.acadiva.ng</code> (final domain convention remains subject to domain decisions).
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

---

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

---

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

---

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

---

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

---

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
