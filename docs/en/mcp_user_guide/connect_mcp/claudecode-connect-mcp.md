# Use Claude Code to connect to KernelGen Operator Development MCP Toolkit

## Prerequisites

Use Claude Code version 2.1 and later

## Steps

To connect Claude Code to the KernelGen Operator Development MCP Toolkit, perform the following steps:

1. Use the Server-Sent Events (SSE) protocol and Bear authentication to register the KernelGen Operator Development MCP Toolkit with Claude Code:

   - **Option 1** (Recommended): Send a prompt to connect to the KernelGen Operator Development MCP Toolkit, for example:

     - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`

     - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>. `
  
   - **Option 2** : Use the following command:

     ```bash
     claude mcp add --transport sse kernelgen-mcp https://kernelgen.flagos.io/sse/ --header "Authorization: Bearer <your KernelGen Token>"
     ```

     **Note**:

     - local (default):`.claude/settings.local.json`, only yourself in the current project.

     - project: `.mcp.json`, team sharing, submitted to git.

     - user: `~/.claude/settings.json`, all your projects.

     For more information, see <https://code.claude.com/docs/en/settings#>

   - **Option 3**: Manually modify the configuration file.

     Edit `~/.claude/settings.json` as follows:

     ```json
     {
       "mcpServers": {
         "kernelgen-mcp": {
           "transport": "sse",
           "url": "https://kernelgen.flagos.io/sse",
           "headers": {
             "Authorization": "Authorization: Bearer <your KernelGen Token>"
           }
         }
       }
     }
     ```

     **Note**:

     - For personal use, use the command `--scope user`(Recommended);

     - For team sharing, use the command `--scope project` (Do not submit tokens to Git).

2. Chat with Claude Code and ask it to verify the connection.
