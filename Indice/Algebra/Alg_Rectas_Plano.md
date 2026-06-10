> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Vectores]] ← Anterior • Siguiente: [[Alg_Conicas_Cuadricas]]

# Rectas en el Plano y Planos en el Espacio

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Vectores]] (tema anterior)**
> **→ [[Alg_Conicas_Cuadricas]] (siguiente tema)**

También: [[Eje_Fisica]] | [[Eje_Analisis_Matematico]]

---

## Parte 1: Rectas en el plano (R²)

### 1. Ecuación vectorial
`(x, y) = (x₀, y₀) + t·(d₁, d₂)` donde:
- (x₀, y₀) = punto de la recta
- (d₁, d₂) = **vector dirección** (indica la orientación)
- t ∈ ℝ = parámetro

### 2. Ecuación paramétrica
```
x = x₀ + t·d₁
y = y₀ + t·d₂
```

### 3. Ecuación continua
`(x - x₀)/d₁ = (y - y₀)/d₂` (si d₁,d₂ ≠ 0)

### 4. Ecuación implícita (cartesiana)
`Ax + By + C = 0`
- Vector normal: n = (A, B)
- Pendiente: m = -A/B

### 5. Ecuación explícita
`y = mx + b`
- m = pendiente
- b = ordenada al origen

### 6. Ecuación segmentaria
`x/a + y/b = 1`
- a = intersección con eje x
- b = intersección con eje y

**Diagrama de una recta en R²:**
```
      y
      ↑
   3  ┊        ╱
   2  ┊      ╱
   1  ┊    ╱   θ
      ┊·──╱────→ x
      0  1  2  3
      m = tan θ
```

> [!EXAMPLE] Ecuaciones de una recta
> Hallar las distintas formas de la recta que pasa por P(2, 1) con dirección d = (3, 2).
>
> **Solución:**
> 1. **Vectorial:** (x, y) = (2, 1) + t·(3, 2)
> 2. **Paramétrica:** x = 2 + 3t, y = 1 + 2t
> 3. **Continua:** (x - 2)/3 = (y - 1)/2
> 4. **Implícita:** 2(x - 2) = 3(y - 1) → 2x - 4 = 3y - 3 → 2x - 3y - 1 = 0
> 5. **Explícita:** 2x - 3y = 1 → y = (2/3)x - 1/3
>
> **Verificación:** P(2,1): 2·2 - 3·1 - 1 = 4 - 3 - 1 = 0 ✓

> [!WARNING] Formas de la recta
> - La ecuación **continua** requiere d₁,d₂ ≠ 0. Si alguna componente es 0, se escribe por separado.
> - Si d₁ = 0 → la recta es vertical: x = x₀.
> - Si d₂ = 0 → la recta es horizontal: y = y₀.
> - La pendiente no existe para rectas verticales.

---

## 7. Ángulo entre rectas

Dadas dos rectas con pendientes m₁ y m₂:
`tan θ = |(m₂ - m₁) / (1 + m₁·m₂)|`

**Rectas paralelas:** m₁ = m₂ (o A₁/A₂ = B₁/B₂)
**Rectas perpendiculares:** m₁·m₂ = -1 (o A₁·A₂ + B₁·B₂ = 0)

**Tabla de condiciones de paralelismo y perpendicularidad:**

| Forma | Paralelas | Perpendiculares |
|---|---|---|
| Explícita | m₁ = m₂ | m₁·m₂ = -1 |
| Implícita | A₁/A₂ = B₁/B₂ | A₁·A₂ + B₁·B₂ = 0 |
| Vectorial | d₁ ∥ d₂ | d₁·d₂ = 0 |

> [!EXAMPLE] Ángulo entre rectas
> Hallar el ángulo entre r: 2x - 3y + 5 = 0 y s: x + 4y - 1 = 0.
>
> **Solución:**
> 1. Pendiente de r: m₁ = -A/B = -2/(-3) = 2/3
> 2. Pendiente de s: m₂ = -1/4
> 3. tan θ = |(m₂ - m₁) / (1 + m₁·m₂)| = |(-1/4 - 2/3) / (1 + (2/3)(-1/4))|
> 4. tan θ = |(-11/12) / (1 - 1/6)| = |(-11/12) / (5/6)| = |-11/10| = 11/10
> 5. θ = arctan(11/10) ≈ 47.7°

---

## 8. Distancia de un punto a una recta

`d(P, r) = |A·x₀ + B·y₀ + C| / √(A² + B²)`

> [!EXAMPLE] Distancia punto-recta
> Calcular la distancia de P(3, -2) a la recta r: 2x - y + 4 = 0.
>
> **Solución:**
> d(P, r) = |2·3 + (-1)·(-2) + 4| / √(2² + (-1)²)
>         = |6 + 2 + 4| / √(4 + 1)
>         = 12 / √5 ≈ 5.37 u

> [!TIP] Distancia entre rectas paralelas
> Si r₁: Ax + By + C₁ = 0 y r₂: Ax + By + C₂ = 0 son paralelas, la distancia entre ellas es:
> d(r₁, r₂) = |C₂ - C₁| / √(A² + B²)

---

## Parte 2: Rectas en el espacio (R³)

### 1. Ecuación vectorial
`(x, y, z) = (x₀, y₀, z₀) + t·(d₁, d₂, d₃)`

### 2. Ecuación paramétrica
```
x = x₀ + t·d₁
y = y₀ + t·d₂
z = z₀ + t·d₃
```

### 3. Ecuación continua (simétrica)
`(x - x₀)/d₁ = (y - y₀)/d₂ = (z - z₀)/d₃` (si d₁,d₂,d₃ ≠ 0)

> [!EXAMPLE] Recta en R³
> Hallar la recta que pasa por P(1, -1, 2) y Q(3, 0, 5).
>
> **Solución:**
> 1. Vector dirección: d = Q - P = (2, 1, 3)
> 2. Vectorial: (x, y, z) = (1, -1, 2) + t·(2, 1, 3)
> 3. Paramétrica: x = 1 + 2t, y = -1 + t, z = 2 + 3t
> 4. Continua: (x-1)/2 = (y+1)/1 = (z-2)/3

---

## Parte 3: Planos en R³

### 1. Ecuación vectorial
`(x, y, z) = (x₀, y₀, z₀) + t·u + s·v`
donde u, v son vectores directores del plano.

**Diagrama de un plano:**
```
        z
        ↑
        ┊     ╱ v
        ┊   ╱
        ┊ ╱
   ·──────→ y
   ╲  P₀
    ╲ u
     ╲
      ↓ x
```

### 2. Ecuación paramétrica
```
x = x₀ + t·u₁ + s·v₁
y = y₀ + t·u₂ + s·v₂
z = z₀ + t·u₃ + s·v₃
```

### 3. Ecuación implícita
`Ax + By + Cz + D = 0`
- Vector normal: n = (A, B, C)
- Se obtiene como `n = u × v` (producto vectorial de los vectores directores)

### 4. Ecuación normal
`n · (X - P₀) = 0` donde n es el vector normal y P₀ un punto del plano.

> [!EXAMPLE] Plano a partir de tres puntos
> Hallar la ecuación del plano que pasa por A(1,0,0), B(0,2,0), C(0,0,3).
>
> **Solución:**
> 1. Vectores directores: u = B - A = (-1, 2, 0), v = C - A = (-1, 0, 3)
> 2. Vector normal: n = u × v = |î ĵ k̂; -1 2 0; -1 0 3|
> 3. n = î(2·3-0·0) - ĵ(-1·3-0·(-1)) + k̂(-1·0-2·(-1))
> 4. n = (6, 3, 2)
> 5. Ecuación: 6(x - 1) + 3(y - 0) + 2(z - 0) = 0 → 6x + 3y + 2z - 6 = 0
> 6. **Verificación:** A: 6+0+0-6=0 ✓; B: 0+6+0-6=0 ✓; C: 0+0+6-6=0 ✓
>
> **Forma segmentaria:** x/1 + y/2 + z/3 = 1

> [!TIP] Ecuación segmentaria del plano
> Si un plano corta los ejes en (a,0,0), (0,b,0), (0,0,c), su ecuación es:
> x/a + y/b + z/c = 1
> Es la forma más rápida cuando se conocen las intersecciones con los ejes.

---

## 5. Posiciones relativas

### Entre dos rectas en R³

| Caso | Condición | Intersección |
|---|---|---|
| **Paralelas** | vectores dirección paralelos, no tienen punto común | ∅ |
| **Coincidentes** | vectores dirección paralelos y comparten un punto | infinita (la misma recta) |
| **Secantes** | vectores dirección NO paralelos y se cruzan | un punto |
| **Alabeadas** | vectores dirección NO paralelos y NO se cruzan | ∅ |

### Entre recta y plano

| Caso | Condición |
|---|---|
| **Recta contenida** | punto de la recta ∈ plano y dirección paralela al plano |
| **Recta paralela** | punto de la recta ∉ plano y dirección paralela |
| **Recta secante** | dirección NO paralela al plano → se intersecan en un punto |

### Entre dos planos

| Caso | Condición |
|---|---|
| **Coincidentes** | normales paralelas y mismo punto |
| **Paralelos** | normales paralelas y puntos distintos |
| **Secantes** | normales NO paralelas → se intersecan en una recta |

> [!EXAMPLE] Intersección recta-plano
> Hallar la intersección de la recta r: (x,y,z) = (1,0,2) + t·(1,-1,1) con el plano π: 2x - y + 3z = 4.
>
> **Solución:**
> 1. Reemplazamos las paramétricas en el plano:
>    x = 1 + t, y = -t, z = 2 + t
>    2(1 + t) - (-t) + 3(2 + t) = 4
> 2. Resolvemos: 2 + 2t + t + 6 + 3t = 4
>    8 + 6t = 4 → 6t = -4 → t = -2/3
> 3. Punto de intersección: (1 - 2/3, 0 + 2/3, 2 - 2/3) = (1/3, 2/3, 4/3)
> 4. **Verificación:** 2·(1/3) - (2/3) + 3·(4/3) = 2/3 - 2/3 + 4 = 4 ✓

---

## 6. Distancias

| Distancia | Fórmula |
|---|---|
| Punto a recta (R³) | d(P, r) = \|\|(P - P₀) × d\|\| / \|\|d\|\| |
| Punto a plano | d(P, π) = \|A·x₀ + B·y₀ + C·z₀ + D\| / √(A² + B² + C²) |
| Recta y plano (paralelos) | d(r, π) = d(P₀, π) donde P₀ ∈ r |
| Planos paralelos | d(π₁, π₂) = \|D₂ - D₁\| / √(A² + B² + C²) |

> [!EXAMPLE] Distancia punto a plano
> Hallar la distancia de P(1, -2, 3) al plano π: 3x - y + 2z + 1 = 0.
>
> **Solución:**
> d(P, π) = |3·1 + (-1)·(-2) + 2·3 + 1| / √(3² + (-1)² + 2²)
>         = |3 + 2 + 6 + 1| / √(9 + 1 + 4)
>         = 12 / √14 ≈ 3.21 u

---

## 🔧 Aplicaciones de ingeniería

| Concepto | Aplicación |
|---|---|
| **Rectas en R²** | Trayectorias rectilíneas, pendientes de carreteras, diseño de rampas |
| **Planos en R³** | Superficies de piezas mecánicas, planos de corte, estructuras |
| **Intersecciones** | Cálculo de encuentros entre vigas y planos en estructuras |
| **Distancias** | Tolerancias entre componentes mecánicos, separación mínima |
| **Proyecciones** | Sombras, perspectivas en CAD, gráficos 3D |
| **Ángulo entre rectas** | Dirección de taladros, rutas de mínima energía |

> [!TIP] Visualización en R³
> Usá GeoGebra 3D o gráficos a mano alzada. La clave para entender posiciones relativas es dibujar siempre el plano como un paralelogramo y la recta como una línea que lo atraviesa (o no). En [[Eje_Analisis_Matematico]] vas a usar planos tangentes y rectas normales en superficies.

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (profes)/AyG1/AyG I - Unidad 6.pdf` | Apunte: R³ (teoría completa) |
| `Raw/material y ejercicios (profes)/AyG1/Apunte Rectas en el plano.pdf` | Apunte: rectas en el plano |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Rectas en el plano.pdf` | Alfonso: rectas en el plano |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Rectas y planos en el espacio.pdf` | Alfonso: R³ |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/Unidad 5.pdf` | Curapil: Unidad 5 (R²) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/Unidad 6.pdf` | Curapil: Unidad 6 (R³) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Rectas en el plano.pdf` | Vannicola: rectas en el plano |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Rectas en el espacio.pdf` | Vannicola: rectas en el espacio |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Planos.pdf` | Vannicola: planos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Paralelismo y perpendicularidad.pdf` | Vannicola: paralelismo y perpendicularidad |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Angulo - distancia.pdf` | Vannicola: ángulo y distancia |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Angulos y distancia.pdf` | Vannicola: ángulos y distancia |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/U 5 - R2 - 114 a 133.pdf` | Teoría extendida R² |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/U 6 - R3 - 134 a 174.pdf` | Teoría extendida R³ |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 14-RECTAS EN EL PLANO-FAIN 1°C 2025-p7.pdf` | Diapo: rectas en el plano |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 15-RECTAS EN EL PLANO-FAIN 1°C 2025-p12.pdf` | Diapo: rectas en el plano p2 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 16a-RECTAS EN EL PLANO-FAIN 1°C 2025.pdf` | Diapo: rectas en el plano p3 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 16b- PLANOS-Ecuaciones-FAIN 2024-p9.pdf` | Diapo: planos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 17- PLANOS y Rectas-posiciones relativas-1°C-FAIN 2025.pdf` | Diapo: posiciones relativas |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 18- Distancias en R3-FAIN 1°C-2025.pdf` | Diapo: distancias en R³ |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 19- posición rel-proyección-FAIN-1°C 2025.pdf` | Diapo: posición relativa y proyección |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Unidad V R2.docx` | Guía complementaria R² |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Univad VI R3.docx` | Guía complementaria R³ |

## 📝 Ejercicios

### TPs oficiales
- [[Raw/material y ejercicios (profes)/AyG1/TP_5_Rectas__en_el_plano_AyGI_mecánica.pdf|TP N° 5 Rectas en el plano]]
- [[Raw/material y ejercicios (profes)/AyG1/TP_6_Rectas_y_planos_en_el_espacio_mecánica_2025.pdf|TP N° 6 Rectas y planos en el espacio]]

### TPs con resoluciones
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Solucionario - T.P. N° 5.pdf|Solucionario TP5]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Solucionario - T.P. N° 6.pdf|Solucionario TP6]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Respuestas TP N°6. 1° C 2024.pdf|Respuestas TP6]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TPN°5 Rectas en el Plano.pdf|TPN°5 Rectas en el Plano]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TPN°6.pdf|TPN°6]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N° 5. Rectas en el Plano 1°C 2024.pdf|TP5 1°C 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N°6. Rectas y planos en el Espacio 1°C 2024.pdf|TP6 1°C 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 5_Rectas__en_el_plano_Algebra_y_geometria_i__Ea_Eo_.pdf|TP5 prácticas]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 6_Rectas_y_planos_en_el_espacio_AYG1___Victor_.pdf|TP6 prácticas]]

### Parciales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/parciales/Ejercicios 2° parcial-vectores_rectas_planos 2023.pdf|Ejercicios 2° parcial: vectores, rectas, planos]]

---

## 🧪 Ejercicios modelados

> [!EXAMPLE] Ejercicio 1 — Recta en R² (todas las formas)
> Dados los puntos A(2, -1) y B(5, 3), hallar:
> a) La ecuación vectorial de la recta AB.
> b) La ecuación paramétrica.
> c) La ecuación implícita.
> d) La ecuación explícita.
> e) La pendiente y la ordenada al origen.
>
> **Guía:**
> 1. Calculá el vector dirección d = B - A.
> 2. Usá A como punto de paso.
> 3. Para la implícita, deducí A y B de las paramétricas.
> 4. Despejá y para la explícita.

> [!EXAMPLE] Ejercicio 2 — Posiciones relativas de rectas
> Determinar si las rectas r: (x,y) = (1,2) + t(2,-1) y s: (x,y) = (-1,4) + s(-4,2) son paralelas, coincidentes o secantes.
>
> **Guía:**
> 1. Compará los vectores dirección: ¿son paralelos? (uno es múltiplo del otro).
> 2. Si son paralelos, verificá si comparten algún punto (igualando paramétricas).
> 3. Si comparten punto → coincidentes. Si no → paralelas.
> 4. Si no son paralelos → secantes (se cruzan en un punto).

> [!EXAMPLE] Ejercicio 3 — Plano a partir de dos rectas
> Hallar la ecuación del plano que contiene a las rectas r: (x,y,z) = (1,0,1) + t(1,2,-1) y s: (x,y,z) = (1,0,1) + s(0,1,2).
>
> **Guía:**
> 1. Ambas pasan por el mismo punto P(1,0,1).
> 2. Los vectores directores son dos vectores del plano: u = (1,2,-1), v = (0,1,2).
> 3. El vector normal es n = u × v.
> 4. La ecuación normal es n·(X - P) = 0.

> [!EXAMPLE] Ejercicio 4 — Distancia punto a recta en R³
> Hallar la distancia de P(2, -1, 3) a la recta r: (x,y,z) = (1,0,2) + t(2,1,-1).
>
> **Guía:**
> 1. Tomá un punto P₀ de la recta (con t=0).
> 2. Calculá el vector P - P₀.
> 3. Calculá el producto vectorial (P - P₀) × d.
> 4. Aplicá d(P,r) = ||(P-P₀)×d|| / ||d||.

> [!EXAMPLE] Ejercicio 5 — Proyección de punto sobre plano
> Hallar la proyección ortogonal de P(2, 1, 3) sobre el plano π: x - y + 2z = 5.
>
> **Guía:**
> 1. El vector normal del plano es n = (1, -1, 2).
> 2. Armá la recta perpendicular a π que pasa por P: (x,y,z) = P + t·n.
> 3. Hallá la intersección de esa recta con π (reemplazando paramétricas).
> 4. Ese punto de intersección es la proyección ortogonal.

---

## 📚 Referencias

- **Abad** "Elementos de Álgebra" → [[Raw/material y ejercicios (profes)/AyG1/Manuel_Abad_-_Elementos_de_Algebra.pdf|PDF]]
- **Anton** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/6.- Álgebra Lineal (MathRocks) - Anton.pdf|PDF]]
- **Lipschutz Schaum** → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/7.- Álgebra Lineal (MathRocks) - Lipschutz Schaum.pdf|PDF]]

> [!WARNING] Visualizá todo en GeoGebra 3D o papel. Las posiciones relativas, distancias y proyecciones son pura geometría espacial — si no ves el espacio en tu cabeza, dibujalo.
