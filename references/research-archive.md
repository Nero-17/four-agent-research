# Project Archives and Latest Progress

Apply this procedure in both solo and four-agent execution. Honor explicit current user instructions, including an instruction not to upload. These routine project records are authorized by this workflow; do not ask for consent again each round. Use the available Drive skill/connector and obey its access controls. Never embed personal folder IDs in this public skill.

## A Round and Its Clock

- Record the actual start time when beginning long work. A round is one continuous work session, not a fixed 30-minute block. Once it exceeds 30 minutes of real elapsed wall-clock time, archiving is mandatory. A two-hour continuous run is one round, not four.
- Tool calls, progress messages, subtasks, compaction, automatic continuations, and user corrections during the same run do not start new rounds. Do not sum agent-hours or include the user's absence between completed runs. After a run ends, a subsequent user request to continue begins a new round. Never prolong work merely to trigger archiving.
- Preserve the original start timestamp, round identity, Drive folder and file IDs, and pending upload state across compaction and continuation. After crossing the threshold, create or update the round record at an actionable checkpoint; complete and verify it at the end. On cancellation, record the existing state within permitted wrap-up without continuing canceled research.

## Locate the Project and Continue Its Numbering

- At the start of long work, locate the corresponding project's existing Drive folder and read its `00_最新进展` (or existing equivalent) first, then the linked relevant round records. Use an explicit project destination when supplied. Do not mix unrelated projects or use another project's folder by convenience.
- If no folder exists, create a clearly named project folder. Within it, use the established archive location or, when needed, one `逐轮研究记录` subfolder. Keep the latest-progress file at the project root.
- Continue the project's existing round sequence across conversations and dates. Inspect existing archives and recorded state, including all relevant listing pages; never reset to R001 for a new day or task, and never number by file count.
- Recheck occupied numbers immediately before writing. If numbering cannot be verified or a concurrent collision remains unresolved, use a unique timestamp-based temporary identity, explicitly marking the round number unresolved. Do not guess, claim an occupied number, or automatically renumber historical records.

## One Authoritative File per Round

Use the project's established single Markdown or Google Doc format. For a new project, default to Markdown. A suggested title is `主题_R045_YYYY-MM-DD_完整研究记录`, using the user's timezone. Preserve historical formats and records; do not migrate, split, delete, or renumber them automatically. A specifically requested format takes precedence.

Create only one complete authoritative record per round. Intermediate saves, final results, corrections, and supplements update the **same Drive file ID**. Do not create checkpoint, summary, audit, final, or v2 fragments. If essential code, certificates, or attachments cannot reasonably fit inside the report, the one record may instead be a ZIP containing the full report and all necessary attachments; update that same archive file rather than leaving multiple authoritative copies.

Make the record independently readable and suitable for handoff. Include:

- Project/topic, round identity, source conversation reference when available, execution mode and research strategy, actual start/end times with timezone, and wall-clock duration (mark an in-progress checkpoint as such).
- Goal, baseline, new results, key arguments, assumptions, scope, reproducible methods, verification evidence, and source links.
- Precise distinctions between proved results, conditional conclusions, finite computational support, conjectures, and unresolved claims; include the claim ledger and material review limitations.
- Failed routes, reasons for abandoning methods, withdrawals, corrections, and the direction/method ledger and stage when bottleneck work applies.
- Exact remaining gaps, next steps, and the compact effort-control disclosure. Record no breakthrough honestly.

Record auditable arguments and a work summary, not private internal reasoning transcripts. In mathematical proofs, avoid unnecessary abbreviation variables.

## A Persistent Latest-Progress File

Keep one project-root file named `00_最新进展`, in the established Markdown or Google Doc format. Reuse an existing equivalent rather than creating a duplicate. Initialize it with the current research state when first establishing the project archive.

After that, update the same file ID only for substantive changes: solving a core problem, proving a key theorem, obtaining a decisive counterexample, materially removing a central obstacle, or withdrawing/correcting a principal argument. Repeated checking and ordinary local progress are not breakthroughs. A major withdrawal must be reflected so the overview does not retain misleading claims.

Read the current file before updating it; retain important still-valid conclusions. Include the last substantive update time, strongest reliable result and its scope, the material change, core unresolved gaps, next step, and supporting round numbers with full-report links. Distinguish proof, conditional conclusions, computational support, and conjecture. This overview complements and never replaces round records.

## Verify and Recover

Before reporting success, verify each written file's ID, parent folder, name, and readable saved content. After an uncertain response, search for the existing file before retrying. Preserve file identity on retries and subsequent updates. Do not change sharing permissions.

If Drive cannot be connected or written, preserve the same complete record locally in an allowed location, with the original start time, round identity, known IDs, and pending-upload state. Say **尚未上传 / not uploaded**. Do not claim success or create scheduled jobs. On later authorized continuation, upload/update that record once access returns, checking for duplicates first.

The final response must include the round identity and verified Drive link, or explicitly report the unresolved number and/or local record with upload still pending. Report the latest-progress link when it was materially updated.
