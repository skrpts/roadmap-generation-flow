# Release Notes

## v1.1.35
GH#863 Wave 1 (#858-A1 class) — K-045 intent/output-mismatch fix. The workflow shipped three producer prompts that were never invoked, so it emitted polished intermediate analysis (executive summary) rather than the promised roadmap document. This release wires the never-invoked `roadmap-assembler` (final assembler), `roadmap-narrative-writer`, and `initiative-breakdown-prompt` into the execution block in dependency order, each behind a new backing skill (`initiative-breakdown`, `roadmap-narrative`, `roadmap-assembly`) so they are `from_step`-addressable. Cross-step references were converted from positional/title form to explicit `from_step` bindings via `context_params`. The `roadmap-assembly` step is now the final content step before `language-polish`, and `polish-language` is repinned 1.0.1 → 1.0.6 (adds the bindable `source` slot) with `language-polish` `source` bound to the assembled roadmap — so the output is the polished roadmap, not the polished summary. Skills 4 → 7, total 17 → 20.

## v1.1.34
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.33
GH#745 — declare per-step `output: {name, type}` on every execution step (themes/list, dependencies/text, timeline/text, resource_plan/text, stakeholder_analysis/text, summary/text, merged_roadmap/text, polished_roadmap/text, compliance_verdict/decision, consistency_verdict/decision, input_gaps/decision, risk_assessment/text). Lights up the #744 rich flow-map with named, typed outputs. **Also corrects the input-gap-check step to its intended `validation` type** — its `step_type` was mis-indented (outside the parallel item) and dropped at parse time, so the step previously ran untyped; it is now a validation gate. Content + structural fix (GH#748); no bindings changes.

## v1.1.32
GH#638 Row 4 + Row 13 closure — migrate the dependencies block to K-037 schema and repin every dep at v1.0.1 (assess-risks at v1.0.2 per its own fix-forward). Pre-K-037 v1.1.31 bundle had `id: hub-shared/<slug>` for each dep, which engine STEP 4d strict-UUID match cannot reconcile against the catalog. v1.1.32 ships each dep with `id: "<UUID>"` (canonical manifest.id from catalog) plus `name: "<slug>"` (logical alias for URL routing and human readability). All 18 dep bundles were also republished (Row 11 cascade) so their own `manifest.id` aligns with the catalog UUID, closing the v1.0.0 STEP 4d mismatch end-to-end. No consumer content changes; identity + dep-version repin only. UUIDs sourced from Hub catalog per K-037; checksums fetched via gen-dep-checksums.mjs (F2 fail-loud).

## v1.1.31
Re-sign of v1.1.30 — the v1.1.30 publish ran before the scanner fix `4f97762e` was on origin/main, so CI fetched the old scanner and the published bundle still carried the WARN-bearing security block. v1.1.31 republishes against origin/main's fixed scanner; clean security block; App import-review shows PASS on structural validation.

## v1.1.30
Re-signed after GH#633 Hub scanner fix: the previous bundle's security block carried a false-positive WARN ("output_step language-polish does not exist as a skill file") because the Hub JS scanner's C1 check was dep-blind. v1.1.30 ships against the fixed scanner; clean security block; App import-review now shows PASS on structural validation. **NB: actually shipped with the OLD scanner due to a push-vs-publish ordering issue — v1.1.31 is the one that picks up the fix.**

## v1.1.29
Fix-forward for caller-release.yml CONTENT_HASH extraction bug surfaced by v1.1.28: the previous regex matched the first `checksum:` in the manifest (which became a dep checksum once the dependencies block landed), not the bundle's integrity checksum. v1.1.28 registered an incorrect contentHash in D1; v1.1.29 ships the integrity-block-anchored regex and the correct bundle checksum.

## v1.1.28
GH#625 Step 3 (Path A pilot): migrated 18 inline-vendored shared slugs to dep-references against the `hub-shared/*` catalog. Same canonical content, now sourced from versioned `hub-shared/<slug>@1.0.0` deps with checksums. Slugs: analyse-stakeholders, assess-risks, brief-compliance-check, check-brief-compliance, check-consistency, check-input-gaps, company-okrs, consistency-check, dedup-and-merge, executive-summary, executive-summary-prompt, input-gap-check, language-polish, llm-service, polish-language, product-strategy-guide, risk-assessment, stakeholder-analysis.

## v1.1.27
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.26
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.25
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.24
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.23
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
