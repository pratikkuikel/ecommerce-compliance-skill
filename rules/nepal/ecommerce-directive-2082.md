# Nepal — Electronic Commerce (E-Commerce) Directive, 2082 Audit Rules

Rule-pack ID: `NP-ECD-2082`

Use this file only after reading `rules/nepal/README.md`, loading `ecommerce-act-2081.md`, and completing the mandatory 10-question discovery interview in `SKILL.md`.

## Source and verification status

The Ministry of Industry, Commerce and Supplies and the Department of Commerce, Supplies and Consumer Protection both publish official pages for the **Electronic Commerce (E-Commerce) Directive, 2082**.

Official publication pages:

- Ministry: https://moics.gov.np/content/13547/electronic-business--e-commerce--directory--2082/
- Department: https://doc.gov.np/content/338/electronic-business--e-commerce--directory--2082/

The Ministry publication page identifies the Directive and shows a publication date of 17 Falgun 2082. The Department also publishes the Directive in its current resources.

### Verification limitation

In the repository-maintenance environment used for this mapping, the government content pages exposed the publication metadata but did not expose the full attached Directive text in a machine-readable form. Therefore this file is a **verified-interim operational mapping** rather than a claim that every clause of the official attachment has been line-by-line transcribed.

The rules below are limited to operative requirements that were corroborated after final release by multiple sources reporting the issued Directive, including requirements also consistent with Department listing materials. Do **not** invent a Directive section number where the official attachment has not been directly verified.

When an agent reports these rules, it must identify the legal basis as `Electronic Commerce (E-Commerce) Directive, 2082 — operative requirement; exact clause pending official-attachment verification` unless a clause number has subsequently been verified in the repository.

This limitation affects citation precision, not the existence of the Directive itself.

## Penalty discipline

The Directive adds implementation, monitoring, and enforcement procedures around the Act. Do not create a new monetary or imprisonment penalty merely from a Directive rule. Where conduct also maps to an offence under the Electronic Commerce Act, 2081, report the Act penalty separately through the corresponding `NP-ECA-*` rule.

---

# A. Department listing and registration operations

### NP-ECD-2082-LIST-01 — Department portal listing is mandatory

- **Applies to:** businesses conducting electronic commerce in Nepal, subject to the Act and Directive.
- **Requirement:** the e-commerce business must be listed through the Department of Commerce, Supplies and Consumer Protection's electronic-commerce listing system and obtain a listing number.
- **Public evidence:** displayed Department listing number; official portal result when verifiable.
- **Internal/manual evidence:** listing application, approval/confirmation, current Department record.
- **Decision:** confirmed absence of required listing → `FAIL`; inability to validate listing authenticity → `MANUAL_VERIFICATION`.
- **Severity:** High.
- **Act relationship:** reinforces `NP-ECA-005-01` and the Section 21(b)/Section 22 offence mapping for operating without required listing.
- **Remediation:** complete Department listing and display the issued listing number with the business disclosures required by the Act.

### NP-ECD-2082-LIST-02 — Listing information must be updated within seven days after relevant changes

- **Requirement:** after listing, changed business details and new outlet/branch information must be updated through the Department system within seven days.
- **Evidence:** Department portal history, internal master-data change timestamps, compliance workflow records.
- **Decision:** normally `MANUAL_VERIFICATION` without official or internal evidence.
- **Severity:** Medium.
- **Act relationship:** operationalizes and broadens the evidence expectations around Act Section 5 updates.
- **Remediation:** trigger a seven-day compliance task whenever business identity, ownership/business nature, or outlet/branch master data changes.

### NP-ECD-2082-LIST-03 — Existing platforms must satisfy the Directive transition listing requirement

- **Applies when:** the business was already operating when the Directive took effect.
- **Requirement:** existing e-commerce businesses were given a transition period to complete Department portal listing; post-release reporting identifies a 35-day transition period.
- **Evidence:** business start date, Directive effective date, listing confirmation date.
- **Decision:** if the business predates the Directive and remained unlisted after the transition period, treat as `FAIL`; otherwise `MANUAL_VERIFICATION` when dates cannot be established.
- **Severity:** High.
- **Remediation:** verify historical listing timing and immediately complete current listing if still outstanding.

### NP-ECD-2082-LIST-04 — Listing/update/cancellation service is not conditioned on a Department service fee, but tax obligations must be current

- **Requirement:** Department listing, update, and cancellation services are reported as free; the business must satisfy applicable tax obligations before receiving the service.
- **Evidence:** tax-clearance/compliance records where required; Department service records.
- **Decision:** tax compliance is generally `MANUAL_VERIFICATION`; do not treat a website tax number alone as proof.
- **Severity:** Medium.
- **Remediation:** maintain tax-compliance evidence and do not build merchant workflows that assume a Department listing fee.

---

# B. Payment, invoicing, charges, and refunds

### NP-ECD-2082-PAY-01 — Use only Nepal Rastra Bank-approved digital payment gateways for regulated digital payment flows

- **Requirement:** e-commerce business transactions using digital payment gateways must use gateways/payment systems approved or licensed by Nepal Rastra Bank as required by the Directive and prevailing payment law.
- **Public evidence:** checkout payment methods and named payment providers.
- **Internal evidence:** payment provider configuration, merchant accounts, gateway integration credentials/configuration, settlement flow.
- **Decision:** an obviously unlicensed/unapproved gateway used for covered transactions → `FAIL`; provider status uncertainty → `MANUAL_VERIFICATION` and current-law research.
- **Severity:** High.
- **Remediation:** restrict payment integrations to currently authorized providers and maintain a provider-approval verification record.

### NP-ECD-2082-PAY-02 — Electronic invoice is mandatory, including cash-payment commerce

- **Requirement:** issue an electronic invoice for e-commerce transactions; post-release reporting specifically confirms that cash payment does not remove the electronic-invoice requirement.
- **Public evidence:** order confirmation/invoice UX where safely testable.
- **Internal evidence:** invoice generation rules for prepaid, online-paid, COD/cash, refund, and cancellation states.
- **Decision:** cash/COD path with no electronic invoice capability → `FAIL`; browser-only inability to complete a transaction → `MANUAL_VERIFICATION`.
- **Severity:** High.
- **Act relationship:** supplements `NP-ECA-008-01`.
- **Remediation:** generate and retain a compliant electronic invoice independent of payment method.

### NP-ECD-2082-PAY-03 — Failed payment must be refunded within seven days

- **Requirement:** where an e-commerce payment fails but customer funds require reversal/refund, the business must arrange the refund within seven days.
- **Evidence:** payment/refund event logs, support tickets, payment-provider records, refund SLA configuration.
- **Decision:** normally requires internal/transaction evidence; policy text alone is not proof of actual timing.
- **Severity:** High.
- **Remediation:** automate failed-payment reconciliation, alert before SLA breach, and record refund completion timestamps.

### NP-ECD-2082-PAY-04 — Avoid undisclosed or impermissible payment-related extra charges

- **Requirement:** do not impose payment-related amounts beyond the disclosed price and applicable delivery/transfer cost where the Directive prohibits additional charges; the total payable amount must remain transparent.
- **Public evidence:** product page, cart, checkout, payment-method surcharge behavior.
- **Decision:** a hidden or newly introduced fee at payment without lawful/disclosed basis → `FAIL` or `PARTIAL` depending on scope.
- **Severity:** High.
- **Act relationship:** complements the Act's final-price and additional-delivery-charge disclosures.
- **Remediation:** centralize fee calculation, show all lawful charges before contract conclusion, and remove payment-method surprise fees.

---

# C. Privacy, cybersecurity, and incident response

### NP-ECD-2082-DATA-01 — Sensitive user information must be stored securely in encrypted form

- **Requirement:** sensitive personal/authentication information used by the e-commerce platform, including examples reported such as passwords, phone/mobile numbers, address, date of birth, and similar verification information, must be protected with encryption/security controls appropriate to the Directive.
- **Public evidence:** privacy/security representations are only supporting evidence.
- **Internal evidence:** password hashing implementation, encryption-at-rest/application-layer protections where applicable, key management, database schema/configuration, secrets handling.
- **Decision:** never mark `PASS` from a privacy policy alone. Plain-text password storage or clearly unprotected sensitive data → `FAIL`.
- **Severity:** Critical.
- **Act relationship:** strengthens `NP-ECA-012-01`.
- **Remediation:** hash passwords with an appropriate password-hashing scheme; encrypt sensitive data where required; separate keys/secrets; restrict access; test backup and log exposure.

### NP-ECD-2082-DATA-02 — Prevent unauthorized access, misuse, and leakage with technical and organizational controls

- **Requirement:** implement appropriate technical and managerial safeguards against unauthorized access, misuse, or leakage of user information.
- **Internal evidence:** authentication/authorization design, least privilege, audit logging, access reviews, security testing, incident response, vendor controls.
- **Decision:** code/repository access can support a deeper finding; a public audit will usually be `MANUAL_VERIFICATION`.
- **Severity:** Critical.
- **Remediation:** implement layered access control, logging, monitoring, security testing, and documented data-handling responsibilities.

### NP-ECD-2082-DATA-03 — Suspend affected commerce after serious data/system incident and resume after recovery

- **Requirement:** when unauthorized access, user-information leakage, or a material platform malfunction occurs, the business must stop affected transactions/operations as required, perform recovery/remediation, and resume only after the problem is resolved; post-release reporting also identifies notification/public-information duties around such incidents.
- **Internal evidence:** incident response plan, kill switch/maintenance capability, incident timeline, customer/regulator notification process, recovery validation.
- **Decision:** typically `MANUAL_VERIFICATION`; absence of any incident response/transaction suspension mechanism in a platform code audit → `PARTIAL` or `FAIL` depending on risk.
- **Severity:** Critical.
- **Remediation:** create an incident runbook with authority to suspend commerce, regulator/public communication steps, recovery criteria, and auditable restart approval.

---

# D. Advertising and consumer-facing conduct

### NP-ECD-2082-ADS-01 — Misleading or exaggerated advertising is prohibited

- **Requirement:** the platform/business must not publish misleading or exaggerated advertising about goods or services.
- **Public evidence:** ads, landing pages, product pages, claims, comparison statements, promotional banners.
- **Decision:** concrete materially misleading claim → `FAIL`; subjective marketing language without a factual deception should not be over-penalized.
- **Severity:** High.
- **Act relationship:** complements unfair-trade and misleading-presentation duties under the Act.
- **Remediation:** require substantiation for objective claims and maintain merchant/content moderation controls.

---

# E. Complaints and dispute resolution

### NP-ECD-2082-GRV-01 — Platform must provide an online grievance mechanism

- **Requirement:** each e-commerce platform/business must provide an online mechanism for consumers to lodge and manage complaints/grievances.
- **Public evidence:** complaint form, account grievance workflow, support ticket portal, grievance contact path.
- **Internal evidence:** ticket schema, status workflow, timestamps, escalation rules.
- **Decision:** no functional online grievance path → `FAIL`.
- **Severity:** High.
- **Act relationship:** supplements Act Section 33 and `NP-ECA-033-*` rules.
- **Remediation:** provide a persistent online complaint channel with case ID, acknowledgement, status, and resolution record.

### NP-ECD-2082-GRV-02 — Consumer complaints must be handled within the Act/Directive grievance timeline

- **Requirement:** complaint handling must align with the statutory 15-day business grievance decision/communication period.
- **Evidence:** ticket timestamps, SLA configuration, response logs.
- **Decision:** actual cases exceeding the required period without lawful basis → `FAIL`; public policy promising a longer period → strong `FAIL`/`PARTIAL` signal.
- **Severity:** High.
- **Act relationship:** use Act Section 33 as the primary explicit 15-day legal basis.
- **Remediation:** set 15-day maximum SLA with internal earlier warning/escalation thresholds.

### NP-ECD-2082-GRV-03 — Unresolved disputes can escalate to Department dispute resolution

- **Requirement:** the business grievance process must not block a consumer from escalating unresolved matters to the Department; the Directive provides for an e-commerce dispute-resolution mechanism/committee at Department level.
- **Public evidence:** grievance/terms language that preserves regulatory complaint rights.
- **Internal evidence:** escalation scripts, support playbooks, complaint closure reasons.
- **Decision:** terms falsely claiming the merchant's decision is final or waiving Department complaint rights → `FAIL`.
- **Severity:** Medium.
- **Remediation:** preserve external complaint/escalation rights and train support staff accordingly.

---

# F. Recordkeeping and inspection readiness

### NP-ECD-2082-REC-01 — Preserve e-commerce transaction and invoice records for five years

- **Requirement:** post-release reporting of the final Directive confirms a five-year retention requirement for transaction records and invoices; complaint and inspection-related records are also reported within the retention framework.
- **Internal evidence:** retention policy, database lifecycle, archive configuration, immutable invoice storage, deletion jobs.
- **Decision:** browser-only audit → `MANUAL_VERIFICATION`; configured deletion before five years for covered records → `FAIL`.
- **Severity:** High.
- **Remediation:** implement at least the Directive retention period for covered records, with legal-hold capability where other law requires longer retention.

### NP-ECD-2082-MON-01 — Business must provide records and documents during Department inspection/monitoring

- **Requirement:** the Department may deploy inspection officers and relevant subject-matter experts for e-commerce monitoring; the business must make necessary documents, details, and records available during lawful inspection.
- **Internal/manual evidence:** audit export, document register, transaction/invoice archives, complaint records, security documentation, responsible owner.
- **Decision:** typically `MANUAL_VERIFICATION`; absence of a practical export/retrieval path can be `PARTIAL` in a deep code/admin audit.
- **Severity:** Medium.
- **Remediation:** create an inspection-readiness export/index covering business identity, listing, catalog, orders, invoices, delivery/returns, complaints, privacy/security, and relevant audit logs.

### NP-ECD-2082-MON-02 — Audit the platform against cybersecurity, labeling, delivery/return, and personal-data controls

- **Requirement:** the Directive's monitoring framework specifically covers whether the platform follows legal requirements, whether goods/services correspond to their platform labels/descriptions, whether delivery and return arrangements are implemented, whether cybersecurity practices are used, and whether consumer personal information is protected from unauthorized use.
- **Evidence:** combine public and internal evidence; do not collapse these topics into one binary website check.
- **Decision:** report the underlying rule findings individually and use this rule as inspection-readiness coverage.
- **Severity:** Medium.
- **Remediation:** maintain an evidence index linking each inspected domain to controls, logs, responsible owner, and remediation history.

---

# G. Enforcement-facing controls

### NP-ECD-2082-ENF-01 — Unlisted business ordered to list must remediate within the enforcement window

- **Requirement:** post-release reporting states that an unlisted e-commerce business identified through enforcement can be ordered to complete listing within seven days; continued failure can lead to action to terminate/cancel the platform in addition to action under the Act.
- **Evidence:** Department notice/order, listing remediation record, platform status.
- **Decision:** applies only when such an order exists; otherwise `NOT_APPLICABLE`.
- **Severity:** Critical when triggered.
- **Penalty:** do not invent a new monetary penalty; separately report applicable Act Section 21/22 consequences for operating without listing.
- **Remediation:** treat any Department listing order as an immediate legal blocker and complete/verify listing within the stated period.

---

# H. Cross-border operator verification

### NP-ECD-2082-XB-01 — Foreign-registered e-commerce operator serving Nepal requires local-compliance verification

- **Applies when:** an e-commerce company is registered abroad but conducts e-commerce in Nepal.
- **Requirement:** reporting on the Directive identifies a local-representative and Nepal-law compliance obligation for foreign operators. Because the full official attachment clause has not yet been directly verified in this repository, this requirement must be reported as `MANUAL_VERIFICATION` unless current official text is obtained during the audit.
- **Evidence:** Nepal representative appointment, local contact/address, registrations, contracts, tax/legal compliance records.
- **Decision:** do not issue a definitive `FAIL` solely from absence of a public local-representative page until the operative clause is directly verified.
- **Severity:** High.
- **Remediation:** obtain current Nepal counsel/compliance verification and document the local representative and applicable registrations.

---

# Source corroboration notes

The operational requirements in this interim file were cross-checked against post-release reporting dated after the Directive was issued, including:

- Ministry/Department official publication pages confirming the Directive's existence and current publication status.
- Equity Nepal, February 18, 2026: listing, seven-day updates, encrypted data, incident suspension/recovery, payment gateway, electronic invoice, seven-day refund, inspection, tax obligations.
- Nepalitelecom, February 18, 2026: mandatory listing, encryption, additional-fee/misleading-ad controls, seven-day failed-payment refund, electronic invoices, enforcement against persistent non-listing, online grievance mechanism, dispute-resolution committee, 35-day transition statement.
- Other post-release reporting used only to corroborate five-year record retention and enforcement implementation.

Secondary reporting is not used to create imaginary clause numbers or penalties. A future maintenance pass should replace the `exact clause pending official-attachment verification` labels with verified Directive clause references once the official attachment is directly machine-readable or manually reviewed.
