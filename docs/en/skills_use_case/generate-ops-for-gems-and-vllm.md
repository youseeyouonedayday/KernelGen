# Generate a kernel for FlagGems or vLLM project

## Prerequisites

Before generating a kernel, make sure you read the prerequisites and accomplish the pre-installation steps in this section.

- We have tested the following AI agent versions. We recommend using the tested version or a newer one.

  | AI agent                  | Tested version |
  |--------------------------|----------------|
  | Claude Code              | 2.1.72         |
  | VS Code （and Copilot）   | 0.38.2         |
  | openClaw                 | 2026.2.26      |

- Preinstall FlagGems or vLLM.

  - KernelGen Skills support FlagGems, see the next [Preinstall FlagGems](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-PTNCdXxFUobOUxxZ76xcwgzEnSb) section.

  - KernelGen Skills support vLLM, see [vLLM user guide](https://docs.vllm.ai/en/latest/getting_started/installation/).

## Preinstall FlagGems

For installation information, see [FlagGems Documentation](https://docs.flagos.io/projects/FlagGems/en/latest/getting_started/install.html#).

**Note**: During the installation, skip the`pip install -r flag_tree_requirements/requirements_nvidia.txt` command since this command relates to installation of FlagTree and its dependencies.

## Generate a kernel

Using VS Code (and Copilot), Claude Code, or OpenClaw to generate an operator for the FlagGems or vLLM project follows a similar general process in [KernelGen Skills User Guide](../skills_user_guide/skills-user-guide.md). Prompts are generally interchangeable; for example, you can simply add "Integrate the kernel into FlagGems" to your request. KernelGen automatically detects if FlagGems is installed and submits the output files to the project's experimental directory.
