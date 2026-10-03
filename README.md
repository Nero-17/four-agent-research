# Four-Agent Research

A reusable Codex skill for rigorous research and reasoning, with four-agent execution by default and ordinary single-researcher execution when you request no subagents.

It is designed for complex scientific, technical, policy, strategic, historical, and other questions where a plausible answer is not enough. The workflow tracks material claims, tests conjectures, searches for disconfirming evidence, and distinguishes verified progress from effort.

## Solo Research / 单人研究

Say `不要 sub agent`, `单独工作`, or `work alone` to keep all work with the current agent. This takes precedence over the default four-agent workflow, even when delegation tools are available. No helpers, extra tasks, or simulated agent personas are created. Evidence gathering, substantive advancement, and explicitly labeled self-review remain required; self-review is not independent validation.

Solo Research is intended to save the token overhead of delegation, repeated context transfer, inter-agent discussion, and duplicate reports. It shares **all mathematical methods and research rules** with four-agent execution: strategy selection, literature coverage, proofs and counterexamples, experiments, method IDs, the 5%/1% screening passes and outcome stages, verification criteria, effort policy, stopping rules, and archiving. Only agent count and the assignment/scheduling of responsibilities differ. The single researcher performs the same substantive review checks, honestly labeled self-review rather than independent-agent review.

Both execution modes choose Startup, Standard, or Bottleneck Research by the same criteria; solo has no separate default or reduced method set. Method updates apply to both through the same shared instructions. Token savings come from removing coordination overhead, not dropping decisive tests, lowering mathematical standards, automatically lowering reasoning effort, or truncating required archives. Actual savings depend on the task and are not guaranteed.

```text
$four-agent-research 不要 sub agent，单独研究这个问题；遵守逐轮归档和最新进展规则。
$four-agent-research 单人瓶颈研究：先整理大方向及各自方法，逐项尝试，按 5% / 1% 初筛与复筛规则推进。
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

## Bottleneck Search: Screening and Outcomes

Map major directions and concrete methods, numbered `method-001` onward. Keep three independent concepts:

| Dimension | Names | Meaning |
| --- | --- | --- |
| Research run | `round-000`, `round-001`, ... | One continuous research session |
| Method screening | 初筛 / 复筛 | Initial screening suspends below 5%; rescreening revisits suspended methods with a below-1% threshold |
| Outcome stage | 第一阶段通过 / 第二阶段通过 | Eligible for focused advancement / an actual verified substantive global conclusion obtained |

Rescreening begins only when every mapped method has initial-screening suspension or rigorous exclusion. Unknown, untested, blocked, or downstream-failed methods do not automatically satisfy that gate. Passing the applicable screen supports 第一阶段通过. Concentrate on one eligible method and queue others.

After further investigation, an evidence-backed probability **below 5% of producing a substantive global conclusion for the final objective** means **第一阶段通过但后续失败**. Record the grounds and reopening conditions. This is a separate assessment from screening viability; uncertainty or resource shortage is not automatic failure.

**第二阶段通过 requires an already obtained, clear, checkable global conclusion**, with a result ID, proof/verification record, explicit scope, and material contribution to the final objective. A probability at or above 5% supports continued work only. Local progress, an unproved route, or finite numerical evidence alone does not establish a global mathematical result. A substantive global result need not solve the entire final objective; state the remaining gap.

Screening and outcome fields never overwrite one another: 复筛通过 can coexist with 第一阶段通过但后续失败. New evidence addressing the downstream failure is needed before restarting concentrated advancement; the 1% screening threshold does not waive the separate downstream criterion. Preserve old labels as aliases, including old 第一阶段放弃 → 初筛放弃 and 第二阶段放弃 → 复筛放弃. See [Direction and Method Search](references/bottleneck-methods.md).

## Standard Research IDs

The project maintains `01_方法状态.xlsx` in its Drive root, with one row per method and separate **筛选轮次、筛选判定、成果状态、当前单点推进** fields. It records historical initial/rescreening suspensions, separate viability estimates, actual global conclusion IDs and verification links, and a transition-history sheet. Update the same file ID and preserve legacy evidence during schema migration. Solo and four-agent execution share this tracker. See [Persistent Excel Method Tracker](references/method-workbook.md).

Both execution modes automatically assign stable project-wide identifiers:

| Object | Starting ID |
| --- | --- |
| Research round | `round-000` |
| Problem / direction | `problem-000` / `direction-000` |
| Concrete method | `method-001` (existing convention retained) |
| Conjecture / theorem | `conjecture-000` / `theorem-000` |
| Proposition / lemma / corollary | `proposition-000` / `lemma-000` / `corollary-000` |
| Definition / general claim | `definition-000` / `claim-000` |
| Experiment / counterexample / gap | `experiment-000` / `counterexample-000` / `gap-000` |

Each prefix has its own sequence, continued across conversations, rounds, and execution modes. IDs are used in updates, ledgers, archives, and the latest-progress file, without generating unused categories. A conjecture that is proved keeps its original ID and links to the new theorem or lemma ID and the same proof. Withdrawals and corrections preserve IDs and update status; a label alone does not establish a proof. Existing records retain their labels and file names with aliases as needed. See [Shared Research Identifiers](references/research-identifiers.md).

## Long-Running Research Records

In either execution mode, one continuous work session exceeding 30 minutes of real wall-clock time requires a complete Google Drive record. Two hours of continuous work remains one round. Subtasks, updates, compaction, and automatic continuations do not reset the clock, and user absence between completed runs does not count. Do not prolong work to reach the threshold.

Use the corresponding project folder, creating a clearly named one if absent. New project rounds start at `round-000`; continue existing project round numbers across dates and conversations. Each archived round has one authoritative Markdown or Google Doc in the established format, for example `主题_round-045_YYYY-MM-DD_完整研究记录`; all checkpoint, final, and correction saves update the same Drive file ID. Essential attachments may instead be bundled with the full report into one ZIP. Historical archives are not automatically migrated or renumbered.

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
|   |-- research-identifiers.md
|   |-- method-workbook.md
|   `-- research-archive.md
|-- README.md
`-- LICENSE
```

The skill follows the [Open Agent Skills specification](https://agentskills.io/) and the [OpenAI skill authoring guidance](https://learn.chatgpt.com/docs/build-skills).

## License

MIT
