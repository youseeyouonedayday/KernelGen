# KernelGen Skills 使用案例

本节介绍如何使用 VS Code、Claude Code 或 OpenClaw，通过 KernelGen Skills 为任意项目生成 Kernel，以及跨硬件平台进行优化和特化。


## 前提条件

在生成 Kernel 之前，请确保您已阅读本节的前提条件并完成预安装步骤。

- 我们已对以下 AI 智能体版本进行了测试，建议使用已测试的版本或更新版本。

  | AI 智能体                  | 已测试版本 |
  |--------------------------|----------------|
  | Claude Code              | 2.1.72         |
  | VS Code（及 Copilot）     | 0.38.2         |
  | OpenClaw                 | 2026.2.26      |

- 预安装 FlagGems 或 vLLM。

  - KernelGen Skills 支持 FlagGems，请参阅下一节[*预安装 FlagGems*](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-PTNCdXxFUobOUxxZ76xcwgzEnSb)。

  - KernelGen Skills 支持 vLLM，请参阅 [vLLM 用户指南](https://docs.vllm.ai/en/latest/getting_started/installation/)。

## 预安装 FlagGems

有关安装信息，请参阅 [FlagGems 文档](https://docs.flagos.io/projects/FlagGems/en/latest/getting_started/install.html#)。

**注意**：安装过程中，请跳过 `pip install -r flag_tree_requirements/requirements_nvidia.txt` 命令，该命令与 FlagTree 及其依赖项的安装相关。



```{toctree}
:maxdepth: 2


generate-ops-for-gems-and-vllm.md
optimize-ops.md
specialize-ops.md


```
