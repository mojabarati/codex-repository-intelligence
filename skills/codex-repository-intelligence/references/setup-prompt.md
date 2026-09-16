# Codex Repository Intelligence, Security & Self-Evolving Skills Setup

You are setting up a persistent, repository-specific instruction and skills system for this EXISTING software project.

Parts of this project may already be running in production.

Your objective is NOT to implement a product feature.

Your objective is to:

1. understand the actual repository,
2. create a repository-specific `AGENTS.md`,
3. discover and create the Skills this repository currently needs,
4. establish production and security safeguards,
5. establish a self-maintaining Skill Evolution mechanism so future Codex tasks can improve the repository Skills when justified.

The final guidance system should primarily consist of:

- `<repository-root>/AGENTS.md`
- `<repository-root>/.agents/skills/<skill-name>/SKILL.md`

Everything must be derived from the ACTUAL repository.

Do not invent architecture, conventions, commands, technologies, security controls, business rules, or implementation patterns that cannot be verified from repository evidence.

======================================================================
1. REPOSITORY SAFETY CHECK
======================================================================

Before making ANY changes:

1. Identify the repository associated with this Codex project.
2. Identify the repository root.
3. Inspect the top-level repository structure.
4. Verify that you are operating inside the intended repository.
5. Use the repository root as the only base location for the files created by this task.

Create:

`AGENTS.md`

at the repository root.

Create repository-local Skills only under:

`.agents/skills/<skill-name>/SKILL.md`

Do NOT create or modify:

- global Codex instructions,
- user-level Codex configuration,
- Skills outside this repository,
- AGENTS.md files outside this repository,
- unrelated repositories.

If the repository root cannot be determined confidently:

STOP before modifying files and report the problem.

======================================================================
2. SETUP TASK BOUNDARY
======================================================================

This task is ONLY for repository analysis and Codex guidance setup.

During this task you MAY:

- inspect repository files,
- inspect source code,
- inspect configuration,
- inspect package manifests,
- inspect documentation,
- inspect tests,
- inspect migrations,
- inspect CI/CD configuration,
- inspect deployment-related files,
- inspect representative implementations,
- inspect git history when useful,
- create/update repository-root `AGENTS.md`,
- create/update repository-local Skills.

During this setup task, DO NOT:

- implement product features,
- fix unrelated bugs,
- refactor application code,
- upgrade dependencies,
- modify application behavior,
- modify database data,
- run destructive migrations,
- change production configuration,
- change infrastructure,
- change deployment behavior,
- rotate or modify credentials,
- expose secrets.

If you discover bugs, vulnerabilities, technical debt, missing tests, or architectural problems:

DO NOT fix them during this setup task.

Report important findings separately at the end.

======================================================================
3. ANALYZE THE REPOSITORY BEFORE CREATING GUIDANCE
======================================================================

Before writing `AGENTS.md` or any Skill, inspect the repository thoroughly enough to understand how it actually works.

Determine, where applicable:

PROJECT STRUCTURE

- repository layout
- applications
- packages
- services
- modules
- shared libraries
- important directories
- entry points
- configuration locations

TECHNOLOGY STACK

Identify the actual:

- programming languages
- frameworks
- runtime
- package manager
- frontend stack
- backend stack
- database
- ORM/query layer
- API technology
- authentication technology
- authorization approach
- state management
- styling system
- UI/component libraries
- build tools
- test frameworks
- linting tools
- formatting tools
- type-checking tools

Do not assume technologies when stronger repository evidence exists.

======================================================================
4. FRONTEND ANALYSIS
======================================================================

If a frontend exists, inspect representative implementations and determine:

- frontend framework
- application structure
- routing
- layouts
- server/client boundaries where relevant
- component organization
- reusable components
- UI primitives
- state management
- data fetching
- forms
- validation
- loading states
- empty states
- error states
- styling
- design system
- responsive behavior
- accessibility patterns
- naming conventions
- frontend testing

Do not infer frontend conventions from one isolated component.

Look for recurring patterns.

======================================================================
5. UI / DESIGN SYSTEM ANALYSIS
======================================================================

If the repository contains meaningful UI, inspect:

- design-system primitives
- component libraries
- typography
- spacing
- layout conventions
- colors/tokens
- reusable patterns
- navigation
- dialogs/modals
- forms
- tables
- feedback states
- loading states
- empty states
- error states
- responsive behavior
- accessibility patterns

Determine whether UI/design work is substantial enough to justify a dedicated repository Skill.

======================================================================
6. BACKEND ANALYSIS
======================================================================

If a backend exists, inspect representative implementations and determine:

- routes
- controllers
- handlers
- services
- domain logic
- repositories/data access
- request validation
- API response conventions
- authentication
- authorization
- error handling
- logging
- database access
- transaction handling
- caching
- asynchronous processing
- queues
- background jobs
- external integrations
- backend testing

Inspect neighboring implementations before documenting a backend pattern.

======================================================================
7. DATA & DATABASE ANALYSIS
======================================================================

If a database exists, inspect:

- schema
- migrations
- important entities
- relationships
- constraints
- uniqueness rules
- transaction boundaries
- data-integrity patterns
- audit/history mechanisms
- soft-delete behavior
- idempotency patterns where applicable

Do NOT infer permanent business rules solely from database column names.

======================================================================
8. TESTING & QUALITY ANALYSIS
======================================================================

Determine the actual:

- unit-test framework
- integration-test framework
- E2E setup
- test commands
- lint commands
- formatting commands
- type-check commands
- build validation
- CI checks

Only document commands that actually exist or are clearly supported by the repository.

Do not claim tests exist when they do not.

======================================================================
9. PRODUCTION & OPERATIONAL ANALYSIS
======================================================================

Identify production-sensitive areas, where applicable:

- deployment
- database migrations
- environment configuration
- authentication
- authorization
- payments
- billing
- external APIs
- webhooks
- queues
- background jobs
- scheduled jobs
- file storage
- infrastructure
- production databases
- destructive scripts
- observability
- secrets

Do not modify these areas during this setup task.

======================================================================
10. SECURITY ANALYSIS
======================================================================

Explicitly evaluate the repository's actual security attack surface.

Inspect, where applicable:

- authentication
- authorization
- roles
- permissions
- privilege boundaries
- session management
- JWT/token handling
- OAuth
- password handling
- secrets
- environment variables
- API security
- input validation
- injection risks
- XSS
- CSRF
- CORS
- SSRF
- file uploads
- file validation
- malware scanning
- path traversal
- rate limiting
- brute-force protection
- sensitive-data exposure
- sensitive logging
- database access
- external integrations
- webhook verification
- dependency/security configuration
- admin/back-office functionality
- privilege escalation
- tenant isolation
- trust boundaries

Do not assume all these mechanisms exist.

Only document security concerns and patterns that are relevant to the actual repository.

Do NOT weaken existing security controls.

Do NOT expose secrets while analyzing or documenting the project.

======================================================================
11. EVIDENCE-BASED GUIDANCE
======================================================================

All persistent instructions must be based on repository evidence.

Before documenting an important convention, inspect representative existing implementations.

Where useful, reference actual repository paths.

Prefer:

- paths
- concise explanations
- commands
- established patterns
- constraints

over copied source code.

Do not copy large source-code blocks into Skills.

If the repository is inconsistent:

document the inconsistency rather than inventing a standard.

If something cannot be determined confidently:

mark it as uncertain or omit it.

======================================================================
12. CREATE ROOT AGENTS.md
======================================================================

Create or update:

`<repository-root>/AGENTS.md`

This file contains persistent repository-wide context and rules for future Codex tasks.

Keep it concise and actionable.

Do NOT turn it into general project documentation.

At minimum, evaluate whether it should contain:

PROJECT CONTEXT

- high-level architecture
- major applications/services
- important directories
- technology stack

DEVELOPMENT

- package manager
- install command
- development command
- build command
- test commands
- lint command
- formatting command
- type-check command

Only include verified commands.

REPOSITORY CONVENTIONS

- file organization
- naming
- module boundaries
- frontend conventions
- backend conventions
- API conventions
- database conventions
- testing conventions

CHANGE PRINCIPLES

Future Codex tasks should generally:

1. understand the requested change,
2. inspect relevant existing implementations,
3. inspect available repository Skills,
4. identify relevant Skills,
5. identify impacted layers,
6. preserve established project patterns,
7. implement the smallest sufficient change,
8. avoid unrelated refactors,
9. run appropriate validation,
10. report meaningful risks or unresolved issues.

======================================================================
13. PRODUCTION SAFETY RULES
======================================================================

Add repository-appropriate production-safety rules to `AGENTS.md`.

Future Codex tasks should generally:

- preserve existing behavior unless explicitly changing it,
- preserve backwards compatibility where practical,
- inspect consumers/call sites before changing public interfaces,
- avoid unrelated refactoring,
- prefer small and reversible changes,
- inspect existing migrations before schema changes,
- never assume production data can safely be deleted,
- avoid destructive database operations unless explicitly requested,
- never expose secrets,
- never hardcode credentials,
- treat authentication and authorization changes as security-sensitive,
- treat payments/billing as high-risk if they exist,
- treat database migrations as high-risk,
- treat infrastructure/deployment changes as high-risk,
- treat external integrations and webhooks carefully,
- consider duplicate/retry/idempotency behavior when applicable,
- validate production-sensitive changes appropriately.

Do not add rules for technologies or domains that do not exist.

======================================================================
14. DISCOVER THE INITIAL SKILLS THIS REPOSITORY NEEDS
======================================================================

After repository analysis, determine which repository-local Skills are genuinely useful NOW.

Create them under:

`.agents/skills/<skill-name>/SKILL.md`

You MUST actively evaluate the repository and create the Skills that are justified by the current codebase.

Do NOT limit yourself to a predefined list.

Potential candidates include:

- `frontend-development`
- `ui-design`
- `backend-development`
- `architecture`
- `testing`
- `security`
- `production-safety`

These are candidates, NOT mandatory output.

You may:

- create them,
- rename them,
- combine them,
- split them,
- omit unnecessary ones,
- add better repository-specific Skills.

The objective is:

A SMALL SET OF HIGH-VALUE, PROJECT-SPECIFIC SKILLS.

Do not create generic Skills merely to satisfy this prompt.

======================================================================
15. SKILL STRUCTURE
======================================================================

Every Skill must have valid `SKILL.md` frontmatter.

At minimum:

---
name: skill-name
description: Precise description of when this Skill should be used.
---

The `description` is critical.

It must make implicit Skill selection reliable.

Describe:

- what task types trigger the Skill,
- which repository areas it applies to,
- important situations where it should be used.

Avoid vague descriptions such as:

"Use for backend work."

Prefer precise repository-specific trigger descriptions.

======================================================================
16. SKILLS MUST BE PROJECT-SPECIFIC
======================================================================

Do NOT create generic persona Skills such as:

"You are a senior frontend developer."

A useful repository Skill should answer:

- How does THIS repository perform this kind of work?
- Which existing patterns should be followed?
- Which directories are relevant?
- Which abstractions should be reused?
- Which constraints matter?
- Which validation should run?
- Which common mistakes should be avoided?

Skills should contain verified repository knowledge, not generic software-development tutorials.

======================================================================
17. FRONTEND DEVELOPMENT SKILL
======================================================================

If justified, create a frontend Skill covering actual repository conventions around:

- components
- routing
- layouts
- state management
- data fetching
- forms
- validation
- styling
- responsive behavior
- accessibility
- loading/error/empty states
- reusable abstractions
- testing
- validation commands

Reference representative repository paths where useful.

======================================================================
18. UI DESIGN SKILL
======================================================================

If justified, create a UI/design Skill covering:

- design system
- shared UI primitives
- component reuse
- typography
- spacing
- layout
- responsive conventions
- interaction patterns
- forms
- dialogs/modals
- navigation
- loading states
- empty states
- error states
- accessibility

Future Codex tasks should reuse existing design-system primitives when possible.

Avoid arbitrary:

- colors,
- spacing systems,
- components,
- visual patterns,
- interaction patterns

when established equivalents exist.

======================================================================
19. BACKEND DEVELOPMENT SKILL
======================================================================

If justified, create a backend Skill covering actual repository patterns around:

- routes
- controllers
- handlers
- services
- domain logic
- repositories
- validation
- authentication
- authorization
- errors
- logging
- transactions
- queues
- jobs
- caching
- integrations
- API responses
- tests

Reference representative implementations.

======================================================================
20. ARCHITECTURE SKILL
======================================================================

If justified, create an architecture Skill covering:

- major modules
- domain boundaries
- dependency direction
- shared abstractions
- extension points
- where new functionality belongs
- ownership of business logic
- architectural constraints
- patterns to reuse
- patterns to avoid

The Skill should help future Codex tasks decide:

- where functionality belongs,
- which layer owns logic,
- whether an existing module should be extended,
- whether a new abstraction is justified.

Prefer the simplest architecture consistent with the repository.

Avoid overengineering.

======================================================================
21. TESTING SKILL
======================================================================

If justified, create a testing Skill documenting actual tools and validation expectations for:

- frontend changes
- backend changes
- API changes
- database changes
- bug fixes
- refactors
- authentication/authorization changes
- production-sensitive changes

Use actual repository commands.

======================================================================
22. SECURITY SKILL EVALUATION
======================================================================

Explicitly determine whether the repository's attack surface is substantial enough to justify a dedicated Security Skill.

If YES, create:

`.agents/skills/security/SKILL.md`

The Security Skill must be repository-specific.

Where applicable, it should describe:

- security-sensitive areas
- authentication patterns
- authorization patterns
- roles and permissions
- privilege boundaries
- trust boundaries
- tenant isolation
- sensitive operations
- input-validation expectations
- secrets-handling rules
- API security patterns
- file-upload security
- webhook verification
- sensitive logging restrictions
- reusable security middleware/utilities
- security validation expected after relevant changes
- security anti-patterns that must not be introduced

Do NOT introduce security changes during this setup task.

If a potential vulnerability is discovered:

DO NOT silently fix it.

Report it separately with:

- affected area
- severity estimate
- repository evidence
- potential impact
- recommended remediation

without exposing secrets or sensitive production information.

======================================================================
23. PRODUCTION SAFETY SKILL
======================================================================

If production risk is substantial enough, create:

`.agents/skills/production-safety/SKILL.md`

Make it repository-specific.

Potential areas include:

- migrations
- destructive operations
- backwards compatibility
- public APIs
- authentication
- authorization
- payments
- webhooks
- external integrations
- queues
- background jobs
- environment configuration
- secrets
- infrastructure
- deployment
- data migration
- irreversible operations

Only include relevant areas.

======================================================================
24. SECURITY VS PRODUCTION SAFETY
======================================================================

Do not automatically merge Security and Production Safety.

They address different concerns.

SECURITY focuses primarily on:

- preventing unauthorized behavior,
- protecting data,
- preserving trust boundaries,
- authentication,
- authorization,
- validation,
- attack surfaces,
- security invariants.

PRODUCTION SAFETY focuses primarily on:

- preventing outages,
- preventing data loss,
- safe migrations,
- backwards compatibility,
- deployment safety,
- operational reliability,
- reversible changes.

If the repository justifies both concerns independently, create both Skills.

If the repository is simple enough that separation provides little value, combining them is acceptable, but explain the decision in the final report.

======================================================================
25. MANDATORY SKILL SELECTION FOR FUTURE TASKS
======================================================================

Add this behavior to `AGENTS.md`.

For every substantial future task, Codex MUST:

1. understand the request,
2. inspect the available repository Skills,
3. identify all meaningfully relevant Skills,
4. use those Skills,
5. inspect relevant code,
6. determine impacted layers,
7. implement the requested change,
8. run appropriate validation.

A task may use multiple Skills.

Examples:

frontend + ui-design + testing

backend + security + testing

backend + production-safety

architecture + backend + testing

frontend + backend + security + testing

Do NOT require unrelated Skills to be fully loaded for every task.

Use relevant Skills only.

======================================================================
26. MANDATORY SKILL EVOLUTION
======================================================================

Add a dedicated section named:

`Skill Evolution`

to `AGENTS.md`.

The repository Skills system is a living part of this codebase and MUST evolve when meaningful reusable project knowledge is discovered.

For every substantial future task, Codex MUST evaluate whether the repository Skills still adequately represent the relevant project knowledge.

The required decision process is:

1. Inspect available repository Skills.
2. Determine which Skills are relevant.
3. Determine whether the task reveals reusable project-specific knowledge that is missing or outdated.
4. If an existing Skill covers the responsibility but lacks important reusable knowledge:
   UPDATE that Skill.
5. If no existing Skill adequately covers a meaningful recurring domain/workflow:
   CREATE a new Skill.
6. If existing Skill guidance became incorrect because the architecture changed:
   UPDATE, consolidate, or remove obsolete guidance.
7. If the knowledge is task-local, temporary, trivial, speculative, or unlikely to be reused:
   DO NOT modify the Skills system.
8. Continue with the requested implementation using the relevant Skills.

Codex should NOT wait for the user to explicitly request:

"create a skill"

or

"update the skills."

Skill maintenance should happen proactively when justified.

======================================================================
27. WHEN A NEW SKILL MUST BE CREATED
======================================================================

Create a new repository Skill when ALL or most of the following are true:

- the task introduces or reveals a meaningful category of work,
- the knowledge is repository-specific,
- similar work is likely to happen again,
- the domain has meaningful conventions/workflows/risks,
- existing Skills do not adequately represent it,
- dedicated guidance would materially improve future correctness, consistency, safety, or development speed.

Potential future domains MAY include:

- payments
- subscriptions
- Stripe
- webhooks
- analytics
- search
- notifications
- permissions
- file uploads
- background jobs
- queues
- integrations
- observability
- infrastructure
- internationalization

These are examples only.

Do NOT pre-create them unless the repository currently justifies them.

======================================================================
28. WHEN AN EXISTING SKILL MUST BE UPDATED
======================================================================

If reusable knowledge naturally belongs to an existing Skill, UPDATE that Skill instead of creating another Skill.

Examples:

new frontend convention
→ update frontend Skill

new UI convention
→ update UI Skill

new API/service pattern
→ update backend Skill

new architectural boundary
→ update architecture Skill

new testing strategy
→ update testing Skill

new production migration rule
→ update production-safety Skill

new security invariant
→ update security Skill

Prefer evolving existing Skills over creating overlapping Skills.

======================================================================
29. SECURITY EXCEPTION TO NORMAL SKILL EVOLUTION
======================================================================

Security knowledge does NOT need to be frequently recurring to justify persistent repository guidance.

If a task reveals a stable and important:

- security boundary,
- authorization invariant,
- authentication invariant,
- permission rule,
- privilege boundary,
- tenant-isolation requirement,
- trust boundary,
- webhook-verification requirement,
- sensitive-data handling rule,
- file-validation requirement,
- secrets-handling requirement,
- other high-impact security invariant

that future changes MUST preserve:

Codex SHOULD update the appropriate Security or Production Safety Skill even if the specific issue was discovered only once.

Do NOT encode a temporary vulnerability as a permanent rule.

Encode the VERIFIED UNDERLYING SECURITY INVARIANT that future implementations must preserve.

Example:

Do NOT encode:

"Endpoint X currently has an authorization bug."

Instead encode the verified invariant:

"All administrative endpoints under the verified admin boundary must enforce the project's established admin authorization mechanism."

======================================================================
30. PREVENT SKILL BLOAT
======================================================================

The objective is NOT to maximize the number of Skills.

Maintain a small, high-quality Skill system.

Do NOT create Skills for:

- one-off fixes,
- trivial UI changes,
- temporary implementation details,
- task-specific decisions,
- experimental code that may disappear,
- speculative architecture,
- generic programming knowledge,
- information already adequately covered by another Skill.

Before creating a Skill, evaluate:

1. Will this knowledge likely be reused?
2. Is it repository-specific?
3. Is it stable enough to document?
4. Is it meaningfully different from existing Skills?
5. Would updating an existing Skill be better?
6. Would the Skill materially improve future correctness, safety, consistency, or speed?

If the answer is mostly NO:

do not create the Skill.

======================================================================
31. CONTINUOUS REPOSITORY LEARNING
======================================================================

During future implementation work, distinguish between:

TASK-LOCAL KNOWLEDGE

and

REUSABLE PROJECT KNOWLEDGE.

Task-local knowledge should remain within the task.

Reusable repository-specific knowledge should be incorporated into the appropriate Skill when it materially improves future work.

The intended lifecycle is:

Repository evolves
→ Codex discovers verified reusable patterns
→ relevant Skills evolve
→ future Codex tasks receive better project-specific guidance.

Skills must describe the CURRENT repository.

Do not document imagined future architecture.

If implementation changes a convention already documented in a Skill:

update that Skill as part of the same task.

If a subsystem becomes important enough to deserve a dedicated Skill:

create it as part of that task.

If a Skill becomes obsolete:

update, consolidate, or remove it as appropriate.

======================================================================
32. BUSINESS RULE SAFETY
======================================================================

Do not convert implementation accidents into permanent business rules.

Only document business rules when supported by strong evidence such as:

- explicit documentation,
- domain validation,
- application/domain logic,
- tests,
- schema constraints combined with application behavior,
- repeated consistent implementations.

If uncertain:

mark the rule as uncertain rather than encoding it as permanent guidance.

======================================================================
33. DATABASE & DATA-INTEGRITY GUIDANCE
======================================================================

If the repository uses a database, evaluate whether relevant Skills should capture:

- migration conventions
- transaction usage
- uniqueness constraints
- relationships
- data-integrity expectations
- idempotency
- audit/history mechanisms
- soft deletion

Do not introduce new database conventions during this setup task.

======================================================================
34. EXTERNAL INTEGRATION GUIDANCE
======================================================================

If external integrations exist, inspect existing patterns for:

- API failures
- timeouts
- retries
- duplicate events
- idempotency
- webhook verification
- rate limits
- partial failures
- reconciliation

Only document relevant patterns.

======================================================================
35. KEEP AGENTS.md AND SKILLS SEPARATE
======================================================================

Avoid unnecessary duplication.

Use `AGENTS.md` primarily for:

- repository-wide context
- universal rules
- development expectations
- production-safety principles
- security principles that apply globally
- Skill-selection behavior
- Skill-evolution behavior

Use Skills primarily for:

- specialized workflows
- subsystem-specific knowledge
- implementation conventions
- domain-specific rules
- detailed engineering guidance

If guidance applies only to one category of work, it probably belongs in a Skill.

======================================================================
36. KEEP CONTEXT EFFICIENT
======================================================================

All generated guidance should remain efficient as agent context.

Avoid huge instruction files.

Prefer:

- concise rules
- precise triggers
- actual repository paths
- verified commands
- concrete conventions

over long theoretical explanations.

Do not duplicate repository documentation unnecessarily.

======================================================================
37. FINAL VALIDATION
======================================================================

After creating `AGENTS.md` and the initial Skills:

Re-read every generated guidance file.

Compare it against the actual repository.

Remove:

- invented information,
- unsupported assumptions,
- generic filler,
- redundant rules,
- duplicate Skill content,
- conflicting instructions,
- unnecessary Skills,
- speculative architecture,
- nonexistent commands,
- nonexistent technologies.

Verify:

- `AGENTS.md` exists at repository root,
- all Skills exist under `.agents/skills/`,
- Skill frontmatter is valid,
- Skill descriptions have precise triggers,
- Skills are repository-specific,
- production rules reflect actual repository risks,
- Security was explicitly evaluated,
- Security Skill was created if justified,
- Production Safety was explicitly evaluated,
- Skill Selection behavior exists,
- Mandatory Skill Evolution exists,
- Security Exception exists,
- Skill-bloat prevention exists.

======================================================================
38. FINAL REPORT
======================================================================

After completing the setup, provide a concise report containing:

REPOSITORY

- detected repository root
- detected stack
- high-level architecture

FILES

List every instruction/Skill file created or modified.

INITIAL SKILLS

For each Skill provide:

- name
- purpose
- trigger
- important repository areas it covers
- why it was created

SECURITY

Report:

- whether a dedicated Security Skill was created
- why or why not
- important verified security-sensitive areas
- any potential security findings discovered during inspection

Do not expose secrets.

PRODUCTION SAFETY

Report:

- whether a dedicated Production Safety Skill was created
- why or why not
- important production-sensitive areas

SKILL EVOLUTION

Explain how future Codex tasks will decide whether to:

- use an existing Skill,
- update an existing Skill,
- create a new Skill,
- remove/consolidate obsolete guidance,
- make no Skill change.

INTENTIONALLY OMITTED SKILLS

Mention meaningful Skills considered but not created and why.

UNCERTAINTIES

List important things that could not be confidently determined.

APPLICATION CHANGES

Explicitly confirm whether application code was modified.

Expected result:

Application code modified: NO

======================================================================
39. SUCCESS CRITERIA
======================================================================

This setup is successful only if:

1. Codex understands the repository from actual evidence.
2. `AGENTS.md` contains concise repository-wide guidance.
3. The repository has the initial Skills it genuinely needs.
4. Skills contain repository-specific knowledge rather than generic personas.
5. Future substantial tasks are instructed to inspect and use relevant Skills.
6. Future substantial tasks evaluate whether Skills need to evolve.
7. Existing Skills are updated when appropriate.
8. New Skills are created when genuinely justified.
9. Skill bloat is prevented.
10. Security is explicitly evaluated.
11. Stable security invariants can update persistent guidance even when discovered once.
12. Production-sensitive changes are treated conservatively.
13. Skills remain synchronized with meaningful future architectural/convention changes.
14. No application code is modified during this setup task.
15. Persistent guidance is based on sufficient repository evidence.
16. Conflicting repository evidence is not silently converted into rules.
17. Skills are actionable engineering playbooks, not generic documentation.
18. Major architectural decisions are not silently established through Skill Evolution.
19. Skill changes are explicitly reported to the user.
20. AGENTS.md and Skills remain focused, reviewable, and version-controlled.

======================================================================
40. EVIDENCE & CONFIDENCE THRESHOLD
======================================================================

Do not promote a discovered pattern into persistent repository guidance
merely because it appears once.

Before adding or changing persistent guidance, evaluate the strength of
the evidence.

Prefer evidence from:

1. explicit project documentation or architectural decisions,
2. enforced configuration or schema constraints,
3. tests that verify the behavior,
4. repeated consistent implementations,
5. a single representative implementation only when clearly intentional.

If evidence is weak, inconsistent, or ambiguous:

- do not present the pattern as an established repository rule,
- mark it as uncertain when useful,
- and do not create a dedicated Skill solely from that evidence.

Persistent guidance should represent stable repository knowledge,
not accidental implementation details.

======================================================================
41. SOURCE OF TRUTH & CONFLICT RESOLUTION
======================================================================

When repository sources disagree, do not silently choose one.

Evaluate the conflict using this general priority:

- explicit current user requirement for the task,
- enforced security/data constraints,
- executable tests and validation,
- current production-relevant implementation,
- current project documentation,
- historical or stale documentation.

This is not an absolute hierarchy.

Use repository context and evidence.

If a meaningful contradiction cannot be resolved confidently,
report it rather than encoding one side as a permanent Skill rule.

======================================================================
42. CHANGE IMPACT ANALYSIS FOR FUTURE TASKS
======================================================================

For substantial future changes, before implementation identify the
reasonably affected areas.

Evaluate where applicable:

- frontend
- backend
- APIs
- database/schema
- authentication
- authorization
- security
- integrations
- webhooks/events
- background jobs
- configuration
- tests
- deployment
- backwards compatibility
- production data

Do not perform exhaustive analysis for trivial changes.

The depth of impact analysis should be proportional to the risk and
scope of the task.

For production-sensitive changes, explicitly inspect downstream
consumers and failure scenarios before modifying behavior.

======================================================================
43. SKILL ACTIONABILITY
======================================================================

Every Skill should be operational rather than descriptive.

Where applicable, a Skill should contain concise guidance for:

- when to use the Skill,
- relevant repository areas,
- established implementation patterns,
- required safety checks,
- validation/tests to run,
- common repository-specific mistakes to avoid,
- Definition of Done for that category of work.

Do not turn Skills into architecture documentation.

A future Codex task should be able to use a Skill as an actionable
engineering playbook.

======================================================================
44. ARCHITECTURAL DECISION SAFETY
======================================================================

Skill Evolution must NOT give Codex authority to silently establish
major new architectural or product decisions.

Codex may document architecture that has already been established by
the repository or explicitly requested implementation.

However, if a task requires a significant new decision such as:

- introducing a new architectural layer,
- replacing a core framework,
- changing an important domain boundary,
- introducing a major infrastructure dependency,
- changing a public API contract,
- changing a security boundary,
- changing a critical data model,
- changing an established business rule,

do not encode the decision as permanent repository guidance merely
because Codex selected it during implementation.

First treat it as a task-level architectural decision.

If the decision is explicitly requested, clearly established by the
implementation, or approved through the normal project process, then
update the relevant Skill afterward.

Skills document established decisions.
They should not silently create governance decisions.

======================================================================
45. SKILL CHANGE TRANSPARENCY
======================================================================

Whenever a future task creates, updates, consolidates, or removes a
repository Skill, include that change in the task's final report.

Report:

- which Skill changed,
- why it changed,
- what reusable repository knowledge was added/removed,
- what repository evidence justified the change.

Do not silently change persistent repository guidance without
mentioning it in the task summary.

======================================================================
46. GIT & CHANGE HYGIENE
======================================================================

Treat `AGENTS.md` and `.agents/skills/**` as version-controlled
repository artifacts.

Do not modify them unnecessarily.

Skill changes should be reviewable alongside the code changes that
caused the repository knowledge to evolve.

Do not commit, push, merge, release, deploy, or modify remote branches
unless explicitly requested by the user.

Do not rewrite unrelated guidance during a task.

Keep Skill diffs focused on knowledge actually affected by the task.