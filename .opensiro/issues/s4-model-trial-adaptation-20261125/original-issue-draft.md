# Proposal: Optional delegated reader-model adaptation for Keel — Opensiro VSM architecture review

## Proposal in the project's own terms
Could Keel optionally let developers compose an adaptation actor that chooses when to test a newly listed reader model and, within owner-defined limits, whether to prefer it for future reads?

**What exists today:** [src/providers/first-seen.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/providers/first-seen.ts) detects new models. [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/server/routes/model-trials.ts) starts a guarded live trial on an operator action. [src/admin/experiments.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/admin/experiments.ts) freezes its report and explicitly keeps arms temporary.
**What may be missing:** A scoped decision interface that lets a developer-supplied actor select a trial, accept or retain the baseline after evaluation, and observe the effect on future reader requests.
**Closest existing project-native solution:** Manually run a reader trial and edit small_models via [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/server/routes/admin.ts); that shared setting also affects other choices, so a reader-only preference may be useful. The existing manual flow should remain the default.
**Existing discussion:** No Issues or PRs found in the bounded all-state original repository list on 2026-11-25; no maintainer demand inferred.

## How we reached this proposal — Opensiro VSM assessment
Opensiro uses the Viable System Model to examine organizational decision ownership, not product quality.

**Historical assessment:** [accepted Index assessment](https://github.com/opensiro/vsm-harness-index/blob/7abafd36dd9216d94e795dac9e6030bc0e8e56a6/assessments/ke/keel.md); Index 7abafd36dd9216d94e795dac9e6030bc0e8e56a6; assessment blob a5386e12418ca14fc4a17e32786b4026104e064f; reviewed 2026-11-20; review_ref a7981c9d6d022d3086e6ac09dc9358f0aba4727b; Profile 0.2.4, Methodology 0.3.8.
**Boundary:** Local Bun daemon, built-in agent trees, optional linked fleet; model providers external, owner parent.
**Current original HEAD:** [86a03cc80fb2841fdb117d521e7f54db0898eb9b](https://github.com/agent-sh/keel/commit/86a03cc80fb2841fdb117d521e7f54db0898eb9b), observed 2026-11-25. Historical states are not current grades.

| Key | Function | Historical state | Evidence |
| --- | --- | --- | --- |
| **S1 · Operations** | Performs work | A | [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/engine/turn.ts) |
| **S2 · Coordination** | Coordinates operational units | A | [src/automation/agents.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/automation/agents.ts) |
| **S3 · Current management** | Current commitments/resources | A | [src/automation/budget.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/automation/budget.ts) |
| **S3* · Independent audit** | Independent corrective evidence | A | [src/automation/verify.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/automation/verify.ts) |
| **S4 · Future adaptation** | External change and future choices | — | [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/server/routes/model-trials.ts), current source may differ from historical classification |
| **S5 · Identity/policy** | Ultimate authority | P | [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/server/routes/admin.ts) |

`A` autonomous owner; `C` first-party developer-composable autonomous ownership; `P` parent-governed; `A(P)` / `C(P)` additional independently evidenced parent mode; `—` bounded absence; `?` unresolved. Ownership categories, not quality ranks.

## Why this particular construction?
**Whole-repository prioritization:** Existing operational, coordination, management and review paths do not imply a need for mandatory conversion. S5 stays parent-owned; S4 has a specific external-novelty and durable-choice hypothesis.
**Construction hypothesis:** S4=— -> S4=C; proposed future construction, not an Index grade change.
**Native building blocks:** First-seen listing, guarded model trial, frozen report, [src/engine/readers.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/engine/readers.ts) and role selection.
**Minimal proposed addition:** Typed candidate/report callbacks with scoped start/defer and adopt/retain choices; owner model/provider/spend constraints; role-specific persistent reader preference, actual selected-model/fallback and quality/cost receipt, revoke/rollback. Optional unstructured release evidence is data, not authority.
**Scope exclusions:** No change to other roles, ultimate owner policy, manual default, or automatic cheapest-model promotion.

## Proposed approach and validation
1. Reuse native listing/trial lifecycle, preserve one live trial and guards; add reader-quality evidence rather than assuming lower cost implies quality.
2. Enforce an owner-defined envelope at choice and later use. A reader-only overlay must not change shared small_models; honor explicit owner overrides.
3. Test a fake new listing and start/defer; adopt/retain after a frozen report; observe an actual later non-trial read and receipt. Deny stale or revoked authority, failed guard, unavailable model and role spillover. No tests executed.

**Hypothesized benefit:** Delegated adaptation without broad owner-settings rights; empirical demand, quality and operator-time benefit unknown.
**How to falsify:** Equivalent native scoped path already exists, no real later reader effect/feedback, or the proposed authority cannot be enforced.
**Cost status:** NOT_MEASURED.

## Feedback requested
Would an optional, reader-only adaptation path fit Keel's architecture, or is the manual native flow preferable? Is any part of the functional mapping incorrect? Maintainers alone decide adoption; no request to adopt VSM.

## Three independent ways to participate
- Discuss or implement the focused native improvement if useful.
- Challenge the VSM mapping or methodology.
- Explore an optional legally permitted domain-specific fork without requiring upstream adoption.

## Research attribution and AI disclosure
[Opensiro Upstream](https://github.com/opensiro/upstream) · [VSM Profile](https://github.com/opensiro/vsm-harness-profile/blob/main/PROFILE.md) · [VSM Skills](https://github.com/opensiro/vsm-harness-skills) · [VSM Index](https://github.com/opensiro/vsm-harness-index).

**AI involvement:** Prepared with AI assistance; no independent human review, maintainer endorsement, implemented constructor, new grade or measured savings claimed.
