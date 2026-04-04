# 使用 Claude Code 连接到 KernelGen 算子开发 MCP 工具集

## 前提条件

- 使用 Claude Code 2.1 及更高版本。
- 了解 Claude Code 设置：<https://code.claude.com/docs/en/settings#>。

## 步骤

按照以下步骤将 Claude Code 连接到 KernelGen 算子开发 MCP 工具集：

1. 使用 Server-Sent Events（SSE）协议和 Bearer 认证方式，将 KernelGen 算子开发 MCP 工具集注册到 Claude Code：

   - **方式一**（推荐）：发送提示词连接到 KernelGen 算子开发 MCP 工具集，例如：

     - `连接到 MCP，其 URL 为 https://kernelgen.flagos.io/sse，token 为 <your KernelGen Token>。`

     - `请配置 kernelgen mcp, url 是 https://kernelgen.flagos.io/sse，token 是 <你的KernelGen Token>。`
  
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

        ```{code-block} json
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
    请验证 kernelgen mcp 能否测通。
    ```

   - 方式二：使用命令

    ```{code-block} shell
    /mcp
    ```
