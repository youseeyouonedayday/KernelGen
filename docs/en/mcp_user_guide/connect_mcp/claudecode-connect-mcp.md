# Use Claude Code to connect to KernelGen Operator Development MCP Toolkit

## Prerequisites

- Use Claude Code version 2.1 and later
- Learn Claude Code settings: <https://code.claude.com/docs/en/settings#>.

## Steps

To connect Claude Code to the KernelGen Operator Development MCP Toolkit, perform the following steps:

1. Use the Server-Sent Events (SSE) protocol and Bear authentication to register the KernelGen Operator Development MCP Toolkit with Claude Code:

   - **Option 1** (Recommended): Send a prompt to connect to the KernelGen Operator Development MCP Toolkit, for example:

     - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`

     - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>.`
  
   - **Option 2** : Use the following command:

     ```bash
     claude mcp add --transport sse kernelgen-mcp https://kernelgen.flagos.io/sse/ --header "Authorization: Bearer <your KernelGen Token>"
     ```

   - **Option 3**: Manually modify the configuration file.
  
      - **Option A**: Add JSON configuration to the `.claude.json` file

          ```{code-block} json
          {
            "projects": {
              "/root/projects/my-project": {
                "mcpServers": {
                  "kernelgen-mcp": {
                    "type": "sse",
                    "url": "https://kernelgen.flagos.io/sse",
                    "headers": {
                      "Authorization": "Bearer <your KernelGen Token>"
                    }
                  }
                }
              }
            }
          }
          ```

      - **Option B**：Create `mcp.json` file, and add JSON configuration.

        ```{code-block} python
        {
          "mcpServers": {
            "kernelgen_mcp": {
              "url": "http://kernelgen.flagos.io/sse",
              "headers": {
                "Authorization": "Bearer <your KernelGen Token>"
              }
            }
          }
        }
        ```

2. Verify KernelGen Operator Development MCP Toolkit connection：

   - Option 1: Use prompt

    ```{code-block} shell
    Please verify the kernelgen mcp connection is successful.
    ```

- Option 2: Use command

    ```{code-block} shell
    /mcp
    ```
