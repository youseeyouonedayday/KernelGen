# KernelGen Skills User Guide

This section introduces how to use VS Code (and Copilot), Claude Code, and OpenClaw to connect to the KernelGen MCP server and use KernelGen Skills to generate an operator generally.

Regarding generating operators for FlagGems or vLLM project, optimizing operators, specializing operators across hardware platforms, and generating TLE operators, see see [KernelGen Skills Use Cases](../skills_use_case/skills-use-case.md).


## Load skills

### Use VS Code to load skill

#### Prerequisites

- VS Code version should be greater than 1.99 released after March 2025.

- Install the GitHub Copilot extension. During your chat with Copilot, MCP tools are automatically invoked.

#### Steps

```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 4
:relative-docs: ..
:relative-images: ../../assets/images
```

```{include} ../mcp_user_guide/connect_mcp/vscode-connect-mcp.md
:heading-offset: 4
:relative-docs: ..
:relative-images: ../../assets/images
```

##### Install kernelgen-flagos skill

Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) or [SkillHub](https://flagos.io/SkillHub?q=kernelgen&lang=cn).

<!-- cSpell:disable -->

For more information, see [VS Code documentation](https://code.visualstudio.com/docs/copilot/customization/agent-skills).

### Use Claude Code to load skill

#### Steps

```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 4
:relative-docs: ..
:relative-images: ../../assets/images
```

```{include} ../mcp_user_guide/connect_mcp/claudecode-connect-mcp.md
:heading-offset: 4
:relative-docs: ..
:relative-images: ../../assets/images
```

##### Install kernelgen-flagos skill

Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) or [SkillHub](https://flagos.io/SkillHub?q=kernelgen&lang=cn).

- **Option 1**: Quick install via npx

```{code-block} shell
# Install the unified kernelgen skill (includes all sub-skills)
npx skills add flagos-ai/skills --skill kernelgen -a claude-code

# Or install all Flagos skills at once
npx skills add flagos-ai/skills -a claude-code
```

- **Option 2**: Manual install

```{code-block} python
# From your project root
mkdir -p .claude/skills
cp -r <path-to-this-repo>/skills/kernelgen .claude/skills/
```

### Use OpenClaw to load skills

#### Steps

```{include} ../mcp_user_guide/connect_mcp/prerequisites.md
:heading-offset: 4
:relative-docs: ..
:relative-images: ../../assets/images
```


```{include} ../mcp_user_guide/connect_mcp/openclaw-connect-mcp.md
:heading-offset: 4
:relative-docs: ..
:relative-images: ../../assets/images
```

##### Install kernelgen-flagos skill

Prompt to OpenClaw to install the following skills different places:

- McPorter skills created by Peter Steinberger from [ClawHub](https://clawhub.ai/steipete/mcporter)

- `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) or [SkillHub](https://flagos.io/SkillHub?q=kernelgen&lang=cn).

```{note}
You need to prompt to OpenClaw to convert the skill to OpenClaw-compatible skill. 
```

## Generate an operator

A typical prompt should include the following mandatory and optional elements: Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, testing devices, and the number of iterations of operator optimization.

You can use one of the following methods to invoke the `kernelgen-flagos` skill and generate an operator:

- **Option 1**: Use the slash command `/kernelgen-flagos` 

   ```{code-block} shell
   /kernelgen-flagos Generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

- **Option 2**: Completely use prompt

   ```{code-block} python
   Invoke kernelgen-flagos to generate the ReLU operator. The classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use MetaX.
   ```

Regarding generating operators for FlagGems or vLLM project, optimizing operators, specializing operators across hardware platforms, and TLE-related use cases, see [KernelGen Skills Use Cases](../skills_use_case/skills-use-case.md).
