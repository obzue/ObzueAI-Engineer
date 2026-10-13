# ObzueAI Engineer

Local reverse-engineering workflows for agents and the command line. Evidence-driven analysis of binaries, packages, and runtime captures with Ghidra integration and a thin MCP server.

## Quick start

```bash
node scripts/cli.mjs --help
npm run mcp
```

For agents, install skills from `skills/` (reverse-engineer-agent and obzueai-binary-triage).

## Components

- CLI and thin MCP server for analyze-binary, analyze-js, doctor, evidence
- Agent skills with references for native, JavaScript, evidence, firmware/packets, and binary triage
- Integration points for the existing Ghidra headless skill

Analysis stays local. Results include digests and limitations.

## Responsible use

Analyze only software you own or are authorized to examine.
