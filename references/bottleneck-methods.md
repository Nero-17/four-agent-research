# Direction and Method Search: Screening and Outcomes

Use this protocol when research reaches a documented bottleneck, in solo or four-agent execution. It is a method-allocation policy, not a proof of mathematical impossibility. Keep the existing research strategy and round identity; passing from initial screening to rescreening does not start a new round or authorize additional time, compute, or agents.

## Map Directions Before Focusing

Maintain the project-level [Excel method tracker](method-workbook.md) alongside this ledger. Each method has one current row, including whether it has entered initial-screening suspension; preserve previous suspension events when entering rescreening.

Use [Shared Research Identifiers](research-identifiers.md) throughout this ledger, including `direction-000`, `problem-000`, `gap-000`, and `experiment-000` where applicable, while retaining the `method-001` starting rule below.

State the exact target and bottleneck. Organize a bounded, explicitly scoped map of **major directions**, each containing distinct **concrete methods**. A direction is a broad approach; a method is a specific mechanism for overcoming the obstacle. Explain the connection, required assumptions, missing lemma or resource, and cheapest discriminating test. New methods may be added with provenance; never claim to have enumerated every conceivable method.

Maintain stable direction/method IDs and a ledger containing: target and scope; method mechanism; assumptions and dependencies; attempted tests and actual outcomes; precise failure or remaining gap; stage; viability estimate and uncertainty; evidence for the estimate; disposition; and the evidence that would justify reopening it. Keep earlier estimates and reasons when revising judgments. This is separate from the claim ledger: suspending a method does not refute its target theorem.

Assign every concrete method an ID in the form `method-001`, `method-002`, and so on, starting at `method-001` for a new project's method ledger. Use one project-wide sequence across all major directions, not a separate sequence per direction. Read the existing ledger before assigning IDs and continue after the highest assigned number; use at least three digits, continuing to `method-1000` if needed. Preserve IDs across conversations, research rounds, initial-screening suspension, and rescreening reopening. Never renumber or reuse a retired method's ID. A renamed or refined version of the same method keeps its ID; a substantively distinct method or separately tested variant gets the next ID and a link to its parent or related method. When introducing these IDs into an older ledger, retain old labels as aliases so historical references remain traceable. Include method IDs in attempt records, review findings, screening decisions, and round archives, and use them when referring to methods in the latest-progress file.

At a bottleneck, focus substantive advancement on one concrete method and its decisive obstacle at a time, then review and update the ledger before moving on. In four-agent execution, evidence gathering and review may support that focal attempt; do not disperse advancement across many superficial simultaneous attempts. In solo execution, the same researcher performs the work and self-review.

## What the Percentages Mean

Estimate the subjective chance that the specified method can resolve the stated target, under explicit assumptions and a stated feasible continuation/resource horizon. These are reasoned feasibility estimates, not calibrated statistical probabilities, theorem-truth probabilities, or percentages of work completed. Do not silently redefine the target, horizon, or method between stages to cross a threshold.

Base estimates on concrete attempts, structural obstacles, relevant results, and counterexamples to required premises. Prefer an honest range where exact precision is unjustified. If the range crosses the threshold or evidence is inadequate, mark viability uncertain and choose a discriminating test; do not force a point estimate. Lack of access, elapsed effort, unfamiliarity, one failed example, or an untested idea alone does not justify a below-threshold judgment.

Maintain separate fields: **screening pass** (`INITIAL` / 初筛 or `RESCREEN` / 复筛), **screening decision** (`UNTESTED`, `PASSED`, `SUSPENDED`, `VIABILITY_UNCERTAIN`, `BLOCKED`, or `IMPOSSIBLE_IN_SCOPE`), **outcome status** as defined below, and **current focus**. The screening decision always belongs to its identified screening pass. `IMPOSSIBLE_IN_SCOPE` requires a proof excluding that precise formulation, not a low estimate. Research run IDs (`round-...`) are a third, unrelated notion: neither screening transitions nor outcome transitions start a new research round.

## Initial Screening / 初筛: Below 5%

For each mapped method, perform the most informative feasible probe or inspect decisive existing evidence. Pursue viable methods by focused attempts. Suspend a method for initial screening only when the evidence supports viability **strictly below 5%**; record the basis, uncertainty, obstacle, and reopening condition. Exactly 5% is not below the threshold. A range qualifies only if its upper end is below 5%.

After substantive assessment, record 初筛通过 (`INITIAL` + `PASSED`) when the evidence-backed estimate is at least 5%, or the lower end of a defensible range is at least 5%, with a concrete feasible next attempt. Unassessed, blocked, or uncertain methods are not automatic passes. A range straddling 5% remains uncertain. A first screening pass qualifies the method for outcome status 第一阶段通过, not 第二阶段通过.

Sweep the scoped direction/method map, working through alternatives rather than abandoning an entire direction because one method failed. A direction is exhausted for this stage only when every mapped method has been suspended or rigorously excluded in scope. `UNTESTED`, `BLOCKED`, and `VIABILITY_UNCERTAIN` entries are not eliminated methods. Downstream outcome failure alone is also not a screening suspension: reassess the screening criterion separately if needed.

Enter rescreening only after **all mapped methods in all scoped directions** have initial-screening suspension or rigorous exclusion, and continued work remains authorized and within budget. If a viable route survives, develop it. If resources end before the sweep is complete, report the incomplete map rather than claiming all methods failed.

## Rescreening / 复筛: Below 1%

Reopen the methods suspended in initial screening, preserving the earlier record. Use a more permissive continuation threshold: now suspend only if the evidence supports viability **strictly below 1%**. Exactly 1% is not below it; a 1–5% method can remain worth pursuing in rescreening. Record 复筛通过 (`RESCREEN` + `PASSED`) only after an assessment supporting at least 1% (or a range wholly at/above 1%) and a feasible next attempt. This can qualify a newly viable method for 第一阶段通过 but does not erase an existing downstream failure. Thresholds are not cumulative probabilities.

For each method, identify what a second inspection can add: a previously untested variant, relaxed assumption, new source, deeper bounded test, or challenge to the earlier obstacle. Perform that discriminating work when feasible. A method already credibly below 1% still gets its basis re-examined but need not repeat identical costly tests. Do not reopen a proved impossibility under unchanged conditions merely by changing the numerical threshold; check the proof or explicitly broaden the formulation.

Log new evidence and any changed judgment. If all methods are also suspended in rescreening or excluded, report the unresolved bottleneck, the coverage limits, and what new idea, evidence, or resource could change the assessment. Do not declare the problem impossible, invent a third stage, or recycle exhausted attempts indefinitely. Stop earlier if the target is solved, useful discrimination is unavailable, the user stops, or a resource limit is reached; carry the ledger and current screening pass into the same round archive and any later authorized continuation.

## Outcome Stages / 成果阶段

These are independent of 初筛/复筛 and use a separate outcome status:

| Code | User-facing status | Meaning |
| --- | --- | --- |
| `PENDING` | 待评估 | No completed positive screening assessment yet |
| `PASSED_STAGE_1` | 第一阶段通过 | Passed the applicable screening and is eligible for focused development |
| `ADVANCING_STAGE_1` | 第一阶段通过，正在推进 | The selected method is being developed and tested for global consequences |
| `GLOBAL_ASSESSMENT_PENDING` | 第一阶段通过，全局结论待判定 | Evidence is insufficient for the downstream decision |
| `OUTCOME_BLOCKED` | 第一阶段通过，推进受阻 | A resource or access obstacle prevents useful development |
| `FAILED_AFTER_STAGE_1` | 第一阶段通过但后续失败 | Further investigation supports a chance below 5% of obtaining a substantive global conclusion for the final objective |
| `PASSED_STAGE_2` | 第二阶段通过 | A clear, checkable substantive global conclusion has actually been obtained and verified |

Before concentrated advancement, state the final objective and what would constitute a substantive global conclusion for it, with scope, quantifiers, and verification criteria. A global theorem, a proved reduction materially advancing the final objective, or a verified decisive counterexample may qualify if its relevance is explicit. A local lemma, toy example, finite computational pattern, hopeful route, or unresolved prerequisite does not qualify merely by being relabeled global. A global conclusion can materially advance the final objective without solving all of it; specify what remains open. Do not lower or redefine the success criterion to earn a pass.

Prioritize one passed method at a time and queue the others, using evidence, expected progress, and tractability to select the focal method ID. Concentrate available effort on its decisive gap rather than completing a broad screening list for its own sake. Four-agent roles support the same focal method; solo performs the same work alone. Continue substantive advancement and review until a checkable result is obtained, new evidence changes the assessment, useful continuation is blocked/exhausted, or a user/resource limit is reached. Full effort does not authorize unlimited resources or ignoring stop instructions.

For each previously passed method, assess **the chance of producing a substantive global conclusion for the final objective** separately from screening viability. State the event, assumptions, feasible continuation horizon, evidence, and uncertainty for each estimate; do not copy the screening estimate into this field. After actual further investigation, a defensible estimate strictly below 5% (or range with upper end below 5%) yields `FAILED_AFTER_STAGE_1`. Exactly 5% supports continued consideration, not failure. Inadequate evidence or a range straddling 5% yields pending judgment; lack of resources alone yields a blocker. Record failure reasons and reopening conditions, release that method from current focus, and choose another eligible method or resume screening.

`PASSED_STAGE_2` requires an **already obtained** precise global statement, applicable assumptions, stable conclusion ID (such as `theorem-...` or `counterexample-...`), proof or domain-appropriate verification record, and explicit explanation of its material effect on the final objective. Apply the shared adoption gate; for a mathematical claim, computational support without a proof is insufficient. Solo labels its checks self-review and never claims independent validation. A predicted probability of 5%, 50%, or 99% cannot substitute for an actual verified result.

Keep screening and outcome judgments independent. A method may show 复筛通过 while its outcome remains 第一阶段通过但后续失败; the lower 1% rescreening threshold does not override the separate 5% global-conclusion criterion. Do not automatically reopen a failed method for full focused development just because it passes rescreening: require new evidence or a meaningful variant addressing the recorded failure, and log the reassessment. Method failure is not a proof that the final objective is impossible. If all eligible methods fail downstream and no further discriminating work is available, report that impasse without inventing screening suspensions to force rescreening eligibility. Preserve all earlier decisions and actual results, including later corrections or withdrawals.

## Legacy Labels

Preserve old archive text and method IDs. Map historical `SUSPENDED_STAGE_1` / 第一阶段放弃 to 初筛放弃 and `SUSPENDED_STAGE_2` / 第二阶段放弃 to 复筛放弃, retaining their evidence and aliases. Existing `PASSED_STAGE_1` remains a first-outcome-stage pass; record its supported initial-screening decision separately. Old 第二阶段判定 described rescreening and must never become evidence of 第二阶段通过. An old rescreening pass maps only to 复筛通过; outcome promotion requires the criteria above.
