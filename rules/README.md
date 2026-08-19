# Country Rule Packs

Each jurisdiction lives under `rules/<country>/`.

A country pack converts legal requirements into auditable agent instructions. It is not a free-form legal summary.

## Required files

Every country pack should contain:

- `README.md` — jurisdiction scope, official source hierarchy, source freshness, known gaps, and supported business roles.
- one or more rule files — each mapping auditable requirements to legal provisions and evidence expectations.

## Rule contract

Every auditable rule should provide, in prose or a structured table:

1. **Rule ID** — stable, country-prefixed identifier.
2. **Legal basis** — Act/regulation/directive and section/clause.
3. **Applies to** — business roles and conditions.
4. **Requirement** — plain-language statement faithful to the source.
5. **Public evidence** — what can be checked from a customer-facing website/app when possible.
6. **Internal evidence** — code/config/API/database/admin evidence that can strengthen the check when available.
7. **Decision rule** — what supports `PASS`, `FAIL`, `PARTIAL`, or manual/unobserved status.
8. **Severity** — operational severity, kept separate from statutory penalty mapping.
9. **Penalty mapping** — only where the source explicitly supports it.
10. **Remediation** — implementation-oriented fix without inventing business-owned facts.

## Source discipline

Prefer sources in this order:

1. official statute/regulation/directive text
2. official gazette or regulator publication
3. official regulator notices/manuals that explain implementation
4. secondary sources only as explanatory context

A secondary source must never silently override an official source.

When an official source exists but has not yet been incorporated, state that limitation in the country README and in any audit report that relies on the incomplete pack.

## Contributions

A new country rule pack should be reviewable independently from the core skill. Contributors should include source metadata, effective/publication dates where known, and enough mapping detail for another reviewer to trace each audit rule back to the legal source.
