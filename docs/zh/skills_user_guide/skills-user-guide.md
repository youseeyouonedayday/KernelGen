# KernelGen 技能（Skills）用户指南

本节介绍如何使用 VSCode（及 Copilot）、Claude Code 和 OpenClaw 连接到 KernelGen 算子开发 MCP Toolkit，并使用 KernelGen 技能（Skills）进行算子的通用生成。

有关为 FlagGems 或 vLLM 项目生成算子、优化算子以及跨硬件平台专化算子的使用案例，请参见 [KernelGen Skills 使用案例](../skills_use_case/skills-use-case.md)。

## 前提条件

- Claude Code 2.1 及更高版本

- OpenClaw 2026.3.2 及更高版本

- 已安装并激活 GitHub Copilot 的 VSCode


```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 1
:relative-docs: ..
:relative-images: ../../assets/images
```

## 将 Claude Code 连接到 KernelGen 算子开发 MCP 工具集并加载技能（Skills）

```{include} ../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md
:heading-offset: 2
:relative-docs: ..
:relative-images: ../../assets/images
```

### 配置技能（Skills）

1. 配置 `kernelgen-flagos` 统一技能（Skills），包含所有子技能：
   - **方式一**（推荐）：发送提示词配置 `kernelgen-flagos` 统一技能（Skills），例如：

      ```{code-block} python
      Setup kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos.
      ```

   - **方式二**：使用命令配置

      ```{code-block} shell
      npx skills add flagos-ai/skills --skill kernelgen-flagos -a claude-code
      ```

      ```{note}
      npx 需要 npm 5.2.0 或更高版本。如果未安装 npm 或版本过旧，请运行 `npm -v` 检查当前版本并进行更新。
      ```

      **方式三**：手动配置

      在项目中创建名为 skills 的文件夹并添加技能文件。

      您可以前往 https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos 克隆技能（Skills）。下载技能文件并将其添加到 skills 文件夹中。

      ```{code-block} python
      mkdir -p .claude/skills
      git clone https://github.com/flagos-ai/skills/
      cp -r skills/skills/kernelgen-flagos/ .claude/skills/
      ```

2. 配置技能（Skills）后，使用 **Control+C** 重启 Claude Code。

3. 验证技能（Skills）是否已成功配置：

   {style=lower-alpha}

   1. 方式一：使用提示词：`Please verify if the kernelgen-flagos skills are working correctly.`
   2. 方式二：使用斜杠命令"/"，若列表中显示 kernelgen-flagos，则说明技能（Skills）已安装成功。


## 将 OpenClaw 连接到 KernelGen 算子开发 MCP 工具集并加载技能（Skills）

1. 发送提示词连接到 KernelGen 算子开发 MCP Toolkit，例如：
   - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`
   - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>.`

2. 发送提示词重启 OpenClaw，因为上一步已将 KernelGen 算子开发 MCP 工具集作为 MCP Server 添加到 `openclaw.json` 配置文件中。

3. 发送提示词配置 kernelgen-flagos 统一技能（Skills），包含所有子技能，例如：`Setup kernelgen-flagos skills from <https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos>`。

4. 向 OpenClaw 发送提示词：`Convert the skills to OpenClaw compatible skills and install again`。

## 将 VSCode 和 Github Copilot 连接到 KernelGen 算子开发 MCP 工具集并加载技能（Skills）

1. 发送提示词连接到 KernelGen 算子开发 MCP Toolkit，例如：
   - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`
   - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>.`

2. 启动 KernelGen 算子开发 MCP Toolkit：

    {style=lower-alpha}

   1. 按 **Ctrl+Shift+P** 打开命令面板，输入并搜索"MCP: List Servers"，然后按 Enter 键，查看 VSCode 中当前所有已配置的 MCP Server 及其运行状态。
   2. 选择"kernelgen-mcp"，然后选择"Start Server"。

3. 验证 KernelGen 算子开发 MCP 工具集连接，发送提示词：`Please verify the kernelgen mcp connection is successful.`

4. 发送提示词配置 kernelgen-flagos 统一技能（Skills），包含所有子技能，例如：`Setup kernelgen-flagos skills from <https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos>`。

5. 验证技能（Skills）是否已成功安装：`Please verify if the kernelgen-flagos skills are working correctly.`

6. 发送提示词执行任务，例如生成算子。

## 通用算子生成

生成算子时，典型提示词应包含以下必填项和可选项：算子名称（必填）、任务描述（必填）、输入参数及数据类型、输出参数及数据类型、测试设备，以及算子优化的迭代轮数。

您可以使用以下任一方式调用 `kernelgen-flagos` 技能（Skills）并生成算子：

- **方式一**：使用斜杠命令和提示词

   ```{code-block} shell
   /kernelgen-flagos Generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

- **方式二**：完全使用提示词

   ```{code-block} shell
   Use kernelgen-flagos to generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

有关支持生成算子的硬件平台，请参见[支持的硬件平台](../KernelGen_overview/supported-hardware-platforms.md)。

有关为 FlagGems 或 vLLM 项目生成算子、优化算子以及跨硬件平台专化算子的使用案例，请参见 [KernelGen Skills 使用案例](../skills_use_case/skills-use-case.md)。
