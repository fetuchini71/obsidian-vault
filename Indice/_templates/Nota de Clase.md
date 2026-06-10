---
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [clase/<% tp.system.suggester(["Algebra", "Analisis", "Quimica"], ["algebra", "analisis", "quimica"]) %>]
materia: <% tp.system.suggester(["Algebra y Geometria I", "Analisis Matematico I", "Introduccion a la Quimica"], ["AGI", "AMI", "IQ"]) %>
estado: pendiente
semana: <% tp.date.now("ww-YYYY") %>
---

# <% tp.file.title %>

**Fecha:** <% tp.date.now("dddd, DD/MM/YYYY") %>
**Materia:** `= this.materia`
**Profesor:**
**Temas cubiertos:**

---

## Apuntes

_(Escribí acá)_

## Preguntas pendientes

- [ ]

## Proxima clase

- [ ] Repasar
- [ ] Leer material
- [ ] Hacer ejercicios

---

> [!abstract] Resumen rapido
>
