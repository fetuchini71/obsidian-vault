---
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [ejercicio/<% tp.system.suggester(["Algebra", "Analisis", "Quimica"], ["algebra", "analisis", "quimica"]) %>]
materia: <% tp.system.suggester(["Algebra y Geometria I", "Analisis Matematico I", "Introduccion a la Quimica"], ["AGI", "AMI", "IQ"]) %>
fuente: <% tp.system.prompt("Fuente (libro, guia, parcial...)", "") %>
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

> [!success]- Solucion
>
