---
name: ecommerce-compliance-auditor
description: Audit e-commerce websites, marketplaces, platforms, and available implementation evidence against country-specific compliance rule packs. Always run the mandatory 10-question discovery interview before auditing.
---

# E-Commerce Compliance Auditor

## Mission

Audit an e-commerce operation against the applicable rule pack using only evidence the agent can actually observe or access.

The skill is environment-adaptive. Do not force artificial `basic` or `advanced` modes. First discover the business context and available access; then use every relevant evidence source the environment genuinely provides.

## Non-negotiable first step: ask all 10 discovery questions

Before opening pages for the audit, scanning a repository, querying an API/database, or producing compliance findings, ask the user these 10 questions. The user must answer all 10; `unknown`, `not available`, and `not applicable` are valid answers.

1. **Jurisdiction** — Which country or countries are you asking me to audit for? If Nepal, confirm that Nepal is the target market/jurisdiction.
2. **Business role** — Which best describes the audited business: first-party/list-based seller, marketplace/intermediary, individual seller using a marketplace, platform/software provider, delivery provider, or a combination?
3. **Audit targets** — What exact public targets should I inspect: website URL(s), app/web-app URL(s), social-commerce handle(s), storefront(s), checkout domain(s), or other customer-facing endpoints?
4. **Customer journey** — Which flows are in scope and safely testable: browse/search, product/service page, cart, checkout, payment selection, account/profile, cancellation, return/refund, review/rating, complaint/grievance, seller onboarding, or delivery tracking?
5. **Environment and test safety** — Is the target production, staging, development, or local? May I submit forms, create a test account, add to cart, or proceed to checkout? Never place a paid order, send a real complaint, modify production data, or trigger an external action unless explicitly authorized.
6. **Internal access available** — What can the agent access in this environment: GitHub/repository, local filesystem, CMS/admin, API documentation, database/schema/read-only query access, configuration/secrets metadata, logs, network/devtools, or none?
7. **Business identity expected** — What legal/business identifiers should exist, if known: registered business name, registration authority/number, PAN/VAT, registered/head/branch addresses, e-commerce portal listing number, contact details, grievance contact, licenses? `Unknown` is acceptable.
8. **Commerce model details** — Does the operation sell its own inventory/services, third-party seller inventory/services, or both? Does it rank, feature, sponsor, or prefer sellers/listings? Are reviews/ratings supported?
9. **Products/services and regulatory sensitivity** — What categories are sold? Are any licensed, restricted, age-sensitive, imported, expiring, warrantied/guaranteed, digital, professional, financial, health, travel, education, or otherwise specially regulated?
10. **Desired output and remediation authority** — Do you want audit-only findings, remediation instructions, proposed code changes, or direct fixes where the agent has write access? State any files/systems that must not be changed.

Do not silently infer unanswered discovery items. If an answer is incomplete, record it as `unknown` and reflect the limitation in the report.

## After discovery: build an audit plan automatically

From the 10 answers, create a short capability matrix.

| Evidence capability | Use when available | Typical evidence |
|---|---|---|
| Browser/web | Public URL exists | visible text, forms, navigation, product data, policy pages, checkout UI, screenshots |
| Search/web research | Current law/source verification is permitted | official government notices, directives, portals, current source status |
| Repository/local code | Code access exists | templates, routes, models, validation, policy components, checkout/refund/grievance logic |
| CMS/admin | Read access exists | merchant identity fields, product fields, policy settings, seller settings |
| API | Docs or read access exists | invoice endpoints, order state, returns, grievances, seller metadata |
| Database | Read-only/schema access exists | required fields, persistence, audit records, retention structures |
| Network/devtools | Available | request/response behavior, exposed data, client/server flow evidence |

Use all relevant available capabilities. Do not call a missing capability a failure by itself.

## Rule-pack selection

1. Load the country pack from `rules/<country>/`.
2. Read its source hierarchy and freshness warnings.
3. Apply only rules that match the discovered business role and product/service scope.
4. If multiple jurisdictions apply, audit each jurisdiction separately before giving any combined summary.
5. If a required current legal source is known to exist but is not incorporated or verifiable, mark the audit scope limitation clearly and avoid claiming full legal compliance.

## Evidence-first audit method

For each applicable rule:

1. Read the rule's legal basis and applicability.
2. Identify the strongest evidence source available.
3. Inspect the relevant customer journey and, when available, implementation evidence.
4. Record exact evidence: URL/page, UI text or field, repository path/symbol, configuration key, database/API field, screenshot reference, or other reproducible observation.
5. Decide status using the status definitions below.
6. Record confidence.
7. Provide a precise remediation that fixes the legal gap rather than merely changing wording.
8. If code write access and user authorization exist, propose or implement the smallest safe fix; still keep the finding and evidence trail.

Never treat absence from one sampled page as proof that a feature never exists. Search appropriate navigation/flows first.

## Required statuses

- **PASS** — Sufficient observed evidence supports the requirement.
- **FAIL** — Observed evidence directly contradicts the requirement, or a required element is clearly absent after reasonable inspection.
- **PARTIAL** — Some required elements are present, but one or more material elements are missing/unclear.
- **NOT_OBSERVED** — The requirement may be testable, but available evidence was insufficient to determine it.
- **MANUAL_VERIFICATION** — The requirement depends on records, conduct, licenses, timing, authenticity, confidentiality, or other facts that cannot be reliably established from the available environment.
- **NOT_APPLICABLE** — The discovery answers establish that the rule does not apply.

Do not convert `NOT_OBSERVED` into `FAIL` just to produce a stronger report.

## Confidence

Use:

- **High** — Direct, reproducible evidence.
- **Medium** — Strong indirect evidence or incomplete flow coverage.
- **Low** — Limited evidence; finding should normally be `NOT_OBSERVED` or `MANUAL_VERIFICATION` rather than `PASS`/`FAIL`.

## Severity

Use four operational severities:

- **Critical** — Direct statutory exposure to serious punishment, prohibited trade, material consumer harm, or a foundational condition whose absence makes the operation unlawful.
- **High** — Direct statutory offence/fine exposure or major consumer-rights failure.
- **Medium** — Material compliance gap that should be fixed but is not mapped to the highest penalty tier in the loaded source.
- **Low** — Documentation, clarity, accessibility, or evidence-readiness weakness with limited standalone impact.

Where the rule pack maps a specific penalty provision, report that mapping separately from operational severity. Do not invent a penalty.

## Scoring: Lighthouse-inspired, not certification

The report may show a 0–100 **Compliance Readiness Score** for navigation, but it must never be called a government score, certification, approval, or legal opinion.

Recommended weighting:

- Critical: 10
- High: 6
- Medium: 3
- Low: 1

For scored applicable rules:

- PASS = 100% of weight
- PARTIAL = 50%
- FAIL = 0%
- NOT_OBSERVED / MANUAL_VERIFICATION = exclude from compliance numerator and show separately as **unverified coverage**
- NOT_APPLICABLE = exclude

Always display:

1. Compliance Readiness Score for verified/scored items.
2. Evidence Coverage percentage.
3. Count of Critical/High failures.
4. Count of unverified/manual items.

A high score with poor evidence coverage must be visibly labeled low-confidence.

## Report requirements

Use `templates/audit-report.md`.

The report must include:

- target and timestamp
- jurisdiction and loaded rule-pack version/source status
- 10 discovery answers
- capabilities used and unavailable
- executive summary
- readiness score + evidence coverage
- blockers first
- category results
- every applicable rule finding
- legal basis
- exact evidence
- confidence
- remediation
- source/freshness limitations
- statement that the audit is not a legal certification

## Remediation behavior

When the user requests fixes:

1. Prioritize Critical, then High, then Medium, then Low.
2. Prefer reusable platform-level fixes over one-off text patches.
3. Do not fabricate business identifiers, licenses, registration numbers, warranty terms, refund promises, country of origin, expiry dates, or legal policies.
4. If a required value is business-owned data, implement the field/validation/display path and mark the actual value as requiring merchant/user input.
5. Preserve existing architecture and conventions where possible.
6. Re-run the affected checks after changes and show before/after evidence.

## Nepal-specific invocation

When Nepal is in scope, load:

- `rules/nepal/README.md`
- `rules/nepal/ecommerce-act-2081.md`

Treat the Act checks as the current implemented baseline in this repository. Follow any freshness warning in the Nepal README before representing the audit as complete current-law coverage.
