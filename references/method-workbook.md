# Persistent Excel Method Tracker

In solo and four-agent execution, create and maintain one actual Excel workbook named `01_方法状态.xlsx` in the corresponding Google Drive project root when the first concrete method is recorded. Reuse an existing equivalent workbook and its Drive file ID. This is a project-wide living tracker, alongside `00_最新进展`, not an additional report for each round. Do not create dated or per-round workbook copies. A Markdown table in chat is not a substitute for the requested Excel file.

Use the available spreadsheet skill to create/edit and verify `.xlsx` files, and the authorized Drive connector to save them. If either capability is unavailable, preserve the best available local workbook or complete pending table data and disclose the exact limitation; never claim an Excel file was created or uploaded when it was not. An explicit no-upload instruction takes precedence. No personal Drive IDs belong in this public skill.

## Sheets and Fields

The `方法状态` sheet has exactly one current row per concrete method, keyed by its stable ID (`method-001`, `method-002`, etc.) and sorted by the numeric suffix. Include existing methods when first establishing the tracker; preserve unknown historical fields as unknown rather than inventing evaluations. Use these columns:

| Column | Meaning |
| --- | --- |
| 方法编号 | Stable method ID; unique and never recycled |
| 方法名称 | Short readable name |
| 方向编号 | Related direction ID |
| 目标问题或猜想 | Target IDs and short scope |
| 当前状态 | Current method disposition from the shared method ledger |
| 当前阶段 | 未开始 / 第一阶段 / 第二阶段 |
| 第一阶段判定 | 未评估 / 第一阶段通过 / 第一阶段放弃 / 不确定 / 资源受阻 / 已证明该范围不可行 |
| 当前单点推进 | 是 / 否; at most one current focal method per coordinated research run |
| 已进入第一阶段放弃 | 是 / 否 / 未知; whether a documented stage-1 suspension has occurred |
| 首次第一阶段放弃轮次 | The `round-...` of the first recorded suspension; otherwise blank or 未知 |
| 第二阶段判定 | 未进入 / 待重审 / 继续 / 放弃 / 不确定 / 资源受阻 / 已证明该范围不可行 |
| 已进入第二阶段放弃 | 是 / 否 / 未知; whether a documented stage-2 suspension has occurred |
| 可行性估计与不确定性 | Subjective estimate or range, with assumptions/resource horizon; 未评估 where unknown |
| 判定依据与精确障碍 | Concrete evidence and smallest remaining gap, not just a percentage |
| 下一步或重启条件 | Discriminating test or evidence needed to reopen |
| 最近更新轮次 | Most recent `round-...` changing this row |
| 更新时间 | Timestamp in the user's timezone |
| 证据与完整记录 | Links to supporting tests/proofs and round records, where available |

Use a second sheet, `状态历史`, inside the same workbook for concise transition records: method ID, round ID, timestamp, previous and new status/stage decision, reason, and evidence link. Preserve past suspension events when a method is reopened or a judgment is corrected. Put detailed proofs and experiments in their existing records and link them rather than duplicating them into cells.

## State Meaning and Update Rules

- Here 第一阶段/第二阶段 mean the 5%/1% method-screening stages, not research rounds. A `round-...` may contain work from either or both stages.
- Stage-1 放弃 requires the shared evidence-backed **strictly below 5%** criterion; stage-2 放弃 requires **strictly below 1%**. Thresholds, uncertainty rules, and the all-methods stage-transition gate remain those in [Direction and Method Search](bottleneck-methods.md).
- Record a completed, favorable stage-1 assessment as `第一阶段通过`, with current disposition `PASSED_STAGE_1`. Apply the shared pass criterion (at least 5%, or a range wholly at/above 5%, plus a feasible next attempt); neither an unchecked method nor `已进入第一阶段放弃 = 否` is sufficient. Mark the selected passed method `当前单点推进 = 是`; other passed methods remain queued. Keep assessment and focus separate, and preserve pass-to-suspension or reopening transitions in 状态历史. When adopting these labels in an existing workbook, map old `继续` entries to `第一阶段通过` only after checking their evidence; do not invent past passes or erase old decisions.
- The 已进入 columns record historical entry, not the current disposition. Reopening a stage-1-suspended method in stage 2 leaves `已进入第一阶段放弃 = 是`, while 当前状态 and 第二阶段判定 show current work. A correction remains visible in 状态历史 and the current explanation. `否` alone does not mean viable or reviewed: 未评估/不确定/资源受阻 must remain explicit. Incomplete legacy history uses 未知.
- Proven impossibility in scope is a separate decision, not a fabricated below-threshold estimate. Record its proof and do not mark the suspension-history flag 是 unless a suspension actually occurred.
- Read the existing workbook before editing. Update the matching row when a method is added, assessed, suspended, reopened, refined, or corrected; append a history entry for actual decision/status transitions. At actionable checkpoints and the end of a research run, save pending changes to the same file ID, even if there is no major breakthrough. Unchanged data does not require repeated writes. The 30-minute threshold governs mandatory round reports, not whether method rows should be maintained.
- In four-agent execution the lead coordinates workbook writes; subagents supply changes rather than racing to overwrite it. Before saving after another conversation may have edited it, reread and reconcile by method ID; do not silently discard concurrent updates.

## Presentation and Verification

Use an Excel table with filters, frozen header and ID/name columns, readable column widths, wrapped explanations, and validated status choices. Highlight 第一阶段通过 in green and distinguish the focal method, stage-1 suspension, stage-2 suspension, and uncertainty, while retaining explicit text so color is not the sole signal. Keep method IDs and round IDs as text. Do not convert unknown estimates into numeric zero or automatically infer a pass or suspension from an estimate without a recorded decision.

Before reporting success, reopen/read the saved workbook and verify that it is valid `.xlsx`, method IDs are unique, every currently recorded method has a row, key stage flags agree with the ledger/history, and changed rows and links were preserved. After upload, verify the Drive file ID, project parent, and accessible saved content. Include the workbook's Drive link when first created or relevant to a status request. If saving/uploading fails, keep pending changes locally and explicitly say 尚未上传; reconcile them on later authorized continuation.

The workbook is the project's current method-status view. The full round archive remains the authoritative account of that round's reasoning and evidence. Reference the same method IDs in both and resolve discrepancies before claiming they are synchronized; this living tracker does not replace the single complete round report.
