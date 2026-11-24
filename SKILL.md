---
name: debug-agent-tool-calls
description: Use when an AI agent selects the wrong tool, sends invalid arguments, misreads a tool result, or repeats a tool call unexpectedly. 适用于 Agent 工具调用排查。
---

# Agent 工具调用排查

查看一次失败运行中的用户目标、工具定义、实际调用参数和返回。按时间顺序定位第一个有证据的偏差：选错工具、参数不合规、执行失败、结果理解错误或满足停止条件后继续调用。

对照工具定义核实必填字段、类型和允许值。遇到外部操作超时时，先查状态或用模拟结果验证分支。确认工具具备幂等保护后再考虑重放可能已执行的操作。

给出首个偏差、对应记录、最小修正和预期行为。缺少记录时，指出要补哪条日志。展示日志时隐藏凭据和私密字段。

示例：参数 `"limit": "10"` 被拒绝，工具定义要求整数。先修正参数构造为 `"limit": 10`，再用同一输入和模拟工具验证。
