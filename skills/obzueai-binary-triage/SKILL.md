---
name: obzueai-binary-triage
description: "Structured initial binary triage for ObzueAI Engineer. Survey layout, strings, imports, functions, and flag interesting areas with evidence. Use when first examining a binary or before deep analysis."
type: workflow
lifecycle: active
---

# ObzueAI Binary Triage

Perform a fast, evidence-backed survey of a native binary before deeper investigation. Goal: identify key components, flag suspicious areas, and produce a prioritized next-step list.

## Principles

- Start with inventory, not full decompilation.
- Cite addresses, digests, and tool outputs.
- Distinguish observations from inferences.
- Leave temporary projects clean unless requested.

## Workflow

1. Confirm absolute path and record SHA-256.
2. Run inventory via the Ghidra skill wrapper or ObzueAI Engineer CLI/MCP:
   - Functions list
   - Strings
   - Symbols / imports / exports
3. Survey:
   - Entry points and main-like functions
   - Interesting strings (URLs, paths, crypto constants, error messages)
   - Suspicious imports (network, process, crypto, file)
   - Function count and size distribution
4. Flag areas:
   - Potential crypto, C2, anti-analysis, or packing indicators
   - Unresolved or large functions worth later decompilation
5. Produce a short triage report with:
   - Binary identity (path, digest, processor if known)
   - Key observations with evidence IDs or offsets
   - Prioritized next steps (deep analysis targets, runtime checks)
   - Explicit unknowns and limitations

## Integration

- Prefer the existing `ghidra` skill or ObzueAI Engineer MCP `analyze_binary` for data.
- Hand flagged functions to the main reverse-engineer-agent skill for depth-first work.
- See `references/triage-checklist.md` for the survey checklist.

## Finish

Deliver the triage summary in plain language, attach evidence, and list the top 3–5 follow-up questions.
