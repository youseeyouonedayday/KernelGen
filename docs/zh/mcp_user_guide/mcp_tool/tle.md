
# TLE Kernel

您可以使用 MCP 工具在 NVIDIA 上生成基于 TLE 的 Kernel。本节以 sparse\_mla Kernel 为例进行说明。关于该 Kernel 的详细信息，请参见 [FlagTree 文档](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-U0vAdwqqooUphDxTAWocWyXJnad)。

在生成 TLE 算子之前，请预先安装 FlagTree 3.6.x 分支。请参见[安装 FlagTree](https://docs.flagos.io/projects/FlagTree/en/latest/getting_started/install.html)。

生成 TLE Kernel 时，典型的提示词应包含以下必填和可选要素："Invoke MCP tools"（必填）、算子名称（必填）以及任务描述（必填）。

提示词示例：

```{code-block} python
Invoke MCP tools to generate the TLE ReLU operator.
```

**注意**：TLE 算子生成能力目前为实验性功能，正在积极开发中。
