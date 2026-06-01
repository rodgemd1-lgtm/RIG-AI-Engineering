# RIG AI Engineering v15

**Operator-grade AI engineering coach, prompt upload/fix workflow, prompt template library, open-source harness catalog, and deterministic v15 intake/proof system.**

Makes every coding-agent run more effective through context awareness, RIG doctrine enforcement, automatic enhancement, reviewed harness references, methodology-agent review, and ProofPacket discipline.

## What This Is

A comprehensive prompting and agent-engineering program with 20 CLI command groups, local RIG Prompt Master web app/API, MCP server, zsh hook, background daemon, HTTP proxy, reviewed open-source resource catalog, 10 methodology-agent lenses, and a 100-question intake system — all working together to improve AI-assisted coding across 5 harnesses (Claude Code, Codex, OpenCode, Hermes, GSD-Pi).

The daily front door is now `rig prompt-master`: upload or pipe any rough prompt, and RIG rewrites it with current work context from the local repo, QNAP policy, GitHub/Gitea remotes and APIs when configured, Recall API when configured, and the local RIG context pack. `rig fix-prompt` remains the compatible alias.

### Key Features

- **Prompt Scoring** — 4-axis scoring (Specificity, RIG Doctrine, Context, Actionability) with 0-100 grades
- **RIG Prompt Master** — `rig prompt-master` accepts prompt files/stdin/arguments and returns a context-grounded prompt with a RigForge DoneContract
- **Claude Design Prompt Mode** — `rig design-prompt` turns rough Claude Design requests into page-by-page walkthrough prompts with screenshot QA and RIG branding
- **Local Prompt Master App** — `rig app --open` launches a browser app for prompt upload/fix, v15 gates, catalog search, browser envelopes, contracts, and ProofPackets
- **Auto-Enhancement** — Automatically rewrites weak prompts with context, acceptance criteria, and verification
- **Closed-Loop Learning** — Executes prompts via Hermes, analyzes outcomes, tracks success patterns
- **Proactive Coaching** — Background daemon watches your workspace and injects coaching into AGENTS.md
- **Pre-Send Hook** — Scores prompts before they reach Hermes, warns if below threshold
- **V15 Operator Layer** — Auditable catalog search, full/focused intake packets, 13 proof gates, and ProofPacket templates
- **MCP Server** — 17 tools exposed via MCP protocol for any AI assistant
- **HTTP Proxy** — Transparent prompt scoring/rewriting for any AI tool
- **1,000 Prompt Templates** — Searchable across 10 categories
- **Open-Source Harness Catalog** — 50 reviewed resources, license posture, first experiment, and load triggers
- **Methodology-Agent Panel** — 10 named public-method lenses with 100 required questions for agent, harness, and product-build review
- **Cross-Harness Auditing** — Detects silos, mega-sessions, and doctrine gaps

## Installation

### Prerequisites

- macOS or Linux
- Python 3.10+
- Node.js 20+ (for the AI Engineering Coach VS Code extension)
- Hermes Agent (optional, for `rig run` execution)

### Quick Install

```bash
# Clone the repo
git clone https://github.com/rodgemd1-lgtm/RIG-AI-Engineering.git
cd RIG-AI-Engineering

# Install the CLI to ~/bin/rig
./rig-install

# Add to PATH if needed
export PATH="$HOME/bin:$PATH"
```

### Install Options

```bash
# User install (default) — installs to ~/bin/rig
./rig-install

# Global install — installs to /usr/local/bin/rig
./rig-install --global

# Force overwrite existing install
./rig-install --force

# Install Hermes pre-send hook
./rig-install --hook

# Register MCP server in Hermes config
./rig-install --mcp

# Install background watcher daemon (macOS launchd)
./rig-install --launchd
```

### Verify Installation

```bash
rig --help          # Show all commands
rig doctor          # System health check
rig watch scan      # Single workspace scan
rig v15 audit       # Validate the v15 catalogs
rig app --smoke     # Validate the local app/API/static wiring
```

## Quick Start

```bash
# Upload or pipe a rough prompt and get a fixed prompt back
rig app --open
rig fix-prompt --file prompt.md
rig prompt-master --mode claude-design --file prompt.md
rig design-prompt "fix this Claude Design walkthrough from entry point to contact page"
echo "build a browser-agent harness for RIG" | rig fix-prompt
rig fix "connect this prompt to QNAP GitHub Gitea and Recall"

# Check whether the context adapters are connected
rig context-status

# Score a prompt
rig score "fix the auth bug"

# Enhance a prompt (auto-injects context, RIG doctrine, verification)
rig enhance "fix the auth bug"

# Full closed-loop: enhance → execute via Hermes → learn
rig run "deploy model to fleet"

# Personal coaching diagnostic
rig coach

# Weekly summary report
rig report 7

# Audit all 5 harness sessions
rig check --days 7

# Generate a full v15 intake packet with all 100 questions
rig v15 intake "build a browser-agent harness for RIG"

# Generate a focused v15 packet for fast local planning
rig v15 intake "build a browser-agent harness for RIG" --fast

# Create a ProofPacket template
rig v15 proof "browser-agent harness"

# Search prompt templates
rig suggest "agent orchestration"

# A/B test two prompt variants
rig ab-test "fix bug" "fix the authentication bug in src/auth/login.js with tests"
```

## All Commands

### Prompt Intelligence
| Command | Description |
|---------|-------------|
| `rig fix-prompt [prompt]` | Fix rough prompt with current work/QNAP/GitHub/Gitea/Recall context |
| `rig fix [prompt]` | Alias for `rig fix-prompt` |
| `rig prompt-master [prompt]` | Alias for RIG Prompt Master prompt repair |
| `rig design-prompt [prompt]` | Fix Claude Design prompts with walkthrough, screenshot QA, and design polish defaults |
| `rig context-status` | Check context adapter status without fixing a prompt |
| `rig enhance <prompt>` | Score + auto-enhance with context injection |
| `rig score <prompt>` | 4-axis scoring (0-100) with detailed findings |
| `rig run <prompt>` | Enhance → Execute via Hermes → Learn outcome |
| `rig ab-test "A" "B"` | A/B test two prompt variants, declare winner |
| `rig validate` | Score the prompt in your clipboard |
| `rig suggest <query>` | Search 1000+ prompt templates |

### Learn & Improve
| Command | Description |
|---------|-------------|
| `rig learn` | Analyze latest Hermes session → extract signals |
| `rig coach` | Personal diagnostic: weaknesses + recommendations |
| `rig trends [days]` | Score trends over time (default 30 days) |
| `rig report [days]` | Summary report with trend + top prompts (default 7) |
| `rig history [n]` | Last n prompts with scores (default 10) |
| `rig stats` | Personal prompting dashboard |

### System
| Command | Description |
|---------|-------------|
| `rig check [--days n]` | Audit all 5 harness sessions |
| `rig prompt [prompt]` | Quick score (pipe or argument) |
| `rig refresh` | Refresh CLAUDE.md/AGENTS.md coaching context |
| `rig doctor` | Full system health check |
| `rig template <key>` | Fill built-in template (code-review, bug-fix, deploy, research) |
| `rig install [--hook\|--mcp\|--launchd]` | Install dependencies + integrations |
| `rig app [--open\|--smoke]` | Start or validate the local RIG Prompt Master browser app and JSON API |
| `rig watch [scan\|daemon\|status\|stop]` | Workspace watcher daemon |
| `rig proxy` | HTTP prompt proxy for automatic scoring/rewriting |
| `rig archon` | List Archon workflows |
| `rig catalog [resources\|personas\|questions]` | Show reviewed OSS resources, methodology agents, or the 100-question intake |
| `rig v15 [audit\|resources\|personas\|questions\|intake\|proof]` | Run the v15 deterministic operator layer |

## V15 Operator Layer

RIG v15 turns the open-source expansion into a deterministic operator layer for agent and harness work:

- `catalogs/open-source-agent-harnesses.yaml` — 50 GitHub resources with license posture, RIG role, first experiment, and load trigger.
- `catalogs/rig-methodology-persona-agents.yaml` — 10 methodology-inspired multi-role agents based on public engineering/product leadership methods. They are review lenses, not endorsements or impersonation.
- `catalogs/rig-methodology-question-bank.yaml` — 100 required intake/review questions, mapped 10 per methodology agent.
- `docs/rig-open-source-expansion.md` — operating guide and safety contract.
- `python/rig/rig_v15.py` — deterministic catalog, intake, audit, and ProofPacket CLI/MCP implementation.
- `python/rig/rig_prompt_fixer.py` — RIG Prompt Master prompt upload/fix workflow with read-only context adapters, Prompt Master modes, enhancement packs, and RigForge DoneContracts.
- `python/rig/rig_app_server.py` and `python/rig/app_static/` — local browser app and JSON API for the daily RIG Prompt Master workflow.

Use `rig app --open` when you want the daily browser workflow. Use `rig prompt-master` when you want RIG to repair any rough prompt and inject current context from the terminal. Use `rig design-prompt` for Claude Design prompts like page walkthroughs, website polish, screenshot repair, and RIG branding passes. Use `rig v15 audit`, `rig v15 resources`, `rig v15 personas`, `rig v15 questions`, `rig v15 intake`, and `rig v15 proof` when the work needs the full operator checklist. `rig catalog resources`, `rig catalog personas`, and `rig catalog questions` remain as raw catalog inspectors. The catalog is reference-first: do not clone or execute a third-party harness until the repo is pinned, license-reviewed, sandboxed, and captured in a ProofPacket.

### Prompt Master API

`rig app` binds to localhost and serves these read-first endpoints:

```bash
rig app --open
curl http://127.0.0.1:8765/api/health
curl http://127.0.0.1:8765/api/prompt-master/enhancements
curl http://127.0.0.1:8765/api/v15/resources
curl -X POST http://127.0.0.1:8765/api/prompt-master/fix \
  -H 'Content-Type: application/json' \
  -d '{"prompt":"walk through the website pages in Claude Design and polish them one at a time","mode":"claude-design","enhancements":["rigforge-contract","claude-design-walkthrough","screenshot-qa","proofpacket"],"screenshot_note":"attached screenshot shows walkthrough.html active in Claude Design","include_context_pack":false,"include_apis":false}'
```

### Context Adapter Setup

`rig fix-prompt` works without API keys, but these optional environment variables connect more sources:

```bash
export RIG_QNAP_MOUNT="/Volumes/RIG"          # Optional mounted QNAP path
export RIG_QNAP_IP="192.168.68.88"           # Optional QNAP reference IP
export RIG_RECALL_API_URL="https://..."      # Recall/recall.it API base URL
export RIG_RECALL_API_PATH="/search"         # Default: /search
export RIG_RECALL_API_KEY="..."              # Optional Recall API token
export RIG_GITEA_BASE_URL="https://..."      # Gitea base URL
export RIG_GITEA_REPO="owner/repo"           # Optional when no local Gitea remote exists
export RIG_GITEA_TOKEN="..."                 # Optional Gitea API token
```

GitHub context uses local git remotes by default and enriches with `gh repo view` when the GitHub CLI is installed and authenticated. Gitea and Recall use read-only API calls when configured. Secrets are never printed into prompt output.

## Integration Layers

### 1. CLI (any terminal)
```bash
rig fix-prompt --file prompt.md
rig prompt-master --mode claude-design --file prompt.md
rig design-prompt "polish this Claude Design file page by page"
echo "your prompt" | rig fix-prompt
rig enhance "your prompt"
rig run "your prompt"
```

### 2. MCP Server (any AI assistant)
Registers 17 tools in Hermes config automatically via `rig-install --mcp`:
- `rig_score_prompt` — Score a prompt
- `rig_enhance_prompt` — Analyze and enhance
- `rig_fix_prompt` — Fix any prompt with work/QNAP/GitHub/Gitea/Recall context and a RigForge DoneContract
- `rig_prompt_master_catalog` — List Prompt Master modes and enhancement packs
- `rig_context_status` — Check context adapter status
- `rig_run_prompt` — Execute and learn
- `rig_coach` — Personal diagnostic
- `rig_get_stats` — Personal stats
- `rig_get_trends` — Score trends
- `rig_suggest_template` — Search templates
- `rig_get_history` — Prompt history
- `rig_validate_clipboard` — Score clipboard
- `rig_v15_audit` — Validate v15 catalogs and hashes
- `rig_v15_resources` — Search reviewed OSS resources
- `rig_v15_personas` — Search methodology-agent lenses
- `rig_v15_questions` — Return all or filtered v15 questions
- `rig_v15_intake` — Generate a v15 intake packet

### 3. Zsh Pre-Send Hook
```bash
rig-install --hook    # Install
rig-hook-on           # Enable
# Now `hermes chat -q "prompt"` scores before sending
rig-hook-off          # Disable
```

### 4. Background Daemon (macOS)
```bash
rig-install --launchd  # Install launchd service
rig watch status       # Check daemon status
rig watch scan         # Run single scan
```
Watches workspace every 5 minutes, injects coaching into AGENTS.md.

### 5. HTTP Proxy
```bash
rig proxy --port 18787 --target http://127.0.0.1:4141
# Configure AI tools to use http://127.0.0.1:18787 as API base
# All prompts are scored and auto-rewritten if below threshold
```

## Harness Data Paths

| Harness | Data Path | Parser |
|---------|-----------|--------|
| Claude Code | `~/.claude/projects/<path>/<uuid>.jsonl` | `parser-claude.ts` |
| Codex CLI | `~/.codex/sessions/<y>/<m>/<d>/rollout-*.jsonl` | `parser-codex.ts` |
| OpenCode | `~/.local/share/opencode/storage/` | `parser-opencode.ts` |
| **Hermes** | `~/.hermes/sessions/session_*.json` | `parser-hermes.ts` (custom) |
| **GSD-Pi** | `~/.gsd/sessions/<project>/` | `parser-gsd.ts` (custom) |

## Custom Rules

| Rule | What it detects |
|------|---------------|
| `hermes-skill-usage` | Low skill invocation in Hermes sessions |
| `hermes-context-injection` | Prompts missing context injection |
| `hermes-terminal-overuse` | Raw terminal over purpose-built tools |
| `gsd-plan-verify-gaps` | Missing plan/verify cycle in GSD-Pi |
| `rig-doctrine-adherence` | RIG doctrine pattern gaps |
| `cross-harness-context-loss` | Single-harness silos (>70% in one tool) |

## Prompt Templates

10 categories, 100+ templates each in `prompt-templates/rig-prompt-templates.json`:

1. **rig-doctrine-execution** — IQRSQPI, BMS modes, gates, ProofPackets
2. **fleet-infrastructure** — Nodes, models, mesh, security
3. **agent-orchestration** — Susan, Jake, fleets, swarms
4. **content-engineering** — LinkedIn, brand, engagement
5. **client-acquisition** — Outreach, proposals, ROI
6. **product-code** — Features, APIs, releases
7. **research-intelligence** — Blueprints, signals, forecasts
8. **healthcare-verticals** — Hospital, PE, law, fintech
9. **personal-brand** — Speaking, hiring, advisory
10. **diagnostic-coaching** — Scoring, audits, optimization

## Architecture

```
rig (bash CLI)
  ├── 20 command groups
  └── → python/rig/prompt_engine.py (1700+ lines)
        ├── ContextSynthesizer (git, sessions, project)
        ├── PromptOptimizer (scoring, enhancement, lattice)
        ├── LearningEngine (outcome tracking, success patterns)
        ├── SessionAnalyzer (Hermes session post-analysis)
        ├── CoachingEngine (diagnostic, trends, recommendations)
        └── TemplateEngine (semantic search, built-in templates)
  └── → python/rig/rig_v15.py
        ├── Catalog audit (50 resources, 10 personas, 100 questions)
        ├── Deterministic ranking/search
        ├── Full/focused intake packet generation
        ├── 13 v15 gate checklist
        └── ProofPacket template generation
  └── → python/rig/rig_prompt_fixer.py
        ├── Prompt file/stdin/argument intake
        ├── Work surface, QNAP, GitHub, Gitea, Recall, and context-pack adapters
        ├── Secret redaction and approval boundaries
        └── Markdown/JSON fixed prompt output

rig-mcp-server.py — JSON-RPC stdio MCP server (17 tools)
rig-watch.py      — Background workspace daemon (launchd)
rig-proxy.py      — HTTP prompt proxy (auto-score + rewrite)
rig-hook.zsh      — Zsh pre-send hook (hermes-smart wrapper)
```

## License

MIT (upstream Microsoft AI Engineering Coach) + custom extensions MIT

<!-- AGENTFORGE:WORKFLOWS START -->
## AgentForge Workflows

**Repo maturity:** `66.84 / 100`

### 10x Plan


**Visual workflow designer:** [.agentforge/workflows.html](.agentforge/workflows.html)

### Workflows (editable)

> These workflows live in the README and are editable here. Each is a `WorkflowDoc` (`name` · BMS mode · ordered steps) that round-trips losslessly with the visual designer and the agent IR.

#### 1. rig-coach-check  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. check
2. analyze
3. refresh
4. report

#### 2. rig-coach-refresh  `A1`

_A1 · Python-only (deterministic)_

1. refresh
2. verify

#### 3. rig-coach-score  `A3`

_A3 · Agent-bounded (budget-capped)_

1. score
2. suggest
3. report

#### 4. rig-coach-template  `A1`

_A1 · Python-only (deterministic)_

1. search
2. fill
3. validate
4. report

#### 5. prompt-score-4axis  `A1`

_A1 · Python-only (deterministic)_

1. load-prompt
2. tokenize
3. score-specificity
4. score-doctrine
5. score-context
6. score-actionability
7. aggregate-grade
8. report

#### 6. prompt-enhance-inject  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. score
2. detect-weaknesses
3. inject-context
4. add-acceptance-criteria
5. add-verification
6. rewrite
7. rescore
8. report

#### 7. prompt-ab-test  `A1`

_A1 · Python-only (deterministic)_

1. parse-variants
2. score-a
3. score-b
4. diff-axes
5. declare-winner
6. report

#### 8. prompt-quick-score  `A1`

_A1 · Python-only (deterministic)_

1. read-stdin-or-arg
2. score
3. threshold-check
4. emit

#### 9. prompt-validate-clipboard  `A1`

_A1 · Python-only (deterministic)_

1. read-clipboard
2. score
3. report

#### 10. prompt-master-fix  `A3`

_A3 · Agent-bounded (budget-capped)_

1. intake-prompt
2. detect-mode
3. gather-context
4. redact-secrets
5. select-enhancements
6. rewrite
7. attach-donecontract
8. emit-md-json

#### 11. prompt-master-claude-design  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. intake
2. parse-pages
3. build-walkthrough-steps
4. add-screenshot-qa
5. add-rig-branding
6. assemble-prompt
7. report

#### 12. prompt-master-donecontract  `A1`

_A1 · Python-only (deterministic)_

1. extract-intent
2. derive-acceptance
3. derive-verification
4. set-kill-criteria
5. seal-contract

#### 13. prompt-master-enhancement-pack  `A1`

_A1 · Python-only (deterministic)_

1. list-packs
2. select
3. validate-compat
4. apply
5. report

#### 14. design-prompt-screenshot-repair  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. intake-screenshot-note
2. infer-active-page
3. build-repair-steps
4. add-qa-loop
5. emit

#### 15. context-status-check  `A1`

_A1 · Python-only (deterministic)_

1. probe-git
2. probe-qnap
3. probe-github
4. probe-gitea
5. probe-recall
6. probe-context-pack
7. report-matrix

#### 16. context-git-worksurface  `A1`

_A1 · Python-only (deterministic)_

1. read-git-status
2. read-recent-commits
3. read-branch
4. read-changed-files
5. summarize

#### 17. context-github-enrich  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. read-remotes
2. check-gh-auth
3. fetch-repo-view
4. parse-metadata
5. merge-into-context

#### 18. context-gitea-fetch  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-gitea-config
2. validate-token
3. fetch-repo
4. fetch-issues
5. merge-into-context

#### 19. context-recall-search  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-recall-config
2. build-query
3. call-recall-search
4. dedupe-results
5. merge-into-context

#### 20. context-qnap-mount  `A1`

_A1 · Python-only (deterministic)_

1. resolve-mount
2. read-policy
3. scan-paths
4. summarize
5. merge

#### 21. context-secret-redaction  `A1`

_A1 · Python-only (deterministic)_

1. scan-for-secrets
2. classify
3. redact
4. verify-clean
5. emit

#### 22. v15-catalog-audit  `A1`

_A1 · Python-only (deterministic)_

1. load-catalogs
2. validate-schema
3. recompute-hashes
4. compare-pinned
5. report-drift

#### 23. v15-intake-full  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. parse-request
2. classify-domain
3. select-all-questions
4. map-to-personas
5. assemble-packet
6. attach-gate-checklist
7. emit

#### 24. v15-intake-focused  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. parse-request
2. classify-domain
3. select-priority-questions
4. assemble
5. emit

#### 25. v15-proofpacket-generate  `A1`

_A1 · Python-only (deterministic)_

1. slugify-title
2. resolve-artifact-path
3. fill-template
4. add-gate-checklist
5. write

#### 26. v15-gate-checklist  `A1`

_A1 · Python-only (deterministic)_

1. load-gates
2. bind-to-task
3. mark-status
4. report

#### 27. v15-approval-boundary  `A4`

_A4 · LLM-agent-free (crew)_

1. classify-action
2. detect-external-impact
3. block-if-unsafe
4. request-human-approval
5. record-decision
6. proceed-or-halt

#### 28. catalog-resource-search  `A1`

_A1 · Python-only (deterministic)_

1. load-catalog
2. parse-query
3. rank
4. format-results

#### 29. catalog-resource-review  `A3`

_A3 · Agent-bounded (budget-capped)_

1. fetch-repo-metadata
2. assess-license
3. assess-rig-role
4. define-first-experiment
5. set-load-trigger
6. draft-catalog-entry

#### 30. catalog-harness-adopt  `A4`

_A4 · LLM-agent-free (crew)_

1. pin-commit
2. license-review
3. clone-to-sandbox
4. sandbox-execute
5. capture-proofpacket
6. human-approval-gate
7. promote-to-catalog

#### 31. catalog-license-posture  `A1`

_A1 · Python-only (deterministic)_

1. load-entries
2. read-licenses
3. classify-posture
4. flag-conflicts
5. report

#### 32. persona-lens-search  `A1`

_A1 · Python-only (deterministic)_

1. load-personas
2. parse-query
3. rank
4. format

#### 33. persona-panel-review  `A3`

_A3 · Agent-bounded (budget-capped)_

1. select-relevant-lenses
2. load-question-subset
3. run-lens-reviews
4. collect-findings
5. dedupe-severity
6. synthesize-report

#### 34. question-bank-filter  `A1`

_A1 · Python-only (deterministic)_

1. load-question-bank
2. apply-filter
3. map-to-personas
4. emit

#### 35. methodology-agent-build-review  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. intake-build-spec
2. map-questions
3. answer-or-flag
4. score-readiness
5. report-gaps

#### 36. harness-session-audit  `A1`

_A1 · Python-only (deterministic)_

1. discover-session-paths
2. parse-each-harness
3. compute-metrics
4. apply-rules
5. aggregate
6. report

#### 37. harness-parse-claude  `A1`

_A1 · Python-only (deterministic)_

1. locate-jsonl
2. stream-parse
3. extract-events
4. normalize
5. emit

#### 38. harness-parse-codex  `A1`

_A1 · Python-only (deterministic)_

1. locate-rollouts
2. stream-parse
3. normalize
4. emit

#### 39. harness-parse-opencode  `A1`

_A1 · Python-only (deterministic)_

1. locate-storage
2. parse
3. normalize
4. emit

#### 40. harness-parse-hermes  `A1`

_A1 · Python-only (deterministic)_

1. locate-sessions
2. parse
3. normalize
4. emit

#### 41. harness-parse-gsd  `A1`

_A1 · Python-only (deterministic)_

1. locate-project-sessions
2. parse
3. normalize
4. emit

#### 42. rule-cross-harness-silo  `A1`

_A1 · Python-only (deterministic)_

1. aggregate-by-harness
2. compute-distribution
3. threshold-check
4. flag-silo
5. report

#### 43. rule-mega-session-detect  `A1`

_A1 · Python-only (deterministic)_

1. measure-session-sizes
2. threshold-check
3. flag
4. recommend-split

#### 44. rule-doctrine-adherence  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-doctrine-patterns
2. scan-sessions
3. classify-gaps
4. score-adherence
5. report

#### 45. rule-skill-usage-audit  `A1`

_A1 · Python-only (deterministic)_

1. count-skill-calls
2. compare-baseline
3. flag-low
4. report

#### 46. rule-context-injection-gap  `A1`

_A1 · Python-only (deterministic)_

1. scan-prompts
2. check-context-markers
3. flag-missing
4. report

#### 47. rule-terminal-overuse  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. scan-tool-calls
2. classify-terminal-vs-tool
3. compute-ratio
4. flag
5. recommend

#### 48. run-closed-loop  `A4`

_A4 · LLM-agent-free (crew)_

1. enhance-prompt
2. create-run-envelope
3. dispatch-to-hermes
4. monitor-execution
5. capture-outcome
6. learn-signals
7. proofpacket

#### 49. learn-session-signals  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-latest-session
2. extract-events
3. classify-outcome
4. extract-patterns
5. update-learning-store

#### 50. coach-diagnostic  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-history
2. compute-weakness-profile
3. rank-issues
4. generate-recommendations
5. report

#### 51. coach-trends  `A1`

_A1 · Python-only (deterministic)_

1. load-scored-history
2. bucket-by-time
3. compute-trend
4. chart
5. report

#### 52. coach-weekly-report  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. gather-window
2. compute-stats
3. select-top-prompts
4. narrate-summary
5. emit

#### 53. coach-stats-dashboard  `A1`

_A1 · Python-only (deterministic)_

1. load-history
2. compute-metrics
3. format-dashboard

#### 54. template-semantic-search  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-templates
2. embed-or-rank-query
3. score-relevance
4. return-top

#### 55. template-builtin-fill  `A1`

_A1 · Python-only (deterministic)_

1. select-template
2. collect-slots
3. fill
4. validate
5. emit

#### 56. template-category-browse  `A1`

_A1 · Python-only (deterministic)_

1. load-index
2. filter-category
3. paginate
4. emit

#### 57. mcp-server-serve  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-tool-registry
2. start-stdio-loop
3. route-rpc
4. invoke-tool
5. return-result

#### 58. vscode-extension-activate  `A1`

_A1 · Python-only (deterministic)_

1. register-commands
2. init-webview-panels
3. wire-rpc
4. warm-cache
5. ready

#### 59. app-local-serve  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. bind-localhost
2. mount-static
3. register-api-routes
4. wire-prompt-master
5. serve

#### 60. app-smoke-validate  `A1`

_A1 · Python-only (deterministic)_

1. check-routes
2. check-static
3. check-api-contracts
4. report

#### 61. zsh-presend-hook  `A1`

_A1 · Python-only (deterministic)_

1. intercept-prompt
2. score
3. threshold-check
4. warn-or-pass
5. forward

#### 62. watch-daemon-scan  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. scan-workspace
2. compute-coaching
3. diff-agents-md
4. write-injection
5. log

#### 63. http-proxy-rewrite  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. accept-request
2. extract-prompt
3. score
4. rewrite-if-below
5. forward-to-target
6. relay-response

#### 64. install-cli  `A1`

_A1 · Python-only (deterministic)_

1. resolve-target
2. check-existing
3. copy-binary
4. set-path-hint
5. verify

#### 65. install-hook  `A1`

_A1 · Python-only (deterministic)_

1. locate-shell-rc
2. inject-hook-source
3. verify
4. print-enable-cmd

#### 66. install-mcp-register  `A1`

_A1 · Python-only (deterministic)_

1. locate-hermes-config
2. add-server-entry
3. validate-json
4. verify

#### 67. install-launchd  `A1`

_A1 · Python-only (deterministic)_

1. render-plist
2. write-to-launchagents
3. load-service
4. verify-running

#### 68. package-desktop-build  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. install-deps
2. build-next
3. wrap-desktop
4. smoke
5. emit-artifact

#### 69. doctor-health-check  `A1`

_A1 · Python-only (deterministic)_

1. check-python
2. check-node
3. check-adapters
4. check-installs
5. report

#### 70. doctrine-enforce-scan  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. load-doctrine
2. scan-target
3. classify-violations
4. score
5. report

#### 71. repo-maturity-score  `A1`

_A1 · Python-only (deterministic)_

1. gather-signals
2. weight-signals
3. compute-score
4. write-readme-block

#### 72. readme-workflow-sync  `A1`

_A1 · Python-only (deterministic)_

1. read-json-workflows
2. render-md-block
3. diff-readme
4. write-between-markers
5. verify-roundtrip

#### 73. release-tag-publish  `A4`

_A4 · LLM-agent-free (crew)_

1. run-full-test-suite
2. bump-version
3. build-artifacts
4. proofpacket
5. human-approval-gate
6. push-tag-and-publish

#### 74. proofpacket-seal  `A1`

_A1 · Python-only (deterministic)_

1. gather-evidence
2. attach-commands
3. attach-outputs
4. hash
5. write-sealed

#### 75. bms-band-classify  `A2`

_A2 · Hybrid (schema-constrained LLM)_

1. parse-steps
2. detect-determinism
3. detect-external-impact
4. assign-band
5. justify
<!-- AGENTFORGE:WORKFLOWS END -->
