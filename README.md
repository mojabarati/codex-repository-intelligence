# Codex Repository Intelligence & Self-Evolving Skills

A repository-specific setup prompt for turning project context, engineering conventions, security constraints, and operational knowledge into persistent guidance for Codex.

Instead of repeatedly re-explaining architecture and project rules in every task, the setup asks Codex to inspect the **actual repository** and create a compact, version-controlled context system using:

- `AGENTS.md` for repository-wide guidance and rules
- `.agents/skills/<skill-name>/SKILL.md` for project-specific engineering playbooks
- a **Skill Evolution** mechanism that updates or creates Skills when future tasks reveal stable, reusable repository knowledge

> The goal is not to make the repository accumulate generic AI instructions. The goal is to keep a small, evidence-based context layer synchronized with the codebase.

## What the setup covers

The prompt instructs Codex to inspect the repository before creating guidance, including relevant areas such as:

- project structure and technology stack
- frontend and UI/design-system patterns
- backend and API conventions
- database and data-integrity patterns
- testing and validation commands
- production-sensitive areas
- authentication, authorization, permissions, uploads, webhooks, secrets, and other security boundaries

It then creates only the repository-local Skills that are justified by the codebase.

## Self-Evolving Skills

For substantial future tasks, Codex is instructed to:

1. inspect available repository Skills;
2. select the Skills relevant to the task;
3. identify reusable project knowledge that is missing or outdated;
4. update an existing Skill when the knowledge belongs there;
5. create a new Skill only when a meaningful recurring domain is not adequately covered;
6. avoid Skill changes for temporary, trivial, speculative, or one-off knowledge;
7. keep Skill changes reviewable and report them explicitly.

The prompt also includes safeguards against Skill bloat and against silently turning task-level decisions into permanent architecture or product rules.

## Security and production safety

Security is explicitly evaluated during setup. A dedicated Security Skill is created only when the repository's real attack surface justifies one.

The same applies to Production Safety. Security and Production Safety are treated as different concerns and are separated when the repository benefits from that distinction.

The setup itself is analysis/guidance-only: it instructs Codex **not** to implement product features, modify application behavior, run destructive migrations, change production configuration, or expose secrets during the initial setup.

## How to use it

### 1. Start from the repository root

Open a **new Codex chat/session** from the root of the existing project you want to configure.

### 2. Run the setup prompt

Copy the full contents of [`PROMPT.md`](./PROMPT.md) into that new session and let Codex complete the repository analysis and guidance setup.

Expected repository-local output will typically include:

```text
AGENTS.md
.agents/
└── skills/
    ├── <skill-name>/
    │   └── SKILL.md
    └── ...
```

The exact Skills should be determined from the repository rather than from a fixed list.

### 3. Start a fresh session for normal work

After the initial setup finishes, open a **new session** from the same repository root and continue with normal feature, bug-fix, refactor, or maintenance tasks.

For substantial tasks, the generated `AGENTS.md` should instruct Codex to inspect and use the relevant repository Skills before implementation, then evaluate whether those Skills should evolve based on verified reusable knowledge discovered during the task.

## Important design principles

- Repository evidence over assumptions
- Project-specific Skills over generic personas
- Small, high-value Skill set over Skill proliferation
- Security invariants can justify persistent guidance even when discovered once
- Skills document established decisions; they should not silently create governance decisions
- Persistent context should remain concise enough to be useful as agent context
- `AGENTS.md` and Skills should remain version-controlled and reviewable

## Full prompt

The complete setup prompt is available here:

**[PROMPT.md](./PROMPT.md)**

## Notes

This is an opinionated workflow for AI-assisted software development. It is intended to reduce repeated context transfer and improve consistency, but the generated guidance still needs normal engineering review. Repository instructions should evolve from verified project evidence, not from assumptions or accidental implementation patterns.
