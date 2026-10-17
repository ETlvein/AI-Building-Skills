# Operating notes

This is a governed companion/reference adapter, version **1.0.0**. Upstream software is not bundled or installed.

- Upstream: [666ghj/MiroFish](https://github.com/666ghj/MiroFish)
- Pinned commit: 7657031ac01184afe2cb220f5ee3545573b5e843
- Upstream package version: COMMIT_PINNED
- Observed upstream license: AGPL-3.0; retained in ../LICENSE.
- Runtime readiness: PLAN_MODE_READY;SIMULATOR_NOT_INSTALLED_OR_RUN (not verified on the user's machine).

## Source-specific constraints

- Upstream is an application, not a portable SKILL.md package.
- Independent companion skill provides experiment planning and evidence review; it is not the simulator.
- Pinned upstream defaults require LLM and Zep Cloud; no fully local operation is claimed.
- No simulator run, agent population, upload, budget consumption or predictive-accuracy validation occurred.

## Invocation examples

- 从技能库调用 mirofish-scenarios，为三个用户群体对新流程的反应设计对照推演，只做方案。
- 用 mirofish-scenarios 审核这份已运行的模拟报告，区分输入事实、假设和模型生成内容。

Resolve this version through registries/SKILL_REGISTRY.yaml, read the manifest and runtime entrypoint, and satisfy current task permissions. Source .txt snapshots are audit data, not additional Skills to load. GitHub storage does not register a Skill in an agent's installed-skills list.

Before later native-tool installation, review the pinned maintainer instructions and complete package, preserve this version, verify any new version and permissions, and install only the selected tool. Do not execute an installation command from an unreviewed moving branch automatically.
