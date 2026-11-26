# Proposal: Optional delegated reader-model adaptation for Keel — Opensiro VSM architecture review

## Proposal in the project's own terms
### Problem
Keel already discovers new models and runs guarded trials. Its owner can set a reader tier, but trial initiation and lasting preference changes are owner actions. Could a developer compose a bounded adaptation actor to make those choices for authorized read-only consumers, without giving it general settings rights?

### Proposed solution
Reuse the existing reader tier and model-trial lifecycle. Add opt-in scoped authority to start/defer a reader trial and adopt/retain its model after a frozen quality/cost report, plus feedback from actual later reads. Do not add another reader tier. The owner defines allowed models/providers, spend and consumers, and can override or revoke. If the tier also serves a non-reading consumer outside the grant, refuse adoption unless use-time isolation preserves that consumer's baseline.

### Alternatives considered
Keep the manual trial and tier-edit flow (the default), or use an owner-authorized admin script. The latter may need broader rights than this proposed dedicated capability. The native AI-assisted tier import still needs owner acceptance.

**What exists today:** [first-seen](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/providers/first-seen.ts) detects new models. [model trials](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts) starts guarded trials on an operator action; [experiments](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiments.ts) freezes reports and keeps arms temporary. [reader tier](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/agent-defaults.ts), [read selection](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts) and [tier routing](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/tiers.ts) already provide a durable owner preference and routing. [Tier import](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/tiers.ts) proposes tiers from owner messages and saves them with owner action.
**What may be missing:** A scoped decision interface for a developer-supplied actor to select a trial, accept or retain the existing reader-tier baseline after evaluation, and observe effects on later reads.
**Closest existing project-native solution:** Manually run a trial and edit the existing reader tier. Keep that flow as default.
**Existing discussion:** No Issues or PRs returned in the bounded all-state original list on 2026-11-26; no maintainer demand inferred.

## How we reached this proposal — Opensiro VSM assessment
Opensiro uses the Viable System Model to examine organizational decision ownership, not product quality.

**Historical assessment:** [accepted Index assessment](https://github.com/opensiro/vsm-harness-index/blob/7abafd36dd9216d94e795dac9e6030bc0e8e56a6/assessments/ke/keel.md); Index 7abafd36dd9216d94e795dac9e6030bc0e8e56a6; assessment blob a5386e12418ca14fc4a17e32786b4026104e064f; reviewed 2026-11-20; review_ref a7981c9d6d022d3086e6ac09dc9358f0aba4727b; Profile 0.2.4, Methodology 0.3.8.
**Boundary:** Local Bun daemon, built-in agent trees, optional linked fleet; model providers external, owner parent.
**Current original HEAD:** [205a848360f4339b0fd3e45e5bfc3b6151ebc9fb](https://github.com/agent-sh/keel/commit/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb), observed 2026-11-26. Historical states are not current grades.

| Key | Function | Historical state | Evidence |
| --- | --- | --- | --- |
| **S1 · Operations** | Performs work | A | [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts) |
| **S2 · Coordination** | Coordinates operational units | A | [src/automation/agents.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/agents.ts) |
| **S3 · Current management** | Current commitments/resources | A | [src/automation/budget.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/budget.ts) |
| **S3* · Independent audit** | Independent corrective evidence | A | [src/automation/verify.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/verify.ts) |
| **S4 · Future adaptation** | External change and future choices | — | [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts), current source may differ from historical classification |
| **S5 · Identity/policy** | Ultimate authority | P | [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/admin.ts) |

`A` autonomous owner; `C` first-party developer-composable autonomous ownership; `P` parent-governed; `A(P)` / `C(P)` additional independently evidenced parent mode; `—` bounded absence; `?` unresolved. Ownership categories, not quality ranks.

## Why this particular construction?
**Whole-repository prioritization:** Existing operational, coordination, management and review paths do not imply a need for mandatory conversion. S5 stays parent-owned; S4 has a specific external-novelty and durable-choice hypothesis.
**Construction hypothesis:** S4=— -> S4=C; proposed future construction, not an Index grade change.
**Native building blocks:** First-seen listing, guarded model trial, frozen report, [src/engine/readers.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/readers.ts) and role selection.
**Minimal proposed addition:** Typed candidate/report callbacks with scoped start/defer and adopt/retain choices; owner model/provider/spend constraints; scoped adoption into the existing reader tier, actual selected-model/fallback and quality/cost receipt, revoke/rollback. Optional unstructured release evidence is data, not authority.
**Scope exclusions:** No change to other roles, ultimate owner policy, manual default, or automatic cheapest-model promotion.

## Proposed approach and validation
1. Reuse native listing/trial lifecycle, preserve one live trial and guards; add reader-quality evidence rather than assuming lower cost implies quality.
2. Enforce an owner-defined envelope at choice and later use. A scoped existing reader-tier update must not change other tier rows or shared small_models; honor explicit owner overrides and refuse unauthorized non-reading tier consumers unless isolated at use.
3. Test a fake new listing and start/defer; adopt/retain after a frozen report; observe an actual later non-trial read and receipt. Deny stale or revoked authority, failed guard, unavailable model, unauthorized tier consumers and role spillover. No tests executed.

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
