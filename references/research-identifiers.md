# Shared Research Identifiers

Use the same identifiers in solo and four-agent execution, conversation reports, ledgers, round archives, and the latest-progress overview. Assign IDs automatically when an object is first recorded; do not ask the user to number it. IDs support communication and traceability, not additional mathematical notation or unnecessary abbreviation variables in proofs.

## Namespaces

Each project has an independent counter for each prefix. Use lowercase prefixes and at least three decimal digits, expanding naturally after 999.

| Object | First ID | Use |
| --- | --- | --- |
| Research round | `round-000` | One continuous research run, as defined in the archive procedure |
| Research problem | `problem-000` | A precise target question or separately tracked subproblem |
| Major direction | `direction-000` | A broad approach containing concrete methods |
| Concrete method | `method-001` | Preserve the previously established one-based method sequence |
| Conjecture | `conjecture-000` | A precise proposed statement requiring proof or falsification |
| Theorem | `theorem-000` | A proved principal result with explicit scope and assumptions |
| Proposition | `proposition-000` | A proved standalone supporting result |
| Lemma | `lemma-000` | A proved auxiliary result |
| Corollary | `corollary-000` | A proved consequence of identified results |
| Definition | `definition-000` | A substantive definition reused across the investigation |
| General claim | `claim-000` | A tracked material assertion not better captured by another type |
| Experiment or computation | `experiment-000` | A reproducible test, including finite computational checks |
| Counterexample | `counterexample-000` | A verified example refuting an explicitly scoped claim |
| Unresolved obstacle | `gap-000` | A precise missing step, bottleneck, or unresolved prerequisite |

Instantiate only objects needed for the research; do not produce empty categories or number every sentence, routine tool call, or algebraic step. A candidate lemma/theorem without a complete proof is tracked as a conjecture or open claim with its intended role noted. Finite computational support alone does not earn a theorem ID; a candidate counterexample remains an experiment/open claim until verified. A proved implication may be a theorem under clearly stated hypotheses, but an unresolved prerequisite must not be hidden by relabeling a conditional claim.

## Allocation and Persistence

- Start at the listed initial ID only for a genuinely new project namespace. Read the project's existing registry, latest-progress overview, and relevant round records before allocating. Continue after the highest assigned suffix, not the count of surviving entries. Do not reset at a new direction, date, round, conversation, execution mode, or screening pass, or outcome stage.
- In four-agent execution the lead allocates IDs centrally; subagents return existing IDs or proposed new objects for allocation, not competing counters. Across simultaneous conversations, recheck the registry before saving. If existing allocations cannot be verified, use a clearly provisional unique timestamp-based label and reconcile later rather than guessing a permanent ID.
- Keep IDs stable when renaming, retrying, refining exposition, changing status, or moving a method between directions, screening passes, or outcome stages. Never recycle retired IDs. Materially different statements, assumptions, or independently investigated variants receive new IDs linked to the original.
- Preserve legacy IDs and historical file names. Record an explicit alias mapping when adding this scheme; do not rewrite, rename, or renumber old archives. Where a verified legacy round sequence ended at R045, the next round can be `round-046`; retain R045 as the historical reference. If sequence mapping is ambiguous, keep the legacy reference and resolve it before assigning a permanent continuation number.
- Track an actual research run as a round, including a short substantive run; ordinary Q&A is not automatically a research round. Crossing 30 minutes makes Drive archiving mandatory but does not create another round or another ID. Short rounds do not gain a mandatory full Drive archive merely from having an ID; preserve their IDs in existing project state so later rounds do not reuse them.

## Registry, Status, and Relationships

Maintain a compact object registry within the existing research ledger and carry its current state into the single round record. Do not create a second authoritative archive or repeatedly duplicate full records to hold IDs. Each entry contains its ID, readable title and precise statement/scope, applicable status, creation and last-change round, supporting evidence/proof location, dependencies, related IDs or aliases, and material revision history. Use claim-ledger statuses for assertions and method dispositions for methods; the prefix is an object type, not a substitute for its current evidentiary status.

When a conjecture is proved, retain `conjecture-000`, set its status to `PROVED`, and create the next appropriate result ID (for example `theorem-000`) linked as `proved_as`. The theorem points back with `originates_from`. Both refer to the same proof and precise statement rather than duplicating independently maintained claim bodies. A refutation instead links the conjecture to a verified `counterexample-000` and records its scope. A later withdrawal preserves all IDs, updates statuses and dependency warnings, and updates the latest-progress overview if material; a theorem prefix must never conceal a withdrawn proof.

Methods link to their direction, target problem/conjecture, decisive gap, and experiments/results. Results list the IDs of premises they actually depend on. Round records list material objects created or changed and their prior/current status. The latest-progress file cites the strongest reliable result IDs and supporting round links.

In user-facing updates, pair the ID with a short readable description on first mention, then reuse it consistently. For example: `round-003: method-007 (coupling argument) addresses gap-002; experiment-004 gives finite evidence for conjecture-001, still unproved.` The round ID goes immediately after the required research-mode opening; IDs do not replace the explanation of what was established.
