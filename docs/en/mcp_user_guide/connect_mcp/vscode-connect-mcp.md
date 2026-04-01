# Use VS Code to connect to KernelGen Operator Development MCP Toolkit

If you use VS Code, note the following requirements:

* VS Code version should be greater than 1.99 released after March 2025.

* Install the GitHub Copilot extension.

To connect VS Code to KernelGen Operator Development MCP Toolkit, perform the following steps:

1. Select **File** > **Preferences** > **Settings** > **Chat** > **MCP**.  In the **Server Sampling** section, click the "Edit in settings.json" link.
2. Add the following code to the `setting.json` file.

   ```json
   {
     "servers": {
       "kernelgen-mcp": {
         "type": "sse",
         "url": "http://kernelgen.flagos.io/sse",
         "headers": {
           "Authorization": "Bearer <your Token>"
         }
       }
     }
   }
   ```

3. Verify the connection between VS Code and KerngelGen MCP server.

   1. Press **Ctrl**+**Shift**+**P** to open the command palette, type and search for "MCP: List Servers", then press Enter to display a list of all MCP servers currently configured in VS Code along with their running status.

   2. Select "kernelgen-mcp" from list and select "Start Server".
   3. Verify that the status of the "kernelgen-mcp" is `connected`.

**Note**:

* The configuration format of VS Code is `servers`, not `mcpServers`.

* The SSE mode URL path is typically `/sse` (default in FastMCP).