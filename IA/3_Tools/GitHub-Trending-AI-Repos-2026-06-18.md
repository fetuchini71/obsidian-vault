1|# Trending GitHub AI Repos — June 18, 2026
2|
3|**Researched for:** Braian's AI-automation stack (Hermes Agent, n8n, OpenClaw, Odysseus, Obsidian)
4|
5|---
6|
7|## Top 5 Most Interesting for an AI-Automation Stack
8|
9|### 1. 🏆 [nexu-io/open-design](https://github.com/nexu-io/open-design) ⭐ 67.3k
10|**Local-first, open-source Claude Design alternative.** Native desktop app with 259+ Skills, 142+ Design Systems. Web/desktop/mobile prototyping, slides, images, videos, HyperFrames. Sandboxed preview, HTML/PDF/PPTX/MP4 export. Works with Claude Code, OpenClaw, Codex, Cursor, OpenCode, Qwen, Copilot, **Hermes**, Kimi & 17+ CLIs.
11|- **Why it matters:** Directly compatible with Hermes Agent and OpenClaw. Massive skill ecosystem for UI prototyping. Tags include `hermes-agent` and `open-claw`.
12|
13|### 2. 🔥 [chopratejas/headroom](https://github.com/chopratejas/headroom) ⭐ 33.2k (+9,475 this week!)
14|**Compress tool outputs, logs, files, and RAG chunks before they reach the LLM.** 60-95% fewer tokens, same answers. Library, proxy, and MCP server.
15|- **Why it matters:** Token-cost optimization is critical for any AI-automation stack. Works as MCP server → drop into Hermes/n8n/OpenClaw. Saves ~80% on LLM costs.
16|
17|### 3. 🧠 [DeusData/codebase-memory-mcp](https://github.com/DeusData/codebase-memory-mcp) ⭐ 6.7k (+1,097 this week)
18|**High-performance code intelligence MCP server.** Indexes codebases into a persistent knowledge graph — average repo in milliseconds. 158 languages, sub-ms queries, 99% fewer tokens. Single static binary, zero dependencies.
19|- **Why it matters:** Ideal for Hermes and Obsidian workflows — gives coding agents persistent memory of your codebase. Written in C for performance.
20|
21|### 4. 🐝 [activeloopai/hivemind](https://github.com/activeloopai/hivemind) ⭐ 1.3k (+538 this week)
22|**Turns your traces into reusable skills across agents.** TypeScript/React.
23|- **Why it matters:** Directly solves the "skill reuse" problem across Hermes, n8n, OpenClaw, and Odysseus. Extract patterns from agent traces and deploy as reusable skills.
24|
25|### 5. 🛡️ [NVIDIA/SkillSpector](https://github.com/NVIDIA/SkillSpector) ⭐ 7.8k (+5,257 this week)
26|**Security scanner for AI agent skills.** Detect vulnerabilities, malicious patterns, and security risks in agent skills.
27|- **Why it matters:** As you build agent skills for your stack, you need security scanning. NVIDIA-backed, Python, active development.
28|
29|### 6. 📡 [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) ⭐ 44.3k (+5,235 this week)
30|**AI agent skill that researches any topic across Reddit, X, YouTube, HN, Polymarket, and the web** — then synthesizes a grounded summary. Python.
31|- **Why it matters:** Plug-and-play research skill for Hermes Agent. Great for adding web-intelligence gathering to your agent stack.
32|
33|---
34|
35|## Honorable Mentions
36|
37|| Repo | Stars | Why |
38||------|-------|-----|
39|| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | 62.8k ⭐ | Production-grade engineering skills for AI coding agents. Google engineer-curated. |
40|| [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach) | 34.1k ⭐ | Zero-API-fee social media scraper CLI (Twitter, Reddit, YouTube, GitHub, Bilibili). |
41|| [Mintplex-Labs/anything-llm](https://github.com/Mintplex-Labs/anything-llm) | 61.8k ⭐ | Local-first agent experience. Tags include `hermes-agent` and `open-claw` |
42|| [kenn-io/agentsview](https://github.com/kenn-io/agentsview) | 2.8k ⭐ | Session search, analytics, and token stats for coding agents (Claude Code, Codex, +20). |
43|| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 58.9k ⭐ | Memory layer for AI agents — smart agent memory |
44|| [babel/babel](https://github.com/babel/babel) | 44k ⭐ | JS compiler (TS trending) |
45|| [makeplane/plane](https://github.com/makeplane/plane) | 51.7k ⭐ | Open-source Jira/Linear alternative |
46|| [refactoringhq/tolaria](https://github.com/refactoringhq/tolaria) | 16.7k ⭐ | Desktop app to manage markdown knowledge bases (Obsidian-like) |
47|
48|---
49|
50|## Sources Visited
51|1. https://github.com/trending?since=weekly — Top AI/Python weekly trending
52|2. https://github.com/topics/awesome-mcp-servers — MCP server ecosystem
53|3. https://github.com/topics/ai-agents — AI agent frameworks & tools
54|4. https://github.com/trending/typescript?since=weekly — TypeScript weekly trending
55|
56|---
57|
58|## Key Themes
59|- **MCP everything** — MCP servers have exploded. headroom, codebase-memory-mcp, SkillSpector all ship as MCP servers.
60|- **Agent skills marketplace** — The "skill" concept (championed by Hermes) is now mainstream. agent-skills (62.8k), pm-skills (19.5k), awesome-claude-skills (65.1k) all pure skill collections.
61|- **Token optimization** — headroom (+9,475/week) proves token compression is the #1 pain point.
62|- **Trace → Skill pipeline** — hivemind and agentsview both address the "capture agent sessions and turn them into skills" workflow.
63|