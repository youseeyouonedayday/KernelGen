# Generate a kernel for FlagGems or vLLM project

Using VS Code (and Copilot), Claude Code, or OpenClaw to generate an operator for the FlagGems or vLLM project follows a similar general process.

1. Configure the KernelGen MCP server. See [Configure and connect to KernelGen MCP server](https://file+.vscode-resource.vscode-cdn.net/d:/kernelgen20/docs/en/mcp_user_guide/connect_mcp/connect-mcp.md).

2. Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos).

3. Invoke the `kernelgen-flagos` skill through one of the following methods:

   - Use the slash command `/kernelgen-flagos`

   - Include the name in your prompt

 For skill installation, see the corresponding documentation:

- [VS Code documentation](https://code.visualstudio.com/docs/copilot/customization/agent-skills)
- [Claude Code documentation](https://code.claude.com/docs/en/skills)
- [OpenClaw documentation](https://docs.openclaw.ai/tools/skills)

- Chat with the AI agent about your requirements for generating the ReLU operator.

  - **Typical requirements**: Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, and testing devices.

  - **Requirement example**: "**Generate a ReLU operator**, and the classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Integrate the operator into FlagGems. Use MetaX. "

  The output files will be automatically submitted to the FlagGems project.