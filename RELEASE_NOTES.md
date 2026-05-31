# Release Notes

## v1.1.30
Re-signed after GH#633 Hub scanner fix: the previous bundle's security block carried a false-positive WARN ("output_step language-polish does not exist as a skill file") because the Hub JS scanner's C1 check was dep-blind. v1.1.30 ships against the fixed scanner; clean security block; App import-review now shows PASS on structural validation.

## v1.1.29
Fix-forward for caller-release.yml CONTENT_HASH extraction bug surfaced by v1.1.28: the previous regex matched the first `checksum:` in the manifest (which became a dep checksum once the dependencies block landed), not the bundle's integrity checksum. v1.1.28 registered an incorrect contentHash in D1; v1.1.29 ships the integrity-block-anchored regex and the correct bundle checksum.

## v1.1.28
GH#625 Step 3 (Path A pilot): migrated 18 inline-vendored shared slugs to dep-references against the `hub-shared/*` catalogue. Same canonical content, now sourced from versioned `hub-shared/<slug>@1.0.0` deps with checksums. Slugs: analyse-stakeholders, assess-risks, brief-compliance-check, check-brief-compliance, check-consistency, check-input-gaps, company-okrs, consistency-check, dedup-and-merge, executive-summary, executive-summary-prompt, input-gap-check, language-polish, llm-service, polish-language, product-strategy-guide, risk-assessment, stakeholder-analysis.

## v1.1.27
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.26
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.25
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.24
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.23
Initial catalogue release with full structural and content-quality validation. All scanner checks pass.
