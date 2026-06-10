---
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [flashcards/<% tp.system.suggester(["Algebra", "Analisis", "Quimica"], ["algebra", "analisis", "quimica"]) %>]
materia: <% tp.system.suggester(["Algebra y Geometria I", "Analisis Matematico I", "Introduccion a la Quimica"], ["AGI", "AMI", "IQ"]) %>
estado: pendiente
semana: <% tp.date.now("ww-YYYY") %>
---

# <% tp.file.title %>

## Flashcards

#flashcards

Q:: 
A:: 

Q:: 
A:: 

Q:: 
A:: 

---

> [!info]- Como usar
> Editar en vivo, formato `Pregunta::` / `Respuesta::`.
> Usar el plugin **Spaced Repetition** para repasar.
