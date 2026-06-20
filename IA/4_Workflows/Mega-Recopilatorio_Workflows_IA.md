1|# 🎯 Mega-Recopilatorio: Ideas de Workflows de Estudio
2|
3|> Compilado de **5 IAs** (Claude, ChatGPT, DeepSeek, Gemini, Odysseus)
4|> Generado: 15 Jun 2026 | Propósito: Automatizar estudio Ing. Mecánica UNCo
5|
6|---
7|
8|# 1️⃣ CLAUDE — "Sistema de Automatización de Estudio"
9|
10|## MÓDULO 1: Buscador Automático de PDFs
11|**Stack:** n8n → Odysseus → Google Scholar scraping
12|
13|**Workflow n8n:**
14|- Trigger HTTP (webhook `/buscar-pdf`)
15|- Scholar Search via endpoint en Odysseus
16|- Filtro por PDFs de acceso abierto
17|- Descarga y envío a ingest pipeline
18|
19|**Endpoint Odysseus a implementar:**
20|```python
21|from scholarly import scholarly
22|
23|@app.post("/scholar/search")
24|async def search_scholar(query: str, num_results: int = 10):
25|    search = scholarly.search_pubs(query)
26|    # retorna título, url, año, open_access
27|```
28|
29|**Uso:** `curl -X POST http://localhost:5678/webhook/buscar-pdf -d '{"tema": "determinantes matrices algebra lineal"}'`
30|
31|## MÓDULO 2: PDF → Obsidian Vault
32|- n8n Watch Folder + Odysseus (PyMuPDF) → chunking → Ollama resumen → Obsidian
33|- Endpoint `/pdf/ingest` que descarga, extrae texto, resume con deepseek-r1:8b
34|- Formato: Markdown con headers, **negritas**, $$fórmulas$$, tags #concepto
35|
36|## MÓDULO 3: Flashcards Automáticas
37|- Odysseus + OpenClaw (qwen3:8b) → AnkiConnect
38|- Prompt genera JSON con preguntas/respuestas/tipo
39|- n8n File Watcher dispara al crear .md nuevo
40|
41|## MÓDULO 4: Tutor Virtual 24/7 (RAG)
42|- Odysseus con SentenceTransformers + FAISS para indexar vault
43|- Endpoint `/tutor/preguntar`: busca chunks relevantes, responde con deepseek-r1:8b
44|- OpenClaw configurado como "TutorBot" que consulta al endpoint
45|
46|## MÓDULO 5: Planificación Semanal
47|- n8n cron (lunes 8am) → Odysseus analiza archivos no revisados → genera plan
48|- Prompt personalizado con materias, horas disponibles, urgencia
49|
50|---
51|
52|# 2️⃣ CHATGPT — "Sistema Operativo para Ingeniería Mecánica"
53|
54|**Arquitectura:** n8n (cerebro) → Odysseus (API) → Obsidian (DB) → OpenClaw (investigador) → Claude Code (mano de obra)
55|
56|### Workflow 1: Radar Científico Automático
57|- Cron diario 7:00 → Google Scholar + Semantic Scholar → OpenClaw analiza relevancia
58|- Prompt: "Analiza estos papers: relevancia (1-10), dificultad matemática, relación con materias"
59|
60|### Workflow 2: PDF → Obsidian
61|- Watch Folder → Odysseus OCR → Chunking → OpenClaw resume → Nota en vault
62|- Incluye: resumen, fórmulas, conceptos, preguntas de examen
63|
64|### Workflow 3: Flashcards
65|- Cada nota nueva → OpenClaw genera 30 flashcards en JSON
66|- Exportable a Anki u Obsidian Spaced Repetition
67|
68|### Workflow 4: Tutor Virtual UNCo
69|- Pregunta → Odysseus busca en vault → Top 20 chunks → OpenClaw responde
70|- Prompt: "Responde SOLO usando apuntes del usuario. Siempre: explicación + ejemplo + ejercicio + dificultad"
71|
72|### Workflow 5: Planificador Semanal
73|- Domingo 22:00 → Lee calendario + materias + parciales → OpenClaw genera plan
74|- Salida: bloques pomodoro con prioridad y riesgo de desaprobar
75|
76|### Workflow 6: Generador de Exámenes
77|- Nota nueva → OpenClaw → Simulacro de parcial (MCQ + ejercicios + problemas integradores)
78|
79|### Workflow 7: Claude Code Profesor Particular
80|- "Tengo que estudiar integrales dobles" → Claude Code genera carpeta con teoria.md, ejercicios.md, examen.md, soluciones.md, graficos.py
81|
82|### Workflow 8: Asistente de Resolución de Guías
83|- Subís guía PDF → Odysseus extrae ejercicios → OpenClaw clasifica dificultad → ruta sugerida
84|
85|### Workflow 9: Graficador Matemático
86|- Detecta f(x)=x²+2x+1 → Claude Code genera Python → PNG guardado en vault
87|
88|### Workflow 10: Segundo Cerebro Mecánico
89|- Cada PDF → Resumen → Embeddings → Vector DB → Mapa conceptual interconectado
90|- Preguntás "¿Cómo conecta la entropía con los motores diesel?" y responde con todo tu historial
91|
92|**Orden de implementación recomendado:**
93|1. PDF → Obsidian
94|2. Flashcards automáticas
95|3. Tutor RAG 24/7
96|4. Planificador semanal
97|5. Radar científico
98|6. Generador de simulacros
99|7. Segundo cerebro mecánico
100|
101|---
102|
103|# 3️⃣ DEEPSEEK — "Plan de Batalla Técnico"
104|
105|**Estrategia híbrida:** n8n orquesta el flujo de datos, OpenClaw/Claude Code actúan como nodos de procesamiento inteligente.
106|
107|### Búsqueda Automática de PDFs
108|**Enfoque con OpenClaw (recomendado):**
109|```bash
110|openclaw run "Busca papers sobre 'Tribología en motores a reacción' publicados después de 2020 en Google Scholar. Para cada resultado con más de 50 citas, intenta descargar el PDF"
111|```
112|**Prompt:** Navega a Scholar, filtra por fecha, extrae título/autores/resumen/citas/PDF, busca DOI en Sci-Hub si no hay PDF.
113|
114|### PDF → Obsidian (paper-to-note)
115|**Workflow n8n:** Watch Folder (PDF nuevo) → Claude Code con skill (paper-to-note) → Obsidian local REST API.
116|- paper-to-note analiza figuras, cadena de argumentos, separa contenido experimental vs teórico
117|
118|### Flashcards con n8n + Ollama
119|**Trigger:** Nota nueva en Obsidian → Obsidian API Get → AI Agent (qwen3:8b) → AnkiConnect
120|**Prompt:** "Genera flashcards. Formato P: [Pregunta] \n R: [Respuesta]"
121|
122|### Tutor Virtual RAG
123|**Arquitectura:**
124|- ChromaDB como vector store (docker: chromadb/chroma)
125|- Indexación con nomic-embed-text vía Ollama
126|- n8n: Telegram trigger → ChromaDB query → OpenClaw RAG → respuesta
127|- Escalación: si OpenClaw no tiene confianza → llama a modelo externo
128|
129|### Planificación Semanal
130|**n8n Smart_Study_Planner:** Webhook (materias, parciales, disponibilidad) → Python distribuye horas → Obsidian nota con tabla → Google Calendar events opcional
131|
132|---
133|
134|# 4️⃣ GEMINI — "Ingeniería de Workflows Detallada"
135|
136|### Búsqueda Google Scholar
137|**n8n:** Webhook → SerpAPI (Google Scholar) → Code node filtra PDFs → Odysseus recibe binario → descarga
138|**Claude Code:** `make-code "Crea un endpoint POST /upload-pdf en FastAPI que reciba archivo binario y lo guarde"`
139|
140|### PDF → Vault
141|**Prompt OpenClaw para deepseek-r1:8b:**
142|> "Actuás como tutor experto en Ing. Mecánica. Resumí el texto técnico. Formateá ecuaciones en LaTeX. Creá secciones: Conceptos Clave, Fórmulas Principales, Aplicación Práctica."
143|
144|**Endpoint `/process-pdf` en Odysseus:** extrae texto → llama a Ollama → guarda .md en vault
145|
146|### Flashcards con formato Obsidian-Anki
147|**n8n:** Cron nocturno → script lee notas modificadas → qwen3:8b extrae → formato `Pregunta :: Respuesta`
148|**Tip:** Usar formato del plugin Anki de Obsidian (separador `::`)
149|
150|### Tutor RAG
151|**Claude Code:** `make-code "Crea script que lea .md del vault, fragmente en chunks de 500, genere embeddings con Ollama nomic-embed-text y guarde en ChromaDB/FAISS"`
152|**Endpoint `/tutor-query`:** recibe pregunta → busca en vector DB → deepseek-r1:8b responde
153|
154|### Planificación Semanal
155|**n8n:** Google Calendar (eventos/parciales) + Read Obsidian (Pendientes_Estudio.md) → OpenClaw genera cronograma
156|**Prompt:** "Armame cronograma de lunes a viernes priorizando temas difíciles, bloques de 2h, Pomodoro. Tabla Markdown."
157|
158|**Tip diferencial:** Pedirle a deepseek-r1:8b que verifique **consistencia dimensional** (análisis de unidades) en ecuaciones de mecánica.
159|
160|---
161|
162|# 5️⃣ ODYSSEUS — "Ecosistema de Estudio Autónomo (SEA-Ing)"
163|
164|**Mapa del ecosistema:**
165|```
166|[Obsidian Vault] ←→ [n8n] ←→ [OpenClaw (Ollama)]
167|     |                    |          ├── DeepSeek-R1:8B (razonamiento)
168|     |                    |          ├── Qwen3:8B (texto general)
169|     |                    |          └── nomic-embed-text (embeddings)
170|     |                    ├── [Claude Code] (scripts)
171|     |                    └── [Odysseus] (escalación de alta complejidad)
172|     [ChromaDB (Vector DB)]
173|```
174|
175|### W1: Buscador Automático de PDFs
176|**Trigger:** n8n schedule (domingo 22:00)
177|**SerpAPI** + n8n HTTP Request + filtro por PDF_url → curl descarga → Telegram notifica
178|**OpenClaw genera queries:** Prompt genera 5 queries académicas en español/inglés
179|
180|### W2: Procesador de PDFs → Obsidian
181|**Trigger:** Watch Folder (~/Downloads/inbox/)
182|**Script Claude Code (pdf_to_vault.py):** PyMuPDF extrae texto → chunking → escribe al vault con YAML frontmatter
183|**OpenClaw resumidor inteligente:** Prompt estructurado con secciones: Conceptos Clave, Fórmulas (LaTeX), Aplicaciones Ing. Mecánica, Preguntas Autoevaluación
184|
185|### W3: Flashcards Automáticas
186|**Trigger:** Nota con tag `#anki_auto`
187|**Pipeline:** Obsidian REST API → OpenClaw (qwen3:8b) → formato CSV "Pregunta | Respuesta" → AnkiConnect (addNote batch)
188|
189|### W4: Tutor Virtual 24/7 con RAG
190|**Arquitectura:**
191|```
192|User (Telegram) → n8n Webhook → ChromaDB Query → OpenClaw (DeepSeek) → ¿Confianza?
193|                                                                  Sí → Responder
194|                                                                  No → Llamar a Odysseus
195|```
196|**Indexación:** Claude Code script (index_vault.py) → chromadb + OllamaEmbeddingFunction (nomic-embed-text)
197|**ChromaDB Docker:** `chromadb/chroma:latest` en puerto 8000
198|**Query Pipeline:** Telegram/Webhook → ChromaDB query → OpenClaw RAG prompt → respuesta
199|**Escalación:** Si OpenClaw no tiene confianza → llama a Odysseus para respuesta avanzada
200|
201|---
202|
203|# 📊 Comparativa de Enfoques por Herramienta
204|
205|| Herramienta | Mejor para | Evitar para |
206||---|---|---|
207|| **n8n** | Tareas lineales/repetitivas, integraciones, ETL, triggers programados | Razonamiento complejo, decisiones no determinísticas |
208|| **OpenClaw (Ollama)** | Procesamiento inteligente, RAG, tutoría, análisis de PDFs, generación de contenido | Tareas de alta velocidad, orquestación multi-paso |
209|| **Claude Code** | Scripts de una sola vez, prototipado rápido, código de infraestructura | Procesamiento recurrente (mejor n8n+Ollama) |
210|| **Odysseus** | Endpoints personalizados, pipeline de datos, escalación de queries complejas | Tareas que corren 24/7 sin supervisión (mejor OpenClaw) |
211|
212|---
213|
214|# 🚀 Roadmap Sugerido (de más fácil a más complejo)
215|
216|**Fase 1 — Inmediato (días)**
217|- [ ] Workflow n8n: Watch Folder PDF → extraer texto → nota en Obsidian
218|- [ ] Endpoint Odysseus `/process-pdf` con PyMuPDF
219|- [ ] Claude Code: script pdf_to_vault.py
220|
221|**Fase 2 — Corto plazo (1-2 semanas)**
222|- [ ] OpenClaw resumidor de PDFs con deepseek-r1:8b
223|- [ ] n8n + Ollama: flashcards desde notas de Obsidian
224|- [ ] Google Scholar + SerpAPI: radar de papers
225|
226|**Fase 3 — Mediano plazo (3-4 semanas)**
227|- [ ] ChromaDB + indexación del vault
228|- [ ] Tutor RAG 24/7 con Telegram gateway
229|- [ ] Planificador semanal automático
230|
231|**Fase 4 — Avanzado (1-2 meses)**
232|- [ ] Segundo cerebro: mapas conceptuales interconectados
233|- [ ] Generador de simulacros de parcial
234|- [ ] Claude Code Profesor Particular
235|- [ ] Escalación a Odysseus para queries complejas
236|
237|---
238|
239|> *"No es un simple chatbot de apuntes. Es un Sistema Operativo para Ingeniería Mecánica que funciona 24/7."* — ChatGPT
240|