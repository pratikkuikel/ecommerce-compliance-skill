# Nepal E-Commerce Rule Pack

## Implemented baseline

This pack currently implements auditable requirements from Nepal's **Electronic Commerce Act, 2081 (2025)**.

Source metadata used for the Act baseline:

- Title: Electronic Commerce Act, 2081 (2025)
- Act No.: 13 of the Year 2081 (2025)
- Assent/publication: 2081.12.03 / March 16, 2025
- Commencement: 31st day after assent
- Geographic scope: Nepal, including a person residing or staying outside Nepal who provides goods or services within Nepal through e-commerce
- Responsible department named by the Act: Department of Commerce, Supplies and Consumer Protection

Official Department source page:

- https://doc.gov.np/content/324/electronic-business--e-commerce--act--2081/

## Important current-law freshness warning

The Department of Commerce, Supplies and Consumer Protection has published **Electronic Commerce (E-Commerce) Directive, 2082**.

Official Department source page:

- https://doc.gov.np/content/338/electronic-business--e-commerce--directory--2082/

The Department also operates e-commerce listing services and has published notices/manuals relating to electronic-commerce listing.

**Repository status:** the operative text of the Directive, 2082 has not yet been fully mapped into this rule pack. Therefore an audit using only `ecommerce-act-2081.md` must be labeled:

> Act 2081 baseline audit — current Nepal implementation directives may add or clarify requirements.

Do not call an Act-only result `fully compliant with all current Nepal e-commerce law` until the Directive and any other applicable current instruments have been incorporated and reviewed.

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

Do not infer penalties from severity labels. The implemented rule file uses the Act's explicit offence mapping:

- **Section 22 tier** — offences under Section 21(a), (b), (c), or (d): inspection-officer fine of NPR 20,000 to NPR 100,000 depending on gravity.
- **Section 23 tier** — offence under Section 21(e): NPR 50,000 to NPR 500,000, or imprisonment from 6 months to 3 years, or both, depending on gravity.

Other duties may be enforceable through other provisions or prevailing laws. Unless a direct penalty mapping is present in the source, report the duty without inventing a penalty.

## Related-law boundary

Section 31 of the Act states that, unless otherwise provided in the Act, matters including quality, labeling, return grounds/procedure, pricing, inspection/monitoring, dispute resolution, compensation, and consumer rights are governed by prevailing consumer-protection law and apply to electronically traded goods/services.

This means the current pack is **not a complete Nepal consumer-law audit**. A future Nepal pack can add Consumer Protection Act/Regulation checks as separate sourced rules.

## Audit file

Load `ecommerce-act-2081.md` after this README.
