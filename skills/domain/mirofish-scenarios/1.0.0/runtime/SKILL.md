---
name: mirofish-scenarios
description: Prepare reproducible MiroFish scenario experiments and review runs from an already configured simulator.
  用于多角色场景假设、实验设计和结果审阅；没有实际运行时仅交付推演方案。
---

# MiroFish Scenarios

MiroFish 是完整的多智能体模拟应用。这个入口是为其准备的独立 companion Skill，不把应用本体描述为已安装 Skill，也不把文字角色讨论描述成引擎运行。

默认先交付 `SIMULATION_PLAN_ONLY`：明确决策问题、输入材料、已知事实、关键假设、角色来源、变量、对照条件、轮数与预算、随机性、停止条件和需要观察的指标。模拟适合探索可能反应与失败情形；不得将模型共识当作事实、临床证据或已经校准的预测概率。

实际运行前核对用户已有环境。固定提交要求 Node.js 18+、Python 3.11 至 3.12 和 uv；默认方案使用 LLM API 及 Zep Cloud。不要承诺默认完全本地化，也不要把 Ollama-ready fork 的能力归给本次固定的上游。

只有在任务明确授权模拟运行、外部数据流向、费用预算及相应文件写入时，才调用现有实例。密钥、服务地址、硬件能力和输入许可未知时明确标记 UNKNOWN。未获授权不要创建付费资源、启动服务、批量生成 Agent 或上传材料；使用公开或合成输入，真实个人/医疗材料需要专门的数据授权。

为每次真实运行保留输入材料身份、配置、上游提交、模型/服务版本（可获时）、运行 ID、起止时间、轮次与消费、日志和原始报告。配置偏差、缺失证据和失败单独记录；运行未完成就报告 `INCOMPLETE_RUN`。

结果应同时列出支持当前方案的场景、反例与敏感假设。说明哪些是输入事实、哪些是设定、哪些是模拟生成结果。只有得到真实运行产物才使用 `EXECUTED_SIMULATION`；计划、手工角色分析和模拟运行分开命名。

查看依赖、默认数据流向及许可证证据时读 [Operating notes](references/OPERATING_NOTES.md)。
