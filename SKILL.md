---
name: four-agent-research
description: Conduct rigorous complex research with evidence mapping, concrete advancement, critical review, and staged bottleneck investigation, using four agents by default or one researcher when requested. Use across scientific, technical, policy, strategic, historical, or other research domains; do not use for simple lookups or routine execution.
---

# Four-Agent Research

Select the execution mode **before any delegation**. Explicit instructions such as "不要 sub agent", "不要 agent", "单独工作", "单人研究", "no subagents", or "work alone" select **Solo Research / 单人研究**. This overrides every delegation, parallel-work, and independent-agent requirement below, including when subagent tools are available. Keep this choice until the user changes it; never spawn helpers, ask another task to do the work, or create conversations to bypass it.

In Solo Research, the current agent performs the same research responsibilities: frame the question, gather evidence, develop and falsify arguments, check the result, and report it. Do not simulate four personas or produce fictional agent contributions. Read later role descriptions as responsibilities of this one researcher, not instructions to instantiate agents. Replace Agent 3 review and progress assessment with explicitly labeled **self-review**; this is not independent validation. Apply the same substantive adoption checks through documented self-review and qualify unchecked claims. Select Startup, Standard, or Bottleneck Research by the same rules used in four-agent execution; solo has no separate strategy default.

Otherwise investigate through four distinct roles. Agent 0 is the current parent agent. When genuine subagent or delegation tools are available and allowed, create one persistent subagent session for each of Agents 1-3 and reuse it for follow-up work. Do not create user-visible tasks or conversations merely to simulate subagents. If a role session fails, Agent 0 may replace it once and must disclose the replacement. Invoking this skill authorizes those research delegations unless the user opts for solo execution. Project archiving follows the authorization and destination rules below; other external writes, purchases, publication, account changes, and consequential side effects require their own authorization.

If four-agent execution was selected but true subagents are unavailable, perform clearly separated role passes and disclose that fallback. This fallback does not apply to an explicit solo request. Never pretend simulated passes were independent agents.

## Shared Standard

Solo Research exists to reduce the token overhead of multi-agent coordination. Both execution modes share one mathematical and research methodology: the same strategy-selection rules, literature and method coverage, proof and counterexample techniques, experiments, method numbering, 5%/1% stages, claim ledger, verification criteria, effort-selection policy, stopping rules, and archive requirements. Maintain these rules once in the shared sections and references; future method changes apply to both modes. Execution mode changes only the number of agents and how responsibilities are scheduled and assigned. Independent-agent review is possible only with separate agents; solo must perform the same substantive checks without claiming independence.

Save tokens in solo execution by avoiding delegation briefs, repeated context transfer, inter-agent messages, duplicate evidence summaries, and four-role report packaging. Reuse one working evidence/method ledger and present a compact synthesis. Do not save tokens by silently omitting mathematical methods, decisive tests, verification, required method coverage, or complete archive content, or by automatically lowering reasoning effort. Explicit resource limits still apply equally to both modes; disclose any work they prevent. Do not promise a fixed token reduction.

- Convert the request into a precise research question, scope, definitions, decision criteria, and deliverable before delegating.
- Separate sourced facts, observations, calculations, inferences, hypotheses, and value judgments.
- Use the strongest available evidence for the domain: primary sources when they directly establish a claim, and authoritative or systematic syntheses when they better represent the evidence base. Cite sources close to the claims they support.
- Search for disconfirming evidence, boundary cases, alternative explanations, and counterexamples.
- Do not treat agreement among agents as validation. Agent 0 adjudicates by evidence and valid reasoning.
- Preserve uncertainty. State what would change the conclusion and what remains unknown.
- In mathematical proofs, do not introduce unnecessary abbreviation variables. Distinguish proof, conditional results, finite computational support, conjectures, and unresolved gaps.
- Keep all consequential external actions subject to the user's authorization and the active environment's permission rules.

## Shared Research Identifiers

Read [Shared Research Identifiers](references/research-identifiers.md) when starting or resuming research. Automatically number rounds from `round-000`, conjectures from `conjecture-000`, theorems from `theorem-000`, and other material objects by their documented type. Preserve the existing `method-001` starting rule. Each prefix has one persistent project-wide sequence, shared by solo and four-agent execution. Reuse IDs throughout conversation, ledgers, archives, and progress summaries; never reset or recycle them. Keep historical labels as aliases rather than renumbering archives. A proved conjecture retains its ID and links to its result ID; a changed status never silently rewrites its history. IDs organize records and are not extra abbreviation variables in mathematical proofs.

## Research Mode Selection

For each research round, choose one primary research strategy after selecting solo or four-agent execution. Strategy does not override execution mode, evidence standards, the applicable review gate, or archiving rules.

| Mode | Accepted names | Main purpose |
| --- | --- | --- |
| Startup Research | 启动研究, Startup Research | Map the literature, identify gaps, and minimally probe every promising shortlisted direction. |
| Standard Research | 标准研究, Standard Research | Advance an established question until marginal research benefit diminishes or a clear obstacle prevents useful progress. |
| Bottleneck Research | 瓶颈研究, Bottleneck Research | Break a documented impasse through extensive numerical experiments, renewed broad literature search, and unconventional methods. |

Honor the user's explicit mode for the current round, including an ongoing mode instruction that still applies. Otherwise select automatically from the request, available project materials, previous reports, and claim ledger:

1. Choose **Bottleneck Research** when substantive prior attempts have repeatedly stalled, the same material obstacle persists, or established approaches are exhausted.
2. Otherwise choose **Startup Research** for a new or substantially reframed topic without an adequate evidence map or tested candidate directions.
3. Otherwise choose **Standard Research** when a precise question and a plausible next route are available. When context is inconclusive after a brief orientation, use this mode provisionally and state the uncertainty.

Do not ask the user merely to choose a mode, run all three by default, or infer a bottleneck from one failed attempt or missing access alone. Read the selected mode's section in [Research Modes](references/research-modes.md) and include the mode, selection basis, work budget, and stopping criteria in the agents' briefs. Respect explicit time, cost, compute, access, and scope constraints. If required search or experiment tools are unavailable, disclose the limitation instead of claiming that work was performed.

Keep the chosen mode for the round. If its stopping condition is reached, report; do not silently restart under another mode. Reassess automatic selection at the next requested or already-authorized round, preserving any still-applicable user choice.

## Bottleneck Direction and Method Ledger

Number every concrete method `method-001`, `method-002`, etc. in one project-wide sequence across directions. Continue existing numbering across rounds and conversations; keep the same ID when suspending or reopening a method, and never reuse retired IDs. Use these IDs in research records and reports; see the reference below for variants and legacy labels.

When bottleneck investigation is needed, read [Direction and Method Search](references/bottleneck-methods.md). Map major directions and concrete methods beneath them, then focus on one decisive method-level obstacle at a time. Stage 1 suspends a method only on an evidence-backed subjective viability estimate strictly below 5%. Only when all mapped methods have been suspended or rigorously excluded does stage 2 revisit them with a strictly-below-1% threshold. Untested, blocked, or uncertain methods are not eliminated. Estimates are resource- and scope-dependent judgments, never proofs of impossibility; preserve attempts, reasons, uncertainty, and reopening conditions in the ledger. Both stages remain within the current round and budget.

## Adaptive Reasoning Effort

Agent 0 selects effort per subtask and phase, not once for the whole research mode or permanently by agent role. Default to `xhigh` (Extra High) for substantive research reasoning; use `high` for routine retrieval and organization, `max` for critical advancement and review, and `ultra` only for a precisely identified difficult gap with a concrete promising next attempt and sufficient budget. Explicit user choices and resource limits take precedence.

Before delegation and at meaningful phase boundaries, read [Reasoning Effort](references/reasoning-effort.md), select the target, apply it through available supported runtime controls, and distinguish the requested effort from any verified effective effort. A Skill instruction is not itself a runtime setting. If control or verification is unavailable, disclose that limitation and continue under the existing settings when permitted; never claim a switch occurred. Do not alter global configuration, switch models, or create extra conversations merely to enforce this policy.

## Agent 0: Lead Researcher

Agent 0 owns the full result and is accountable to the user for the other agents' work.

1. Frame the long-term objective when one exists and the exact objective for this run. For a one-shot question, use the user's requested outcome as the objective without inventing a larger project.
2. Before seeing results, establish domain-appropriate standards of evidence and an outcome-based weighted milestone list for measuring progress toward the user's goal.
3. Delegate bounded, role-specific briefs to Agents 1-3. Give them the question, scope, definitions, raw materials, required output format, and the phase's effort target selected under Adaptive Reasoning Effort. Apply and verify supported runtime settings rather than relying on the brief alone. Avoid accidental duplicate work, while requiring deliberate overlap for independent verification.
4. Keep Agent 3 independent: do not give it Agent 0's preferred conclusion or tentative synthesis before its review.
5. Integrate the agents' work, resolve disagreements, and apply the adoption gate below before accepting any material claim.
6. Request focused repair and re-review only while another iteration is likely to change a material conclusion. Bound retries according to time, cost, and risk; expose unresolved gaps instead of iterating ceremonially.
7. Report the answer, evidentiary basis, live disagreements, limitations, and next step to the user. Agent 0 remains responsible for every adopted claim.

## Agent 1: Evidence and Conjectures

Agent 1 maps what is known and proposes precise claims worth testing.

- Locate and assess the most relevant literature, data, prior art, definitions, and competing positions.
- Record source quality, date, relevance, and the exact claim each source supports; distinguish a source's statement from Agent 1's inference.
- Keep a minimal reproducibility log: sources or databases searched, material search terms, search date or evidence cutoff, inclusion and exclusion rationale, stopping rule, and durable identifiers or URLs for decisive sources.
- Reconcile terminology and identify contradictions, missing evidence, and neglected edge cases.
- Produce a short evidence map rather than an indiscriminate bibliography.
- Propose testable conjectures, hypotheses, intermediate claims, or candidate explanations. For each, state assumptions, predicted consequences, and a plausible falsifier.
- Rank proposals by expected value and tractability for Agent 2.

Agent 1 must not present a plausible narrative as a settled conclusion.

## Agent 2: Advancement and Falsification

Agent 2 turns the strongest candidate claims into concrete, checkable progress.

- In Standard Research, select the highest-value tractable claim, explaining the choice. In Startup Research, probe every promising shortlisted direction; in Bottleneck Research, pursue the selected experiment-and-method campaign.
- Attempt a proof, derivation, calculation, experiment, implementation, case analysis, data test, counterexample, or other domain-appropriate check.
- Actively try to falsify the claim and test hidden assumptions, extreme cases, and rival explanations.
- Make the work reproducible with stated inputs, assumptions, methods, auditable derivations or code, and relevant outputs. Do not reveal or request hidden chain-of-thought.
- Assign the result a Claim Ledger status and state the smallest remaining gap.
- Never upgrade suggestive evidence into proof or certainty.

## Agent 3: Independent Reviewer

Agent 3 is an adversarial but fair reviewer. It evaluates Agent 1 and Agent 2 before seeing Agent 0's conclusion.

- Verify citations, definitions, calculations, logical steps, quantifiers, assumptions, causal claims, and the match between evidence and conclusion.
- Perform an independent, proportionate source search for omitted decisive evidence. Open or retrieve decisive cited sources and reproduce critical calculations or tests when feasible.
- Audit Agent 1's search scope, inclusion choices, cutoff, and stopping rule for selection bias.
- Look for omitted alternatives, cherry-picking, circularity, leakage between training and testing, non-representative examples, boundary failures, and unsupported generalization.
- Give each material claim a review disposition of `ACCEPT`, `REVISE`, or `REJECT`, with a concrete reason and the appropriate ledger status.
- Identify the strongest surviving objection and the cheapest decisive next test.
- Audit the milestone model and produce the progress estimate defined below.
- Review independently; do not defer to consensus, authority, or Agent 0's status.

## Claim Ledger

Maintain stable IDs for material claims and update them rather than silently rewriting history. Use the narrowest applicable status:

- `PROVED`: deductively established under explicit assumptions. Never use this for an empirical generalization.
- `SUPPORTED`: meets the domain's evidentiary standard without an unresolved decisive objection, but is not deductively proved.
- `CONDITIONAL`: follows only if a specifically named unresolved premise holds; do not use it merely because every claim has scope assumptions.
- `CONJECTURAL`: precise and plausible but not adequately established.
- `CONTESTED`: credible evidence or valid analyses materially conflict.
- `REFUTED`: defeated by a valid logical counterexample or decisive contrary evidence against the explicitly scoped claim.
- `OPEN`: unresolved or not yet tested.

For each claim, record its statement, status, evidence, assumptions, dependencies, strongest objection, smallest remaining gap, and status history. `ACCEPT` means the reviewer finds the current wording and ledger status justified. `REVISE` requires a change to wording, evidence, or status before adoption. `REJECT` prevents adoption and normally leaves the claim `REFUTED`, `CONTESTED`, `CONJECTURAL`, or `OPEN` as the evidence warrants.

## Progress Estimate

Agent 0 defines milestone weights totaling 100 before results are known. Agent 3 may correct distorted weights but must record the change. Agent 3 assigns each milestone verified completion of `0`, `0.25`, `0.5`, `0.75`, or `1`; downstream work receives no credit when it depends on an unverified prerequisite. Calculate progress as the sum of `weight x verified completion`.

Report the result as `X%` with a plausible range, confidence level, and justification. Unknown work or an unstable denominator must widen the range. If the goal or denominator is too undefined for a defensible estimate, report `not estimable` and explain what definition is missing. Progress reflects validated completion toward the user's goal, never effort, elapsed time, token use, or document length.

## Agent 0 Adoption Gate

Before final synthesis, verify that:

- Every adopted material claim has a stable ledger ID, supporting source or auditable derivation, and an Agent 3 `ACCEPT` disposition or a documented response to `REVISE` followed by re-review.
- Decisive sources were opened or retrieved, not accepted from snippets or second-hand descriptions.
- Critical calculations, tests, or proofs were independently checked when feasible; anything not checked is explicitly qualified.
- No rejected, contested, conditional, or open claim is worded as settled.

## Execution Pattern

For solo execution, frame the question, gather evidence, make a concrete attempt, self-review material claims, and synthesize the result in the current agent. Follow the selected strategy, applicable adoption gate, stopping conditions, and archive procedure. Do not execute the delegation steps below.

For four-agent execution, use this default sequence, adapting when dependencies require it:

1. Agent 0 frames the problem, evidence standard, and milestones, selects the research mode under Research Mode Selection, and reads its procedure. Plan the initial per-subtask effort allocation under Adaptive Reasoning Effort. For long-running research, record the actual start time and resolve the project archive folder and existing round numbering under Long-Running Research Archive.
2. Agent 1 and Agent 2 begin in parallel when Agent 2 can independently attack the core question; otherwise Agent 1 goes first and Agent 2 receives its ranked conjectures.
3. Agent 3 first receives the original brief and evaluation criteria, forms its own review checklist and search plan, and only then receives the evidence map, Agent 2's work, and raw supporting artifacts. It never receives Agent 0's tentative conclusion before review.
4. Agent 0 applies the adoption gate and adjudicates by evidence, not votes.
5. Carry out the selected mode's work and repair-and-review iterations until its stopping condition or an explicit limit is reached. Reassess effort at meaningful phase boundaries without treating higher effort as a substitute for missing resources or a new method. Report the stopping reason and unresolved gaps.
6. When continuous work exceeds 30 minutes of actual wall-clock time, complete the single-record Drive archive procedure below. This applies to solo and four-agent execution alike.

## Report to the User

The first sentence of every end-of-round report to the user must identify the mode actually used, before any greeting, heading, result, or archive-status note. In Chinese, use exactly one of: "本次研究模式：启动研究。", "本次研究模式：标准研究。", or "本次研究模式：瓶颈研究。" In an English report, use "Research mode: Startup Research.", "Research mode: Standard Research.", or "Research mode: Bottleneck Research." Use an equivalent first sentence in another requested language.

After that opening, state the execution mode (solo, four-agent, or disclosed tool-unavailable fallback), give the useful answer and the compact target/requested/effective effort summary defined in [Reasoning Effort](references/reasoning-effort.md). In solo execution, use researcher/self-review labels throughout the following fields; never attribute work to nonexistent Agents 1-3. Include a compact audit trail containing:

1. **Long-term objective**
2. **This run's objective and mode**: whether the mode was user-specified or automatically selected, the selection basis, and the evidence-based stopping reason
3. **Agent 3 progress assessment**: percentage and range, confidence, and basis, or `not estimable`
4. **Agent 0 synthesis**: answer and recommended interpretation or decision
5. **Evidence and advancement**: the strongest sources and Agent 2's concrete result
6. **Independent review**: accepted claims, revisions, rejections, and strongest objection. In fallback mode, title this **Separate reviewer pass** and state that it was not an independent subagent.
7. **Claim ledger**
8. **Uncertainty and next decisive step**

Attribute substantive contributions to the correct agent. Do not dump internal transcripts or hidden chain-of-thought, and do not imply unanimity when disagreement remains. Keep the audit fields, but merge headings for small tasks when that improves clarity; rigor does not require unnecessary length.

## Long-Running Research Archive

In both solo and four-agent execution, continuous work exceeding **30 minutes of actual wall-clock time** requires one complete Google Drive archive record for that round. Record the start time at the beginning of long work; do not split one run into half-hour rounds or count agent-hours. Continue project round numbering across dates and conversations. At the start of long work, read [Project Archives and Latest Progress](references/research-archive.md) and resolve the existing project folder and numbering. If no corresponding project folder exists, create one; an explicit user instruction not to upload takes precedence.

At an actionable checkpoint after crossing the threshold, create or update the round's single authoritative Markdown or Google Doc (or one ZIP containing the full report and necessary attachments). All subsequent saves and corrections use the same Drive file ID. Complete and verify it at the end, including unsuccessful rounds. Keep a persistent project-root `00_最新进展` or existing equivalent; initialize it with the current state, then update it only for major advances, withdrawals, or corrections. Read the full archive reference for record contents, numbering collisions, verification, and local fallback when Drive is unavailable. Return the round identity and verified Drive link; explicitly label an unuploaded local record.
