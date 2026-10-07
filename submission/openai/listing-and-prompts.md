# Listing Copy and Starter Prompts — MixMatter 2.2

## Info

### Plugin name

`MixMatter`

### Short description

`AI art direction for existing imagery`

### Long description

MixMatter turns a user-supplied image into a source-aware contemporary print reconstruction.

It reads the source before transforming it: identifying the one to three structures that make the scene recognizable, then disassembling the photograph into meaningful components and rebuilding them into a new hierarchy through crop, scale shift, overlap, displacement, and compressed depth. Different regions take different states — retained photography, visible halftone or duotone, flat graphic fields, and tactile torn-paper collage — so the result reads as a designed, printed surface rather than a filtered photo.

> **Photography is source material, not sacred material.**
>
> **Reconstruct, do not decorate.**
>
> **Preserve semantic identity, not visual completeness.**

Color is derived from each source rather than from a fixed palette, so unrelated images produce materially different results instead of one recurring template. Clear requests execute directly; vague requests get source-specific judgment. Revisions keep successful crop, identity, and hierarchy, and alternatives start again from the original image.

MixMatter adds zero new text by default. Existing source text remains in its original language and may be preserved selectively when it matters to identity. It is never translated or duplicated into a bilingual layout by default. If exact source text cannot be reproduced reliably, it is obscured, cropped, simplified, or treated as texture rather than replaced with hallucinated wording. New wording is used only when the user supplies it exactly.

MixMatter is designed for existing imagery. It is not a generic style marketplace, broad photo editor, cinematic realism engine, or from-scratch design suite.

Typical sources include:

- cities, streets, architecture, transport, and infrastructure
- landscapes, interiors, and public spaces
- portraits, people, and performance
- objects, retail environments, and cultural artifacts

MixMatter does not operate a separate image-generation backend or require an MCP service. Image understanding and generation/editing are performed by the host platform when available.

### Category

`Creativity`

### Publisher

- Public publisher brand: `Galok`
- Developer: `Fan Jiale`, an individual developer publishing under the Galok brand
- Verified developer identity: `Fan Jiale`

### Version

`2.2.0`

### Public URLs

- Website: `https://www.galok.me/mixmatter/`
- Support: `https://www.galok.me/mixmatter/support/`
- Privacy policy: `https://www.galok.me/mixmatter/privacy/`
- Terms of use: `https://www.galok.me/mixmatter/terms/`

## Starter prompts

1. `Process this image with MixMatter. Preserve what makes the source identifiable and do not add new text.`
2. `Make this image flatter and more graphic with MixMatter. Preserve the main subject and defining structure.`
3. `Reconstruct this portrait with MixMatter. Keep the identity intact, simplify the background, and add no new typography.`

## Prompt intent

The three prompts test autonomous default judgment, stronger graphic reconstruction, and portrait preservation.

All starter prompts assume that the user attaches a source image. MixMatter uses host image understanding and image generation/editing when those capabilities are available; it does not operate a separate image-generation backend or custom host UI.
