> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Numeros_Complejos]] ← Anterior • Siguiente: [[Alg_Espacios_Vectoriales]]

# Polinomios

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Numeros_Complejos]] (tema anterior)**
> **→ [[Alg_Espacios_Vectoriales]] (siguiente tema)**

También: [[Eje_Analisis_Matematico]]

---

## 1. Definición

Un **polinomio** es una expresión de la forma:

`P(x) = aₙ·xⁿ + aₙ₋₁·xⁿ⁻¹ + ... + a₁·x + a₀`

| Elemento | Significado |
|---|---|
| aₙ, …, a₀ ∈ ℝ (o ℂ) | Coeficientes |
| n | Grado (si aₙ ≠ 0) |
| aₙ | Coeficiente principal |
| a₀ | Término independiente |
| aₙ = 1 | Polinomio mónico |

**Ejemplos:**
- P(x) = 3x⁴ - 2x² + 5x - 1 → grado 4, coeficiente principal 3
- Q(x) = x² + 3x + 2 → mónico, grado 2

**Notación:** ℙₙ = {polinomios de grado ≤ n}. ℙₙ es un espacio vectorial de dimensión n+1 (ver [[Alg_Espacios_Vectoriales]]).

> [!WARNING] Grado del polinomio nulo
> El polinomio nulo P(x) = 0 no tiene grado definido. Algunos autores le asignan grado -∞. No confundir con el polinomio constante P(x) = c, que tiene grado 0 (si c ≠ 0).

---

## 2. Operaciones

| Operación | Cómo se hace | Ejemplo |
|---|---|---|
| **Suma/resta** | se suman/restan coeficientes del mismo grado | (2x² + x) + (x² - 3x) = 3x² - 2x |
| **Multiplicación** | se distribuye término a término | (x+1)(x-2) = x² - x - 2 |
| **División** | algoritmo de división: P(x) / Q(x) = C(x) + R(x)/Q(x) | |
| **Regla de Ruffini** | división rápida cuando Q(x) = x - a | |
| **Teorema del resto** | el resto de P/(x-a) es P(a) | |

> [!EXAMPLE] Regla de Ruffini
> Dividir P(x) = 2x³ - 5x² + 7x - 3 por x - 2.
>
> **Solución:**
> ```
> Coeficientes: 2  -5   7  -3
> Raíz a = 2:   2  -5   7  -3
>               ↓   4  -2  10
>              ───────────────
>               2  -1   5   7
> ```
> C(x) = 2x² - x + 5, resto = 7
>
> **Verificación (Teorema del resto):** P(2) = 2·8 - 5·4 + 7·2 - 3 = 16 - 20 + 14 - 3 = 7 ✓

> [!TIP] Ruffini vs división larga
> Ruffini solo funciona para divisores de la forma (x - a). Para divisores de grado mayor (ej: x² + 1) hay que usar división larga de polinomios.

---

## 3. Raíces de un polinomio

**Raíz:** a es raíz de P(x) si P(a) = 0.

**Propiedades fundamentales:**

| Propiedad | Enunciado |
|---|---|
| **Teorema del factor** | Si a es raíz → (x - a) divide a P(x) |
| **Teorema Fundamental del Álgebra** | Todo polinomio de grado n ≥ 1 tiene exactamente n raíces en ℂ |
| **Raíces complejas** | Si coeficientes son reales, las raíces complejas aparecen en pares conjugados |
| **Factorización** | P(x) = aₙ·(x - r₁)·(x - r₂)·…·(x - rₙ) |
| **Raíces enteras** | Si aₙ = 1, las raíces enteras posibles son divisores de a₀ |

### Relaciones de Cardano-Vieta

Para P(x) = xⁿ - S₁·xⁿ⁻¹ + S₂·xⁿ⁻² - … ± Sₙ:

| Símbolo | Significado | Para grado 2 |
|---|---|---|
| S₁ | Suma de raíces | x² - S₁x + S₂ = 0 |
| S₂ | Suma de productos de a pares | S₁ = r₁ + r₂ |
| Sₙ | Producto de todas las raíces | S₂ = r₁·r₂ |

> [!EXAMPLE] Cardano-Vieta
> Las raíces de x² - 5x + 6 = 0 son r₁ = 2, r₂ = 3.
> S₁ = 2 + 3 = 5 ✓ ; S₂ = 2·3 = 6 ✓
>
> Para el cúbico x³ - 6x² + 11x - 6 = 0:
> S₁ = 1 + 2 + 3 = 6 ✓ ; S₂ = 1·2 + 1·3 + 2·3 = 11 ✓ ; S₃ = 1·2·3 = 6 ✓

> [!WARNING] Cardano-Vieta
> Las relaciones de Cardano-Vieta valen para polinomios **mónicos**. Si el polinomio no es mónico, hay que dividir todo por el coeficiente principal primero. Ej: 2x² - 8x + 6 = 0 → dividido por 2 → x² - 4x + 3 = 0 → raíces 1 y 3.

---

## 4. Factorización

**Métodos de factorización:**

1. **Factor común:** extraer el término que se repite
   - Ej: 6x³ + 3x² = 3x²(2x + 1)

2. **Diferencia de cuadrados:** a² - b² = (a+b)(a-b)
   - Ej: x² - 9 = (x+3)(x-3)

3. **Trinomio cuadrado perfecto:** a² ± 2ab + b² = (a ± b)²
   - Ej: x² + 6x + 9 = (x+3)²

4. **Ruffini:** buscar raíces enteras/racionales
   - Probar divisores del término independiente

5. **Teorema de Gauss (raíces racionales):** las raíces racionales posibles son de la forma ±(divisor de a₀)/(divisor de aₙ)

> [!EXAMPLE] Factorización completa
> Factorizar P(x) = x⁴ - 5x² + 4.
>
> **Solución:**
> 1. Sustitución: t = x² → t² - 5t + 4 = 0
> 2. t = (5 ± √(25 - 16))/2 = (5 ± 3)/2 → t₁ = 4, t₂ = 1
> 3. x² = 4 → x = ±2 ; x² = 1 → x = ±1
> 4. Factorización: P(x) = (x - 2)(x + 2)(x - 1)(x + 1)
> 5. **Verificación:** (x-2)(x+2)(x-1)(x+1) = (x²-4)(x²-1) = x⁴ - 5x² + 4 ✓

---

## 5. Teorema Fundamental del Álgebra

**Todo polinomio de grado n ≥ 1 con coeficientes complejos tiene al menos una raíz compleja.**
→ Por lo tanto, todo polinomio de grado n tiene exactamente n raíces en ℂ.

### Consecuencias
- Todo polinomio real factoriza como producto de factores lineales y cuadráticos irreducibles
- Las raíces complejas de polinomios reales vienen en pares conjugados
- Un polinomio de grado impar con coeficientes reales tiene al menos una raíz real

> [!EXAMPLE] Polinomio de grado impar
> Demostrar que P(x) = x⁵ + x - 1 tiene al menos una raíz real.
>
> **Solución:**
> 1. P es continuo (es polinómico).
> 2. P(0) = -1 < 0 ; P(1) = 1 + 1 - 1 = 1 > 0
> 3. Por el Teorema de Bolzano ([[Eje_Analisis_Matematico]]), existe c ∈ (0,1) tal que P(c) = 0.
> 4. También se deduce del Teorema Fundamental del Álgebra: grado impar → al menos 1 raíz real.

---

## 6. Máximo común divisor y mínimo común múltiplo

**MCD:** polinomio de mayor grado que divide a ambos.
**MCM:** polinomio de menor grado que es múltiplo de ambos.

Se calculan igual que con números: factorización o algoritmo de Euclides.

> [!EXAMPLE] MCD y MCM de polinomios
> Hallar MCD y MCM de P(x) = x² - 1 y Q(x) = x² + 2x + 1.
>
> **Solución:**
> 1. Factorizamos: P(x) = (x-1)(x+1), Q(x) = (x+1)²
> 2. MCD = (x+1) (factores comunes con menor exponente)
> 3. MCM = (x-1)(x+1)² (factores comunes y no comunes con mayor exponente)

---

## 🔧 Aplicaciones de ingeniería

| Concepto | Aplicación |
|---|---|
| **Raíces de polinomios** | Frecuencias naturales de vibración, polos de sistemas de control |
| **Factorización** | Descomposición en fracciones simples (para transformada de Laplace) |
| **Cardano-Vieta** | Diseño de filtros, relaciones entre parámetros de circuitos |
| **Interpolación polinómica** | Aproximación de funciones en métodos numéricos |
| **Polinomios de Taylor** | Aproximación local de funciones ([[Eje_Analisis_Matematico]]) |
| **Polinomios característicos** | Valores propios en [[Alg_Espacios_Vectoriales]] y [[Alg_Matrices_Determinantes]] |

> [!TIP] Polinomios y matrices
> El polinomio característico de una matriz A es det(A - λI). Sus raíces son los **autovalores** de la matriz, fundamentales en diagonalización y sistemas de ecuaciones diferenciales. Esto lo vas a ver en [[Alg_Espacios_Vectoriales]] y en Análisis II.

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U3 polinomios.pdf` | Apunte Ariela: polinomios |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/polinomios.pdf` | Apunte Muñoz: polinomios |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U3 polinomios - ejercicios.pdf` | Ejercicios Ariela: polinomios |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 7-Polinomios-contenidos-FAIN-1°C 2025.pdf` | Diapo: polinomios contenidos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 8-Polinomios-factorizacion-FAIN-1°C 2025.pdf` | Diapo: factorización |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 9-Polinomios-Relaciones Cardano-Vieta-FAIN-1°C 2025.pdf` | Diapo: Cardano-Vieta |

## 📝 Ejercicios

### TPs
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP3 Polinomios.pdf|TP3 Polinomios (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°3 Polinomios.pdf|TP N°3 Polinomios]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Ariela Garcés/TP 3.pdf|TP3 Polinomios (Ariela)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica polinomios _230904_171355.pdf|Práctica: polinomios]]

---

## 🧪 Ejercicios modelados

> [!EXAMPLE] Ejercicio 1 — Ruffini y factorización
> Factorizar completamente P(x) = x³ - 3x² - 4x + 12.
>
> **Guía:**
> 1. Probá divisores de 12: ±1, ±2, ±3, ±4, ±6, ±12.
> 2. P(2) = 8 - 12 - 8 + 12 = 0 → x = 2 es raíz.
> 3. Aplicá Ruffini con a = 2.
> 4. Resulta C(x) = x² - x - 6.
> 5. Factorizá el cuadrático: x² - x - 6 = (x - 3)(x + 2).
> 6. P(x) = (x - 2)(x - 3)(x + 2).

> [!EXAMPLE] Ejercicio 2 — Cardano-Vieta
> Sabiendo que las raíces de x³ + ax² + bx + c = 0 son r₁ = 1, r₂ = -2, r₃ = 3, hallar a, b, c.
>
> **Guía:**
> 1. Usá Cardano-Vieta para polinomio mónico:
>    S₁ = r₁ + r₂ + r₃ = -a
>    S₂ = r₁·r₂ + r₁·r₃ + r₂·r₃ = b
>    S₃ = r₁·r₂·r₃ = -c
> 2. Reemplazá los valores y despejá a, b, c.

> [!EXAMPLE] Ejercicio 3 — Raíces complejas
> Sabiendo que P(x) = x⁴ - 2x³ + 4x² - 2x + 3 tiene raíces i y -i, hallar las otras dos raíces y factorizar.
>
> **Guía:**
> 1. Si i y -i son raíces, (x - i)(x + i) = x² + 1 divide a P(x).
> 2. Dividí P(x) por x² + 1 (división larga).
> 3. El cociente es un polinomio de grado 2 → resolvelo con fórmula resolvente.
> 4. Factorizá completo.

> [!EXAMPLE] Ejercicio 4 — Aplicación: polinomio interpolador
> Hallar el polinomio de grado ≤ 2 que pasa por (-1, 2), (0, -1), (1, 4).
>
> **Guía:**
> 1. Sea P(x) = ax² + bx + c.
> 2. Reemplazá cada punto para obtener 3 ecuaciones:
>    P(-1) = a - b + c = 2
>    P(0) = c = -1
>    P(1) = a + b + c = 4
> 3. Resolvé el sistema lineal para a, b, c.
> 4. Verificá que P(x) pase por los tres puntos.

> [!EXAMPLE] Ejercicio 5 — Raíces y multiplicidad
> Determinar las raíces y su multiplicidad de P(x) = (x - 2)²(x + 1)(x - 3)².
> Construir un polinomio de grado 5 que tenga estas raíces.
>
> **Guía:**
> 1. Las raíces son: x = 2 (mult. 2), x = -1 (mult. 1), x = 3 (mult. 2).
> 2. El polinomio ya está factorizado; solo hay que expandirlo (opcional).
> 3. Para construir otro polinomio con las mismas raíces, multiplicá por cualquier constante no nula.
> 4. Verificá que la suma de las multiplicidades = grado del polinomio.

---

## 📚 Referencias

- **Grossman** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf|PDF]]
- **Kolman** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Algebra Lineal - Kolman.pdf|PDF]]

> [!NOTE] Los polinomios son el tema puente entre números complejos y espacios vectoriales. Usan complejos para sus raíces y son el ejemplo clásico de espacio vectorial (ℙₙ).
