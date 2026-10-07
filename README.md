# MixMatter

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/mixmatter-icon-dark.svg">
    <img src="./assets/mixmatter-icon-light.svg" alt="MixMatter app icon" width="184">
  </picture>
</p>

**AI art direction and source-aware visual reconstruction for existing imagery.**

MixMatter is an open-source **Agent Skill** that takes a photograph you supply, decides what must survive, and rebuilds it into a bold, flat, print-driven composition: selective photography, visible halftone or duotone, flattened graphic fields, tactile torn-paper collage, and modernist hierarchy.

> **Photography is source material, not sacred material.**
>
> **Reconstruct, do not decorate.**
>
> **Preserve semantic identity, not visual completeness.**

It runs anywhere Agent Skills load (Claude, Claude Code, ChatGPT, Codex) and needs no MCP server, account, or separate backend. The host model does the image understanding and, where available, the image generation.

## Install

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

### Claude.ai and the Claude apps

Zip the skill folder so that `mixmatter/SKILL.md` sits at the top of the archive:

```bash
git clone https://github.com/galokme/MixMatter.git
cd MixMatter/skills && zip -r ../../mixmatter-skill.zip mixmatter
```

Then upload `mixmatter-skill.zip` under **Settings → Capabilities → Skills** and switch it on.

### ChatGPT and Codex

The repository is also an OpenAI plugin (`plugin.json`, `.codex-plugin/plugin.json`). For local Codex testing:

```bash
codex plugin marketplace add galokme/MixMatter --ref main
```

### Other Agent Skills hosts

```bash
npx skills add galokme/MixMatter --skill mixmatter
```

## Use

Attach a photograph and ask in plain language:

```text
Process this image with MixMatter.
用 MixMatter 處理這張圖，不要加任何文字。
Make this flatter and more graphic with MixMatter. Keep the main subject and the tower silhouette.
Keep this crop. Reduce the tearing and make the right side quieter.
Try another direction from the original image — more restrained and planar.
```

In Claude Code you can also call it explicitly with `/mixmatter:mixmatter`.

If the host can generate or edit images, MixMatter produces the image. If it can only read images (for example, a Claude conversation without an image tool), MixMatter returns a concise, source-specific brief you can paste into your image model instead of pretending to render.

## How it works

MixMatter's runtime is the **v1 visual baseline** in [`skills/mixmatter/SKILL.md`](skills/mixmatter/SKILL.md). For every source it silently:

1. **Identifies structural anchors**: the 1–3 structures that make the scene recognizable (a tower silhouette, a coastline curve, a window grid, identity-critical signage).
2. **Disassembles** the photo into meaningful components rather than treating it as one intact image.
3. **Recomposes** them into a new hierarchy through crop, scale shift, overlap, displacement, and compressed depth.
4. **Reassigns visual states**: some regions stay photographic, some become printed (halftone or duotone), some graphic (flat fields and silhouettes), some collaged.
5. **Reduces and hierarchizes**, so the result has dominant, secondary, and quiet zones.

Color is derived from the source (roughly 3–6 families), not from a fixed MixMatter palette, so unrelated images produce materially different results.

You can steer three things in ordinary language: **direction** (what to amplify or suppress), **structure** (how far the original composition may be broken), and **intensity** (how strongly the print and collage treatment appears). Revisions keep what already works; alternatives start again from the original source.

## Source-text policy

MixMatter adds **zero new text by default**.

- Source text is content: it may be kept, cropped, obscured, fragmented, or reduced to texture.
- Identity-critical wording (a station name, a storefront) is preserved faithfully where feasible.
- Source text is never translated, duplicated into a bilingual layout, rewritten, or replaced with guessed wording or pseudo-text.
- If you supply exact wording, only that wording is added.

## Showcase

The ten canonical v1 before/after plates live in [`examples/showcase/`](examples/showcase/). They are kept at full resolution so halftone structure and paper edges stay inspectable; click a plate to open the original.

<p>
  <a href="examples/showcase/0D0EB3E7-CDA9-4F6C-B8C5-B6613F6CEBCB.png"><img src="examples/showcase/0D0EB3E7-CDA9-4F6C-B8C5-B6613F6CEBCB.png" alt="MixMatter before/after plate 1" width="100%"></a>
  <a href="examples/showcase/2045E30A-8BAE-4625-B726-1EBC31166618.png"><img src="examples/showcase/2045E30A-8BAE-4625-B726-1EBC31166618.png" alt="MixMatter before/after plate 2" width="100%"></a>
  <a href="examples/showcase/43A519AD-FAA7-40EE-9425-D8EA1CCAA11C.png"><img src="examples/showcase/43A519AD-FAA7-40EE-9425-D8EA1CCAA11C.png" alt="MixMatter before/after plate 3" width="100%"></a>
  <a href="examples/showcase/48FEE737-3D46-446B-AAEF-6F1ADB22E70F.png"><img src="examples/showcase/48FEE737-3D46-446B-AAEF-6F1ADB22E70F.png" alt="MixMatter before/after plate 4" width="100%"></a>
  <a href="examples/showcase/52C803C9-C030-4574-8FEF-CE30FDF6A5C4.png"><img src="examples/showcase/52C803C9-C030-4574-8FEF-CE30FDF6A5C4.png" alt="MixMatter before/after plate 5" width="100%"></a>
  <a href="examples/showcase/7AA8CDA5-FC9F-4698-A622-329A248F90FB.png"><img src="examples/showcase/7AA8CDA5-FC9F-4698-A622-329A248F90FB.png" alt="MixMatter before/after plate 6" width="100%"></a>
  <a href="examples/showcase/8E3C63CD-7AD2-4E0A-A4AD-AB9C82A9044A.png"><img src="examples/showcase/8E3C63CD-7AD2-4E0A-A4AD-AB9C82A9044A.png" alt="MixMatter before/after plate 7" width="100%"></a>
  <a href="examples/showcase/A9F371AC-D68C-4BC5-AD10-261487723695.png"><img src="examples/showcase/A9F371AC-D68C-4BC5-AD10-261487723695.png" alt="MixMatter before/after plate 8" width="100%"></a>
  <a href="examples/showcase/AE838326-B4A9-443E-AF99-B1FE4AB22525.png"><img src="examples/showcase/AE838326-B4A9-443E-AF99-B1FE4AB22525.png" alt="MixMatter before/after plate 9" width="100%"></a>
  <a href="examples/showcase/C24DF515-DCB7-4D3A-A871-BDC8F58B38C1.png"><img src="examples/showcase/C24DF515-DCB7-4D3A-A871-BDC8F58B38C1.png" alt="MixMatter before/after plate 10" width="100%"></a>
</p>

See [`examples/README.md`](examples/README.md) for what to look for and the media rights note.

## Research layer

The 2.0 research documents describe a staged art-direction model (`READ → UNDERSTAND → PROTECT → DIRECT → RECONSTRUCT → MATERIALIZE → CRITIQUE → REVISE`), preservation contracts, and a 40-image regression benchmark. They are kept for design reference and evaluation. **They are not runtime authority**: since 2.1.1 the v1 visual runtime in `skills/mixmatter/` is the only behavior hosts load.

1. [`docs/MIXMATTER_2_RUNTIME.md`](docs/MIXMATTER_2_RUNTIME.md)
2. [`docs/system/MIXMATTER_ART_DIRECTION_POLICY.md`](docs/system/MIXMATTER_ART_DIRECTION_POLICY.md)
3. [`docs/system/MIXMATTER_CORE_CONSTITUTION.md`](docs/system/MIXMATTER_CORE_CONSTITUTION.md)
4. [`docs/system/MIXMATTER_REGRESSION_BENCHMARK.md`](docs/system/MIXMATTER_REGRESSION_BENCHMARK.md)
5. [`docs/system/MIXMATTER_SYSTEM_SCHEMA.yaml`](docs/system/MIXMATTER_SYSTEM_SCHEMA.yaml)
6. [`docs/system/MIXMATTER_TOOL_SPEC.md`](docs/system/MIXMATTER_TOOL_SPEC.md)
7. [`docs/system/MIXMATTER_VISUAL_GRAMMAR.md`](docs/system/MIXMATTER_VISUAL_GRAMMAR.md)

## Evaluation

- [`eval/quality-rubric.md`](eval/quality-rubric.md): the 100-point rubric (mirror of the packaged copy)
- [`docs/system/MIXMATTER_REGRESSION_BENCHMARK.md`](docs/system/MIXMATTER_REGRESSION_BENCHMARK.md): broader release benchmark
- [`eval/openai-plugin-test-plan.md`](eval/openai-plugin-test-plan.md): host test plan

## Repository structure

```text
MixMatter/
├── skills/mixmatter/            # canonical runtime (what every host loads)
│   ├── SKILL.md
│   └── references/
│       ├── mixmatter-v1.md      # master generation prompt
│       └── quality-rubric.md
├── SKILL.md                     # root entry point that points to the canonical skill
├── prompt/mixmatter-v1.md       # mirror of references/mixmatter-v1.md
├── eval/                        # rubric mirror and host test plan
├── plugin.json                  # portable / OpenAI manifest
├── .codex-plugin/plugin.json    # Codex compatibility manifest
├── .claude-plugin/              # Claude Code plugin + marketplace
├── .agents/plugins/             # Codex development marketplace
├── docs/                        # 2.0 research layer (reference only)
├── examples/showcase/           # canonical before/after plates
├── submission/openai/           # OpenAI review materials
└── assets/                      # icons
```

CI checks that every manifest carries the same version, that the mirrors match the packaged copies byte for byte, and that retired names do not reappear.

## Status

**Version:** 2.2.0 · **Runtime:** v1 visual baseline (v1.0.2 text policy) · **Architecture:** Skills-only

See [`CHANGELOG.md`](CHANGELOG.md).

## Author

Created by **Fan Jiale / Galok**: [galok.me/mixmatter](https://www.galok.me/mixmatter/) · [support](SUPPORT.md)

## License

MIT for the MixMatter skill text, prompt system, documentation, and related project materials. See [`LICENSE`](LICENSE). The MixMatter and Galok names and marks are not licensed for implied endorsement; see [`BRAND.md`](BRAND.md).

Showcase image rights may depend on their original provenance. See [`examples/README.md`](examples/README.md).
