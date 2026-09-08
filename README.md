# Four-Agent Research

A reusable Codex skill for rigorous research and reasoning through four distinct roles: leadership, evidence mapping, concrete advancement, and independent review.

It is designed for complex scientific, technical, policy, strategic, historical, and other questions where a plausible answer is not enough. The workflow tracks material claims, tests conjectures, searches for disconfirming evidence, and distinguishes verified progress from effort.

## Roles

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

## Long-Running Research Reports

After each sustained research round, the skill uploads a standalone English LaTeX progress report to the Google Drive folder the user has designated for that project. Ordinary Q&A does not trigger an archive. When no folder or prior opt-out is known, it asks whether the user wants to configure one; declining skips file generation and upload without interrupting research or repeatedly asking.

Reports use `<overall-title>-YYYY-MM-DD-<round>.tex`, for example `Erdos-Similarity-Problem-2026-09-05-2.tex`. The project title stays stable, the date uses the user's timezone, and the daily round number continues after existing or recorded rounds. The report body starts with the English research-mode sentence and includes objectives, the mode-selection basis and stopping reason, reviewed progress, substantive results, failed routes, sources, a claim ledger, and next steps. Historical reports are never overwritten.

This requires an authorized Drive connector or API. Selecting a report destination authorizes only new progress reports there, not broader Drive changes. Uploads are verified before success is reported; missing access or upload failures are disclosed. Personal folder settings stay in the project's context, not in this repository.

## Independence and Fallbacks

When genuine subagent tools are available, the skill assigns Agents 1-3 to separate persistent subagent sessions. When they are unavailable, it runs clearly separated role passes and discloses that limitation. A simulated reviewer pass is never described as an independent agent.

Using the skill authorizes research delegation only. It does not authorize publication, purchases, account changes, external writes, or other consequential actions.

## Files

```text
four-agent-research/
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- research-modes.md
|   `-- reasoning-effort.md
|-- README.md
`-- LICENSE
```

The skill follows the [Open Agent Skills specification](https://agentskills.io/) and the [OpenAI skill authoring guidance](https://learn.chatgpt.com/docs/build-skills).

## License

MIT
