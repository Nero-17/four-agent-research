# Four-Agent Research

A reusable Codex skill for rigorous research and reasoning, with four-agent execution by default and ordinary single-researcher execution when you request no subagents.

It is designed for complex scientific, technical, policy, strategic, historical, and other questions where a plausible answer is not enough. The workflow tracks material claims, tests conjectures, searches for disconfirming evidence, and distinguishes verified progress from effort.

## Solo Research / 单人研究

Say `不要 sub agent`, `单独工作`, or `work alone` to keep all work with the current agent. This takes precedence over the default four-agent workflow, even when delegation tools are available. No helpers, extra tasks, or simulated agent personas are created. Evidence gathering, substantive advancement, and explicitly labeled self-review remain required; self-review is not independent validation.

Solo execution defaults to Standard Research and can also use Startup or Bottleneck Research as the question requires. Execution mode and research strategy are separate choices.

```text
$four-agent-research 不要 sub agent，单独研究这个问题；遵守逐轮归档和最新进展规则。
$four-agent-research 单人瓶颈研究：先整理大方向及各自方法，逐项尝试，按 5% / 1% 两阶段规则推进。
```

## Roles (Four-Agent Execution)

- **Agent 0: Lead Researcher** frames the question, delegates work, adjudicates disagreements, and owns the final answer.
- **Agent 1: Evidence and Conjectures** maps the literature and evidence, reconciles definitions, and proposes testable claims.
- **Agent 2: Advancement and Falsification** attempts proofs, calculations, experiments, implementations, counterexamples, or other concrete checks.
- **Agent 3: Independent Reviewer** audits sources and reasoning, challenges hidden assumptions, and estimates verified progress.

The workflow uses a stable claim ledger with `PROVED`, `SUPPORTED`, `CONDITIONAL`, `CONJECTURAL`, `CONTESTED`, `REFUTED`, and `OPEN` statuses.

## Install

In Codex, invoke the built-in installer and provide this repository:

```text
$skill-installer

Install the four-agent-research skill from:
https://github.com/Nero-17/four-agent-research
```

For a repository-scoped installation, clone it into that repository's skills directory:

```bash
git clone https://github.com/Nero-17/four-agent-research.git .agents/skills/four-agent-research
```

Codex normally detects newly installed skills automatically. Restart Codex if it does not appear.

## Use

Invoke it explicitly:

```text
$four-agent-research Investigate whether the proposed policy is likely to achieve its stated objective, including the strongest counterevidence.
```

Codex may also select the skill automatically when a request clearly matches its description.

## Research Modes

Each research round uses one mode. Specify it in the request, or let Agent 0 select it from the project's current state:

| Mode | What it does | Automatic selection |
| --- | --- | --- |
| 启动研究 / Startup Research | Broad literature search, an organized evidence map and candidate gaps, and at least one minimal concrete probe of every promising shortlisted direction to assess difficulty. | A new or reframed topic lacks an adequate literature map or tested directions. |
| 标准研究 / Standard Research | Sustained, reviewed advancement until research benefit diminishes, useful progress is clearly blocked, or the objective or a resource limit is reached. | An established question has a plausible next route; also the provisional fallback when context is inconclusive. |
| 瓶颈研究 / Bottleneck Research | An extensive numerical or computational experiment campaign, renewed broad literature search, and concrete trials of unconventional or niche methods. | Repeated substantive attempts have stalled or established approaches are exhausted. |

An explicit user choice takes precedence. When selecting automatically, a documented impasse takes priority over startup criteria; one failed attempt or missing access alone is not a research bottleneck. The skill does not run all three modes by default or silently switch modes to prolong a round. Numerical patterns are hypotheses to test, not proofs. A domain where numerical experiments are inappropriate uses a disclosed, reproducible alternative.

Examples:

```text
$four-agent-research 启动研究：梳理这个新方向的文献，寻找空缺并对每个 promising 方向做一次最小尝试。
$four-agent-research 标准研究：继续推进当前猜想，到收益递减或明显受阻时报告。
$four-agent-research 瓶颈研究：针对反复卡住的引理，扩大数值实验、重新搜索文献并尝试偏门方法。
$four-agent-research Continue this project and choose the research mode from the current evidence and prior attempts.
```

Every end-of-round report starts by naming the mode actually used, for example `本次研究模式：标准研究。` or `Research mode: Standard Research.` It also explains whether selection was explicit or automatic and why the round stopped. See [Research Modes](references/research-modes.md) for the mode-specific procedures.

## Adaptive Reasoning Effort

Effort is selected per subtask and phase, independently of the research mode or agent role:

| Subtask | Automatic target |
| --- | --- |
| Routine retrieval, classification, fact extraction, or result organization | `high` |
| Literature analysis, gap finding, conjectures, experiment design, or other substantive research reasoning | `xhigh` (default) |
| Critical proofs, difficult counterexamples, core-conclusion review, or adjudication of substantive disagreement | `max` |
| A precisely identified exceptionally difficult gap with a concrete promising next attempt and sufficient budget | `ultra`, when supported |

User-specified settings and resource limits take precedence. Agent 0 reassesses reasoning complexity, the consequence of error, and the expected benefit of deeper reasoning at phase boundaries. Missing data, access, or compute is not a reason to blindly increase effort. Running a large numerical experiment campaign does not automatically require the highest reasoning effort.

This is an adaptive policy, **not a hard runtime override**. The skill instructs the agent to use supported spawn or subsequent-turn controls and verify effective settings when available. Unsupported automatic targets fall back to compatible lower levels, such as `max` to `xhigh`, without changing the user's model. If controls or verification are unavailable, research can continue under existing settings with that limitation disclosed. The skill does not modify global configuration, change an already-running parent turn, or replace persistent agents merely to change effort.

Reports preserve the mode-first opening, then distinguish target, requested, and verified effective effort, including unknown values and compatibility fallbacks. See [Reasoning Effort](references/reasoning-effort.md) for the decision procedure, runtime boundaries, and examples. These are research-workflow defaults, not a claim of experimentally optimal effort settings.

## Bottleneck Search: Directions, Methods, and Two Stages

Map major directions and the concrete methods under each, then focus on one method's decisive obstacle at a time. Record actual tests, outcomes, assumptions, remaining gaps, subjective viability estimates, uncertainty, and reopening conditions.

- **Stage 1:** suspend a method when evidence supports a chance of resolving the scoped target **below 5%**. Sweep the mapped methods across all scoped directions.
- **Stage 2:** only after every mapped method is suspended or rigorously excluded, revisit stage-1 methods using **below 1%** as the suspension threshold. Methods at 1–5% can still be pursued. Reassessment needs a meaningful new test or re-examination of the earlier evidence, not identical repetitions.

These are subjective feasibility thresholds under stated assumptions and resources, not measured probabilities or proofs of impossibility. Exact threshold values are not below threshold; uncertain, untested, or resource-blocked methods cannot count as eliminated. Exhausting a scoped map does not prove that all possible approaches fail. Both stages respect the current budget and round identity. See [Direction and Method Search](references/bottleneck-methods.md).

## Long-Running Research Records

In either execution mode, one continuous work session exceeding 30 minutes of real wall-clock time requires a complete Google Drive record. Two hours of continuous work remains one round. Subtasks, updates, compaction, and automatic continuations do not reset the clock, and user absence between completed runs does not count. Do not prolong work to reach the threshold.

Use the corresponding project folder, creating a clearly named one if absent. Continue existing project round numbers across dates and conversations. Each round has one authoritative Markdown or Google Doc in the established format, for example `主题_R045_YYYY-MM-DD_完整研究记录`; all checkpoint, final, and correction saves update the same Drive file ID. Essential attachments may instead be bundled with the full report into one ZIP. Historical archives are not automatically migrated or renumbered.

Keep a single persistent `00_最新进展` (or existing equivalent) in the project root. Read it first when resuming research. Initialize it with the current state, then update the same file only for major advances, decisive counterexamples, key proofs, or substantial withdrawals/corrections. It links to the supporting round records and distinguishes proof, conditional results, finite computational support, conjectures, and open gaps.

Records include timing, conversation source, objectives, auditable arguments, verification evidence, failed routes, corrections, exact remaining gaps, and next steps. Mathematical proofs avoid unnecessary abbreviation variables. Archive at an actionable checkpoint after crossing the threshold, finalize and verify at the end, and return the round identity and Drive link. Routine archiving is authorized by this workflow; explicit no-upload instructions override it. If Drive is unavailable, retain the complete record locally and say **尚未上传 / not uploaded**, without claiming success or creating a scheduled job. Personal folder IDs stay outside this public repository. See [Project Archives and Latest Progress](references/research-archive.md).

## Independence and Fallbacks

In four-agent execution, use three persistent subagent sessions when genuine delegation is available and authorized; otherwise disclose separate role passes as a fallback. An explicit solo request instead uses normal single-researcher work and labeled self-review. Neither self-review nor simulated passes are independent-agent validation.

The skill authorizes its selected research execution and routine project archiving, subject to active permissions and user choices. It does not authorize unrelated publication, purchases, account changes, or other external mutations.

## Files

```text
four-agent-research/
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- research-modes.md
|   |-- reasoning-effort.md
|   |-- bottleneck-methods.md
|   `-- research-archive.md
|-- README.md
`-- LICENSE
```

The skill follows the [Open Agent Skills specification](https://agentskills.io/) and the [OpenAI skill authoring guidance](https://learn.chatgpt.com/docs/build-skills).

## License

MIT
