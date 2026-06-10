> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Sistemas_Ecuaciones]] ← Anterior • Siguiente: [[Alg_Rectas_Plano]]

# Vectores en R² y R³

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Sistemas_Ecuaciones]] (tema anterior)**
> **→ [[Alg_Rectas_Plano]] (siguiente tema)**

También: [[Eje_Fisica]] | [[Eje_Analisis_Matematico]]

---

## 1. Definición y representación

Un **vector** es un segmento orientado con:
- **Módulo** (magnitud o longitud)
- **Dirección** (recta de acción)
- **Sentido** (hacia dónde apunta)

En R²: `v = (v₁, v₂) = v₁·î + v₂·ĵ`
En R³: `v = (v₁, v₂, v₃) = v₁·î + v₂·ĵ + v₃·k̂`

**Representación gráfica en R²:**
```
      y
      ↑
   4  ┊
   3  ┊
   2  ┊       / (3, 2)
   1  ┊     ↗
      ┊·──·──·──·──·→ x
      0  1  2  3  4
```

### Vector entre dos puntos
`AB = B - A = (b₁-a₁, b₂-a₂, b₃-a₃)`

### Módulo (norma)
`||v|| = √(v₁² + v₂²)` en R²
`||v|| = √(v₁² + v₂² + v₃²)` en R³

### Vector unitario
`û = v / ||v||` (módulo = 1)

> [!TIP] Vector unitario
> Cualquier vector se puede escribir como v = ||v||·û. Esto separa la magnitud de la dirección, útil en física para expresar fuerzas: F = |F|·F̂.

---

## 2. Operaciones

### Suma
`u + v = (u₁+v₁, u₂+v₂, u₃+v₃)`

Geométricamente: regla del paralelogramo o punta a cola:

```
    u+v
    ↗
  /   \
u      v
 \   /
   v
```

> [!EXAMPLE] Suma de vectores
> Dados u = (2, -1, 3) y v = (1, 4, -2), hallar u + v, u - v, 3u - 2v.
>
> **Solución:**
> u + v = (2+1, -1+4, 3-2) = (3, 3, 1)
> u - v = (2-1, -1-4, 3-(-2)) = (1, -5, 5)
> 3u - 2v = (6, -3, 9) - (2, 8, -4) = (4, -11, 13)

### Producto por escalar
`c·v = (c·v₁, c·v₂, c·v₃)`
- Si c > 0: misma dirección y sentido, módulo = c·||v||
- Si c < 0: misma dirección, sentido opuesto

### Combinación lineal
`w = α·u + β·v`
Un vector es combinación lineal de otros si puede expresarse así.

---

## 3. Producto escalar (punto)

`u · v = u₁·v₁ + u₂·v₂ + u₃·v₃` (resultado: **escalar**)

`u · v = ||u||·||v||·cos θ`

**Relación con ángulo:**
```
cos θ = (u·v) / (||u||·||v||)
θ = arccos(u·v / (||u||·||v||))
```

**Propiedades:**
| Propiedad | Fórmula |
|---|---|
| Conmutativa | u · v = v · u |
| Distributiva | u · (v + w) = u·v + u·w |
| Ortogonalidad | u·v = 0 ⇔ u ⟂ v |
| Norma al cuadrado | v · v = \|\|v\|\|² |

### Proyección escalar
`comp_uv = u·v / ||v||`  (componente de u en dirección de v)

### Proyección vectorial
`proy_v(u) = (u·v / ||v||²)·v`  (vector proyección de u sobre v)

> [!EXAMPLE] Producto escalar y ángulo
> Hallar el ángulo entre u = (1, 0, 2) y v = (2, -1, 0).
>
> **Solución:**
> 1. u·v = 1·2 + 0·(-1) + 2·0 = 2
> 2. ||u|| = √(1² + 0² + 2²) = √5
> 3. ||v|| = √(2² + (-1)² + 0²) = √5
> 4. cos θ = 2 / (√5·√5) = 2/5 = 0.4
> 5. θ = arccos(0.4) ≈ 66.42°
>
> **Interpretación:** Los vectores forman un ángulo agudo (producto escalar positivo).

> [!WARNING] Producto escalar
> Si u·v = 0 los vectores son ortogonales. Si u·v < 0 el ángulo es obtuso (> 90°). ¡No confundir con producto vectorial!

---

## 4. Producto vectorial (cruz) — solo en R³

`u × v = (u₂·v₃ - u₃·v₂, u₃·v₁ - u₁·v₃, u₁·v₂ - u₂·v₁)`

Resultado: **vector perpendicular** a u y v.

**Cálculo mediante determinante:**
```
u × v = | î   ĵ   k̂ |
        | u₁  u₂  u₃ |
        | v₁  v₂  v₃ |
```

**Módulo:** `||u × v|| = ||u||·||v||·sen θ`
**Interpretación geométrica:** área del paralelogramo formado por u y v.

**Propiedades:**
| Propiedad | Fórmula |
|---|---|
| Antisimetría | u × v = -(v × u) |
| Paralelismo | u × v = 0 ⇔ u ∥ v |
| Perpendicular | (u × v) ⟂ u y (u × v) ⟂ v |
| Doble producto | u × (v × w) = (u·w)·v - (u·v)·w |

### Versores canónicos
- î × ĵ = k̂
- ĵ × k̂ = î
- k̂ × î = ĵ

> [!EXAMPLE] Producto vectorial
> Calcular u × v para u = (1, 2, 3), v = (4, 5, 6).
>
> **Solución:**
> ```
> u × v = | î  ĵ  k̂ |
>         | 1  2  3 |
>         | 4  5  6 |
> ```
> = î·(2·6 - 3·5) - ĵ·(1·6 - 3·4) + k̂·(1·5 - 2·4)
> = î·(12 - 15) - ĵ·(6 - 12) + k̂·(5 - 8)
> = (-3, 6, -3)
>
> **Verificación:** u · (u×v) = (1,2,3)·(-3,6,-3) = -3+12-9 = 0 ✓
> v · (u×v) = (4,5,6)·(-3,6,-3) = -12+30-18 = 0 ✓

---

## 5. Producto mixto (triple producto escalar)

`(u × v) · w` — resultado escalar.

**Interpretación geométrica:** volumen del **paralelepípedo** formado por u, v, w.

`Vol = |(u × v) · w| = |det(u, v, w)|`

```
          w╱
          ┃
     ╱    ┃  v
      u
```

> [!EXAMPLE] Producto mixto
> Dados u = (1, 0, 0), v = (0, 1, 0), w = (0, 0, 1), calcular el volumen del paralelepípedo.
>
> **Solución:**
> u × v = (0·0-0·1, 0·0-1·0, 1·1-0·0) = (0, 0, 1) = k̂
> (u × v) · w = (0,0,1)·(0,0,1) = 1
> Vol = |1| = 1 (¡es el cubo unitario!)
>
> Por determinante: det([u v w]) = det(`[[1,0,0],[0,1,0],[0,0,1]]`) = 1 ✓
>
> **Interpretación:** el producto mixto de los vectores canónicos da el volumen del cubo de arista 1.

---

## 6. Dependencia e independencia lineal

Un conjunto de vectores es **linealmente independiente (LI)** si ninguno es combinación lineal de los otros.

En R²: máximo 2 vectores LI
En R³: máximo 3 vectores LI

**Criterio:** son LI si el determinante formado por ellos ≠ 0 (en R³).

| Condición | Interpretación |
|---|---|
| det([u,v,w]) ≠ 0 | LI — forman una base de R³ |
| det([u,v,w]) = 0 | LD — están en el mismo plano o recta |
| u = k·v | LD — paralelos (rango 1) |

---

## 7. Bases

Una **base** de Rⁿ es un conjunto de n vectores LI que generan todo el espacio.

**Base canónica:**
- R²: {î=(1,0), ĵ=(0,1)}
- R³: {î=(1,0,0), ĵ=(0,1,0), k̂=(0,0,1)}

**Base ortonormal:** vectores unitarios y ortogonales entre sí.

> [!TIP] Cambio de base
> En [[Alg_Espacios_Vectoriales]] vas a profundizar en cambio de base. La idea es que cualquier vector se escribe de forma única como combinación lineal de los vectores de la base.

---

## 8. Dependencia lineal en R²

**Criterio práctico:** dos vectores u = (u₁, u₂) y v = (v₁, v₂) son LD si existe un escalar k tal que u = k·v, o equivalentemente si det([u,v]) = u₁·v₂ - u₂·v₁ = 0.

**Casos:** dos vectores en R² son LD si son paralelos (misma dirección); si tienen direcciones distintas, generan todo R².

---

## 🔧 Aplicaciones de ingeniería

| Concepto | Aplicación |
|---|---|
| **Suma de vectores** | Composición de fuerzas en estática (puentes, estructuras) |
| **Producto escalar** | Trabajo mecánico: W = F · Δr |
| **Producto vectorial** | Momento de fuerza: τ = r × F, campo magnético |
| **Producto mixto** | Volumen de sólidos en 3D (CAD, diseño mecánico) |
| **Vectores unitarios** | Dirección de esfuerzos, vectores normales en superficies |
| **Bases ortonormales** | Sistemas de coordenadas en robótica y animación 3D |

> [!WARNING] Vectores en la práctica
> En ingeniería, los vectores aparecen en **todos lados**: fuerzas, velocidades, aceleraciones, campos eléctricos, flujo de calor. Si no entendés vectores ahora, física, estática y resistencia de materiales van a ser muy cuesta arriba.

**Conexiones:** Los vectores son la base de [[Alg_Rectas_Plano]] (rectas y planos en R³), [[Alg_Espacios_Vectoriales]] (estructura algebraica), y del cálculo en varias variables en [[Eje_Analisis_Matematico]].

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (profes)/AyG1/AyG I - Unidad 5.pdf` | Apunte: Vectores (teoría completa) |
| `Raw/material y ejercicios (profes)/AyG1/Vectores.pdf` | Apunte adicional de vectores |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Vectores.pdf` | Alfonso: vectores |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/Unidad 4.pdf` | Curapil: Unidad 4 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Vectores - modulo de un vector.pdf` | Vannicola: módulo de vector |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Producto escalar - angulos - proyecciones.pdf` | Vannicola: producto escalar |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Producto vectorial - producto mixto.pdf` | Vannicola: producto vectorial/mixto |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/U 4 - Vectores - 85 a 113.pdf` | Teoría extendida (cuadernillo) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 11-vectores-FAIN 1°C 2025_p23.pdf` | Diapo: vectores intro |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 12-vectores-FAIN 1°C 2025_p15.pdf` | Diapo: vectores p2 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 13-vectores-FAIN-1°C 2025.pdf` | Diapo: vectores p3 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/apuntes matrices,vectores,r2,r3.pdf` | Apunte: matrices, vectores, R2, R3 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Ejercicios_adicionales_de_R3.pdf` | Ejercicios adicionales de R³ |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Unidad IV Vectores.docx` | Guía complementaria: vectores |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 10-SISTEMAS DE ECUACIONES LINEALES-FAIN 1°C 2025-p23.pdf` | Diapo: SEL (prerrequisito) |

## 📝 Ejercicios

### TP oficial
- [[Raw/material y ejercicios (profes)/AyG1/TP N° 4 Vectores 2025.pdf|TP N° 4 Vectores 2025]]

### TPs con resoluciones
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/AYGI - tp4 vectores.pdf|AyGI TP4 Vectores]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N° 4 Vectores 1°C 2024.pdf|TP4 Vectores 1°C 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Resolucion_TP_Vectores_230605_090050[1].pdf|Resolución TP Vectores]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 4 Vectores_2025.pdf|TP4 Vectores prácticas]]

### Parciales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/parciales/Ejercicios 2° parcial-vectores_rectas_planos 2023.pdf|Ejercicios 2° parcial: vectores, rectas, planos]]

---

## 🧪 Ejercicios modelados

> [!EXAMPLE] Ejercicio 1 — Producto escalar y proyección
> Dados u = (2, -1, 3) y v = (0, 4, -2), hallar:
> a) u·v
> b) La proyección escalar de u sobre v
> c) La proyección vectorial de u sobre v
> d) El ángulo entre u y v
>
> **Guía:**
> 1. a) Usá la fórmula directa: u·v = u₁v₁+u₂v₂+u₃v₃.
> 2. b) comp_uv = (u·v) / ||v||.
> 3. c) proy_v(u) = comp_uv · (v/||v||).
> 4. d) cos θ = (u·v)/(||u||·||v||).

> [!EXAMPLE] Ejercicio 2 — Producto vectorial y área
> Dados u = (2, 1, -1) y v = (3, 0, 1), hallar:
> a) u × v
> b) Un vector unitario perpendicular a u y v
> c) El área del paralelogramo formado por u y v
>
> **Guía:**
> 1. a) Usá el determinante con î, ĵ, k̂.
> 2. b) El vector perpendicular es (u×v)/||u×v||.
> 3. c) Área = ||u × v||.

> [!EXAMPLE] Ejercicio 3 — Producto mixto y volumen
> Determinar si u = (1, 2, 0), v = (0, 1, 3), w = (2, 1, -1) son coplanares.
>
> **Guía:**
> 1. Calculá (u × v) · w.
> 2. Si el producto mixto = 0, los vectores son coplanares (volumen = 0).
> 3. También se puede calcular det([u v w]).

> [!EXAMPLE] Ejercicio 4 — Dependencia lineal
> Determinar si los vectores u = (1, 2, 1), v = (2, 4, 2), w = (0, 1, -1) son LI o LD.
>
> **Guía:**
> 1. Armá la matriz con los vectores como filas o columnas.
> 2. Calculá el determinante (si es 3×3).
> 3. Si det ≠ 0 → LI; si det = 0 → LD.
> 4. Si son LD, encontrá la relación de dependencia.

> [!EXAMPLE] Ejercicio 5 — Aplicación: fuerzas
> Un cuerpo está sometido a dos fuerzas: F₁ = (10, 5, 0) N y F₂ = (-3, 8, 2) N.
> a) Hallar la fuerza resultante.
> b) Hallar el ángulo entre F₁ y F₂.
> c) Hallar un vector perpendicular a ambas fuerzas.
>
> **Guía:**
> 1. a) Sumá componente a componente.
> 2. b) Usá producto escalar.
> 3. c) Usá producto vectorial.

---

## 📚 Referencias

- **Abad** "Elementos de Álgebra" → [[Raw/material y ejercicios (profes)/AyG1/Manuel_Abad_-_Elementos_de_Algebra.pdf|PDF]]
- **Larson** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf|PDF]]

> [!WARNING] Los vectores son el lenguaje de la física y la geometría. Sin entender vectores no vas a poder hacer estática, dinámica, electromagnetismo, ni análisis de varias variables. Usá GeoGebra 3D para visualizar!
