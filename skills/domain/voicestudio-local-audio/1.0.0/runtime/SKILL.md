---
name: voicestudio-local-audio
description: Use an existing local VoiceStudio backend for speech synthesis or transcription, checking live voices,
  engines and output files. 用于本地语音、转写和旁白；安装、下载模型及远端处理按任务另行授权。
---

# VoiceStudio Local Audio

使用用户已安装的 VoiceStudio 和已有模型生成语音或转写音频。优先本地处理；保存 Skill 不代表本地服务、模型或麦克风已经可用。

在任务允许网络/本地服务访问时，先检查用户指定后端；默认是 `http://localhost:3900`。依次读取 `GET /health`、`GET /openapi.json` 和 `GET /v1/audio/voices`，以运行实例为准确认版本、端点、语音 ID 与引擎能力。目录展示不证明模型已下载。

后端不可用时报告 `BLOCKED_BACKEND_UNAVAILABLE`。不要自动安装第二份应用、下载模型、切换到云服务或公开端口。若用户要求安装或启动，先复用已有位置与数据，再按对应固定版本说明和授权执行。

常用兼容 API 为 `POST /v1/audio/speech` 和 `POST /v1/audio/transcriptions`；原生异步任务、配音和克隆操作以实时 OpenAPI 为准。MCP 默认地址为 `http://localhost:3900/mcp`，仅在客户端已连接且该任务允许时使用，不自行修改客户端配置。

生成前明确文本、语言、声音、输出格式、允许目录和是否使用参考录音。确认用户有权使用该声音。保留原音频、参考录音、已有声音档案和项目；输出使用新路径。鉴权失败不得通过关闭鉴权解决，凭据不得出现在命令回显、文件或报告中。

本地不等于永远离线：模型下载、远端 ASR、翻译服务和远程后端可能传出数据。按实际配置说明数据去向；没有授权时不发送私有录音或文字。应用许可证和模型/声音/素材权利分别核实，不承诺输出的商业使用资格。

检查 HTTP 状态，并实际解码或探测输出音频的格式与时长，防止把 JSON 错误响应当成音频。异步任务按运行实例返回的 ID 跟踪终态，超时不能盲目重提。转写完成与写入另一个应用是不同动作。

交付可用文件路径、实际格式/时长或转写时间范围、使用的引擎与声音、处理位置和已知限制。服务不可用、模型缺失、权限失败及未完成任务分别报告，不生成虚假的旁白或转写结果。

安装版本和 AGPL 来源见 [Operating notes](references/OPERATING_NOTES.md)。
