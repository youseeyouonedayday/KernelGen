# KernelGen Skills 用户指南

本节介绍如何使用 VS Code（及 Copilot）、Claude Code 和 OpenClaw 连接 KernelGen MCP Server，并使用 KernelGen Skills 进行通用算子生成。

有关为 FlagGems 或 vLLM 项目生成算子、优化算子、跨硬件平台特化算子以及生成 TLE 算子的内容，请参阅《KernelGen Skills 使用案例》。

## 通用算子生成

本节介绍如何使用 VS Code（及 GitHub Copilot）、Claude Code 和 OpenClaw 进行通用 ReLU 算子生成。

### 加载技能（Skills）

#### 使用 VS Code 加载技能

##### 前提条件

- VS Code 版本需高于 2025 年 3 月发布的 1.99 版本。

- 安装 GitHub Copilot 扩展。在与 Copilot 对话时，MCP 工具将自动调用。

##### 步骤

1. 配置 KernelGen MCP Server。请参阅[使用 VS Code 连接 KernelGen MCP Server](../mcp_user_guide/connect_mcp/vscode-connect-mcp.md)。

2. 从 [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) 下载并安装 `kernelgen-flagos` 技能。有关技能安装方法，请参阅 [VS Code 文档](https://code.visualstudio.com/docs/copilot/customization/agent-skills)。

#### 使用 Claude Code 加载技能

##### 步骤

1. 配置 KernelGen MCP Server。请参阅[使用 Claude Code 连接 KernelGen MCP Server](../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md)。

2. 从 [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) 下载并安装 `kernelgen-flagos` 技能。有关技能安装方法，请参阅 [Claude Code 文档](https://code.claude.com/docs/en/skills)。

#### 使用 OpenClaw 加载技能

##### 步骤

1. 配置 KernelGen MCP Server。请参阅[使用 OpenClaw 连接 KernelGen MCP Server](../mcp_user_guide/connect_mcp/openclaw-connect-mcp.md)。

2. 下载并安装以下技能：

   - 从 [ClawHub](https://clawhub.ai/steipete/mcporter) 获取由 Peter Steinberger 创建的 McPorter 技能

   - 从 [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) 获取 `kernelgen-flagos` 技能

   有关技能安装方法，请参阅 [OpenClaw 文档](https://docs.openclaw.ai/tools/skills)。

### 生成算子

1. 通过以下任一方式调用 `kernelgen-flagos` 技能：

   - 使用斜杠命令 `/kernelgen-flagos`

   - 在提示词中包含技能名称

2. 与 OpenClaw 对话，通过自然语言描述生成 ReLU 算子的需求。

   - **典型需求**：算子名称（必填）、任务描述（必填）、输入参数及数据类型、输出参数及数据类型、测试设备和算子优化迭代次数。

   - **需求示例**："**算子名称为 ReLU**，分类为逐元素（pointwise）。有 1 个输入参数：input: torch.Tensor，输入张量，可以是任意形状和数据类型，通常为浮点类型，需要应用 ReLU 激活函数。有 1 个输出。Output: torch.Tensor，经过 ReLU 激活后的输出张量，形状与输入相同，逻辑为 max(0, input)，即所有负值变为 0，正值保持不变。使用沐曦（MetaX）。"

有关为 FlagGems 或 vLLM 项目生成算子、优化算子、跨硬件平台特化算子以及 TLE 相关使用案例，请参阅《KernelGen Skills 使用案例》。

```{toctree}
:maxdepth: 2


configure-and-connect-mcp.md
generate-ops-generally.md


```
