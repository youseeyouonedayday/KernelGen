# KernelGen Skills User Guide

This section introduces how to use VSCode (and Copilot), Claude Code, and OpenClaw to connect to the KernelGen Operator Development MCP Toolkit and use KernelGen Skills to generate an operator generally.

Regarding generating operators for FlagGems or vLLM project, optimizing operators, and specializing operators across hardware platforms use cases, see [KernelGen Skills Use Cases](../skills_use_case/skills-use-case.md).

## Prerequisites

- Claude Code version 2.1 and later

- OpenClaw version 2026.3.2 and later

- VSCode with Github Copilot activated


```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 1
:relative-docs: ..
:relative-images: ../../assets/images
```

## Connect Claude Code to KernelGen Operator Development MCP Toolkit and load skills

```{include} ../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md
:heading-offset: 2
:relative-docs: ..
:relative-images: ../../assets/images
```

### Setup skills

1. Setup `kernelgen-flagos` unified skill：  
   - **Option 1** (Recommended): Send a prompt to setup the `kernelgen-flagos` unified skill, including all sub-skills, for example:

      ```{code-block} python
      Setup kernelgen-flagos skills from https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos.
      ```

   - **Option 2**: Command setup

      ```{code-block} shell
      npx skills add flagos-ai/skills --skill kernelgen-flagos -a claude-code
      ```

      ```{note}
      npx requires npm version 5.2.0 or higher. If npm is missing or your version is outdated, please run `npm -v` to check your current version and update it.
      ```

      **Option 3**: Manual setup

      Create a folder named skills within your project and add the skill file.

      You can go to https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos to clone the skills. Download this skill file and add it to your skills folder.

      ```{code-block} python
      mkdir -p .claude/skills
      git clone https://github.com/flagos-ai/skills/
      cp -r skills/skills/kernelgen-flagos/ .claude/skills/
      ```

2. After installing skills, restart the Claude Code with **Control+C**.

3. Verify the skills are setup:

   {style=lower-alpha}

   1. Option 1: Use prompt: `Please verify if the kernelgen-flagos skills are working correctly.`
   2. Option 2: Use command "/", if kernelgen-flagos is listed, the skills are installed.


## Connect OpenClaw to KernelGen Operator Development MCP Toolkit and load skills

1. Send a prompt to connect to the KernelGen Operator Development MCP Toolkit, for example:
   - "Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>."
   - "Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>. "

2. Send a prompt to restart OpenClaw, since the previous step adds the KernelGen Operator Development MCP Toolkit as a MCP server to the `openclaw.json` configuration file.

3. Send a prompt to setup the kernelgen-flagos unified skill, including all sub-skills, for example:: "Setup kernelgen-flagos skills from <https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos>".

4. Send a prompt to OpenClaw: "Convert the skills to OpenClaw compatible skills and install again".

## Connect VSCode and Github Copilot to KernelGen Operator Development MCP Toolkit and load skills

1. Send a prompt to connect to the KernelGen Operator Development MCP Toolkit, for example:
   - "Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>."
   - "Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>. "

2. Start KernelGen Operator Development MCP Toolkit:

    {style=lower-alpha}

   1. Press **Ctrl+Shift+P** to open the command palette, type and search for “MCP: List Servers”, then press Enter to display a list of all MCP servers currently configured in VSCode along with their running status.
   2. Select "kernelgen-mcp" and "Start Server".

3. Verify KernelGen Operator Development MCP Toolkit connection, send a prompt “Please verify the kernelgen mcp connection is successful.”

4. Send a prompt to setup the kernelgen-flagos unified skill, including all sub-skills, for example:: "Setup kernelgen-flagos skills from <https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos>".

5. Verify skills are successfully installed: "Please verify if the kernelgen-flagos skills are working correctly."

6. Send a prompt to run a task, for example, generating an operator.

## Generate an operator generally

To generate an operator, a typical prompt should include the following mandatory and optional elements: Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, testing devices, and the number of iterations of operator optimization.

You can use one of the following methods to invoke the `kernelgen-flagos` skill and generate an operator:

- **Option 1**: Use the slash command and prompt

   ```{code-block} shell
   /kernelgen-flagos Generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

- **Option 2**: Completely use prompt

   ```{code-block} shell
   Use kernelgen-flagos to generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

Regarding which hardware platforms you can generate operators for, see [Supported Hardware Platforms](../KernelGen_overview/supported-hardware-platforms.md).

Regarding generating operators for FlagGems or vLLM project, optimizing operators, and specializing operators across hardware platforms use cases, see [KernelGen Skills Use Cases](../skills_use_case/skills-use-case.md).
