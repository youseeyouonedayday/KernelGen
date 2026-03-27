# 前提条件

在将您的 AI 智能体配置并连接至 KernelGen MCP Server 之前，您必须先从 KernelGen Web 平台获取 Bearer Token。

请按以下步骤获取 Token：

1. 在浏览器中打开 [https://KernelGen.flagos.io/login](https://kernelgen.flagos.io/login)。

2. 点击**免费开始构建**。
   ![alt text](../../assets/images/start-building-from-free-zh.png)

3. 向下滚动页面至底部，点击 **MCP 服务**。
   ![alt text](../../assets/images/building-methods-zh.png)

4. 在右侧的 **Access Token** 区域，点击眼睛图标查看 Bearer Token，然后点击**复制**将其复制到剪贴板，并妥善保存以备后续使用。
   
   ```{note}
   访问 Token 需要先登录 KernelGen Web 平台。登录步骤请参阅"登录"。
   ```
   

   ![](<images/KernelGen MCP Server User Guide-image-2.png>)

   之后，您可以在请求的 `Authorization` 请求头中按如下方式使用该 Token：

   ```{code-block} json
   Authorization: Bearer <your Token>
   ```

**注意**：

- 请将 Bearer Token 视为敏感凭证，切勿共享或在公开代码仓库中暴露。

- Token 具有有效期。如果 Token 已过期且无法连接 KernelGen MCP Server，您可以登录 KernelGen Web 平台获取新的 Token。
