# Research Modes

Read the section for the selected mode. All modes retain the SKILL.md review, claim-ledger, progress-estimation, and authorization requirements. Broader exploration never lowers the evidentiary standard.

## Startup Research

Objective: establish the research landscape and learn which gaps are both valuable and approachable.

- Agent 1 automatically conducts a broad, scope-appropriate literature search: foundational and recent work, surveys, competing approaches, relevant adjacent fields, terminology variants, and backward/forward citation trails. Organize findings by question, method, assumptions, established result, and limitation; keep the shared search log and disclose coverage limits. Do not call an unbounded literature search complete.
- Agent 1 proposes precise candidate gaps and explains their value, relation to the closest prior work, and what would invalidate the claimed novelty. A gap in retrieved literature is provisional, not proof that nobody has addressed it.
- Agent 0 defines a promising shortlist using importance, plausibility, and feasibility within the available budget. Agent 2 performs at least one minimal concrete probe for **every** shortlisted promising direction before committing to a main route. A probe may be a small-case calculation, proof fragment, counterexample search, toy experiment, baseline implementation, or domain-appropriate evidence check; a verbal promise to try is not a probe.
- For each probe record the question, method and result, observed difficulty, assumptions exposed, first obstacle, and cheapest next discriminating test. Rank directions again using those observations, not initial enthusiasm. If a resource limit prevents a probe, label that direction untested and explain the shortfall.
- Agent 3 checks the literature coverage, gap claims, probe validity, and whether the ranking overinterprets easy toy cases or overlooks contrary evidence.

Stop after the scoped literature map and gap shortlist are assembled and each promising direction has been probed, or an explicit limit prevents completion. Deliver the organized evidence map, a direction-by-direction probe comparison, difficulty estimates with uncertainty, and a recommended next route. This round need not solve the selected project.

## Standard Research

Objective: make sustained, checkable progress on the strongest available route.

- Agent 0 chooses the highest-value tractable subproblem. Agent 1 maintains targeted literature support and precise conjectures; Agent 2 develops proofs, falsifications, calculations, experiments, or other substantive results; Agent 3 independently reviews material advances before adoption.
- Continue through meaningful advancement and repair cycles while the next cycle is likely to change a material claim, close a concrete gap, improve a decision, or eliminate a viable route. Do not stop merely after producing a plausible answer or the first minor result.
- At checkpoints assess **marginal research benefit**, not output length or raw activity. Repeated reformulations with no stronger evidence, increasingly costly tests that no longer distinguish alternatives, and successive attempts that expose the same unresolved prerequisite are signs of diminishing returns.
- Stop and report when further work has low expected information or advancement value, a clear blocker makes useful continuation unavailable, the run's objective is achieved, or an explicit resource limit is reached. Distinguish a scientific obstacle from missing data, access, compute, or time. Agent 3 reviews whether the stated stopping reason is supported by the actual attempts.

Deliver the validated change from the baseline, attempted and failed routes, exact reason for stopping, smallest remaining gap, and highest-value next step. A blocked standard round may recommend Bottleneck Research for a future round; it does not silently switch modes now.

## Bottleneck Research

Objective: generate and discriminate new routes around a documented research obstacle.

- Agent 0 states the precise bottleneck, failed approaches, and assumptions that may be relaxed. Plan a bounded but substantially broader experiment-and-search campaign than in Standard Research, reserving resources for verification rather than consuming everything on discovery.
- Agent 2 performs extensive, systematic numerical or computational experiments to find patterns: vary parameters and scales, enumerate small cases, search for counterexamples, compare baselines, and repeat stochastic tests across seeds where relevant. Adapt successive batches to the observations. Record methods, inputs, code or reproducible procedures, precision, outputs, and null or contrary results. One token toy example is not an extensive campaign.
- Treat discovered numerical patterns as hypotheses. Check finite-size effects, numerical instability, selection effects, and alternative explanations; use fresh cases or held-out ranges for confirmation. Move to exact calculations or proof attempts when a pattern provides a plausible route.
- Agent 1 simultaneously renews a broad literature search, including alternative terminology, adjacent disciplines, older or overlooked results, negative results, and methods absent from the current project's bibliography. Explain precisely which obstacle each imported idea might address.
- Agents 1 and 2 deliberately explore unconventional or niche methods when there is a concrete connection to the bottleneck: reformulations, dual or inverse problems, special-case models, cross-disciplinary analogies, or nonstandard tools. Record the mapping of assumptions, run a cheap falsification probe before expensive use, and do not equate obscurity with credibility.
- Where numerical experiments are not meaningful for the domain, explain why and use a reproducible empirical, comparative-case, or structured counterexample campaign instead. Do not invent numbers or claim that unrun experiments succeeded. Any unavailable component remains a disclosed limitation.
- Agent 3 stress-tests the emergent patterns, reproduces decisive experiments when feasible, audits the renewed search, and challenges transfers whose assumptions do not match. Empirical regularities remain appropriately qualified in the claim ledger; they are not mathematical proof.

Stop when a credible new route has survived initial review and is ready for focused development, further diverse probes/searches cease to produce useful discrimination, or an explicit limit is reached. Deliver the experiment matrix and patterns, new literature connections, unconventional approaches tried and rejected, surviving hypotheses, and the next decisive test. Report an unresolved impasse honestly when no route survives.
