# Autotune Kernel

KernelGen Operator Development MCP Toolkit integrates an MCP tool for autotuning Kernels. You only need to provide a functional description of the operator. Through multiple rounds of intelligent iteration, the KernelGen automatically generates, verifies, and continuously optimizes the operator implementation, ultimately delivering a high-performance Triton Kernel along with a complete test report.

The autotune kernel function is supported on all testing devices. See [Supported Hardware Platforms](../../KernelGen_overview/KernelGen-overview.md). You can invoke this tool through AI agents, including VS Code (and Github Copilot), Cursor, Claude Code, and OpenClaw.

If you haven’t connected to the KernelGen Operator Development MCP Toolkit, see [Configure and connect to KernelGen Operator Development MCP Toolkit](../connect_mcp/connect-mcp.md).

To autotune kernels, a typical prompt should include the following mandatory and optional elements:

“Invoke MCP tools” (mandatory), operator name（mandatory）, task description (mandatory), testing device, the number of rounds of iterations, and speedup ratio.

Prompt example:

```{code-block} shell
Invoke MCP tools to iteratively generate the rmsnorm operator on MetaX.
```

**Note**:

- If the number of iterations is not specified, a default of 3 rounds will be used; each iteration takes approximately 10 minutes.

- If no speedup target is provided, a default speedup ratio of 1.2 will be assumed.
