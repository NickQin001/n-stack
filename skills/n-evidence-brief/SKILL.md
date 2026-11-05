---
name: n-evidence-brief
description: >-
  Turn source material into an evidence brief: dedupe while keeping IDs,
  mark each item as checked, unverified, or claim-only, and split reported
  claims from what was executed this turn. Use for source checking, research
  notes, or when a report must not be treated as a measurement.
---

# n-evidence-brief

把输入整理成简报。格式用 [templates/evidence-brief.md](../../templates/evidence-brief.md)。纪律见 [principles.md](../../principles.md)。

## 何时使用

- 要核对一批材料、链接、笔记或对话摘录
- 有人把旧报告当成已经测过的事实

## 步骤

1. 列出输入。没拿到的材料写「未提供」，不要用常识补成出处。
2. 去重：同一对象合成一行，原始 ID 全部保留。
3. 每行只标一个状态：
   - `已核对`：这一轮对照过原始材料或实际跑过
   - `待确认`：还没核对
   - `仅声称`：只出现在报告、摘要或别人的结论里
4. 「声称 vs 本轮执行」必须分成两列。把报告抄进执行列是错误。
5. 待确认项单独列出，方便下一轮补证据。
6. 看起来像结论、但这一轮没核对的句子，放进「不采用的说法」。

## 禁止

- 因为材料写了「已验证」，就把状态改成 `已核对`。
- 合并条目时丢掉 ID。
- 编造不存在的引用、命令输出或核对过程。
