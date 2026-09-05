---
name: four-agent-research
description: Run a rigorous four-agent research workflow for complex questions that benefit from evidence gathering, testable conjectures, concrete advancement, adversarial verification, and accountable synthesis. Use across scientific, technical, policy, strategic, historical, or other research domains; do not use for simple lookups or routine execution.
---

# Four-Agent Research

Investigate the user's question through four distinct roles. Agent 0 is the current parent agent. When genuine subagent or delegation tools are available, create one persistent subagent session for each of Agents 1-3 and reuse it for follow-up work. Do not create user-visible tasks or conversations merely to simulate subagents. If a role session fails, Agent 0 may replace it once and must disclose the replacement. Invoking this skill authorizes those research delegations, but it does not authorize external writes, purchases, publication, account changes, or other consequential side effects.

If true subagents are unavailable, perform three clearly separated role passes and disclose that fallback. Never pretend simulated passes were independent agents; label Agent 3's output as a separate reviewer pass rather than an independent-agent review.

## Shared Standard

- Convert the request into a precise research question, scope, definitions, decision criteria, and deliverable before delegating.
- Separate sourced facts, observations, calculations, inferences, hypotheses, and value judgments.
- Use the strongest available evidence for the domain: primary sources when they directly establish a claim, and authoritative or systematic syntheses when they better represent the evidence base. Cite sources close to the claims they support.
- Search for disconfirming evidence, boundary cases, alternative explanations, and counterexamples.
- Do not treat agreement among agents as validation. Agent 0 adjudicates by evidence and valid reasoning.
- Preserve uncertainty. State what would change the conclusion and what remains unknown.
- Keep all consequential external actions subject to the user's authorization and the active environment's permission rules.

## Agent 0: Lead Researcher

Agent 0 owns the full result and is accountable to the user for the other agents' work.

1. Frame the long-term objective when one exists and the exact objective for this run. For a one-shot question, use the user's requested outcome as the objective without inventing a larger project.
2. Before seeing results, establish domain-appropriate standards of evidence and an outcome-based weighted milestone list for measuring progress toward the user's goal.
3. Delegate bounded, role-specific briefs to Agents 1-3. Give them the question, scope, definitions, raw materials, and required output format. Avoid accidental duplicate work, while requiring deliberate overlap for independent verification.
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

- Select the highest-value tractable claim, explaining the choice.
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

Use this default sequence, adapting only when dependencies require it:

1. Agent 0 frames the problem, evidence standard, and milestones. For long-running research, resolve the report-folder preference under Long-Running Research Archive before the first round.
2. Agent 1 and Agent 2 begin in parallel when Agent 2 can independently attack the core question; otherwise Agent 1 goes first and Agent 2 receives its ranked conjectures.
3. Agent 3 first receives the original brief and evaluation criteria, forms its own review checklist and search plan, and only then receives the evidence map, Agent 2's work, and raw supporting artifacts. It never receives Agent 0's tentative conclusion before review.
4. Agent 0 applies the adoption gate and adjudicates by evidence, not votes.
5. Run targeted repair-and-review iterations only while their expected value is material, then stop with a clear unresolved-gap statement.
6. After a long-running research round, complete the English TeX archive procedure below when the user has enabled it.

## Report to the User

Lead with the useful answer, then provide a compact audit trail containing:

1. **Long-term objective**
2. **This run's objective**
3. **Agent 3 progress assessment**: percentage and range, confidence, and basis, or `not estimable`
4. **Agent 0 synthesis**: answer and recommended interpretation or decision
5. **Evidence and advancement**: the strongest sources and Agent 2's concrete result
6. **Independent review**: accepted claims, revisions, rejections, and strongest objection. In fallback mode, title this **Separate reviewer pass** and state that it was not an independent subagent.
7. **Claim ledger**
8. **Uncertainty and next decisive step**

Attribute substantive contributions to the correct agent. Do not dump internal transcripts or hidden chain-of-thought, and do not imply unanimity when disagreement remains. Keep the audit fields, but merge headings for small tasks when that improves clarity; rigor does not require unnecessary length.

## Long-Running Research Archive

### Scope and Destination

This archive applies only to sustained research rounds: extended investigation, proof or falsification work, experiments, or scheduled research iterations undertaken to advance a project, whether or not they succeed. Ordinary questions, explanations, quick lookups, and brief follow-up answers do not trigger it, even when they use the four roles. Do not classify work by response length alone.

Before the first applicable round, check the current project's instructions and prior user decisions for a Google Drive report folder or an explicit opt-out. If neither exists, ask whether the user wants to set a report folder and, if so, request its link or folder ID. A folder explicitly designated for these reports authorizes creating new progress reports there, subject to active permissions; an unrelated Drive link is not a report destination. Reuse this choice for subsequent rounds in that project. Do not infer one project's destination or opt-out for another project.

If the user declines, skip report-file generation and upload, continue the research normally, and do not ask again unless the user reopens the choice. The normal conversational answer still applies. If no answer has arrived, continue otherwise authorized research without uploading and state that archiving is not configured. Retain the folder or opt-out in existing project/task context when supported; do not claim cross-session persistence without a supported mechanism. Never put personal folder IDs or account details in this public skill.

### English TeX Report

When archiving is enabled, Agent 0 must create and upload one standalone English `.tex` progress report at the end of every long-running research round, including rounds with negative results, unresolved gaps, or blocked progress. Do not substitute a chat summary, Google Doc, or PDF for the TeX source.

Start the report with the overall research title, long-term objective, this round's objective, and Agent 3's progress assessment under the Progress Estimate rules. Include the baseline and changes since the previous round, substantive results with reproducible proofs or methods, counterexamples and failed routes, sources, review findings, the claim ledger and status changes, remaining gaps, and the next decisive steps. Clearly distinguish proved, conditional, conjectural, and unverified results, and disclose simulated reviewer passes. Record the round's start/end timestamps and timezone. Use a complete LaTeX document with escaped special characters and self-contained references; check its structure and compile when a suitable compiler is available. If compilation is unavailable, say so without claiming it compiled.

### Filename and Upload

Use exactly `<overall-title>-YYYY-MM-DD-<round>.tex`, for example `Erdos-Similarity-Problem-2026-09-05-2.tex`. Keep the overall project title stable across rounds, not the current subproblem's title; replace only characters unsuitable for a filename. Use the round's completion date in the user's configured timezone, or UTC with an explicit note when no timezone is available.

The round is a positive integer starting at 1 each day for that project in its designated folder. Before choosing it, list all pages of matching reports for that title and date and reconcile them with any known rounds in the current project context; use the next unused round after the highest existing or recorded round, not the file count. Do not restart at 1 merely because this is a new conversation. Reuse the same round when retrying the same report.

Create a new file without overwriting, editing, or deleting historical reports. Recheck names immediately before upload. Google Drive can contain duplicate names, so a filename is not an atomic reservation: after creation, check for a concurrent naming collision and, if necessary, renumber only this round's newly created file after relisting. If a collision cannot be resolved safely, disclose it. After an uncertain upload response, check for an already-created report before retrying to avoid duplicate reports.

Use the available authorized Drive connector or supported API. Verify the created file's ID, parent folder, filename, and readable TeX content before reporting success; include its Drive link in the final response. If tools, access, or upload verification are unavailable, state the exact limitation and do not claim the report was saved. An upload failure is not a user opt-out: preserve the prepared report in an allowed accessible location when possible and report the remaining upload step. Do not switch folders, change sharing permissions, or bypass authorization.
