---
name: n-recall-chat
description: >-
  Mine conversations that are actually in context for repeated corrections,
  missing background, and steps a person had to take over. Propose a skill,
  script, or environment constraint. Use when starting or updating a skill,
  or when the same shortcut shows up again. Do not invent chat history.
---

# n-recall-chat

从拿得到的旧对话里捞反复出现的纠偏，决定是写成技能，还是收成环境约束。对应 [principles.md](../../principles.md) 第三条。

## 何时使用

- 要新建或修改一个技能
- 同一类错误又出现了，需要决定改 prompt 还是改环境
- 用户指出代理又漏了背景、又要人接手操作

## 步骤

1. 只使用当前上下文里真实存在的对话、摘录或文件。没有对话就写「未提供」，停止归纳，不要虚构以往纠正过什么。
2. 标出三类原句或原步骤（带可回指的位置，例如消息顺序或文件名）：
   - 反复纠正
   - 用户被迫补充的背景
   - 用户亲手接手的操作
3. 合并相同模式，并数出现次数。次数数不清就写「待确认」，不要估一个好看的数字。
4. 对每个模式给一个处置，三选一：
   - 改技能（判断标准、何时调用）
   - 改环境（lint、类型、CI、目录约定）
   - 收成 `tools/` 脚本（步骤稳定、不需要再判断）
5. 同一捷径达到第二次：优先改环境或脚本，而不是再加一句提醒。提议要具体到文件或规则名；做不到就标「待确认」。
6. 若本仓库有 [kitchen-log.md](../../kitchen-log.md)，只在用户要求记录、或已经有可引用证据时追加一行。不要预填抽样结论。

## 输出

| 模式 | 证据位置 | 次数 | 建议处置 | 状态 |
| --- | --- | --- | --- | --- |
|  |  | 待确认 |  | 待确认 |

## 禁止

- 编造「上次你说过」。
- 把一次偶发口误升格成硬规则。
- 在没有对话文本时输出一份看起来完整的回顾。
