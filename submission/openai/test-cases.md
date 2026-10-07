# OpenAI Review Test Cases — MixMatter 2.2

These cases cover the UI-independent MixMatter 2.2 Skill, including autonomous art direction, preservation contracts, visible reconstruction, revision continuity, alternative-from-source behavior, and source-text protection.

MixMatter requires no account, authentication, demo credentials, external MCP server, or private fixture data.

For positive tests, attach any non-sensitive source image the reviewer has permission to use.

## Positive test cases

### P1 — Vague invocation / autonomous judgment

**User prompt**

`Process this image with MixMatter.`

**Fixture**

Attach a non-sensitive street, city, interior, object, or landscape image.

**Expected behavior**

MixMatter should inspect the actual source, identify semantic and structural anchors, determine what may be spent, form one source-specific direction thesis, and reconstruct the image without forcing the user through a custom menu or widget.

The result should be visibly recomposed rather than the intact photograph with a filter. Material effects should appear only where they support structure or hierarchy.

No new text should be introduced by default.

### P2 — Explicit strong reconstruction

**User prompt**

`Make this flatter and more graphic with MixMatter. Preserve the main subject and defining structure. No new text.`

**Fixture**

Attach a non-sensitive architecture, transport, streetscape, or public-space image.

**Expected behavior**

The request should execute directly. The result should use planar compression, crop/reframe, scale contrast, isolation, suppression, or other structural operations before decorative texture.

The subject and identity-bearing structure should survive while the camera composition is visibly reconstructed.

### P3 — Portrait preservation

**User prompt**

`Reconstruct this portrait with MixMatter. Keep the identity intact, simplify the background, and add no new typography.`

**Fixture**

Attach a non-sensitive portrait image the reviewer has permission to use.

**Expected behavior**

MixMatter should protect face identity, decisive pose/gesture, and important subject relationships while spending redundant background detail first.

The result should remain recognizable as the same person and source situation while becoming more planar, hierarchically intentional, and designed.

### P4 — Dense source signage

**User prompt**

`用 MixMatter 重构这张街景。保留场景身份，但不要新增、翻译或双语复制任何文字。`

**Fixture**

Attach a non-sensitive metro, railway, storefront, or dense commercial-street image with visible signage.

**Expected behavior**

Scene-identifying or identity-critical source text may remain selectively when feasible. Other text may be cropped, fragmented, obscured, halftoned, or reduced into texture.

MixMatter must not translate monolingual signs, create bilingual duplicates, invent replacement wording, or generate filler editorial copy. If exact text cannot be reproduced reliably, obscure or simplify it rather than hallucinating it.

### P5 — Revision continuity

**Prerequisite**

Create a successful MixMatter result from any suitable source.

**User prompt**

`Keep this crop and the subject treatment. Reduce the tearing and make the right side quieter.`

**Expected behavior**

The revision should preserve successful crop, subject identity, hierarchy, locks, and useful material decisions. It should primarily reduce fragmentation/materiality and suppress the right side rather than rerolling the full composition.

The revised result should remain clearly related to the previous successful version.

### P6 — Alternative from original source

**Prerequisite**

Create at least one MixMatter result from a source image.

**User prompt**

`Try another direction from the original image. Make it more restrained and planar.`

**Expected behavior**

MixMatter should conceptually return to the original source image rather than recursively transforming the previous generated result.

Useful semantic lessons and explicit preservation locks may carry over, but the alternative should form a new direction thesis from the original source.

## Optional positive extension — Exact user wording

**User prompt**

`Reconstruct this with MixMatter and add only the exact text “地铁”.`

**Expected behavior**

The result may add `地铁` and no other new copy unless the user separately authorizes generated text. It must not add a translation, subtitle, caption, date, filler copy, or bilingual parallel wording.

## Negative test cases

### N1 — Faithful restoration without MixMatter intent

**User prompt**

`Restore this old photograph naturally and faithfully.`

**Expected behavior**

MixMatter should not be selected automatically. Faithful archival-style restoration is outside its core reconstruction workflow.

**Safe fallback**

Use the host's normal restoration or enhancement behavior.

### N2 — Unrelated watercolor conversion

**User prompt**

`Turn this image into a watercolor painting.`

**Expected behavior**

MixMatter should not be selected automatically because the request asks for a different transformation language rather than MixMatter reconstruction.

### N3 — From-scratch typography-heavy design

**User prompt**

`Design a typography-heavy exhibition poster from scratch with a large headline, date, and editorial body copy.`

**Expected behavior**

MixMatter should not be selected automatically. Its core identity is source-image art direction and reconstruction, not a generic from-scratch typesetting suite.

If the user explicitly invokes MixMatter with a source image, exact supplied wording or explicitly authorized generated copy may be used under the Skill's typography rules.

## 2.2 regression checks

Reject or revise a generated result if any of the following occurs:

- source semantic identity collapses
- the output is mostly the intact source photo with cosmetic treatment
- hierarchy is weaker or no more intentional than the source without a deliberate reason
- a vague request produces generic style presets instead of source-specific judgment
- arbitrary fragmentation damages identity-bearing relations
- halftone, tearing, paper, grain, or misregistration is used globally without structural cause
- the result drifts into cinematic realism or generic premium-ad polish
- unrelated source categories collapse into the same template
- cultural references become decorative costume or stereotypes
- a revision rerandomizes successful decisions instead of addressing the requested axis
- an alternative requested from the original silently uses the prior generated result as mandatory visual input
- unrequested readable text appears
- source text is translated, bilingual-duplicated, materially rewritten, or replaced with hallucinated wording
- user-supplied exact text is altered or surrounded with extra unrequested copy

## Research benchmark note

For broader release validation, use `docs/system/MIXMATTER_REGRESSION_BENCHMARK.md`, which defines the 40-image target set, source categories, hard cases, scoring dimensions, identity gates, and failure taxonomy.
