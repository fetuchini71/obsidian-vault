# 🧠 Sistema Académico

Pipeline activo de descubrimiento, procesamiento y organización de conocimiento.

```
Descubrir → Indexar → Curar → Sintetizar → Notas
   │          │         │         │
   v          v         v         v
 _inbox/   Libros/   criterios  Notas/
```

---

## ⚡ Estado del pipeline

| Etapa | Carpeta | Estado |
|-------|---------|--------|
| 📥 Descubrimientos nuevos | → [[Sistema/_inbox/_index|_inbox/]] | Vacío |
| 📚 Catálogo de libros | → [[Sistema/Libros/_index|Libros/]] | Vacío |
| 📝 Notas desarrolladas | → [[Sistema/Notas/_index|Notas/]] | Vacío |
| 📄 Textos de referencia | → [[Sistema/_referencia/_index|_referencia/]] | Vacío |

---

## 🔧 Cómo funciona

1. **Descubrir** — scripts y búsquedas encuentran material → cae a `_inbox/`
2. **Indexar** — se genera ficha del libro con metadata + score → `Libros/`
3. **Curar** — se seleccionan las mejores fuentes según criterios definidos
4. **Sintetizar** — con múltiples fuentes se arman notas desarrolladas → `Notas/`

> 📖 Documentación del sistema → [[Sistema/_pipeline/_index|_pipeline/]]
> 🛠️ Herramientas y scripts → [[Sistema/_herramientas/_index|_herramientas/]]
