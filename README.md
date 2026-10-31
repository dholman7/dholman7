## Dan Holman

Senior SDET moving into AI engineering. I build agents that write and verify tests, and the evaluation harnesses that show whether those agents actually work. 14+ years in test infrastructure, automation frameworks, and developer tooling: Python, TypeScript, AWS, Playwright, and contract testing.

**Portfolio: [dholman7.github.io](https://dholman7.github.io/)**, a visual guide to how these projects fit together and how to run each one.

### Featured

| Project | What it is | Result |
|---|---|---|
| [storywright](https://github.com/dholman7/storywright) | LangGraph + Claude agent: turns a Jira story into Playwright API tests, runs them against the real app, repairs what fails without weakening an assertion, opens the PR, and closes the issue on merge | 97% of held-out trials (58/60) vs 60% for a single call on the same model, at $0.0028 per trial |
| [agent-eval-gate](https://github.com/dholman7/agent-eval-gate) | Benchmark runner and CI gate for test-writing agents: 32 tasks, 32 seeded bugs, Wilson confidence intervals, record/replay, a GitHub Action | Fails a PR only when results drop by more than run-to-run noise |
| [agent-dev-skills](https://github.com/dholman7/agent-dev-skills) | Claude Code plugin with review-loop: PR review that checks every citation and re-derives each finding before commenting, then re-reviews new commits | On Opus 5.5, catches 29 of 32 seeded bugs with 0 false alarms in 24 harmless changes, 14 of them built to look risky |
| [ci-context-mcp](https://github.com/dholman7/ci-context-mcp) | Read-only MCP server that gives Claude Code, Cursor, or any MCP client CI runs, failure summaries, logs, coverage, and PR checks from GitHub Actions | GET-only client, repo allowlist, and the token never leaves GitHub; tested through the MCP SDK's in-process client |
| [agent-telemetry](https://github.com/dholman7/agent-telemetry) | Static Next.js dashboard over every agent-eval-gate run: success and bug-detection intervals per split, a task × trial grid, and an OpenTelemetry trace and agent log for each trial | [Live site](https://dholman7.github.io/agent-telemetry/), 12 runs, rebuilt weekly from published results |
| [vendor-intake-app](https://github.com/dholman7/vendor-intake-app) | Next.js + FastAPI app used as the system under test: Gherkin specs, tenant isolation, audit trail, generated API types | 68 backend tests, 27 Playwright tests with accessibility scans (7 written by Storywright from Jira stories), CI on every push |

### Claims and where to check them

| Skill | Evidence |
|---|---|
| Agent evaluation | agent-eval-gate: frozen dev/held-out split, seeded bugs validated against reference tests, intervals on every rate |
| Tool orchestration, failure handling | storywright: bounded write/verify/repair graph, typed failure diagnosis, read-only repo tools, a deterministic guard on every repair |
| Claude Code skills and plugins | agent-dev-skills: a validated plugin and marketplace manifest, a skill that asks before posting, and the same pipeline as a CLI and GitHub Action |
| MCP | ci-context-mcp: six read-only tools on the MCP Python SDK 2.x, with a security model covering allowlisting, credential handling, and untrusted log text |
| Observability | agent-telemetry: an OpenTelemetry trace per trial with GenAI token attributes, drawn as waterfalls beside the harness verdict and agent log |
| LLM application development | storywright and agent-eval-gate's Claude baseline: structured outputs, prompt caching, model profiles, cost accounting |
| Test automation | vendor-intake-app: pytest at 97% coverage, Playwright UI and API suites, axe accessibility checks |
| React and TypeScript | vendor-intake-app frontend (Next.js 16, strict TypeScript, types generated from OpenAPI); agent-telemetry (React 19, static export, charts built without a chart library) |
| CI/CD | GitHub Actions with secret scanning in every project repo; OpenAPI and type drift checks and Docker builds in vendor-intake-app; a reusable composite action in agent-eval-gate |

### Contact

[LinkedIn](https://linkedin.com/in/danxholman) · danxholman@gmail.com
