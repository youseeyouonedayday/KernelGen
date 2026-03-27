# 特化算子

您可以使用 VS Code（及 Copilot）、Claude Code 或 OpenClaw，将 CUDA 实现的算子迁移至华为昇腾。

## 步骤

与 AI 智能体对话以特化算子：

- **典型需求**：算子名称（必填）和任务描述（必填）。
- **需求示例**："将 CUDA 实现的算子 fused/silu_and_mul.py 迁移至昇腾芯片，算子文件存储在 FlagGems 代码仓库中，目标目录为 _ascend/fused/silu_and_mul.py，并确保精度验证通过。"
