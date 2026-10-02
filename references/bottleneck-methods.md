# Direction and Method Search: Two Stages

Use this protocol when research reaches a documented bottleneck, in solo or four-agent execution. It is a method-allocation policy, not a proof of mathematical impossibility. Keep the existing research strategy and round identity; passing from stage 1 to stage 2 does not start a new round or authorize additional time, compute, or agents.

## Map Directions Before Focusing

State the exact target and bottleneck. Organize a bounded, explicitly scoped map of **major directions**, each containing distinct **concrete methods**. A direction is a broad approach; a method is a specific mechanism for overcoming the obstacle. Explain the connection, required assumptions, missing lemma or resource, and cheapest discriminating test. New methods may be added with provenance; never claim to have enumerated every conceivable method.

Maintain stable direction/method IDs and a ledger containing: target and scope; method mechanism; assumptions and dependencies; attempted tests and actual outcomes; precise failure or remaining gap; stage; viability estimate and uncertainty; evidence for the estimate; disposition; and the evidence that would justify reopening it. Keep earlier estimates and reasons when revising judgments. This is separate from the claim ledger: suspending a method does not refute its target theorem.

Assign every concrete method an ID in the form `method-001`, `method-002`, and so on, starting at `method-001` for a new project's method ledger. Use one project-wide sequence across all major directions, not a separate sequence per direction. Read the existing ledger before assigning IDs and continue after the highest assigned number; use at least three digits, continuing to `method-1000` if needed. Preserve IDs across conversations, research rounds, stage-1 suspension, and stage-2 reopening. Never renumber or reuse a retired method's ID. A renamed or refined version of the same method keeps its ID; a substantively distinct method or separately tested variant gets the next ID and a link to its parent or related method. When introducing these IDs into an older ledger, retain old labels as aliases so historical references remain traceable. Include method IDs in attempt records, review findings, stage decisions, and round archives, and use them when referring to methods in the latest-progress file.

At a bottleneck, focus substantive advancement on one concrete method and its decisive obstacle at a time, then review and update the ledger before moving on. In four-agent execution, evidence gathering and review may support that focal attempt; do not disperse advancement across many superficial simultaneous attempts. In solo execution, the same researcher performs the work and self-review.

## What the Percentages Mean

Estimate the subjective chance that the specified method can resolve the stated target, under explicit assumptions and a stated feasible continuation/resource horizon. These are reasoned feasibility estimates, not calibrated statistical probabilities, theorem-truth probabilities, or percentages of work completed. Do not silently redefine the target, horizon, or method between stages to cross a threshold.

Base estimates on concrete attempts, structural obstacles, relevant results, and counterexamples to required premises. Prefer an honest range where exact precision is unjustified. If the range crosses the threshold or evidence is inadequate, mark viability uncertain and choose a discriminating test; do not force a point estimate. Lack of access, elapsed effort, unfamiliarity, one failed example, or an untested idea alone does not justify a below-threshold judgment.

Use `ACTIVE`, `UNTESTED`, `BLOCKED`, `VIABILITY_UNCERTAIN`, `SUSPENDED_STAGE_1`, `SUSPENDED_STAGE_2`, or `IMPOSSIBLE_IN_SCOPE` as method dispositions. The last requires an actual proof excluding that precise method under stated conditions; a low estimate alone never warrants it. A proof excluding one formulation need not exclude broader variants.

## Stage 1: Below 5%

For each mapped method, perform the most informative feasible probe or inspect decisive existing evidence. Pursue viable methods by focused attempts. Suspend a method for stage 1 only when the evidence supports viability **strictly below 5%**; record the basis, uncertainty, obstacle, and reopening condition. Exactly 5% is not below the threshold. A range qualifies only if its upper end is below 5%.

Sweep the scoped direction/method map, working through alternatives rather than abandoning an entire direction because one method failed. A direction is exhausted for this stage only when every mapped method has been suspended or rigorously excluded in scope. `UNTESTED`, `BLOCKED`, and `VIABILITY_UNCERTAIN` entries are not eliminated methods.

Enter stage 2 only after **all mapped methods in all scoped directions** have stage-1 suspension or rigorous exclusion, and continued work remains authorized and within budget. If a viable route survives, develop it. If resources end before the sweep is complete, report the incomplete map rather than claiming all methods failed.

## Stage 2: Below 1%

Reopen the methods suspended in stage 1, preserving the earlier record. Use a more permissive continuation threshold: now suspend only if the evidence supports viability **strictly below 1%**. Exactly 1% is not below it; a 1–5% method can remain worth pursuing in stage 2. Thresholds are not cumulative probabilities.

For each method, identify what a second inspection can add: a previously untested variant, relaxed assumption, new source, deeper bounded test, or challenge to the earlier obstacle. Perform that discriminating work when feasible. A method already credibly below 1% still gets its basis re-examined but need not repeat identical costly tests. Do not reopen a proved impossibility under unchanged conditions merely by changing the numerical threshold; check the proof or explicitly broaden the formulation.

Log new evidence and any changed judgment. If all methods are also suspended in stage 2 or excluded, report the unresolved bottleneck, the coverage limits, and what new idea, evidence, or resource could change the assessment. Do not declare the problem impossible, invent a third stage, or recycle exhausted attempts indefinitely. Stop earlier if the target is solved, useful discrimination is unavailable, the user stops, or a resource limit is reached; carry the ledger and current stage into the same round archive and any later authorized continuation.
