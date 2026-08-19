# Nepal — Electronic Commerce Act, 2081 (2025) Audit Rules

Rule-pack ID: `NP-ECA-2081`

Use this file only after reading `rules/nepal/README.md` and completing the mandatory 10-question discovery interview in `SKILL.md`.

## Status discipline

A public website audit can establish many disclosure requirements, but it usually cannot prove business registration validity, portal listing validity, record retention, confidentiality practices, seller agreements, or actual complaint-resolution timing. Use `MANUAL_VERIFICATION` or `NOT_OBSERVED` for those unless stronger evidence is available.

## Penalty labels

- `ACT-S22` — Section 21(a)-(d) offence mapping; Section 22 fine: NPR 20,000–100,000 depending on gravity.
- `ACT-S23` — Section 21(e) offence mapping; Section 23: NPR 50,000–500,000, or 6 months–3 years imprisonment, or both, depending on gravity.
- `OTHER/UNMAPPED` — the Act states a duty or points to prevailing law but this rule file does not map a specific Section 22/23 penalty.

Operational severity and penalty labels are separate.

---

# A. Legal eligibility and platform foundation

### NP-ECA-003-01 — Registered and authorized business

- **Legal basis:** Section 3(1)
- **Applies to:** entity conducting e-commerce.
- **Requirement:** the firm, company, or institution must be duly registered and authorized under prevailing law to trade the relevant goods/services.
- **Public evidence:** displayed registration authority/number and business identity can support, but not prove, validity.
- **Internal/manual evidence:** registration certificate, license/authorization, matching legal entity details.
- **Decision:** `PASS` only with reliable registration/authorization evidence; otherwise `MANUAL_VERIFICATION` rather than assuming from a website footer.
- **Severity:** Critical.
- **Penalty:** `OTHER/UNMAPPED` in this Act rule map.
- **Remediation:** obtain/validate required registration and authorization; ensure platform identity matches legal records.

### NP-ECA-003-02 — Prohibited goods/services are not traded electronically

- **Legal basis:** Section 3(2)
- **Applies to:** all e-commerce offerings.
- **Requirement:** goods/services prohibited from electronic trade by prevailing law or Nepal Gazette notice must not be traded electronically.
- **Evidence:** inventory/catalog categories, product pages, marketplace policy, seller controls, prohibited-product rules; current-law research may be required.
- **Decision:** `FAIL` only when an actually prohibited item/service is observed or reliably evidenced; otherwise manual verification may be needed.
- **Severity:** Critical.
- **Penalty:** `OTHER/UNMAPPED` here; other prevailing laws may apply.
- **Remediation:** block prohibited categories/listings and implement seller/product controls.

### NP-ECA-004-01 — Electronic platform established

- **Legal basis:** Section 4(1)
- **Applies to:** business entity conducting e-commerce, subject to the Act's proviso for micro/equivalent small-scale entrepreneurs using other electronic platforms.
- **Requirement:** establish an electronic platform for e-commerce, with the statutory small/micro proviso considered from discovery facts.
- **Public evidence:** operating website/app/platform or other qualifying electronic platform.
- **Decision:** apply carefully to small/micro sellers; do not assume a standalone website is specifically required.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(a).
- **Remediation:** ensure the business conducts e-commerce through a qualifying electronic platform appropriate to its statutory status.

### NP-ECA-004-02 — Business/platform identity disclosure matrix

- **Legal basis:** Section 4(2)(a)-(i), Section 4(4)
- **Applies to:** business entity.
- **Requirement:** disclose clearly, completely, and accessibly enough for an informed purchase decision:
  1. electronic platform name;
  2. business name, address, registering authority, registration certificate number;
  3. registered office, head office, and branches/outlets if any;
  4. details of any license for a specific type of business;
  5. whether the business is intermediary or list-based e-commerce;
  6. VAT registration number or PAN;
  7. contact details including email, telephone/mobile, telefax where applicable, social-media link, and designated customer-service email/telephone/mobile;
  8. grievance-responsible person/unit email, telephone/mobile, and address;
  9. e-commerce portal listing number under Section 5.
- **Public evidence:** footer, contact/about/legal/business-info page, seller/platform identity panel.
- **Internal evidence:** merchant settings schema and storefront rendering logic.
- **Decision:** `PASS` requires all applicable elements; missing material elements → `PARTIAL` or `FAIL` depending on breadth.
- **Severity:** High.
- **Penalty:** Section 21 does not separately name Section 4(2) disclosure failure, but Section 4 compliance is foundational; do not invent a direct Section 22 mapping for this subrule.
- **Remediation:** create one canonical compliance/business-information component and render it accessibly across the platform.

### NP-ECA-004-03 — Business disclosure changes updated within 48 hours

- **Legal basis:** Section 4(3)
- **Requirement:** changes to Section 4(2) information must be updated on the electronic platform within 48 hours.
- **Evidence:** change history, audit logs, CMS timestamps, deployment records.
- **Decision:** normally `MANUAL_VERIFICATION` on a browser-only audit.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** add ownership, timestamping, and SLA/automation for legal-business field updates.

---

# B. Department e-commerce listing

### NP-ECA-005-01 — Listed on Department e-commerce portal

- **Legal basis:** Section 5(1)-(3), and transition requirement in Section 5(2)
- **Applies to:** business entity after establishing its platform.
- **Requirement:** apply electronically for listing on the Department's e-commerce portal with required business/owner/director, business-description, PAN/VAT, contact, branch/outlet, and portal-requested details; obtain the platform listing number.
- **Public evidence:** listing number displayed under Section 4(2)(i); official portal record where verifiable.
- **Internal/manual evidence:** application/listing confirmation and current official record.
- **Decision:** missing required listing → `FAIL`; inability to validate → `MANUAL_VERIFICATION`.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(b).
- **Remediation:** complete Department listing and expose the issued listing number in the public business disclosure area.

### NP-ECA-005-02 — Branch/outlet changes updated on portal within 7 days

- **Legal basis:** Section 5(4)
- **Requirement:** after listing, additions/reductions in branches/outlets must be updated on the electronic portal within seven days.
- **Evidence:** official portal record, branch change logs, internal compliance records.
- **Decision:** generally `MANUAL_VERIFICATION` without official/internal records.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** add a compliance workflow triggered by branch/outlet master-data changes.

---

# C. Product and service disclosure

### NP-ECA-006-01 — Section 6 product/service disclosure matrix

- **Legal basis:** Section 6(a)-(p)
- **Applies to:** goods/services traded through e-commerce, subject to relevance of each item.
- **Requirement:** disclose on the electronic platform:
  1. name, nature, design, trademark, shape/image or combination, weight or underlying substance as applicable;
  2. final selling price including tax;
  3. additional delivery/transfer charges;
  4. precautions for use;
  5. delivery time and date;
  6. payment methods/modes;
  7. warranty/guarantee duration and conditions;
  8. producer or service provider identity;
  9. for imported goods/services, country of production/processing;
  10. post-purchase conditions;
  11. whether returnable/non-returnable and, if returnable, conditions and duration;
  12. for services, place of receiving the service and sale conditions;
  13. whether buyer requests can be cancelled before dispatch/service initiation and the details;
  14. manufacture date, expiry date, and other essential conditions applicable to the goods;
  15. key contractual terms in language understandable to the general public;
  16. mechanism for customer reviews, ratings, grievances, and feedback.
- **Public evidence:** representative product/service pages, cart, checkout, policy links, review/grievance UI.
- **Internal evidence:** product schema required fields, validation, publication gates, policy configuration.
- **Decision:** audit each applicable matrix item. Any missing item must be listed individually in evidence. Overall status: all applicable present → `PASS`; some missing → `PARTIAL`; disclosure system broadly absent → `FAIL`.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(c) for conducting e-commerce without disclosing Section 6 details.
- **Remediation:** encode Section 6 fields as structured commerce data with validation and storefront rendering; do not fabricate merchant-owned values.

---

# D. Contract, payment, delivery, return and refund

### NP-ECA-007-01 — Electronic transaction terms cover statutory lifecycle topics

- **Legal basis:** Section 7(1)-(2)
- **Requirement:** electronic transactions are valid contracts under prevailing law, and the business contract/terms must address necessary notice and provisions relating to delivery, cancellation, return, exchange, warranty/guarantee, and refund.
- **Public evidence:** checkout terms, order confirmation, linked terms/policies.
- **Internal evidence:** terms acceptance/versioning, checkout implementation, order snapshot of applicable terms.
- **Decision:** missing major lifecycle terms → `PARTIAL`/`FAIL`; validity/version evidence may need manual verification.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** centralize versioned commerce terms and make them available before contract conclusion.

### NP-ECA-008-01 — Lawful payment flow and immediate invoice/receipt

- **Legal basis:** Section 8(1)-(4)
- **Requirement:** permitted payment arrangements may be before/during/after transfer; lawful payment instruments must be used; on payment, provide an electronic or physical invoice plus payment receipt immediately and maintain a record; foreign-currency commerce remains subject to prevailing federal law.
- **Public evidence:** payment methods, post-payment receipt/invoice behavior where safely testable.
- **Internal evidence:** payment provider configuration, invoice generation, order/payment records, foreign-currency controls.
- **Decision:** do not perform a real paid transaction without explicit authorization. Use test/staging evidence when possible.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** generate immutable order invoice/receipt artifacts on successful payment and retain transaction records.

### NP-ECA-009-01 — Delivery matches agreed place/person/time

- **Legal basis:** Section 9(1)-(5)
- **Requirement:** deliver to buyer/representative at the agreed location and date/time/period; allow pickup where applicable; pre-dispatch delivery changes require mutual agreement; related charge changes may be made by mutual agreement.
- **Public evidence:** checkout delivery promise, pickup option, change-delivery workflow, fee disclosure.
- **Internal evidence:** order promise fields, fulfillment state machine, change consent/history.
- **Decision:** public terms alone cannot prove actual delivery performance; use operational records where available.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** persist the agreed delivery promise and consented changes as part of the order record.

### NP-ECA-010-01 — Mismatch return accepted unconditionally; exchange/refund supported

- **Legal basis:** Section 10(1)-(5)
- **Requirement:** if purchased goods/services do not conform to the Section 6 description, buyer may return them without use/damage; business must accept that return unconditionally; at buyer request it may provide equivalent-value exchange; if buyer refuses exchange, refund the paid amount including applicable taxes.
- **Public evidence:** return/refund policy and self-service/customer-service path.
- **Internal evidence:** return reason codes, refund calculation including taxes, exchange workflow.
- **Decision:** a blanket `no returns/no refunds` policy that conflicts with this statutory mismatch right is a strong `FAIL` signal.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED` under this section itself; role-specific Sections 14–16 may create additional offence mappings.
- **Remediation:** create a statutory-mismatch return path that cannot be overridden by merchant policy.

### NP-ECA-011-01 — Import/export legal controls where applicable

- **Legal basis:** Section 11
- **Applies when:** importing from foreign e-commerce businesses or exporting from a Nepal-operated electronic platform.
- **Requirement:** comply with prevailing federal laws; exports under the stated scenario require payment through the banking system in accordance with the mutual contract.
- **Evidence:** shipping countries, currency/payment configuration, trade/export process records.
- **Decision:** normally `MANUAL_VERIFICATION` unless implementation evidence clearly establishes controls.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** route cross-border transactions through applicable trade/payment compliance controls.

---

# E. Personal information and account controls

### NP-ECA-012-01 — Personal information confidentiality and lawful use/disclosure

- **Legal basis:** Section 12(1)-(2), with transaction-information proviso
- **Requirement:** maintain confidentiality of personal/identifying information; do not disclose or use it except as permitted by prevailing law; necessary transaction information exchange among buyer, business entity, and delivery service provider is not impeded.
- **Public evidence:** privacy notice is supportive but does not prove practice.
- **Internal evidence:** access control, data flows, third-party sharing, logging, secrets handling, data minimization, delivery-provider integration.
- **Decision:** privacy policy only → usually `MANUAL_VERIFICATION` or `PARTIAL`, not automatic `PASS`.
- **Severity:** Critical.
- **Penalty:** Section 12(4) says contravention of subsection (2) is punishable under prevailing law; exact penalty is `OTHER/UNMAPPED` here.
- **Remediation:** restrict use/disclosure to lawful purposes and transaction-necessary sharing; document and enforce access boundaries.

### NP-ECA-012-02 — User can access/modify personal information and deactivate identity-related sources

- **Legal basis:** Section 12(3)
- **Requirement:** business must not deprive a user of the facility to access the platform, enter or modify personal information, or deactivate identity-related sources.
- **Public evidence:** account/profile editing and deactivation controls where applicable.
- **Internal evidence:** account settings routes, APIs, authorization rules.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** provide accessible account/profile controls consistent with the Act.

---

# F. Licensed/restricted commerce

### NP-ECA-013-01 — Required license/conditions satisfied before sale

- **Legal basis:** Section 13(1)-(2)
- **Requirement:** where separate license, conditions, or procedures are legally required for a category, do not sell/transact without satisfying them.
- **Evidence:** product categories, seller onboarding, license fields/verification, restricted-category rules.
- **Decision:** requires category-specific current-law verification.
- **Severity:** Critical.
- **Penalty:** action under prevailing federal law; `OTHER/UNMAPPED` here.
- **Remediation:** create category gates that require verified licenses/conditions before publication/sale.

---

# G. Intermediary marketplace duties

Apply this section when discovery identifies an **Intermediary Business Entity**.

### NP-ECA-014-01 — Accurate accessible listing information; only listed goods/services traded

- **Legal basis:** Section 14(a), linked to Section 6
- **Requirement:** clearly and accurately present Section 6 details and trade only goods/services as mentioned on the platform.
- **Evidence:** listing UI plus product/seller data integrity controls.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** validate required listing data and prevent order/fulfillment substitution that breaks the listing representation.

### NP-ECA-014-02 — Transaction records retained for tax-law period

- **Legal basis:** Section 14(b)
- **Requirement:** maintain purchase/sale transaction records for the period prescribed by prevailing taxation laws based on transaction nature.
- **Evidence:** data-retention policy, database lifecycle, archive records.
- **Decision:** `MANUAL_VERIFICATION` without internal evidence.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** implement retention controls tied to applicable tax requirements; do not guess the retention period in this rule pack.

### NP-ECA-014-03 — Warranty/guarantee honored for stated duration

- **Legal basis:** Section 14(c)
- **Evidence:** warranty workflow, support cases, policy and order/product warranty snapshots.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** persist warranty terms at purchase and support claims for the promised duration.

### NP-ECA-014-04 — No undisclosed preferential treatment among comparable sellers

- **Legal basis:** Section 14(d)
- **Requirement:** do not discriminate among same-category goods/services from different sellers or preferentially treat a seller; if special preference is given, clearly indicate it accessibly to buyers.
- **Public evidence:** sponsored/featured labels, ranking explanations where present.
- **Internal evidence:** ranking code/config, sponsorship flags, merchandising rules.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** disclose preferential treatment and make ranking/sponsorship state explicit in the product/listing model.

### NP-ECA-014-05 — Seller agreement exists before listing

- **Legal basis:** Section 14(e)
- **Requirement:** enter into an agreement with the seller before listing the seller's goods/services.
- **Evidence:** seller onboarding contract acceptance/version/timestamp.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** gate seller publication on executed agreement evidence.

### NP-ECA-014-06 — Intermediary accepts statutory return/exchange/refund

- **Legal basis:** Section 14(f)
- **Requirement:** accept return, exchange, or refund of goods/services provided/facilitated by the intermediary when buyer is entitled under prevailing law, notwithstanding contract terms.
- **Evidence:** marketplace policy, support workflow, returns/refund logic; look for unlawful disclaimers shifting all responsibility to sellers.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** implement platform-level statutory redress that contract terms cannot disable.

---

# H. List-based / first-party e-commerce duties

Apply when discovery identifies a **List-Based Electronic Commerce Business Entity**.

### NP-ECA-015-01 — Section 6 details clear and accessible

- **Legal basis:** Section 15(a)
- **Requirement:** display Section 6 details clearly/accessibly.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** use the Section 6 disclosure matrix and enforce publish-time validation.

### NP-ECA-015-02 — Required legal information/notices published

- **Legal basis:** Section 15(b)
- **Requirement:** publish platform information/notices required under prevailing laws.
- **Evidence:** applicable notices and category-specific disclosure requirements.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** maintain a sourced registry of required notices; do not invent notices from general practice.

### NP-ECA-015-03 — No fake/fictitious consumer reviews

- **Legal basis:** Section 15(c)
- **Requirement:** do not post/cause reviews, ratings, or feedback by impersonating oneself/another as a fictitious consumer.
- **Evidence:** review provenance, moderation/admin behavior, seeded reviews, code/data indicators.
- **Decision:** absence of proof is not proof of compliance; browser-only audits often require `MANUAL_VERIFICATION`.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** prohibit synthetic merchant reviews; preserve reviewer/order provenance and moderation audit trails.

### NP-ECA-015-04 — Advertising is not misleading

- **Legal basis:** Section 15(d)
- **Requirement:** do not misrepresent actual features, usage methods, or other details to deceive buyers/consumers.
- **Evidence:** compare advertisements, listing copy, product facts, imagery/claims, underlying source data.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** make claims traceable to product/service source data and review high-risk claims before publication.

### NP-ECA-015-05 — Transaction records retained for tax-law period

- **Legal basis:** Section 15(e)
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Decision/remediation:** same evidence discipline as NP-ECA-014-02.

### NP-ECA-015-06 — Delivery within predetermined timeframe except force majeure

- **Legal basis:** Section 15(f)
- **Requirement:** deliver sold goods/provide service within predetermined timeframe except force majeure.
- **Evidence:** promised vs actual timestamps, SLA logic, order records.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** persist promised fulfillment time and monitor breach/exceptions.

### NP-ECA-015-07 — Warranty/guarantee conditions honored

- **Legal basis:** Section 15(g)
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** implement claim handling against the warranty/guarantee actually offered.

### NP-ECA-015-08 — Return/cancel/discontinue and refund for mismatch, late delivery, or defect

- **Legal basis:** Section 15(h)
- **Requirement:** accept return/cancellation/discontinuation and refund when goods/services do not conform to display/agreement, are delivered later than predetermined time, or are defective.
- **Evidence:** policy + operational flow + refund calculation.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** encode these statutory reason codes as non-overridable redress paths.

### NP-ECA-015-09 — Authenticity commitment carries liability

- **Legal basis:** Section 15(i)
- **Applies when:** a formal commitment regarding authenticity has been made.
- **Requirement:** business bears liability when authenticity is questioned under such a commitment.
- **Evidence:** authenticity promises, certificates, guarantee language, resolution workflow.
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** make authenticity claims evidence-backed and provide a claim-resolution process.

---

# I. Seller duties on an intermediary platform

Apply when auditing a **Seller** or marketplace seller-onboarding controls.

### NP-ECA-016-01 — Seller agreement before offering goods/services

- **Legal basis:** Section 16(a)
- **Requirement:** seller enters written/electronic contract with intermediary before making goods/services available.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** block listing activation until agreement execution is recorded.

### NP-ECA-016-02 — Seller provides required business/grievance/refund/tax documents

- **Legal basis:** Section 16(b)
- **Requirement:** provide intermediary with business registration evidence, relevant documents, full name/address, grievance mechanism, exchange/return/refund details, and PAN/VAT details.
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Evidence:** seller onboarding fields/documents and verification state.
- **Remediation:** model these as mandatory onboarding requirements without fabricating values.

### NP-ECA-016-03 — Seller supplies Section 6 information for each offering

- **Legal basis:** Section 16(c)
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Remediation:** require Section 6 structured fields before seller listing publication.

### NP-ECA-016-04 — Seller delivers within predetermined time except force majeure

- **Legal basis:** Section 16(d)
- **Severity:** High.
- **Penalty:** `ACT-S22` via Section 21(d).
- **Evidence/remediation:** promised vs actual fulfillment records and SLA enforcement.

### NP-ECA-016-05 — Seller does not engage in unfair trade practices

- **Legal basis:** Section 16(e)
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** seller policy, monitoring, enforcement, and evidence trails for unfair-practice controls.

### NP-ECA-016-06 — Seller does not create fictitious-consumer reviews

- **Legal basis:** Section 16(f)
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** verified review provenance and seller/admin restrictions.

### NP-ECA-016-07 — Seller accepts return/cancel/discontinue and refunds mismatch/late/defect cases

- **Legal basis:** Section 16(g)
- **Severity:** Critical.
- **Penalty:** `ACT-S23` via Section 21(e).
- **Remediation:** marketplace seller policy and platform enforcement must support statutory redress.

---

# J. Delivery, unfair trade, and platform responsibility

### NP-ECA-018-01 — Business entity remains responsible for contracted delivery

- **Legal basis:** Section 18(1)-(4)
- **Requirement:** where contract requires delivery/transfer to buyer-designated person/place/time, delivery liability lies with the business entity; it may separately contract a delivery provider; consumer-protection obligations also apply to delivery provider.
- **Public evidence:** terms must not improperly disclaim all delivery responsibility merely because a courier is used.
- **Internal evidence:** courier contracts/integration and incident ownership.
- **Severity:** High.
- **Penalty:** delivery-provider contrary acts are punishable under prevailing consumer-protection law; `OTHER/UNMAPPED` here.
- **Remediation:** keep platform/business ownership of delivery obligations and define courier escalation.

### NP-ECA-019-01 — No unfair trade/commercial practices

- **Legal basis:** Section 19
- **Requirement:** seller, business entity, or other party must not engage/cause unfair trade or commercial practice as defined by prevailing laws.
- **Evidence:** pricing/claims/dark-pattern-like conduct may trigger review, but the prevailing-law definition must be sourced before declaring a legal violation.
- **Severity:** High.
- **Penalty:** action under prevailing laws; `OTHER/UNMAPPED`.
- **Remediation:** map any suspected practice to the controlling consumer law before labeling it a statutory failure.

### NP-ECA-020-01 — Platform cannot escape complaint/grievance duty by blaming manufacturer/importer/seller

- **Legal basis:** Section 20
- **Applies to:** business entity operating the electronic platform.
- **Requirement:** when a complaint under Section 28 or grievance under Section 33 concerns goods/services provided/sold through the platform, the business entity is not exempt merely because it did not manufacture, import, or directly make them available.
- **Public evidence:** marketplace support/returns terms and complaint flow.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** remove blanket `contact seller/manufacturer only` disclaimers where they defeat platform grievance obligations.

---

# K. Monitoring, standards, and grievance management

### NP-ECA-027-01 — Monitoring/inspection instruction readiness

- **Legal basis:** Section 27
- **Requirement:** Department monitors/inspects e-commerce; if defects are found, competent authority may give necessary instructions and business entity must comply.
- **Evidence:** compliance ownership, issue tracking, regulator instruction records.
- **Decision:** normally process/manual evidence.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** retain auditable compliance records and an owner/process for regulator instructions.

### NP-ECA-030-01 — Applicable IT regulatory standards followed

- **Legal basis:** Section 30
- **Requirement:** follow standards prescribed by Government of Nepal's IT regulatory authority for improvement/upgrading of electronic platforms under prevailing law.
- **Decision:** do not invent standards. Verify current prescribed standards before scoring this as `FAIL` or `PASS`.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** add the verified applicable standards as a sourced sub-pack when identified.

### NP-ECA-031-01 — Consumer-protection-law dependency disclosed

- **Legal basis:** Section 31
- **Requirement context:** quality, labeling, return grounds/procedure, pricing, inspection/monitoring, dispute resolution, compensation, and consumer rights are governed by prevailing consumer-protection law unless otherwise stated in the Act.
- **Audit behavior:** this is a scope-control rule, not a standalone website PASS. If those subjects are material, flag the need for a Consumer Protection Act/Regulation audit.
- **Severity:** Medium.
- **Penalty:** `OTHER/UNMAPPED`.

### NP-ECA-032-01 — Government/sector regulator instructions complied with

- **Legal basis:** Section 32
- **Requirement:** business entity must comply with necessary instructions issued by Department or applicable separate regulator under the section.
- **Evidence:** regulator correspondence, action records.
- **Decision:** `MANUAL_VERIFICATION` unless such records are available.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.

### NP-ECA-033-01 — Grievance channels available

- **Legal basis:** Section 33(1), read with Section 4(2)(h)
- **Requirement:** buyer/consumer may lodge grievance electronically, in writing, or in person to the responsible person/unit; public business disclosure includes grievance contact details.
- **Public evidence:** complaint/grievance form/email/contact plus responsible unit information.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** provide an online grievance path and publish the responsible contact/unit.

### NP-ECA-033-02 — Complaint registered and acknowledgement/information provided immediately

- **Legal basis:** Section 33(2)
- **Evidence:** grievance ticket creation, acknowledgement behavior, timestamps.
- **Decision:** browser test only when authorized and using safe/staging data; otherwise inspect implementation.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** create a durable complaint record and immediate acknowledgement containing a reference/status channel.

### NP-ECA-033-03 — Complaint investigated and decided within 15 days

- **Legal basis:** Section 33(3)
- **Evidence:** ticket lifecycle timestamps, SLA jobs/dashboards, historical samples.
- **Decision:** `MANUAL_VERIFICATION` without operational records.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** implement 15-day grievance SLA tracking and escalation.

### NP-ECA-033-04 — Written outcome/reason provided within 15 days

- **Legal basis:** Section 33(5)
- **Requirement:** responsible grievance handler provides written information within 15 days whether complaint can be addressed; if not, provide written information with reason.
- **Evidence:** notification templates + historical ticket timestamps/content.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** require a written resolution or reasoned non-resolution outcome before SLA closure.

### NP-ECA-033-05 — Online grievance redress mechanism implemented

- **Legal basis:** Section 33(6)
- **Requirement:** business entity develops and implements an online grievance-redress mechanism.
- **Public evidence:** functioning online grievance/contact/ticket path.
- **Internal evidence:** persistence, routing, status, acknowledgement, SLA/resolution logic.
- **Severity:** High.
- **Penalty:** `OTHER/UNMAPPED`.
- **Remediation:** implement a real tracked grievance mechanism, not only static policy text.

---

# L. Audit notes from remaining provisions

- **Section 17 (buyer liabilities):** relevant to contract/user behavior but generally not a platform compliance requirement; do not score the business for buyer conduct.
- **Section 28 (filing complaints with Director General/Inspection Officer):** any person with information/evidence may complain, including electronically; complainant identity may be confidential on request. Use this as enforcement context, not a requirement to build the Department's complaint mechanism into the merchant site.
- **Section 29 (coordination):** government coordination requirement, not merchant checklist item.
- **Section 34:** e-commerce carried out by employee/worker/representative on behalf of business entity is deemed conducted by the business entity. Do not treat employee action as automatically outside business responsibility.
- **Section 35:** possible government discounts/facilities/concessions for qualifying micro/small/cottage industries; not a baseline compliance requirement.
- **Section 36:** prosecution under other prevailing law is not barred when conduct is also an offence elsewhere. The audit must not imply this Act is the only applicable law.
- **Sections 37–38:** directive-making and statutory implementation assessment provisions; not direct storefront checklist items.

---

# Recommended Nepal report categories

1. Legal eligibility & platform identity
2. Department listing
3. Product/service transparency
4. Contract & checkout
5. Payment/invoice
6. Delivery
7. Returns/refunds
8. Privacy/account controls
9. Licensed/restricted commerce
10. Marketplace/intermediary duties
11. First-party/list-based duties
12. Seller controls
13. Grievance redress
14. Monitoring/standards/manual verification
15. Related-law gaps and current-source freshness

Always surface `ACT-S23` failures first, then `ACT-S22`, then other Critical/High findings.
