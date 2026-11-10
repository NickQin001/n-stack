# N stack

Nick 的个人代理工程栈：以证据优先，把反复纠偏收成技能、脚本和仓库约束。

N stack is Nick's personal agent engineering stack: evidence-first verification, skills, and kitchen constraints. It borrows principles discussed around poteto/pstack. It is not a fork, and pull-request count is not the goal.

N0 硬规则见 [principles.md](principles.md)。各 bot 共用前置见 [principles/shared-preamble.md](principles/shared-preamble.md)。完整设计见 [N-stack.md](N-stack.md)。灵感链接见 [docs/references.md](docs/references.md)。跨仓库多 bot 协作见 [docs/multi-bot-repo-collaboration.md](docs/multi-bot-repo-collaboration.md)。

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

B 站学习视频的登录态采集、资料包和长访谈覆盖见 [docs/bilibili-video-skills.md](docs/bilibili-video-skills.md)。这是已批准的职责记录，流水线尚未自动化。

## 工作循环

顺序是 `plan → test → implement → review → verify → remember → improve`。这不是新的一层，而是穿过 N0–N6 的用法。顺序借自 ECC，落点是上面这些层，见 [docs/references.md](docs/references.md)。

| 步骤 | 在这里的意思 | 层 |
| --- | --- | --- |
| plan | 先写用户能观察到的完成标准。工作可以从外环进来，「怎样算做完」由证据纪律决定。 | N5 进料，N0 定完成 |
| test | 改代码前先定检查：怎么启动、哪一条用户路径、什么现象算失败。单测变绿本身不算这条检查。 | N1 |
| implement | 在已有权限内改。稳定步骤进 `tools/`，不在技能里重写一遍。 | N2、N6 |
| review | 把 diff 里的声称和这一轮实际跑过的分开。 | N0 |
| verify | 按路径做一轮，留下命令输出、截图、日志或 trace 的位置。没有位置就保持「待确认」。 | N1、N0 |
| remember | 只记下真实出现过的纠偏，收成技能或厨房日志。对话不在上下文里就不归纳。 | N4 |
| improve | 同一捷径第二次出现，改 lint、类型、脚本或 CI。 | N3 |

专职代理还没建。角色桩在 [agents/README.md](agents/README.md)。

平台内容先核实再入库的职责和交接清单见 [docs/source-knowledge-handoff.md](docs/source-knowledge-handoff.md)。

## 怎么开始

1. 先读 [principles.md](principles.md)。没有运行证据，不要写「已完成」或「已修复」。
2. 给一个真实项目复制 [templates/N-VERIFY.md](templates/N-VERIFY.md)，写清启动方式和至少一条用户路径。功能对照表用 [templates/feature-map.md](templates/feature-map.md)。
3. 核验资料时用 [templates/evidence-brief.md](templates/evidence-brief.md)，或按 [n-evidence-brief](skills/n-evidence-brief/SKILL.md) 填写。材料里的报告和这一轮实际执行必须分开。
4. 要从旧对话里找反复纠偏，用 [n-recall-chat](skills/n-recall-chat/SKILL.md)。只根据拿得到的对话，不要编造。
5. 同一类捷径出现第二次：记到 [kitchen-log.md](kitchen-log.md)，优先改环境（lint、类型、脚本、CI），而不是再加一句提醒。
6. 平台上的视频要先由平台管理员实际获取并核实，再整理、再入库。按 [docs/source-knowledge-handoff.md](docs/source-knowledge-handoff.md) 由主管分步交接。

## 现在还没有的东西

- `tools/` 里没有脚本。技能不得假装已经跑过某个不存在的命令。
- `evals/` 里没有失败样本，也没有评分。不要写虚构的通过记录。
- `kitchen-log.md` 还没有抽样。空白表示尚未抽样，不表示产线干净。
- `agents/` 只有角色桩，没有可运行的代理。
- 平台内容到领域知识库的交接尚未自动化，首次案例也未完成。约定见 [docs/source-knowledge-handoff.md](docs/source-knowledge-handoff.md)。没有获取和读取记录，不能写成已整理或已入库。

许可：[MIT](LICENSE)。
