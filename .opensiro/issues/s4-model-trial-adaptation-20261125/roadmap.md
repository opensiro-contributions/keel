# Keel — reader adaptation
## Identity and pins
- Receipt contract: proposal-gate
- Original repository: agent-sh/keel
- Original HEAD: 205a848360f4339b0fd3e45e5bfc3b6151ebc9fb
- Observed at: 2026-11-26
- Initial research HEAD: 86a03cc80fb2841fdb117d521e7f54db0898eb9b (2026-11-25); targeted source refresh before proposal, not a new Index assessment.
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/7abafd36dd9216d94e795dac9e6030bc0e8e56a6/assessments/ke/keel.md
- Accepted assessment blob SHA: a5386e12418ca14fc4a17e32786b4026104e064f
- Accepted review ref: a7981c9d6d022d3086e6ac09dc9358f0aba4727b
- Accepted reviewed at: 2026-11-20
- Accepted VSM vector: S1=A · S2=A · S3=A · S3*=A · S4=— · S5=P
- Accepted Profile version: 0.2.4
- Accepted Methodology version: 0.3.8
- Review age: 6 days.
- System in focus: local Bun daemon, built-in agent trees and optional fleet; providers external and owner parent.
- Repository-wide source map: Initial 2426-file directory census; refreshed tree 2599 tracked files, targeted change review of engine, providers, automation, safety, fleet, admin, server, board, tools, clients, docs/tests/package; targeted deep reads of decision paths, not every file. [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts), [src/automation/agents.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/agents.ts), [src/automation/budget.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/budget.ts), [src/automation/verify.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/verify.ts), [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts), [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/admin.ts).
- Target transition: S4=— -> S4=C
- Proposed C construction: Optional developer-composed reader-model adaptation using discovery, guarded trial, frozen report, scoped adoption into the existing reader tier and later read receipts.
- C sufficiency falsifier: equivalent scoped autonomous actor and actual later reader effect already exists, or proposed path is only temporary trial or generic settings write.
- Priority rationale: external novelty and experiments make S4 concrete; four historical A functions and parent S5 have no independently justified C target. Current S4 may differ from historical classification; no regrade.
## Rights and authority
MIT [license](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/LICENSE); inherited [CONTRIBUTING](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/CONTRIBUTING.md) welcomes responsible AI-assisted contributions; [Feature Request](https://github.com/agent-sh/.github/blob/0011d30037ea379c7392cf7379be021d3365b8b7/.github/ISSUE_TEMPLATE/feature.yml) requires Problem and Proposed solution, Alternatives considered optional. No CLA/DCO requirement found in reviewed files. Bounded all-state Issue/PR queries empty. Verified fork parent and admin/push; Issues disabled. Owner-directed roadmap bootstrap ACTIVE/ALLOW, not public consent. [Claim](https://github.com/opensiro/upstream/issues/58#issuecomment-7171894968).
## Existing work / overlap
[src/providers/first-seen.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/providers/first-seen.ts) discovers post-baseline models; [src/server/routes/model-trials.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/model-trials.ts) starts trial on owner press with one live experiment and guard metrics. [src/admin/experiments.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiments.ts) freezes result and explicitly disallows kept switches; [src/admin/experiment-report.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/admin/experiment-report.ts) returns winner/inconclusive/regression. [reader tier](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/agent-defaults.ts) and [turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts) use an owner-defined tier after trial model and before small_models. [tiers.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/tiers.ts) and [agents.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/agents.ts) show this tier can route Explore and explicitly named or mapped agents. [tier import](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/tiers.ts) saves only on owner action. Reuse that setting; delegated trial and adoption authority remains the hypothesis. No prior case found; historical novelty not certified.
## Parallel contribution-on-top review
- Evaluation object: future reader-role configuration following external model novelty.
- Existing-work overlap: discovery, guarded trials, reports, role selection and fallback shipped; no lasting delegated adoption observed.
- Our on-top contribution: registered actor chooses trial/defer and adopt/retain under owner envelope; role-specific preference affects later reads with feedback.
- Incremental benefit: hypothetical delegate adaptation without broad settings rights or other role changes.
- Decision scope: architectural feasibility, not demand or adoption. Reject notification only, arbitrary admin writer, fixed cheapest-model promotion. Manual owner alternative remains.
## Function ownership
- S1 disposition: NO_TARGET; model executes via [src/engine/turn.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/engine/turn.ts).
- S2 disposition: NO_TARGET; parent coordinates workers via [src/automation/agents.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/agents.ts).
- S3 disposition: NO_TARGET; present commitments and budget via [src/automation/budget.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/budget.ts).
- S3* disposition: NO_TARGET; goal verification via [src/automation/verify.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/automation/verify.ts).
- S4 disposition: P0; external novelty and experiments; no enduring scoped adoption observed, parent adaptation possible.
- S5 disposition: NO_TARGET; owner controls policy/settings via [src/server/routes/admin.ts](https://github.com/agent-sh/keel/blob/205a848360f4339b0fd3e45e5bfc3b6151ebc9fb/src/server/routes/admin.ts). Contributor interest NOT_STATED.
## Capability priority
- P0: Optional developer-composed reader-model adaptation using discovery, guarded trial, frozen report, scoped adoption into the existing reader tier and later read receipts.
- P1 dependencies: Owner-defined model/provider and spend envelope, reader-specific quality guard, durable scoped reader-tier update and receipts.
- P2 optional: NONE; other model roles remain outside scope.
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Proposed validation: fake listing, start/defer, frozen report with quality/cost guards, adopt/retain, actual non-trial read and receipt; deny stale/revoked/guard-failed/unlisted, no spillover.
- Validation state: NOT_RUN
- Proposal falsifier: equivalent native C, ineffective authority or no actual later read feedback.
## Implementation options
Reuse trial creation and report; developer registers callbacks for candidate and finished trial. Owner restricts model/provider, spend and role; revision and report identity checked at decision/use. Actor may consume unstructured release notes as evidence, not instructions. Atomic compare-and-set of existing reader-tier model under scoped grant and receipt; explicitly authorize read-only consumers including Explore if desired. Refuse adoption affecting non-reading consumers unless use-time isolation preserves their baseline. Recheck mappings, policy revision and eligibility; owner override/revoke restores baseline; do not change other tier rows or small_models. Return actual model/fallback/quality/cost to actor. Manual flow and one-live-trial rule remain.
## Specification and domain alternatives
Separate Index reassessment if current parent S4 path proved; no method change or implementation authorized. MIT fork experiment optional after approval.
## Cost experiment
- Cost status: NOT_MEASURED
Matched manual vs composed adaptation: quality, spend, operator time, engineering/integration/review/test/maintenance.
## Delivery and publication
- Result: NEEDS_EVIDENCE
- External issue: DRAFT — NOT PUBLISHED
- Fork issue: FORK_ISSUES_DISABLED / NOT_PUBLISHED
PLAN_ONLY; no tests/product change/Index grade change. Separate exact consent and history gate.
- Publication review source HEAD: 205a848360f4339b0fd3e45e5bfc3b6151ebc9fb
- Publication review action: original_issue
- Publication review destination: https://github.com/agent-sh/keel
- Publication review title SHA256: fa31efe58fdbc20c7898691b2c62df3a2f304591f291ecc53d65d7dbccaa9406
- Publication review history SHA256: 36b6a55abf4ed23d12047822580ffef3867b897ed7392536b2698e95122788f3
- Publication review resolution: NEW_DISTINCT_OUTCOME
- Publication review rationale: Bounded current native and named archive scan NEW_PROPOSAL; no prior match, not exhaustive. Reader tier already exists; delegated trial and scoped adoption/retention with actual later read receipts is the proposed delta, not a new tier. Inherited native Feature Request route and revised draft fields passed after Upstream #116. Source and text changed; renewed owner approval required. No public Issue.
