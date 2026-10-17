# Operating notes

This is a governed companion/reference adapter, version **1.0.0**. Upstream software is not bundled or installed.

- Upstream: [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach)
- Pinned commit: 94f06c1969dfc1834001269d79d3ad0972d9dee6
- Upstream package version: 1.5.0
- Observed upstream license: MIT; retained in ../LICENSE.
- Runtime readiness: NOT_INSPECTED_NOT_INSTALLED_BY_THIS_TASK (not verified on the user's machine).

## Source-specific constraints

- Raw upstream requires nearly every internet task to use it; adapter narrows routing to relevant public retrieval.
- Auto-update checks, mandatory temporary-directory policy and credential-configuration instructions are not inherited.
- No posting, private content access, browser cookie extraction, account setup or restriction bypass is authorized.
- Only selected instructions and package metadata reviewed; implementation, platform access and runtime remain untested.

## Invocation examples

- 从技能库调用 agent-reach-public-data，抓取这些公开网页并保存来源、时间和正文摘录。
- 用 agent-reach-public-data 整理公开产品讨论；先说明可用渠道和抓取范围。

Resolve this version through registries/SKILL_REGISTRY.yaml, read the manifest and runtime entrypoint, and satisfy current task permissions. Source .txt snapshots are audit data, not additional Skills to load. GitHub storage does not register a Skill in an agent's installed-skills list.

Before later native-tool installation, review the pinned maintainer instructions and complete package, preserve this version, verify any new version and permissions, and install only the selected tool. Do not execute an installation command from an unreviewed moving branch automatically.
