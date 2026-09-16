# Codex Repository Intelligence & Self-Evolving Skills

[![skills.sh](https://skills.sh/b/mojabarati/codex-repository-intelligence)](https://skills.sh/mojabarati/codex-repository-intelligence)

Turn recurring project context into persistent, version-controlled repository intelligence for Codex and other Agent Skills-compatible coding agents.

Instead of repeatedly re-explaining architecture, conventions, security constraints, testing expectations, and production risks in every AI-assisted development session, this project provides an installable Agent Skill that teaches an agent how to inspect the **actual repository** and establish a repository-specific context system using:

- `AGENTS.md` for concise repository-wide guidance and rules
- `.agents/skills/<skill-name>/SKILL.md` for project-specific engineering playbooks
- a **Skill Evolution** mechanism that updates, creates, consolidates, or removes Skills when future work reveals stable reusable repository knowledge

> The goal is not to accumulate generic AI instructions. The goal is to keep a small, evidence-based context layer synchronized with the codebase.

## Install as an Agent Skill

Install directly from GitHub with the Skills CLI:

```bash
npx skills add mojabarati/codex-repository-intelligence
```

If the CLI discovers multiple skills and you want to select this one explicitly:

```bash
npx skills add https://github.com/mojabarati/codex-repository-intelligence --skill codex-repository-intelligence
```

The installable skill lives at:

```text
skills/codex-repository-intelligence/SKILL.md
```

## What the Skill does

When used on an existing software repository, the Skill guides the agent to:

1. verify the repository root and scope;
2. inspect the actual architecture, stack, conventions, tests, data layer, security boundaries, and production-sensitive areas;
3. create or update a concise root `AGENTS.md`;
4. discover only the repository-local Skills that are genuinely justified by evidence;
5. make each generated Skill an actionable engineering playbook rather than generic documentation;
6. establish mandatory Skill selection for future substantial tasks;
7. establish a controlled Skill Evolution mechanism;
8. prevent Skill bloat and unsupported permanent rules;
9. protect major architectural, security, product, and data decisions from being silently established through Skill Evolution;
10. validate the generated guidance against the real repository before completion.

## Expected output in the target repository

A typical result looks like:

```text
AGENTS.md
.agents/
└── skills/
    ├── frontend-development/
    │   └── SKILL.md
    ├── backend-development/
    │   └── SKILL.md
    ├── testing/
    │   └── SKILL.md
    └── ...
```

The exact Skills are **not predefined**. They should be derived from the target repository.

## Skill Evolution

For substantial future tasks, the generated repository guidance instructs the agent to:

1. inspect available repository Skills;
2. select the Skills relevant to the task;
3. identify reusable project knowledge that is missing or outdated;
4. update an existing Skill when the knowledge belongs there;
5. create a new Skill only when a meaningful recurring domain is not adequately covered;
6. consolidate or remove obsolete guidance when needed;
7. make no Skill change for temporary, trivial, speculative, or one-off knowledge;
8. report Skill changes explicitly.

This creates a lifecycle like:

```text
Repository evolves
        ↓
Agent discovers verified reusable patterns
        ↓
Relevant Skills evolve
        ↓
Future tasks receive better project-specific context
```

## Security and production safety

Security is explicitly evaluated during setup. A dedicated Security Skill is created only when the repository's actual attack surface justifies one.

Production Safety is evaluated separately. Depending on the repository, this may cover areas such as:

- migrations and production data
- backwards compatibility
- authentication and authorization
- payments and billing
- webhooks and external integrations
- queues and background jobs
- infrastructure and deployment
- secrets and environment configuration
- irreversible or destructive operations

Security and Production Safety are kept separate when doing so improves clarity and future correctness.

## Setup safety boundary

The initial setup is intentionally analysis/guidance-only. It should **not** be used to:

- implement product features
- fix unrelated bugs
- refactor application code
- upgrade dependencies
- change application behavior
- modify database data
- run destructive migrations
- change production configuration or infrastructure
- rotate credentials
- expose secrets

Important findings can be reported, but they should not be silently fixed during the setup pass.

## Evidence over assumptions

Persistent repository guidance should be based on strong evidence such as:

1. explicit current project documentation or approved decisions;
2. enforced configuration or schema constraints;
3. executable tests and validation;
4. repeated consistent implementations;
5. a single implementation only when it is clearly intentional.

Weak or contradictory evidence should be marked uncertain rather than promoted into a permanent rule.

## Why this exists

In AI-assisted development, a seemingly simple task like:

> “Add this feature.”

may depend on hidden context such as:

- this API must remain backwards compatible;
- this component must reuse the design system;
- this endpoint requires a specific permission check;
- this migration affects production data;
- this flow requires particular tests;
- this webhook must preserve idempotency;
- this subsystem has established failure-handling patterns.

As a product grows, this context grows too.

This project treats that as a **Context Architecture** problem: part of the knowledge required to work safely on the codebase should live with the codebase itself.

## Repository structure

```text
codex-repository-intelligence/
├── README.md
├── PROMPT.md
└── skills/
    └── codex-repository-intelligence/
        └── SKILL.md
```

### `SKILL.md`

The installable Agent Skill. It contains the operational workflow, safety constraints, Skill Evolution logic, evidence rules, and validation requirements.

### `PROMPT.md`

The original long-form setup prompt. It is retained for transparency, human review, direct-session usage, and comparison with the packaged Skill.

## Direct prompt usage

You can still use the original workflow without installing the Skill:

1. open a new Codex session from the root of the existing project;
2. copy the full contents of [`PROMPT.md`](./PROMPT.md) into the session;
3. let the initial repository analysis/setup finish;
4. open a fresh session from the same repository root for normal development work.

## Design principles

- Repository evidence over assumptions
- Project-specific Skills over generic personas
- Small, high-value Skill set over Skill proliferation
- Security invariants may justify persistent guidance even when discovered once
- Skills document established decisions; they should not silently create governance decisions
- Persistent context should remain concise enough to be useful as agent context
- `AGENTS.md` and Skills should remain version-controlled and reviewable
- Skill changes should be transparent

## skills.sh

The repository is structured as an Agent Skill source and can be installed with the Skills CLI:

```bash
npx skills add mojabarati/codex-repository-intelligence
```

Once the Skill is installed through the CLI, skills.sh can discover and track it through its anonymous installation telemetry.

## Full long-form prompt

For the original detailed setup specification, see:

**[PROMPT.md](./PROMPT.md)**

## Notes

This is an opinionated workflow for AI-assisted software development. Generated guidance still requires normal engineering review. Repository instructions should evolve from verified project evidence, not assumptions, temporary implementation details, or accidental patterns.
