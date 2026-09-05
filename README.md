# Hi, I'm ordinary-s

### Java Backend × AI Agent Engineer

Building reliable AI Agent systems with Java, Spring Boot, and LLM engineering.

**Agent Runtime · Tool Calling · MCP · State Recovery · Distributed Systems**

## About Me

I focus on the backend engineering behind AI agents: restoring conversation state safely, coordinating execution across replicas, and making tool and protocol behavior predictable. My open source contributions below document the problems, implementation choices, and regression tests.

## Engineering Profile

| Area | Engineering interests |
| --- | --- |
| Java backend | Java, Spring Boot, Spring MVC / WebFlux, distributed systems |
| Agent runtime | Agent State Recovery, persisted state, failure propagation, subagents and hooks |
| Tools & protocols | MCP, Tool Calling, tool filtering, execution and security boundaries |
| Data & retrieval | PostgreSQL, Redis, Elasticsearch, Milvus, RAG and retrieval pipelines |

## Current Focus

- **Reliable agent execution:** state restoration, Agent Resume, atomic ownership, and distributed coordination.
- **LLM application infrastructure:** MCP integration, tool lifecycles, RAG, Hybrid Retrieval, and Reranker evaluation.
- **Open Source Contribution:** reproducible failures, root cause analysis, focused fixes, benchmarks, and regression testing.

## Tech Stack

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=java%2Cspring%2Cpython%2Cpostgres%2Credis%2Celasticsearch%2Cdocker%2Ckubernetes%2Cgit%2Cgithub%2Clinux%2Cmaven%2Cgradle&amp;perline=7&amp;theme=dark" />
  <source media="(prefers-color-scheme: light)" srcset="https://skillicons.dev/icons?i=java%2Cspring%2Cpython%2Cpostgres%2Credis%2Celasticsearch%2Cdocker%2Ckubernetes%2Cgit%2Cgithub%2Clinux%2Cmaven%2Cgradle&amp;perline=7&amp;theme=light" />
  <img alt="Java, Spring Boot, Python, PostgreSQL, Redis, Elasticsearch, Docker, Kubernetes, Git, GitHub, Linux, Maven, Gradle" src="https://skillicons.dev/icons?i=java%2Cspring%2Cpython%2Cpostgres%2Credis%2Celasticsearch%2Cdocker%2Ckubernetes%2Cgit%2Cgithub%2Clinux%2Cmaven%2Cgradle&amp;perline=7&amp;theme=light" />
</picture>

![Milvus](https://img.shields.io/badge/Milvus-Vector%20Database-0077C8?style=flat-square)

**AI engineering:** LLM · RAG · AI Agent · MCP · Tool Calling · Agent Runtime · State Recovery · Hybrid Retrieval · Reranker

## Selected Open Source Contributions

PR authorship and status verified on **2026-09-06**. Each link opens the upstream PR and its current status.

### ✅ Merged

**[AgentScope Java #2760 — Propagate agent state load failures](https://github.com/agentscope-ai/agentscope-java/pull/2760)**<br>
Agent Runtime · Agent State Recovery · Persisted State

Propagated state loading and decoding failures instead of silently creating an empty `AgentState`. This prevents failed recovery from being treated as a new session and potentially overwriting valid persisted conversation state. Added regression coverage for failure, missing-state, restoration, and cache/persistence integrity paths.

**[DBX #7315 — Reduce HTTP tunnel round-trip latency](https://github.com/t8y2/dbx/pull/7315)**<br>
Root Cause Analysis · Network / I/O Latency · Adaptive Polling

Traced sequential exchange latency to the PHP worker's socket-only wait, which could not be woken by incoming file-queue writes. Added bounded adaptive polling and regression tests for forwarding, polling transitions, and shutdown.

| Benchmark: 100 sequential round trips | Before | After |
| --- | ---: | ---: |
| Total time | 20.100 s | 1.073 s |

**Approximately 18.7× faster in this benchmark.** Measured with the real PHP worker and file queues on PHP 7.4/Linux against a local deterministic TCP echo target; this is not a general database performance claim.

### 🔍 In Review

These PRs are open and have not been merged.

**[AgentScope Java #2890 — Share resume coordination state across replicas](https://github.com/agentscope-ai/agentscope-java/pull/2890)**<br>
Multi-replica · Redis · Lua · Atomic Ownership · Agent Resume

Proposes a shared resume state store, Redis Lua scripts for atomic ownership and state transitions, and Spring MVC / WebFlux integration. Tests cover cross-replica coordination and competing claims. Hard-crash stale ownership remains a documented limitation; lease renewal and fencing are follow-up work.

**[AgentScope Java #2996 — Inherit parent hooks in declared subagents](https://github.com/agentscope-ai/agentscope-java/pull/2996)**<br>
Subagent · Hooks · Tool Calling · Agent Harness · Security Boundaries

Proposes inheriting explicitly configured parent hooks in declared subagents while applying declaration and workspace tool filters to hook-contributed tools. Regression tests cover child tool execution, argument interception, denied tools, and hook ordering.

**[MCP Java SDK #1098 — Fix roots/list_changed handling for stateful clients](https://github.com/modelcontextprotocol/java-sdk/pull/1098)**<br>
Java · MCP · Stateful Client · Notifications · Protocol Runtime

Proposes skipping unnecessary roots listing when no roots change consumer is registered, so `roots/list_changed` notification handling does not block until the request timeout. Includes integration regression coverage.

## GitHub Analytics

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./profile/stats-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="./profile/stats.svg" />
  <img alt="ordinary-s GitHub statistics" src="./profile/stats.svg" width="420" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./profile/top-langs-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="./profile/top-langs.svg" />
  <img alt="Languages across ordinary-s public repositories" src="./profile/top-langs.svg" width="330" />
</picture>

Public activity cards generated daily with [GitHub Readme Stats Action](https://github.com/stats-organization/github-readme-stats-action). Language distribution reflects repository code, not proficiency or the full scope of upstream contributions.

## 3D Contribution Graph

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./profile-3d-contrib/profile-night-rainbow.svg" />
  <source media="(prefers-color-scheme: light)" srcset="./profile-3d-contrib/profile-green.svg" />
  <img alt="ordinary-s 3D contribution graph" src="./profile-3d-contrib/profile-night-rainbow.svg" width="900" />
</picture>

## Contribution Snake

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ordinary-s/ordinary-s/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/ordinary-s/ordinary-s/output/github-snake.svg" />
  <img alt="Snake animation of ordinary-s GitHub contributions" src="https://raw.githubusercontent.com/ordinary-s/ordinary-s/output/github-snake.svg" width="900" />
</picture>
