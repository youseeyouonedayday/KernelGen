# 优化算子

您可以使用 VS Code（及 Copilot）、Claude Code 或 OpenClaw 在 **NVIDIA** 上优化算子。

优化算子时，典型的提示词应包含以下必填和可选要素：

算子名称（必填）、任务描述（必填），以及优化迭代次数。

## 步骤

如果您尚未连接到 KernelGen 算子开发 MCP Toolkit 并加载技能，请参见 [KernelGen 技能用户指南](../skills_user_guide/skills-user-guide.md)；否则，请使用以下任一方式调用 `kernelgen-flagos` 技能并优化算子：

- **方式一**：使用斜杠命令和提示词

   ```{code-block} python
   /kernelgen-flagos Optimize the index_put operator. Optimize 5 iterations.
   ```

- **方式二**：完全使用提示词

   ```{code-block} python
   Use kernelgen-flagos to optimize the index_put operator. Optimize 5 iterations.
   ```
