# 支持的硬件平台

KernelGen Web 平台和 KernelGen MCP Server 内置支持以下测试设备：华为昇腾（Huawei Ascend）、海光（Hygon）、天数智芯（Iluvatar）、沐曦（MetaX）、摩尔线程（Mthreads）和 NVIDIA。

- **生成算子**：
  - 若用户未选择测试设备，默认使用 NVIDIA。
  - 针对生成 FlagTree TLE 算子，测试设备只能为 NVIDIA。
- **优化算子**：仅支持在 NVIDIA 上进行算子优化。
- **特化算子**：仅支持将算子从 NVIDIA 特化至华为昇腾。
