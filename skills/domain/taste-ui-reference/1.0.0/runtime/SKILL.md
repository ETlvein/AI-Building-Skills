---
name: taste-ui-reference
description: Use Taste Skill as an optional reference for UI layout, typography, spacing and visual review; distinguish
  product workbenches from public marketing pages. 用于界面设计参考，不覆盖既有设计系统和工作区约束。
---

# Taste UI Reference

将 Taste Skill 用作设计参考。先判断页面属于产品界面还是公开展示页面，再选取适用原则。

- 产品工作台、表单、仪表盘：参考同源 `minimalist-ui` 的层级、间距、扁平表面与克制用色。
- 官网、介绍页、作品集：参考 `design-taste-frontend` 的主题构思、构图、真实素材与视觉检查方法。
- 已有品牌和组件系统优先；保留业务状态色、可访问性、表格密度、中文可读性以及用户批准的主体宽度。

先读实际页面、任务目标和写入范围。给出可验证的设计判断：用户最先需要看见什么、主要操作在哪里、内容如何分组、不同宽度如何呈现。仅在用户要求实现且项目允许时修改代码。

把上游的字体禁用、固定色板、卡片边框、强制图片数量、强制动画、`max-w-4xl/max-w-5xl` 等视为其特定风格主张。不要把它们提升为项目规则；尤其不要据此缩窄需要全宽的工作台。上游 minimalist 文档同时含有禁用渐变及建议渐变的指令，本适配版不继承这些矛盾要求。

输出设计建议时连接具体问题与预期效果。实现后只报告实际运行的检查；截图观察、自动规则检查和 Owner 接受分别记录。没有查看截图就不得声称视觉验收通过。

本入口自包含，不加载两份上游 Skill。上游快照仅用于来源审计；完整 v2 的 Node 22、浏览器、素材库和检查脚本没有随本入口安装。若用户要求原生 v2 工作流，先按固定提交重新审查完整包和执行权限。

需要来源细节时读 [Operating notes](references/OPERATING_NOTES.md)。
