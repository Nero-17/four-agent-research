# Adaptive Reasoning Effort

This is a task-sensitive allocation policy, not a claim of empirically optimal settings or a guarantee that a host can override effort. It applies across all three research modes and all four roles.

## Choose a Target

First honor explicit user model and effort choices, including an applicable user-pinned higher effort, and the run's resource limits. Otherwise use the following targets for the next bounded subtask:

| Work | Target |
| --- | --- |
| Routine literature retrieval, deduplication, fact extraction, bibliography or experiment-output organization | `high` |
| Comparing sources, identifying gaps, forming conjectures, designing experiments, or substantive reasoning of uncertain difficulty | `xhigh` |
| Original or multi-step proofs, difficult counterexamples, critical logical obstacles, review of core conclusions, or adjudication of substantive disagreement | `max` |
| A precisely identified exceptionally difficult gap with a concrete promising next attempt, when the model supports it and resources permit | `ultra` |

Use `xhigh` as the default for substantive research reasoning, not for every clerical action. Judge the operation, not just the agent's title: Agent 1 can move from routine retrieval to difficult novelty assessment; Agent 3 can move from checking references to auditing a central proof. Agent 0's critical synthesis also merits a `max` target, but this does not imply it can change its own active turn.

Startup Research tends to contain more search and exploration; Standard Research more focused advancement; Bottleneck Research more new-method exploration and hard-gap work. None locks all agents to one effort. Running many numerical experiments consumes compute but does not, by itself, justify increasing reasoning effort.

## Reassess at Checkpoints

Before a new subtask or a supported next-turn boundary, assess:

1. **Reasoning demand:** dependency length, hidden assumptions, competing explanations, and genuinely novel inference.
2. **Consequence of error:** whether failure would invalidate a central claim, downstream work, or the user's decision.
3. **Expected marginal benefit:** the specific gap and concrete next attempt that deeper reasoning could help resolve.
4. **Actual bottleneck and budget:** whether progress instead needs better sources, data, tools, permissions, compute, a different method, or a stop.

Assign `max` to critical work from the outset; do not require a ceremonial lower-effort failure first. Escalate other work when a checkpoint supplies a concrete reason. Use `ultra` only for a bounded deep attempt with an identifiable route and an adequate remaining budget, not as a blanket response to difficulty or an unspecified budget.

An unanswered question, a single failed attempt, long output, or an agent's confidence is not an escalation criterion. Missing access or data cannot be fixed by more reasoning. When the task becomes routine, lower the automatic target at the next supported boundary, respecting explicit user choices. Repeated effort increases without validated progress or new information trigger the selected research mode's stopping/replanning criteria, not an unlimited retry loop. Reserve resources for independent review.

## Apply and Verify

- Check the selected model's actual supported effort levels and the available tool/configuration schema. Keep the user's model; do not select another model or provider merely to obtain a preferred effort.
- For automatic selection, if a target is unsupported, choose the highest supported level not above that target in the order `low < medium < high < xhigh < max < ultra`, and disclose the fallback. For example, a `max` target can fall back to `xhigh`; never upgrade to `ultra` just because `max` is unavailable. If capabilities are unknown, retain a known working inherited/default setting and mark the effective level unverified instead of guessing parameter values.
- An unsupported explicit user setting must be disclosed; substitute only within fallback permission the user has given. Honor the scope of an explicit choice rather than treating it as permission to change unrelated agents.
- When supported, pass effort through the real subagent spawn or subsequent-turn API using that API's documented field. Existing authorized custom-agent configuration may also supply it. Check effective configuration or returned runtime metadata when available: a custom-agent setting may take precedence over a requested spawn value.
- Keep the existing persistent role sessions. Change effort only at boundaries the host actually supports; if an existing session cannot be reconfigured, retain its setting and record the mismatch. Do not restart a role, create extra user-visible tasks, or rewrite global/project configuration just to enforce a target.
- Agent 0 retains its current runtime effort unless a supported, authorized control can change it for a subsequent turn. Never claim to change the effort of an already-generating turn. Simulated role passes all share the parent runtime; their different planned targets are not separate effective settings.
- A prompt saying "use max" is not proof of application. A successful request without effective-setting metadata establishes what was requested, not independent verification of what ran. Do not infer runtime effort from response length, self-reports, or a global default alone.
- If effort controls or verification are unavailable, continue otherwise authorized research under existing settings and explain the limitation. Do not block a research round solely for an optional effort preference, weaken the evidence standard, or bypass permissions.

Current configuration behavior is documented in the [official Codex subagent reference](https://learn.chatgpt.com/docs/agent-configuration/subagents#choosing-models-and-reasoning). Consult current host capabilities rather than assuming all models or clients support these controls.

## Report the Allocation

After the mandatory first sentence identifying the research mode, include a compact effort summary in the conversational report and, when archiving is enabled, the English TeX report. For each distinct role/phase allocation, record the target, requested setting (or not configurable), verified effective setting (or unknown), and any material change, fallback, or reason. Group identical allocations to avoid a verbose activity log.

For example: `Agent 2, core proof: target max; requested max; effective unknown (runtime metadata unavailable).` Never replace the required research-mode opening with the effort summary.

## Decision Examples

| Situation | Expected policy decision |
| --- | --- |
| Agent 1 extracts bibliographic facts during Bottleneck Research | `high`, not `max` just because the mode is Bottleneck |
| Agent 2 formulates candidate conjectures during Startup Research | `xhigh` |
| Agent 3 checks a core multi-step proof during Startup Research | `max`, despite the early project stage |
| A failed proof exposes a precise deep gap and a promising new approach; `ultra` is supported and budgeted | A bounded `ultra` attempt is eligible |
| A download fails because access is missing | Address or report access; no effort escalation for that failure |
| The user explicitly pins all agents to supported `ultra` | Preserve that explicit choice rather than automatically lowering routine phases |
| The automatic target is `max`, but supported levels end at `xhigh` | Request `xhigh` and disclose the compatibility fallback |
| A persistent agent has no supported effort setter or readback | Keep its existing runtime; report the target and unknown effective effort, with no invented switch |
