# Optimize an operator

You can use either VS Code (and Copilot), Claude Code, or OpenClaw to optimize operators on NVIDIA.

## Steps

Chat with the AI agent to optimize the operator：

1. Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos).

2. Invoke the `kernelgen-flagos` skill through one of the following methods:

   * Use the slash command `/kernelgen-flagos`

   * Include the name in your prompt

    For skill installation, see the corresponding documentation:

* [VS Code documentation](https://code.visualstudio.com/docs/copilot/customization/agent-skills)

* [Claude Code documentation](https://code.claude.com/docs/en/skills)

* [OpenClaw documentation](https://docs.openclaw.ai/tools/skills)

3. Chat with the AI agent to optimize the operator and include the number of iterations of operator optimization in the prompts.

   * **Typical requirements**: Operator name（mandatory）, task description (mandatory), and optimization iterations.

   * **Requirement example**: "**Optimize the index\_put operator. Optimize 5 iterations**."
