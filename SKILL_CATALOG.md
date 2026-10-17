# 按需调用目录 · 2026-10-17

本次保存五个独立、版本为 **1.0.0** 的治理适配入口。每项保留原始来源、固定提交、许可证和来源快照。完整第三方软件、模型和渲染器没有安装或运行。

| 入口 | 优先度 | 适合的需求 | 保存后的能力 |
|---|---|---|---|
| [taste-ui-reference](skills/domain/taste-ui-reference/1.0.0/runtime/SKILL.md) | 高 | 工作台、表单与页面的布局/排版/密度 | 可直接作为设计参考；原生完整 v2 另行准备 |
| [archify-reference-diagrams](skills/domain/archify-reference-diagrams/1.0.0/runtime/SKILL.md) | 高 | 解释已批准架构、数据流与执行流程 | 可制作有来源的参考图；原生渲染器另行准备 |
| [agent-reach-public-data](skills/domain/agent-reach-public-data/1.0.0/runtime/SKILL.md) | 中 | 公开网页、社交讨论、RSS、视频字幕抓取 | 可准备抓取方案；实际抓取需要已有工具/平台权限 |
| [voicestudio-local-audio](skills/domain/voicestudio-local-audio/1.0.0/runtime/SKILL.md) | 按需 | 旁白、语音合成与录音转写 | 需要运行中的本地后端和适用模型 |
| [mirofish-scenarios](skills/domain/mirofish-scenarios/1.0.0/runtime/SKILL.md) | 实验性储备 | 多角色反应、流程失败情形和决策假设 | 可直接准备实验方案；实际模拟需完整环境、服务与预算 |

优先度基于用途与接入成本，是使用建议，不是软件质量或预测准确度的实测评级。

## 以后如何调用

向能读取此仓库的 AI 说明：

> 从 ETlvein/AI-Building-Skills 的 SKILL_REGISTRY 查询并读取 taste-ui-reference 1.0.0，根据当前需求给出设计建议；先满足当前项目的权限与范围约束。

也可把名称替换为表中其他入口；Operating notes 提供更多示例。GitHub 保存不会自动加入本机已安装 Skill 列表。若要使用 $名称 这类本机快捷调用，需要后续将选定 runtime 安装到该 Agent 的技能目录；也可由 AI 按本仓库路径显式读取使用。

每次正式选择仍需新的 Online Discovery、注册表比较和当前权限核对。五项均为 STANDALONE；与彼此或现有 systematic-debugging 共同加载的兼容性为 UNKNOWN，不能同时加载。源快照以 .txt 保存，仅供审计。

## 选择依据与限制

Taste 当前默认入口针对公开展示页，不适用于仪表盘。同源 minimalist-ui 更贴近产品界面，但其固定宽度、字体禁用及矛盾渐变要求没有被继承。本适配版保留品牌、业务状态色、中文可读性、密度与获准的全宽布局。

Archify 按灵感来源使用：参考结构和呈现，不因此修改既定架构。原生 finalize、浏览器或导出验证没有执行。

Agent Reach 可能要求额外 CLI 或登录态。“零 API 费用”不能理解为所有平台、代理或服务均免费。仅获取明确授权的公开内容。

MiroFish 是完整应用，本仓库为其创建 companion Skill。固定上游默认使用 LLM API 和 Zep Cloud，不承诺完全本地。模拟结果用于探索假设，不等于事实、临床证据或可靠概率。

VoiceStudio 的本地语音依赖应用和模型。远程处理和模型下载另核对授权。它与 MiroFish 的应用许可为 AGPL-3.0，模型、声音和素材许可分别检查；保留许可证不等于授予第三方声音或素材使用权。

## 记录

- [机器可读目录](catalogs/2026-10-17/CATALOG.json)
- [选择与来源审查](catalogs/2026-10-17/SELECTION_AUDIT.json)
- [发布前校验](catalogs/2026-10-17/PREPUBLICATION_VALIDATION.json)
- [当前 Skill 注册表](registries/SKILL_REGISTRY.yaml)
- [当前来源注册表](registries/SKILL_SOURCE_REGISTRY.yaml)

v1.0.0 治理基线、PromptStandard、原有 Skill 版本与历史证据保留原样。根 README 初始数量属于冻结基线；当前库存以当前注册表为准。
