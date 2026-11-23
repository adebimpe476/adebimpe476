<!-- Source: https://app.notion.com/p/41e9a9b48b7a81f2babfe4451c5ed779?pvs=204 -->
<!-- Exported from Notion on 2026-11-23. Original content preserved below. -->

# 🌐 ACADIVA — Subdomain & Digital Presence Strategy

# Proposed domain rule — availability and ownership not verified

<b>ACADIVA's proposed root domain is </b><b><code>acadiva.ng</code></b><b>.</b> The intended main website would be <code>https://acadiva.ng</code>, subject to domain availability, purchase, and configuration. Treat all uses of this domain in this document as provisional; do not publish or configure it until ownership and availability are confirmed. All proposed subdomains below are provisional as well.

The brand-name decision is separate from domain clearance. No claim is made that [acadiva.ng](http://acadiva.ng) is available, owned, registered, or configured. Verify the domain and complete company/trademark checks before public use.

---

# Purpose

ACADIVA should use dedicated subdomains as focused, credible destinations for different audiences and operational functions. When ACADIVA approaches an investor, strategic partner, school, journalist, technical contributor, or existing customer, the team should be able to share a relevant ACADIVA-owned link instead of sending everyone to the same homepage or assembling documents repeatedly.

This is a proposed information architecture. The domains are recommendations, not claims that the subdomains have already been purchased, configured, built, or launched.

# Core principle

- The main website remains the public front door and source of truth for the overall ACADIVA story.
- Each subdomain has one clear audience, purpose, owner, and content standard.
- Public-facing pages must remain consistent with the main website and current verified facts.
- Restricted operational areas must use authentication and role-based access; a hard-to-guess URL is not security.
- Build only when there is a real use case. Reserve important names where practical, but do not create empty subdomains just to have them.

# Proposed subdomain map

| Subdomain | Primary audience | Purpose | Access |
| --- | --- | --- | --- |
| [partnership.acadiva.ng](http://partnership.acadiva.ng) | Investors, strategic partners, sponsors, institutions | Default link for investor and partnership outreach. Include ACADIVA overview, problem, solution, product, market opportunity, business model, verified traction/work completed, deployment model, pilot proposal, partnership opportunities, pitch materials, and contact. Tailor recipient-specific material when needed; do not imply an existing relationship. | Public summary; confidential materials shared separately |
| [cto.acadiva.ng](http://cto.acadiva.ng) | CTO, engineering leads, authorised technical contributors | Technical command centre for architecture, repositories, environments, integrations, security, infrastructure, technical decisions, release process, change approvals, and incident notes. Coordinate changes; do not make this an unreviewed route to production. | Restricted; named accounts and least-privilege access |
| [news.acadiva.ng](http://news.acadiva.ng) | Schools, partners, media, public | Official announcements, product releases, pilot updates, milestones, events, company statements, and media notes. Date and fact-check every update. | Public |
| [impact.acadiva.ng](http://impact.acadiva.ng) | Investors, funders, partners, schools | Evidence of completed work and outcomes: verified milestones, pilot activity, schools onboarded, teachers trained, devices deployed and operational, usage, case studies, and progress reports. Separate results from targets and projections. | Public summary; sensitive data restricted |
| [schools.acadiva.ng](http://schools.acadiva.ng) | School proprietors, principals, administrators, teachers | School-facing information and onboarding: how ACADIVA works, implementation steps, requirements, training, FAQs, pilot/application interest, and school-specific onboarding links. A future authenticated school portal may live here or at a dedicated app subdomain. | Public information plus authenticated areas |
| [docs.acadiva.ng](http://docs.acadiva.ng) | Schools, technical partners, internal team | Product documentation and practical guides: setup, user guides, feature instructions, release notes, integrations/API documentation where appropriate, and troubleshooting. | Public or selectively restricted |
| [support.acadiva.ng](http://support.acadiva.ng) | Existing schools and users | Help requests, issue reporting, FAQs, and support policies. Launch only when requests can be routed to a monitored process with clear ownership and escalation. | Public entry point; private case details |
| <code>staging.acadiva.ng</code> (optional; not required at launch) | CTO and authorised testers | A permanent shared pre-production environment only if the team later needs one. Initially, use temporary preview deployments for individual branches or proposed changes. Use test data and access controls; never expose real student information. | Restricted if created |

# How the main website and subdomains work together

- [acadiva.ng](https://acadiva.ng) — main public website and front door.
- [partnership.acadiva.ng](http://partnership.acadiva.ng) — default investor and partner destination.
- [cto.acadiva.ng](http://cto.acadiva.ng) — technical governance and coordination.
- Preview deployment URLs — test individual changes before approving production release. A permanent <code>staging.acadiva.ng</code> can be added later if the team needs a shared, always-on test environment.
- [news.acadiva.ng](http://news.acadiva.ng) — official announcements.
- [impact.acadiva.ng](http://impact.acadiva.ng) — evidence of progress and outcomes.
- [schools.acadiva.ng](http://schools.acadiva.ng) — school acquisition, information, and onboarding.
- [docs.acadiva.ng](http://docs.acadiva.ng) — user and technical guidance.
- [support.acadiva.ng](http://support.acadiva.ng) — user assistance.

The investor/partner hub can link to news and impact pages so recipients can verify public updates and progress. The main website should direct each audience to the relevant destination without duplicating every page.

# Partnership and investor hub: required content

[partnership.acadiva.ng](http://partnership.acadiva.ng) is the priority external-facing subdomain because it is intended to be shared repeatedly during investor and partner outreach. It should be a current, reusable information pack rather than a generic landing page.

1. ACADIVA at a glance — what it is, who it serves, and the school problem it addresses.
2. Product — current features, clearly separating live from planned.
3. Why now — the case for digital infrastructure in schools.
4. Business model — pricing assumptions, revenue logic, and open questions.
5. Deployment model — school rollout, shared tablet infrastructure proposal, onboarding, training, and support.
6. Work completed — verified product, operational, and market-development milestones.
7. Pilot proposal — scope, participating schools, responsibilities, budget assumptions, and success measures.
8. Partnership opportunities — technology, distribution, school access, implementation, funding, and strategic collaboration.
9. Evidence — product demonstrations, approved case studies, metrics, and dated updates.
10. Contact — a clear route for investor and partnership enquiries.

Maintain a master version of company facts and figures. Create recipient-specific proposals only when needed. Do not publish confidential financial, student, school, or partner information on the public hub.

# CTO and production-change governance

Because technical changes can directly affect the main website, the CTO space must support controlled delivery:

- Keep production credentials, secrets, and sensitive configuration out of public pages and ordinary documentation.
- Use named accounts, multi-factor authentication where available, and least-privilege permissions.
- Track significant changes with a written change record: reason, affected systems, owner, test evidence, approval, deployment time, and rollback plan.
- Test meaningful changes using preview deployments before production. A permanent staging subdomain is optional, not a requirement for every change.
- Back up critical data and configuration before high-risk changes.
- Define who can approve and deploy production changes; access to the CTO subdomain must not automatically grant production authority.
- Keep an incident log for outages, regressions, security events, and lessons learned.

# Content integrity rules

- Label information as Live, In development, Proposed, or Target where status could be misunderstood.
- Date announcements, milestones, metrics, and reports.
- Do not present a prospective partner, investor conversation, pilot, funding request, or roadmap item as a confirmed commitment or completed achievement.
- Distinguish actual traction from targets, estimates, and projections.
- Do not expose identifiable student records, personal information, school-sensitive information, credentials, or confidential partner discussions.
- Keep one approved source of truth for company description, product status, pricing, metrics, and contact details.

# Recommended rollout order

<b>Phase 1 — External-facing essentials</b>

1. [partnership.acadiva.ng](http://partnership.acadiva.ng) — build first; use as the standard investor and partner destination.
2. [news.acadiva.ng](http://news.acadiva.ng) — launch when there are real announcements to publish.
3. [impact.acadiva.ng](http://impact.acadiva.ng) — publish verified milestones and evidence of work completed.

<b>Phase 2 — School adoption and safe delivery</b><br />4. [schools.acadiva.ng](http://schools.acadiva.ng) — school information and onboarding.<br />5. [cto.acadiva.ng](http://cto.acadiva.ng) — establish technical governance when a CTO or engineering contributor is in place. Use temporary preview deployments for testing; create a permanent staging subdomain only if the team needs a shared always-on test environment.<br />6. [docs.acadiva.ng](http://docs.acadiva.ng) — publish as product and implementation documentation becomes substantial.

<b>Phase 3 — Operational maturity</b><br />7. [support.acadiva.ng](http://support.acadiva.ng) — once support requests can be actively handled.

# Decisions still to make

- Confirmed: ACADIVA's official news address is <code>news.acadiva.ng</code>.
- Confirm domain/DNS ownership, registrar, hosting, and deployment approach.
- Decide whether [partnership.acadiva.ng](http://partnership.acadiva.ng) is public to everyone or has private, recipient-specific areas for confidential materials.
- Define who owns content updates for each subdomain and how often each is reviewed.
- Decide whether the CTO area is a documentation/workspace portal, an engineering dashboard, or both; do not expose deployment controls without a proper security design.
- Confirm whether the existing product app should remain at its current address or eventually move to [app.acadiva.ng](http://app.acadiva.ng). Do not migrate without a technical and SEO review.
- Set up analytics, privacy notices, access controls, backups, and monitoring consistently across relevant properties.

# Immediate next steps

- [x] Confirm the main domain as <code>acadiva.ng</code>, remove <code>status.acadiva.ng</code>, and use <code>news.acadiva.ng</code> for official news.
- [ ] Audit the current main website and existing app so the proposed structure does not duplicate or disrupt live functionality.
- [ ] Draft partnership hub content from verified ACADIVA facts and current proposals.
- [ ] Create the DNS and deployment plan with the technical owner.
- [ ] Launch only the first priority destination; add others as their content and operating processes are ready.

<b>Status:</b> Proposed information architecture, recorded 20 November 2026. No subdomain is represented as configured or live unless separately verified.
