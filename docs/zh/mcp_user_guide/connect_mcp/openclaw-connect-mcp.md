# 使用 OpenClaw 连接到 KernelGen 算子开发 MCP Toolkit

## 前提条件

使用 OpenClaw 2026.3.2 及更高版本。

## 步骤

按照以下步骤将 OpenClaw 连接到 KernelGen 算子开发 MCP Toolkit：

1. 发送提示词连接到 KernelGen 算子开发 MCP Toolkit，例如：

   - `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`

   - `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>.`

    **注意**：如果当前 OpenClaw 版本不支持 MCP，可通过提示词或命令安装 `mcporter`。以下为命令示例：

    ```{code-block} shell
    "npx skills add steipete/clawdis@mcporter -g -y"
    ```

2. 验证 KernelGen 算子开发 MCP 工具集连接：

   - **方式一**：使用提示词

    ```{code-block} shell
    Please verify the kernelgen mcp connection is successful.
    ```

   - **方式二**：使用命令
  
    ```{code-block} python
    /mcp
    ```
