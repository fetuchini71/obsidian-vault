---
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [clase/<% tp.system.suggester(["Álgebra", "Análisis Matemático", "Química"], ["algebra", "analisis", "quimica"], true, "¿Qué materia?") %>]
materia: <% tp.system.suggester(["Álgebra y Geometría I", "Análisis Matemático I", "Introducción a la Química"], ["AGI", "AMI", "IQ"], true, "¿Qué materia?") %>
estado: pendiente
semana: <% tp.date.now("ww-YYYY") %>
---

# <% tp.file.title %>

**Fecha:** <% tp.date.now("dddd, DD [de] MMMM [de] YYYY", 0, "es") %>
**Materia:** `= this.materia`
**Profesor:**
**Temas cubiertos:**

---

## Apuntes



## Preguntas pendientes

- [ ] <%= await tp.system.prompt("Pregunta pendiente (opcional)", "", false) %>

## Próxima clase

- [ ] Repasar
- [ ] Leer material
- [ ] Hacer ejercicios

---

> [!abstract] Resumen rápido
>
>
