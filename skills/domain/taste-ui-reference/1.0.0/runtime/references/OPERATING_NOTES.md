# Operating notes

This is a governed companion/reference adapter, version **1.0.0**. Upstream software is not bundled or installed.

- Upstream: [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill)
- Pinned commit: f624f37a8c650b9cc550253104925efe4c8de246
- Upstream package version: COMMIT_PINNED
- Observed upstream license: MIT; retained in ../LICENSE.
- Runtime readiness: REFERENCE_MODE_READY;UPSTREAM_RUNTIME_NOT_INSTALLED (not verified on the user's machine).

## Source-specific constraints

- Default upstream design-taste-frontend targets public-facing pages and excludes dashboards.
- minimalist-ui is more relevant to workbenches; fixed max widths, font bans and conflicting gradient directives are not adopted.
- Adapter is optional reference; approved design systems, accessibility, density and width constraints retain authority.
- Native v2 assets/scripts/library are not bundled or executed. Raw skills are not co-loaded.

## Invocation examples

- 从技能库调用 taste-ui-reference，为这个工作台提出三个布局方案，保留既有交互和语义颜色。
- 用 taste-ui-reference 检查页面的字体层级、对比度和信息密度，只提出修改建议。

Resolve this version through registries/SKILL_REGISTRY.yaml, read the manifest and runtime entrypoint, and satisfy current task permissions. Source .txt snapshots are audit data, not additional Skills to load. GitHub storage does not register a Skill in an agent's installed-skills list.

Before later native-tool installation, review the pinned maintainer instructions and complete package, preserve this version, verify any new version and permissions, and install only the selected tool. Do not execute an installation command from an unreviewed moving branch automatically.
