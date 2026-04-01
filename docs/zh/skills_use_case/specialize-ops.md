# 专化算子

您可以使用 VS Code（及 Copilot）、Claude Code 或 OpenClaw，将 CUDA 实现的算子迁移到华为昇腾（Huawei Ascend）。

专化算子时，典型的提示词应包含以下必填要素：算子名称（必填）和任务描述（必填）。

## 步骤

如果您尚未连接到 KernelGen 算子开发 MCP Toolkit 并加载技能，请参见 [KernelGen 技能用户指南](../skills_user_guide/skills-user-guide.md)；否则，请使用以下任一方式调用 `kernelgen-flagos` 技能并专化算子：

- **方式一**：使用斜杠命令和提示词

   ```{code-block} python
   /kernelgen-flagos Migrate the CUDA-implemented operator fused/silu_and_mul.py to the Ascend chip, with the operator file stored in the FlagGems repository, and the directory is _ascend/fused/silu_and_mul.py, ensuring that the accuracy verification passes.
   ```

- **方式二**：完全使用提示词

   ```{code-block} python
   Use kernelgen-flagos to migrate the CUDA-implemented operator fused/silu_and_mul.py to the Ascend chip, with the operator file stored in the FlagGems repository, and the directory is _ascend/fused/silu_and_mul.py, ensuring that the accuracy verification passes.
   ```
