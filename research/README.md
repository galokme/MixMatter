# MixMatter Research

MixMatter Research is the software and experimentation layer that sits alongside the independently packageable MixMatter 2.1 OpenAI/Codex plugin.

The Research Prototype exists to validate:

- a Semantic Design Document as the structured representation of a design;
- an Intent Engine that converts natural-language direction into design intent;
- a Design Engine that produces source-aware design operations;
- a Constraint Engine that protects semantic, structural, and product rules;
- A/B/C candidate generation and comparison;
- Accept, Reject, and Undo preference signals;
- contextual Learning V0;
- a portable `.mixmemory` format for personal design intelligence; and
- a Windows Research Prototype.

Research plans belong in `research/plan/`, architectural decisions in `research/decisions/`, and experiment records in `research/experiments/`.

The existing plugin and Skill remain the current production-compatible product layer. Research software must evolve without making that layer depend on web, desktop, backend, or workspace tooling.
