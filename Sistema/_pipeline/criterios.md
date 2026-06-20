# 📏 Criterios de Calidad

Cómo se evalúa y filtra el material en el Sistema.

---

## Score de calidad (para fichas de libros)

## Score de calidad (para fichas de libros)

Cada ficha en `Libros/` incluye un score que combina:

### 1. Reputación del autor (+0 a +4)
- +4: Autor de referencia mundial en el área (ej: Stewart, Kolman, Chang, Atkins)
- +3: Autor reconocido internacionalmente, usado como textbook
- +2: Autor con obra conocida pero sin gran renombre
- +1: Autor con publicaciones mínimas
- +0: Autor desconocido o sin referencias

### 2. Reconocimiento de la obra (+0 a +4)
- +4: Múltiples ediciones, textbook estándar en universidades
- +3: Varias ediciones, citado en bibliografías
- +2: Una edición pero bien referenciado
- +1: Edición única, referencias limitadas
- +0: Sin referencias ni reediciones conocidas

### 3. Actualidad (+0 a +1)
- +1: Edición coherente (últimos 20 años para ciencias exactas)
- +0: Desactualizado (puede tener valor histórico)

### 4. Disponibilidad (+0 a +1)
- +1: Accesible sin DRM
- +0: Difícil de conseguir

**Score total: 0-10**

| Rango | Interpretación |
|-------|----------------|
| 9-10  | Fuente principal recomendada |
| 6-8   | Fuente complementaria valiosa |
| 3-5   | Fuente secundaria, usar con contexto |
| 0-2   | Descartar o archivar |

---

## Criterio de paso por el pipeline

| De | A | Requisito |
|----|---|-----------|
| `_inbox/` | `Libros/` | Score ≥ 3 + ficha completa |
| `_inbox/` | Descartado | Score ≤ 2 o duplicado confirmado |
| `Libros/` | Fuente para notas | Score ≥ 6 o tema único no cubierto por fuentes principales |

## Criterio de paso por el pipeline

| De | A | Requisito |
|----|---|-----------|
| `_inbox/` | `Libros/` | Score ≥ 1 + ficha completa |
| `_inbox/` | Descartado | Score 0 o duplicado confirmado |
| `Libros/` | Fuente para notas | Score ≥ 4 o tema único no cubierto por fuentes principales |

---

> [[Sistema/_pipeline/_index|← Volver a Pipeline]]
