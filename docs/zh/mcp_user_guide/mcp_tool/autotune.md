# 自动调优 Kernel

KernelGen MCP 服务器集成了用于自动调优 Kernel 的 MCP 工具。您只需提供算子的功能描述，KernelGen 即可通过多轮智能迭代，自动生成、验证并持续优化算子实现，最终输出高性能 Triton Kernel 及完整的测试报告。

自动调优 Kernel 功能支持所有测试设备。请参阅[支持的硬件平台](../../KernelGen_overview/KernelGen-overview.md)。您可以通过 AI 智能体调用此工具，支持的智能体包括 VS Code（及 GitHub Copilot）、Cursor、Claude Code 和 OpenClaw。

**前提条件**：请先配置 KernelGen MCP 服务器，参阅[配置并连接 KernelGen MCP 服务器](../connect_mcp/connect-mcp.md)。

**示例**：与 Copilot 对话，描述您对 rmsnorm 算子进行自动调优的需求。

- **典型需求**：包含"调用 MCP 工具"（必填）、算子名称（必填）、任务描述（必填）、测试设备、迭代轮数和目标加速比。

- **需求示例**："**调用 MCP 工具，在 MetaX 上迭代生成 rmsnorm 算子**。"

**注意**：

- 如未指定迭代次数，默认为 3 轮；每轮迭代约需 10 分钟。

- 如未指定目标加速比，默认加速比为 1.2。
