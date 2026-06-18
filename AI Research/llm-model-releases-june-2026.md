# LLM Model Releases — June 2026

## Research Summary

**Date:** Thursday, June 18, 2026  
**Sources checked:**
- Simon Willison's Weblog (comprehensive LLM coverage)
- Anthropic Newsroom
- Hugging Face Blog & Model Hub
- Nous Research website & GitHub
- Hacker News
- Google AI Blog
- Meta AI Blog
- Artificial Intelligence News

---

## Top 3 Most Significant Releases

### 1. GLM-5.2 by Z.ai (formerly Zhipu AI)
| Field | Detail |
|-------|--------|
| **Released** | June 16, 2026 (open weights) |
| **Size** | 753B total, **40B active** (Mixture of Experts) |
| **Open/Closed** | ✅ **Open weights** — MIT license |
| **Context window** | 1 million tokens |
| **Key benchmarks** | #1 open-weights model on Artificial Analysis Intelligence Index (score 51); #2 on Code Arena WebDev leaderboard (behind only Claude Fable 5) |
| **Pricing (API)** | ~$1.40/M input, $4.40/M output via OpenRouter |
| **Relevance to local-first AI agent** | High. The 40B active MoE architecture is intriguing — a 4-bit quantized version could run on high-end consumer hardware (48GB+ VRAM). Available via OpenRouter for API fallback. Text-only, but excels at coding and agentic tasks. |

**Notes:** Outperforms MiniMax-M3 (44), DeepSeek V4 Pro (44), and Kimi K2.6 (43) on the Intelligence Index. Also ranked 2nd on Code Arena WebDev behind only Claude Fable 5. Produces more output tokens per task than peers (43k vs 26k for GLM-5.1). Released under MIT license.

---

### 2. Claude Fable 5 / Mythos 5 by Anthropic
| Field | Detail |
|-------|--------|
| **Released** | June 9, 2026 |
| **Size** | Undisclosed (large frontier model) |
| **Open/Closed** | ❌ **Closed** — API only (access suspended June 12 by US export control directive) |
| **Key benchmarks** | SOTA on nearly all benchmarks. Stripe: compressed months of engineering into days on a 50M-line Ruby codebase. Top of Code Arena WebDev. |
| **Pricing** | $10/M input, $50/M output |
| **Relevance to local-first AI agent** | Very high. The best available model for agentic coding tasks. Claude Opus 4.8 (predecessor, still available) scored 84% on Online-Mind2Web for browser agents. Relevant as the high-end API model in an agent stack. |

**Notes:** Fable 5 is Mythos 5 with safety guardrails. Mythos 5 has lifted restrictions for cybersecurity use via Project Glasswing. Both models suspended from access on June 12 due to US government export controls. Opus 4.8 (released May 28) remains available and is an excellent agentic model.

---

### 3. Microsoft MAI Models (MAI-Thinking-1 & MAI-Code-1-Flash)
| Field | Detail |
|-------|--------|
| **Released** | June 2, 2026 (Microsoft Build) |
| **Size** | MAI-Thinking-1: **1T total, 35B active** (MoE). MAI-Code-1-Flash: **137B total, 5B active** (MoE) |
| **Open/Closed** | ❌ **Closed** — MAI-Thinking-1 to "select early partners"; MAI-Code-1-Flash rolling out to GitHub Copilot users in VS Code |
| **Key benchmarks** | MAI-Thinking-1 "preferred to Sonnet 4.6 in blind human side-by-side". Both trained on "enterprise grade, clean and commercially licensed data" (though technical paper reveals they still used Common Crawl + proprietary web crawl). |
| **Relevance to local-first AI agent** | High. The 5B active MoE of MAI-Code-1-Flash is small enough for local inference. MAI-Thinking-1 at 35B active could run on high-end hardware (quantized). These models represent a new direction for Microsoft — purpose-built, efficient MoE models for specific domains. |

**Notes:** Announced alongside 7 new MAI models total. Both are text-only. The "clean data" claim is nuanced — they train on web data but filter heavily. MAI-Code-1-Flash is specifically optimized as a copilot model.

---

## Other Notable June 2026 Releases

### Cohere North Mini Code
- **Released:** June 9, 2026
- **Status:** Cohere's first model for developers
- **Relevance:** Code-specialized model. Details on size and benchmarks still emerging.

### Claude Opus 4.8
- **Released:** May 28, 2026
- **Status:** Closed, API. Available today.
- **Key:** "Effort" control allows user to dial compute for a task. Fast mode now 3x cheaper.

---

## Benchmark Leaderboard Context

| Rank | Model | Intelligence Index | Notes |
|------|-------|-------------------|-------|
| 1 (open) | **GLM-5.2** | 51 | Open weights, MIT |
| 2 | MiniMax-M3 | 44 | |
| 3 | DeepSeek V4 Pro (max) | 44 | |
| 4 | Kimi K2.6 | 43 | |
| — | **Claude Fable 5** | SOTA | Not on this leaderboard; tops Code Arena WebDev |

---

## Relevance to Hermes Agent / Local-First Setup

1. **GLM-5.2 (40B active, MIT)** — Most promising open model for a hybrid local/API agent stack. Could run quantized on high-end consumer hardware. Strong coding and agentic capabilities.

2. **MAI-Code-1-Flash (5B active)** — If Microsoft opens access, this tiny-active-parameter code model is perfect for local deployment. Watch for potential GGUF conversions.

3. **Claude Opus 4.8** — Currently the best available API model for agent stacks (Fable 5 is suspended). Strong scores on agent benchmarks (Mind2Web at 84%, Legal Agent benchmark highest ever).

4. **Nous Research** — No new model releases found in June 2026. Last activity on HuggingFace was papers on byte-level tokenization simulation (27 days ago) and targeted neuron modulation. The Hermes-Function-Calling repo continues but no new base models this month.
