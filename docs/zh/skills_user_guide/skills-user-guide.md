# KernelGen Skills 用户指南

本节介绍如何使用 VS Code（及 Copilot）、Claude Code 和 OpenClaw 连接到 KernelGen 算子开发 MCP 工具集，并使用 KernelGen Skills 生成算子的一般流程。

关于为 FlagGems 或 vLLM 项目生成算子、优化算子以及跨硬件平台特化算子的使用案例，请参见 [KernelGen Skills 使用案例](../skills_use_case/skills-use-case.md)。

## 前提条件

- VS Code 版本须高于 2025 年 3 月发布的 1.99 版本。

- 使用 VS Code 时，请安装 GitHub Copilot 扩展。

- 使用 KernelGen Skills 时，必须连接到 KernelGen 算子开发 MCP 工具集。

```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 1
:relative-docs: ..
:relative-images: ../../assets/images
```

## 连接 VS Code 和 GitHub Copilot 到 KernelGen 算子开发 MCP 工具集并加载Skills

1. 向 Copilot 发送提示词："从 https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos 安装 kernelgen-flagos Skills"。
2. 在对话过程中，允许所有会话请求。
3. 当 `mcp.json` 弹出时，向 Copilot 发送提示词："将Token替换为*你的 Token*"。
4. 启动 KernelGen 算子开发 MCP 工具集：

    {style=lower-alpha}

   1. 按 **Ctrl+Shift+P** 打开命令面板，输入并搜索"MCP: List Servers"，然后按 Enter，即可显示当前在 VS Code 中配置的所有 MCP Server 及其运行状态。
   2. 选择"kernelgen-mcp"并点击"Start Server"。

## 连接 Claude Code 到 KernelGen 算子开发 MCP 工具集并加载Skills

```{include} ../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md
:heading-offset: 2
:relative-docs: ..
:relative-images: ../../assets/images
```

### 安装 Skills

1. 安装 kernelgen-flagos 统一技能：
   - **选项一**：向 Copilot 发送提示词："从 https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos 安装 kernelgen-flagos Skills。"。
   - **选项二**：使用命令来安装技能。
2. 安装 Skills 后，使用 **Control+C** 重启 Claude Code。
3. 使用命令"/"验证Skills是否已安装，若列表中出现 kernelgen-flagos，则说明Skills安装成功。

### npx 环境要求

npx 需要 npm 版本在 5.2.0 或更高。

## 连接 OpenClaw 到 KernelGen 算子开发 MCP 工具集并加载Skills

1. 向 OpenClaw 发送提示词："连接 MCP，其 URL 为 http://kernelgen.flagos.io/sse，Token为*你的 Token*"。

2. 提示 OpenClaw 重启自身，因为上一步已将 KernelGen 算子开发 MCP 工具集作为 MCP Server 添加到 `openclaw.json` 配置文件中。

3. 向 OpenClaw 发送提示词："从 https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos 安装 kernelgen-flagos Skills"。

4. 向 OpenClaw 发送提示词："将 Skills 转换为 OpenClaw 兼容的 Skills 格式，然后重新安装"。

## 一般性生成算子

生成算子时，典型的提示词应包含以下必填和可选要素：算子名称（必填）、任务描述（必填）、输入参数及数据类型、输出参数及数据类型、测试设备，以及算子优化的迭代次数。

您可以使用以下任一方式调用 `kernelgen-flagos` Skills并生成算子：

- **方式一**：使用斜杠命令和提示词

   ```{code-block} shell
   /kernelgen-flagos 生成 ReLU 算子。分类为逐点（pointwise）操作。包含 1 个输入参数：input: torch.Tensor，即输入张量，可以是任意形状和数据类型（通常为浮点型），需要对其应用 ReLU 激活函数。包含 1 个输出：output: torch.Tensor，即经过 ReLU 激活后的输出张量，形状与 input 相同，逻辑为 max(0, input)，即所有负值变为 0，正值保持不变。使用 MetaX。
   ```

- **方式二**：完全使用提示词

   ```{code-block} shell
   使用 kernelgen-flagos 生成 ReLU 算子。分类为逐点（pointwise）操作。包含 1 个输入参数：input: torch.Tensor，即输入张量，可以是任意形状和数据类型（通常为浮点型），需要对其应用 ReLU 激活函数。包含 1 个输出：output: torch.Tensor，即经过 ReLU 激活后的输出张量，形状与 input 相同，逻辑为 max(0, input)，即所有负值变为 0，正值保持不变。使用 MetaX。
   ```

关于可生成算子的硬件平台，请参见[支持的硬件平台](../KernelGen_overview/supported-hardware-platforms.md)。

关于为 FlagGems 或 vLLM 项目生成算子、优化算子以及跨硬件平台特化算子的使用案例，请参见 [KernelGen Skills 使用案例](../skills_use_case/skills-use-case.md)。
