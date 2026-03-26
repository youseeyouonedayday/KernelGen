# Generate an operator generally

This section introduces how to use VS Code (and GitHub Copilot), Claude Code, and OpenClaw to generate an operator.

Regarding generating operators for FlagGems or vLLM project, optimizing operators, specializing operators across hardware platforms, and TLE-related use cases, see *KernelGen Skills Use Cases*.

## Use VS Code to generate an operator

This section introduces how to use VS Code, KernelGen MCP server, and KernelGen Skills to generate the ReLU operator.

### **Prerequisites**

* VS Code version should be greater than 1.99 released after March 2025.

* Install the GitHub Copilot extension. During your chat with Copilot, MCP tools are automatically invoked.

### **Steps**

1. Configure the KernelGen MCP server. See [Use VS Code to connect to KernelGen MCP server](https://file+.vscode-resource.vscode-cdn.net/d:/kernelgen20/docs/en/mcp_user_guide/connect_mcp/vscode-connect-mcp.md).

2. Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos). For skill installation, see [VS Code documentation](https://code.visualstudio.com/docs/copilot/customization/agent-skills).

3. Invoke the `kernelgen-flagos` skill through one of the following methods:

   * Use the slash command `/kernelgen-flagos`&#x20;

   * Include the name in your prompt

4. Chat with Copilot about your requirements for generating the ReLU operator.

   * **Typical requirements**: “Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, testing devices, and optimization iterations.

   * **Requirement example**: "**Generate a ReLU operator.&#x20;**&#x54;he classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. **Use Tsingmicro**. **Optimize 5 iterations**."

## Use Claude Code to generate an operator

This section introduces how to use Claude Code, KernelGen MCP server, and KernelGen Skills to generate the ReLU operator.

### Steps

1. Configure the KernelGen MCP server. See [Use Claude Code to connect to KernelGen MCP server](https://file+.vscode-resource.vscode-cdn.net/d:/kernelgen20/docs/en/mcp_user_guide/connect_mcp/claudecode-connect-mcp.md).

2. Download and install the `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos). For skill installation,  see [Claude Code documentation](https://code.claude.com/docs/en/skills).

3. Invoke the `kernelgen-flagos` skill through one of the following methods:

   * Use the slash command `/kernelgen-flagos`&#x20;

   * Include the name in your prompt

4. Chat with Claude Code about your requirements for generating the ReLU operator.

   * **Typical requirements**: Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, testing devices, and the number of iterations of operator optimization.

   * **Requirement example**: "**The operator name is ReLU**, and the classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use Tsingmicro."

## Use OpenClaw to generate an operator

This section introduces how to use OpenClaw, KernelGen MCP server, and first- and third-party skills to generate the ReLU operator.

### Steps

1. Install OpenClaw. See <https://docs.openclaw.ai/>.

2. Download and install the following skills:

   * McPorter skills created by Peter Steinberger from [ClawHub](https://clawhub.ai/steipete/mcporter)

   * `kernelgen-flagos` skill from [FlagOS Skills Github](https://github.com/flagos-ai/skills/tree/main/skills/kernelgen-flagos)

   For skill installation, see [OpenClaw documentation](https://docs.openclaw.ai/tools/skills).

3. Configure the KernelGen MCP server. See [Use OpenClaw to connect to KernelGen MCP server](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-UQWNdyXCZokoFTxb8EXch8APnWg).

4. Invoke the `kernelgen-flagos` skill through one of the following methods:

   * Use the slash command `/kernelgen-flagos`&#x20;

   * Include the name in your prompt

5. Chat with OpenClaw and provide requirements for generating the ReLU operator through natural language.

   * **Typical requirements**: Operator name（mandatory）, task description (mandatory), input parameters and data type, output parameters and data type, testing devices, and the number of iterations of operator optimization.

   * **Requirement example**: "**The operator name is ReLU**, and the classification is pointwise. There is 1 input parameter: input: torch. Tensor, the input tensor, which can be of any shape and data type, usually floating-point type, and requires the application of the ReLU activation function. There is 1 output. Output: torch. Tensor, the output tensor after ReLU activation, with the same shape as input, and the logic is max(0, input), i.e., all negative values become 0, and positive values remain unchanged. Use Tsingmicro."
