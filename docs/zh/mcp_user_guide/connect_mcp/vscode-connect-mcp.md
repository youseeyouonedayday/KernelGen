# 使用 VS Code 连接 KernelGen MCP 服务器

如果您使用 VS Code，请注意以下要求：

* VS Code 版本需高于 2025 年 3 月发布的 1.99 版本。

* 需安装 GitHub Copilot 扩展。

如需将 VS Code 连接至 KernelGen MCP 服务器，请执行以下步骤：

1. 配置 KernelGen MCP 服务器。在项目根目录下创建 `.VS Code/mcp.json` 文件。

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

2. 验证 VS Code 与 KernelGen MCP 服务器之间的连接。

   1. 按 **Ctrl**+**Shift**+**P** 打开命令面板，输入并搜索"MCP: List Servers"，然后按 Enter，即可显示当前在 VS Code 中配置的所有 MCP 服务器列表及其运行状态。

   2. 验证 KernelGen MCP 服务器的状态为 `connected`（已连接）。

**注意**：

* VS Code 的配置格式使用 `servers`，而非 `mcpServers`。

* SSE 模式的 URL 路径通常为 `/sse`（FastMCP 默认路径）。
