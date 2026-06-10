---
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [ejercicio/<% tp.system.suggester(["Álgebra", "Análisis Matemático", "Química"], ["algebra", "analisis", "quimica"], true, "¿Qué materia?") %>]
materia: <% tp.system.suggester(["Álgebra y Geometría I", "Análisis Matemático I", "Introducción a la Química"], ["AGI", "AMI", "IQ"], true, "¿Qué materia?") %>
fuente: <% tp.system.prompt("Fuente (libro, guía, parcial...):", "", false) %>
estado: pendiente
semana: <% tp.date.now("ww-YYYY") %>
---

# <% tp.file.title %>

## Enunciado



## Desarrollo



## Resultado

---

> [!tip]- Pista
>

> [!success]- Solución
>
