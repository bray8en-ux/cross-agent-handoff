> DocsFix 2026-10-31：以下为原 RC 的历史合并验收；其中 15 文件/41 链接等数字仅适用于原包，不自动成为文档修复包的新验收。README.md 现为英文，README.zh-CN.md 为中文，README.en.md 保留兼容入口。新包检查由本次独立交付的 INSTALLATION_VALIDATION.md / DOCS_FIX_REPORT.md 给出；历史 NOT VERIFIED / NOT RUN 不变。

# Phase 1A + Phase 1B 合并验收报告

版本：**v0.2.0-rc.1**。收口日期：2026-10-31，Asia/Tokyo。

**结论：READY FOR HUMAN REVIEW — WITH LIMITATIONS。** A 默认交接增强可提交人工验收；不等于完整跨宿主、所有平台或自动事件验证通过。已有功能证据与会话身份/时序证明分别评价，不因后两者缺口否定已通过测试，也不把缺口推断为 PASS。

本文是版本验收报告，不是测试项目的新状态入口。项目当前事实仍保存在各自唯一的 HANDOFF.md。原始材料保留原位；本地 RC 审计目录另有 29 份逐字节归档快照、来源/哈希索引和本轮检查输出。分发 ZIP 不含这些带本机路径的原始材料，也不包含私有会话。

## 状态含义

- **PASS**：该项有实际源码、命令结果、哈希、可读文件或其他对应证据支持；范围只到该项。
- **NOT VERIFIED**：已有叙述或报告，但缺少能独立核实该主张的证据。
- **NOT RUN**：未执行该种检查或场景。原记录的 `NOT_RUN` 与此写法含义相同。
- **FAIL（历史尝试）**：真实发生过的失败，不混同当前修复后实现的状态。

用户已确认：Phase 1B 没有额外保存接收会话准确 ID 或独立的修改前理解文件；按现有证据收口，不重做跨宿主流程、不补写历史。本报告采用此口径。

## 分项结果

| 项目 | 结论 | 实际证据与边界 |
| --- | --- | --- |
| Phase 1A 交出 | PASS | Decimal 加法，5 项测试通过；float 实验实际退出 1，并保留错误与哈希 |
| Phase 1A 独立上下文接续 | PASS，限定同一 Codex 宿主体系 | `fork_turns=none` 派发记录、修改前理解、现场检查及受测哈希；实现 multiply 后 10 项通过；不是 Claude 跨宿主验证 |
| Phase 1A 决策/失败经验继承 | PASS，限该案例 | 修改前理解正确解释 Decimal 理由、float 失败、未决显示问题和唯一下一步；理解文件哈希与接收测试记录一致 |
| Phase 1A 手动意图/负向边界 | PASS，8/8 可观察案例 | 显式提供 Skill 后的案例产物；不是原生隐式选择率或 8 个独立宿主会话 |
| Phase 1A 接收端自收尾 | 有已记录缺陷 | 控制回合额度中断，曾引用不存在的 receiver-closeout；原主控以真实 parent-closeout 修正，未伪造缺失文件 |
| Phase 1B 交出 | PASS | CSV 读取层 9 项通过；直接 split 的初版真实报 ValueError、退出 1；有失败源码与日志 |
| Phase 1B 接续产物与功能 | PASS | stock_totals 已实现；日志包含 9 项读取回归和 5 项汇总测试，14/14、exit 0；三份受测文件哈希与现场一致 |
| Phase 1B 实际宿主、会话独立性 | **NOT VERIFIED** | 最终 HANDOFF 自述“Claude Code 桌面独立会话”；无可独立核实的会话 ID/原始会话材料，不能单凭事后文字确认为通过 |
| Phase 1B 修改前理解及先后时序 | **NOT VERIFIED** | 既有报告及用户说明表示修改前曾回答五问；无独立保存的修改前记录或可定位时序证据，不追补历史证明 |
| Phase 1B 最终 HANDOFF 与引用 | PASS，限定文件可核验部分 | 状态为范围内无剩余开发任务，保留 BOM 导出策略未决问题；13 个本地 Markdown 引用均存在；“接收端会话记录”这一未定位来源仍属上述证明缺口 |
| Phase 1A 最终 HANDOFF 引用 | PASS | 17 个本地 Markdown 引用均存在；原始错误快照仍按历史材料保留，不伪装成当前入口 |
| RC 复核 Phase 1B 代码 | PASS | 在逐字节隔离副本运行相同 unittest 命令，14/14、exit 0；没有在原项目写文件，也不代表重新完成跨宿主验收 |
| RC 格式、Skill 结构、本地链接、哈希、隐私模式与 ZIP 内容 | PASS，限定静态/打包检查 | 官方 quick_validate、UTF-8、模板/引用结构、清单覆盖、压缩内容逐文件比对；不替代宿主行为验收 |
| RC / V0.2 原生 Skill 安装与加载 | **NOT RUN** | 显式读取候选文件不等于原生调用已加载 |
| 隐式选择稳定性、真实生命周期事件、跨设备、其他平台逐一实测 | **NOT RUN** | 没有事件回执，没有逐平台执行记录 |

## Phase 1A 实测关联

原命令：`python -B -X utf8 -m unittest -v test_calculator.py`。接收端测试开始于 2026-10-29 15:22:13 +09:00，10 项通过、exit 0；原主控之后曾独立复跑通过。本次不再重复整个 Phase 1A。

| 受测文件 | SHA256 |
| --- | --- |
| `calculator.py` | `72dc39c09228c06faa4291d0f6abfd458e24190e5481910a454cb8b77f017437` |
| `test_calculator.py` | `d04a33eda87ad79054d7c79ac8684e6fb4f068de3a3fa2b17ab5f724fd0f2c99` |
| 修改前 `receiver-understanding.md` | `81e677bc1547af59832688ca0f264a5f93993cc38729c4d5860bf745de3c5fbc` |
| `receiver-tests.txt` 原始日志 | `0308ffd3366f0d2d702599c860f460dc678d035141b4fa5bf06d02518621f887` |

原始证据标识包括 `AGENT_DISPATCH.json`、`receiver-field-check.json`、`receiver-tests.json` 与 `RECEIVER_AUDIT.json`，均在本地归档索引中登记。这些名称是包外证据标识，不是声称本 ZIP 内有同名文件的导航链接。

## Phase 1B 的 14 项测试与哈希

原命令：`python -B -X utf8 -m unittest -v test_inventory.py`。

原记录：2026-10-31 11:03:39.595003 至 11:03:39.726318 +09:00，Python 3.12.10，**14/14 PASS，exit 0**。覆盖现有读取校验，以及新增汇总的空输入、有符号合计、文本 SKU 区别、净零保留与生成器输入。

| 受测文件 | SHA256 |
| --- | --- |
| `inventory.py` | `03dfb791945caded928c441d1915f88e5848fe6b1a1a69f744a751b9d8d8d38a` |
| `test_inventory.py` | `30ee3247f790e09165392d39c7e9ee1881a4306a0fa198fc8f32539ef03710c4` |
| `fixtures/movements.csv` | `11a34ff429bbc33ea686145af05bd5d98b26d3abedf4e36ca6bd9875b66bced5` |
| `evidence/receiver-tests.txt` 原始日志 | `26859c4bae328240ddfe8d445988b5637cd5f484107d202fcf2bd8f78825acfc` |

本轮核对三份受测文件与日志完全一致，隔离副本复跑也是 14/14。样本、旧测试日志、失败源码/日志、旧 Git 记录和 .gitignore 与交出端保存的哈希一致。现有项目 Git 为 `main`、unborn HEAD、无暂存/远程，10 个项目文件未跟踪；没有将空 diff 当作干净状态。

最终 HANDOFF 仍保留“未来导出 CSV 时是否需要 UTF-8 BOM”的未决问题，不把读取端支持 BOM 推成输出策略已定，也不启动导出开发。接收端新实现与测试已经是事实；宿主身份及修改前五问的时序则没有因这些事实而自动得到证明。

## 证据先保存、再引用：本轮回归与剩余风险

Phase 1A 最终候选相对当时独立前向测试所读的 Skill，只多出这条窄规则；原来的独立回归缺口依旧如实保留为 **NOT RUN**，不会把今天的静态核对改写成当时已测试。

本次执行限定回归：

1. 核对规则确实存在，RC 的 Skill 除版本文字外与 Phase 1A 最终版一致，质量清单保持原字节。
2. 核对两项目现行 HANDOFF 的全部本地 Markdown 引用，共 30 个，未发现悬空引用。Phase 1B 的 receiver-tests 已有真实文件、原始结果及适用代码哈希，没有补造“计划中的收尾文件”。
3. 对照保存的时间与现行文件元数据：Phase 1B 测试证据文件早于最终 HANDOFF 写入，符合先保存证据的预期。文件时间不等于经过认证的会话操作轨迹，不能证明会话独立性或完整执行顺序。
4. RC 示例已明确“未附日志的虚构材料不能作为证据”，不再列出看似已落盘的示例证据占位路径。分发包的实际 Markdown 导航链接均检查真实存在。

**剩余风险：** 本包是模型工作流，不是强制落盘事务执行器；不能保证任意 Agent 在断电、额度中断或其他异常中断下都不会提前引用计划文件。异常中断行为、最后窄规则的新独立前向验证仍为 **NOT RUN**。原 Phase 1A 自收尾缺陷未被隐藏。用户要求按现有证据收口后，额外前向案例停止，残留材料保留且不计通过项；没有重新执行整个 Phase 1B。

## 已知限制与未提供范围

- 短任务可能生成偏长的交接，接收方也可能因材料确认而多等待；Phase 1A 已记录该使用风险。
- 测试只证明指定的有限十进制与虚构 CSV 场景，不代表任意输入、无限精度、显示或导出策略已经验证。
- 明确意图触发、宿主语义选择、真实生命周期事件是不同层次；本包没有事件注册、后台持续扫描或其他会话监控。
- B1 会话提取、完整聊天/原生状态迁移、CLI 编排、数据库、MCP、服务器和 Web UI 均未实现，也未为其增加抽象框架。
- 包内隐私检查是公开文件清单审阅加本机路径/常见凭据模式检查，不能承诺识别所有敏感信息。原始项目、日志和会话不进入分发 ZIP。
- 人工安装、真实宿主加载、自动安装/回退运行与 GitHub Release：**NOT RUN**。本次也没有授权或执行这些动作。

## 保护基线、回滚与停止

V0.1 正式目录及冻结 ZIP、Phase 1A 整体目录、Phase 1B 整体目录在本次修改前记录文件清单、SHA256、大小和修改时间，交付前再次逐项比较。RC 在独立目录整理，不改写旧候选、项目或原始证据。

本包两份 LICENSE、.gitignore、模板、质量清单和平台流程相对 Phase 1A 最终候选保持字节一致；Skill 只调整版本标识。实际变化见 [CHANGELOG.md](CHANGELOG.md)，[RELEASE_NOTES.md](RELEASE_NOTES.md) 描述发布边界，[ROLLBACK.md](ROLLBACK.md) 提供回退方法。

交付后停止，等待人工验收。不替换 V0.1、不发布 GitHub、不进入 B1。


## README positioning and diagrams update (2026-10-31)

After the DocsFix package audit, the two user-facing README files received a documentation-only presentation update for GitHub publication:

- `README.md` and `README.zh-CN.md` now explain the project's positioning and non-goals.
- Both contain two GitHub-rendered Mermaid diagrams: the agent handoff loop and the information preserved by the handoff.
- Both include copyable handoff/resume prompts and an anonymized desktop-companion example.
- Wording now explicitly says to reuse an existing project state document (for example `CURRENT_STATE.md`) rather than creating a parallel `HANDOFF.md`.
- `CHANGELOG.md` records this documentation-only update.

No Skill instructions, templates, platform references, runtime behavior, or validation claims were changed. The existing NOT VERIFIED / NOT RUN limitations above remain unchanged. This update does not add native host-loading or cross-platform execution evidence.
