# KernelGen Overview

**KernelGen** is designed to generate, optimize, and specialize operators across diverse hardware platforms. After connecting to KernelGen MCP Server, you can either accomplish these tasks using the server alone or combine it with first- and third-party skills. Users can invoke KernelGen MCP Server and these skills in VS Code (and GitHub Copilot), Claude Code, or OpenClaw.

## Features

KernelGen Web Platform and KernelGen MCP Server platforms support generating, optimizing, and specializing operators through one of the following methods:

- KernelGen Web Platform
- KernelGen MCP Server and its MCP tools: All MCP tools are integrated into the MCP server.
- KernelGen MCP Server and KernelGen skills: All KernelGen skills are bundled in the kernelgen-flagos skill. Users can invoke the bundled skill to invoke the sub-skills.

## Supported hardware platforms

KernelGen Web Platform and KernelGen MCP Server internally integrate support for the following testing devices: Huawei Ascend, Hygon, Iluvatar, MetaX, Mthreads, and NVIDIA.

- **Generating operators**:
  - If users do not select a testing device, NVIDIA is used by default.
  - For generating FlagTree TLE operators specifically, the testing device can only be NVIDIA.
- **Optimizing operators**: Only support operator optimization on NVIDIA.
- **Specializing operators**: Only support operator specialization from NVIDIA to Huawei Ascend.

## Where to Begin?

- New to KernelGen?
If you're just getting started and want to quickly explore KernelGen, begin with the *Getting Started* guide.
- Developing custom operators?
If you're an operator developer, jump straight into the following guides:
  - *KernelGen Web Platform User Guide*
  - *KernelGen MCP Server User Guide*
  - *KernelGen Skills Guide*

```{toctree}

workflow.md
concept.md
```
