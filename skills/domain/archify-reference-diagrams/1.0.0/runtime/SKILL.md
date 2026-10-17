---
name: archify-reference-diagrams
description: Create source-grounded architecture or workflow diagrams using Archify as visual and structural inspiration,
  or prepare a native Archify handoff. 用于架构图灵感与只读可视化，不授权改变架构。
---

# Archify Reference Diagrams

把 Archify 用作架构图的视觉与结构参考，依据输入说明或实际源码表达系统。绘图权限不等于架构变更权限。

先确定要回答的问题和图型：组件关系用 architecture；流程与 Gate 用 workflow；调用先后用 sequence；数据去向用 dataflow；状态变化用 lifecycle。表结构、类、层级、历史和耗时使用对应图型。选择能解释当前问题的粒度，避免把所有目录都当成运行组件。

每个节点和连线都应有输入依据；对源码图记录源文件位置与版本，区分已确认行为、设计意图与 UNKNOWN。不得从目录名称猜测调用链，也不得为美观添加不存在的缓存、服务、信任边界或安全能力。

参考 Archify 的分组、清晰边界、短标签、明暗主题和独立 HTML 交付方式。保留连接语义，先解决交叉、遮挡和阅读顺序，再增加装饰。优先自包含输出，外部字体或网络资源必须符合任务许可。

本入口默认 `ARCHIFY_INSPIRED`：允许直接制作有来源的图形，不需要安装 Archify；不宣称使用了其渲染器或通过其质量 Gate。对小型静态图，可用当前环境已有的 Mermaid 或 SVG，但不要因此加载另一 Skill。

若用户明确要求 `NATIVE_ARCHIFY`，先确认固定版本完整包已安装、Node.js 18+、相关 schema/example/references 和浏览器验证权限。遵守那一版真实 CLI 契约，不能仅凭本仓库保存的入口快照运行不完整的包。原生工具缺失时给出可执行的交接说明，实际渲染保持 BLOCKED。

保存图源和输出到授权路径，使用新文件保护已有成果。实际查看后再报告视觉观察；文件语义检查、原生工具检查、浏览器运行和视觉检查分别记录。没有执行的检查标为 NOT_RUN。

原生版本与来源见 [Operating notes](references/OPERATING_NOTES.md)。
