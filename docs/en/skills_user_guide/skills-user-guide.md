# KernelGen Skills User Guide

This section introduces how to use VS Code (and Copilot), Claude Code, and OpenClaw to connect to the KernelGen Operator Development MCP Toolkit and use KernelGen Skills to generate an operator generally.

Regarding generating operators for FlagGems or vLLM project, optimizing operators, specializing operators across hardware platforms, and generating TLE operators, see see [KernelGen Skills Use Cases](../skills_use_case/skills-use-case.md).

## Prerequisites

- VS Code version should be greater than 1.99 released after March 2025.

- Install the GitHub Copilot extension. During your chat with Copilot, MCP tools are automatically invoked.

- When using KernelGen skills, you must connect to the KernelGen Operator Development MCP Toolkit.

```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 1
:relative-docs: ..
:relative-images: ../../assets/images
```

## Connect to KernelGen Operator Development MCP Toolkit and load skills

Depending on the selected AI agent, the steps may vary.

### Connect VS Code and Github Copilot to KernelGen Operator Development MCP Toolkit and load skills

1. Prompt to Copilot: "Install kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos".
2. Allow all the sessions during the chat.
3. When the `mcp.json` pops up, prompt to Copilot: “Replace the token with the your token”.
4. Start KernelGen Operator Development MCP Toolkit:
   {style=lower-alpha}
   1. Press **Ctrl+Shift+P** to open the command palette, type and search for “MCP: List Servers”, then press Enter to display a list of all MCP servers currently configured in VS Code along with their running status.
   2. Select "kernelgen-mcp" and "Start Server".

### Connect Claude Code to KernelGen Operator Development MCP Toolkit and load skills

```{include} ../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md
:heading-offset: 3
:relative-docs: ..
:relative-images: ../../assets/images
```

#### Install skills

1. Prompt to Copilot: "Install kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos".
2. After installing skills, restart the Claude Code with **Control+C**.
3. Verify the skills are installed using command "/", if kernelgen-flagos listed, the skills are installed.

### Connect OpenClaw to KernelGen Operator Development MCP Toolkit and load skills

1. Prompt to OpenClaw: "Connect to MCP, its url is <http://kernelgen.flagos.io/sse> and token is your token ".

2. Prompt to OpenClaw to restart itself, since the previous step adds the KernelGen Operator Development MCP Toolkit as a MCP server to the `openclaw.json configuration file.

3. Prompt to OpenClaw: "Install kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos".

4. Prompt to OpenClaw: "Convert the skills to OpenClaw compatible skills".

## Generate an operator

To generate an operator, a typical prompt should include the following mandatory and optional elements: Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, testing devices, and the number of iterations of operator optimization.

You can use one of the following methods to invoke the `kernelgen-flagos` skill and generate an operator:

- **Option 1**: Use the slash command `/kernelgen-flagos`

   ```{code-block} shell
   /kernelgen-flagos Generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

- **Option 2**: Completely use prompt

   ```{code-block} shell
   Use kernelgen-flagos to generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

Regarding generating operators for FlagGems or vLLM project, optimizing operators, specializing operators across hardware platforms, and TLE-related use cases, see [KernelGen Skills Use Cases](../skills_use_case/skills-use-case.md).
