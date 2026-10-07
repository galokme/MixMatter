# Contributing to MixMatter

Thanks for testing MixMatter.

The project is especially interested in evidence about where the reconstruction system succeeds, where it fails, and how different image models interpret the same source.

## Good contributions

Useful contributions include:

- source/result comparison pairs
- model-to-model comparisons using the same source and prompt
- reproducible failure cases
- improvements to the quality rubric
- tighter wording that improves cross-model consistency
- new source categories that expose weaknesses in the current method

## Before proposing a prompt change

Please test the current prompt on multiple image categories first. Avoid changing the system because of one unusually good or bad generation.

A proposed change should ideally improve more than one category without degrading another.

## Evaluation

Use [`eval/quality-rubric.md`](eval/quality-rubric.md) when comparing outputs.

Pay particular attention to these recurring failure modes:

- filter-only transformation
- blanket halftone
- over-abstraction that destroys source identity
- template-like collage
- arbitrary circles, suns, triangles, or decorative blocks
- flat vectorization without print hierarchy
- fake vintage treatment
- invented text

## v1.0 scope

MixMatter v1.0.2 is source-text controlled: it adds zero new text by default and permits only exact wording explicitly supplied by the user.

Please keep typography, inferred place names, captions, slogans, dates, and metadata outside the core v1.0 proposal unless the discussion is explicitly about a future typography extension.

## Core baseline and platform packaging

MixMatter v1.0.0 is the frozen image-only core baseline. Changes must preserve the v1.0.2 rules against translation, bilingual duplication, approximate source-text reconstruction, and unrequested copy.

The canonical behavioral source is [`skills/mixmatter/`](skills/mixmatter/): `SKILL.md` plus `references/mixmatter-v1.md` (master prompt) and `references/quality-rubric.md` (evaluation contract). [`prompt/mixmatter-v1.md`](prompt/mixmatter-v1.md) and [`eval/quality-rubric.md`](eval/quality-rubric.md) are byte-identical mirrors; edit the packaged copy first, then copy it over. CI fails if they drift.

Platform-specific packaging may add manifests, metadata, assets, or synchronized copies of the Skill, but it should not silently change the v1.0 behavior.

When adapting MixMatter to another platform:

1. keep the root `SKILL.md` as a thin entry point that defers to `skills/mixmatter/`
2. point every platform manifest at `skills/mixmatter/` rather than adding another copy of the Skill
3. keep the version identical across `plugin.json`, `.codex-plugin/plugin.json`, `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json`, the package workflow, and `CHANGELOG.md`
4. treat packaging changes separately from behavioral changes
5. require a version bump and changelog entry for any change that alters reconstruction behavior, trigger boundaries, or hard constraints

This keeps OpenAI, Codex, Claude, Vercel Skills, and future integrations aligned around the same core system.

## Example submissions

When possible, include:

1. the source image
2. the generated result
3. model name
4. whether the master prompt was used unchanged
5. a short evaluation using the rubric
6. any observed failure mode

Do not submit images you do not have permission to share publicly.

## Design principle

The governing principle remains:

> Preserve semantic identity, not visual completeness.

Changes that create more visual drama while weakening source identity are not automatically improvements.
