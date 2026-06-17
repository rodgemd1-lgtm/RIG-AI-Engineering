# RIG AI Engineering

**A CLI + local web workbench that intakes, refines, and scores the prompts you hand your AI coding agents — then reads your past harness sessions to show you where your prompting is costing you.**

![License](https://img.shields.io/badge/license-source--available-blue.svg)
![Tests](https://img.shields.io/badge/tests-588%20passing-brightgreen.svg)
![Templates](https://img.shields.io/badge/prompt%20templates-1%2C010-orange.svg)
![Status](https://img.shields.io/badge/status-beta-yellow.svg)

> This is the **public teaser**. It proves the product is real and shows you exactly what you get. The complete, production source lives in a private repo — see [Get full access](#get-full-access).

## The problem

Your AI coding agent is only as good as the prompt you hand it. A vague, context-free prompt burns an expensive LLM call, returns code you have to re-prompt, and leaves no record of what actually worked. Most engineers run the same task through Claude Code or Codex three times before they get something usable — and learn nothing in the process.

The feedback loop that should exist — write prompt, run agent, learn what to do better next time — is almost never closed. There's no scoreboard for prompt quality, no record of which phrasings produced clean first-pass output, and no coach telling you that the prompt you're about to send is missing context, specificity, and a verification step.

## What it does

A coach that sits in front of your agents, in your terminal and in a local browser app:

- **Scores any prompt on 4 axes** — Specificity, RIG Doctrine, Context, Actionability — and returns a 0–100 grade with concrete findings. `rig score "fix the auth bug"`.
- **Rewrites weak prompts** with real repo context, acceptance criteria, and a verification step auto-injected. `rig enhance` / `rig fix-prompt`.
- **A/B tests two prompt variants** and declares a winner. `rig ab-test "A" "B"`.
- **Reads your existing harness sessions** — Claude Code, Codex, OpenCode, Hermes, GSD-Pi — to surface silos, mega-sessions, and doctrine gaps in how you've actually been prompting. `rig check --days 7`.
- **Local browser workbench** — `rig app --open` launches a localhost app for upload-and-fix, template search, gate checks, and ProofPacket creation. 13 navigation surfaces, zero console errors (proven, below).
- **1,010 prompt templates** across 10 categories, searchable. `rig suggest <query>`.
- **Coaching diagnostics** — `rig coach` reports your personal weaknesses and recommendations from your own session history.
- **MCP server** — exposes the scoring/fix/catalog tools to any MCP-capable assistant.
- **Optional integrations** — zsh pre-send hook (scores prompts before they reach your agent), HTTP proxy (transparently scores/rewrites), and a macOS background watcher.

## Proof

Real numbers from the repository, not marketing:

- **1,010 prompt templates** ship in `prompt-templates/rig-prompt-templates.json` — across 10 categories: rig-doctrine-execution, fleet-infrastructure, agent-orchestration, content-engineering, client-acquisition, product-code, research-intelligence, healthcare-verticals, personal-brand, diagnostic-coaching. Each is a structured object with `id`, `category`, `prompt_template`, `variables`, `use_case`, and a `specificity_level`.
- **49 test files, 1,003 test cases** across the TypeScript core (`src/core`, `src/webview`). A representative run on this machine collected **595 tests with 588 passing** — see the honesty note below.
- **Committed Playwright proof** of the local workbench at `apps/rig-prompt-master/.data/playwright/navigation-audit.json`: **13/13 navigation surfaces clicked and rendered, 0 console events, prompt-run output evidence = true.** This is a checked-in artifact, not a screenshot.
- **50 reviewed open-source harness resources** in `catalogs/open-source-agent-harnesses.yaml`, each with license posture, RIG role, first experiment, and load trigger.
- **10 methodology review lenses + a 100-question intake/review bank** for auditing agent and harness work.

**Honesty note (read it).** The full test suite shows 18 files failing to load under Node 26's Vite transform in a parallel run — those same files pass clean in isolation (e.g. `schemas.test.ts` → 9/9). It's an environment artifact, not a product-logic failure. The product README is equally blunt about what is **not** yet production-proven: live credential-backed GitHub/Gitea/QNAP/Recall sync, SSO, cloud pgvector memory, worker-agents, Vercel production, and notarized desktop packaging are roadmap or read-only-local, not shipped. You're buying a working local coach, not a finished SaaS — and the repo says so in writing.

## Who it's for

- **IC engineers** on Claude Code, Codex, OpenCode, or Hermes who want better first-pass agent output and fewer re-prompts.
- **AI coaches and eng managers** who need a repeatable, auditable way to score and improve prompting across a team — with a 4-axis scoreboard and trend reports.
- **Anyone** tired of running the same task three times because the first prompt had no context, no specificity, and no verification step.

## A peek

One real prompt-template object, straight from `rig-prompt-templates.json` (1 of 1,010):

```json
{
  "id": "RIG-0001",
  "category": "rig-doctrine-execution",
  "name": "IQRSQPI-{step}-a",
  "prompt_template": "Execute IQRSQPI step [STEP] for [PROJECT]. Requirements: [REQS]. Constraints: [CONSTRAINTS]. Output: [FORMAT]. Verify: [VERIF].",
  "variables": ["TASK", "REQS", "FORMAT", "VERIF", "CONTEXT"],
  "use_case": "Systematic variation a",
  "specificity_level": 4
}
```

And a slice of the committed workbench proof (`navigation-audit.json`):

```json
{
  "appUrl": "http://127.0.0.1:8767/",
  "navPassCount": 13,
  "consoleEvents": [],
  "promptRunHasOutputEvidence": true,
  "navResults": [
    { "label": "Workbench", "exists": true, "clicked": true, "h1After": "Workbench", "changed": true },
    { "label": "Context",   "exists": true, "clicked": true, "h1After": "Context",   "changed": true }
  ]
}
```

The daily loop looks like this:

```bash
# Score a prompt — 0-100 across 4 axes, with findings
rig score "fix the auth bug"

# Rewrite it with repo context, acceptance criteria, a verify step
rig enhance "fix the auth bug"

# Audit how you've actually been prompting across all 5 harnesses
rig check --days 7

# Launch the local browser workbench
rig app --open
```

That's the surface. The scoring engine, the enhancement/context-injection logic, the session parsers for all five harnesses, the full 1,010-template library, the workbench app, the MCP server, and the V15 operator layer (catalog audit, intake packets, gates, ProofPacket templates) are all in the private repo.

## Get full access

This public repo is the teaser. The complete, production source lives in a private repo.

**Want it?** ⭐ Star this repo, then email **mike@rodgersintelligence.com** or DM **Mike Rodgers** on LinkedIn — say which product and your use case. You'll get pricing + a private-repo invite.
