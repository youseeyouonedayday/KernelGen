# 使用 OpenClaw 连接到 KernelGen 算子开发 MCP 工具集

## 前提条件

使用 OpenClaw 2026.3.2 及更高版本。

## 步骤

按照以下步骤将 OpenClaw 连接到 KernelGen 算子开发 MCP 工具集：

1. 发送提示词连接到 KernelGen 算子开发 MCP 工具集，例如：

   - `连接到 MCP，其 URL 为 https://kernelgen.flagos.io/sse，token 为 <your KernelGen Token>。`

   - `请配置 kernelgen mcp, url 是 https://kernelgen.flagos.io/sse，token 是 <你的KernelGen Token>。`

    **注意**：如果当前 OpenClaw 版本不支持 MCP，可通过提示词或命令安装 `mcporter`。以下为命令示例：

    ```{code-block} shell
    "npx skills add steipete/clawdis@mcporter -g -y"
    ```

2. 验证 KernelGen 算子开发 MCP 工具集连接, 发送提示词：
  
  ```{code-block} shell
  请验证 kernelgen mcp 能否测通。
  ```
