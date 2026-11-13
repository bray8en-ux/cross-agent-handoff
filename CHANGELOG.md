# V0.1 → V0.2 RC 变更清单

## 2026-11-13 — Release packaging and documentation

- Added concise English/Chinese fresh-install commands.
- Moved the existing guarded installation and rollback scripts to INSTALL.md and INSTALL.zh-CN.md.
- Added a 15-second illustrated handoff GIF.
- Prepared the versioned GitHub pre-release ZIP and SHA256 attachment.
- Protocol, Skill resources, and existing validation limitations are unchanged.

## 已有能力继续保留

V0.1 已具备交接、恢复、按需扩展平台三模式，以及复用项目事实源、核对真实文件/Git、记录测试和下一步的基础协议。V0.2 不把这些重新计为新增功能，不强制引入任务管理目录。

## A 增强（来自 Phase 1A）

| 文件 | 相对 V0.1 的变化 |
| --- | --- |
| `skills/cross-agent-handoff/SKILL.md` | 更明确的交接意图、决定理由、失败经验、未决问题、DO NOT REDO、唯一立即动作、修改前解释、测试版本与 Git 特殊状态；证据先保存后引用；手动/宿主事件边界 |
| `skills/cross-agent-handoff/assets/HANDOFF.template.md` | 补充理由、失败、问题、项目状态与待核实信息，保留原有目标/进度/验证/下一步 |
| `skills/cross-agent-handoff/references/quality-check.md` | 新增交出/接收质量核对清单，不增加运行时或任务系统 |
| `skills/cross-agent-handoff/references/platforms.md` | 保留开放平台集合与通用 Markdown 优先，澄清事件前提和非 CLI 控制范围 |
| `examples/HANDOFF.example.md` | 虚构示例展示理由、失败和未决问题；不计为运行证据 |

## RC 文档与分发整理（本轮）

| 文件 | 相对 Phase 1A 最终候选的变化 |
| --- | --- |
| `README.md` | 英文使用说明、安装与自动触发边界、证据状态口径 |
| `README.zh-CN.md` | 中文使用说明；`README.en.md` 保留为英文入口兼容页 |
| `VALIDATION.md` | 合并两阶段真实证据、受测哈希、风险及 NOT RUN / NOT VERIFIED 项 |
| `RELEASE_NOTES.md` | 新增版本说明与阶段范围 |
| `CHANGELOG.md` | 新增本变更清单 |
| `ROLLBACK.md` | 新增不覆盖旧版的回退方法 |
| `SHA256SUMS` | 覆盖此 RC 的实际文件，不借用旧候选或 ZIP 校验值 |
| `skills/cross-agent-handoff/SKILL.md` | 仅版本标识改为 `v0.2.0-rc.1`，其余正文/元数据不变 |
| `examples/HANDOFF.example.md` | 明确未附日志的示例路径不能视为已存在证据，仍是同一虚构示例 |

两份 LICENSE、`.gitignore`、模板、质量清单及平台参考相对 Phase 1A 最终候选保持字节一致。逐文件前后 SHA256 与实际统一差异保存在分发包外的本机 RC 审计材料中。没有新增 B1、事件执行器、CLI 控制或其他运行时代码。

状态与风险以 [合并验收报告](VALIDATION.md) 为准；回退见 [ROLLBACK.md](ROLLBACK.md)。

## DocsFix 2026-10-31（独立副本）

仅补齐双语安装、卸载、升级、回滚与 FAQ；README.md 为英文，新增 README.zh-CN.md，旧 README.en.md 为兼容入口。协议、模板、触发规则和许可不变。重新计算此副本清单与 ZIP，不覆盖原 RC。新包验证不沿用旧包 PASS。


## GitHub README visuals and quick-start update

| File | Update |
| --- | --- |
| `README.md` | Clarifies project positioning; adds Mermaid handoff-flow and handoff-content diagrams, copyable handoff/resume prompts, and an anonymized desktop-companion example. |
| `README.zh-CN.md` | Adds the equivalent Chinese positioning, diagrams, quick-start prompts, and desktop-companion example. |

The diagrams use GitHub-rendered Mermaid blocks; no external image host or remote asset is required. The wording clarifies that a project may reuse an existing state document (for example, `CURRENT_STATE.md`) rather than creating a parallel `HANDOFF.md`. No Skill runtime behavior, templates, platform adapters, or validation claims were changed.
