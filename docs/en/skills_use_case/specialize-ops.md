# Specialize an operator

You can use either VSCode (and Copilot), Claude Code, or OpenClaw to migrate CUDA-implemented operators to Huawei Ascend.

To optimize an operator, a typical prompt should include the following mandatory and optional elements: Operator name（mandatory）and task description (mandatory).

## Steps

If you haven't connected to the KernelGen Operator Development MCP Toolkit and load skills, see [KernelGen Skills User Guide](../skills_user_guide/skills-user-guide.md), otherwise use one of the following methods to invoke the `kernelgen-flagos` skill and specialize an operator:

- **Option 1**: Use the slash command and prompt

   ```{code-block} python
   /kernelgen-flagos Migrate the CUDA-implemented operator fused/silu_and_mul.py to the Ascend chip, with the operator file stored in the FlagGems repository, and the directory is _ascend/fused/silu_and_mul.py, ensuring that the accuracy verification passes.
   ```

- **Option 2**: Completely use prompt

   ```{code-block} python
   Use kernelgen-flagos to migrate the CUDA-implemented operator fused/silu_and_mul.py to the Ascend chip, with the operator file stored in the FlagGems repository, and the directory is _ascend/fused/silu_and_mul.py, ensuring that the accuracy verification passes.
   ```