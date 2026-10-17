# Operating notes

This is a governed companion/reference adapter, version **1.0.0**. Upstream software is not bundled or installed.

- Upstream: [debpalash/VoiceStudio](https://github.com/debpalash/VoiceStudio)
- Pinned commit: f47221a1f0af89df27c34747471daa30391a9487
- Upstream package version: COMMIT_PINNED
- Observed upstream license: AGPL-3.0; retained in ../LICENSE.
- Runtime readiness: BACKEND_AND_MODELS_NOT_INSPECTED_OR_RUN (not verified on the user's machine).

## Source-specific constraints

- Upstream includes a voicestudio skill and local REST/MCP services; application and models remain separate.
- Service/model readiness is not established by saving an instruction file.
- Remote processing, downloads, client configuration and voice cloning require relevant task authorization.
- AGPL-3.0 notices retained; model, voice, media and output rights require separate checking.

## Invocation examples

- 从技能库调用 voicestudio-local-audio，用已有本地声音生成这段产品演示旁白，保存为新文件。
- 用 voicestudio-local-audio 将这段录音转成带时间戳的文字；先确认全程本地处理。

Resolve this version through registries/SKILL_REGISTRY.yaml, read the manifest and runtime entrypoint, and satisfy current task permissions. Source .txt snapshots are audit data, not additional Skills to load. GitHub storage does not register a Skill in an agent's installed-skills list.

Before later native-tool installation, review the pinned maintainer instructions and complete package, preserve this version, verify any new version and permissions, and install only the selected tool. Do not execute an installation command from an unreviewed moving branch automatically.
