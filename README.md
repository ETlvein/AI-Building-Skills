# AI-Building-Skills

Central repository for reusable AI Skills, Skill Registry, and safe technical references.

## Governance

This repository is governed by:

AI-Building-PromptStandard

Locked Prompt Standard reference:

v1.0.0

Repository:

https://github.com/ETlvein/AI-Building-PromptStandard

## Purpose

本仓库负责保存和治理可复用的 AI Skill。

公开仓库只允许：

- GLOBAL Skills
- DOMAIN Skills
- Public-safe References
- Skill Registry
- Reference Registry
- Skill Templates
- Schemas

PROJECT Skills 不应默认进入本公开仓库。

项目专属或敏感 Skill 应保存于：

- Project Local Repository
- Private Repository

## Resolution Model

默认采用：

Registry First

流程：

TASK
-> Skill Registry Discovery
-> Skill Selection
-> Load Required Skill
-> Execute

禁止一次加载全部 Skill。

## Skill Structure

每个正式 Skill 原则上采用：

<pre>
skill-name/
|-- SKILL.md
|-- manifest.yaml
</pre>

其中：

SKILL.md

负责描述 Skill 的实际使用规则、步骤、边界和验证要求。

manifest.yaml

负责提供机器可读的身份、版本、Scope、依赖、兼容性和发布状态。

## Public Repository Safety

禁止提交：

- Password
- Token
- API Key
- Cookie
- SSH Private Key
- Certificate Private Key
- Database Password
- Patient Data
- Customer Private Data
- Unauthorized Business Secrets
- Sensitive Project-Specific Skills
- Other Sensitive Credentials

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
|   |-- domain
|
|-- registries
|   |-- SKILL_REGISTRY.yaml
|   |-- REFERENCE_REGISTRY.yaml
|
|-- references
|
|-- templates
|   |-- SKILL_TEMPLATE.md
|   |-- SKILL_MANIFEST_TEMPLATE.yaml
|
|-- schemas
|   |-- SKILL_MANIFEST.schema.json
|
|-- changelog
    |-- CHANGELOG.md
</pre>

## Current Status

Repository Status:

DRAFT

Current public Skills:

0

Current public References:

0

Initial repository structure and governance are still being prepared.

## Publication Model

Local Authoring Source:

D:\AI Building_Skills

Git Published Source:

https://github.com/ETlvein/AI-Building-Skills

本地文件不等于正式发布。

只有经过必要验证并完成：

Git Commit
+
Git Push

之后，内容才进入 Published Source.
