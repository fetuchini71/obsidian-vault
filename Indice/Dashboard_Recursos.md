---
tags:
  - dashboard
  - recursos
exclude: true
---

# 📊 Dashboard de Recursos

> [!tip] Última actualización
> ```dataviewjs
> const log = dv.page("_Sistema/Registro_Busquedas.md");
> if (log) {
>   const lines = log.file.content.split("\n").filter(l => l.startsWith("|"));
>   const last = lines[lines.length - 1];
>   if (last) {
>     const fecha = last.split("|")[1]?.trim();
>     dv.paragraph(`🕐 Última búsqueda: **${fecha}**`);
>   }
> }
> ```

---

## 📈 Resumen por Eje

```dataview
TABLE 
  rows.L.len() as "PDFs encontrados",
  rows.L.filter(x => x.dificultad).dificultad as "Dificultad"
FROM "resultados"
WHERE materia
SORT fecha DESC
```

> *(Requiere que las notas de recursos tengan datos estructurados)*

## 📄 Recursos Recientes

```dataview
TABLE
  fecha as "Fecha",
  resumen as "Resumen",
  dificultad as "Nivel"
FROM "resultados"
SORT fecha DESC
LIMIT 10
```

---

## 🃏 Flashcards Pendientes

```dataview
TABLE
  rows.L.length as "Flashcards"
FROM "Flashcards"
WHERE materia
```

---

## 🔗 Acceso Rápido

| Eje | Recursos | Flashcards |
|-----|----------|------------|
| 🔷 Álgebra | [[Recursos_Algebra\|📖 Ver]] | [[Flashcards_Algebra\|🃏 Ver]] |
| 📐 Análisis | [[Recursos_Analisis\|📖 Ver]] | [[Flashcards_Analisis\|🃏 Ver]] |
| 🧪 Química | [[Recursos_Quimica\|📖 Ver]] | [[Flashcards_Quimica\|🃏 Ver]] |

---

## 📋 Últimas Búsquedas

> [!info]- Ver bitácora completa
> → [[_Sistema/Registro_Busquedas|📋 Registro de Búsquedas]]
