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

## Independence and Fallbacks

When genuine subagent tools are available, the skill assigns Agents 1-3 to separate persistent subagent sessions. When they are unavailable, it runs clearly separated role passes and discloses that limitation. A simulated reviewer pass is never described as an independent agent.

Using the skill authorizes research delegation only. It does not authorize publication, purchases, account changes, external writes, or other consequential actions.

## Files

```text
four-agent-research/
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- README.md
`-- LICENSE
```

The skill follows the [Open Agent Skills specification](https://agentskills.io/) and the [OpenAI skill authoring guidance](https://learn.chatgpt.com/docs/build-skills).

## License

MIT
