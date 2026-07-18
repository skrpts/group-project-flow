# Release Notes

## v1.1.29
GH#863 Wave 1 — fix K-045 intent/output mismatch. The task-tracker-builder and final-assembly-checker prompts (which produce the tracker and the final assembled submission) were never invoked by the workflow. Wire both as execution steps in dependency order: task-tracker-builder after role allocation; final-assembly-checker as the last content step, assembling the submission from the scope, roles, tracker, and feedback before language polish. Add two backing skills (Task Tracker Builder, Final Assembly Checker) so the new from_step targets resolve, convert cross-step refs to named context_params with bindings, and bind polish-language `source` to the final-assembly output (re-pinned polish-language@1.0.6 for the `source` slot).

## v1.1.28
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.27
GH#745 — declare per-step `output: {name, type}` on every execution step (project_scope/text, role_allocation/text, peer_feedback/text, project_tracker/text, team_charter/text, progress/text, polished_output/text, consistency_verdict/decision). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.26
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 10 inline shared-content files and declare 10 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.25
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.24
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.23
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.22
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.21
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
