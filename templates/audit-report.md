# E-Commerce Compliance Audit Report

> This template is required by `SKILL.md`. Replace placeholders with observed facts. Do not delete scope limitations or the non-certification statement.

## 1. Audit identity

- **Target:** `<website/app/repo/business>`
- **Jurisdiction:** `<country>`
- **Audit timestamp:** `<ISO/local timestamp>`
- **Rule pack(s):** `<IDs/versions>`
- **Business role(s):** `<first-party/list-based | intermediary | seller | platform provider | delivery | combination>`
- **Environment:** `<production | staging | development | local | mixed>`

## 2. Legal-source status

- **Implemented sources:** `<official source names>`
- **Known current sources not yet incorporated:** `<none or list>`
- **Freshness warning:** `<required limitation text from country README>`

## 3. Mandatory discovery answers

Record all 10 answers exactly enough that another auditor understands the scope.

1. Jurisdiction: `<answer>`
2. Business role: `<answer>`
3. Audit targets: `<answer>`
4. Customer journey: `<answer>`
5. Environment/test safety: `<answer>`
6. Internal access available: `<answer>`
7. Business identity expected: `<answer>`
8. Commerce model details: `<answer>`
9. Products/services and regulatory sensitivity: `<answer>`
10. Desired output/remediation authority: `<answer>`

## 4. Capability matrix

| Capability | Available? | Used? | Scope/evidence |
|---|---:|---:|---|
| Browser/web | Yes/No | Yes/No | `<details>` |
| Current-source web research | Yes/No | Yes/No | `<details>` |
| Repository/local code | Yes/No | Yes/No | `<details>` |
| CMS/admin | Yes/No | Yes/No | `<details>` |
| API | Yes/No | Yes/No | `<details>` |
| Database/schema | Yes/No | Yes/No | `<details>` |
| Network/devtools | Yes/No | Yes/No | `<details>` |

## 5. Executive summary

### Compliance Readiness

- **Readiness score:** `<0-100 or N/A>`
- **Evidence coverage:** `<percent>`
- **Critical failures:** `<count>`
- **High failures:** `<count>`
- **Manual/unverified items:** `<count>`
- **Overall confidence:** `<High | Medium | Low>`

Explain the result in plain language. If evidence coverage is weak, say so prominently even if the readiness score is high.

## 6. Immediate blockers

List Critical and High failures first, ordered by explicit statutory penalty mapping when present.

| Priority | Rule | Status | Legal basis | Penalty mapping | Evidence | Fix |
|---|---|---|---|---|---|---|
| 1 | `<rule ID>` | FAIL | `<section>` | `<ACT-S23/ACT-S22/etc>` | `<exact observation>` | `<short remediation>` |

If none: `No Critical/High failure was established from the available evidence.`

## 7. Results by category

| Category | Pass | Partial | Fail | Not observed | Manual verification | N/A |
|---|---:|---:|---:|---:|---:|---:|
| `<category>` | 0 | 0 | 0 | 0 | 0 | 0 |

## 8. Detailed findings

Repeat this block for every applicable rule.

### `<RULE-ID>` — `<title>`

- **Status:** `<PASS | FAIL | PARTIAL | NOT_OBSERVED | MANUAL_VERIFICATION | NOT_APPLICABLE>`
- **Severity:** `<Critical | High | Medium | Low>`
- **Confidence:** `<High | Medium | Low>`
- **Legal basis:** `<source + section/clause>`
- **Penalty mapping:** `<explicit mapping or OTHER/UNMAPPED>`
- **Applies because:** `<discovery fact>`
- **Evidence source:** `<URL/page | screenshot | repo path/symbol | API | DB field | admin setting | manual document>`
- **Observed evidence:** `<specific reproducible evidence>`
- **Gap:** `<what is missing/contradictory, or None>`
- **Remediation:** `<concrete fix>`
- **Implementation note:** `<optional code/platform approach>`

For `NOT_OBSERVED` and `MANUAL_VERIFICATION`, state exactly what additional evidence would resolve the check.

## 9. Remediation plan

### P0 — Critical

- [ ] `<fix>` — rules: `<IDs>` — owner/input needed: `<if any>`

### P1 — High

- [ ] `<fix>`

### P2 — Medium

- [ ] `<fix>`

### P3 — Low

- [ ] `<fix>`

Prefer platform-level fixes that resolve multiple findings. Never fill legal identifiers or merchant-owned facts with invented values.

## 10. Re-test plan

For every proposed or implemented fix, state the exact evidence needed to close the finding.

| Rule | Re-test action | Expected evidence |
|---|---|---|
| `<ID>` | `<visit page/run test/inspect code>` | `<what proves closure>` |

## 11. Scope and evidence limitations

Explicitly list:

- inaccessible pages or flows
- login/payment/order actions not authorized
- missing repository/admin/API/database access
- facts supplied by user but not independently verified
- current legal instruments known but not incorporated
- sample-size limitations
- category-specific laws not loaded

## 12. Non-certification statement

This report is an evidence-based compliance audit aid. It is not a government approval, legal certification, legal opinion, or guarantee that the audited business complies with every applicable law. `PASS` means the collected evidence supported the specific loaded rule at the time of the audit.
