# Nystead Builder (`nystead-builder` 0.7.5)

Nystead Builder — the same gated engineering workflow for people who do not write software: a technical question is never put to you — it is answered from the canon, queued for review and surfaced as an assumption; only business decisions reach you. The skills are served by the Nystead server the plugin connects to on install. One-week trial, then paid.

## What is in this plugin

Nothing but shells. Every skill, command and agent here is a stub whose only instruction is to
fetch the real one from the Nystead server and follow it; the server is declared in `.mcp.json`
and connects the moment the plugin is installed. Skills are fetched once per conversation and
again when their version changes on the server, so an update needs no reinstall. The runnable
files the skills use (scripts, CLIs, checks) are written under this plugin's folder on first use.

## Install

```
/plugin marketplace add <owner>/nystead-builder
/plugin install nystead-builder@nystead-builder
```

This repository is its own marketplace. Nystead for Teams lives in its
own repository the same way.

Nothing to configure. Check the connection with `/mcp` — `nystead` is listed — and run
`node "${CLAUDE_PLUGIN_ROOT}/scripts/skill.mjs" --list` from any session to see what is served.

## Money

**Nystead Builder is a one-week trial, then paid**, enforced on the server — an expired
subscription is answered with a short "subscription required" message and the pipeline stops
cleanly, with no partial artefacts. This version ships before the per-user licence exists: the
bearer token in `.mcp.json` is shared abuse protection, and the plain-language interview and
assumptions ledger Nystead Builder is designed around are not in it yet — today it runs the same
workflow as Nystead for Teams with every technical question answered from the canon instead of
being put to you.

## Where the workflow itself is documented

On the server: run any skill and read what it prints. The canon and the rules it cites are served
too (`--rule R-XNN`); they are not in this repository.
