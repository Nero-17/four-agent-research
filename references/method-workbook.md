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
| 筛选轮次 | 未开始 / 初筛 / 复筛; distinct from `round-...` |
| 筛选判定 | 未评估 / 通过 / 放弃 / 不确定 / 资源受阻 / 已证明该范围不可行; scoped to 筛选轮次 |
| 成果状态 | 待评估 / 第一阶段通过 / 第一阶段通过，正在推进 / 第一阶段通过，全局结论待判定 / 第一阶段通过，推进受阻 / 第一阶段通过但后续失败 / 第二阶段通过 |
| 当前单点推进 | 是 / 否; at most one focal method per coordinated research run |
| 已进入初筛放弃 | 是 / 否 / 未知; historical initial-screening suspension |
| 首次初筛放弃轮次 | First relevant `round-...`; blank or 未知 if appropriate |
| 已进入复筛放弃 | 是 / 否 / 未知; historical rescreening suspension |
| 筛选可行性估计与不确定性 | Screening event, estimate/range, assumptions and resource horizon |
| 全局结论可行性估计与不确定性 | Separate downstream event, estimate/range, assumptions and horizon; 未评估 if unknown |
| 全局结论及编号 | Precise actual global result and ID; do not fill with a promised result |
| 全局结论核查记录 | Proof/verification link, assumptions, review outcome, and relevance to the final objective |
| 判定依据与精确障碍 | Concrete evidence and smallest remaining gap, not just a percentage |
| 下一步或重启条件 | Discriminating test or evidence needed to reopen |
| 最近更新轮次 | Most recent `round-...` changing this row |
| 更新时间 | Timestamp in the user's timezone |
| 证据与完整记录 | Links to supporting tests/proofs and round records, where available |

Use a second sheet, `状态历史`, inside the same workbook for concise transition records: method ID, round ID, timestamp, previous and new status/stage decision, reason, and evidence link. Preserve past suspension events when a method is reopened or a judgment is corrected. Put detailed proofs and experiments in their existing records and link them rather than duplicating them into cells.

## State Meaning and Update Rules

- Keep 筛选轮次, 筛选判定, 成果状态, and 当前单点推进 separate. 初筛/复筛 use the 5%/1% suspension criteria; `round-...` identifies a continuous research run; 第一阶段/第二阶段 describe outcomes. Apply [Direction and Method Search](bottleneck-methods.md) for all thresholds, transition gates, and evidence requirements.
- After positive screening, mark the first outcome stage passed and concentrate on one eligible method. Further investigation giving a defensible global-conclusion probability below 5% yields 第一阶段通过但后续失败. Record its evidence, retain the screening decision, and release it from focus. Unknown/straddling estimates remain pending; resource constraints alone are blockers.
- 第二阶段通过 requires an actual verified global conclusion. Verify the conclusion ID, proof or appropriate verification link, explicit scope, and substantive effect on the final objective before assigning it. No probability formula, rescreening pass, or absence of a failure flag can automatically produce this status.
- A row may read 复筛 / 通过 / 第一阶段通过但后续失败. Do not overwrite the outcome or select it for full advancement just because the 1% screen passed; reopening requires evidence addressing the downstream failure.
- The 已进入 columns record historical suspensions and remain true when methods reopen. Preserve transitions and corrections in 状态历史, including their dimension (screening or outcome), event, evidence, and related round. Unknown legacy history remains 未知.
- For existing workbooks, migrate the schema in the same file ID without losing history: old 当前阶段 becomes 筛选轮次; old 第一阶段判定 and 第二阶段判定 become their corresponding initial/rescreening records. Rename the old suspension flags to 初筛/复筛 flags, retaining aliases in history. Keep supported historical 第一阶段通过 as an outcome, but never interpret old 第二阶段判定 or a rescreening pass as 第二阶段通过. Mark any unmappable data pending instead of guessing. Do not rename historical round archives.
- Proven impossibility is separate from a probabilistic screening suspension; preserve the proof and do not invent a suspension event.
- Read the existing workbook before editing. Update the matching row when a method is added, assessed, suspended, reopened, refined, or corrected; append a history entry for actual decision/status transitions. At actionable checkpoints and the end of a research run, save pending changes to the same file ID, even if there is no major breakthrough. Unchanged data does not require repeated writes. The 30-minute threshold governs mandatory round reports, not whether method rows should be maintained.
- In four-agent execution the lead coordinates workbook writes; subagents supply changes rather than racing to overwrite it. Before saving after another conversation may have edited it, reread and reconcile by method ID; do not silently discard concurrent updates.

## Presentation and Verification

Use an Excel table with filters, frozen header and ID/name columns, readable column widths, wrapped explanations, and validated status choices. Distinguish first-outcome-stage passes, verified 第二阶段通过, 第一阶段通过但后续失败, the focal method, screening suspensions, and uncertainty, while retaining explicit text so color is not the sole signal. Keep method IDs and round IDs as text. Do not convert unknown estimates into numeric zero or automatically infer a pass or suspension from an estimate without a recorded decision.

Before reporting success, reopen/read the saved workbook and verify that it is valid `.xlsx`, method IDs are unique, every currently recorded method has a row, screening and outcome fields agree with the ledger/history and every 第二阶段通过 has actual verification evidence, and changed rows and links were preserved. After upload, verify the Drive file ID, project parent, and accessible saved content. Include the workbook's Drive link when first created or relevant to a status request. If saving/uploading fails, keep pending changes locally and explicitly say 尚未上传; reconcile them on later authorized continuation.

The workbook is the project's current method-status view. The full round archive remains the authoritative account of that round's reasoning and evidence. Reference the same method IDs in both and resolve discrepancies before claiming they are synchronized; this living tracker does not replace the single complete round report.
