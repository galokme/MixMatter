# Final Submission Readiness Checklist — MixMatter 2.2

This checklist covers the UI-independent Skills-only MixMatter 2.2 package.

## Repository readiness

- [x] New plugin public name is `MixMatter`; technical package name is `mixmatter`.
- [x] Package version is `2.2.0` in every manifest (enforced by CI).
- [x] Portable manifest is present at root `plugin.json`; technical `name` is `mixmatter`, and `extensions.com.openai.interface.displayName` is `MixMatter`. The submission ZIP omits `.codex-plugin/plugin.json` because the OpenAI portal normalizes and adds it during conversion.
- [x] Packaged Skill is present at `skills/mixmatter/`.
- [x] Packaged references are `mixmatter-v1.md` and `quality-rubric.md`.
- [x] The seven research/system documents are retained under `docs/` as reference, not runtime authority.
- [x] ChatGPT host UI source code has been removed from the active product architecture.
- [x] Host-UI specification documents have been removed from the active product architecture.
- [x] The Skill no longer depends on creation/result cards, widgets, or MCP UI tools.
- [x] Direction / Structure / Intensity remain available as natural-language product semantics.
- [x] Revision continuity and alternative-from-source are part of the packaged Skill.
- [x] Source-text protection remains strict.
- [x] Light and dark MixMatter icon assets are present.
- [x] Privacy and Terms describe a Skills-only architecture with no separate MixMatter MCP service.

## Behavior checks

- [ ] Re-test default vague invocation with representative source images.
- [ ] Confirm vague requests produce autonomous source-specific judgment rather than a menu or generic preset list.
- [ ] Confirm explicit requests execute directly.
- [ ] Confirm a revision preserves successful crop, identity, hierarchy, locks, and useful material decisions.
- [ ] Confirm an alternative-from-source returns to the original source image unless the user requests otherwise.
- [ ] Confirm default results are visibly reconstructed rather than ordinary photo styling.
- [ ] Confirm material effects remain selective and causally justified.
- [ ] Confirm zero new text is added by default.
- [ ] Confirm uncertain source text is obscured/cropped rather than hallucinated.
- [ ] Confirm source text is not translated or bilingual-duplicated by default.
- [ ] Run representative cases from `docs/system/MIXMATTER_REGRESSION_BENCHMARK.md`.

## Submission package

The final ZIP should preserve this relevant structure:

```text
plugin.json
skills/
└── mixmatter/
    ├── SKILL.md
    └── references/
        ├── mixmatter-v1.md
        └── quality-rubric.md

assets/
├── mixmatter-icon-light.svg
└── mixmatter-icon-dark.svg
```

Do not include the retired `apps/mixmatter-chatgpt/` implementation as an active runtime dependency.

## Review materials

- [x] 2.2 listing copy prepared.
- [x] Three starter prompts prepared.
- [x] Positive and negative review-test framework prepared.
- [x] 2.2 release notes prepared.
- [x] Public website, support, privacy, and terms URLs are listed.
- [x] Developer / publisher relationship remains `Fan Jiale` / `Galok`.

## Portal actions

- [ ] Rebuild the final Plugin ZIP for 2.2.0 from the reviewed repository state using the `Build MixMatter OpenAI Package` workflow.
- [ ] Upload that exact ZIP to the OpenAI submission flow.
- [ ] Confirm the portal creates a new plugin from root `plugin.json` with technical name `mixmatter`, converts it to normalized Codex format, and preserves `MixMatter` as the display name.
- [ ] Copy the finalized listing details and starter prompts.
- [ ] Add the positive and negative tests from `test-cases.md`.
- [ ] Confirm country / region availability at submission time.
- [ ] Review all policy attestations before submission.

## Go / no-go status

**Status: MIXMATTER 2.2.0 REPOSITORY READY; ZIP REBUILD + PORTAL UPLOAD PENDING.**


## Previous validated build (2.1.0, superseded)

- Artifact: `mixmatter-openai-2.1.0.zip`
- GitHub Actions run: `35335988945`
- Source commit: `921d8f971df980a427d76c58e9d4b1e1febdd076`
- SHA-256: `81e74a48eabe4d0ac4235e05c6e276a242e0493d22d720eaf052f489a848863a`
- Package contents: root `plugin.json`, `skills/mixmatter/`, active MixMatter icon assets, and `LICENSE`
- Stale-brand scan: no retired product names or retired website paths in the ZIP
