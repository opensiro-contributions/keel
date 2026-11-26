# Keel — reader-model adaptation technical contract
**Canonical storage:** opensiro-contributions/keel@opensiro/meta:.opensiro/issues/s4-model-trial-adaptation-20261125.
**Level 1:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md).
**DRAFT — NOT PUBLISHED** · PLAN_ONLY · NOT_RUN.

## 1. Function-specific construction boundary and methodology checks
**Source and mode boundary:** [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts); local daemon and agents, optional fleet, providers external and owner parent.
**Target transition:** S4=— -> S4=C
**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** S1 readers support work; preserve coordination/budgets/audit; S4 reader policy only; S5 owner controls envelope.
**Function witness:** External provider novelty; operator starts trial and manually sets durable defaults. Composed actor decides start/defer and adopt/retain with effect on later reads and feedback.
**Counterfactual owner test:** Without actor, manual trial works but no bounded autonomous selection/adoption.
**Possible methodological negative control:** Manual parent path legitimate; arms deliberately temporary. No mandatory local S4 or changed grade.
**Contributor / maintainer priorities:** NOT_STATED.
## 2. Source-pinned baseline and parallel native Track A / on-top Track B
**Original native workflow:** [src/providers/first-seen.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/providers/first-seen.ts) detects new model, [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts) starts one live trial, [src/admin/experiments.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiments.ts) freezes report and states no kept switches; [src/admin/experiment-report.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiment-report.ts) decides.
**Closest existing solution:** [reader tier](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/agent-defaults.ts) precedes small_models after trial in [turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts); [tier import](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/tiers.ts) proposes rows but owner action saves. [tiers.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/tiers.ts) can route Explore and explicitly named or mapped agents. Reuse the setting; delegated authority, not another tier or a generic PATCH, is the hypothesis.
**Relevant original Issues/PRs:** inherited [CONTRIBUTING](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/CONTRIBUTING.md) welcomes responsible AI-assisted contributions; [Feature Request](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/.github/ISSUE_TEMPLATE/feature.yml) requires Problem and Proposed solution, Alternatives considered optional. No CLA/DCO requirement found in reviewed files. Bounded all-state Issue/PR queries empty.
| Link | Track A | Track B | Falsifier |
| --- | --- | --- | --- |
| Novelty | first-seen | typed deduped event | equivalent scoped event |
| Decision | trial and frozen report | actor chooses test/defer and adopt/retain | only automatic winner |
| Future effect | reader selection | role-only preference and receipt | temporary arm or spillover |
**On-top distinctness:** Reuse experiment; reject notification-only, general settings writer and fixed cost-minimizer.
**Source ambiguity / rights blockers:** No blocking source fact for design; empirical benefit unknown. MIT, inherited [CONTRIBUTING](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/CONTRIBUTING.md) welcomes responsible AI-assisted contributions; [Feature Request](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/.github/ISSUE_TEMPLATE/feature.yml) requires Problem and Proposed solution, Alternatives considered optional. No CLA/DCO requirement found in reviewed files. Bounded all-state Issue/PR queries empty.; verified fork, Issues disabled; no public consent.
## 3. Minimal complete S4 first-party C construction
**Required property:** Developer-composed actor with lawful choice, effect and returned evidence.
| Native port | Existing | Proposed edit | Return |
| --- | --- | --- | --- |
| Candidate/trial | first-seen, model-trials | typed callback, dedupe provider identity/model, check owner envelope, reuse one-live-trial rule | trial receipt or defer |
| Result/decision | experiments, frozen report | quality guard; actor chooses adopt/retain, persist scoped decision and revision atomically | accepted/refused receipt |
| Later reading | readers, turn | compare-and-set existing reader tier model; grant includes read-only consumers only, refuse non-reader spillover unless use-time isolation preserves baseline; no other tiers or small_models writes | actual model/fallback/errors/cost/quality, rollback on revoke |
**Architectural C-sufficiency argument:** Trusted developer-registered callback supplies real alternatives on external novelty; dedicated capability enforces owner allowlist/budget and policy generation at decision/use. Trial temporary, adoption separate; guarded tier update and use-time scope enforcement prevent spillover. Quality guard uses checked/unread results plus held-out evidence, not cost alone. Durable receipt, feedback and restart idempotency; retain/revoke. External release notes optional untrusted evidence, never policy.
**Explicit non-goals:** No other model role, generic supervisor, S5 transfer or automatic promotion.
**Implementation dependency graph:** P1 envelope/quality/receipt → trial seams → role preference → feedback → tests.
## 4. Priorities, optional alternative and stopping rules
**P0 and P1:** Optional developer-composed reader-model adaptation using discovery, guarded trial, frozen report, scoped adoption into the existing reader tier and later read receipts. Owner-defined model/provider and spend envelope, reader-specific quality guard, durable scoped reader-tier update and receipts.
**P2:** NONE; other model roles remain outside scope.
**Alternative path:** Manual owner trial and preference; owner-authorized script where broad rights acceptable.
**Stop:** Equivalent supported C or lack of scope/feedback, not absent measurements.
## 5. Future source-native acceptance — derive tests, do not copy a matrix
**Native test commands and entry points:** Bun tests in [src/admin/model-trials.test.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/model-trials.test.ts), [src/engine/model-trial.test.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/model-trial.test.ts), [src/providers/first-seen.test.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/providers/first-seen.test.ts), [src/engine/reader.test.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/reader.test.ts); no execution.
**Positive functional closure:** Fake new listing; actor starts trial, accepts frozen quality/cost report, actual later non-trial read uses model and returns receipt.
**Independent alternative (where applicable):** Same lawful options, actor retains baseline; observe unchanged read.
**Negative authority and compatibility (where applicable):** Missing/revoked actor, stale revision, failed guard, unlisted model, other live trial, explicit override; baseline safe, other roles unchanged; deny unauthorized non-reading tier consumers unless isolated; restart no duplicate.
**Matched native alternative:** Same trial/read with manual settings; compare quality, cost, operator time, maintenance.
| Test | Expected | Falsifier |
| --- | --- | --- |
| Candidate/start/defer | one or no trial | duplicates |
| Adopt/retain | later read and receipt | trial-only |
| Revoke/restart | baseline, no spillover | unauthorized effect |
## 6. Proposal verdict, falsification, evidence ownership and handoff
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE
**Primary falsifier:** Existing equivalent scoped C, no lawful discretionary actor, no actual reader feedback or spillover.
**Validation state:** NOT_RUN
**Ownership of truth:** Profile/Skills semantics/method, Index historical grade, original maintainer adoption, roadmap.md case decisions.
**Cost status:** NOT_MEASURED
**Next permitted action:** Separate exact original publication gate and implementation consent.
**Human backlink:** [issue.md](issue.md).
**case receipt:** [roadmap.md](roadmap.md).
**AI disclosure:** AI-assisted plan, no tests or independent review.
