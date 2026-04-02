# 使用 VSCode 连接到 KernelGen 算子开发 MCP 工具集

使用 VSCode 时，请注意以下要求：

* VSCode 版本须高于 2025 年 3 月发布的 1.99 版本。

* 请安装 GitHub Copilot 扩展。

请按照以下步骤将 VSCode 连接到 KernelGen 算子开发 MCP 工具集：

1. 选择 **文件** > **首选项** > **设置** > **聊天** > **MCP**。在 **Server Sampling** 区域，点击"在settings.json中编辑"链接。
2. 将以下代码添加到 `setting.json` 文件中。

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

3. 验证 VSCode 与 KernelGen 算子开发 MCP 工具集之间的连接。

   1. 按 **Ctrl**+**Shift**+**P** 打开命令面板，输入并搜索"MCP: 列出服务器"，然后按 Enter，即可显示当前在 VSCode 中配置的所有 MCP 服务器及其运行状态。

   2. 从列表中选择"kernelgen-mcp"，然后选择"启动服务器"。
   3. 验证"kernelgen-mcp"的状态为 `connected`。

**注意**：

* VSCode 的配置格式使用 `servers`，而非 `mcpServers`。

* SSE 模式的 URL 路径通常为 `/sse`（FastMCP 默认路径）。
