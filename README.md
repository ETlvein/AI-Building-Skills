# AI-Building-Skills

Central repository for reusable AI Skills, Skill discovery governance, compatibility control, version retention, and safe public technical references.

## Governance

This repository is governed by:

AI-Building-PromptStandard

Locked Prompt Standard reference:

v1.0.0

Repository:

https://github.com/ETlvein/AI-Building-PromptStandard

---

## Core Purpose

本仓库负责保存、发现、审查、版本化和选择可复用 AI Skill。

核心原则：

1. 每次 Skill 选择周期都必须进行新的 Online Discovery。
2. Online Discovery 必须与本地 Skill Registry 同时参与选择。
3. 外部 Skill 必须先与本地 Skill 对比。
4. Skill 之间存在任何未解决冲突时禁止共同加载。
5. UNKNOWN compatibility 不等于 COMPATIBLE。
6. Skill 永久保留。
7. 历史版本永久保留。
8. 禁止因为 Skill 相似而自动合并。
9. 禁止用新版覆盖旧版。
10. 每个 Skill 必须保持独立身份与独立目录。
11. Agent 只能使用 AI Control Plane 已批准的 FINAL_SKILL_SET。

---

## Public Repository Scope

本公开仓库只允许：

- GLOBAL Skills
- DOMAIN Skills
- Public-safe References
- Skill Registries
- Source Registry
- Compatibility Registry
- Protocols
- Templates
- Schemas

PROJECT Skills 不应默认进入本公开仓库。

项目专属或敏感 Skill 应保存在：

- Project Local Repository
- Private Repository

---

## Skill Discovery Model

每次生成最终 Agent Execution Prompt 前，Skill 选择流程原则上为：

<pre>
TASK
|
v
ONLINE SKILL DISCOVERY
+
LOCAL SKILL REGISTRY DISCOVERY
|
v
EXTERNAL / LOCAL COMPARISON
|
v
SOURCE REVIEW
|
v
CANDIDATE SKILL SET
|
v
PAIRWISE COMPATIBILITY CHECK
|
v
SKILL_COMPOSITION_GATE
|
+-- CONFLICT / UNKNOWN --> BLOCK
|
v
FINAL_SKILL_SET
|
v
AGENT EXECUTION BLOCK
</pre>

本地已经存在相关 Skill 时，也不能因此跳过新的 Online Discovery。

如果没有适用 Skill：

NO_APPLICABLE_SKILL

是合法结果。

禁止为了“必须使用 Skill”而选择无关 Skill。

---

## Zero-Unresolved-Conflict Rule

多个 Skill 共同加载之前，必须完成兼容性检查。

每一对候选 Skill 至少需要检查：

- Input Contract
- Output Contract
- Tool Requirements
- File Mutation Scope
- Execution Order
- Technology Stack
- Version Requirements
- Permission Requirements
- Security Rules
- Project Governance
- Git Workflow
- Dependency Requirements

只有：

COMPATIBLE

才允许共同加载。

以下结果均禁止共同加载：

- CONFLICT
- UNKNOWN

规则：

<pre>
NO VERIFIED COMPATIBILITY
=
NO CO-LOAD
</pre>

---

## Skill Isolation

每个 Skill 都是独立治理资产。

每个 Skill 必须拥有：

- Independent Skill ID
- Independent Directory
- Independent Manifest
- Independent Source Record
- Independent Version History
- Independent Compatibility Relationships

禁止：

- Skill A 修改 Skill B 的文件
- 因相似而合并 Skill
- 因功能重叠而合并 Skill
- 用新 Skill 覆盖旧 Skill
- 删除不再默认使用的 Skill

---

## Permanent Retention

Skill 生命周期允许：

- DRAFT
- AVAILABLE
- INACTIVE
- QUARANTINED

不使用：

DEPRECATED

因为不再默认选择并不意味着删除或作废。

含义：

DRAFT

尚未完成正式审核。

AVAILABLE

正常允许选择。

INACTIVE

当前默认不选择，但永久保留。

QUARANTINED

因为安全、兼容或治理问题暂时禁止执行，但永久保留。

---

## Version Model

历史版本不可覆盖。

示例：

<pre>
SKILL_A
|
|-- v1.0.0
|-- v1.1.0
|-- v2.0.0
|
`-- current_version -> v2.0.0
</pre>

改变 current_version 只改变默认选择版本。

不会删除：

- v1.0.0
- v1.1.0
- 任何其他历史版本

---

## External Skill Discovery

外部发现由：

SKILL_SOURCE_REGISTRY

进行治理。

外部 Skill：

发现不等于批准。

更新不等于覆盖。

相似不等于合并。

新版本必须作为新版本加入。

外部候选在导入前必须进行必要的：

- Source Review
- License Review
- Safety Review
- Secret / Credential Review
- Private Data Review
- Local Comparison
- Compatibility Review
- Project Relevance Review

---

## Registries

### SKILL_REGISTRY

负责：

- 本地有哪些 Skill
- Skill Identity
- Skill Version History
- Current Version
- Skill Status

### SKILL_SOURCE_REGISTRY

负责：

- Skill 从哪里发现
- External Source
- External Version / Commit
- Source Review
- Update Detection
- Import Decision
- Discovery History

### SKILL_COMPATIBILITY_REGISTRY

负责：

- COMPATIBLE
- CONFLICT
- REQUIRES
- ALTERNATIVE
- SIMILAR
- NEWER_THAN
- EXCLUSIVE

以及：

SKILL_COMPOSITION_GATE

### REFERENCE_REGISTRY

负责可复用公共技术资料和参考来源。

---

## Selection Audit

每次重要 Skill 选择周期都应保存足够证据，包括：

- Online Search
- Local Registry Search
- External / Local Comparison
- Source Review
- Candidate Set
- Pairwise Compatibility
- Conflict / Unknown Result
- Final Skill Selection
- Rejected Candidates
- Exact Skill Version
- Final Gate Result

模板：

templates/SKILL_SELECTION_AUDIT_TEMPLATE.yaml

---

## Skill Structure

每个正式 Skill 原则上保持独立目录。

Skill 本体与版本化目录结构将在正式 Skill 引入阶段按照永久版本策略建立。

单个 Skill 的核心信息包括：

- SKILL.md
- manifest.yaml
- Version
- Source Identity
- Compatibility Metadata
- Lifecycle Metadata

---

## Repository Structure

<pre>
AI-Building-Skills
|
|-- CURRENT_SKILLS.yaml
|-- README.md
|-- .gitattributes
|
|-- skills
|   |-- global
|   `-- domain
|
|-- registries
|   |-- SKILL_REGISTRY.yaml
|   |-- SKILL_SOURCE_REGISTRY.yaml
|   |-- SKILL_COMPATIBILITY_REGISTRY.yaml
|   `-- REFERENCE_REGISTRY.yaml
|
|-- protocols
|   `-- SKILL_DISCOVERY_SELECTION_PROTOCOL.md
|
|-- references
|
|-- templates
|   |-- SKILL_TEMPLATE.md
|   |-- SKILL_MANIFEST_TEMPLATE.yaml
|   `-- SKILL_SELECTION_AUDIT_TEMPLATE.yaml
|
|-- schemas
|   `-- SKILL_MANIFEST.schema.json
|
`-- changelog
    `-- CHANGELOG.md
</pre>

---

## Current Status

Repository Status:

DRAFT

Current public Skills:

0

Current public References:

0

Skill governance infrastructure is being established before the first formal reusable Skill is admitted.

---

## Publication Model

Local Authoring Source:

D:\AI Building_Skills

Git Published Source:

https://github.com/ETlvein/AI-Building-Skills

本地修改不等于正式发布。

只有经过必要验证并完成：

Git Commit
+
Git Push
+
Remote Verification

之后，内容才进入 Published Source。
