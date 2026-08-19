# Nepal E-Commerce Rule Pack

## Implemented legal sources

This pack currently implements auditable requirements from:

1. Nepal's **Electronic Commerce Act, 2081 (2025)** — fully mapped from the Act text into stable `NP-ECA-*` audit rules.
2. Nepal's **Electronic Commerce (E-Commerce) Directive, 2082** — implemented as a verified-interim operational mapping using stable `NP-ECD-2082-*` rule IDs.

### Act source metadata

- Title: Electronic Commerce Act, 2081 (2025)
- Act No.: 13 of the Year 2081 (2025)
- Assent/publication: 2081.12.03 / March 16, 2025
- Commencement: 31st day after assent
- Geographic scope: Nepal, including a person residing or staying outside Nepal who provides goods or services within Nepal through e-commerce
- Responsible department named by the Act: Department of Commerce, Supplies and Consumer Protection

Official Department source page:

- https://doc.gov.np/content/324/electronic-business--e-commerce--act--2081/

### Directive source metadata and verification status

The Ministry of Industry, Commerce and Supplies and the Department of Commerce, Supplies and Consumer Protection publish the **Electronic Commerce (E-Commerce) Directive, 2082**.

Official publication pages:

- Ministry: https://moics.gov.np/content/13547/electronic-business--e-commerce--directory--2082/
- Department: https://doc.gov.np/content/338/electronic-business--e-commerce--directory--2082/

The Directive is mapped in `ecommerce-directive-2082.md` as a **verified-interim operational rule pack**. The government publication pages confirm the Directive, but the full attached Directive text was not machine-readable in the repository-maintenance environment used for the first mapping. For that reason:

- the pack does not invent Directive section/clause numbers;
- requirements that cannot yet be tied to a directly reviewed official clause are labeled accordingly;
- explicit Act penalties remain separately traceable to the Act;
- uncertain or access-dependent requirements use `MANUAL_VERIFICATION` rather than unsupported `FAIL` findings.

Until the complete official Directive attachment has been reviewed clause by clause, reports using this pack should identify their source status as:

> Nepal Electronic Commerce Act 2081 + Directive 2082 operational audit — Directive clause-level source verification remains pending for interim Directive rules.

This is still more complete than an Act-only audit, but it must not be represented as regulator certification or as a complete audit of every Nepal consumer, tax, privacy, payment, cyber, or sector-specific law.

## Business-role model used by this pack

The Act distinguishes several roles that matter for audit applicability:

- **Business Entity** — either an intermediary business entity or a list-based e-commerce business entity.
- **Intermediary Business Entity** — facilitates sale of a seller's goods/services to a buyer through an electronic platform.
- **List-Based E-Commerce Business Entity** — owns the goods/services it lists and sells them directly to consumers through an electronic platform.
- **Seller** — provides goods/services for sale to an intermediary business entity; the Act's definition also includes a list-based e-commerce business entity in relevant context.
- **Delivery Service Provider** — transports goods for a business.
- **Buyer/Consumer** — purchaser/user of goods or services.

The discovery interview must identify the actual role(s) before applying role-specific checks.

## Electronic platform scope

The Act defines an electronic platform broadly enough to include systems using websites, applications, software, internet/intranet, or social-media marketplaces on electronic devices. E-commerce is the buying or selling of goods/services through such a platform. Merely using an electronic platform to provide information about or promote goods/services is excluded from the Act's e-commerce definition.

## Penalty mapping used by the auditor

Do not infer penalties from severity labels. The Act rule file uses the Act's explicit offence mapping:

- **Section 22 tier** — offences under Section 21(a), (b), (c), or (d): inspection-officer fine of NPR 20,000 to NPR 100,000 depending on gravity.
- **Section 23 tier** — offence under Section 21(e): NPR 50,000 to NPR 500,000, or imprisonment from 6 months to 3 years, or both, depending on gravity.

The Directive may add procedures, timelines, monitoring expectations, and operational duties. Do not turn those into a new monetary or imprisonment penalty unless an authoritative source expressly supports it. Where a Directive requirement also violates an Act offence provision, report the Act consequence through the corresponding `NP-ECA-*` rule.

## Related-law boundary

Section 31 of the Act states that, unless otherwise provided in the Act, matters including quality, labeling, return grounds/procedure, pricing, inspection/monitoring, dispute resolution, compensation, and consumer rights are governed by prevailing consumer-protection law and apply to electronically traded goods/services.

The Nepal pack therefore is **not a complete Nepal consumer-law or technology-law audit**. Additional country modules may later cover Consumer Protection law, payment regulation, tax law, privacy/data protection, cybersecurity, sector licensing, and other prevailing laws as separate sourced rule packs.

## Audit load order

When Nepal is in scope, load these files in order:

1. `rules/nepal/README.md`
2. `rules/nepal/ecommerce-act-2081.md`
3. `rules/nepal/ecommerce-directive-2082.md`

Keep Act and Directive findings separately traceable in the final report.
