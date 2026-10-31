# 回滚方法

## 本次交付

RC 目录和 ZIP 独立保存。V0.1 正式目录、冻结 ZIP、Phase 1A 候选、Phase 1B 项目和原始证据均未被覆盖。本轮没有安装、修改宿主入口、暂存/提交、推送或创建 GitHub Release，因此无需对原环境执行回滚操作。

继续使用原 V0.1 正式目录即可，不需要删除 RC 或测试材料。保留原冻结 ZIP：`cross-agent-handoff-v0.1.0.zip`，SHA256 为：

```text
ad9a568f2f4c2282368eb5f21b55da0cc68e65da11ca9c66bf53de801c8bf35f
```

## 以后人工安装 RC 后需要回退时

1. 先核对实际安装位置和是否存在其他会话修改；保留当前安装及项目文件。
2. 使用安装前保留的 V0.1 完整 Skill 副本恢复原入口；不要只换 SKILL.md 而遗漏配套资源，也不要覆盖来源不明的改动。
3. 在实际宿主的新会话确认它加载的是预期版本；文件恢复与宿主加载分别验证。

以上是人工回退说明，本轮未执行安装或宿主回退。项目 HANDOFF.md 和真实工作文件不因回退 Skill 自动降级或删除，Phase 1A/1B 测试材料继续保留。未进行自动安装/回退的运行验证，记为 NOT RUN。

English: this delivery does not change the existing installation. Keep using V0.1 to opt out of the RC. If the RC is manually installed later, preserve its current files, restore the pre-install V0.1 skill copy at the verified installation path, and verify loading in a new host session. Do not delete project handoffs or test evidence.
