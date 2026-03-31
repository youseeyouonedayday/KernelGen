# KernelGen 技能（Skills）用户指南

本节介绍如何使用 VS Code（及 Copilot）、Claude Code 和 OpenClaw 连接到 KernelGen 算子开发 MCP Toolkit，并使用 KernelGen 技能（Skills）生成算子的一般流程。

关于为 FlagGems 或 vLLM 项目生成算子、优化算子以及跨硬件平台专化算子的使用案例，请参见 [KernelGen 技能使用案例](../skills_use_case/skills-use-case.md)。

## 前提条件

- VS Code 版本须高于 2025 年 3 月发布的 1.99 版本。

- 使用 VS Code 时，请安装 GitHub Copilot 扩展。

- 使用 KernelGen 技能（Skills）时，必须连接到 KernelGen 算子开发 MCP Toolkit。

```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 1
:relative-docs: ..
:relative-images: ../../assets/images
```

## 连接 VS Code 和 GitHub Copilot 到 KernelGen 算子开发 MCP Toolkit 并加载技能

1. 向 Copilot 发送提示词："Install kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos"。
2. 在对话过程中，允许所有会话请求。
3. 当 `mcp.json` 弹出时，向 Copilot 发送提示词："Replace the token with *your token*"。
4. 启动 KernelGen 算子开发 MCP Toolkit：

    {style=lower-alpha}

   1. 按 **Ctrl+Shift+P** 打开命令面板，输入并搜索"MCP: List Servers"，然后按 Enter，即可显示当前在 VS Code 中配置的所有 MCP Server 及其运行状态。
   2. 选择"kernelgen-mcp"并点击"Start Server"。

## 连接 Claude Code 到 KernelGen 算子开发 MCP Toolkit 并加载技能

```{include} ../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md
:heading-offset: 2
:relative-docs: ..
:relative-images: ../../assets/images
```

### 安装技能

1. 向 Copilot 发送提示词："Install kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos"。
2. 安装技能后，使用 **Control+C** 重启 Claude Code。
3. 使用命令"/"验证技能是否已安装，若列表中出现 kernelgen-flagos，则说明技能安装成功。

## 连接 OpenClaw 到 KernelGen 算子开发 MCP Toolkit 并加载技能

1. 向 OpenClaw 发送提示词："Connect to MCP, its url is <http://kernelgen.flagos.io/sse> and token is your token"。

2. 提示 OpenClaw 重启自身，因为上一步已将 KernelGen 算子开发 MCP Toolkit 作为 MCP Server 添加到 `openclaw.json` 配置文件中。

3. 向 OpenClaw 发送提示词："Install kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos"。

4. 向 OpenClaw 发送提示词："Convert the skills to OpenClaw compatible skills and install again"。

## 生成算子

### 一般性生成算子

生成算子时，典型的提示词应包含以下必填和可选要素：算子名称（必填）、任务描述（必填）、输入参数及数据类型、输出参数及数据类型、测试设备，以及算子优化的迭代次数。

您可以使用以下任一方式调用 `kernelgen-flagos` 技能并生成算子：

- **方式一**：使用斜杠命令和提示词

   ```{code-block} shell
   /kernelgen-flagos Generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

- **方式二**：完全使用提示词

   ```{code-block} shell
   Use kernelgen-flagos to generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

关于可生成算子的硬件平台，请参见[支持的硬件平台](../KernelGen_overview/supported-hardware-platforms.md)。

关于为 FlagGems 或 vLLM 项目生成算子、优化算子以及跨硬件平台专化算子的使用案例，请参见 [KernelGen 技能使用案例](../skills_use_case/skills-use-case.md)。
