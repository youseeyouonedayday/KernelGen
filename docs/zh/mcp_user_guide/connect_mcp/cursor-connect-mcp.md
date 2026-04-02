# 使用 Cursor 连接到 KernelGen 算子开发 MCP 工具集

如需将 Cursor 连接到 KernelGen 算子开发 MCP 工具集，请按如下方式配置 `mcp.json` 文件：

```json
"mcp_kernelgen": {
      "url": "https://kernelgen.flagos.io/sse",
      "headers": {
        "Authorization": "Bearer <your KernelGen Token>"
      },
      "timeout": 3600,
      "disabled": false
    },
```
