# KernelGen Skills Use Cases

This section introduces how to generate kernels for any project, optimize and specialize them across hardware platforms using VS Code, Claude Code, or OpenClaw.&#x20;


## Prerequisites

Before generating a kernel, make sure you read the prerequisites and accomplish the pre-installation steps in this section.

- We have tested the following AI agent versions. We recommend using the tested version or a newer one.

- Preinstall FlagGems or vLLM.

  - KernelGen Skills support FlagGems, see the next [*Preinstall FlagGems*](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-PTNCdXxFUobOUxxZ76xcwgzEnSb) section.

  - KernelGen Skills support vLLM, see [vLLM user guide](https://docs.vllm.ai/en/latest/getting_started/installation/).

## Preinstall FlagGems

For installation information, see [FlagGems Documentation](https://docs.flagos.io/projects/FlagGems/en/latest/getting_started/install.html#).

**Note**: During the installation, skip the`pip install -r flag_tree_requirements/requirements_nvidia.txt` command since this command relates to installation of FlagTree and its dependencies.



```{toctree}
:maxdepth: 2


generate-ops-for-gems-and-vllm.md
optimize-ops.md
specialize-ops.md


```