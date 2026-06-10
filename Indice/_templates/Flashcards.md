---
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [flashcards/<% tp.system.suggester(["Álgebra", "Análisis Matemático", "Química"], ["algebra", "analisis", "quimica"], true, "¿Qué materia?") %>]
materia: <% tp.system.suggester(["Álgebra y Geometría I", "Análisis Matemático I", "Introducción a la Química"], ["AGI", "AMI", "IQ"], true, "¿Qué materia?") %>
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

> [!info]- Cómo usar
> Editar en vivo, formato `Pregunta::` / `Respuesta::`.  
> Usar el plugin **Spaced Repetition** para repasar.
