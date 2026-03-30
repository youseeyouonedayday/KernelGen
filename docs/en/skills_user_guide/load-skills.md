# Load skills

## Use VS Code to load skill

### Prerequisites

- VS Code version should be greater than 1.99 released after March 2025.

- Install the GitHub Copilot extension. During your chat with Copilot, MCP tools are automatically invoked.

### Steps

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

#### Install kernelgen-flagos skill

Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) or [SkillHub](https://flagos.io/SkillHub?q=kernelgen&lang=cn).

<!-- cSpell:disable -->

For more information, see [VS Code documentation](https://code.visualstudio.com/docs/copilot/customization/agent-skills).

## Use Claude Code to load skill

### Steps

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

#### Install kernelgen-flagos skill

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

## Use OpenClaw to load skills

### Steps

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

#### Install kernelgen-flagos skill

Prompt to OpenClaw to install the following skills different places:

- McPorter skills created by Peter Steinberger from [ClawHub](https://clawhub.ai/steipete/mcporter)

- `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos) or [SkillHub](https://flagos.io/SkillHub?q=kernelgen&lang=cn).

```{note}
You need to prompt to OpenClaw to convert the skill to OpenClaw-compatible skill. 
```
