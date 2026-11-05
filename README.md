# N stack

Nick 的个人代理工程栈：以证据优先，把反复纠偏收成技能、脚本和仓库约束。

N stack is Nick's personal agent engineering stack: evidence-first verification, skills, and kitchen constraints. It borrows principles discussed around poteto/pstack. It is not a fork, and pull-request count is not the goal.

硬规则见 [principles.md](principles.md)。完整设计见 [N-stack.md](N-stack.md)。

## 分层

| 层 | 名称 | 在本仓库 |
| --- | --- | --- |
| N0 | 证据纪律 | [principles.md](principles.md) |
| N1 | 验证环 | [templates/N-VERIFY.md](templates/N-VERIFY.md)、[skills/n-verify](skills/n-verify/SKILL.md) |
| N2 | 机械工具 | [tools/](tools/)（目前只有占位，没有可执行脚本） |
| N3 | 仓库收窄 | 按具体项目再加，不在这里预写 lint |
| N4 | 技能库 | [skills/](skills/) |
| N5 | 外环 | 尚未自动化 |
| N6 | 权限阶梯 | 本地观察 → 受限改动 → 独立验证 → 云端分支 |

## 怎么开始

1. 先读 [principles.md](principles.md)。没有运行证据，不要写「已完成」或「已修复」。
2. 给一个真实项目复制 [templates/N-VERIFY.md](templates/N-VERIFY.md)，写清启动方式和至少一条用户路径。功能对照表用 [templates/feature-map.md](templates/feature-map.md)。
3. 核验资料时用 [templates/evidence-brief.md](templates/evidence-brief.md)，或按 [n-evidence-brief](skills/n-evidence-brief/SKILL.md) 填写。材料里的报告和这一轮实际执行必须分开。
4. 要从旧对话里找反复纠偏，用 [n-recall-chat](skills/n-recall-chat/SKILL.md)。只根据拿得到的对话，不要编造。
5. 同一类捷径出现第二次：记到 [kitchen-log.md](kitchen-log.md)，优先改环境（lint、类型、脚本、CI），而不是再加一句提醒。

## 现在还没有的东西

- `tools/` 里没有脚本。技能不得假装已经跑过某个不存在的命令。
- `evals/` 里没有失败样本，也没有评分。不要写虚构的通过记录。
- `kitchen-log.md` 还没有抽样。空白表示尚未抽样，不表示产线干净。

许可：[MIT](LICENSE)。
