# ADR-0001: Plugin and software boundary

- **Status:** Accepted for Day 0
- **Date:** 2026-09-21

## Context

MixMatter 2.1 is an independently packageable OpenAI/Codex plugin and Skill. MixMatter Research will add an executable design environment alongside it. The two layers need a clear boundary so software experimentation does not destabilize the current plugin.

## Decision

1. The existing MixMatter 2.1 plugin and Skill layer remains independently packageable.
2. The new MixMatter Research software must not break, replace, or make the current OpenAI plugin dependent on the software workspace.
3. Shared design intelligence may later be extracted into packages when executable contracts are stable. Until then, the current canonical plugin documents and Skill remain intact.
4. Plugin packaging must explicitly exclude and must not accidentally include desktop, web, backend, workspace, or development dependencies.
5. Old Press Print UI branches remain historical references only. Their host UI and MCP implementation are not restored as the new application architecture.
6. The intended software architecture is React + TypeScript + pnpm + Tauri. React, TypeScript applications, Tauri, backends, and their dependencies are not initialized during Day 0.

## Repository boundary

- Existing plugin layer: root plugin manifests, `.codex-plugin/`, `.agents/`, `SKILL.md`, `skills/mixmatter/`, current plugin documentation, current plugin evaluation, submission materials, assets, examples, and plugin packaging workflows.
- Research/software layer: `research/`, `apps/`, `packages/`, `services/`, `evals/`, `fixtures/`, and `scripts/`.
- Root workspace files may discover future packages under `apps/*`, `packages/*`, and `services/*`, but they do not change the contents or packaging contract of the plugin layer.

## Consequences

- Existing plugin validation remains a release gate throughout the migration.
- `eval/` remains the current plugin evaluation suite; `evals/` is reserved for executable research/software evaluation.
- The legacy filename `.github/workflows/press-print-2-ci.yml` is a future cleanup item and is intentionally unchanged on Day 0.
- Any future extraction of shared rules must preserve behavior and be introduced through a separate architectural decision.
