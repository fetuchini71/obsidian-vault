> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Numeros_Reales]] ← Anterior • Siguiente: [[Alg_Sistemas_Ecuaciones]]

# Matrices y Determinantes

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Numeros_Reales]] (tema anterior)**
> **→ [[Alg_Sistemas_Ecuaciones]] (siguiente tema)**

También: [[Eje_Analisis_Matematico]] | [[Eje_Fisica]]

---

## 1. Matrices

Una **matriz** es un arreglo rectangular de números (reales en nuestro caso) ordenados en **filas** (horizontales) y **columnas** (verticales).

``
Aₘₓₙ = [aᵢⱼ]   (i = 1,…,m filas, j = 1,…,n columnas)

     col₁  col₂  …  colₙ
     ┌                       ┐
fil₁ │ a₁₁   a₁₂   …   a₁ₙ  │
fil₂ │ a₂₁   a₂₂   …   a₂ₙ  │
  …  │   …     …    …    …   │
filₘ │ aₘ₁   aₘ₂   …   aₘₙ  │
     └                       ┘
``

El elemento aᵢⱼ está en la fila i, columna j.

> [!EXAMPLE] Las matrices aparecen en **todos** los problemas de ingeniería: en [[Eje_Fisica]] para representar sistemas de fuerzas, en [[Eje_Analisis_Matematico]] para sistemas de ecuaciones diferenciales, en [[Eje_Quimica]] para balanceo estequiométrico.

### Tipos de matrices

| Matriz | Propiedad | Ejemplo |
|--------|-----------|---------|
| **Fila** | 1 fila, n columnas | [1  0  −3] |
| **Columna** | m filas, 1 columna | [2;  −1;  5] |
| **Cuadrada** | m = n | 3×3, 2×2, etc. |
| **Nula** | todos los elementos son 0 | [0  0;  0  0] |
| **Diagonal** | solo elementos en diagonal principal ≠ 0 | diag(2, −1, 5) |
| **Identidad Iₙ** | diagonal = 1, resto = 0 | I₃, I₂ |
| **Triangular superior** | aᵢⱼ = 0 para i > j | [1 2 3;  0 4 5;  0 0 6] |
| **Triangular inferior** | aᵢⱼ = 0 para i < j | [1 0 0;  2 3 0;  4 5 6] |
| **Simétrica** | A = Aᵀ (aᵢⱼ = aⱼᵢ) | [1 2;  2 3] |
| **Antisimétrica** | A = −Aᵀ (aᵢⱼ = −aⱼᵢ) | [0  −2;  2 0] |
| **Ortogonal** | Aᵀ = A⁻¹ | Matrices de rotación |

---

## 2. Operaciones con matrices

### Suma y resta
Se suman/restan **elemento a elemento**. Misma dimensión requerida.
``
Si A y B son m×n → (A ± B)ᵢⱼ = aᵢⱼ ± bᵢⱼ
``

### Multiplicación por escalar
``
c·A = [c·aᵢⱼ]   (cada elemento se multiplica por c)
``

### Multiplicación de matrices
Dadas A(m×n) y B(n×p), su producto C = A·B es de tamaño m×p:

``
cᵢⱼ = Σₖ aᵢₖ · bₖⱼ   (producto punto de la fila i de A con columna j de B)
``

``
     B: n×p
     ┌─────┐
     │ b₁ⱼ │
     │  ⁞  │
A    │ bₙⱼ │          C = A·B : m×p
┌─────┐     │          ┌─────────┐
│aᵢ₁…aᵢₙ│──╋──→ cᵢⱼ──→│   cᵢⱼ   │
└─────┘     │          └─────────┘
     └─────┘
``

> [!EXAMPLE] **Ejemplo 1: Multiplicación de matrices**
>
> Sean A = [2  −1  0]  (1×3) y B = `[[3];  [1];  [−2]]`  (3×1)
>          [1   2  3]
>
> A·B = [ 2·3 + (−1)·1 + 0·(−2) ] = [6 − 1 + 0] = [5]
>        [ 1·3 +   2·1  + 3·(−2) ]   [3 + 2 − 6]   [−1]
>
> Resultado: A·B = [5;  −1]  (2×1)

> [!WARNING] La multiplicación de matrices **NO es conmutativa**: A·B ≠ B·A en general. De hecho, ni siquiera están garantizadas las dimensiones compatibles en ambos sentidos. Siempre verificá dimensiones antes de multiplicar.

### Potencias
Para matrices cuadradas: A² = A·A, A³ = A·A·A, etc. Solo definidas para matrices cuadradas.

### Traspuesta
Aᵀ: intercambiar filas por columnas.

| Propiedad | Fórmula |
|-----------|---------|
| Involutiva | (Aᵀ)ᵀ = A |
| Distributiva suma | (A + B)ᵀ = Aᵀ + Bᵀ |
| Producto | (A·B)ᵀ = Bᵀ·Aᵀ (¡el orden se invierte!) |
| Escalar | (c·A)ᵀ = c·Aᵀ |
| Inversa | (A⁻¹)ᵀ = (Aᵀ)⁻¹ |

### Traza
Para matrices cuadradas: tr(A) = Σᵢ aᵢᵢ (suma de la diagonal principal).

Propiedades:
- tr(A + B) = tr(A) + tr(B)
- tr(c·A) = c·tr(A)
- tr(A·B) = tr(B·A) (¡aunque sean de distinto tamaño!)

---

## 3. Determinantes

El **determinante** es un número escalar que se asigna a una matriz cuadrada y condensa información clave (invertibilidad, volumen, orientación).

### Cálculo

**2×2:**
``
det( [a  b] ) = ad − bc
     [c  d]
``

**3×3 (Regla de Sarrus):**
Repetí las primeras dos columnas a la derecha. Sumá las diagonales descendentes (↘) y restá las ascendentes (↗).

``
det( [a₁₁  a₁₂  a₁₃] )    a₁₁  a₁₂
     [a₂₁  a₂₂  a₂₃]      a₂₁  a₂₂
     [a₃₁  a₃₂  a₃₃]      a₃₁  a₃₂

  = a₁₁·a₂₂·a₃₃ + a₁₂·a₂₃·a₃₁ + a₁₃·a₂₁·a₃₂
   − a₁₃·a₂₂·a₃₁ − a₁₁·a₂₃·a₃₂ − a₁₂·a₂₁·a₃₃
``

> [!EXAMPLE] **Ejemplo 2: Regla de Sarrus paso a paso**
>
> `A = [[1,  2,  0],`
> `     [3, −1,  2],`
> `     [0,  4, −3]]`
>
> ``
> det(A) = 1·(−1)·(−3) + 2·2·0 + 0·3·4
>         − 0·(−1)·0 − 1·2·4 − 2·3·(−3)
>
>       = 1·(3) + 0 + 0  − 0 − 8 − (−18)
>       = 3 + 0 + 0 − 0 − 8 + 18
>       = 13
> ``

**n×n (Desarrollo por cofactores / Laplace):**
``
det(A) = Σⱼ aᵢⱼ·Cᵢⱼ   (desarrollo por fila i, o por columna j)
``

Donde:
- **Menor complementario** Mᵢⱼ = determinante de la submatriz que queda al eliminar fila i, columna j
- **Cofactor** Cᵢⱼ = (−1)ⁱ⁺ʲ · Mᵢⱼ

> [!TIP] Elegí la fila o columna con más ceros para minimizar cuentas. Si no hay ceros, podés crear ceros usando operaciones elementales (que no cambien el det o lo alteren de forma conocida).

> [!EXAMPLE] **Ejemplo 3: Determinante 4×4 por Laplace**
>
> `Sea A = [[2,  1,  0, −1],`
> `        [0,  3,  1,  0],`
> `        [0,  0, −2,  1],`
> `        [0,  0,  0,  4]]`
>
> Por ser triangular superior: det(A) = 2·3·(−2)·4 = −48
>
> (Para matrices triangulares, el determinante es el producto de la diagonal principal.)

### Propiedades de los determinantes

| Propiedad | Significado | Ejemplo |
|-----------|-------------|---------|
| det(Aᵀ) = det(A) | Igual por filas o columnas | |
| det(A·B) = det(A)·det(B) | | |
| Si una fila/columna es 0 → det = 0 | Matriz singular | |
| Si dos filas/columnas iguales → det = 0 | | |
| Intercambiar filas → det cambia de signo | | |
| Multiplicar una fila por k → det × k | | |
| Sumar múltiplo de una fila a otra → det no cambia | Operación elemental clave | |
| det(c·A) = cⁿ·det(A) | **Importante:** es cⁿ, no c·det(A) | n = 3: det(2A) = 8·det(A) |
| det(A⁻¹) = 1/det(A) | | |
| Filas/columnas LD → det = 0 | | |
| det(A·B) = det(A)·det(B) | | det(P⁻¹AP) = det(A) (similitud) |

> [!WARNING] Errores frecuentes con determinantes:
> - ❌ det(A + B) ≠ det(A) + det(B) (el determinante **no** es lineal en suma)
> - ❌ det(c·A) ≠ c·det(A) (es cⁿ·det(A), con n = dimensión)
> - ❌ det(Aᴮ) no existe. Solo potencias: det(Aᵏ) = [det(A)]ᵏ
> - ❌ Olvidar el cambio de signo al intercambiar filas

---

## 4. Matriz inversa

**Definición:** A·A⁻¹ = A⁻¹·A = I (solo para matrices cuadradas con det(A) ≠ 0).

Una matriz con det(A) = 0 se llama **singular** (no invertible).

### Métodos de cálculo

**2×2 (fórmula directa):**
``
A = [a  b]  →  A⁻¹ = (1/det(A)) · [d  −b]
    [c  d]                      [−c  a ]
``

**Por matriz adjunta (cofactores):**
``
A⁻¹ = (1/det(A)) · adj(A)
adj(A) = [Cⱼᵢ]ᵀ    (matriz de cofactores traspuesta = matriz adjunta)
``

**Por operaciones elementales (Gauss-Jordan):**
``
[A | I]  ∼  [I | A⁻¹]
``

Se aplican las mismas operaciones elementales a A y a I hasta que A se convierte en I. Lo que queda del lado derecho es A⁻¹.

> [!EXAMPLE] **Ejemplo 4: Inversa 3×3 por Gauss-Jordan**
>
> `A = [[1,  2,  0],`
> `     [0, −1,  1],`
> `     [2,  0,  1]]`
>
> **Paso 1:** [A | I]
> ``
> [1  2  0 | 1  0  0]
> [0 −1  1 | 0  1  0]
> [2  0  1 | 0  0  1]
> ``
>
> **Paso 2:** F₃ ← F₃ − 2·F₁
> ``
> [1  2  0 |  1  0  0]
> [0 −1  1 |  0  1  0]
> [0 −4  1 | −2  0  1]
> ``
>
> **Paso 3:** F₃ ← F₃ − 4·F₂
> ``
> [1  2  0 |  1  0  0]
> [0 −1  1 |  0  1  0]
> [0  0 −3 | −2 −4  1]
> ``
>
> **Paso 4:** Normalizar filas (F₂ ← −F₂, F₃ ← −F₃/3) y eliminar hacia arriba:
> Resultado:
> ``
> [1  0  0 | −1/3  −2/3   2/3]
> [0  1  0 |  2/3   1/3  −1/3]
> [0  0  1 |  2/3   4/3  −1/3]
> ``
>
> **Verificación:** A·A⁻¹ = I ✓

> [!WARNING] Inversa existe solo si det(A) ≠ 0. Si det(A) = 0 → matriz singular (no invertible). En ese caso el sistema A·x = b no tiene solución única.

---

## 5. Aplicaciones en ingeniería

| Área | Aplicación |
|------|-----------|
| **Estructuras** | Matriz de rigidez K·u = f (método de elementos finitos) |
| **Circuitos** | Análisis nodal: G·v = i (matriz de conductancias) |
| **Computación gráfica** | Matrices de transformación (rotación, escala, traslación en 3D) |
| **Mecánica** | Tensor de inercia, momentos de segundo orden |
| **Control** | Ecuaciones de estado: dx/dt = A·x + B·u |
| **Métodos numéricos** | Factorización LU, QR, SVD (descomposición en valores singulares) |

> [!TIP] La mayoría de los problemas en ingeniería se reducen a resolver A·x = b. Por eso matrices y determinantes son el **alfabeto** del álgebra lineal. Si no dominás este tema, [[Alg_Sistemas_Ecuaciones]] y todo lo que sigue se te va a complicar.

### Conexiones con otras materias
- [[Alg_Sistemas_Ecuaciones]]: resolución de A·x = b con matrices y determinantes
- [[Alg_Espacios_Vectoriales]]: las matrices son transformaciones lineales entre espacios
- [[Anm_Ecuaciones_Diferenciales]]: sistemas de EDO lineales dx/dt = A·x
- [[Eje_Fisica]]: matrices de rotación, tensores, momento de inercia

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---------|-----------|
| `Raw/material y ejercicios (profes)/AyG1/AyG I - Unidad 2.pdf` | Apunte: Matrices (teoría completa) |
| `Raw/material y ejercicios (profes)/AyG1/AyG I - Unidad 3.pdf` | Apunte: Determinantes (teoría completa) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Matrices y Determinantes.pdf` | Alfonso: matrices y determinantes |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/Propiedades Determinantes - RESUMEN.pdf` | Alfonso: resumen propiedades determinantes |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/Unidad 2.pdf` | Curapil: Unidad 2 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Matrices.pdf` | Vannicola: matrices |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Determinante.pdf` | Vannicola: determinante |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Matriz inversa.pdf` | Vannicola: matriz inversa |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/U 2 - Matrices - 37 a 64.pdf` | Teoría extendida (cuadernillo) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 5- Matrices- FAIN 1°C 2025.pdf` | Diapo: Matrices |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 6-Ecuaciones_Matriciales -FAIN 1°C 2025.pdf` | Diapo: Ecuaciones matriciales |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 7-Determinante-FAIN 1°C 2025.pdf` | Diapo: Determinante |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 8a-Determinantes y Matriz Inversa por Adjunta-FAIN 1°C 2025.pdf` | Diapo: Matriz inversa por adjunta |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 8b-Matriz inversa por OE-FAIN 1°C 2025.pdf` | Diapo: Matriz inversa por OE |

## 📝 Ejercicios

### TP oficial
- [[Raw/material y ejercicios (profes)/AyG1/TP N° 2 Matrices y determinantes 2025.pdf|TP N° 2 Matrices y determinantes 2025]]

### TPs con resoluciones
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/AYGI - tp2 matrices y determinantes.pdf|AyGI TP2 matrices y determinantes]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Respuesta TPN°2-Matrices y determinantes 2024.pdf|Respuestas TP2 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N° 2 Matrices y Determinantes 1°C 2024.pdf|TP2 1°C 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TPN°2 Matrices (1).pdf|TPN°2 Matrices]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/parciales/Ejercicios 1° parcial-Reales-Matrices-SEL.pdf|Ejercicios 1er parcial: Reales-Matrices-SEL]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 2_Matrices_y_Determinantes_Algebra_y_geometria_i_2025__Copy_ (3).pdf|TP2 prácticas]]

### Ejercicios modelados

1. **Multiplicación 3×3:** Dadas A = `[[1, 0, 2], [−1, 3, 1], [0, 1, −2]]` y B = `[[2, 1, 0], [0, −1, 3], [1, 0, 1]]`, calcular A·B y B·A. ¿Son iguales?
   > *Guía:* Usá la fórmula cᵢⱼ = Σₖ aᵢₖ·bₖⱼ. Compará los resultados. Si son distintos (y seguro lo son), tenés un ejemplo de que A·B ≠ B·A.

2. **Determinante 3×3 por Sarrus:** Calcular det(A) para A = `[[2, 1, −1], [0, 3, 2], [4, −2, 1]]` usando la regla de Sarrus. Verificar desarrollando por la primera fila con cofactores.
   > *Guía:* Primero aplicá Sarrus (sumar diagonales ↘, restar diagonales ↗). Luego desarrollá por fila 1: det = 2·det`[[3,2],[−2,1]]` − 1·det`[[0,2],[4,1]]` + (−1)·det`[[0,3],[4,−2]]`.

3. **Inversa por adjunta:** Hallar la inversa de A = `[[3, 1], [2, 4]]` usando la fórmula 2×2. Verificar que A·A⁻¹ = I.
   > *Guía:* det(A) = 3·4 − 1·2 = 10. A⁻¹ = (1/10)·`[[4, −1], [−2, 3]]`.

4. **Propiedades combinadas:** Si A es 4×4 con det(A) = 2, calcular:
   a) det(3A)    b) det(A⁻¹)    c) det(A³)    d) det(Aᵀ·A)    e) det(P⁻¹AP) para P invertible
   > *Guía:* a) 3⁴·2 = 81·2 = 162   b) 1/2   c) 8   d) det(Aᵀ)·det(A) = 2·2 = 4   e) det(P⁻¹AP) = det(A) = 2 (invariante por similitud)

5. **Sistema matricial:** Resolver A·X = B, donde A = `[[2, 1], [5, 3]]` y B = `[[1, 0], [0, 1]]`.
   *Sugerencia:* acá X resulta ser A⁻¹. Resolvé usando el método de Gauss-Jordan.

---

## 📚 Referencias

- **Abad** "Elementos de Álgebra" → [[Raw/material y ejercicios (profes)/AyG1/Manuel_Abad_-_Elementos_de_Algebra.pdf|PDF]]
- **Larson** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf|PDF]]
- **Anton** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/6.- Álgebra Lineal (MathRocks) - Anton.pdf|PDF]]
- **Lipschutz Schaum** → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/7.- Álgebra Lineal (MathRocks) - Lipschutz Schaum.pdf|PDF]]

> [!WARNING] Este tema es **fundamental** para todo lo que viene. Sin matrices no podés resolver SEL, ni vectores, ni espacios vectoriales. Asegurate de practicar bien las operaciones y el cálculo de determinantes. Es el filtro de álgebra lineal — dominá esto y el resto viene solo.
