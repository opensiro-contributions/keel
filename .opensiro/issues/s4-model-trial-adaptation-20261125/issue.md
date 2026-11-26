# Keel — optional reader-model adaptation (Opensiro roadmap)
**PLAN_ONLY · proposal-stage GO · research NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED**

**One-sentence proposal:** Let a developer compose an optional actor which chooses new reader model trials and lasting preferences under owner-defined rights.
**Canonical decision receipt:** [roadmap.md](roadmap.md).
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md).
**Working fork:** opensiro-contributions/keel.
**Case:** .opensiro/issues/s4-model-trial-adaptation-20261125 on opensiro/meta.
## 1. Why Opensiro and central accepted VSM assessment
VSM-informed ownership may simplify engineering; this is a research hypothesis, not proven savings or a mandate.

> ACCEPTED HISTORICAL INDEX — not current grades
> S1=A · S2=A · S3=A · S3*=A · S4=— · S5=P

[Accepted assessment](https://github.com/opensiro/vsm-harness-index/blob/7abafd36dd9216d94e795dac9e6030bc0e8e56a6/assessments/ke/keel.md) · 7abafd36dd9216d94e795dac9e6030bc0e8e56a6 · blob a5386e12418ca14fc4a17e32786b4026104e064f · review a7981c9d6d022d3086e6ac09dc9358f0aba4727b · 2026-11-20 · Profile 0.2.4 / Methodology 0.3.8.

**Repository-wide audit:** Initial census and targeted refresh; [Original HEAD](https://github.com/agent-sh/keel/commit/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb); local daemon and optional fleet; directory census and targeted runtime/authority/experiment paths.

| Function | Historical state | Current source | Priority |
| --- | --- | --- | --- |
| **S1 · Operations** | A | [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts) | NO_TARGET |
| **S2 · Coordination** | A | [src/automation/agents.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/agents.ts) | NO_TARGET |
| **S3 · Current management** | A | [src/automation/budget.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/budget.ts) | NO_TARGET |
| **S3* · Independent review** | A | [src/automation/verify.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/verify.ts) | NO_TARGET |
| **S4 · Future adaptation** | — | [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts) | P0: external novelty and trials, no lasting delegated adoption |
| **S5 · Identity/policy** | P | [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/admin.ts) | NO_TARGET: parent |
A = autonomous owner; C = developer-composable path; P = parent-governed; A(P)/C(P) = additional parent mode; — = bounded absence; ? = unresolved. Ownership categories, not quality ranks.

**Priority rationale:** S4 has existing evidence and a specific missing future effect. Other functions do not need mandatory conversion.
**Deliberate exclusions / methodology challenge:** Owner settings remain parent-owned; experiments explicitly avoid kept switches. Historical grade is not current classification.
**Contributor / maintainer interests:** NOT_STATED.
## 2. Selected construction hypothesis and operator outcome
**Target transition:** S4=— -> S4=C
**Function-specific disturbance:** Provider lists a new model after baseline.
**Proposed C capability (P0):** Optional developer-composed reader-model adaptation using discovery, guarded trial, frozen report, scoped adoption into the existing reader tier and later read receipts.
**Best native operator alternative:** Start reader trial, inspect report, manually edit the existing reader tier.
**Expected user benefit:** Hypothetical scoped delegation of when to test/adopt and actual future read without broad settings rights.
**Architectural sufficiency argument:** Existing discovery and guarded experiment reused; developer actor makes lawful choices; existing reader-tier preference and actual feedback close future adaptation.
## 3. Existing native work versus missing construction
**Track A — native coverage:** [src/providers/first-seen.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/providers/first-seen.ts), [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts), [src/admin/experiments.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiments.ts), [src/admin/experiment-report.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiment-report.ts), [src/engine/readers.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/readers.ts); original all-state Issue/PR queries empty. [Reader tier](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/agent-defaults.ts), [tier routing](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/tiers.ts) and [owner import](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/tiers.ts) already cover persistent manual preference and model-generated owner-reviewed tier import; no new tier proposed.
**Track B — independent on-top C construction:** typed candidate/report callbacks, scoped selection and adoption/revert, actual later read feedback.
| C link | Native | Proposed |
| --- | --- | --- |
| Novelty and trial | listing, manual trial | actor starts or defers |
| Durable future effect | frozen report; manual settings | adopt or retain the existing reader tier, only for authorized read-only consumers |
| Rights and feedback | eligibility, guard | owner envelope, rollback and later receipt |
**Distinctness and falsifier:** Existing equivalent first-party scoped closure or no actual downstream effect refutes the proposal.
## 4. Priorities and minimum sufficient result
- **P0:** Optional developer-composed reader-model adaptation using discovery, guarded trial, frozen report, scoped adoption into the existing reader tier and later read receipts.
- **P1:** Owner-defined model/provider and spend envelope, reader-specific quality guard, durable scoped reader-tier update and receipts.
- **P2:** NONE; other model roles remain outside scope.
**Proposed C-sufficiency verdict:** PROPOSED_C_SUFFICIENT, not shipped.
## 5. Proposed acceptance and stop gates
**Future positive test:** New reader candidate, actor starts trial, frozen quality/cost report, adopts and real later read uses it with receipt.
**Future negative test:** Retain, revoked/stale rights, guard failure, model gone, owner override, unauthorized tier consumers and no spillover.
**Proposed falsifier:** No actual effect/feedback or already equivalent native path.
**Validation state:** NOT_RUN
## 6. Independent paths
**Original-native contribution:** Reuse trial and reader seams, seek maintainer feedback separately.
**Profile / Skills:** No rule change; separate reassessment if justified.
**Domain fork:** Optional MIT experiment after authorization.
## 7. Cost hypothesis
Matched quality/spend/operator and engineering costs, NOT_MEASURED.
## 8. Decision / handoff
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE
**Decision reason / next permitted step:** Credible bounded design; no tests, demand or measured savings. Maintainers decide adoption.
**Agent/developer handoff:** [constructor-sufficiency.md](constructor-sufficiency.md) and [roadmap.md](roadmap.md).
**Rights and publication:** MIT [license](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/LICENSE); inherited [CONTRIBUTING](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/CONTRIBUTING.md) welcomes responsible AI-assisted contributions; [Feature Request](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/.github/ISSUE_TEMPLATE/feature.yml) requires Problem and Proposed solution, Alternatives considered optional. No CLA/DCO requirement found in reviewed files. Bounded all-state Issue/PR queries empty. Fork verified parent and admin/push, Issues disabled. Owner-directed roadmap bootstrap ACTIVE/ALLOW; not public consent. No public fork or original Issue/PR; separate exact approval required.
**AI disclosure:** AI-assisted, no native tests or independent human review claimed.
