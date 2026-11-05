---
name: n-verify
description: >-
  Verify a user-facing change with evidence. Use when asked to confirm a fix,
  finish a feature, or prove a path works. Record commands, screenshots, logs,
  or traces, and keep claims separate from what was actually run. Never mark
  work done or a bug fixed without run evidence.
---

# n-verify

按 [principles.md](../../principles.md) 的 N0 规则做验证。判断留给模型，稳定步骤留给 `tools/` 里的脚本。

## 何时使用

- 要回答「修好了吗」「做完了吗」「这条路径通不通」
- 准备写验证记录，或项目里已有 `N-VERIFY.md`

## 步骤

1. 读项目里的 `N-VERIFY.md` 和功能地图。没有就从 `templates/N-VERIFY.md` 与 `templates/feature-map.md` 复制后再填，不要空口报完成。
2. 启动方式以文件里的命令为准。`tools/` 里如果已有对应脚本，调用脚本，不要另写一套浏览器自动化放进技能正文。
3. 没有脚本时：按文件中的用户路径做一轮可观察检查，记下命令、退出状态和证据路径。然后提议把重复步骤收进 `tools/`，不要在技能里保存一次性脚本。
4. 至少走一条用户路径。代码审阅或单测变绿不能代替这一步。
5. 分栏写下「声称」和「本轮实际执行」。没跑的项目放进「未执行项」。
6. 结论只用 `未开始` / `部分执行` / `已观察`。没有证据路径，就写「待确认」。

## 禁止

- 把「已修改」「测试绿了」「模型认为正确」写成「已验证」或「已修复」。
- 编造命令输出、截图路径或通过记录。
- 在 `tools/` 仍为空时声称已经跑过确定性脚本。
