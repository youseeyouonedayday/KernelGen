# 为 FlagGems 或 vLLM 项目生成 Kernel

使用 VS Code（及 Copilot）、Claude Code 或 OpenClaw 为 FlagGems 或 vLLM 项目生成算子，遵循相似的通用流程。

## 步骤

1. 配置 KernelGen MCP 服务器。请参阅[配置并连接 KernelGen MCP 服务器](../mcp_user_guide/connect_mcp/connect-mcp.md)。

2. 从 [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) 下载并安装 `kernelgen-flagos` 技能。

3. 通过以下任一方式调用 `kernelgen-flagos` 技能：

   - 使用斜杠命令 `/kernelgen-flagos`

   - 在提示词中包含技能名称

  有关技能安装方法，请参阅相应文档：

- [VS Code 文档](https://code.visualstudio.com/docs/copilot/customization/agent-skills)

- [Claude Code 文档](https://code.claude.com/docs/en/skills)

- [OpenClaw 文档](https://docs.openclaw.ai/tools/skills)

- 与 AI 智能体对话，描述您生成 ReLU 算子的需求。

  - **典型需求**：算子名称（必填）、任务描述（必填）、输入参数及数据类型、输出参数及数据类型和测试设备。

  - **需求示例**："**生成一个 ReLU 算子**，分类为逐元素（pointwise）。有 1 个输入参数：input: torch.Tensor，输入张量，可以是任意形状和数据类型，通常为浮点类型，需要应用 ReLU 激活函数。有 1 个输出。Output: torch.Tensor，经过 ReLU 激活后的输出张量，形状与输入相同，逻辑为 max(0, input)，即所有负值变为 0，正值保持不变。将算子集成到 FlagGems 中。使用沐曦（MetaX）。"

输出文件将自动提交到 FlagGems 项目。
