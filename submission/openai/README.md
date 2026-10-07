# OpenAI Plugin Submission Materials — MixMatter 2.2

This directory contains review-facing materials for the UI-independent MixMatter 2.2 Plugin package.

## Architecture

**Skills-only / no MCP runtime**

MixMatter 2.2 does not require:

- an MCP server,
- a custom ChatGPT host UI,
- authentication,
- an external account,
- a separate MixMatter image-generation backend,
- reviewer credentials or private fixture data.

The Plugin supplies art-direction and visual-reconstruction instructions. The host platform performs image understanding and image generation/editing when those capabilities are available.

## Plugin identity

- Public name: `MixMatter`
- Package name: `mixmatter`
- Publisher brand: `Galok`
- Developer identity: `Fan Jiale`
- Category: `Creativity`
- Short description: `AI art direction for existing imagery`
- Version: `2.2.0`
- Repository: `https://github.com/galokme/MixMatter`

## Package contents

The complete Plugin ZIP should preserve the repository-relative structure required by the submission portal, including the manifest and the Skill bundle.

Relevant files:

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

Do not package the abandoned `apps/mixmatter-chatgpt/` UI layer. It is not part of MixMatter 2.2.

## Canonical behavior

The runtime is the restored v1 visual baseline in `skills/mixmatter/SKILL.md`: identify structural anchors, disassemble, recompose, reassign photographic / printed / graphic / collaged states, then reduce and hierarchize. The 2.0 research documents under `docs/` are reference material, not runtime authority.

Key reviewer expectations:

- clear requests execute directly,
- vague requests are handled with source-specific judgment rather than a generic menu,
- semantic identity and source-defining structural anchors are protected,
- reconstruction is visibly compositional rather than filter-only,
- halftone and collage are selective, never blanket effects,
- unrelated sources do not collapse into one recurring decorative template,
- revisions preserve successful decisions; alternatives start from the original source,
- zero new text is added by default,
- source text is not translated or bilingual-duplicated by default.

## Public listing URLs

- Website: `https://www.galok.me/mixmatter/`
- Support: `https://www.galok.me/mixmatter/support/`
- Privacy: `https://www.galok.me/mixmatter/privacy/`
- Terms: `https://www.galok.me/mixmatter/terms/`

Fan Jiale is the individual developer; Galok is the public publishing brand.

## Submission files

- `listing-and-prompts.md` — 2.2 listing copy and starter prompts
- `test-cases.md` — positive and negative review tests
- `release-notes.md` — 2.2 release notes and availability guidance
- `final-checklist.md` — final packaging and portal checklist

## Reviewer setup

For positive tests, reviewers can attach any non-sensitive image they have permission to use. No MixMatter account, API key, demo credentials, MFA, private-network access, or fixture database is required.
