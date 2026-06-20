1|# Comparativa Completa de APIs de IA Gratuitas (Junio 2026)
2|
3|> Investigación realizada para Hermes Agent — comparación de tiers gratuitos de APIs de inferencia LLM.
4|> Fecha: 18 de junio de 2026
5|
6|---
7|
8|## RESUMEN EJECUTIVO
9|
10|### Mejor opción como modelo PRIMARIO (agente conversacional + tool use):
11|1. **NVIDIA Nemotron 3 Ultra (550B)** vía OpenRouter (`:free`) — 1M contexto, tool use, $0/0
12|2. **Nex AGI Nex-N2-Pro (397B/17B)** vía OpenRouter (`:free`) — multimodal, tool use, $0/0
13|3. **Google Gemini 2.0 Flash** vía API directa — multimodal, tool use, 1M contexto
14|4. **Groq (Llama 3.3 70B)** — ultrafápido, tool use, buena calidad
15|
16|### Mejor opción como modelo AUXILIAR (visión, clasificación, resúmenes):
17|1. **Google Gemini 2.0 Flash** — multimodal gratuito más capaz
18|2. **Nex-N2-Pro:free** (OpenRouter) — visión + tool use
19|3. **Groq (Llama 3.1 8B, Gemma 2)** — para tareas rápidas
20|4. **GitHub Models (GPT-4o mini, Llama)** — varios modelos gratuitos
21|
22|---
23|
24|## TABLA COMPARATIVA PRINCIPAL
25|
26|| Proveedor | Modelos Gratis Disponibles | Contexto | Multimodal | Tool/FC | Streaming | Límites de Tasa | Calidad |
27||---|---|---|---|---|---|---|---|
28|| **OpenRouter** (`:free`) | `nex-agi/nex-n2-pro:free` (397B/17B), `nvidia/nemotron-3-ultra-550b-a55b:free`, `cohere/north-mini-code:free`, más modelos comunitarios | 262K–1M | Sí (Nex-N2-Pro) | ✅ Sí | ✅ Sí | ~20 RPM, ~200 RPD (varía) | ⭐⭐⭐ Variable — Nex-N2-Pro es excelente |
29|| **Google Gemini API** | Gemini 2.0 Flash, 2.0 Flash-Lite, 1.5 Flash, 1.5 Pro (limitado) | 32K–1M | ✅ Sí (img, audio, video) | ✅ Sí | ✅ Sí | 10 RPM / 1,500 RPD (Flash) | ⭐⭐⭐⭐ Excelente calidad general |
30|| **Groq** | Llama 3.3-70B, Llama 3.1-8B, Mixtral 8x7B, Gemma 2 9B/27B, DeepSeek R1 Distill | 8K–128K | Emulación (LLaVA) | ✅ Sí (mayoría) | ✅ Sí | 30 RPM (mayoría) | ⭐⭐⭐⭐ Velocidad extremadamente rápida |
31|| **OpenCode-Zen** | `deepseek-v4-flash-free` (proxy DeepSeek V4 Flash) | 1M | No (solo texto) | ✅ Sí | ✅ Sí | Desconocido | ⭐⭐⭐⭐ DeepSeek V4 Flash es fronterizo |
32|| **GitHub Models** | GPT-4.1, GPT-4o mini, Llama 3.3/3.2/3.1, Mistral, DeepSeek, Cohere, Phi-3, AI21 | 8K–128K | Depende del modelo | ✅ Sí | ✅ Sí | ~10 RPM, ~50 RPD | ⭐⭐⭐⭐ Acceso a modelos premium gratis |
33|| **Cloudflare Workers AI** | Llama 3.2 1B/3B, Llama 3.1 8B/70B, Mistral 7B, DeepSeek R1, Llama Vision | 4K–128K | ✅ Sí (Llama Vision) | No (solo chat) | ✅ Sí | 10,000 neuronas/día (~$0.11 valor) | ⭐⭐⭐ Modelos pequeños mayormente |
34|| **Hugging Face** | Miles de modelos open-source via Inference API o credits | Varía | ✅ Sí (según modelo) | Varía | ✅ Sí | $0.10/mes créditos free | ⭐⭐⭐ Depende del modelo elegido |
35|| **Together AI** | Créditos gratuitos iniciales (~$1-5), modelos open-source | 4K–128K | Algunos | ✅ Sí | ✅ Sí | Créditos limitados | ⭐⭐⭐⭐ Buenos modelos |
36|| **Mistral AI** | Créditos de prueba al registrarse (cantidad limitada) | 32K–128K | ✅ Sí (Medium 3.5) | ✅ Sí | ✅ Sí | Una vez, créditos limitados | ⭐⭐⭐⭐ Mistral Medium 3.5 es excelente |
37|| **Cohere** | `north-mini-code:free` via OpenRouter; trial API con créditos | 256K | No | ✅ Sí | ✅ Sí | Trial: 5 RPM | ⭐⭐⭐ Bueno para código |
38|| **DeepSeek Oficial** | No tiene free tier permanente ($5 crédito inicial) | 1M | No | ✅ Sí | ✅ Sí | 2,500 RPM (pago) | ⭐⭐⭐⭐ Excelente calidad-precio |
39|| **Amazon Bedrock** | Free trial de 3 meses (modelos limitados) | Varía | ✅ Sí | ✅ Sí | ✅ Sí | 3 meses, luego pago | ⭐⭐⭐⭐⭐ Acceso a Claude, Llama |
40|| **AI21 Labs** | Créditos de prueba al registrarse | 8K–32K | No | Sí | Sí | Una vez | ⭐⭐⭐ Jurassic-2 |
41|| **Replicate** | No free tier real (créditos mínimos al registrarse) | Varía | Sí (algunos) | No | ✅ Sí | Créditos únicos | ⭐⭐⭐ Variable |
42|| **Perplexity** | API gratuita descontinuada (solo producto web) | — | — | — | — | — | — |
43|
44|---
45|
46|## 1. GOOGLE GEMINI API (GOOGLE_API_KEY) — RECOMENDADO
47|
48|**Modelos gratuitos disponibles:**
49|- `gemini-2.0-flash` — modelo principal rápido (tier gratuito)
50|- `gemini-2.0-flash-lite` — versión más económica
51|- `gemini-1.5-flash` — 1M contexto, muy capaz
52|- `gemini-1.5-flash-8b` — versión más pequeña
53|- `gemini-1.5-pro` — limitado a 60 RPD en tier gratuito
54|
55|**Límites del tier gratuito (vía API con GOOGLE_API_KEY):**
56|| Modelo | RPM | RPD | TPM |
57||---|---|---|---|
58|| Gemini 2.0 Flash | 10 | 1,500 | 4M (input) / 2M (output) por minuto |
59|| Gemini 2.0 Flash-Lite | 30 | 1,500 | 4M / 2M |
60|| Gemini 1.5 Flash | 10 | 1,500 | 4M / 2M |
61|| Gemini 1.5 Pro | 2 | 60 | 1M / 500K |
62|
63|**Contexto:** 1M tokens (1.5 Flash), 32K (2.0 Flash), 1M (2.0 Flash con cache)
64|
65|**Multimodal:** ✅ Sí — texto, imágenes, audio, video (nativo)
66|
67|**Tool Use (Function Calling):** ✅ Sí — excelente soporte, parallel function calling
68|
69|**Streaming:** ✅ Sí — SSE streaming
70|
71|**Calidad:** ⭐⭐⭐⭐ — Gemini 2.0 Flash compite bien con GPT-4o mini. Excelente para visión. Buena velocidad.
72|
73|**Ideal para:** **PRIMARIO** (tool use) y **AUXILIAR** (visión, resúmenes, clasificación)
74|
75|---
76|
77|## 2. OPENROUTER (OPENROUTER_API_KEY) — MODELOS :FREE
78|
79|OpenRouter actúa como agregador. Los modelos con `:free` tienen precio $0 (gratis vía community providers).
80|
81|**Modelos gratuitos confirmados (pricing prompt=0, completion=0):**
82|
83|| Model ID | Params | Context | Multimodal | Tool Use | Calidad |
84||---|---|---|---|---|---|
85|| `nex-agi/nex-n2-pro:free` | 397B/17B MoE | 262K | ✅ (texto+imagen) | ✅ Sí | ⭐⭐⭐⭐ Muy bueno — comparable a Qwen3 |
86|| `nvidia/nemotron-3-ultra-550b-a55b:free` | 550B/55B MoE | 1M | No (solo texto) | ✅ Sí | ⭐⭐⭐ Fronterizo en razonamiento |
87|| `cohere/north-mini-code:free` | 30B/3B MoE | 256K | No (solo texto) | ✅ Sí | ⭐⭐⭐ Bueno para código (Coding Index 33) |
88|| `nvidia/nemotron-3.5-content-safety:free` | 4B | 128K | ✅ (texto+imagen) | No | ⭐ Solo safety/guardrails |
89|
90|**Otros modelos `:free` que suelen estar disponibles:**
91|- `google/gemini-2.0-flash-exp:free` (el que usas como auxiliar)
92|- `meta-llama/llama-3.2-3b-instruct:free`
93|- `microsoft/phi-3-mini-128k-instruct:free`
94|- `mistralai/mistral-7b-instruct:free`
95|(disponibilidad varía según community providers)
96|
97|**Límites de OpenRouter:**
98|- Free tier: ~20 RPM, ~200 RPD (varía por modelo y proveedor)
99|- Los modelos `:free` pueden ser eliminados sin aviso
100|- No hay garantía de disponibilidad
101|
102|**Calidad:** ⭐⭐⭐ — El mejor es **Nex-N2-Pro**. Variable porque los providers son comunitarios.
103|
104|**Ideal para:** **PRIMARIO** (Nex-N2-Pro o Nemotron 3 Ultra) si no necesitas garantías. **AUXILIAR** bueno.
105|
106|---
107|
108|## 3. GROQ (GROQ_API_KEY) — RECOMENDADO
109|
110|**Modelos gratuitos disponibles:**
111|
112|| Modelo | Contexto | RPM (free) | Tool Use | Calidad |
113||---|---|---|---|---|
114|| `llama-3.3-70b-versatile` | 128K | 30 | ✅ Sí | ⭐⭐⭐⭐⭐ Excelente |
115|| `llama-3.1-8b-instant` | 128K | 30 | ✅ Sí | ⭐⭐⭐⭐ Bueno y rápido |
116|| `mixtral-8x7b-32768` | 32K | 30 | ✅ Sí | ⭐⭐⭐⭐ |
117|| `gemma2-9b-it` | 8K | 30 | ✅ Sí | ⭐⭐⭐ |
118|| `llama-guard-3-8b` | 8K | 30 | No | ⭐ Solo safety |
119|| `llama-3.2-3b-preview` | 8K | 30 | Limitado | ⭐⭐ |
120|| `llama-3.1-70b-versatile` | 131K | 15 | ✅ Sí | ⭐⭐⭐⭐⭐ |
121|| `deepseek-r1-distill-llama-70b` | 128K | 15 | Limitado | ⭐⭐⭐⭐ Razonamiento |
122|
123|**Límites del tier gratuito:** 30 RPM para la mayoría de modelos, 15 RPM para los modelos de 70B.
124|Límite de tokens: ~6,000 tokens/minuto en free tier.
125|Sin límite diario duro (fair use).
126|
127|**Multimodal:** No nativo. Groq tiene `llama-3.2-11b-vision` pero en preview.
128|
129|**Tool Use:** ✅ Sí — excelente soporte, parallel function calling en Llama 3.3
130|
131|**Velocidad:** ⭐⭐⭐⭐⭐ — **El más rápido de todos**. Respuestas en 100-500ms.
132|
133|**Calidad:** ⭐⭐⭐⭐ — **Llama 3.3 70B** es calidad GPT-4-class.
134|
135|**Ideal para:** **PRIMARIO** si usas Groq como respaldo. Excelente como **AUXILIAR** por velocidad.
136|
137|---
138|
139|## 4. OPENCODE-ZEN (OPENCODE_ZEN_API_KEY) — PROXY DEEPSEEK
140|
141|**¿Qué es OpenCode-Zen?** Es un proxy/proveedor comunitario de código abierto que ofrece acceso gratuito a modelos como `deepseek-v4-flash`. No es un proveedor oficial — es parte del ecosistema Nous Research / Hermes Agent.
142|
143|**Modelo actual:** `deepseek-v4-flash-free` → mapea a DeepSeek V4 Flash
144|
145|**Características del modelo mapeado (DeepSeek V4 Flash):**
146|- **Contexto:** 1M tokens ✅
147|- **Tool Use:** ✅ Sí (tool calls, parallel function calling)
148|- **JSON Output:** ✅ Sí
149|- **Streaming:** ✅ Sí
150|- **Thinking Mode:** ✅ Sí (modo razonamiento incluido)
151|
152|**Límites:** Desconocidos — depende de la disponibilidad del proxy comunitario.
153|
154|**Calidad:** ⭐⭐⭐⭐ — DeepSeek V4 Flash es un modelo fronterizo competitivo con GPT-4o y Claude Sonnet en muchas tareas.
155|
156|**Ideal para:** **PRIMARIO** — es tu modelo principal actual y funciona bien.
157|
158|⚠️ **Advertencia:** Al ser un proxy comunitario, puede tener tiempos de inactividad o ser descontinuado.
159|
160|---
161|
162|## 5. GITHUB MODELS — GRATIS (RECIÉN LANZADO)
163|
164|**Modelos gratuitos disponibles** (vía API con GitHub PAT):
165|
166|| Modelo | Contexto | Notas |
167||---|---|---|
168|| `openai/gpt-4.1` | 32K | En preview pública |
169|| `openai/gpt-4o-mini` | 128K | Excelente relación calidad |
170|| `meta/llama-3.3-70b-instruct` | 128K | |
171|| `meta/llama-3.2-90b-vision` | 128K | Multimodal |
172|| `meta/llama-3.1-8b-instruct` | 128K | |
173|| `mistral/mistral-large` | 128K | |
174|| `deepseek/deepseek-chat` | 64K | |
175|| `cohere/command-r-plus` | 128K | |
176|| `microsoft/phi-3-medium` | 128K | |
177|| `ai21/jamba-1.5-mini` | 256K | |
178|
179|**Límites (free usando tu GitHub account):**
180|- ~10 RPM, ~50 RPD
181|- 100,000 tokens/día aproximadamente
182|- Sin costo usando GitHub PAT con scope `models`
183|
184|**Tool Use:** ✅ Sí (depende del modelo)
185|
186|**Multimodal:** ✅ Sí (Llama 3.2 Vision, GPT-4o mini)
187|
188|**Streaming:** ✅ Sí
189|
190|**Calidad:** ⭐⭐⭐⭐ — Acceso a GPT-4.1 y GPT-4o mini gratis es increíble.
191|
192|**Ideal para:** **PRIMARIO** o **AUXILIAR** — Excelente acceso a GPT-4.1 gratis.
193|
194|---
195|
196|## 6. CLOUDFLARE WORKERS AI
197|
198|**Modelos disponibles en el tier gratuito** (limitado por 10,000 neuronas/día):
199|
200|| Modelo | Neuronas/M tokens (input) | Costo estimado por request |
201||---|---|---|
202|| `@cf/meta/llama-3.2-1b-instruct` | 2,457 | ~$0.000027 |
203|| `@cf/meta/llama-3.2-3b-instruct` | 4,625 | ~$0.000051 |
204|| `@cf/meta/llama-3.1-8b-instruct-fp8-fast` | 4,119 | ~$0.000045 |
205|| `@cf/meta/llama-3.2-11b-vision-instruct` | 4,410 | ~$0.000049 (multimodal) |
206|| `@cf/meta/llama-3.3-70b-instruct-fp8-fast` | 26,668 | ~$0.000293 |
207|| `@cf/mistralai/mistral-small-3.1-24b` | 31,876 | ~$0.000351 |
208|
209|**Límite gratuito:** 10,000 neuronas/día (~370 requests de Llama 8B o ~$0.11 valor)
210|
211|**Tool Use:** ❌ No — solo chat completions estándar
212|
213|**Multimodal:** ✅ Sí (Llama 3.2 11B Vision para imágenes)
214|
215|**Streaming:** ✅ Sí
216|
217|**Calidad:** ⭐⭐⭐ — Modelos mayormente pequeños o medianos.
218|
219|**Ideal para:** **AUXILIAR** (tareas muy pequeñas, prototipado, integración con Cloudflare)
220|
221|---
222|
223|## 7. HUGGING FACE INFERENCE API
224|
225|**Modelos:** Miles de modelos open-source (Llama, Mistral, Qwen, Gemma, etc.)
226|
227|**Créditos gratuitos:**
228|- Free users: $0.10/mes en créditos
229|- PRO users: $2.00/mes en créditos
230|- Inference API (sin key): limitado a ~30K tokens/día
231|
232|**Tool Use:** Varía según el modelo (algunos lo soportan)
233|
234|**Multimodal:** ✅ Sí (según el modelo)
235|
236|**Streaming:** ✅ Sí
237|
238|**Calidad:** ⭐⭐⭐ — Depende completamente del modelo que elijas.
239|
240|**Ideal para:** **AUXILIAR** — experimentación con modelos open-source.
241|
242|---
243|
244|## 8. MISTRAL AI — CRÉDITOS INICIALES
245|
246|**Modelos (vía créditos de prueba, no free tier permanente):**
247|- `mistral-medium-latest` (Medium 3.5) — multimodal, tool use
248|- `mistral-small-latest` (Small 4)
249|- `ministral-3b-latest`, `ministral-8b-latest`, `ministral-14b-latest`
250|- `codestral-latest`
251|
252|**Créditos:** Cantidad única al registrarse (usualmente $5-10 USD)
253|
254|**Tool Use:** ✅ Sí — excelente soporte
255|
256|**Multimodal:** ✅ Sí (Medium 3.5)
257|
258|**Calidad:** ⭐⭐⭐⭐ — Mistral Medium 3.5 es fronterizo.
259|
260|**Ideal para:** Probar, no como solución permanente gratuita.
261|
262|---
263|
264|## 9. COHERE — FREE TRIAL + OPENROUTER
265|
266|**Modelo gratuito vía OpenRouter:** `cohere/north-mini-code:free` (30B/3B MoE, 256K contexto)
267|
268|**Trial API:** Créditos iniciales al registrarse
269|
270|**Tool Use:** ✅ Sí
271|
272|**Multimodal:** ❌ No (solo texto)
273|
274|**Límites (trial directo):** ~5 RPM
275|
276|**Calidad:** ⭐⭐⭐ — North Mini Code tiene Coding Index 33.4.
277|
278|**Ideal para:** **AUXILIAR** (código) si no usas otro mejor.
279|
280|---
281|
282|## 10. DEEPSEEK OFICIAL — NO FREE TIER
283|
284|**Modelos (solo pago):**
285|- `deepseek-v4-flash` — $0.14/M input, $0.28/M output
286|- `deepseek-v4-pro` — $0.435/M input, $0.87/M output
287|
288|**Bono:** $5 USD gratis al registrarse (no recurrente)
289|
290|**Tool Use:** ✅ Sí
291|
292|**Contexto:** 1M tokens
293|
294|**Calidad:** ⭐⭐⭐⭐ — Excelente relación calidad-precio cuando pagas.
295|
296|**Nota:** No es gratis, pero el bono inicial lo hace útil para pruebas.
297|
298|---
299|
300|## 11. OTROS PROVEEDORES
301|
302|### AI21 Labs
303|- **Modelos:** Jurassic-2, Jamba 1.5
304|- **Trial:** Créditos al registrarse
305|- **Tool Use:** Sí
306|- **Uso:** Solo para probar
307|
308|### Amazon Bedrock
309|- **Free trial:** 3 meses limitados
310|- **Modelos:** Claude 3/3.5, Llama 2/3, Mistral, Cohere, AI21
311|- **Tool Use:** Sí
312|- **Uso:** Solo como prueba temporal
313|
314|### Replicate
315|- **Free credits:** Cantidad mínima al registrarse
316|- **Modelos:** Open-source (Llama, Mistral, SD)
317|- **No hay tier gratuito permanente**
318|- **Uso:** Solo para probar
319|
320|### Together AI
321|- **Free credits:** ~$1-5 al registrarse
322|- **Modelos:** Open-source (Llama, Qwen, DeepSeek, Mixtral)
323|- **Tool Use:** Sí
324|- **Uso:** Solo para probar, no permanente
325|
326|### Perplexity
327|- **API free:** Descontinuada. Solo producto web (Perplexity Pro)
328|- **No recomendado** para API.
329|
330|### Anyscale / Fireworks AI
331|- **Fireworks:** Créditos gratuitos al registrarse, no tier permanente
332|- **Anyscale:** Descontinuó tier gratuito público
333|
334|---
335|
336|## COMPARATIVA DIRECTA PARA HERMES AGENT
337|
338|### Como modelo PRIMARIO (conversación + tool use + razonamiento)
339|Criterios: tool use bueno, contexto largo, buena calidad general, streaming.
340|
341|| Proveedor | Puntuación | Razón |
342||---|---|---|
343|| **OpenCode-Zen (DeepSeek V4 Flash)** | ⭐⭐⭐⭐ | Ya configurado, 1M contexto, tool use. **Ya funciona.** |
344|| **Nex-N2-Pro:free (OpenRouter)** | ⭐⭐⭐⭐ | Mejor alternativa gratuita directa. Tool use + multimodal. |
345|| **Nemotron 3 Ultra:free (OpenRouter)** | ⭐⭐⭐⭐ | 1M contexto, tool use, razonamiento. |
346|| **Groq (Llama 3.3 70B)** | ⭐⭐⭐⭐⭐ | El más rápido. Tool use excelente. |
347|| **GitHub Models (GPT-4.1)** | ⭐⭐⭐⭐⭐ | GPT-4.1 gratis. Tool use nativo. Límites más restrictivos. |
348|| **Google Gemini 2.0 Flash** | ⭐⭐⭐⭐ | Multimodal nativo. Tool use. Buenos límites. |
349|
350|### Como modelo AUXILIAR (visión, resúmenes, clasificación rápida)
351|Criterios: multimodal, velocidad, bajo costo.
352|
353|| Proveedor | Puntuación | Razón |
354||---|---|---|
355|| **Google Gemini 2.0 Flash** | ⭐⭐⭐⭐⭐ | Mejor multimodal gratuito. Audio, video, imágenes. |
356|| **Groq (Llama 3.1 8B)** | ⭐⭐⭐⭐ | Velocidad extrema para clasificación/resúmenes. |
357|| **Nex-N2-Pro:free (OpenRouter)** | ⭐⭐⭐⭐ | Multimodal + tool use gratis. |
358|| **GitHub Models (GPT-4o mini)** | ⭐⭐⭐⭐ | Bueno y rápido para tareas pequeñas. |
359|| **Cloudflare (Llama 3.2 11B Vision)** | ⭐⭐⭐ | Limitado pero útil si ya usas Cloudflare. |
360|
361|---
362|
363|## RECOMENDACIONES FINALES
364|
365|### Para usar AHORA con tus API keys existentes:
366|
367|**Configuración actual (ya funcional):**
368|```
369|PRIMARY: deepseek-v4-flash-free (OpenCode-Zen)
370|AUXILIARY: google/gemini-2.0-flash-exp:free (OpenRouter)
371|```
372|✅ **Esta configuración es buena.** DeepSeek V4 Flash es un modelo fronterizo excelente.
373|
374|### Mejoras sugeridas (sin costo):
375|
376|**Opción 1 — Mejor PRIMARY gratuito alternativo:**
377|```
378|PRIMARY: nex-agi/nex-n2-pro:free (OpenRouter)
379|AUXILIARY: google/gemini-2.0-flash (Google API)  
380|```
381|✅ Nex-N2-Pro (397B/17B MoE) + tool use + multimodal. Excelente.
382|
383|**Opción 2 — Máxima velocidad:**
384|```
385|PRIMARY: llama-3.3-70b-versatile (Groq)
386|AUXILIARY: google/gemini-2.0-flash (Google API)
387|```
388|✅ Groq es el más rápido. Llama 3.3 70B es calidad premium.
389|
390|**Opción 3 — Mejor calidad combinada:**
391|```
392|PRIMARY: deepseek-v4-flash (OpenCode-Zen) [actual]
393|AUXILIARY: groq (llama-3.3-70b) + gemini-2.0-flash
394|```
395|✅ Lo mejor de todos los mundos.
396|
397|### Proveedores a EVITAR como primary:
398|❌ Cloudflare Workers AI — modelos muy pequeños, sin tool use
399|❌ Hugging Face Inference API — créditos muy limitados ($0.10/mes)
400|❌ Replicate — no tiene tier gratuito real
401|❌ Perplexity — API descontinuada
402|
403|---
404|
405|## NOTAS TÉCNICAS
406|
407|### Soporte de tool/function calling por proveedor:
408|| Proveedor | Tool Calls | Parallel FC | Structured Output |
409||---|---|---|---|
410|| Google Gemini | ✅ | ✅ | ✅ (response_schema) |
411|| OpenRouter (modelos :free) | ✅ (Nex, Nemotron, Cohere) | ✅ | ✅ (structured_outputs) |
412|| Groq | ✅ | ✅ | ✅ (JSON mode) |
413|| OpenCode-Zen (DeepSeek) | ✅ | ✅ | ✅ |
414|| GitHub Models | ✅ (depende del modelo) | ✅ | ✅ |
415|| Cloudflare | ❌ | ❌ | ❌ |
416|| Hugging Face | Varía | Varía | Varía |
417|
418|### Contexto máximo gratuito:
419|| Proveedor | Contexto máximo |
420||---|---|
421|| Google Gemini 1.5 Flash | **1M tokens** |
422|| DeepSeek V4 Flash | **1M tokens** |
423|| Nemotron 3 Ultra (OpenRouter) | **1M tokens** |
424|| GitHub Models (GPT-4.1) | 32K |
425|| Nex-N2-Pro (OpenRouter) | 262K |
426|| Groq (Llama 3.3 70B) | 128K |
427|
428|---
429|
430|*Investigación completa — Junio 2026*
431|*Fuentes: Documentación oficial de cada proveedor, API de OpenRouter (v1/models), y análisis de pricing público.*
432|