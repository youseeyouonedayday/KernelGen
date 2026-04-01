# Use Claude Code to connect to KernelGen Operator Development MCP Toolkit

To connect Claude Code to the KernelGen Operator Development MCP Toolkit, perform the following steps:

Two methods are available to register the KernelGen Operator Development MCP Toolkit to Claude Code. No matter which method you use, you must fully understand the scope configuration of Claude Code. For more information, see <https://code.claude.com/docs/en/settings#>

1. Configure and connect to the KernelGen Operator Development MCP Toolkit.

   - **Option 1** (Recommended): Use the Server-Sent Events (SSE) protocol and Bear authentication to register the KernelGen Operator Development MCP Toolkit with Claude Code.

     ```bash
     claude mcp add --transport sse kernelgen-mcp https://kernelgen.flagos.io/sse/ --header "Authorization: Bearer <your token>"
     ```

     **Note**:

     - local (default):`.claude/settings.local.json`, only yourself in the current project.

     - project: `.mcp.json`, team sharing, submitted to git.

     - user: `~/.claude/settings.json`, all your projects.

     For more information, see <https://code.claude.com/docs/en/settings#>

   - **Option 2**: Manually modify the configuration file.

     Edit `~/.claude/settings.json` as follows:

     ```json
     {
       "mcpServers": {
         "kernelgen-mcp": {
           "transport": "sse",
           "url": "http://kernelgen.flagos.io/sse",
           "headers": {
             "Authorization": "Authorization: Bearer <your Token>"
           }
         }
       }
     }
     ```

     **Note**:

     - For personal use, use the command `--scope user`(Recommended);

     - For team sharing, use the command `--scope project` (Do not submit tokens to Git).

2. Chat with Claude Code and ask it to verify the connection.
