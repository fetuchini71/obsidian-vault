# Comparativa Completa de APIs de IA Gratuitas (Junio 2026)

> Investigación realizada para Hermes Agent — comparación de tiers gratuitos de APIs de inferencia LLM.
> Fecha: 18 de junio de 2026

---

## RESUMEN EJECUTIVO

### Mejor opción como modelo PRIMARIO (agente conversacional + tool use):
1. **NVIDIA Nemotron 3 Ultra (550B)** vía OpenRouter (`:free`) — 1M contexto, tool use, $0/0
2. **Nex AGI Nex-N2-Pro (397B/17B)** vía OpenRouter (`:free`) — multimodal, tool use, $0/0
3. **Google Gemini 2.0 Flash** vía API directa — multimodal, tool use, 1M contexto
4. **Groq (Llama 3.3 70B)** — ultrafápido, tool use, buena calidad

### Mejor opción como modelo AUXILIAR (visión, clasificación, resúmenes):
1. **Google Gemini 2.0 Flash** — multimodal gratuito más capaz
2. **Nex-N2-Pro:free** (OpenRouter) — visión + tool use
3. **Groq (Llama 3.1 8B, Gemma 2)** — para tareas rápidas
4. **GitHub Models (GPT-4o mini, Llama)** — varios modelos gratuitos

---

## TABLA COMPARATIVA PRINCIPAL

| Proveedor | Modelos Gratis Disponibles | Contexto | Multimodal | Tool/FC | Streaming | Límites de Tasa | Calidad |
|---|---|---|---|---|---|---|---|
| **OpenRouter** (`:free`) | `nex-agi/nex-n2-pro:free` (397B/17B), `nvidia/nemotron-3-ultra-550b-a55b:free`, `cohere/north-mini-code:free`, más modelos comunitarios | 262K–1M | Sí (Nex-N2-Pro) | ✅ Sí | ✅ Sí | ~20 RPM, ~200 RPD (varía) | ⭐⭐⭐ Variable — Nex-N2-Pro es excelente |
| **Google Gemini API** | Gemini 2.0 Flash, 2.0 Flash-Lite, 1.5 Flash, 1.5 Pro (limitado) | 32K–1M | ✅ Sí (img, audio, video) | ✅ Sí | ✅ Sí | 10 RPM / 1,500 RPD (Flash) | ⭐⭐⭐⭐ Excelente calidad general |
| **Groq** | Llama 3.3-70B, Llama 3.1-8B, Mixtral 8x7B, Gemma 2 9B/27B, DeepSeek R1 Distill | 8K–128K | Emulación (LLaVA) | ✅ Sí (mayoría) | ✅ Sí | 30 RPM (mayoría) | ⭐⭐⭐⭐ Velocidad extremadamente rápida |
| **OpenCode-Zen** | `deepseek-v4-flash-free` (proxy DeepSeek V4 Flash) | 1M | No (solo texto) | ✅ Sí | ✅ Sí | Desconocido | ⭐⭐⭐⭐ DeepSeek V4 Flash es fronterizo |
| **GitHub Models** | GPT-4.1, GPT-4o mini, Llama 3.3/3.2/3.1, Mistral, DeepSeek, Cohere, Phi-3, AI21 | 8K–128K | Depende del modelo | ✅ Sí | ✅ Sí | ~10 RPM, ~50 RPD | ⭐⭐⭐⭐ Acceso a modelos premium gratis |
| **Cloudflare Workers AI** | Llama 3.2 1B/3B, Llama 3.1 8B/70B, Mistral 7B, DeepSeek R1, Llama Vision | 4K–128K | ✅ Sí (Llama Vision) | No (solo chat) | ✅ Sí | 10,000 neuronas/día (~$0.11 valor) | ⭐⭐⭐ Modelos pequeños mayormente |
| **Hugging Face** | Miles de modelos open-source via Inference API o credits | Varía | ✅ Sí (según modelo) | Varía | ✅ Sí | $0.10/mes créditos free | ⭐⭐⭐ Depende del modelo elegido |
| **Together AI** | Créditos gratuitos iniciales (~$1-5), modelos open-source | 4K–128K | Algunos | ✅ Sí | ✅ Sí | Créditos limitados | ⭐⭐⭐⭐ Buenos modelos |
| **Mistral AI** | Créditos de prueba al registrarse (cantidad limitada) | 32K–128K | ✅ Sí (Medium 3.5) | ✅ Sí | ✅ Sí | Una vez, créditos limitados | ⭐⭐⭐⭐ Mistral Medium 3.5 es excelente |
| **Cohere** | `north-mini-code:free` via OpenRouter; trial API con créditos | 256K | No | ✅ Sí | ✅ Sí | Trial: 5 RPM | ⭐⭐⭐ Bueno para código |
| **DeepSeek Oficial** | No tiene free tier permanente ($5 crédito inicial) | 1M | No | ✅ Sí | ✅ Sí | 2,500 RPM (pago) | ⭐⭐⭐⭐ Excelente calidad-precio |
| **Amazon Bedrock** | Free trial de 3 meses (modelos limitados) | Varía | ✅ Sí | ✅ Sí | ✅ Sí | 3 meses, luego pago | ⭐⭐⭐⭐⭐ Acceso a Claude, Llama |
| **AI21 Labs** | Créditos de prueba al registrarse | 8K–32K | No | Sí | Sí | Una vez | ⭐⭐⭐ Jurassic-2 |
| **Replicate** | No free tier real (créditos mínimos al registrarse) | Varía | Sí (algunos) | No | ✅ Sí | Créditos únicos | ⭐⭐⭐ Variable |
| **Perplexity** | API gratuita descontinuada (solo producto web) | — | — | — | — | — | — |

---

## 1. GOOGLE GEMINI API (GOOGLE_API_KEY) — RECOMENDADO

**Modelos gratuitos disponibles:**
- `gemini-2.0-flash` — modelo principal rápido (tier gratuito)
- `gemini-2.0-flash-lite` — versión más económica
- `gemini-1.5-flash` — 1M contexto, muy capaz
- `gemini-1.5-flash-8b` — versión más pequeña
- `gemini-1.5-pro` — limitado a 60 RPD en tier gratuito

**Límites del tier gratuito (vía API con GOOGLE_API_KEY):**
| Modelo | RPM | RPD | TPM |
|---|---|---|---|
| Gemini 2.0 Flash | 10 | 1,500 | 4M (input) / 2M (output) por minuto |
| Gemini 2.0 Flash-Lite | 30 | 1,500 | 4M / 2M |
| Gemini 1.5 Flash | 10 | 1,500 | 4M / 2M |
| Gemini 1.5 Pro | 2 | 60 | 1M / 500K |

**Contexto:** 1M tokens (1.5 Flash), 32K (2.0 Flash), 1M (2.0 Flash con cache)

**Multimodal:** ✅ Sí — texto, imágenes, audio, video (nativo)

**Tool Use (Function Calling):** ✅ Sí — excelente soporte, parallel function calling

**Streaming:** ✅ Sí — SSE streaming

**Calidad:** ⭐⭐⭐⭐ — Gemini 2.0 Flash compite bien con GPT-4o mini. Excelente para visión. Buena velocidad.

**Ideal para:** **PRIMARIO** (tool use) y **AUXILIAR** (visión, resúmenes, clasificación)

---

## 2. OPENROUTER (OPENROUTER_API_KEY) — MODELOS :FREE

OpenRouter actúa como agregador. Los modelos con `:free` tienen precio $0 (gratis vía community providers).

**Modelos gratuitos confirmados (pricing prompt=0, completion=0):**

| Model ID | Params | Context | Multimodal | Tool Use | Calidad |
|---|---|---|---|---|---|
| `nex-agi/nex-n2-pro:free` | 397B/17B MoE | 262K | ✅ (texto+imagen) | ✅ Sí | ⭐⭐⭐⭐ Muy bueno — comparable a Qwen3 |
| `nvidia/nemotron-3-ultra-550b-a55b:free` | 550B/55B MoE | 1M | No (solo texto) | ✅ Sí | ⭐⭐⭐ Fronterizo en razonamiento |
| `cohere/north-mini-code:free` | 30B/3B MoE | 256K | No (solo texto) | ✅ Sí | ⭐⭐⭐ Bueno para código (Coding Index 33) |
| `nvidia/nemotron-3.5-content-safety:free` | 4B | 128K | ✅ (texto+imagen) | No | ⭐ Solo safety/guardrails |

**Otros modelos `:free` que suelen estar disponibles:**
- `google/gemini-2.0-flash-exp:free` (el que usas como auxiliar)
- `meta-llama/llama-3.2-3b-instruct:free`
- `microsoft/phi-3-mini-128k-instruct:free`
- `mistralai/mistral-7b-instruct:free`
(disponibilidad varía según community providers)

**Límites de OpenRouter:**
- Free tier: ~20 RPM, ~200 RPD (varía por modelo y proveedor)
- Los modelos `:free` pueden ser eliminados sin aviso
- No hay garantía de disponibilidad

**Calidad:** ⭐⭐⭐ — El mejor es **Nex-N2-Pro**. Variable porque los providers son comunitarios.

**Ideal para:** **PRIMARIO** (Nex-N2-Pro o Nemotron 3 Ultra) si no necesitas garantías. **AUXILIAR** bueno.

---

## 3. GROQ (GROQ_API_KEY) — RECOMENDADO

**Modelos gratuitos disponibles:**

| Modelo | Contexto | RPM (free) | Tool Use | Calidad |
|---|---|---|---|---|
| `llama-3.3-70b-versatile` | 128K | 30 | ✅ Sí | ⭐⭐⭐⭐⭐ Excelente |
| `llama-3.1-8b-instant` | 128K | 30 | ✅ Sí | ⭐⭐⭐⭐ Bueno y rápido |
| `mixtral-8x7b-32768` | 32K | 30 | ✅ Sí | ⭐⭐⭐⭐ |
| `gemma2-9b-it` | 8K | 30 | ✅ Sí | ⭐⭐⭐ |
| `llama-guard-3-8b` | 8K | 30 | No | ⭐ Solo safety |
| `llama-3.2-3b-preview` | 8K | 30 | Limitado | ⭐⭐ |
| `llama-3.1-70b-versatile` | 131K | 15 | ✅ Sí | ⭐⭐⭐⭐⭐ |
| `deepseek-r1-distill-llama-70b` | 128K | 15 | Limitado | ⭐⭐⭐⭐ Razonamiento |

**Límites del tier gratuito:** 30 RPM para la mayoría de modelos, 15 RPM para los modelos de 70B.
Límite de tokens: ~6,000 tokens/minuto en free tier.
Sin límite diario duro (fair use).

**Multimodal:** No nativo. Groq tiene `llama-3.2-11b-vision` pero en preview.

**Tool Use:** ✅ Sí — excelente soporte, parallel function calling en Llama 3.3

**Velocidad:** ⭐⭐⭐⭐⭐ — **El más rápido de todos**. Respuestas en 100-500ms.

**Calidad:** ⭐⭐⭐⭐ — **Llama 3.3 70B** es calidad GPT-4-class.

**Ideal para:** **PRIMARIO** si usas Groq como respaldo. Excelente como **AUXILIAR** por velocidad.

---

## 4. OPENCODE-ZEN (OPENCODE_ZEN_API_KEY) — PROXY DEEPSEEK

**¿Qué es OpenCode-Zen?** Es un proxy/proveedor comunitario de código abierto que ofrece acceso gratuito a modelos como `deepseek-v4-flash`. No es un proveedor oficial — es parte del ecosistema Nous Research / Hermes Agent.

**Modelo actual:** `deepseek-v4-flash-free` → mapea a DeepSeek V4 Flash

**Características del modelo mapeado (DeepSeek V4 Flash):**
- **Contexto:** 1M tokens ✅
- **Tool Use:** ✅ Sí (tool calls, parallel function calling)
- **JSON Output:** ✅ Sí
- **Streaming:** ✅ Sí
- **Thinking Mode:** ✅ Sí (modo razonamiento incluido)

**Límites:** Desconocidos — depende de la disponibilidad del proxy comunitario.

**Calidad:** ⭐⭐⭐⭐ — DeepSeek V4 Flash es un modelo fronterizo competitivo con GPT-4o y Claude Sonnet en muchas tareas.

**Ideal para:** **PRIMARIO** — es tu modelo principal actual y funciona bien.

⚠️ **Advertencia:** Al ser un proxy comunitario, puede tener tiempos de inactividad o ser descontinuado.

---

## 5. GITHUB MODELS — GRATIS (RECIÉN LANZADO)

**Modelos gratuitos disponibles** (vía API con GitHub PAT):

| Modelo | Contexto | Notas |
|---|---|---|
| `openai/gpt-4.1` | 32K | En preview pública |
| `openai/gpt-4o-mini` | 128K | Excelente relación calidad |
| `meta/llama-3.3-70b-instruct` | 128K | |
| `meta/llama-3.2-90b-vision` | 128K | Multimodal |
| `meta/llama-3.1-8b-instruct` | 128K | |
| `mistral/mistral-large` | 128K | |
| `deepseek/deepseek-chat` | 64K | |
| `cohere/command-r-plus` | 128K | |
| `microsoft/phi-3-medium` | 128K | |
| `ai21/jamba-1.5-mini` | 256K | |

**Límites (free usando tu GitHub account):**
- ~10 RPM, ~50 RPD
- 100,000 tokens/día aproximadamente
- Sin costo usando GitHub PAT con scope `models`

**Tool Use:** ✅ Sí (depende del modelo)

**Multimodal:** ✅ Sí (Llama 3.2 Vision, GPT-4o mini)

**Streaming:** ✅ Sí

**Calidad:** ⭐⭐⭐⭐ — Acceso a GPT-4.1 y GPT-4o mini gratis es increíble.

**Ideal para:** **PRIMARIO** o **AUXILIAR** — Excelente acceso a GPT-4.1 gratis.

---

## 6. CLOUDFLARE WORKERS AI

**Modelos disponibles en el tier gratuito** (limitado por 10,000 neuronas/día):

| Modelo | Neuronas/M tokens (input) | Costo estimado por request |
|---|---|---|
| `@cf/meta/llama-3.2-1b-instruct` | 2,457 | ~$0.000027 |
| `@cf/meta/llama-3.2-3b-instruct` | 4,625 | ~$0.000051 |
| `@cf/meta/llama-3.1-8b-instruct-fp8-fast` | 4,119 | ~$0.000045 |
| `@cf/meta/llama-3.2-11b-vision-instruct` | 4,410 | ~$0.000049 (multimodal) |
| `@cf/meta/llama-3.3-70b-instruct-fp8-fast` | 26,668 | ~$0.000293 |
| `@cf/mistralai/mistral-small-3.1-24b` | 31,876 | ~$0.000351 |

**Límite gratuito:** 10,000 neuronas/día (~370 requests de Llama 8B o ~$0.11 valor)

**Tool Use:** ❌ No — solo chat completions estándar

**Multimodal:** ✅ Sí (Llama 3.2 11B Vision para imágenes)

**Streaming:** ✅ Sí

**Calidad:** ⭐⭐⭐ — Modelos mayormente pequeños o medianos.

**Ideal para:** **AUXILIAR** (tareas muy pequeñas, prototipado, integración con Cloudflare)

---

## 7. HUGGING FACE INFERENCE API

**Modelos:** Miles de modelos open-source (Llama, Mistral, Qwen, Gemma, etc.)

**Créditos gratuitos:**
- Free users: $0.10/mes en créditos
- PRO users: $2.00/mes en créditos
- Inference API (sin key): limitado a ~30K tokens/día

**Tool Use:** Varía según el modelo (algunos lo soportan)

**Multimodal:** ✅ Sí (según el modelo)

**Streaming:** ✅ Sí

**Calidad:** ⭐⭐⭐ — Depende completamente del modelo que elijas.

**Ideal para:** **AUXILIAR** — experimentación con modelos open-source.

---

## 8. MISTRAL AI — CRÉDITOS INICIALES

**Modelos (vía créditos de prueba, no free tier permanente):**
- `mistral-medium-latest` (Medium 3.5) — multimodal, tool use
- `mistral-small-latest` (Small 4)
- `ministral-3b-latest`, `ministral-8b-latest`, `ministral-14b-latest`
- `codestral-latest`

**Créditos:** Cantidad única al registrarse (usualmente $5-10 USD)

**Tool Use:** ✅ Sí — excelente soporte

**Multimodal:** ✅ Sí (Medium 3.5)

**Calidad:** ⭐⭐⭐⭐ — Mistral Medium 3.5 es fronterizo.

**Ideal para:** Probar, no como solución permanente gratuita.

---

## 9. COHERE — FREE TRIAL + OPENROUTER

**Modelo gratuito vía OpenRouter:** `cohere/north-mini-code:free` (30B/3B MoE, 256K contexto)

**Trial API:** Créditos iniciales al registrarse

**Tool Use:** ✅ Sí

**Multimodal:** ❌ No (solo texto)

**Límites (trial directo):** ~5 RPM

**Calidad:** ⭐⭐⭐ — North Mini Code tiene Coding Index 33.4.

**Ideal para:** **AUXILIAR** (código) si no usas otro mejor.

---

## 10. DEEPSEEK OFICIAL — NO FREE TIER

**Modelos (solo pago):**
- `deepseek-v4-flash` — $0.14/M input, $0.28/M output
- `deepseek-v4-pro` — $0.435/M input, $0.87/M output

**Bono:** $5 USD gratis al registrarse (no recurrente)

**Tool Use:** ✅ Sí

**Contexto:** 1M tokens

**Calidad:** ⭐⭐⭐⭐ — Excelente relación calidad-precio cuando pagas.

**Nota:** No es gratis, pero el bono inicial lo hace útil para pruebas.

---

## 11. OTROS PROVEEDORES

### AI21 Labs
- **Modelos:** Jurassic-2, Jamba 1.5
- **Trial:** Créditos al registrarse
- **Tool Use:** Sí
- **Uso:** Solo para probar

### Amazon Bedrock
- **Free trial:** 3 meses limitados
- **Modelos:** Claude 3/3.5, Llama 2/3, Mistral, Cohere, AI21
- **Tool Use:** Sí
- **Uso:** Solo como prueba temporal

### Replicate
- **Free credits:** Cantidad mínima al registrarse
- **Modelos:** Open-source (Llama, Mistral, SD)
- **No hay tier gratuito permanente**
- **Uso:** Solo para probar

### Together AI
- **Free credits:** ~$1-5 al registrarse
- **Modelos:** Open-source (Llama, Qwen, DeepSeek, Mixtral)
- **Tool Use:** Sí
- **Uso:** Solo para probar, no permanente

### Perplexity
- **API free:** Descontinuada. Solo producto web (Perplexity Pro)
- **No recomendado** para API.

### Anyscale / Fireworks AI
- **Fireworks:** Créditos gratuitos al registrarse, no tier permanente
- **Anyscale:** Descontinuó tier gratuito público

---

## COMPARATIVA DIRECTA PARA HERMES AGENT

### Como modelo PRIMARIO (conversación + tool use + razonamiento)
Criterios: tool use bueno, contexto largo, buena calidad general, streaming.

| Proveedor | Puntuación | Razón |
|---|---|---|
| **OpenCode-Zen (DeepSeek V4 Flash)** | ⭐⭐⭐⭐ | Ya configurado, 1M contexto, tool use. **Ya funciona.** |
| **Nex-N2-Pro:free (OpenRouter)** | ⭐⭐⭐⭐ | Mejor alternativa gratuita directa. Tool use + multimodal. |
| **Nemotron 3 Ultra:free (OpenRouter)** | ⭐⭐⭐⭐ | 1M contexto, tool use, razonamiento. |
| **Groq (Llama 3.3 70B)** | ⭐⭐⭐⭐⭐ | El más rápido. Tool use excelente. |
| **GitHub Models (GPT-4.1)** | ⭐⭐⭐⭐⭐ | GPT-4.1 gratis. Tool use nativo. Límites más restrictivos. |
| **Google Gemini 2.0 Flash** | ⭐⭐⭐⭐ | Multimodal nativo. Tool use. Buenos límites. |

### Como modelo AUXILIAR (visión, resúmenes, clasificación rápida)
Criterios: multimodal, velocidad, bajo costo.

| Proveedor | Puntuación | Razón |
|---|---|---|
| **Google Gemini 2.0 Flash** | ⭐⭐⭐⭐⭐ | Mejor multimodal gratuito. Audio, video, imágenes. |
| **Groq (Llama 3.1 8B)** | ⭐⭐⭐⭐ | Velocidad extrema para clasificación/resúmenes. |
| **Nex-N2-Pro:free (OpenRouter)** | ⭐⭐⭐⭐ | Multimodal + tool use gratis. |
| **GitHub Models (GPT-4o mini)** | ⭐⭐⭐⭐ | Bueno y rápido para tareas pequeñas. |
| **Cloudflare (Llama 3.2 11B Vision)** | ⭐⭐⭐ | Limitado pero útil si ya usas Cloudflare. |

---

## RECOMENDACIONES FINALES

### Para usar AHORA con tus API keys existentes:

**Configuración actual (ya funcional):**
```
PRIMARY: deepseek-v4-flash-free (OpenCode-Zen)
AUXILIARY: google/gemini-2.0-flash-exp:free (OpenRouter)
```
✅ **Esta configuración es buena.** DeepSeek V4 Flash es un modelo fronterizo excelente.

### Mejoras sugeridas (sin costo):

**Opción 1 — Mejor PRIMARY gratuito alternativo:**
```
PRIMARY: nex-agi/nex-n2-pro:free (OpenRouter)
AUXILIARY: google/gemini-2.0-flash (Google API)  
```
✅ Nex-N2-Pro (397B/17B MoE) + tool use + multimodal. Excelente.

**Opción 2 — Máxima velocidad:**
```
PRIMARY: llama-3.3-70b-versatile (Groq)
AUXILIARY: google/gemini-2.0-flash (Google API)
```
✅ Groq es el más rápido. Llama 3.3 70B es calidad premium.

**Opción 3 — Mejor calidad combinada:**
```
PRIMARY: deepseek-v4-flash (OpenCode-Zen) [actual]
AUXILIARY: groq (llama-3.3-70b) + gemini-2.0-flash
```
✅ Lo mejor de todos los mundos.

### Proveedores a EVITAR como primary:
❌ Cloudflare Workers AI — modelos muy pequeños, sin tool use
❌ Hugging Face Inference API — créditos muy limitados ($0.10/mes)
❌ Replicate — no tiene tier gratuito real
❌ Perplexity — API descontinuada

---

## NOTAS TÉCNICAS

### Soporte de tool/function calling por proveedor:
| Proveedor | Tool Calls | Parallel FC | Structured Output |
|---|---|---|---|
| Google Gemini | ✅ | ✅ | ✅ (response_schema) |
| OpenRouter (modelos :free) | ✅ (Nex, Nemotron, Cohere) | ✅ | ✅ (structured_outputs) |
| Groq | ✅ | ✅ | ✅ (JSON mode) |
| OpenCode-Zen (DeepSeek) | ✅ | ✅ | ✅ |
| GitHub Models | ✅ (depende del modelo) | ✅ | ✅ |
| Cloudflare | ❌ | ❌ | ❌ |
| Hugging Face | Varía | Varía | Varía |

### Contexto máximo gratuito:
| Proveedor | Contexto máximo |
|---|---|
| Google Gemini 1.5 Flash | **1M tokens** |
| DeepSeek V4 Flash | **1M tokens** |
| Nemotron 3 Ultra (OpenRouter) | **1M tokens** |
| GitHub Models (GPT-4.1) | 32K |
| Nex-N2-Pro (OpenRouter) | 262K |
| Groq (Llama 3.3 70B) | 128K |

---

*Investigación completa — Junio 2026*
*Fuentes: Documentación oficial de cada proveedor, API de OpenRouter (v1/models), y análisis de pricing público.*
