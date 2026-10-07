# Mixmatter

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/mixmatter-icon-dark.svg">
    <img src="./assets/mixmatter-icon-light.svg" alt="Mixmatter app icon" width="184">
  </picture>
</p>

**AI art direction and source-aware visual reconstruction for existing imagery.**

Mixmatter treats photographs as visual matter: something to read, protect, cut, flatten, layer, and rebuild with intent.

Mixmatter is an open-source **Agent Skill / SKILL.md** that reads a source image, decides what must survive, forms a source-specific art-direction thesis, and reconstructs the image into a contemporary print-driven composition.

> **Photography is source material, not sacred material.**
>
> **Reconstruct, do not decorate.**
>
> **Preserve semantic identity, not visual completeness.**

Mixmatter 2.1 keeps the visual DNA established in v1 while adding stronger source understanding, preservation logic, art-direction judgment, critique, and revision continuity. It remains a **Skills-only** system. There is no required MCP server or custom ChatGPT host UI.

## Install

```bash
npx skills add Fanjiale-CN/press-print --list
npx skills add Fanjiale-CN/press-print --skill mixmatter
```

Repository: `Fanjiale-CN/press-print`  
Skill: `mixmatter`  
Entry point: `SKILL.md`

### Claude Code

```text
/plugin marketplace add galokme/MixMatter
/plugin install mixmatter@mixmatter
```

Or copy the skill folder directly:

```bash
git clone https://github.com/galokme/MixMatter.git
mkdir -p ~/.claude/skills && cp -r MixMatter/skills/mixmatter ~/.claude/skills/
```

### Claude.ai / Claude desktop app

Zip the `skills/mixmatter/` folder (so `mixmatter/SKILL.md` is at the top of the archive) and upload it under **Settings → Capabilities → Skills**.

> **Identity:** the OpenAI package and Skill slug are `mixmatter`. The current GitHub repository URL remains `Fanjiale-CN/press-print` until the repository slug itself is renamed.

## How Mixmatter 2.1 works

The internal reasoning sequence is:

```text
READ
→ UNDERSTAND
→ PROTECT
→ DIRECT
→ RECONSTRUCT
→ MATERIALIZE
→ CRITIQUE
→ REVISE
```

The user does not need to operate those stages manually. A clear request executes directly. A vague request is inspected and art-directed autonomously unless genuine ambiguity would materially change the result.

### READ / UNDERSTAND
Identify semantic anchors, visual anchors, structural relations, identity invariants, clutter, low-information fields, directional forces, and transformation opportunities.

### PROTECT
Classify source information into:

- must preserve
- should preserve
- may transform
- may remove

Explicit user locks always outrank defaults.

### DIRECT
Form one dominant source-specific thesis about what to amplify, suppress, reframe, flatten, isolate, or fragment.

Direction is structural judgment, not a generic style preset.

### RECONSTRUCT
Prefer structural operations before effects:

- crop / reframe
- isolate
- suppress
- scale contrast
- planar compression
- controlled fragmentation, overlap, or repetition when justified

A successful default result should be visibly reconstructed, not merely photo-styled.

### MATERIALIZE
Use halftone, duotone, torn/cut edges, paper layering, registration error, photocopy behavior, and related print materiality only when they reinforce the composition.

### CRITIQUE / REVISE
Preserve successful decisions and fix the cause of a failure rather than re-randomizing the whole image.

## Natural-language controls

Mixmatter retains three useful semantic controls without requiring a custom UI:

- **Direction**: the dominant reconstruction thesis
- **Structure**: how much original compositional continuity may be spent
- **Intensity**: how strongly the chosen treatment appears

Users may state these explicitly or simply describe what they want in normal language.

## Core visual identity

Mixmatter generally prefers:

- flat, surface-first composition
- compressed or interrupted depth
- strong editorial hierarchy
- source-derived crop and scale shifts
- interlocking graphic planes
- selective photographic retention
- visible but selective halftone / duotone
- bold silhouette and shape logic
- controlled tactile collage
- active low-information fields
- contemporary print energy rather than generic retro styling

It avoids:

- intact photo + cosmetic texture
- generic premium-ad polish
- cinematic realism drift
- blanket halftone
- uniform torn-paper treatment
- arbitrary fragmentation
- generic vector tracing
- culture-as-costume styling
- template sameness across unrelated sources

## Source text policy

Mixmatter adds **zero new text by default**.

If source text already exists, it may be preserved, cropped, obscured, fragmented, reduced, or treated as source imagery. Identity-critical wording should be preserved faithfully when feasible.

Mixmatter must not:

- invent approximate replacement wording
- translate source text by default
- create bilingual duplicates by default
- turn source signage into a newly typeset headline without instruction
- hallucinate pseudo-text when exact text cannot be reproduced

If the user supplies exact wording, use only that wording unless they explicitly authorize generated copy.

## Research-derived system

Mixmatter 2.1 is grounded in seven canonical system documents:

1. [`docs/MIXMATTER_2_RUNTIME.md`](docs/MIXMATTER_2_RUNTIME.md)
2. [`docs/system/MIXMATTER_ART_DIRECTION_POLICY.md`](docs/system/MIXMATTER_ART_DIRECTION_POLICY.md)
3. [`docs/system/MIXMATTER_CORE_CONSTITUTION.md`](docs/system/MIXMATTER_CORE_CONSTITUTION.md)
4. [`docs/system/MIXMATTER_REGRESSION_BENCHMARK.md`](docs/system/MIXMATTER_REGRESSION_BENCHMARK.md)
5. [`docs/system/MIXMATTER_SYSTEM_SCHEMA.yaml`](docs/system/MIXMATTER_SYSTEM_SCHEMA.yaml)
6. [`docs/system/MIXMATTER_TOOL_SPEC.md`](docs/system/MIXMATTER_TOOL_SPEC.md)
7. [`docs/system/MIXMATTER_VISUAL_GRAMMAR.md`](docs/system/MIXMATTER_VISUAL_GRAMMAR.md)

These preserve the research layer independently of any particular interface implementation.

## Visual authority

The established v1 rendering language remains available at:

- [`prompt/mixmatter-v1.md`](prompt/mixmatter-v1.md)
- [`skills/mixmatter/references/mixmatter-v1.md`](skills/mixmatter/references/mixmatter-v1.md)

The 2.0 reasoning layer extends that visual language rather than replacing it.

## Showcase

The repository retains the ten canonical high-resolution v1 source/result showcase plates in [`examples/showcase/`](examples/showcase/). See [`examples/README.md`](examples/README.md) for notes and evaluation guidance.

## Evaluation

Use:

- [`eval/quality-rubric.md`](eval/quality-rubric.md)
- [`docs/system/MIXMATTER_REGRESSION_BENCHMARK.md`](docs/system/MIXMATTER_REGRESSION_BENCHMARK.md)

The 2.0 benchmark evaluates semantic preservation, Mixmatter identity, reconstruction strength, editorial hierarchy, planar coherence, material coherence, source specificity, and common drift penalties.

## Repository structure

```text
mixmatter/
├── SKILL.md
├── skills/mixmatter/
│   ├── SKILL.md
│   └── references/
│       ├── mixmatter-v1.md
│       ├── mixmatter-v2-runtime.md
│       └── quality-rubric.md
├── docs/
│   ├── MIXMATTER_2_RUNTIME.md
│   └── system/
│       ├── MIXMATTER_ART_DIRECTION_POLICY.md
│       ├── MIXMATTER_CORE_CONSTITUTION.md
│       ├── MIXMATTER_REGRESSION_BENCHMARK.md
│       ├── MIXMATTER_SYSTEM_SCHEMA.yaml
│       ├── MIXMATTER_TOOL_SPEC.md
│       └── MIXMATTER_VISUAL_GRAMMAR.md
├── prompt/mixmatter-v1.md
├── eval/
└── examples/
```

## Current status

**Version:** 2.1.0  
**Architecture:** Skills-only, UI-independent  
**Status:** Research-integrated release candidate

## Author

Created by **Fan Jiale / Galok**.

## License

MIT for the Mixmatter skill text, prompt system, documentation, and related project materials. See `LICENSE`.

Showcase image rights may depend on their original provenance. See [`examples/README.md`](examples/README.md).
