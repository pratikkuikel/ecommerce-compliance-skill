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
├── SKILL.md                              # Agent instructions and mandatory workflow
├── README.md
├── CONTRIBUTING.md
├── rules/
│   ├── README.md                         # Country rule-pack contract
│   └── nepal/
│       ├── README.md                     # Nepal source hierarchy and scope
│       ├── ecommerce-act-2081.md         # Nepal Act audit checks
│       └── ecommerce-directive-2082.md   # Nepal Directive operational checks
└── templates/
    └── audit-report.md                   # Required report shape
```

## Nepal support

The Nepal pack now combines:

- **Electronic Commerce Act, 2081 (2025)** — detailed clause-level `NP-ECA-*` audit rules.
- **Electronic Commerce (E-Commerce) Directive, 2082** — `NP-ECD-2082-*` operational audit rules covering confirmed implementation requirements while preserving an explicit source-verification boundary for Directive clause numbering.

Together they cover areas including:

- business and platform identity disclosures
- Department e-commerce listing and listing updates
- product/service disclosures
- electronic contracts
- payment gateways, receipts, electronic invoices, and failed-payment refunds
- delivery commitments
- returns, exchanges, and refunds
- personal-information confidentiality and security controls
- incident response and transaction suspension/recovery
- licensed/restricted goods and services
- intermediary marketplace duties
- list-based/first-party commerce duties
- seller duties
- transportation/delivery responsibility
- unfair and misleading trade/advertising practices
- grievance handling and escalation
- transaction/invoice record retention
- monitoring, inspection, and evidence readiness

The official government publication pages confirm the Directive, but the first repository mapping could not directly machine-read the complete attached Directive text. The Directive rule file therefore does not invent clause numbers or penalties: it records its verification status and distinguishes corroborated operational requirements from items that still require direct official-clause verification.

An audit must preserve that source-status disclosure and must not present the project as regulator certification or as a complete audit of every Nepal consumer, tax, payment, privacy, cybersecurity, or sector-specific law.

## Usage

Ask an AI agent to load `SKILL.md`, then say something like:

> Audit https://example.com for Nepal e-commerce compliance.

The agent must ask all 10 discovery questions before starting the audit.

## Safety and legal positioning

This project is an audit-assistance tool, not a law firm, regulator, certificate, or substitute for legal advice. A `PASS` means the collected evidence supports the specific rule check. It does not mean the business is legally compliant in every respect.

Rules must be traceable to an official or otherwise clearly identified legal source. Contributors should avoid turning assumptions, industry conventions, or model knowledge into legal requirements.
