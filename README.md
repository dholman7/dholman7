## Dan Holman

SDET who builds and evaluates AI coding agents. I build agents that write and verify tests, and the evaluation harnesses that show whether those agents actually work.

### [See the portfolio: dholman7.github.io](https://dholman7.github.io/)

A visual guide to the six projects below: what each one does, how they fit together, and how to run each one. Every number here and there is recomputed from the repos by a CI check, and [How this was built](https://dholman7.github.io/built.html) covers working with Claude Code as the implementer.

### About me

I've spent 14+ years making software trustworthy: test infrastructure, automation frameworks, and the developer tooling around them. Most recently, as a senior SDET, I ran Pact contract-testing infrastructure on AWS with can-i-deploy release gating and smoke-test auto-rollback, published shared Python and TypeScript verification packages and composite GitHub Actions used across teams, built a serverless synthetic test-data factory on Lambda and Step Functions, and built internal tools with React front-ends for product and engineering teams. Before that, I built Selenium, Appium, and Python API test frameworks for AWS cloud and mobile products, and test frameworks for aerospace and defense quality-management software.

Lately my focus is AI in the software lifecycle: agents that generate tests, skills that encode a team's standards, and the verification that decides whether AI output can be trusted. The projects here are independent work that shows those ideas end to end, in public, so anyone can run them and check the results.

**Python · TypeScript · Playwright · AWS · Contract testing · Claude Code · MCP · LangGraph**

### Featured

| Project | What it is | Result |
|---|---|---|
| [storywright](https://github.com/dholman7/storywright) | LangGraph + Claude agent: turns a Jira story into Playwright API or UI tests, runs them against the real app, repairs what fails (a parsing guard rejects repairs that test less, checked in CI against <!--claim:sw.guard.rejects-->30<!--/claim--> weakening patterns), opens the PR, and closes the issue on merge | On <!--claim:v3.tasks-->15<!--/claim--> blind held-out tasks, catches <!--claim:v3.sw.bugs-->86%<!--/claim--> of seeded bugs on Haiku 5.5 (<!--claim:v3.opus.bugs-->95%<!--/claim--> on Opus), level with plain Claude Code (<!--claim:v3.cc.bugs-->89%<!--/claim-->) at about a third of the cost; prompt injection <!--claim:inj.sw.before-->7/72<!--/claim--> → <!--claim:inj.sw.after-->0/72<!--/claim--> trials after its defenses |
| [agent-eval-gate](https://github.com/dholman7/agent-eval-gate) | Benchmark runner and CI gate for test-writing agents: <!--claim:bench.tasks-->42<!--/claim--> tasks, <!--claim:bench.bugs-->42<!--/claim--> seeded bugs, Wilson confidence intervals, record/replay, a GitHub Action | A paired, task-by-task gate: catches a 20-point drop <!--claim:gate.power20-->87%<!--/claim--> of the time at 20 tasks × 3 trials (interval overlap: <!--claim:gate.overlap20-->47%<!--/claim-->) |
| [agent-dev-skills](https://github.com/dholman7/agent-dev-skills) | Claude Code plugin with review-loop: PR review that checks every citation and re-derives each finding before commenting, then re-reviews new commits | On Opus 5.5, names the defect in <!--claim:rl.opus.caught-->29<!--/claim--> of <!--claim:rl.bugs-->32<!--/claim--> seeded bugs in each of 3 runs (an LLM judge scores this; it agrees with blind hand labels at κ = <!--claim:rl.judge_kappa-->0.86<!--/claim-->) with <!--claim:rl.false_alarms-->0<!--/claim--> false alarms in <!--claim:rl.clean_total-->24<!--/claim--> harmless changes, <!--claim:rl.clean_hard-->14<!--/claim--> of them built to look risky |
| [ci-context-mcp](https://github.com/dholman7/ci-context-mcp) | Read-only MCP server that gives Claude Code, Cursor, or any MCP client CI runs, failure summaries, logs, coverage, and PR checks from GitHub Actions | GET-only client, repo allowlist, and the token never leaves GitHub; tested through the MCP SDK's in-process client |
| [agent-telemetry](https://github.com/dholman7/agent-telemetry) | Static Next.js dashboard over every agent-eval-gate run: success and bug-detection intervals per split, a task × trial grid, and an OpenTelemetry trace and agent log for each trial | [Live site](https://dholman7.github.io/agent-telemetry/), <!--claim:tel.runs-->21<!--/claim--> runs, plus extraction-eval and prompt-injection pages, rebuilt weekly from published results |
| [vendor-intake-app](https://github.com/dholman7/vendor-intake-app) | Next.js + FastAPI app used as the system under test: Gherkin specs, tenant isolation, audit trail, generated API types, and optional Claude document extraction whose every value is grounded in the document's own text | <!--claim:vi.backend_tests-->93<!--/claim--> backend tests, <!--claim:vi.playwright_tests-->31<!--/claim--> Playwright tests with accessibility scans (<!--claim:vi.generated_tests-->7<!--/claim--> written by Storywright from Jira stories), CI on every push |

### Claims and where to check them

| Skill | Evidence |
|---|---|
| Agent evaluation | agent-eval-gate: frozen dev/held-out split, seeded bugs validated against reference tests, intervals on every rate, a paired regression gate with its detection power published |
| Tool orchestration, failure handling | storywright: bounded write/verify/repair graph, typed failure diagnosis, read-only repo tools, a deterministic guard on every repair |
| Claude Code skills and plugins | agent-dev-skills: a validated plugin and marketplace manifest, a skill that asks before posting, and the same pipeline as a CLI and GitHub Action |
| MCP | ci-context-mcp: <!--claim:mcp.tools-->six<!--/claim--> read-only tools on the MCP Python SDK 2.x, with a security model covering allowlisting, credential handling, and untrusted log text |
| Observability | agent-telemetry: an OpenTelemetry trace per trial with GenAI token attributes, drawn as waterfalls beside the harness verdict and agent log |
| LLM application development | storywright and agent-eval-gate's Claude baseline: structured outputs, prompt caching, model profiles, cost accounting |
| Claims that stay true | [dholman7.github.io](https://github.com/dholman7/dholman7.github.io/blob/main/claims/check.py): a CI check recomputes every number on the portfolio page and this README from the repos and fails on drift |
| Testing an LLM feature | vendor-intake-app's extraction evals: a generated set of <!--claim:ext.documents-->75<!--/claim--> documents with known truth, <!--claim:ext.accuracy-->99%<!--/claim--> held-out field accuracy with <!--claim:ext.confident_wrong-->0<!--/claim--> values wrong at high confidence, prompt injection tested, and a keyless CI gate that replays recorded model outputs |
| Test automation | vendor-intake-app: pytest at <!--claim:vi.coverage-->96%<!--/claim--> coverage, Playwright UI and API suites, axe accessibility checks |
| React and TypeScript | vendor-intake-app frontend (Next.js 16, strict TypeScript, types generated from OpenAPI); agent-telemetry (React 19, static export, charts built without a chart library) |
| CI/CD | GitHub Actions with secret scanning in every project repo; OpenAPI and type drift checks and Docker builds in vendor-intake-app; a reusable composite action in agent-eval-gate |

### Contact

[LinkedIn](https://linkedin.com/in/danxholman) · danxholman@gmail.com
