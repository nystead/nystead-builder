---
name: record-rounds
description: >
  Sort a feature's open decisions before its tickets are cut, and have the sorting re-checked by a
  reviewer that did not see it. A reader reads every record on the feature's design-record line and
  returns one row per open decision in exactly one group — closed, decided at build, or blocks
  tickets; a reviewer re-checks every row outside blocks tickets; the conductor writes the sorting
  report from what they returned; then the person reads it and may only move rows into blocks
  tickets. No record changes. Every architecture task writes its line in the state file's
  architecture-tasks block, and three in a row that closed no record are a stall that is told and
  starts the sorting. Dispatched by /new-feature's architecture phase. Triggers on: sort the open
  decisions, sorting report, blocks tickets, decided at build, re-check the sorting, read the
  sorting, stall, architecture-tasks block, BR-12, BR-13, BR-14.
---

# record-rounds

This plugin holds no skill text. The skill is served by the Nystead server this plugin connects
to on install, and this file only fetches it: run the Gate command and follow what it prints
exactly as if it were this file. A file the served text tells you to read under this skill's
folder is read with `--file <path>`; an `R-*` id it cites resolves with `--rule <id>`; the
runnable files it names under `${CLAUDE_PLUGIN_ROOT}` are written to disk by the same command.

## Inputs required

- The `nystead` MCP server declared in this plugin's `.mcp.json`, reachable with the token it
  carries. Nothing else — the served skill states its own inputs.

## Outputs

- What the served skill produces; its own `## Outputs` section says what.

## Gate

```bash
node "${CLAUDE_PLUGIN_ROOT}/scripts/skill.mjs" record-rounds
```

## Done-when

- The served skill's own `## Done-when` holds.
