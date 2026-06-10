> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Rectas_Plano]] ← Anterior • Siguiente: [[Alg_Numeros_Complejos]]

# Cónicas y Cuádricas

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Rectas_Plano]] (tema anterior)**
> **→ [[Alg_Numeros_Complejos]] (siguiente tema — Etapa 2)**

También: [[Eje_Analisis_Matematico]] | [[Eje_Fisica]]

---

## Parte 1: Cónicas (en R²)

Las cónicas son las curvas que se obtienen al cortar un cono con un plano. La ecuación general es:

`Ax² + Bxy + Cy² + Dx + Ey + F = 0`

**Clasificación por discriminante** (Δ = B² - 4AC):

| Δ = B² - 4AC | Tipo de cónica |
|---|---|
| Δ < 0 | Elipse (y circunferencia si A = C) |
| Δ > 0 | Hipérbola |
| Δ = 0 | Parábola |

**Diagrama: cortes del cono**
```
        /\
       /  \
      / eli\pse
     / ______\
    /\      /\
   /  \    /  \   ← plano
  / hi\p / pa \
 /____\/_/______\
        \  /
         \/
      círculo
```

---

### 1. Circunferencia

`(x - h)² + (y - k)² = r²`

- Centro en (h, k), radio r
- Caso particular de elipse con a = b = r

**Diagrama:**
```
      y
      ↑
    ┊     ·····
    ┊   ·   C   ·
    ┊  ·   r    ·
    ┊ ·    ──── ·
    ┊····(h,k)····→ x
```

> [!EXAMPLE] Circunferencia
> Hallar centro y radio de x² + y² - 6x + 4y - 3 = 0.
>
> **Solución — completando cuadrados:**
> 1. (x² - 6x) + (y² + 4y) = 3
> 2. (x² - 6x + 9) + (y² + 4y + 4) = 3 + 9 + 4
> 3. (x - 3)² + (y + 2)² = 16
> 4. Centro C(3, -2), radio r = 4

---

### 2. Elipse

`(x - h)²/a² + (y - k)²/b² = 1`

| Elemento | Significado |
|---|---|
| Centro | (h, k) |
| a | Semieje mayor (eje x si a > b) |
| b | Semieje menor |
| c = √(a² - b²) | Semidistancia focal |
| e = c/a | Excentricidad (0 < e < 1) |
| Focos | (h ± c, k) si a > b |
| Vértices | (h ± a, k), (h, k ± b) |

**Diagrama de elipse:**
```
      y
      ↑
    ┊   b
    ┊ · | ·
    ┊   |     F₁·──·F₂
    ┊   |   a
    ┊---+---→ x
      (h,k)
```

> [!TIP] Excentricidad
> e = 0 → circunferencia; e → 1 → elipse muy alargada. Las órbitas planetarias son elipses con el Sol en un foco (Kepler). En [[Eje_Analisis_Matematico]] las elipses aparecen en integrales dobles y en ecuaciones de Laplace.

> [!EXAMPLE] Elipse
> Dada la elipse (x-1)²/16 + (y+2)²/9 = 1, hallar centro, semiejes, focos y excentricidad.
>
> **Solución:**
> 1. Centro: C(1, -2)
> 2. a² = 16 → a = 4 (semieje mayor, horizontal)
> 3. b² = 9 → b = 3 (semieje menor)
> 4. c = √(a² - b²) = √(16 - 9) = √7 ≈ 2.65
> 5. Focos: F₁(1 + √7, -2) ≈ (3.65, -2); F₂(1 - √7, -2) ≈ (-1.65, -2)
> 6. e = c/a = √7/4 ≈ 0.66

---

### 3. Hipérbola

`(x - h)²/a² - (y - k)²/b² = 1` (eje focal horizontal)
`(y - k)²/a² - (x - h)²/b² = 1` (eje focal vertical)

| Elemento | Significado |
|---|---|
| Centro | (h, k) |
| Asíntotas | y - k = ±(b/a)·(x - h) |
| c = √(a² + b²) | Semidistancia focal |
| e = c/a > 1 | Excentricidad |
| Focos | (h ± c, k) si eje horizontal |

**Diagrama de hipérbola:**
```
      y
      ↑   ╱╲
    ┊  ╱  ╲
    ┊ ╱   ╲
    ┊╱    │ ╲
    ┄┄┄┄┄┄●┄┄┄┄┄→ x
    ┊╲    │ ╱
    ┊ ╲   ╱
    ┊  ╲ ╱
      (asíntotas)
```

> [!WARNING] Hipérbola vs elipse
> En la elipse se **suman** los cuadrados (= 1). En la hipérbola se **restan** (= 1). No confundir los signos. El signo negativo indica qué eje es el focal.

> [!EXAMPLE] Hipérbola
> Dada x²/9 - y²/16 = 1, hallar centro, a, b, c, focos y asíntotas.
>
> **Solución:**
> 1. Centro: C(0, 0); a = 3, b = 4
> 2. c = √(a² + b²) = √(9 + 16) = 5
> 3. Focos: F₁(5, 0), F₂(-5, 0)
> 4. Asíntotas: y = ±(4/3)·x

---

### 4. Parábola

`(x - h)² = 4p·(y - k)` (eje vertical)
`(y - k)² = 4p·(x - h)` (eje horizontal)

| Elemento | Significado |
|---|---|
| Vértice | (h, k) |
| Foco | (h, k + p) si eje vertical |
| Directriz | y = k - p si eje vertical |
| p | Distancia del vértice al foco |

**Diagrama de parábola (vertical):**
```
      y
      ↑   F
    ┊  · |
    ┊ |  |
    ┊ V─┐|
    ┊ |    |___directriz
    ┊·──────→ x
```

> [!TIP] Parábola: p
> p > 0 abre hacia arriba/derecha. p < 0 abre hacia abajo/izquierda. Cuanto mayor es |p|, más "abierta" es la parábola. Las antenas parabólicas y los faros de autos usan la propiedad reflectora de la parábola: todo rayo que llega paralelo al eje se refleja hacia el foco.

> [!EXAMPLE] Parábola
> Dada y² = 8x, hallar vértice, foco, directriz y esbozar.
>
> **Solución:**
> 1. Forma: y² = 4px → 4p = 8 → p = 2
> 2. Vértice: V(0, 0)
> 3. Foco: F(p, 0) = (2, 0) (eje horizontal, abre a derecha)
> 4. Directriz: x = -p = -2

---

## Parte 2: Superficies cuádricas (en R³) — puente a AyG II

Son la generalización de las cónicas a tres dimensiones. Ecuación general:

`Ax² + By² + Cz² + Dxy + Exz + Fyz + Gx + Hy + Iz + J = 0`

### Tipos principales

| Superficie | Ecuación canónica | Forma |
|---|---|---|
| **Elipsoide** | x²/a² + y²/b² + z²/c² = 1 | Huevo 3D |
| **Hiperboloide de 1 hoja** | x²/a² + y²/b² - z²/c² = 1 | "Torre" / hiperboloide |
| **Hiperboloide de 2 hojas** | -x²/a² - y²/b² + z²/c² = 1 | 2 cascos separados |
| **Paraboloide elíptico** | z/c = x²/a² + y²/b² | Taza / bowl |
| **Paraboloide hiperbólico** | z/c = x²/a² - y²/b² | "Silla de montar" |
| **Cono elíptico** | x²/a² + y²/b² - z²/c² = 0 | Cono doble |
| **Cilindro elíptico** | x²/a² + y²/b² = 1 | Tubo (sin z) |

**Diagramas ASCII de cuádricas:**

```
ELIPSOIDE:        PARABOLOIDE HIPERBÓLICO:
    /~\                 ╱╲
   /   \              ╱  ╲
  |     |            ╱    ╲
   \   /            ╱      ╲
    \~/            ╱________╲
                  ╱          ╲
                 ╱            ╲
               "silla de montar"
```

### Trazas de una cuádrica

Son las curvas que se obtienen al intersecar la superficie con planos coordenados (z = k, y = k, x = k). Sirven para identificar la cuádrica y esbozar su gráfica.

**Ejemplo — Trazas del elipsoide x²/4 + y²/9 + z²/1 = 1:**

| Plano | Ecuación | Tipo |
|---|---|---|
| z = 0 | x²/4 + y²/9 = 1 | Elipse |
| y = 0 | x²/4 + z²/1 = 1 | Elipse |
| x = 0 | y²/9 + z²/1 = 1 | Elipse |

> [!EXAMPLE] Identificar una cuádrica
> Identificar la superficie: x² + y² - z² = 1.
>
> **Solución:**
> 1. Ecuación: x²/1 + y²/1 - z²/1 = 1
> 2. Dos signos positivos, uno negativo → **Hiperboloide de 1 hoja**
> 3. Trazas: z = 0 → x² + y² = 1 (circunferencia)
>     x = 0 → y² - z² = 1 (hipérbola)
>     y = 0 → x² - z² = 1 (hipérbola)
> 4. Forma: "torre" o cilindro que se estrecha en el centro.

> [!WARNING] Identificación de cuádricas
> El método es: contar signos positivos en la forma canónica.
> - 3 positivos → elipsoide
> - 2 positivos, 1 negativo → hiperboloide de 1 hoja
> - 1 positivo, 2 negativos → hiperboloide de 2 hojas
> - 1 término lineal (z) y 2 cuadráticos del mismo signo → paraboloide elíptico
> - 1 término lineal (z) y 2 cuadráticos de signo opuesto → paraboloide hiperbólico
> - = 0 en vez de = 1 → cono elíptico

---

## 🔧 Aplicaciones de ingeniería

| Concepto | Aplicación |
|---|---|
| **Circunferencia** | Ruedas, engranajes, tuberías, poleas |
| **Elipse** | Órbitas planetarias (Kepler), puentes elípticos, reflectores |
| **Parábola** | Antenas parabólicas, faros, reflectores solares, trayectorias de proyectiles |
| **Hipérbola** | Sistemas de navegación (LORAN), sombras, telescopios |
| **Elipsoide** | Modelado de planetas, diseño de tanques a presión |
| **Paraboloide hiperbólico** | Techos de estructuras (forma de "silla de montar"), cubiertas arquitectónicas |
| **Hiperboloide** | Torres de enfriamiento, altavoces |

> [!NOTE] Las cuádricas son el puente entre AyG I y AyG II. En AyG I las ves al final como cierre de la geometría; en AyG II arrancás con ellas como TP1. Prestales atención porque combinan vectores, planos y cónicas en un mismo concepto. También se conectan con [[Alg_Espacios_Vectoriales]] para diagonalización de formas cuadráticas.

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Cónicas.pdf` | Alfonso: cónicas |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Cuádricas.pdf` | Alfonso: cuádricas |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/CLASE 24- ELIPSE-Hiperbola- FAIN 2024.pdf` | Curapil: elipse e hipérbola |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Circunferencia - elipse.pdf` | Vannicola: circunferencia y elipse |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Hiperbola - parabola.pdf` | Vannicola: hipérbola y parábola |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Superficies cuádricas.pdf` | Vannicola: cuádricas |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 20 y 21- ELIPSE-Hiperbola- FAIN 2025.pdf` | Diapo: elipse e hipérbola |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 22- PARABOLA-FAIN 1°C 2025.pdf` | Diapo: parábola |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/CLASE 23- CUADRICAS-FAIN 1°C 2025.pdf` | Diapo: cuádricas |
| `Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/Trabajos prácticos_/Práctica/Practica conicas_230630_231349.pdf` | Práctica: cónicas |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/Guía de cónicas.pdf` | Guía complementaria cónicas |

## 📝 Ejercicios

### TP oficial
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 7 Cónicas-Cuádricas 2025.pdf|TP N° 7 Cónicas-Cuádricas 2025]]

### TPs y resoluciones
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Solucionario - T.P. N° 7 - (Parte 2).pdf|Solucionario TP7 Parte 2]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N° 7. Cónicas 1°C 2024.pdf|TP7 Cónicas 1°C 2024]]

---

## 🧪 Ejercicios modelados

> [!EXAMPLE] Ejercicio 1 — Circunferencia
> Hallar la ecuación de la circunferencia que pasa por A(0,0), B(4,0) y C(0,2).
>
> **Guía:**
> 1. Usá la forma general: x² + y² + Dx + Ey + F = 0.
> 2. Reemplazá cada punto para obtener 3 ecuaciones.
> 3. Resolvé el sistema para D, E, F.
> 4. Completá cuadrados para hallar centro y radio.

> [!EXAMPLE] Ejercicio 2 — Elipse
> Dada la elipse 4x² + 9y² = 36, hallar:
> a) Centro, semiejes.
> b) Focos y excentricidad.
> c) Vértices.
>
> **Guía:**
> 1. Dividí todo por 36 para obtener la forma canónica.
> 2. Identificá a² y b².
> 3. Calculá c = √(a² - b²).
> 4. Los focos están sobre el eje mayor.

> [!EXAMPLE] Ejercicio 3 — Parábola (aplicación)
> Un reflector parabólico tiene 2 m de diámetro y 0.5 m de profundidad. ¿Dónde está el foco?
>
> **Guía:**
> 1. Colocá el vértice en el origen y el eje en el eje y.
> 2. La ecuación es x² = 4py.
> 3. Un punto del borde es (1, 0.5) (radio 1 m, profundidad 0.5 m).
> 4. Reemplazá para hallar p: 1² = 4p·0.5 → p = 0.5.
> 5. El foco está a 0.5 m del vértice sobre el eje.

> [!EXAMPLE] Ejercicio 4 — Hipérbola
> Dada x²/4 - y²/5 = 1, hallar:
> a) Centro, a, b.
> b) Focos.
> c) Asíntotas.
> d) Excentricidad.
>
> **Guía:**
> 1. a² = 4, b² = 5 → a = 2, b = √5.
> 2. c² = a² + b² = 9 → c = 3.
> 3. Focos en (±c, 0).
> 4. Asíntotas: y = ±(b/a)x = ±(√5/2)x.

> [!EXAMPLE] Ejercicio 5 — Identificar cuádrica
> Identificar y esbozar la superficie: z = x² + 2y².
>
> **Guía:**
> 1. Un término lineal (z) y dos cuadráticos positivos → **paraboloide elíptico**.
> 2. Trazas: z = k → x² + 2y² = k (elipses para k > 0).
> 3. y = 0 → z = x² (parábola en plano xz).
> 4. x = 0 → z = 2y² (parábola en plano yz).
> 5. Esbozá: forma de taza o bowl abriendo hacia arriba.

---

## 📚 Referencias

- **Abad** "Elementos de Álgebra" → [[Raw/material y ejercicios (profes)/AyG1/Manuel_Abad_-_Elementos_de_Algebra.pdf|PDF]]
- **Swokowski** "Álgebra y Trigonometría con Geometría Analítica" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/Swokowski-Álgebra y Trigonometría con Geometría Analítica.pdf|PDF]] (cónicas)
- **Grossman** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf|PDF]] (cuádricas)

> [!NOTE] Las cuádricas son el puente entre AyG I y AyG II. En AyG I las ves al final como cierre de la geometría; en AyG II arrancás con ellas como TP1. Prestales atención porque combinan vectores, planos y cónicas en un mismo concepto.
