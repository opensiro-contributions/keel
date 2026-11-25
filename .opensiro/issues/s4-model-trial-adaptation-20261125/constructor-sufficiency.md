# Keel — reader-model adaptation technical contract
**Canonical storage:** opensiro-contributions/keel@opensiro/meta:.opensiro/issues/s4-model-trial-adaptation-20261125.
**Level 1:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md).
**DRAFT — NOT PUBLISHED** · PLAN_ONLY · NOT_RUN.

## 1. Function-specific construction boundary and methodology checks
**Source and mode boundary:** [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/engine/turn.ts); local daemon and agents, optional fleet, providers external and owner parent.
**Target transition:** S4=— -> S4=C
**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** S1 readers support work; preserve coordination/budgets/audit; S4 reader policy only; S5 owner controls envelope.
**Function witness:** External provider novelty; operator starts trial and manually sets durable defaults. Composed actor decides start/defer and adopt/retain with effect on later reads and feedback.
**Counterfactual owner test:** Without actor, manual trial works but no bounded autonomous selection/adoption.
**Possible methodological negative control:** Manual parent path legitimate; arms deliberately temporary. No mandatory local S4 or changed grade.
**Contributor / maintainer priorities:** NOT_STATED.
## 2. Source-pinned baseline and parallel native Track A / on-top Track B
**Original native workflow:** [src/providers/first-seen.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/providers/first-seen.ts) detects new model, [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/server/routes/model-trials.ts) starts one live trial, [src/admin/experiments.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/admin/experiments.ts) freezes report and states no kept switches; [src/admin/experiment-report.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/admin/experiment-report.ts) decides.
**Closest existing solution:** [src/engine/readers.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/engine/readers.ts) uses owner small_models, shared with small calls and Explore; [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/server/routes/admin.ts) permits broad manual PATCH. Owner-authorized script possible but not role-specific delegated closure.
**Relevant original Issues/PRs:** Live all-state list empty; no tracked template located. No demand inferred.
| Link | Track A | Track B | Falsifier |
| --- | --- | --- | --- |
| Novelty | first-seen | typed deduped event | equivalent scoped event |
| Decision | trial and frozen report | actor chooses test/defer and adopt/retain | only automatic winner |
| Future effect | reader selection | role-only preference and receipt | temporary arm or spillover |
**On-top distinctness:** Reuse experiment; reject notification-only, general settings writer and fixed cost-minimizer.
**Source ambiguity / rights blockers:** No blocking source fact for design; empirical benefit unknown. MIT, no tracked contributor-specific policy found; verified fork, Issues disabled; no public consent.
## 3. Minimal complete S4 first-party C construction
**Required property:** Developer-composed actor with lawful choice, effect and returned evidence.
| Native port | Existing | Proposed edit | Return |
| --- | --- | --- | --- |
| Candidate/trial | first-seen, model-trials | typed callback, dedupe provider identity/model, check owner envelope, reuse one-live-trial rule | trial receipt or defer |
| Result/decision | experiments, frozen report | quality guard; actor chooses adopt/retain, persist scoped decision and revision atomically | accepted/refused receipt |
| Later reading | readers, turn | role-specific preference behind explicit override, eligibility/availability; do not mutate small_models | actual model/fallback/errors/cost/quality, rollback on revoke |
**Architectural C-sufficiency argument:** Trusted developer-registered callback supplies real alternatives on external novelty; dedicated capability enforces owner allowlist/budget and policy generation at decision/use. Trial temporary, adoption separate; role overlay prevents spillover. Quality guard uses checked/unread results plus held-out evidence, not cost alone. Durable receipt, feedback and restart idempotency; retain/revoke. External release notes optional untrusted evidence, never policy.
**Explicit non-goals:** No other model role, generic supervisor, S5 transfer or automatic promotion.
**Implementation dependency graph:** P1 envelope/quality/receipt → trial seams → role preference → feedback → tests.
## 4. Priorities, optional alternative and stopping rules
**P0 and P1:** Optional developer-composed reader-model adaptation using discovery, guarded trial, frozen report, role-local adoption and later read receipts. Owner-defined model/provider and spend envelope, reader-specific quality guard, durable scoped preference and receipts.
**P2:** NONE; other model roles remain outside scope.
**Alternative path:** Manual owner trial and preference; owner-authorized script where broad rights acceptable.
**Stop:** Equivalent supported C or lack of scope/feedback, not absent measurements.
## 5. Future source-native acceptance — derive tests, do not copy a matrix
**Native test commands and entry points:** Bun tests in [src/admin/model-trials.test.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/admin/model-trials.test.ts), [src/engine/model-trial.test.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/engine/model-trial.test.ts), [src/providers/first-seen.test.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/providers/first-seen.test.ts), [src/engine/reader.test.ts](https://github.com/agent-sh/keel/blob/86a03cc80fb2841fdb117d521e7f54db0898eb9b/src/engine/reader.test.ts); no execution.
**Positive functional closure:** Fake new listing; actor starts trial, accepts frozen quality/cost report, actual later non-trial read uses model and returns receipt.
**Independent alternative (where applicable):** Same lawful options, actor retains baseline; observe unchanged read.
**Negative authority and compatibility (where applicable):** Missing/revoked actor, stale revision, failed guard, unlisted model, other live trial, explicit override; baseline safe, other roles unchanged; restart no duplicate.
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
