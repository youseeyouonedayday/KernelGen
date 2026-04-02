# Use OpenClaw to connect to KernelGen Operator Development MCP Toolkit

## Prerequisites

Use OpenClaw version 2026.3.2 and later

## Steps

To connect OpenClaw to the KernelGen Operator Development MCP Toolkit, perform the following steps:

Send a prompt to connect to the KernelGen Operator Development MCP Toolkit, for example:

- `Connect to MCP, its URL is https://kernelgen.flagos.io/sse and token is <your KernelGen Token>.`

- `Please configure the kernelgen MCP with the URL https://kernelgen.flagos.io/sse and the token is <your KernelGen Token>. `

**Note**: If the current OpenClaw version does not support MCP, you can install `mcporter` via prompt or command．The following is the command example.

```{code-block} shell
"npx skills add steipete/clawdis@mcporter -g -y"
```
