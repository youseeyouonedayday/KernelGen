# 自动调优 Kernel

KernelGen 算子开发 MCP 工具集集成了用于 Kernel 自动调优的 MCP 工具。您只需提供算子的功能描述，KernelGen 便会通过多轮智能迭代，自动生成、验证并持续优化算子实现，最终输出高性能 Triton Kernel 及完整的测试报告。

所有测试设备均支持自动调优 Kernel 功能。请参见[支持的硬件平台](../../KernelGen_overview/KernelGen-overview.md)。您可以通过 AI 智能体调用此工具，支持的智能体包括 VSCode（及 GitHub Copilot）、Cursor、Claude Code 和 OpenClaw。

如果您尚未连接到 KernelGen 算子开发 MCP 工具集，请参见[配置并连接到 KernelGen 算子开发 MCP 工具集](../connect_mcp/connect-mcp.md)。

自动调优 Kernel 时，典型的提示词应包含以下必填和可选要素：

"调用 MCP 工具"（必填）、算子名称（必填）、任务描述（必填）、测试设备、迭代轮数，以及加速比目标。

提示词示例：

```{code-block} shell
调用 MCP 工具，在 MetaX 上迭代生成 rmsnorm 算子。
```

**注意**：

- 若未指定迭代次数，默认使用 3 轮迭代；每轮迭代约需 10 分钟。

- 若未提供加速比目标，默认加速比为 1.2。
