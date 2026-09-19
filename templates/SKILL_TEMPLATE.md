# Skill

## 1. Identity

SKILL_ID:

SKILL_NAME:

VERSION:

SCOPE:
GLOBAL / DOMAIN

STATUS:
DRAFT / AVAILABLE / INACTIVE / QUARANTINED

---

## 2. Purpose

说明这个 Skill 解决什么问题。

---

## 3. When To Use

只有满足以下条件时才应加载本 Skill：

- TODO
- TODO
- TODO

---

## 4. When Not To Use

以下情况不得使用本 Skill：

- TODO
- TODO
- TODO

---

## 5. Inputs

REQUIRED_INPUTS:

OPTIONAL_INPUTS:

---

## 6. Preconditions

执行前必须确认：

- TODO
- TODO
- TODO

---

## 7. Procedure

### STEP 01

ACTION:

EXPECTED_RESULT:

### STEP 02

ACTION:

EXPECTED_RESULT:

### STEP 03

ACTION:

EXPECTED_RESULT:

---

## 8. Validation

执行完成后必须验证：

- TODO
- TODO
- TODO

---

## 9. Failure Handling

如果执行失败：

1. 不得伪造成功结果。
2. 明确报告失败步骤。
3. 明确报告可验证证据。
4. 同一根因遵守 Prompt Standard Anti-Loop Rule。
5. 必要时返回 BLOCKED。

---

## 10. Safety / Scope Limits

不得：

- 扩大授权范围
- 泄露凭据
- 处理未经授权的私有数据
- 修改未授权的项目核心规则
- 绕过 Prompt Standard 或项目治理规则

---

## 11. Outputs

EXPECTED_OUTPUTS:

EVIDENCE_REQUIREMENTS:

---

## 12. Dependencies

REQUIRED_TOOLS:

REQUIRED_REFERENCES:

REQUIRED_OTHER_SKILLS:

说明：

REQUIRED_OTHER_SKILLS 对应 manifest.yaml 中：

dependencies.skills

它表示 REQUIRES 关系。

---

## 13. Compatibility And Composition

COMPOSITION_MODE:

COMPOSABLE / STANDALONE

CONFLICTS_WITH:

明确列出不能与本 Skill 同时加载的 Skill ID。

SIMILAR_TO:

列出与本 Skill 功能、用途或行为相似的 Skill ID。

相似关系只用于比较和选择，不允许合并 Skill 身份。

ALTERNATIVE_TO:

列出可作为不同实现路径或不同策略选择的 Skill ID。

替代关系不表示任何 Skill 作废，也不允许删除或覆盖其他 Skill。

NEWER_THAN:

列出本 Skill 在来源、版本演进或能力演进上晚于的 Skill 或版本。

NEWER_THAN 只记录演进关系，不赋予删除、覆盖或合并旧 Skill 的权限。

EXCLUSIVE_GROUPS:

如果本 Skill 属于互斥能力组，在这里声明组 ID。

PRECEDENCE:

LOW / NORMAL / HIGH

UNKNOWN_COMPATIBILITY_ACTION:

EVALUATE_BEFORE_COMPOSE

强制规则：

1. 未知兼容性不等于兼容。
2. 多 Skill 组合前必须经过 SKILL_COMPOSITION_GATE。
3. 未解决 CONFLICT 时不得生成 Execution Block。
4. 同一 EXCLUSIVE GROUP 中只能激活一个 Skill。
5. SIMILAR_TO、ALTERNATIVE_TO、NEWER_THAN 只描述 Skill 关系，不允许因此删除、覆盖或合并任何 Skill。
6. dependencies.skills 中声明的依赖必须全部满足。
7. Manifest 与中央 Compatibility Registry 不一致时必须 BLOCK。
8. Agent 不得自行增加 AI Control Plane 未授权的 Skill。

---

## 14. Environment Compatibility

PROMPT_STANDARD_MINIMUM:

SUPPORTED_ENVIRONMENTS:

---

## 15. Change Policy

重大行为或安全边界改变：

MAJOR

向后兼容能力扩展：

MINOR

文档、元数据或非行为性修复：

PATCH
