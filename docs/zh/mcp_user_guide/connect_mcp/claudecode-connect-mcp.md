# 使用 Claude Code 连接到 KernelGen 算子开发 MCP 工具集

请按照以下步骤将 Claude Code 连接到 KernelGen 算子开发 MCP 工具集：

将 KernelGen 算子开发 MCP 工具集 注册到 Claude Code 有两种方式。无论使用哪种方式，您都必须充分了解 Claude Code 的 scope 配置。详情请参见 <https://code.claude.com/docs/en/settings#>

1. 配置并连接到 KernelGen 算子开发 MCP 工具集。

   - **方式一**（推荐）：使用 Server-Sent Events（SSE）协议和 Bearer 认证，将 KernelGen 算子开发 MCP 工具集 注册到 Claude Code。

     ```bash
     claude mcp add --transport sse kernelgen-mcp https://kernelgen.flagos.io/sse/ --header "Authorization: Bearer <your token>"
     ```

     **注意**：

     - local（默认）：`.claude/settings.local.json`，仅限您自己在当前项目中使用。

     - project：`.mcp.json`，供团队共享，可提交到 git。

     - user：`~/.claude/settings.json`，适用于您的所有项目。

     更多信息请参见 <https://code.claude.com/docs/en/settings#>

   - **方式二**：手动修改配置文件。

     按如下方式编辑 `~/.claude/settings.json`：

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

     **注意**：

     - 个人使用时，建议使用命令 `--scope user`（推荐）；

     - 团队共享时，使用命令 `--scope project`（请勿将 Token 提交到 Git）。

2. 与 Claude Code 对话，请求其验证连接是否成功。
