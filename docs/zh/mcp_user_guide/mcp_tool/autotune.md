# 自动调优 Kernel

KernelGen 算子开发 MCP 工具集集成了用于自动调优 Kernel 的 MCP 工具。您只需提供算子的功能描述，KernelGen 即可通过多轮智能迭代自动生成、验证并持续优化算子实现，最终交付高性能 Triton Kernel 及完整的测试报告。

所有测试设备均支持自动调优 Kernel 功能。请参见[支持的硬件平台](../../KernelGen_overview/KernelGen-overview.md)。您可以通过 AI 智能体调用此工具，包括 VSCode（及 Github Copilot）、Cursor、Claude Code 和 OpenClaw。

如果尚未连接到 KernelGen 算子开发 MCP Toolkit，请参见[配置并连接到 KernelGen 算子开发 MCP Toolkit](../connect_mcp/connect-mcp.md)。

自动调优 Kernel 时，典型提示词应包含必填项和可选项。详细信息请参见自动调优模板。


## 自动调优模板

```{code-block} shell
Call the MCP tool to iteratively generate the **[operator name]** operator on **[target device]**.
Task description: [Detailed description of the operator's functionality, inputs/outputs, and constraints]
- Iterations: [N]
- Speedup target: [X]
```

### 必填项

1. `调用 KernelGen MCP 工具`
2. 算子名称
3. 任务描述

### 可选项（推荐填写）

1. 目标设备（例如：沐曦（MetaX）、GPU 型号等）
2. 迭代轮数（默认：3 轮，每轮约 10 分钟）
3. 加速比目标（默认：1.2×）


## 自动调优示例

### 示例一 — 基础

```{code-block} shell
Call the KernelGen MCP tool to iteratively generate the **rmsnorm** operator on MetaX.
Task description: Implement RMSNorm with an input tensor of shape `(batch, hidden_size)` and produce the normalized output.
Use defaults:
- Iterations = 3
- Speedup target = 1.2×
```


### 示例二 — 推荐

```{code-block} shell
Call the KernelGen MCP tool to iteratively generate the **rmsnorm** operator on MetaX.
Task description: Implement an RMSNorm operator supporting both float16 and float32 inputs, with input shape `(batch, hidden_size)`. Numerical stability and parallel optimization should be considered.
Iterations: 5
Speedup target: 1.5×
```

### 示例三 — 高级（生产级别）

```{code-block} shell
Call the KernelGen MCP tool to iteratively generate a **fused softmax** operator on an **NVIDIA GPU**.
Task description: Implement a fused softmax with masking. The input is an attention score tensor of shape `(batch, head, seq_len, seq_len)`. The goal is to minimize memory access and maximize throughput.
Iterations: 6
Speedup target: 2.0×
```

### 获得更佳结果的技巧

任务描述越具体，自动调优效果越好。

**建议指定：**

- 数据类型：`fp16` / `bf16` / `fp32`
- 张量形状
- 是否需要算子融合
- 性能瓶颈：访存密集型还是计算密集型

**避免：**

- 模糊描述，如"实现一个算子"
- 省略输入/输出规格
