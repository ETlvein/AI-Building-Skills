# AI-Building-Skills Changelog

## [Unreleased]

Status:

DRAFT

### Added

- SKILL_SOURCE_REGISTRY
- SKILL_COMPATIBILITY_REGISTRY
- Skill Discovery & Selection Protocol
- Skill Selection Audit Template
- Mandatory fresh Online Skill Discovery
- External-to-local Skill comparison
- Pairwise compatibility evaluation
- SKILL_COMPOSITION_GATE
- UNKNOWN compatibility blocking rule
- Permanent Skill retention
- Permanent historical version retention
- Skill isolation model
- Independent Skill identity
- Independent Skill directory requirement
- Independent Skill version history
- Source provenance tracking
- External Skill update detection
- NO_APPLICABLE_SKILL result
- Final Skill Set execution restriction

### Changed

- SKILL_REGISTRY upgraded to permanent version-aware model
- SKILL_MANIFEST_TEMPLATE upgraded with source, composition, lifecycle, and compatibility metadata
- SKILL_MANIFEST JSON Schema upgraded to enforce lifecycle and composition rules
- Skill lifecycle status model changed to:
  - DRAFT
  - AVAILABLE
  - INACTIVE
  - QUARANTINED
- README updated to reflect current governance architecture

### Governance Rules

The following are now explicit repository rules:

- Skill deletion is forbidden
- Automatic Skill merge is forbidden
- Historical version overwrite is forbidden
- Similar Skills remain independent
- Alternative Skills remain independent
- Newer versions preserve older versions
- Online discovery must not be skipped because a local Skill exists
- Unknown compatibility is not compatibility
- Conflicting Skills must not co-load
- Unverified Skill combinations must not enter an Execution Block
- Agent may use only the approved FINAL_SKILL_SET

### Existing Foundation

- AI-Building-Skills repository structure
- CURRENT_SKILLS.yaml
- SKILL_REGISTRY.yaml
- REFERENCE_REGISTRY.yaml
- GLOBAL and DOMAIN Skill storage model
- Skill Template
- Skill Manifest Template
- Skill Manifest JSON Schema
- Registry-based local discovery
- Public repository safety policy
- PromptStandard v1.0.0 governance lock
- Cross-platform line-ending policy

### Pending

- Full governance consistency audit
- Public repository safety re-check
- Git diff validation
- Governance commit
- Git push
- GitHub remote reverse verification
- First real Online Skill Discovery cycle
- First reusable Skill admission

## Versioning Rule

Major:

Breaking Skill governance, compatibility, retention, identity, or schema changes.

Minor:

Backward-compatible Skill system capabilities and governance extensions.

Patch:

Documentation, metadata, or non-behavioral corrections.
