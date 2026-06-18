---
tags: [github-trending, ai-tools, scan, 2026-06]
---

# GitHub Trending Scan — June 18, 2026

> Scanned GitHub Trending (weekly) for AI tools and developer tools that could integrate with Braian's stack. Stack context: Hermes Agent, n8n, OpenClaw, Odysseus, Obsidian. Prioritized: MCP support, CLI interfaces, n8n nodes, Obsidian integration.

---

## 🥇 TOP PICKS (Most Relevant to Braian's Stack)

### 1. chopratejas/headroom — 🚀 HIGHEST PRIORITY
- **Language:** Python | ⭐ 32.2k | +9.5k this week
- **Description:** Compress tool outputs, logs, files, and RAG chunks before they reach the LLM. 60-95% fewer tokens, same answers.
- **Why it fits:** Ships as **library, proxy, AND MCP server**. Has `.claude-plugin` directory. Directly reduces token costs in Hermes Agent by compressing tool output before it reaches the LLM. Could be integrated as a Hermes middleware/plugin.
- **Links:** MCP, CLI, Hermes plugin integration
- **URL:** https://github.com/chopratejas/headroom

### 2. DeusData/codebase-memory-mcp — MCP Code Intelligence
- **Language:** Go/Rust | ⭐ 6k | Trending this week
- **Description:** High-performance code intelligence MCP server. Indexes codebases into a persistent knowledge graph. 158 languages, sub-ms queries, single static binary.
- **Why it fits:** **Pure MCP implementation** — directly usable as an MCP server with Hermes Agent. Could analyze OpenClaw/Odysseus codebases.
- **URL:** https://github.com/DeusData/codebase-memory-mcp

### 3. activeloopai/hivemind — Skills from Traces
- **Language:** TypeScript | ⭐ 1.3k | +538 this week
- **Description:** Hivemind turns your traces into reusable skills across agents.
- **Why it fits:** Has `.claude-plugin` directory. Could turn Hermes agent execution traces into reusable skills. Concept aligns perfectly with Hermes skill ecosystem.
- **URL:** https://github.com/activeloopai/hivemind

### 4. NVIDIA/SkillSpector — Agent Skill Security Scanner
- **Language:** Python | ⭐ 7.7k | +5.3k this week
- **Description:** Security scanner for AI agent skills. Detect vulnerabilities, malicious patterns, and security risks before installing agent skills.
- **Why it fits:** **CLI-based** security scanner. Could be integrated as a pre-installation hook in Hermes Agent to vet skills before loading. Docker-based deployment.
- **URL:** https://github.com/NVIDIA/SkillSpector

### 5. Panniantong/Agent-Reach — Internet Access for Agents
- **Language:** Python | ⭐ 33.7k | +6.9k this week
- **Description:** Give your AI agent eyes to see the entire internet. Read & search Twitter, Reddit, YouTube, GitHub, Bilibili — one CLI, zero API fees.
- **Why it fits:** **CLI tool** — directly usable as a Hermes Agent tool for web/social media research. No API keys needed.
- **URL:** https://github.com/Panniantong/Agent-Reach

---

## 🥈 STRONG CANDIDATES

### 6. addyosmani/agent-skills
- **Language:** Shell | ⭐ 62.5k | +11.7k this week
- Production-grade engineering skills for AI coding agents. Template-based patterns for reliable engineering workflows. Could inspire Hermes skill patterns.
- **URL:** https://github.com/addyosmani/agent-skills

### 7. mvanhorn/last30days-skill
- **Language:** Python | ⭐ 44.1k | +5.2k this week
- AI agent skill researching topics across Reddit, X, YouTube, HN, Polymarket. Instant Hermes skill candidate.
- **URL:** https://github.com/mvanhorn/last30days-skill

### 8. refactoringhq/tolaria
- **Language:** TypeScript | ⭐ 16.7k | +2k this week
- Desktop app to manage markdown knowledge bases. Has a "demo-vault-v2" directory. **Obsidian alternative/complement** — markdown-native knowledge management. Worth watching for integration possibilities.
- **URL:** https://github.com/refactoringhq/tolaria

### 9. hexo-ai/sia
- **Language:** Python | ⭐ 1.8k
- **SIA (Self-Improving AI):** Framework to autonomously improve performance of any AI system on a benchmark task. Novel self-improvement loop. Could inform Hermes agent self-improvement capabilities.
- **URL:** https://github.com/hexo-ai/sia

### 10. shuvonsec/claude-bug-bounty
- **Language:** Python | ⭐ 3.4k
- AI-powered bug bounty hunting from terminal. Has **mcp/ directory** and `.claude/` directory. Shows pattern for building MCP-integrated CLI tools.
- **URL:** https://github.com/shuvonsec/claude-bug-bounty

---

## 🗂️ MCP ECOSYSTEM (Essential References)

These are not trending repos themselves but are foundational MCP resources discovered during scanning:

| Repo | Stars | Description |
|------|-------|-------------|
| punkpeye/awesome-mcp-servers | ⭐ 89.4k | Curated collection of MCP servers |
| microsoft/playwright-mcp | ⭐ 34.1k | Browser automation MCP server |
| github/github-mcp-server | ⭐ 30.8k | Official GitHub MCP server |
| BrowserMCP/mcp | ⭐ 6.7k | Browser control MCP |
| awslabs/mcp | ⭐ 9.3k | AWS MCP implementations |
| microsoft/mcp | ⭐ 3.3k | Microsoft's MCP catalog |

---

## 🔍 INTEGRATION SCORING

| Repo | MCP Support | CLI | n8n Node | Obsidian | Hermes Fit |
|------|:-----------:|:---:|:--------:|:--------:|:----------:|
| headroom | ✅ Yes | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐⭐ |
| codebase-memory-mcp | ✅ Yes | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐ |
| hivemind | ❌ | ❌ | ❌ | ❌ | ⭐⭐⭐⭐ |
| SkillSpector | ❌ | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐ |
| Agent-Reach | ❌ | ✅ Yes | ❌ | ❌ | ⭐⭐⭐⭐ |
| agent-skills | ❌ | ❌ | ❌ | ❌ | ⭐⭐⭐ |
| last30days-skill | ❌ | ❌ | ❌ | ❌ | ⭐⭐⭐ |
| tolaria | ❌ | ❌ | ❌ | ⚡ Similar | ⭐⭐ |
| sia | ❌ | ❌ | ❌ | ❌ | ⭐⭐ |
| claude-bug-bounty | ✅ Partial | ✅ Yes | ❌ | ❌ | ⭐⭐⭐ |

---

## 📋 RECOMMENDED ACTIONS

1. **Try headroom** as an MCP server with Hermes — configure it in `~/.hermes/mcp-settings.json` to compress tool outputs
2. **Evaluate hivemind** for converting Hermes traces into reusable skills
3. **Add SkillSpector** as a pre-flight check in the Hermes skill install pipeline
4. **Browse awesome-mcp-servers** (89k⭐) for more MCP servers to plug into Hermes
5. **Watch DeusData/codebase-memory-mcp** — could power Hermes codebase queries across OpenClaw/Odysseus
6. **Explore Agent-Reach CLI** as a Hermes tool for web/social media data access
