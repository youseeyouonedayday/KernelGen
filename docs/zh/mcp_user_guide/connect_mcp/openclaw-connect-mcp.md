# 使用 OpenClaw 连接 KernelGen MCP 服务器

如需将 OpenClaw 连接至 KernelGen MCP 服务器，请执行以下步骤：

1. 从 [ClawHub](https://clawhub.ai/steipete/mcporter) 下载并安装由 Peter Steinberger 创建的 McPorter 技能。

2. 配置 KernelGen MCP 服务器：与 OpenClaw 对话，要求其配置 KernelGen MCP 服务器，并以 JSON 格式粘贴以下信息：

```json
{
  "mcpServers": {
    "kernelgen-mcp": {
      "transport": "sse",
      "url": "http://kernelgen.flagos.io/sse",
      "headers": {
        "Authorization": "Bearer <your Token>"
```

## 使用 Cursor 连接 KernelGen MCP Server

如需将 Cursor 连接至 KernelGen MCP 服务器，请按如下方式配置 `mcp.json` 文件：

```json
"mcp_kernelgen": {
      "url": "http://kernelgen.flagos.io/sse",
      "headers": {
        "Authorization": "Bearer <your token>"
      },
      "timeout": 3600,
      "disabled": false
    },
```
