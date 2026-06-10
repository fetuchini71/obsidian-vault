---
created: 2026-06-10
tags: [dashboard, progreso, indice]
---

# 📊 Dashboard de Progreso

> [!tip] Atajos
> [[000_Indice|🏠 Índice General]] • [[Eje_Algebra|🔷 Álgebra]] • [[Eje_Analisis_Matematico|📐 Análisis Matemático]] • [[Eje_Quimica|🧪 Química]] • [[Recursos_Complementarios|📚 Recursos]]

---

## 📈 Progreso por Eje

```dataview
TABLE
  icono as "",
  temas as "Temas",
  etapas as "Etapas",
  progreso as "Progreso %",
  choice(estado = "completado", "✅", choice(estado = "en_progreso", "🔄", "⏳")) as "Estado",
  ultima_revision as "Última revisión"
FROM "Indice"
WHERE eje
SORT progreso DESC
```

---

## 📝 Notas por Materia

### 🔷 Álgebra
```dataview
TABLE
  file.size as "Tamaño (KB)",
  file.mtime as "Modificado"
FROM "Indice/Algebra"
WHERE file.name != "Eje_Algebra"
SORT file.name ASC
```

### 📐 Análisis Matemático
```dataview
TABLE
  file.size as "Tamaño (KB)",
  file.mtime as "Modificado"
FROM "Indice/Analisis_Matematico"
WHERE file.name != "Eje_Analisis_Matematico"
SORT file.name ASC
```

### 🧪 Química
```dataview
TABLE
  file.size as "Tamaño (KB)",
  file.mtime as "Modificado"
FROM "Indice/Quimica"
WHERE file.name != "Eje_Quimica"
SORT file.name ASC
```

---

## ⏰ Últimas Modificaciones

```dataview
TABLE
  file.folder as "Materia",
  file.size as "Tamaño (KB)",
  file.mtime as "Modificado"
FROM "Indice"
WHERE file.name != "000_Indice" AND file.name != "Dashboard_Progreso"
SORT file.mtime DESC
LIMIT 15
```

---

## 📊 Totales

```dataview
TABLE WITHOUT ID
  rows.file.folder as "Materia",
  length(rows) as "Notas",
  sum(rows.file.size) as "Total (KB)"
FROM "Indice"
WHERE file.name != "Eje_Algebra" AND file.name != "Eje_Analisis_Matematico" AND file.name != "Eje_Quimica" AND file.name != "000_Indice" AND file.name != "Dashboard_Progreso" AND file.name != "Recursos_Complementarios"
GROUP BY file.folder
SORT sum(rows.file.size) DESC
```

---

> [!info] Cómo usar este dashboard
> Los datos se actualizan automáticamente al abrir Obsidian gracias a Dataview.
> Para marcar progreso, editá el frontmatter de los archivos `Eje_*` (campo `progreso: NN`).
>
> 💡 **Tip:** Para verlo siempre al abrir, configura Homepage para que abra este dashboard en vez de 000_Indice.
