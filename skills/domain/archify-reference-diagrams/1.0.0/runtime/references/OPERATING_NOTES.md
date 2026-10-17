# Operating notes

This is a governed companion/reference adapter, version **1.0.0**. Upstream software is not bundled or installed.

- Upstream: [tt-a1i/archify](https://github.com/tt-a1i/archify)
- Pinned commit: 88d1ae4498b6a1df610badf690c5406882622d15
- Upstream package version: 3.1.0
- Observed upstream license: MIT; retained in ../LICENSE.
- Runtime readiness: REFERENCE_MODE_READY;UPSTREAM_RENDERER_NOT_INSTALLED (not verified on the user's machine).

## Source-specific constraints

- Archify 3.1.0 is an agent skill with renderer/schema/reference dependencies.
- Adapter uses structural and visual inspiration and labels output ARCHIFY_INSPIRED.
- Native renderer, browser gates, built-in update checks and exports were not installed or run.
- Visualization cannot authorize architecture changes; native use requires a complete reviewed package.

## Invocation examples

- 从技能库调用 archify-reference-diagrams，把已批准架构画成组件与数据流图，标明信任边界。
- 用 archify-reference-diagrams 为这段系统说明生成可分享的 HTML 架构图，未知连线单独列出。

Resolve this version through registries/SKILL_REGISTRY.yaml, read the manifest and runtime entrypoint, and satisfy current task permissions. Source .txt snapshots are audit data, not additional Skills to load. GitHub storage does not register a Skill in an agent's installed-skills list.

Before later native-tool installation, review the pinned maintainer instructions and complete package, preserve this version, verify any new version and permissions, and install only the selected tool. Do not execute an installation command from an unreviewed moving branch automatically.
