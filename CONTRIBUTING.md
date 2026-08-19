# Contributing

Contributions are welcome, especially new jurisdiction rule packs and corrections to existing legal mappings.

## Ground rule

A compliance rule must be traceable to a real source. Do not turn assumptions, SEO conventions, platform best practices, or model knowledge into legal requirements.

## Adding a country

Create:

```text
rules/<country>/README.md
rules/<country>/<law-or-rule-pack>.md
```

The country README must identify:

- jurisdiction
- official legal/regulatory sources
- publication/effective dates where known
- regulator/department
- business roles covered
- related laws intentionally excluded
- known current instruments not yet mapped
- freshness date or review note

The rule file must follow the contract in `rules/README.md`.

## Rule IDs

Use stable IDs that survive wording changes. Suggested format:

```text
<COUNTRY>-<SOURCE>-<SECTION>-<SEQUENCE>
```

Example:

```text
NP-ECA-033-05
```

Do not reuse an ID for a different legal obligation.

## Penalties

Only map a fine, imprisonment term, regulator action, or offence tier when the cited source directly supports the mapping.

Keep two concepts separate:

- **operational severity** — audit prioritization
- **statutory penalty mapping** — what the legal source expressly provides

## Evidence design

A good rule should work in different agent environments.

Describe both:

- public/browser evidence, when the requirement can be inspected from customer-facing behavior; and
- internal evidence, when repository, admin, API, database, or operational records are available.

Do not require internal access just to run the skill. Missing access should produce `NOT_OBSERVED` or `MANUAL_VERIFICATION` where appropriate.

## Pull request checklist

Before submitting a country pack:

- [ ] Every legal requirement has a traceable source and section/clause.
- [ ] Applicability is explicit.
- [ ] Browser-only audits do not pretend to prove hidden operational facts.
- [ ] Penalties are not inferred.
- [ ] Business-owned data is never invented in remediation examples.
- [ ] Known source gaps are disclosed.
- [ ] The report can distinguish `FAIL` from `NOT_OBSERVED` and `MANUAL_VERIFICATION`.
- [ ] New rules fit the mandatory discovery-driven workflow in `SKILL.md`.

## Legal-source updates

When a regulation/directive changes:

1. preserve the old mapping in Git history;
2. update the country README freshness warning;
3. modify/add the affected rule IDs carefully;
4. document effective dates when available;
5. avoid declaring an old audit current after the legal source changed.

## Scope of this project

This repository is an AI-agent audit skill. Avoid adding a full crawler, browser automation framework, database driver, or compliance SaaS backend to core unless there is a separate agreed architectural reason. Agents should use the browser, repository, API, database, and other tools already available in their environment.
