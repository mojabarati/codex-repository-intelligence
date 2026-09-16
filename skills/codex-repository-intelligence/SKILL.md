---
name: codex-repository-intelligence
description: Analyze an existing software repository and establish a persistent, repository-specific Codex context system using AGENTS.md and project-specific Agent Skills. Use when setting up Codex for an existing repository, creating repository intelligence, discovering project-specific engineering skills, documenting verified architecture and conventions, establishing security or production-safety guidance, or adding a self-evolving skill-maintenance mechanism.
---

# Codex Repository Intelligence

Set up a persistent, repository-specific guidance system for Codex based on evidence from the actual codebase.

The goal is to move recurring project context out of repeated chat prompts and into version-controlled repository guidance that stays synchronized with meaningful changes to the project.

## Intended output

The setup should primarily produce:

```text
<repository-root>/AGENTS.md
<repository-root>/.agents/skills/<skill-name>/SKILL.md
```

`AGENTS.md` owns concise repository-wide guidance. Repository-local Skills own specialized implementation workflows, subsystem knowledge, and domain-specific constraints.

## Core principles

1. Derive persistent guidance from repository evidence, not assumptions.
2. Inspect representative implementations before declaring a convention.
3. Prefer a small set of high-value, repository-specific Skills.
4. Do not turn implementation accidents into business rules.
5. Keep Security and Production Safety distinct when the repository justifies both.
6. Treat Skills as living, version-controlled engineering playbooks.
7. Do not let Skill Evolution silently establish major architecture or product decisions.
8. Keep guidance concise enough to remain useful as agent context.

## Setup boundary

This setup task is for repository analysis and guidance creation only.

During setup, you may inspect:

- source code and repository structure;
- package manifests and configuration;
- documentation;
- tests and test configuration;
- schemas and migrations;
- CI/CD and deployment-related files;
- representative implementations;
- git history when useful.

You may create or update only the repository guidance needed for this setup, primarily `AGENTS.md` and repository-local Skills.

Do not use the setup task to:

- implement product features;
- fix unrelated bugs;
- perform unrelated refactors;
- upgrade dependencies;
- change application behavior;
- modify production data;
- run destructive migrations;
- change production configuration or infrastructure;
- rotate credentials;
- expose secrets.

If you discover vulnerabilities, bugs, technical debt, missing tests, or architectural problems, report important findings separately rather than silently fixing them during setup.

## Workflow

### 1. Verify repository scope

Before changing anything:

1. determine the repository root;
2. inspect the top-level structure;
3. verify that this is the intended repository;
4. use the repository root as the only base location for generated guidance.

If the repository root cannot be determined confidently, stop before modifying files and report the ambiguity.

### 2. Analyze the actual repository

Inspect enough of the repository to understand how it currently works.

Where applicable, determine:

- applications, packages, services, modules, shared libraries, entry points, and configuration locations;
- languages, frameworks, runtime, package manager, frontend/backend stack, database, ORM/query layer, API technology, authentication/authorization, state management, styling, UI libraries, build tools, test frameworks, linting, formatting, and type checking;
- frontend routing, layouts, reusable components, forms, validation, loading/empty/error states, responsive behavior, accessibility, and design-system patterns;
- backend routes, handlers/controllers, services, domain logic, repositories/data access, validation, errors, logging, transactions, caching, queues/jobs, integrations, and tests;
- database entities, relationships, constraints, uniqueness rules, transaction boundaries, audit/history, soft delete, and idempotency patterns;
- test commands, build validation, lint/format/type-check commands, and CI checks;
- production-sensitive areas such as migrations, deployment, auth, payments, external APIs, webhooks, queues, jobs, file storage, infrastructure, production databases, destructive scripts, observability, and secrets.

Do not infer a repository-wide convention from one isolated implementation when stronger evidence is available.

### 3. Evaluate security explicitly

Inspect the repository's actual security attack surface where relevant, including:

- authentication and session/token handling;
- authorization, roles, permissions, and privilege boundaries;
- input validation and API security;
- XSS, CSRF, CORS, SSRF, and injection risks where applicable;
- file upload validation, malware scanning, and path traversal;
- secrets and environment-variable handling;
- webhook verification and external integrations;
- sensitive logging and data exposure;
- admin/back-office boundaries;
- tenant isolation and trust boundaries;
- rate limiting and brute-force protection.

Create a dedicated Security Skill only when the repository's attack surface and recurring work justify one.

Stable, high-impact security invariants may justify persistent guidance even if discovered only once. Encode the verified invariant, not a temporary vulnerability.

### 4. Create or update root AGENTS.md

Keep `AGENTS.md` concise and actionable rather than turning it into general documentation.

Include only verified, repository-relevant information such as:

- high-level architecture and major modules/services;
- important directories;
- technology stack;
- verified install/dev/build/test/lint/format/type-check commands;
- repository-wide conventions;
- production-safety principles;
- security principles that apply globally;
- mandatory Skill selection behavior;
- mandatory Skill Evolution behavior.

For substantial future tasks, `AGENTS.md` should instruct Codex to:

1. understand the requested change;
2. inspect available repository Skills;
3. select all meaningfully relevant Skills;
4. inspect relevant existing code and neighboring implementations;
5. identify reasonably impacted layers;
6. preserve established project patterns;
7. implement the smallest sufficient change;
8. avoid unrelated refactors;
9. run appropriate validation;
10. report meaningful risks, uncertainties, and Skill changes.

### 5. Discover the initial Skills

Actively evaluate which repository-local Skills are genuinely useful now.

Possible categories include frontend development, UI/design, backend development, architecture, testing, security, and production safety, but these are examples rather than mandatory output.

Create a Skill only when most of the following are true:

- it represents a meaningful category of work;
- the knowledge is repository-specific;
- similar work is likely to recur;
- the domain has meaningful conventions, workflows, or risks;
- existing Skills do not already cover it adequately;
- dedicated guidance would materially improve correctness, consistency, safety, or speed.

Do not create Skills for one-off fixes, trivial UI changes, temporary implementation details, speculative architecture, generic programming knowledge, or information already covered elsewhere.

### 6. Make every Skill operational

Every generated repository Skill must have valid frontmatter with at least:

```yaml
---
name: skill-name
description: Precise repository-specific trigger description.
---
```

A useful Skill should tell future agents:

- when to use it;
- which repository areas matter;
- which established patterns to follow;
- which abstractions to reuse;
- which constraints and safety checks apply;
- which validations/tests to run;
- which repository-specific mistakes to avoid;
- what Definition of Done applies to that category of work.

Prefer paths, concise rules, verified commands, and concrete conventions over large copied source blocks.

### 7. Add Skill Evolution

Add a dedicated `Skill Evolution` section to `AGENTS.md`.

For every substantial future task, Codex must evaluate whether the current Skills still represent relevant project knowledge.

Use this decision process:

1. inspect available repository Skills;
2. identify the Skills relevant to the task;
3. determine whether the task reveals stable, reusable, repository-specific knowledge that is missing or outdated;
4. update an existing Skill when the knowledge naturally belongs there;
5. create a new Skill when a meaningful recurring domain is not adequately covered;
6. update, consolidate, or remove obsolete guidance when architecture or conventions have changed;
7. make no Skill change when the knowledge is task-local, temporary, trivial, speculative, or unlikely to be reused;
8. continue the requested implementation using the relevant current guidance.

Prefer evolving existing Skills over creating overlapping ones.

### 8. Prevent Skill bloat

Before creating a new Skill, evaluate:

1. Will this knowledge likely be reused?
2. Is it repository-specific?
3. Is it stable enough to document?
4. Is it meaningfully different from existing Skills?
5. Would updating an existing Skill be better?
6. Would the new Skill materially improve future correctness, safety, consistency, or speed?

If the answer is mostly no, do not create a new Skill.

### 9. Protect architectural governance

Skill Evolution does not authorize Codex to silently establish major new architectural, product, security, or data-model decisions.

Examples that require task-level treatment before becoming persistent guidance include:

- introducing or replacing a core framework;
- adding a major architectural layer or infrastructure dependency;
- changing an important domain boundary;
- changing a public API contract;
- changing a security boundary;
- changing a critical data model;
- changing an established business rule.

Skills document established decisions. They do not create governance decisions by themselves.

### 10. Handle conflicting evidence carefully

When repository sources disagree, do not silently choose one and encode it as a permanent rule.

Evaluate conflicts using repository context and evidence. Strong sources may include:

- explicit current requirements;
- enforced security/data constraints;
- executable tests and validation;
- current production-relevant implementation;
- current project documentation;
- historical documentation.

If a meaningful contradiction cannot be resolved confidently, report it and avoid promoting either side into persistent guidance.

### 11. Validate the generated guidance

Before finishing:

- re-read every generated guidance file;
- compare it with the actual repository;
- remove unsupported assumptions, generic filler, redundant rules, duplicate content, conflicting instructions, speculative architecture, nonexistent commands, and unnecessary Skills;
- verify `AGENTS.md` is at repository root;
- verify all repository Skills are under `.agents/skills/`;
- verify frontmatter and trigger descriptions;
- verify Security and Production Safety were explicitly evaluated;
- verify Skill selection and Skill Evolution behavior exist;
- verify Skill changes remain focused and reviewable.

## Evidence threshold

Do not promote a pattern into persistent guidance merely because it appears once.

Prefer evidence from:

1. explicit current project documentation or approved architectural decisions;
2. enforced configuration or schema constraints;
3. tests that verify behavior;
4. repeated consistent implementations;
5. a single representative implementation only when clearly intentional.

If evidence is weak, inconsistent, or ambiguous, mark the point as uncertain or omit it rather than presenting it as an established rule.

## Business-rule safety

Do not convert implementation accidents into permanent business rules.

Treat a business rule as established only when supported by strong evidence such as explicit documentation, domain validation, application/domain logic, tests, schema constraints combined with application behavior, or repeated consistent implementations.

## Production safety

For future production-sensitive changes, guidance should emphasize, where applicable:

- backward compatibility;
- downstream consumers and call sites;
- safe migrations and production-data preservation;
- reversible changes;
- authentication/authorization sensitivity;
- payments/billing risk;
- webhook and integration reliability;
- duplicate/retry/idempotency behavior;
- deployment and infrastructure risk;
- appropriate validation before release.

Create a dedicated Production Safety Skill when operational risk is substantial enough to justify specialized recurring guidance.

## Skill change transparency

Whenever a future task creates, updates, consolidates, or removes a repository Skill, the final task report must state:

- which Skill changed;
- why it changed;
- what reusable repository knowledge was added or removed;
- what repository evidence justified the change.

Do not silently modify persistent repository guidance.

## Final report for initial setup

After setup, provide a concise report covering:

- detected repository root;
- detected stack and high-level architecture;
- every guidance/Skill file created or modified;
- initial Skills, their triggers, and why they were created;
- Security Skill decision and verified security-sensitive areas;
- Production Safety Skill decision and production-sensitive areas;
- how Skill Evolution will work;
- meaningful Skills considered but intentionally omitted;
- unresolved uncertainties;
- important findings discovered during analysis;
- explicit confirmation of whether application code changed.

For the initial setup, expected application change status is:

```text
Application code modified: NO
```

## Reference

The repository also contains the original long-form setup prompt for human review and direct-session usage. When working from the source repository, see the root `PROMPT.md` for the extended specification.
