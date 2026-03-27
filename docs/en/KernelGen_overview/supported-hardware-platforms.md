# Supported hardware platforms

KernelGen Web Platform and KernelGen MCP Server internally integrate support for the following testing devices: Huawei Ascend, Hygon, Iluvatar, MetaX, Mthreads, and NVIDIA.

- **Generating operators**:
  - If users do not select a testing device, NVIDIA is used by default.
  - For generating FlagTree TLE operators specifically, the testing device can only be NVIDIA.
- **Optimizing operators**: Only support operator optimization on NVIDIA.
- **Specializing operators**: Only support operator specialization from NVIDIA to Huawei Ascend.