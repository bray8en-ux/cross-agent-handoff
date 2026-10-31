# v0.2.0-rc.1

日期：2026-10-31。状态：独立 Release Candidate，等待人工验收，未正式替换或发布。

## 本候选收录什么

基于 Phase 1A 最终候选收口 A 默认交接增强：当前进度与验证证据、DO NOT REDO、决策理由、真实失败经验、未决问题、唯一下一步、项目/Git 状态及待核实信息。保留手动交接、恢复和按需扩展平台的既有三模式。接收端先核对现场、解释上下文，再开展已授权的未完任务。

本轮没有新增工作流功能。SKILL.md 仅将版本标识从 `v0.2.0-phase1a` 改为 `v0.2.0-rc.1`；模板、质量检查和平台流程沿用 Phase 1A 最终候选。新增英文使用说明、版本/变更/回滚说明，合并两阶段的真实验收记录，澄清虚构示例不附真实证据。

## 验收口径

[VALIDATION.md](VALIDATION.md) 是本包的 Phase 1A + Phase 1B 合并验收报告。Phase 1A 的同宿主独立上下文接续有修改前理解及测试证据；Phase 1B 的代码、14 项测试日志和哈希可核验。Phase 1B 的实际跨宿主会话身份与修改前理解时序缺少可独立核对的原始证据，保持 **NOT VERIFIED**，不影响其他已证实项目，也不补写历史记录。

“证据先保存、再引用”在最终候选中保留。本轮按现有材料核对最终交接引用及证据落盘时间；非正常中断条件下的行为保证、原生加载、隐式发现和真实事件集成仍不能由这些检查替代。

## 明确未提供

B1 会话提取、完整聊天迁移、原生状态转换、数据库、MCP、服务器、Web UI、后台扫描、事件注册及 CLI 编排均未开发。没有声明所有平台原生加载、无条件自动触发或完整跨平台验证通过。

## English release summary

This release candidate packages the final Phase 1A workflow without new behavior. It adds bilingual usage documentation and consolidates the Phase 1A/1B validation evidence. Phase 1B's 14-test result is tied to verified source hashes; receiver host/session identity and the timing of the pre-edit explanation remain **NOT VERIFIED**. Native loading, implicit selection, and lifecycle integrations remain **NOT RUN**. No session extraction, full-chat migration, CLI orchestration, installation, or public release is included.

参见 [变更清单](CHANGELOG.md) 与 [回滚方法](ROLLBACK.md)。

## DocsFix 2026-10-31（独立副本，等待最终复审）

仅补齐双语安装、卸载、升级、回滚与 FAQ；README.md 为英文，新增 README.zh-CN.md，旧 README.en.md 为兼容入口。协议、模板、触发规则和许可不变。重新计算此副本清单与 ZIP，不覆盖原 RC。新包验证不沿用旧包 PASS。
