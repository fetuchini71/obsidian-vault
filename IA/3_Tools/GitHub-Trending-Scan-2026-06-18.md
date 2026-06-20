1|---
2|tags: [github-trending, ai-tools, scan, 2026-06]
3|---
4|
5|# GitHub Trending Scan — June 18, 2026
6|
7|> Scanned GitHub Trending (weekly) for AI tools and developer tools that could integrate with Braian's stack. Stack context: Hermes Agent, n8n, OpenClaw, Odysseus, Obsidian. Prioritized: MCP support, CLI interfaces, n8n nodes, Obsidian integration.
8|
9|---
10|
11|## 🥇 TOP PICKS (Most Relevant to Braian's Stack)
12|
13|### 1. chopratejas/headroom — 🚀 HIGHEST PRIORITY
14|- **Language:** Python | ⭐ 32.2k | +9.5k this week
15|- **Description:** Compress tool outputs, logs, files, and RAG chunks before they reach the LLM. 60-95% fewer tokens, same answers.
16|- **Why it fits:** Ships as **library, proxy, AND MCP server**. Has `.claude-plugin` directory. Directly reduces token costs in Hermes Agent by compressing tool output before it reaches the LLM. Could be integrated as a Hermes middleware/plugin.
17|- **Links:** MCP, CLI, Hermes plugin integration
18|- **URL:** https://github.com/chopratejas/headroom
19|
20|### 2. DeusData/codebase-memory-mcp — MCP Code Intelligence
21|- **Language:** Go/Rust | ⭐ 6k | Trending this week
22|- **Description:** High-performance code intelligence MCP server. Indexes codebases into a persistent knowledge graph. 158 languages, sub-ms queries, single static binary.
23|- **Why it fits:** **Pure MCP implementation** — directly usable as an MCP server with Hermes Agent. Could analyze OpenClaw/Odysseus codebases.
24|- **URL:** https://github.com/DeusData/codebase-memory-mcp
25|
26|### 3. activeloopai/hivemind — Skills from Traces
27|- **Language:** TypeScript | ⭐ 1.3k | +538 this week
28|- **Description:** Hivemind turns your traces into reusable skills across agents.
29|- **Why it fits:** Has `.claude-plugin` directory. Could turn Hermes agent execution traces into reusable skills. Concept aligns perfectly with Hermes skill ecosystem.
30|- **URL:** https://github.com/activeloopai/hivemind
31|
32|### 4. NVIDIA/SkillSpector — Agent Skill Security Scanner
33|- **Language:** Python | ⭐ 7.7k | +5.3k this week
34|- **Description:** Security scanner for AI agent skills. Detect vulnerabilities, malicious patterns, and security risks before installing agent skills.
35|- **Why it fits:** **CLI-based** security scanner. Could be integrated as a pre-installation hook in Hermes Agent to vet skills before loading. Docker-based deployment.
36|- **URL:** https://github.com/NVIDIA/SkillSpector
37|
38|### 5. Panniantong/Agent-Reach — Internet Access for Agents
39|- **Language:** Python | ⭐ 33.7k | +6.9k this week
40|- **Description:** Give your AI agent eyes to see the entire internet. Read & search Twitter, Reddit, YouTube, GitHub, Bilibili — one CLI, zero API fees.
41|- **Why it fits:** **CLI tool** — directly usable as a Hermes Agent tool for web/social media research. No API keys needed.
42|- **URL:** https://github.com/Panniantong/Agent-Reach
43|
44|---
45|
46|## 🥈 STRONG CANDIDATES
47|
48|### 6. addyosmani/agent-skills
49|- **Language:** Shell | ⭐ 62.5k | +11.7k this week
50|- Production-grade engineering skills for AI coding agents. Template-based patterns for reliable engineering workflows. Could inspire Hermes skill patterns.
51|- **URL:** https://github.com/addyosmani/agent-skills
52|
53|### 7. mvanhorn/last30days-skill
54|- **Language:** Python | ⭐ 44.1k | +5.2k this week
55|- AI agent skill researching topics across Reddit, X, YouTube, HN, Polymarket. Instant Hermes skill candidate.
56|- **URL:** https://github.com/mvanhorn/last30days-skill
57|
58|### 8. refactoringhq/tolaria
59|- **Language:** TypeScript | ⭐ 16.7k | +2k this week
60|- Desktop app to manage markdown knowledge bases. Has a "demo-vault-v2" directory. **Obsidian alternative/complement** — markdown-native knowledge management. Worth watching for integration possibilities.
61|- **URL:** https://github.com/refactoringhq/tolaria
62|
63|### 9. hexo-ai/sia
64|- **Language:** Python | ⭐ 1.8k
65|- **SIA (Self-Improving AI):** Framework to autonomously improve performance of any AI system on a benchmark task. Novel self-improvement loop. Could inform Hermes agent self-improvement capabilities.
66|- **URL:** https://github.com/hexo-ai/sia
67|
68|### 10. shuvonsec/claude-bug-bounty
69|- **Language:** Python | ⭐ 3.4k
70|- AI-powered bug bounty hunting from terminal. Has **mcp/ directory** and `.claude/` directory. Shows pattern for building MCP-integrated CLI tools.
71|- **URL:** https://github.com/shuvonsec/claude-bug-bounty
72|
73|---
74|
75|## 🗂️ MCP ECOSYSTEM (Essential References)
76|
77|These are not trending repos themselves but are foundational MCP resources discovered during scanning:
78|
79|| Repo | Stars | Description |
80||------|-------|-------------|
81|| punkpeye/awesome-mcp-servers | ⭐ 89.4k | Curated collection of MCP servers |
82|| microsoft/playwright-mcp | ⭐ 34.1k | Browser automation MCP server |
83|| github/github-mcp-server | ⭐ 30.8k | Official GitHub MCP server |
84|| BrowserMCP/mcp | ⭐ 6.7k | Browser control MCP |
85|| awslabs/mcp | ⭐ 9.3k | AWS MCP implementations |
86|| microsoft/mcp | ⭐ 3.3k | Microsoft's MCP catalog |
87|
88|---
89|
90|## 🔍 INTEGRATION SCORING
91|
92|| Repo | MCP Support | CLI | n8n Node | Obsidian | Hermes Fit |
93||------|:-----------:|:---:|:--------:|:--------:|:----------:|
94|| headroom | ✅ Yes | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐⭐ |
95|| codebase-memory-mcp | ✅ Yes | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐ |
96|| hivemind | ❌ | ❌ | ❌ | ❌ | ⭐⭐⭐⭐ |
97|| SkillSpector | ❌ | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐ |
98|| Agent-Reach | ❌ | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐ |
99|| agent-skills | ❌ | ❌ | ❌ | ❌ | ⭐⭐⭐ |
100|| last30days-skill | ❌ | ❌ | ❌ | ❌ | ⭐⭐⭐ |
101|| tolaria | ❌ | ❌ | ❌ | ⚡ Similar | ⭐⭐ |
102|| sia | ❌ | ❌ | ❌ | ❌ | ⭐⭐ |
103|| claude-bug-bounty | ✅ Partial | ✅ Yes | ❌ | ❌ | ⭐⭐⭐ |
104|
105|---
106|
107|## 📋 RECOMMENDED ACTIONS
108|
109|1. **Try headroom** as an MCP server with Hermes — configure it in `~/.hermes/mcp-settings.json` to compress tool outputs
110|2. **Evaluate hivemind** for converting Hermes traces into reusable skills
111|3. **Add SkillSpector** as a pre-flight check in the Hermes skill install pipeline
112|4. **Browse awesome-mcp-servers** (89k⭐) for more MCP servers to plug into Hermes
113|5. **Watch DeusData/codebase-memory-mcp** — could power Hermes codebase queries across OpenClaw/Odysseus
114|6. **Explore Agent-Reach CLI** as a Hermes tool for web/social media data access
115|