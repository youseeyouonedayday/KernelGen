# 为 FlagGems 或 vLLM 项目生成 Kernel

## 前提条件

生成 Kernel 之前，请确保您已阅读本节中的前提条件，并完成预安装步骤。

- 我们已测试以下 AI 智能体版本，建议使用已测试版本或更新版本。

  | AI 智能体                  | 已测试版本 |
  |--------------------------|----------------|
  | Claude Code              | 2.1.72         |
  | VS Code（及 Copilot）     | 0.38.2         |
  | openClaw                 | 2026.2.26      |

- 预先安装 FlagGems 或 vLLM。

  - KernelGen 技能支持 FlagGems，请参见下方[预安装 FlagGems](https://jwolpxeehx.feishu.cn/wiki/DcB6wnUlyiJzaHkmlUQcUNfcnpb#share-PTNCdXxFUobOUxxZ76xcwgzEnSb) 章节。

  - KernelGen 技能支持 vLLM，请参见 [vLLM 用户指南](https://docs.vllm.ai/en/latest/getting_started/installation/)。

## 预安装 FlagGems

安装信息请参见 [FlagGems 文档](https://docs.flagos.io/projects/FlagGems/en/latest/getting_started/install.html#)。

**注意**：安装过程中，请跳过 `pip install -r flag_tree_requirements/requirements_nvidia.txt` 命令，因为该命令涉及 FlagTree 及其依赖项的安装。

## 生成 Kernel

使用 VS Code（及 Copilot）、Claude Code 或 OpenClaw 为 FlagGems 或 vLLM 项目生成算子，其一般流程与 [KernelGen 技能用户指南](../skills_user_guide/skills-user-guide.md) 中的描述基本相同。提示词通常可以通用，例如，您只需在请求中添加"Integrate the kernel into FlagGems"即可。KernelGen 会自动检测是否已安装 FlagGems，并将输出文件提交到该项目的实验目录中。
