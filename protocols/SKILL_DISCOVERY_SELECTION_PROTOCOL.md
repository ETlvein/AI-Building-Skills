# Skill Discovery & Selection Protocol

## 1. Protocol Identity

PROTOCOL_ID:

SKILL_DISCOVERY_SELECTION_PROTOCOL

VERSION:

1.0.0

STATUS:

FROZEN

GOVERNED_BY:

PROMPT_STANDARD_V1.0 / v1.0.0

OWNER_APPROVAL:

APPROVED

FREEZE_DATE:

2026-09-19

---

## 2. Purpose

This protocol defines the mandatory process used by the AI Control Plane before selecting Skills for an Agent Execution Block.

It ensures that Skill selection is based on:

- fresh online discovery
- local Skill inventory
- external-to-local comparison
- permanent Skill retention
- Skill isolation
- explicit compatibility evaluation
- zero unresolved conflict

---

## 3. Mandatory Invocation

This protocol MUST run before final Skill selection whenever an AI-generated execution prompt may benefit from one or more Skills.

The AI Control Plane MUST NOT skip online discovery merely because a relevant local Skill already exists.

The AI Control Plane MUST NOT generate the final Agent Execution Block until this protocol reaches PASS.

---

## 4. Selection Cycle

### PHASE 01 — Normalize Task

Identify:

- task objective
- technical domain
- environment
- tools
- project governance
- file mutation scope
- required outputs
- safety constraints

RESULT:

TASK_PROFILE_READY

---

### PHASE 02 — Online Skill Discovery

Search current external sources for Skills relevant to the task.

Discovery should prefer trustworthy and technically authoritative sources.

The search must consider:

- official Skill sources
- official documentation
- verified repositories
- maintainer repositories
- mature open-source sources
- other relevant public sources

RESULT:

ONLINE_DISCOVERY_COMPLETED

If online discovery cannot be performed:

RESULT:

BLOCK_AND_REPORT

---

### PHASE 03 — Local Registry Discovery

Search:

SKILL_REGISTRY

for relevant existing Skills and versions.

Do not load every Skill.

Only identify candidates relevant to the current task.

RESULT:

LOCAL_REGISTRY_DISCOVERY_COMPLETED

---

### PHASE 04 — External / Local Comparison

Compare externally discovered candidates against local Skills.

Evaluate:

- same identity
- same version
- newer version
- similar Skill
- alternative Skill
- completely new Skill
- conflicting Skill

Similarity does not authorize merging.

Functional overlap does not authorize merging.

A new external Skill must not overwrite an existing Skill.

RESULT:

EXTERNAL_LOCAL_COMPARISON_COMPLETED

---

### PHASE 05 — Source Review

For any external candidate that may be imported or used, evaluate the source according to:

SKILL_SOURCE_REGISTRY

Required review includes:

- source identity
- source URL
- author or organization
- license status
- external version or commit
- content hash when available
- update recency
- malicious instruction review
- credential and secret review
- private data review
- local duplicate comparison
- local similarity comparison
- compatibility impact
- task relevance

Discovery does not equal approval.

RESULT:

SOURCE_REVIEW_COMPLETED

---

### PHASE 06 — Candidate Preservation

Each candidate Skill remains independently identified.

The following actions are forbidden:

- deleting an existing Skill
- merging two Skills because they are similar
- overwriting an existing Skill identity
- overwriting a historical Skill version
- silently replacing an older Skill

A newer version must be added as a new immutable version.

A similar or alternative Skill must remain a separate Skill asset.

RESULT:

SKILL_IDENTITIES_PRESERVED

---

### PHASE 07 — Candidate Set Construction

Build the smallest candidate Skill set that can satisfy the task.

Candidate inclusion does not authorize co-loading.

Each candidate must retain:

- Skill ID
- exact version
- source identity
- status
- dependency information
- composition information

RESULT:

CANDIDATE_SKILL_SET_READY

---

### PHASE 08 — Pairwise Compatibility Evaluation

If more than one Skill is selected as a candidate, every selected pair must be evaluated.

For Skill A and Skill B, evaluate all required dimensions:

1. INPUT_CONTRACT
2. OUTPUT_CONTRACT
3. TOOL_REQUIREMENTS
4. FILE_MUTATION_SCOPE
5. EXECUTION_ORDER
6. TECHNOLOGY_STACK
7. VERSION_REQUIREMENTS
8. PERMISSION_REQUIREMENTS
9. SECURITY_RULES
10. PROJECT_GOVERNANCE
11. GIT_WORKFLOW
12. DEPENDENCY_REQUIREMENTS

Every required dimension must resolve to PASS before the pair may be marked COMPATIBLE.

Any unresolved dimension produces:

UNKNOWN

UNKNOWN is not COMPATIBLE.

RESULT:

PAIRWISE_COMPATIBILITY_EVALUATED

---

## 5. Compatibility Matrix

For N selected Skills, the AI Control Plane must evaluate every unique Skill pair.

Example:

Skill A + Skill B

Skill A + Skill C

Skill B + Skill C

Each pair must resolve to one of:

COMPATIBLE

CONFLICT

UNKNOWN

Only COMPATIBLE permits co-loading.

CONFLICT blocks co-loading.

UNKNOWN blocks co-loading until evaluated.

---

## 6. Conflict Gate

Gate:

SKILL_COMPOSITION_GATE

PASS requires:

- online discovery completed
- local discovery completed
- external/local comparison completed
- required source reviews completed
- Skill identities preserved
- dependencies resolved
- exclusive groups resolved
- every selected Skill pair evaluated
- no CONFLICT result
- no UNKNOWN result
- final Skill versions identified
- project governance satisfied

PASS:

ALLOW_EXECUTION_BLOCK

FAIL:

BLOCK_EXECUTION_BLOCK

---

## 7. Conflict Resolution Rules

The system must never solve Skill conflict by silently merging Skills.

The system must never delete one Skill merely because another Skill is preferred.

The system may:

- select only Skill A
- select only Skill B
- select another compatible Skill
- select a different version
- request Owner decision when governance requires it

The system must preserve all Skill assets and historical versions.

---

## 8. Skill Update Rules

Every selection cycle must perform fresh external discovery.

When an external update is found:

- compare it with the locally retained version
- preserve the previous version
- review the new version independently
- assign the new immutable version
- perform compatibility evaluation again
- change the current-version pointer only after approval

No silent update is allowed.

---

## 9. Skill Isolation Rules

Every Skill must have:

- independent identity
- independent directory
- independent manifest
- independent source record
- independent version history
- independent compatibility relationships

One Skill must not modify another Skill's files.

Similar Skills remain separate.

Alternative Skills remain separate.

Historical Skills remain retained.

---

## 10. Final Skill Set

Before Agent prompt generation, the AI Control Plane must produce:

FINAL_SKILL_SET

For every selected Skill include:

- Skill ID
- exact version
- reason selected
- source status
- compatibility status
- dependencies
- applicable constraints

The Agent Execution Plane may use only Skills contained in FINAL_SKILL_SET.

The Agent must not independently add another Skill.

---

## 11. No-Skill Case

If online and local discovery identify no useful Skill:

NO_APPLICABLE_SKILL

is a valid result.

The AI Control Plane may generate an execution prompt without a Skill when the task does not require one.

The absence of a useful Skill must not cause an irrelevant Skill to be selected.

---

## 12. Required Evidence

Each selection cycle should preserve enough evidence to establish:

- what was searched
- when it was searched
- what external candidates were found
- what local candidates were found
- what comparisons were performed
- what compatibility checks were performed
- what was selected
- what was rejected
- why the final Skill set was allowed

---

## 13. Final Rule

No Skill set may enter an Agent Execution Block while any required compatibility relation remains unknown or conflicting.

NO VERIFIED COMPATIBILITY
=
NO CO-LOAD
