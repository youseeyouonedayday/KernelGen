# Use VSCode to connect to KernelGen Operator Development MCP Toolkit

## Prerequisites

* Use VSCode version greater than 1.99

* Install the GitHub Copilot extension

## Steps

To connect VSCode to KernelGen Operator Development MCP Toolkit, perform the following steps:

1. Connect to KernelGen Operator Development MCP Toolkit：

   - **Option 1**: Send a prompt to connect to the KernelGen Operator Development MCP Toolkit, for example:

     - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`

     - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>. `

   - **Option 2**: Manual configuration

    {style=lower-alpha}

     1. Select **File** > **Preferences**, then choose **Settings**. Navigate to **Chat** > **MCP**. In the **Server Sampling** section, click the "Edit in settings.json" link.

     2. Add the following code to the `setting.json` file.

        ```json
        {
          "servers": {
            "kernelgen-mcp": {
              "type": "sse",
              "url": "https://kernelgen.flagos.io/sse",
              "headers": {
                "Authorization": "Bearer <your KernelGen Token>"
              }
            }
          }
        }
        ```

2. Start server.

  {style=lower-alpha}

   1. Press **Ctrl**+**Shift**+**P** to open the command palette, type and search for "MCP: List Servers", then press Enter to display a list of all MCP servers currently configured in VSCode along with their running status.

   2. Select "kernelgen-mcp" from list and select "Start Server".

3. Verify KernelGen Operator Development MCP Toolkit connection, prompt：
  
  ```{code-block} python
  Please verify the kernelgen mcp connection is successful.
  ```