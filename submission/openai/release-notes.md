# Release Notes and Availability

## Release notes

### MixMatter 2.2.0 — Cross-host packaging and consistency

MixMatter 2.2 keeps the restored v1 visual baseline and source-text policy unchanged. It adds a Claude Code plugin manifest, makes the Skill's host guidance platform-neutral, defines a concise source-specific brief for hosts that cannot render images, folds revision continuity and alternative-from-source behavior into the packaged Skill, and unifies naming, versions, and repository links across every manifest and document.

### MixMatter 2.1.1 — v1 visual runtime restored

Version 2.1.1 restored the v1 visual runtime as the sole runtime authority and removed the 2.0 runtime reference from the packaged Skill, with explicit guards against unrelated sources collapsing into one recurring decorative template.

### MixMatter 2.1.0 — Unified MixMatter identity and portable OpenAI package

MixMatter 2.1 unifies the product name, Skill slug, public website URLs, active icons, review materials, and plugin manifests under the MixMatter identity. It adds the preferred portable root `plugin.json` while retaining `.codex-plugin/plugin.json` as an OpenAI/Codex compatibility manifest. The core source-aware reconstruction behavior and Skills-only architecture remain unchanged.

### MixMatter 2.0.0 — Research-integrated art direction, no custom host UI

MixMatter 2.0 upgrades the project from a strong source-aware reconstruction prompt into a research-backed AI art-direction system for existing imagery.

The release adds:

- a staged reasoning model: `READ → UNDERSTAND → PROTECT → DIRECT → RECONSTRUCT → MATERIALIZE → CRITIQUE → REVISE`;
- semantic anchors, visual anchors, structural relations, identity invariants, low-information fields, and transformation budgets;
- source-specific preservation contracts;
- autonomous art-direction judgment for vague requests;
- revision continuity that preserves successful decisions;
- distinction between revising an existing result and trying an alternative from the original source;
- a regression benchmark for protecting both quality and MixMatter identity;
- stronger anti-drift rules against generic AI polish, cinematic realism, decorative texture, arbitrary fragmentation, and cultural-costume styling.

The established MixMatter v1 visual language remains authoritative. Version 2.0 extends the intelligence around that language rather than replacing it.

The architecture is deliberately **Skills-only and UI-independent**. MixMatter 2.0 does not require an MCP server, custom ChatGPT widget, external account, authentication flow, or separate image-generation backend. The host platform performs image understanding and generation/editing when supported.

Source-text control remains strict: zero new text by default, no automatic translation, no bilingual duplication, and no approximate hallucinated replacement of uncertain source text.

### MixMatter 1.0.2 — Planar reconstruction and source-text control

Version 1.0.2 strengthened flat 2D composition, interlocking planes, structural halftone, tactile collage, and source-text handling. It remains the visual baseline that 2.0 builds upon.

### MixMatter 1.0.0 — Initial public release

The initial Skills-only release established source-aware reconstruction, structural-anchor preservation, selective photographic / printed / graphic / collaged states, and the first quality rubric.

## Reviewer setup

Attach any non-sensitive source image the reviewer has permission to use. No demo credentials, MFA, SMS, email confirmation, private-network access, test account, or MixMatter API key are required.

## Availability recommendation

**Target:** countries and regions selectable in the OpenAI Plugin submission portal where the relevant host image capabilities are available and where the publisher is comfortable supporting the Plugin.

Rationale:

- MixMatter has no region-specific backend or infrastructure;
- it does not require a regional account system, payment provider, or external data service;
- public support, privacy, terms, and product pages are provided under `galok.me`.

Portal availability and OpenAI policy remain authoritative at submission time.
