# 🎯 Mega-Recopilatorio: Ideas de Workflows de Estudio

> Compilado de **5 IAs** (Claude, ChatGPT, DeepSeek, Gemini, Odysseus)
> Generado: 15 Jun 2026 | Propósito: Automatizar estudio Ing. Mecánica UNCo

---

# 1️⃣ CLAUDE — "Sistema de Automatización de Estudio"

## MÓDULO 1: Buscador Automático de PDFs
**Stack:** n8n → Odysseus → Google Scholar scraping

**Workflow n8n:**
- Trigger HTTP (webhook `/buscar-pdf`)
- Scholar Search via endpoint en Odysseus
- Filtro por PDFs de acceso abierto
- Descarga y envío a ingest pipeline

**Endpoint Odysseus a implementar:**
```python
from scholarly import scholarly

@app.post("/scholar/search")
async def search_scholar(query: str, num_results: int = 10):
    search = scholarly.search_pubs(query)
    # retorna título, url, año, open_access
```

**Uso:** `curl -X POST http://localhost:5678/webhook/buscar-pdf -d '{"tema": "determinantes matrices algebra lineal"}'`

## MÓDULO 2: PDF → Obsidian Vault
- n8n Watch Folder + Odysseus (PyMuPDF) → chunking → Ollama resumen → Obsidian
- Endpoint `/pdf/ingest` que descarga, extrae texto, resume con deepseek-r1:8b
- Formato: Markdown con headers, **negritas**, $$fórmulas$$, tags #concepto

## MÓDULO 3: Flashcards Automáticas
- Odysseus + OpenClaw (qwen3:8b) → AnkiConnect
- Prompt genera JSON con preguntas/respuestas/tipo
- n8n File Watcher dispara al crear .md nuevo

## MÓDULO 4: Tutor Virtual 24/7 (RAG)
- Odysseus con SentenceTransformers + FAISS para indexar vault
- Endpoint `/tutor/preguntar`: busca chunks relevantes, responde con deepseek-r1:8b
- OpenClaw configurado como "TutorBot" que consulta al endpoint

## MÓDULO 5: Planificación Semanal
- n8n cron (lunes 8am) → Odysseus analiza archivos no revisados → genera plan
- Prompt personalizado con materias, horas disponibles, urgencia

---

# 2️⃣ CHATGPT — "Sistema Operativo para Ingeniería Mecánica"

**Arquitectura:** n8n (cerebro) → Odysseus (API) → Obsidian (DB) → OpenClaw (investigador) → Claude Code (mano de obra)

### Workflow 1: Radar Científico Automático
- Cron diario 7:00 → Google Scholar + Semantic Scholar → OpenClaw analiza relevancia
- Prompt: "Analiza estos papers: relevancia (1-10), dificultad matemática, relación con materias"

### Workflow 2: PDF → Obsidian
- Watch Folder → Odysseus OCR → Chunking → OpenClaw resume → Nota en vault
- Incluye: resumen, fórmulas, conceptos, preguntas de examen

### Workflow 3: Flashcards
- Cada nota nueva → OpenClaw genera 30 flashcards en JSON
- Exportable a Anki u Obsidian Spaced Repetition

### Workflow 4: Tutor Virtual UNCo
- Pregunta → Odysseus busca en vault → Top 20 chunks → OpenClaw responde
- Prompt: "Responde SOLO usando apuntes del usuario. Siempre: explicación + ejemplo + ejercicio + dificultad"

### Workflow 5: Planificador Semanal
- Domingo 22:00 → Lee calendario + materias + parciales → OpenClaw genera plan
- Salida: bloques pomodoro con prioridad y riesgo de desaprobar

### Workflow 6: Generador de Exámenes
- Nota nueva → OpenClaw → Simulacro de parcial (MCQ + ejercicios + problemas integradores)

### Workflow 7: Claude Code Profesor Particular
- "Tengo que estudiar integrales dobles" → Claude Code genera carpeta con teoria.md, ejercicios.md, examen.md, soluciones.md, graficos.py

### Workflow 8: Asistente de Resolución de Guías
- Subís guía PDF → Odysseus extrae ejercicios → OpenClaw clasifica dificultad → ruta sugerida

### Workflow 9: Graficador Matemático
- Detecta f(x)=x²+2x+1 → Claude Code genera Python → PNG guardado en vault

### Workflow 10: Segundo Cerebro Mecánico
- Cada PDF → Resumen → Embeddings → Vector DB → Mapa conceptual interconectado
- Preguntás "¿Cómo conecta la entropía con los motores diesel?" y responde con todo tu historial

**Orden de implementación recomendado:**
1. PDF → Obsidian
2. Flashcards automáticas
3. Tutor RAG 24/7
4. Planificador semanal
5. Radar científico
6. Generador de simulacros
7. Segundo cerebro mecánico

---

# 3️⃣ DEEPSEEK — "Plan de Batalla Técnico"

**Estrategia híbrida:** n8n orquesta el flujo de datos, OpenClaw/Claude Code actúan como nodos de procesamiento inteligente.

### Búsqueda Automática de PDFs
**Enfoque con OpenClaw (recomendado):**
```bash
openclaw run "Busca papers sobre 'Tribología en motores a reacción' publicados después de 2020 en Google Scholar. Para cada resultado con más de 50 citas, intenta descargar el PDF"
```
**Prompt:** Navega a Scholar, filtra por fecha, extrae título/autores/resumen/citas/PDF, busca DOI en Sci-Hub si no hay PDF.

### PDF → Obsidian (paper-to-note)
**Workflow n8n:** Watch Folder (PDF nuevo) → Claude Code con skill (paper-to-note) → Obsidian local REST API.
- paper-to-note analiza figuras, cadena de argumentos, separa contenido experimental vs teórico

### Flashcards con n8n + Ollama
**Trigger:** Nota nueva en Obsidian → Obsidian API Get → AI Agent (qwen3:8b) → AnkiConnect
**Prompt:** "Genera flashcards. Formato P: [Pregunta] \n R: [Respuesta]"

### Tutor Virtual RAG
**Arquitectura:**
- ChromaDB como vector store (docker: chromadb/chroma)
- Indexación con nomic-embed-text vía Ollama
- n8n: Telegram trigger → ChromaDB query → OpenClaw RAG → respuesta
- Escalación: si OpenClaw no tiene confianza → llama a modelo externo

### Planificación Semanal
**n8n Smart_Study_Planner:** Webhook (materias, parciales, disponibilidad) → Python distribuye horas → Obsidian nota con tabla → Google Calendar events opcional

---

# 4️⃣ GEMINI — "Ingeniería de Workflows Detallada"

### Búsqueda Google Scholar
**n8n:** Webhook → SerpAPI (Google Scholar) → Code node filtra PDFs → Odysseus recibe binario → descarga
**Claude Code:** `make-code "Crea un endpoint POST /upload-pdf en FastAPI que reciba archivo binario y lo guarde"`

### PDF → Vault
**Prompt OpenClaw para deepseek-r1:8b:**
> "Actuás como tutor experto en Ing. Mecánica. Resumí el texto técnico. Formateá ecuaciones en LaTeX. Creá secciones: Conceptos Clave, Fórmulas Principales, Aplicación Práctica."

**Endpoint `/process-pdf` en Odysseus:** extrae texto → llama a Ollama → guarda .md en vault

### Flashcards con formato Obsidian-Anki
**n8n:** Cron nocturno → script lee notas modificadas → qwen3:8b extrae → formato `Pregunta :: Respuesta`
**Tip:** Usar formato del plugin Anki de Obsidian (separador `::`)

### Tutor RAG
**Claude Code:** `make-code "Crea script que lea .md del vault, fragmente en chunks de 500, genere embeddings con Ollama nomic-embed-text y guarde en ChromaDB/FAISS"`
**Endpoint `/tutor-query`:** recibe pregunta → busca en vector DB → deepseek-r1:8b responde

### Planificación Semanal
**n8n:** Google Calendar (eventos/parciales) + Read Obsidian (Pendientes_Estudio.md) → OpenClaw genera cronograma
**Prompt:** "Armame cronograma de lunes a viernes priorizando temas difíciles, bloques de 2h, Pomodoro. Tabla Markdown."

**Tip diferencial:** Pedirle a deepseek-r1:8b que verifique **consistencia dimensional** (análisis de unidades) en ecuaciones de mecánica.

---

# 5️⃣ ODYSSEUS — "Ecosistema de Estudio Autónomo (SEA-Ing)"

**Mapa del ecosistema:**
```
[Obsidian Vault] ←→ [n8n] ←→ [OpenClaw (Ollama)]
     |                    |          ├── DeepSeek-R1:8B (razonamiento)
     |                    |          ├── Qwen3:8B (texto general)
     |                    |          └── nomic-embed-text (embeddings)
     |                    ├── [Claude Code] (scripts)
     |                    └── [Odysseus] (escalación de alta complejidad)
     [ChromaDB (Vector DB)]
```

### W1: Buscador Automático de PDFs
**Trigger:** n8n schedule (domingo 22:00)
**SerpAPI** + n8n HTTP Request + filtro por PDF_url → curl descarga → Telegram notifica
**OpenClaw genera queries:** Prompt genera 5 queries académicas en español/inglés

### W2: Procesador de PDFs → Obsidian
**Trigger:** Watch Folder (~/Downloads/inbox/)
**Script Claude Code (pdf_to_vault.py):** PyMuPDF extrae texto → chunking → escribe al vault con YAML frontmatter
**OpenClaw resumidor inteligente:** Prompt estructurado con secciones: Conceptos Clave, Fórmulas (LaTeX), Aplicaciones Ing. Mecánica, Preguntas Autoevaluación

### W3: Flashcards Automáticas
**Trigger:** Nota con tag `#anki_auto`
**Pipeline:** Obsidian REST API → OpenClaw (qwen3:8b) → formato CSV "Pregunta | Respuesta" → AnkiConnect (addNote batch)

### W4: Tutor Virtual 24/7 con RAG
**Arquitectura:**
```
User (Telegram) → n8n Webhook → ChromaDB Query → OpenClaw (DeepSeek) → ¿Confianza?
                                                                  Sí → Responder
                                                                  No → Llamar a Odysseus
```
**Indexación:** Claude Code script (index_vault.py) → chromadb + OllamaEmbeddingFunction (nomic-embed-text)
**ChromaDB Docker:** `chromadb/chroma:latest` en puerto 8000
**Query Pipeline:** Telegram/Webhook → ChromaDB query → OpenClaw RAG prompt → respuesta
**Escalación:** Si OpenClaw no tiene confianza → llama a Odysseus para respuesta avanzada

---

# 📊 Comparativa de Enfoques por Herramienta

| Herramienta | Mejor para | Evitar para |
|---|---|---|
| **n8n** | Tareas lineales/repetitivas, integraciones, ETL, triggers programados | Razonamiento complejo, decisiones no determinísticas |
| **OpenClaw (Ollama)** | Procesamiento inteligente, RAG, tutoría, análisis de PDFs, generación de contenido | Tareas de alta velocidad, orquestación multi-paso |
| **Claude Code** | Scripts de una sola vez, prototipado rápido, código de infraestructura | Procesamiento recurrente (mejor n8n+Ollama) |
| **Odysseus** | Endpoints personalizados, pipeline de datos, escalación de queries complejas | Tareas que corren 24/7 sin supervisión (mejor OpenClaw) |

---

# 🚀 Roadmap Sugerido (de más fácil a más complejo)

**Fase 1 — Inmediato (días)**
- [ ] Workflow n8n: Watch Folder PDF → extraer texto → nota en Obsidian
- [ ] Endpoint Odysseus `/process-pdf` con PyMuPDF
- [ ] Claude Code: script pdf_to_vault.py

**Fase 2 — Corto plazo (1-2 semanas)**
- [ ] OpenClaw resumidor de PDFs con deepseek-r1:8b
- [ ] n8n + Ollama: flashcards desde notas de Obsidian
- [ ] Google Scholar + SerpAPI: radar de papers

**Fase 3 — Mediano plazo (3-4 semanas)**
- [ ] ChromaDB + indexación del vault
- [ ] Tutor RAG 24/7 con Telegram gateway
- [ ] Planificador semanal automático

**Fase 4 — Avanzado (1-2 meses)**
- [ ] Segundo cerebro: mapas conceptuales interconectados
- [ ] Generador de simulacros de parcial
- [ ] Claude Code Profesor Particular
- [ ] Escalación a Odysseus para queries complejas

---

> *"No es un simple chatbot de apuntes. Es un Sistema Operativo para Ingeniería Mecánica que funciona 24/7."* — ChatGPT
