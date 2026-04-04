# 使用 VSCode 连接到 KernelGen 算子开发 MCP 工具集

## 前提条件

安装 GitHub Copilot 扩展并确保其已激活。

## 步骤

按照以下步骤将 VSCode 连接到 KernelGen 算子开发 MCP 工具集：

1. 连接到 KernelGen 算子开发 MCP 工具集：

   - **方式一**（推荐）：发送提示词连接到 KernelGen 算子开发 MCP 工具集，例如：

     - `连接到 MCP，其 URL 为 https://kernelgen.flagos.io/sse，token 为 <your KernelGen Token>。`

     - `请配置 kernelgen mcp, url 是 https://kernelgen.flagos.io/sse，token 是 <你的KernelGen Token>。`

   - **方式二**：手动配置

    {style=lower-alpha}

     1. 选择 **File** > **Preferences**，然后选择 **Settings**。导航至 **Chat** > **MCP**。在 **Server Sampling** 区域，点击"Edit in settings.json"链接。

     2. 将以下代码添加到 `settings.json` 文件中：

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

2. 启动服务器。

  {style=lower-alpha}

   1. 按 **Ctrl**+**Shift**+**P** 打开命令面板，输入并搜索"MCP: List Servers"，然后按 Enter 键，即可查看 VSCode 中当前所有已配置的 MCP Server 及其运行状态。

   2. 从列表中选择"kernelgen-mcp"，然后选择"Start Server"。

3. 验证 KernelGen 算子开发 MCP 工具集连接，发送提示词：
  
  ```{code-block} shell
  请验证 kernelgen mcp 能否测通。
  ```
