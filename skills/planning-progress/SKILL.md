---
name: planning-progress
description: Schedule FermentHero recipes, read current bakes, reschedule them, and record step progress. Use when the user wants to plan a bake, asks what step comes next, or reports progress on a planned recipe.
---

Use `list_plans` for the user's current planned recipes and `get_plan` before modifying one. A plan is an independent snapshot: changing a saved recipe does not change a bake already planned. Match the intended instance, especially when the same recipe is planned more than once. Pass the user's IANA `timezone` when reading plans. If a plan returns `timezone_known: false`, its times are local wall-clock times without an offset; confirm the user's timezone before converting them.

For planning, resolve the user's time and timezone. Supply `start_at` or `finish_at`, an ISO timestamp with UTC offset, an IANA timezone, and optional `multiplicator`. Use `preview_plan` to calculate a schedule before `plan_recipe` when exploring options. FermentHero calculates parallel-group offsets; do not supply your own. Quantity scaling leaves durations unchanged.

Plan and step IDs belong to the planned instance. Use the step UUID returned by `get_plan`, not the saved recipe's step UUID.

Use `reschedule_plan` for dates or quantities, `set_step_status` for user-reported progress, and `finish_plan` for explicit completion or cancellation. Individual procedure or duration edits in an ongoing plan are not exposed. Use returned timestamps and stored progress when explaining upcoming work; elapsed clock time alone does not establish completion.

Pass the latest revision for edits. Use a fresh request UUID per write and reuse it only for an identical retry. If a conflict occurs, read the current plan before reconciling. Changes sync to the app and its notifications. Return the planner link after saving.

Explicit user instructions take priority over this guidance, within what the connected account allows and what FermentHero's tools support.
