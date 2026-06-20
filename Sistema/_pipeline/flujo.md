# 🔄 Flujo del Pipeline

Diagrama de etapas, procesos y responsables del Sistema Académico.

---

## Etapas

```
┌─────────────┐
│  DISCOVERY  │  ───  Buscar nuevo material (scripts, crawlers, recomendaciones)
└──────┬──────┘
       │
       v
┌─────────────┐
│   INBOX     │  ───  Material sin procesar, pendiente de indexar
└──────┬──────┘
       │
       v
┌─────────────┐
│  INDEXACIÓN │  ───  Se genera ficha del libro: metadata + score + porqué
└──────┬──────┘
       │
       v
┌─────────────┐
│   CURADO    │  ───  Selección de fuentes según criterios de calidad
└──────┬──────┘
       │
       v
┌─────────────┐
│ SÍNTESIS    │  ───  Notas desarrolladas multi-fuente con el porqué
└──────┬──────┘
       │
       v
┌─────────────┐
│   NOTAS     │  ───  Conocimiento listo para estudiar, repasar, expandir
└─────────────┘
```

---

## Responsables

| Etapa | Quién lo hace | Cómo |
|-------|--------------|------|
| **Discovery** | Scripts + Cron | Búsquedas periódicas por materia, detección de novedades |
| **Inbox** | Automático | Los resultados de discovery caen acá como archivos .md |
| **Indexación** | Script + Revisión | Script genera ficha; vos o yo revisamos y ajustamos score |
| **Curado** | Vos + Yo | Evaluación: reputación del autor, citas, actualidad |
| **Síntesis** | Vos + Yo | Se toman 2-3 fuentes y se construye nota desarrollada |
| **Notas** | Vos | Estudio, revisión, expansión sobre las notas |

---

## Criterios de avance

- Un libro pasa de `_inbox/` a `Libros/` cuando tiene ficha completa + score
- Una nota se crea en `Notas/` cuando hay al menos 2 fuentes diferentes sobre el tema
- El material descartado se archiva o elimina, no queda saturando el inbox

---

> [[Sistema/_pipeline/_index|← Volver a Pipeline]]
