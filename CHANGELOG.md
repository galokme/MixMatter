# Changelog

## 2.2.0 — 2026-10-07

### Added

- Claude Code plugin and marketplace manifests (`.claude-plugin/`), so the skill installs with `/plugin marketplace add galokme/MixMatter`
- host behavior for surfaces that can read images but cannot generate them: the skill returns one concise, source-specific image-editing brief instead of pretending to render or describing a generic style
- runtime guidance for revisions (keep successful crop, identity, hierarchy, and locks; change only the requested axis), alternatives from the original source, and plain-language direction / structure / intensity controls, all bounded by the v1 visual baseline
- CI checks for manifest version agreement, changelog coverage, byte-identical mirrors, skill frontmatter, and retired identities

### Changed

- the skill's host section now covers ChatGPT, Codex, Claude, and Claude Code instead of OpenAI hosts only
- unified the public name as **MixMatter** across documentation, legal pages, icons, and submission materials
- moved every repository link to `galokme/MixMatter`
- `prompt/mixmatter-v1.md` and `eval/quality-rubric.md` are now exact mirrors of the packaged copies in `skills/mixmatter/references/`
- rewrote the README to describe the actual v1 runtime, per-host installation, usage, and the showcase plates; the 2.0 documents are labelled as research, not runtime authority
- renamed the CI workflow to `mixmatter-ci.yml` and ran it on every pull request

### Unchanged

- v1 visual baseline, source-text policy, scope boundary, and hard constraints

## 2.1.1 — 2026-09-30

### Changed

- restored the v1 visual runtime as the sole runtime authority in `skills/mixmatter/SKILL.md` and the root `SKILL.md`
- removed the packaged `mixmatter-v2-runtime.md` and `hierarchy-stabilization.md` references from the skill bundle
- added explicit guards against unrelated sources collapsing into one recurring blue / coral / botanical decorative template, and matching failure items in the quality rubric
- bumped all manifests to `2.1.1`

## 2.1.0 — 2026-09-18

### Changed

- rebranded the public product from **Press Print** to **MixMatter**
- retained the technical repository, package, Skill, and web slugs as `mixmatter` for compatibility
- replaced the previous offset-sheet badge with a layered material icon built from source, photographic, halftone, tape, and marker elements
- added coordinated light and dark icon variants with identical geometry and corrected depth ordering
- shifted the active identity to a cool blue / cyan / lavender material palette
- updated plugin-facing identity and public documentation while keeping the 2.0 reconstruction behavior intact

### Added

- `assets/mixmatter-icon-light.svg`
- `assets/mixmatter-icon-dark.svg`

## 2.0.0 — 2026-09-11

### Added

- seven research-derived canonical system documents covering runtime, art direction, core constitution, regression benchmarking, shared schema, capability contracts, and visual grammar
- staged reasoning model: `READ → UNDERSTAND → PROTECT → DIRECT → RECONSTRUCT → MATERIALIZE → CRITIQUE → REVISE`
- source-specific preservation contracts using `must preserve / should preserve / may transform / may remove`
- semantic-anchor, visual-anchor, structural-relation, identity-invariant, low-information-field, and transformation-budget concepts
- source-specific direction hypotheses rather than generic style presets
- cause-level critique and revision continuity
- source-type preservation defaults and a 40-image regression benchmark design
- natural-language Direction, Structure, and Intensity semantics

### Changed

- upgraded MixMatter from a reconstruction prompt system into a research-backed AI art-direction and visual-reconstruction system
- vague requests now default to autonomous source-specific judgment; clarification or alternatives are reserved for genuine ambiguity
- revisions preserve successful crop, hierarchy, locks, identity, and material decisions instead of behaving like random rerolls
- alternative directions return to the original source image unless the user explicitly asks to build on a prior result
- material effects are now explicitly causal and bounded rather than mandatory style signatures
- strengthened the default requirement for visibly reconstructed composition so restraint does not collapse into ordinary photo styling
- retained the established v1 visual language as rendering authority while adding 2.0 reasoning and preservation intelligence
- retained strict source-text protection and zero-new-text default
- public product name standardized as **MixMatter** while package/repository identifiers may continue to use `mixmatter`

### Architecture

- remains a **Skills-only** Agent Skill / OpenAI Plugin architecture
- no MCP server is required
- no custom ChatGPT host UI is required
- no external MixMatter image-generation backend is required
- host-native image understanding and generation/editing capabilities are used when available
- future web or backend runtimes may implement the same six capability contracts without redefining the core product

### Removed

- ChatGPT creation-card and result-card implementation
- MCP widget server and host bridge
- UI-specific runtime dependencies, state assumptions, and host UI specifications
- prompt behavior that required a card or widget for vague requests and revisions

### Preserved from the abandoned UI experiment

- Direction / Structure / Intensity as product semantics
- revision continuity
- distinction between revision-from-result and alternative-from-source
- Typography, Restore, and Custom as interpretable direction families where relevant
- the final MixMatter product logo

## 1.0.2 — 2026-09-10

### Changed

- rebuilt the master prompt around stronger flat, planar, and designed-2D-surface composition
- added the default zero-new-text rule for sources with and without visible text
- prohibited translation, parallel bilingual versions, and second-language equivalents of monolingual source text
- added explicit handling for source content that is already bilingual
- added the exact-user-wording exception without permitting extra copy, translation, or unrequested bilingual variants
- added text-footprint guidance of about 15% total readable area and about 8% for any single readable block unless the user explicitly requests larger treatment of their exact supplied text
- added high text-density scene guidance that preserves typographic density rather than typographic completeness
- strengthened halftone as a clearly visible, intentionally varied structural device
- strengthened torn-paper collage through visible tears, cut-paper overlaps, rough interruptions, pasted fragments, and deliberate paper-layer transitions
- synchronized the universal Skill, OpenAI-packaged Skill, master prompt, packaged prompt reference, quality rubric, manifest, listing copy, and review tests
- replaced the truncated plugin icon with a safely decodable 1024×1024 RGBA PNG exported from the canonical dark SVG mark
- aligned the plugin manifest with the current ingestion schema by adding capabilities and removing the unsupported `supportURL` field
- bumped OpenAI plugin metadata to `1.0.2`

### Text-control contract

A compliant v1.0.2 result adds zero new text by default. Source text remains in its original language and may be retained, cropped, obscured, fragmented, or reduced. When a user explicitly supplies text to add, only that exact wording may appear; no translation, bilingual duplication, subtitle, caption, label, or filler copy may be added.

## 1.0.1 — 2026-09-10

### Changed

- replaced the ambiguous `text-free` wording with an explicit no-new-typography rule
- added a four-part source-text policy for incidental, scene-identifying, identity-critical, and text-dominant sources
- added the governing principle: `Source text is content. New typography is generation.`
- added a fallback rule: if exact source text cannot be preserved reliably, crop, obscure, simplify, or retain it as photographic texture rather than hallucinating a replacement
- strengthened hard failures for pseudo-text, filler editorial copy, translated/rewritten/duplicated source text, enlarged source-text headlines, and approximate hallucinated replacements
- reduced prompt language that strongly implied typography-led poster or magazine-cover design
- clarified that MixMatter hierarchy must come from crop, scale, color, texture, source-derived geometry, overlap, and negative space rather than generated headlines or body copy
- synchronized the universal Skill, OpenAI-packaged Skill, master prompt, packaged reference, and quality rubric around the same text policy
- updated OpenAI starter prompts to explicitly prohibit new text while allowing source text to survive selectively
- bumped OpenAI plugin metadata to `1.0.1`
- aligned manifest developer name with the verified public developer identity `Fan Jiale`

### Regression target

The v1.0.1 hotfix specifically addressed source photographs containing signage triggering newly invented editorial headlines, filler copy, duplicated source words, or pseudo-text.

## OpenAI Plugin packaging — pre-2.0

### Added

- `.codex-plugin/plugin.json` for OpenAI plugin packaging
- `skills/mixmatter/SKILL.md` as the OpenAI-packaged Skill entry point
- self-contained bundled references for the master prompt and quality rubric
- host behavior for missing-image handling and direct image generation/editing when available
- brand, privacy, terms, support, evaluation, and listing materials
- repo-scoped development marketplace metadata

### Architecture

- Skills-only plugin with no MCP server, authentication layer, or external runtime dependency
- root `SKILL.md` remains the canonical universal Agent Skill entry point
- behavioral changes require a versioned release and changelog entry

## 1.0.0 — 2026-09-09

Initial MixMatter image-only release.

### Added

- source-aware reconstruction workflow
- structural anchor preservation
- Disassemble / Recompose / Reassign / Reduce / Hierarchize method
- selective photographic, printed, graphic, and collaged visual states
- source-derived graphics rule
- limited-palette print language
- selective halftone guidance
- collage discipline rules
- explicit failure modes
- 100-point quality rubric
- 10 canonical high-resolution before/after showcase plates across multiple source categories

### Baseline status

- v1.0.0 established the initial image-only core baseline
- platform-specific packaging may add manifests, metadata, assets, or synchronized Skill copies
- behavioral changes require a versioned release and a changelog entry

### Intentionally excluded

- generated typography
- inferred place names
- captions and metadata
- typography-led poster layouts
