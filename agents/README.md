# 代理占位

以后如果需要专职代理，角色说明放在这里。现在没有代理定义、提示词或调度器。下表只是桩，表示「以后可能有人干这件事」，不是已经在跑的团队。

B 站学习视频的当前实例不写入下面的桩表。B 站管理员使用技能 `b`（登录态采集与核实）；视频知识整理使用 `b-2`（资料包与总结）和 `skill-1794213476980`（长访谈完整覆盖）。这些是 Grok Bot 工作流产品 id，可能变更。音频转写未单独成技能。说明见 [docs/bilibili-video-skills.md](../docs/bilibili-video-skills.md)。

不要按别的仓库的代理名单来填。本页不收录成套角色，也不从 ECC 或其他上游复制代理。

| 角色 | 以后做什么 | 服从 | 状态 |
| --- | --- | --- | --- |
| evidence-brief coordinator | 收齐输入、去重并保留 ID，按简报模板分出「仅声称 / 待确认 / 已核对」 | N0、[n-evidence-brief](../skills/n-evidence-brief/SKILL.md) | 未实现 |
| path verifier | 按项目的 `N-VERIFY` 走一条用户路径，写下证据位置 | N0、N1、[n-verify](../skills/n-verify/SKILL.md) | 未实现 |
| recall miner | 只从当前上下文里的对话提炼反复纠偏 | N4、[n-recall-chat](../skills/n-recall-chat/SKILL.md) | 未实现 |
| kitchen sampler | 把抽样看到的捷径记进厨房日志，并指出要改的规则或脚本 | N3、[kitchen-log.md](../kitchen-log.md) | 未实现 |

未实现的意思是：没有独立代理，相关判断仍由正在做事的那一个代理按技能和模板完成。没有证据时，这些角色也不能把结论写成已核对或已验证。

平台内容经核实后交接入库的职责和清单见 [docs/source-knowledge-handoff.md](../docs/source-knowledge-handoff.md)。当前 bot 名作为实例写在那一页。本表仍是上面四行未实现的桩。
