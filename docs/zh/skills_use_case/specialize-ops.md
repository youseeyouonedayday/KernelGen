# 特化算子

您可以使用 VSCode（及 Copilot）、Claude Code 或 OpenClaw，将 CUDA 实现的算子迁移到华为昇腾（Huawei Ascend）。

特化算子时，典型的提示词应包含以下必填要素：算子名称（必填）和任务描述（必填）。

## 步骤

如果您尚未连接到 KernelGen 算子开发 MCP 工具集并加载Skills，请参见 [KernelGen Skills 用户指南](../skills_user_guide/skills-user-guide.md)；否则，请使用以下任一方式调用 `kernelgen-flagos` Skills 并特化算子：

- **方式一**：使用斜杠命令和提示词

   ```{code-block} python
   /kernelgen-flagos 将 CUDA 实现的算子 fused/silu_and_mul.py 迁移到 Ascend（昇腾）芯片上，算子文件存放在 FlagGems 仓库中，路径为 _ascend/fused/silu_and_mul.py，并确保精度验证通过。
   ```

- **方式二**：完全使用提示词

   ```{code-block} python
   使用 kernelgen-flagos 将 CUDA 实现的算子 fused/silu_and_mul.py 迁移到 Ascend（昇腾）芯片上，算子文件存放在 FlagGems 仓库的 _ascend/fused/silu_and_mul.py 路径下，并确保精度验证通过。
   ```
