> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] ← Anterior: (primero del eje) • Siguiente: [[Alg_Matrices_Determinantes]]
> Recibe de: secundaria • Abre a: matrices, SEL, vectores, análisis matemático

# Números Reales

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Eje_Algebra]] (volver al eje)**
> **→ [[Alg_Matrices_Determinantes]] (siguiente tema)**

También: [[Eje_Analisis_Matematico]] | [[Eje_Quimica]]

---

## 1. Conjuntos numéricos

Los números reales son la base de todo el cálculo y el álgebra. La jerarquía de conjuntos es:

```
        ┌──────────────────────────┐
        │         ℝ (Reales)       │
        │  ┌──────────────────┐    │
        │  │  ℚ (Racionales)  │    │
        │  │  ┌────┐ ┌─────┐  │    │
        │  │  │ ℤ │ │  I  │  │    │
        │  │  │┌─┐│ │(Irrac)│  │    │
        │  │  ││ℕ││ │      │  │    │
        │  │  │└─┘│ │      │  │    │
        │  │  └────┘ └─────┘  │    │
        │  └──────────────────┘    │
        └──────────────────────────┘
```

- **Naturales (ℕ)**: 1, 2, 3, … Enteros positivos. Sirven para contar.
- **Enteros (ℤ)**: …, -2, -1, 0, 1, 2, … Naturales más sus opuestos y el cero.
- **Racionales (ℚ)**: fracciones `a/b` con `a,b ∈ ℤ`, `b ≠ 0`. Tienen representación decimal finita o periódica.
- **Irracionales (I)**: no se expresan como fracción. Decimales infinitos no periódicos: π, √2, e, φ.
- **Reales (ℝ)**: unión de racionales e irracionales. Completitud: toda sucesión de Cauchy converge.

> [!TIP] Visualización
> Pensá en la **recta numérica**: cada punto sobre la recta es un número real. Los racionales son densos (entre dos racionales hay infinitos racionales), pero los irracionales son más (¡potencia del continuo!). La recta real no tiene "agujeros".

### Propiedades clave de ℝ

| Propiedad | Significado |
|---|---|
| **Cuerpo ordenado completo** | Se pueden sumar, restar, multiplicar, dividir (excepto ÷0), comparar (<, >, =), y toda sucesión de Cauchy converge |
| **Asociativa** | (a + b) + c = a + (b + c) • (a·b)·c = a·(b·c) |
| **Conmutativa** | a + b = b + a • a·b = b·a |
| **Distributiva** | a·(b + c) = a·b + a·c |
| **Elemento neutro** | 0 para suma / 1 para producto |
| **Elemento inverso** | -a para suma / 1/a para producto (a ≠ 0) |
| **Tricotomía** | Dados a, b ∈ ℝ: a < b, a = b o a > b |

> [!WARNING] Error común
> La propiedad distributiva **NO** funciona con potencias: (a + b)² ≠ a² + b². El binomio al cuadrado es (a + b)² = a² + 2ab + b². Tampoco confundir 1/(a + b) con 1/a + 1/b.

---

## 2. Intervalos

Representan subconjuntos de ℝ. Son fundamentales para expresar soluciones de inecuaciones y dominios de funciones.

| Tipo | Notación | Desigualdad | Gráfico |
|---|---|---|---|
| Abierto | (a, b) | a < x < b | ○───○ |
| Cerrado | [a, b] | a ≤ x ≤ b | ●───● |
| Semiabierto | (a, b] | a < x ≤ b | ○───● |
| Semirrecta izq | (-∞, b) | x < b | ←───○ |
| Semirrecta der | (a, +∞) | x > a | ○───→ |
| Semirrecta cerrada | (-∞, b] | x ≤ b | ←───● |
| Todo ℝ | (-∞, +∞) | x ∈ ℝ | ←─────→ |

> [!EXAMPLE] Intervalos — Operaciones básicas
> Dados A = [−2, 3) y B = (1, 5], hallar A ∩ B y A ∪ B.
>
> **Solución:**
> Trazamos la recta numérica:
> ```
> A:   ●━━━━━━━━○
>      -2        3
> B:        ○━━━━━━━●
>           1       5
> A∩B:      ○━━━━○
>            1    3
> A∪B: ●━━━━━━━━━━━━●
>      -2            5
> ```
> A ∩ B = (1, 3)   (abierto en ambos extremos)
> A ∪ B = [−2, 5]  (cerrado en -2 y 5)

> [!WARNING] Intervalos
> - **Corchete `[` o `]`** → incluye el extremo (punto lleno ●)
> - **Paréntesis `(` o `)`** → NO incluye el extremo (punto vacío ○)
> - El símbolo ∞ **siempre** va con paréntesis: no es un número que se pueda incluir.

---

## 3. Valor absoluto

`|x| = { x, si x ≥ 0; -x, si x < 0 }`

El valor absoluto mide la **distancia** al origen. Geométricamente, |x - a| es la distancia entre x y a en la recta real.

**Propiedades:**
| Propiedad | Fórmula |
|---|---|
| No negatividad | \|x\| ≥ 0 siempre |
| Multiplicativo | \|x·y\| = \|x\|·\|y\| |
| Desigualdad triangular | \|x + y\| ≤ \|x\| + \|y\| |
| Distancia | \|x\| < a ⇔ -a < x < a |
| Complemento | \|x\| > a ⇔ x < -a o x > a |
| Potencia | \|x²\| = \|x\|² = x² |

> [!EXAMPLE] Ecuación con valor absoluto
> Resolver |2x - 3| = 7.
>
> **Solución paso a paso:**
> 1. Aplicamos la definición: |X| = c ⇒ X = c o X = -c
> 2. **Caso 1:** 2x - 3 = 7 → 2x = 10 → x = 5
> 3. **Caso 2:** 2x - 3 = -7 → 2x = -4 → x = -2
> 4. **Verificación:** |2·5 - 3| = |7| = 7 ✓ ; |2·(-2) - 3| = |-7| = 7 ✓
> 5. **Solución:** x = 5 o x = -2

> [!EXAMPLE] Inecuación con valor absoluto
> Resolver |x + 1| ≤ 3.
>
> **Solución:**
> 1. |X| ≤ a ⇔ -a ≤ X ≤ a
> 2. -3 ≤ x + 1 ≤ 3
> 3. Restamos 1: -4 ≤ x ≤ 2
> 4. **Solución:** x ∈ [−4, 2]

> [!TIP] Clave para desigualdades con valor absoluto
> Recordar el esquema:
> - **|x| < a**  →  intervalo **central**  →  (-a, a)
> - **|x| > a**  →  unión de dos **semirrectas**  →  (-∞, -a) ∪ (a, ∞)
> ¡El signo de la desigualdad determina si la solución es "entre" o "fuera"!

---

## 4. Ecuaciones

Resolver una ecuación es encontrar el/los valor/es de la variable que satisfacen la igualdad.

### Tipos principales

| Tipo | Forma general | Solución |
|---|---|---|
| **Lineal** | ax + b = 0 | x = -b/a |
| **Cuadrática** | ax² + bx + c = 0 | x = [-b ± √(b² - 4ac)]/(2a) |
| **Con valor absoluto** | \|ax + b\| = c | ax + b = c o ax + b = -c |
| **Racional** | P(x)/Q(x) = 0 | P(x) = 0, Q(x) ≠ 0 |
| **Irracional** | √(ax + b) = c | elevar al cuadrado, verificar |

**Discriminante de la ecuación cuadrática:** Δ = b² - 4ac
- Δ > 0 → 2 raíces reales distintas
- Δ = 0 → 1 raíz real doble
- Δ < 0 → 2 raíces complejas conjugadas

> [!EXAMPLE] Ecuación cuadrática
> Resolver 2x² - 5x + 2 = 0.
>
> **Solución:**
> 1. Identificamos: a = 2, b = -5, c = 2
> 2. Discriminante: Δ = (-5)² - 4·2·2 = 25 - 16 = 9
> 3. Como Δ > 0, hay dos soluciones reales:
> 4. x = [5 ± √9] / (2·2) = [5 ± 3] / 4
> 5. x₁ = (5 + 3)/4 = 2 ; x₂ = (5 - 3)/4 = 1/2
> 6. **Verificación:** 2·4 - 10 + 2 = 0 ✓ ; 2·(1/4) - 5·(1/2) + 2 = 0.5 - 2.5 + 2 = 0 ✓

> [!WARNING] Ecuaciones racionales
> Siempre verificar que la solución no anule el denominador. Por ejemplo:
> 1/(x-1) = 2 → 1 = 2(x-1) → x = 3/2. Pero x = 1 no es solución porque anula el denominador. ¡Siempre descartar valores que hagan Q(x) = 0!

---

## 5. Inecuaciones

Desigualdades con variable. Se resuelven como ecuaciones pero:
- **Multiplicar/dividir por negativo invierte el signo de la desigualdad**
- Ejemplo: -2x > 4 ⇒ x < -2

**Solución:** se expresa como intervalo o unión de intervalos.

| Tipo | Ejemplo | Solución |
|---|---|---|
| Lineal | 3x - 6 > 0 | x > 2 → (2, +∞) |
| Cuadrática | x² - 4 ≤ 0 | x ∈ [−2, 2] |
| Racional | (x-1)/(x+2) ≥ 0 | x ∈ (-∞, -2) ∪ [1, +∞) |

> [!EXAMPLE] Inecuación cuadrática
> Resolver x² - x - 6 > 0.
>
> **Solución:**
> 1. Factorizamos: (x - 3)(x + 2) > 0
> 2. Raíces: x = 3, x = -2
> 3. Estudiamos signos en la recta:
> ```
> Signo de (x+2):  -------○+++++++
>                 -2
> Signo de (x-3):  -----------○+++
>                          3
> Producto:        ++++○----○+++
>                 -2     3
> ```
> 4. Solución: x ∈ (-∞, -2) ∪ (3, +∞)

**Aplicación en ingeniería:** Las inecuaciones modelan restricciones físicas: fuerzas máximas que soporta un material, voltajes máximos en un circuito, tolerancias de fabricación, etc.

---

## 6. Sumatoria (notación Σ)

`Σᵢ₌₁ⁿ aᵢ = a₁ + a₂ + a₃ + ... + aₙ`

**Propiedades:**

| Propiedad | Fórmula |
|---|---|
| Factor común | Σc·aᵢ = c·Σaᵢ |
| Linealidad | Σ(aᵢ + bᵢ) = Σaᵢ + Σbᵢ |
| Suma de primeros n naturales | Σᵢ₌₁ⁿ i = n(n+1)/2 |
| Suma de cuadrados | Σᵢ₌₁ⁿ i² = n(n+1)(2n+1)/6 |
| Suma de cubos | Σᵢ₌₁ⁿ i³ = [n(n+1)/2]² |

> [!EXAMPLE] Sumatoria
> Calcular Σᵢ₌₁⁵ (2i + 3).
>
> **Solución:**
> Σ(2i + 3) = 2·Σi + Σ3 = 2·(5·6/2) + 5·3 = 2·15 + 15 = 45
>
> **Verificación directa:** (2·1+3)+(2·2+3)+(2·3+3)+(2·4+3)+(2·5+3) = 5+7+9+11+13 = 45 ✓

> [!TIP] Notación Σ
> Es la base de las sumas de Riemann en cálculo integral ([[Eje_Analisis_Matematico]]). También se usa para promedios, series y estadística. En [[Alg_Matrices_Determinantes]] la vas a usar para definir el producto matricial.

---

## 🔧 Aplicaciones de ingeniería

| Concepto | Aplicación |
|---|---|
| **Intervalos** | Tolerancias en fabricación: una pieza debe medir 10 ± 0.05 mm → [9.95, 10.05] |
| **Valor absoluto** | Margen de error en mediciones: \|x - x_real\| < ε |
| **Desigualdades** | Rangos de operación en circuitos: 3.3V ≤ V ≤ 5V |
| **Ecuaciones cuadráticas** | Trayectoria de proyectiles (caída libre), diseño de lentes, optimización |
| **Sumatoria** | Aproximación de integrales (sumas de Riemann), series de Fourier, análisis de señales |

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (profes)/AyG1/AyG I - Unidad 1.pdf` | Apunte completo de números reales |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Numeros reales.pdf` | Teoría de Alfonso |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/Unidad 1.pdf` | Teoría de Curapil |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Números reales - relacion de orden.pdf` | Vannicola: relación de orden |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Números reales - valor absoluto.pdf` | Vannicola: valor absoluto |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Números reales - sumatoria.pdf` | Vannicola: sumatoria |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Guía de Ejercicios Unidas I a III.docx` | Guía complementaria de Unidades I, II y III |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Demana-Precalculo.pdf` | Precálculo Demana |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Swokowski-Álgebra y Trigonometría con Geometría Analítica.pdf` | Swokowski |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Zill-Algebra trigonometría y geometría analítica.pdf` | Zill |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Larson-Precálculo.pdf` | Larson Precálculo |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Michael_Sullivan_Precalculo_Spanish_Edi.pdf` | Sullivan Precálculo |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/Apuntes AyGI - Cox Rocío 2018.pdf` | Apuntes Cox |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 1-REALES-Conjuntos Numéricos-FAIN-1°C 2025.pdf` | Diapo: conjuntos numéricos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 2-REALES-Ecuaciones-FAIN-1°C 2025.pdf` | Diapo: ecuaciones |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 3-REALES-Relación Orden-FAIN-1°C 2025.pdf` | Diapo: relación de orden |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 4-REALES-Valor Absoluto-FAIN-1°C 2025.pdf` | Diapo: valor absoluto |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 5-REALES-Potencia-Radicales-Logaritmos-FAIN-1°C 2025.pdf` | Diapo: potencia, radicales, logaritmos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 6-SUMATORIA-FAIN-1°C 2025.pdf` | Diapo: sumatoria |

## 📝 Ejercicios

### TP oficial
- [[Raw/material y ejercicios (profes)/AyG1/TP N° 1 - Números Reales 2025.pdf|TP N° 1 - Números Reales 2025]]

### TPs de años anteriores (con resoluciones!)
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 1 - Reales 2025.pdf|TP 1 - Reales 2025 (práctica)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/AYGI - tp1 números reales .pdf|AyGI TP1 Reales (resuelto)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TPN°1 N°Reales (1).pdf|TPN°1 Reales]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Respuestas TPN°1 Reales 2024.pdf|Respuestas TP1 Reales 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N°1 Reales 1°C. 2024.pdf|TP1 Reales 1°C 2024]]

### Parciales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/parciales/Ejercicios 1° parcial-Reales-Matrices-SEL.pdf|Ejercicios 1er parcial: Reales-Matrices-SEL]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/parciales/Parciales 2023.pdf|Parciales 2023]]

### Guías complementarias
- [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Guía de Ejercicios Unidas I a III.docx|Guía Unidades I-III]]

---

## 🧪 Ejercicios modelados

> [!EXAMPLE] Ejercicio 1 — Intervalos y operaciones
> Sean A = [-3, 4), B = (0, 6], C = (-∞, 2). Hallar:
> a) A ∩ B   b) A ∪ C   c) (A ∩ B) − C
>
> **Guía:**
> 1. Dibujá cada intervalo en una recta numérica separada.
> 2. Para la intersección, buscá la zona donde TODOS los intervalos se solapan.
> 3. Para la unión, tomá todo lo que cubre ALGUNO.
> 4. (A ∩ B) − C significa: elementos de A∩B que no están en C.
> 5. Expresá el resultado como intervalo o unión de intervalos.

> [!EXAMPLE] Ejercicio 2 — Valor absoluto
> Resolver |x - 2| + |x + 1| = 5.
>
> **Guía:**
> 1. Identificá los puntos críticos: x = 2 y x = -1 (donde cada valor absoluto cambia de signo).
> 2. Dividí la recta real en tres regiones: x < -1, -1 ≤ x < 2, x ≥ 2.
> 3. En cada región, reemplazá los valores absolutos según la definición.
> 4. Resolvé la ecuación lineal resultante en cada región.
> 5. Verificá que la solución pertenezca a la región correspondiente.

> [!EXAMPLE] Ejercicio 3 — Ecuación cuadrática
> Un proyectil sigue la trayectoria h(t) = -4.9t² + 30t + 2 (en metros).
> a) ¿En qué instante alcanza altura máxima?
> b) ¿Cuándo toca el suelo?
> c) ¿Alcanza los 50 m de altura?
>
> **Guía:**
> 1. a) El máximo de una cuadrática ax²+bx+c está en x = -b/(2a).
> 2. b) h(t) = 0 → fórmula resolvente; descartar t < 0.
> 3. c) Plantear -4.9t² + 30t + 2 = 50 → si el discriminante es positivo, sí alcanza.

> [!EXAMPLE] Ejercicio 4 — Inecuación racional
> Resolver (x² - 1)/(x - 3) ≤ 0.
>
> **Guía:**
> 1. Factorizá numerador: x² - 1 = (x-1)(x+1).
> 2. Hallá las raíces del numerador (x = -1, x = 1) y del denominador (x = 3).
> 3. Ubicá estos puntos en la recta real (el denominador siempre va con ○).
> 4. Analizá el signo del cociente en cada intervalo.
> 5. La solución incluye donde el cociente es ≤ 0.

> [!EXAMPLE] Ejercicio 5 — Sumatoria
> Calcular Σₖ₌₁ⁿ (k² + 3k - 1) y simplificar.
>
> **Guía:**
> 1. Separá la suma en tres sumas independientes: Σk² + 3Σk - Σ1.
> 2. Usá las fórmulas: Σk = n(n+1)/2, Σk² = n(n+1)(2n+1)/6, Σ1 = n.
> 3. Sumá y simplificá la expresión algebraica resultante.
> 4. Verificá para n = 1, 2, 3.

---

## 📚 Referencias

- **Abad** "Elementos de Álgebra" → [[Raw/material y ejercicios (profes)/AyG1/Manuel_Abad_-_Elementos_de_Algebra.pdf|PDF]]
- **Demana** "Precálculo" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Demana-Precalculo.pdf|PDF]]
- **Swokowski** "Álgebra y Trigonometría" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Swokowski-Álgebra y Trigonometría con Geometría Analítica.pdf|PDF]]
- **Cuadernillo Álgebra y Geometría 1** (teoría 2013) → [[Raw/material y ejercicios (profes)/AyG1/Cuadernillo Algebra y Geometría1_teoria 2013 completa.pdf|PDF]]

> [!WARNING] Requisitos
> Necesitás tener claros los conceptos de aritmética básica y álgebra elemental de secundaria. Si tenés dudas, repasá con los libros de Precálculo. Los números reales son el piso de TODO el resto de la materia.
