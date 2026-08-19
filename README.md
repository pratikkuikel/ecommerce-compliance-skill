# E-Commerce Compliance Auditor

A portable AI-agent skill for auditing e-commerce websites, platforms, marketplaces, and codebases against jurisdiction-specific commerce rules.

Nepal is the first supported jurisdiction.

## Design principle

There are no `basic` and `advanced` modes.

The skill always begins with a mandatory 10-question discovery interview. From those answers, the agent determines which evidence sources are available and audits as deeply as its environment allows.

Examples:

- Browser/web access only → public storefront and customer-journey audit.
- Browser + GitHub/repository access → public audit plus code/configuration checks.
- Repository + database/API/admin access → deeper implementation and data-model evidence.
- Any missing access → report the requirement as `NOT_OBSERVED` or `MANUAL_VERIFICATION`, never invent evidence.

## What the skill produces

Each finding includes:

- status: `PASS`, `FAIL`, `PARTIAL`, `NOT_OBSERVED`, `NOT_APPLICABLE`, or `MANUAL_VERIFICATION`
- legal/rule reference
- severity and statutory-penalty relevance when known
- observed evidence
- evidence source and confidence
- why the requirement matters
- concrete remediation
- optional implementation guidance when code access is available

The final report is Lighthouse-inspired, but the score is a risk/coverage indicator—not a legal certification.

## Repository structure

```text
.
├── SKILL.md                         # Agent instructions and mandatory workflow
├── README.md
├── CONTRIBUTING.md
├── rules/
│   ├── README.md                    # Country rule-pack contract
│   └── nepal/
│       ├── README.md                # Nepal source hierarchy and scope
│       └── ecommerce-act-2081.md    # Nepal Act audit checks
└── templates/
    └── audit-report.md              # Required report shape
```

## Nepal support

The first rule pack maps the Electronic Commerce Act, 2081 (2025) into auditable checks for:

- business and platform identity disclosures
- Department e-commerce listing
- product/service disclosures
- electronic contracts
- payment receipts and invoices
- delivery commitments
- returns, exchanges, and refunds
- personal-information confidentiality
- licensed/restricted goods and services
- intermediary marketplace duties
- list-based/first-party commerce duties
- seller duties
- transportation/delivery responsibility
- unfair trade practices
- grievance handling
- monitoring and evidence readiness

The Department of Commerce, Supplies and Consumer Protection has also published an E-Commerce Directive, 2082. Until its operative text is incorporated and reviewed in this repository, the skill must not represent an Act-only audit as complete compliance with every current Nepal e-commerce requirement.

## Usage

Ask an AI agent to load `SKILL.md`, then say something like:

> Audit https://example.com for Nepal e-commerce compliance.

The agent must ask all 10 discovery questions before starting the audit.

## Safety and legal positioning

This project is an audit-assistance tool, not a law firm, regulator, certificate, or substitute for legal advice. A `PASS` means the collected evidence supports the specific rule check. It does not mean the business is legally compliant in every respect.

Rules must be traceable to an official or otherwise clearly identified legal source. Contributors should avoid turning assumptions, industry conventions, or model knowledge into legal requirements.
