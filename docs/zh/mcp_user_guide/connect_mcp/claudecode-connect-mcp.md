# 使用 Claude Code 连接到 KernelGen 算子开发 MCP Toolkit

## 前提条件

- 使用 Claude Code 2.1 及更高版本。
- 了解 Claude Code 设置：<https://code.claude.com/docs/en/settings#>。

## 步骤

按照以下步骤将 Claude Code 连接到 KernelGen 算子开发 MCP Toolkit：

1. 使用 Server-Sent Events（SSE）协议和 Bearer 认证方式，将 KernelGen 算子开发 MCP 工具集注册到 Claude Code：

   - **方式一**（推荐）：发送提示词连接到 KernelGen 算子开发 MCP Toolkit，例如：

     - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`

     - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>.`
  
   - **方式二**：使用以下命令：

     ```bash
     claude mcp add --transport sse kernelgen-mcp https://kernelgen.flagos.io/sse/ --header "Authorization: Bearer <your KernelGen Token>"
     ```

   - **方式三**：手动修改配置文件。
  
      - **方式 A**：在 `.claude.json` 文件中添加 JSON 配置：

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

      - **方式 B**：创建 `mcp.json` 文件并添加 JSON 配置：

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

2. 验证 KernelGen 算子开发 MCP 工具集连接：

   - 方式一：使用提示词

    ```{code-block} shell
    Please verify the kernelgen mcp connection is successful.
    ```

   - 方式二：使用命令

    ```{code-block} shell
    /mcp
    ```
