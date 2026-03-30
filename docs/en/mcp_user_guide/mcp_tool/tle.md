
# TLE Kernel

You can use MCP tool to generate kernels with TLE on NVIDIA. This section uses sparse\_mla Kernel as an example. For information about this Kernel, see [FlagTree Documentation](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-U0vAdwqqooUphDxTAWocWyXJnad).

Before generating the TLE operator, preinstall the FlagTree branch 3.6.x. See [Install FlagTree.](https://docs.flagos.io/projects/FlagTree/en/latest/getting_started/install.html).

To generate a TLE kernel, a typical prompt should include the following mandatory and optional elements: “Invoke MCP tools” (mandatory), operator name (mandatory), and task description (mandatory).

Prompt example:

```{code-block} python
Invoke MCP tools to generate the TLE ReLU operator.
```

**Note**: The TLE operator generation capability is an experimental feature currently under active development.