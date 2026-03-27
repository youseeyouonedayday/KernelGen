# 使用 Claude Code 连接 KernelGen MCP Server

如需将 Claude Code 连接至 KernelGen MCP 服务器，请执行以下步骤：

有两种方法可将 KernelGen MCP 服务器 注册到 Claude Code。无论使用哪种方法，您都必须充分了解 Claude Code 的作用域配置。更多信息请参阅 https://code.claude.com/docs/en/settings#

1. 配置并连接 KernelGen MCP 服务器。

   - **方式一**（推荐）：使用 Server-Sent Events（SSE）协议和 Bearer 认证，将 KernelGen MCP 服务器注册到 Claude Code。

     ```bash
     claude mcp add \
       --transport sse \
       --scope user \
       -H "Authorization: Bearer <your Token>" \
       kernelgen-mcp \
        http:http://kernelgen.flagos.io/sse
     ```

     ```bash
     claude mcp add --transport sse kernelgen-mcp http://kernelgen.flagos.io/sse \
       --header "Authorization: Bearer <token>"
     ```

     **注意**：

     - local（默认）：`.claude/settings.local.json`，仅限当前项目中的您本人使用。

     - project：`.mcp.json`，供团队共享，可提交至 git。

     - user：`~/.claude/settings.json`，适用于您的所有项目。

     更多信息请参阅 https://code.claude.com/docs/en/settings#

   - **方式二**：手动修改配置文件。

     按如下方式编辑 `~/.claude/settings.json`：

     ```json
     {
       "mcpServers": {
         "kernelgen-mcp": {
           "transport": "sse",
           "url": "http://kernelgen.flagos.io/sse",
           "headers": {
             "Authorization": "Authorization: Bearer <your JW Token>"
           }
         }
       }
     }
     ```

     **注意**：

     - 个人使用时，建议使用命令 `--scope user`（推荐）；

     - 团队共享时，使用命令 `--scope project`（请勿将 Token 提交至 Git）。

2. 验证连接

   1. 使用命令 `claude` 启动 Claude。

   2. 输入 `/mcp`，验证连接状态是否为 `connected`（已连接）。
