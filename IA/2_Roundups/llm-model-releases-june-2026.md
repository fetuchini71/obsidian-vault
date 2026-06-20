1|# LLM Model Releases — June 2026
2|
3|## Research Summary
4|
5|**Date:** Thursday, June 18, 2026  
6|**Sources checked:**
7|- Simon Willison's Weblog (comprehensive LLM coverage)
8|- Anthropic Newsroom
9|- Hugging Face Blog & Model Hub
10|- Nous Research website & GitHub
11|- Hacker News
12|- Google AI Blog
13|- Meta AI Blog
14|- Artificial Intelligence News
15|
16|---
17|
18|## Top 3 Most Significant Releases
19|
20|### 1. GLM-5.2 by Z.ai (formerly Zhipu AI)
21|| Field | Detail |
22||-------|--------|
23|| **Released** | June 16, 2026 (open weights) |
24|| **Size** | 753B total, **40B active** (Mixture of Experts) |
25|| **Open/Closed** | ✅ **Open weights** — MIT license |
26|| **Context window** | 1 million tokens |
27|| **Key benchmarks** | #1 open-weights model on Artificial Analysis Intelligence Index (score 51); #2 on Code Arena WebDev leaderboard (behind only Claude Fable 5) |
28|| **Pricing (API)** | ~$1.40/M input, $4.40/M output via OpenRouter |
29|| **Relevance to local-first AI agent** | High. The 40B active MoE architecture is intriguing — a 4-bit quantized version could run on high-end consumer hardware (48GB+ VRAM). Available via OpenRouter for API fallback. Text-only, but excels at coding and agentic tasks. |
30|
31|**Notes:** Outperforms MiniMax-M3 (44), DeepSeek V4 Pro (44), and Kimi K2.6 (43) on the Intelligence Index. Also ranked 2nd on Code Arena WebDev behind only Claude Fable 5. Produces more output tokens per task than peers (43k vs 26k for GLM-5.1). Released under MIT license.
32|
33|---
34|
35|### 2. Claude Fable 5 / Mythos 5 by Anthropic
36|| Field | Detail |
37||-------|--------|
38|| **Released** | June 9, 2026 |
39|| **Size** | Undisclosed (large frontier model) |
40|| **Open/Closed** | ❌ **Closed** — API only (access suspended June 12 by US export control directive) |
41|| **Key benchmarks** | SOTA on nearly all benchmarks. Stripe: compressed months of engineering into days on a 50M-line Ruby codebase. Top of Code Arena WebDev. |
42|| **Pricing** | $10/M input, $50/M output |
43|| **Relevance to local-first AI agent** | Very high. The best available model for agentic coding tasks. Claude Opus 4.8 (predecessor, still available) scored 84% on Online-Mind2Web for browser agents. Relevant as the high-end API model in an agent stack. |
44|
45|**Notes:** Fable 5 is Mythos 5 with safety guardrails. Mythos 5 has lifted restrictions for cybersecurity use via Project Glasswing. Both models suspended from access on June 12 due to US government export controls. Opus 4.8 (released May 28) remains available and is an excellent agentic model.
46|
47|---
48|
49|### 3. Microsoft MAI Models (MAI-Thinking-1 & MAI-Code-1-Flash)
50|| Field | Detail |
51||-------|--------|
52|| **Released** | June 2, 2026 (Microsoft Build) |
53|| **Size** | MAI-Thinking-1: **1T total, 35B active** (MoE). MAI-Code-1-Flash: **137B total, 5B active** (MoE) |
54|| **Open/Closed** | ❌ **Closed** — MAI-Thinking-1 to "select early partners"; MAI-Code-1-Flash rolling out to GitHub Copilot users in VS Code |
55|| **Key benchmarks** | MAI-Thinking-1 "preferred to Sonnet 4.6 in blind human side-by-side". Both trained on "enterprise grade, clean and commercially licensed data" (though technical paper reveals they still used Common Crawl + proprietary web crawl). |
56|| **Relevance to local-first AI agent** | High. The 5B active MoE of MAI-Code-1-Flash is small enough for local inference. MAI-Thinking-1 at 35B active could run on high-end hardware (quantized). These models represent a new direction for Microsoft — purpose-built, efficient MoE models for specific domains. |
57|
58|**Notes:** Announced alongside 7 new MAI models total. Both are text-only. The "clean data" claim is nuanced — they train on web data but filter heavily. MAI-Code-1-Flash is specifically optimized as a copilot model.
59|
60|---
61|
62|## Other Notable June 2026 Releases
63|
64|### Cohere North Mini Code
65|- **Released:** June 9, 2026
66|- **Status:** Cohere's first model for developers
67|- **Relevance:** Code-specialized model. Details on size and benchmarks still emerging.
68|
69|### Claude Opus 4.8
70|- **Released:** May 28, 2026
71|- **Status:** Closed, API. Available today.
72|- **Key:** "Effort" control allows user to dial compute for a task. Fast mode now 3x cheaper.
73|
74|---
75|
76|## Benchmark Leaderboard Context
77|
78|| Rank | Model | Intelligence Index | Notes |
79||------|-------|-------------------|-------|
80|| 1 (open) | **GLM-5.2** | 51 | Open weights, MIT |
81|| 2 | MiniMax-M3 | 44 | |
82|| 3 | DeepSeek V4 Pro (max) | 44 | |
83|| 4 | Kimi K2.6 | 43 | |
84|| — | **Claude Fable 5** | SOTA | Not on this leaderboard; tops Code Arena WebDev |
85|
86|---
87|
88|## Relevance to Hermes Agent / Local-First Setup
89|
90|1. **GLM-5.2 (40B active, MIT)** — Most promising open model for a hybrid local/API agent stack. Could run quantized on high-end consumer hardware. Strong coding and agentic capabilities.
91|
92|2. **MAI-Code-1-Flash (5B active)** — If Microsoft opens access, this tiny-active-parameter code model is perfect for local deployment. Watch for potential GGUF conversions.
93|
94|3. **Claude Opus 4.8** — Currently the best available API model for agent stacks (Fable 5 is suspended). Strong scores on agent benchmarks (Mind2Web at 84%, Legal Agent benchmark highest ever).
95|
96|4. **Nous Research** — No new model releases found in June 2026. Last activity on HuggingFace was papers on byte-level tokenization simulation (27 days ago) and targeted neuron modulation. The Hermes-Function-Calling repo continues but no new base models this month.
97|