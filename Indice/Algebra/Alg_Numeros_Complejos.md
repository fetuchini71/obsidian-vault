> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Conicas_Cuadricas]] ← Anterior • Siguiente: [[Alg_Polinomios]]

# Números Complejos

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Conicas_Cuadricas]] (tema anterior)**
> **→ [[Alg_Polinomios]] (siguiente tema)**

También: [[Eje_Analisis_Matematico]] | [[Eje_Fisica]]

---

## 1. Definición

Los **números complejos** ℂ surgen como extensión de ℝ para resolver ecuaciones como x² + 1 = 0.

**Unidad imaginaria:** i = √(-1) → i² = -1

**Forma binómica:** `z = a + bi`
- a = Re(z) = parte real
- b = Im(z) = parte imaginaria

**Conjugado:** `z̅ = a - bi`

**Opuesto:** `-z = -a - bi`

> [!WARNING] i vs j
> En matemática se usa i (imaginario). En ingeniería eléctrica se usa j para no confundir con la corriente i. En esta materia usamos i. ¡No confundir!

---

## 2. Representaciones

### Plano complejo (Argand-Gauss)
- Eje x → parte real
- Eje y → parte imaginaria
- Cada complejo z = a + bi es un punto (a, b)

**Diagrama del plano complejo:**
```
      Im(z)
        ↑
     3  ┊   z = 3 + 2i
     2  ┊   ·  r = √13
     1  ┊ ↗ │θ
        ┊·──┼──→ Re(z)
       -1  0  1  2  3
      -1  ┊
          ┊   z̅ = 3 - 2i
      -2  ┊   ·
```

### Módulo
`|z| = √(a² + b²)` (distancia al origen)

### Argumento
`arg(z) = θ = arctan(b/a)` (ángulo con el eje real positivo)
- Valor principal: θ ∈ (-π, π] o [0, 2π)

### Forma polar (trigonométrica)
`z = r·(cos θ + i·sen θ)` donde r = |z|

### Forma exponencial (Euler)
`z = r·e^(iθ)`
donde e^(iθ) = cos θ + i·sen θ

> [!TIP] Fórmula de Euler
> e^(iπ) + 1 = 0 — la identidad más bella de las matemáticas, conectando los 5 números fundamentales (e, π, i, 1, 0). También: e^(iθ) = cos θ + i·sen θ, que permite escribir sen y cos como:
> cos θ = (e^(iθ) + e^(-iθ))/2
> sen θ = (e^(iθ) - e^(-iθ))/(2i)

---

## 3. Operaciones en forma binómica

| Operación | Fórmula | Ejemplo |
|---|---|---|
| Suma | (a+bi) + (c+di) = (a+c) + (b+d)i | (2+3i)+(1-2i) = 3+ i |
| Resta | (a+bi) - (c+di) = (a-c) + (b-d)i | (2+3i)-(1-2i) = 1+5i |
| Multiplicación | (a+bi)·(c+di) = (ac-bd) + (ad+bc)i | (2+3i)(1-2i) = 2-4i+3i-6i² = 8- i |
| División | (a+bi)/(c+di) = [(a+bi)·(c-di)]/(c²+d²) | |
| Potencia | Se usa De Moivre (forma polar) | |

**Propiedades del conjugado:**

| Propiedad | Fórmula |
|---|---|
| Suma con conjugado | z + z̅ = 2·Re(z) |
| Producto con conjugado | z · z̅ = \|z\|² |
| Conjugado de suma | (z₁ + z₂)̅ = z̅₁ + z̅₂ |
| Conjugado de producto | (z₁·z₂)̅ = z̅₁ · z̅₂ |
| Conjugado de cociente | (z₁/z₂)̅ = z̅₁ / z̅₂ |

> [!EXAMPLE] Operaciones en forma binómica
> Dados z = 2 + 3i y w = 1 - i, calcular z + w, z·w y z/w.
>
> **Solución:**
> 1. z + w = (2+1) + (3-1)i = 3 + 2i
> 2. z·w = (2·1 - 3·(-1)) + (2·(-1) + 3·1)i = (2+3) + (-2+3)i = 5 + i
> 3. z/w = (2+3i)/(1-i) = (2+3i)(1+i)/((1-i)(1+i)) = (2+2i+3i+3i²)/(1-i²)
>       = (2+5i-3)/(1+1) = (-1+5i)/2 = -1/2 + (5/2)i
>
> **Verificación:** z/w · w = (-1/2 + 5i/2)(1-i) = (-1/2+5i/2) + (1/2-5i/2)i... = 2+3i = z ✓

> [!WARNING] División de complejos
> Para dividir, **siempre** multiplicar numerador y denominador por el conjugado del denominador. Esto transforma el denominador en un número real. ¡No intentar dividir componente a componente!

---

## 4. Operaciones en forma polar/exponencial

| Operación | Fórmula |
|---|---|
| Multiplicación | r₁·e^(iθ₁) · r₂·e^(iθ₂) = r₁·r₂·e^(i(θ₁+θ₂)) |
| División | r₁·e^(iθ₁) / r₂·e^(iθ₂) = (r₁/r₂)·e^(i(θ₁-θ₂)) |
| Potencia (De Moivre) | (cos θ + i·sen θ)ⁿ = cos(nθ) + i·sen(nθ) |
| Potencia general | zⁿ = rⁿ·e^(i·n·θ) = rⁿ·(cos nθ + i·sen nθ) |

> [!EXAMPLE] Potencia con De Moivre
> Calcular (1 + i)⁸.
>
> **Solución:**
> 1. Pasamos a forma polar: |z| = √(1²+1²) = √2, θ = arctan(1/1) = π/4
> 2. z = √2·e^(iπ/4)
> 3. z⁸ = (√2)⁸·e^(i·8·π/4) = 2⁴·e^(i·2π) = 16·(cos 2π + i·sen 2π) = 16·(1 + 0) = 16
>
> **Verificación:** (1+i)² = 2i ; (1+i)⁴ = (2i)² = -4 ; (1+i)⁸ = (-4)² = 16 ✓

---

## 5. Raíces de números complejos

Para encontrar las n raíces de z^(1/n):

`wₖ = r^(1/n) · [cos((θ + 2πk)/n) + i·sen((θ + 2πk)/n)]`

para k = 0, 1, 2, ..., n-1

Las n raíces forman un **polígono regular** de n lados en el plano complejo.

**Diagrama — raíces cúbicas de la unidad:**
```
      Im(z)
        ↑
        │   w₁
     ───┼───●─── Re(z)
        │ ╱   ╲
      w₀●     ●w₂
```

> [!EXAMPLE] Raíces de un número complejo
> Hallar las raíces cúbicas de z = -8.
>
> **Solución:**
> 1. Forma polar: |-8| = 8, θ = π (está en el eje real negativo)
> 2. z = 8·e^(iπ)
> 3. Raíces: wₖ = 8^(1/3)·e^(i(π + 2πk)/3) = 2·e^(i(π/3 + 2πk/3))
> 4. k = 0: w₀ = 2·e^(iπ/3) = 2(cos 60° + i·sen 60°) = 1 + √3·i
> 5. k = 1: w₁ = 2·e^(iπ) = -2 + 0i = -2
> 6. k = 2: w₂ = 2·e^(i5π/3) = 2(cos 300° + i·sen 300°) = 1 - √3·i
>
> **Verificación:** (-2)³ = -8 ✓ ; (1+√3i)³ = 1+3√3i-9-3√3i = -8 ✓

> [!TIP] Las raíces n-ésimas
> Siempre forman un polígono regular de n lados inscrito en una circunferencia de radio r^(1/n). Para las raíces de la unidad (z = 1), el polígono está centrado en el origen con radio 1 y un vértice en z = 1.

---

## 6. Aplicaciones

| Área | Aplicación |
|---|---|
| **Ecuaciones polinómicas** | Todo polinomio de grado n tiene n raíces complejas (Teorema Fundamental del Álgebra) |
| **Circuitos de corriente alterna** | Impedancia Z = R + jX, fasores |
| **Mecánica cuántica** | Función de onda ψ, ecuación de Schrödinger |
| **Análisis de Fourier** | Transformada de Fourier, frecuencias complejas |
| **Control automático** | Polos y ceros en el plano s (Laplace) |
| **Geometría fractal** | Conjunto de Mandelbrot: z_{n+1} = z_n² + c |

> [!WARNING] Complejos en circuitos AC
> En ingeniería eléctrica, la unidad imaginaria se escribe j (no i) para evitar confusión con la corriente. ¡Acordate de este detalle cuando curses Electrotecnia!

**Conexiones con otras notas:**
- [[Alg_Polinomios]]: las raíces complejas aparecen en pares conjugados
- [[Eje_Analisis_Matematico]]: variable compleja, integrales de contorno, series de Laurent
- [[Eje_Fisica]]: oscilaciones amortiguadas, ondas electromagnéticas

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U2 numeros complejos.pdf` | Apunte Ariela: números complejos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/numeros complejos.pdf` | Apunte Muñoz: números complejos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 11-Complejos-introducción-FAIN-1°C 2025.pdf` | Diapo: introducción a complejos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 12-Complejos-Operaciones-FAIN-1°C 2025.pdf` | Diapo: operaciones con complejos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 13-Complejos-Potencia de binomio-FAIN-1°C 2025.pdf` | Diapo: potencia de binomio |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 14-Complejos-Raices-FAIN-1°C 2025.pdf` | Diapo: raíces de complejos |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/teoria/diapositivas/Clase 15-Complejos-Ecuaciones-FAIN-1°C 2025.pdf` | Diapo: ecuaciones con complejos |

## 📝 Ejercicios

### TPs
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP2 complejos.pdf|TP2 Complejos (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°2 Complejos.pdf|TP N°2 Complejos]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Ariela Garcés/TP 2.pdf|TP2 Complejos (Ariela)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica números complejos_230823_200244.pdf|Práctica: números complejos]]

---

## 🧪 Ejercicios modelados

> [!EXAMPLE] Ejercicio 1 — Forma binómica y operaciones
> Dados z = 3 - 2i y w = -1 + 4i, calcular:
> a) z + w   b) z - w   c) z·w   d) z/w   e) |z|   f) z̅
>
> **Guía:**
> 1. a-b) Sumá/restá partes real e imaginaria por separado.
> 2. c) Multiplicá como binomios, recordando i² = -1.
> 3. d) Multiplicá numerador y denominador por el conjugado del denominador.
> 4. e) |z| = √(a² + b²).
> 5. f) z̅ = a - bi.

> [!EXAMPLE] Ejercicio 2 — Forma polar y exponencial
> Expresar z = -1 + √3·i en forma polar y exponencial. Luego calcular z⁶.
>
> **Guía:**
> 1. r = √((-1)² + (√3)²) = √(1 + 3) = 2.
> 2. θ = arctan(√3/(-1)). Como Re < 0, Im > 0 → θ ∈ (π/2, π).
> 3. tan θ = -√3 → θ = 2π/3.
> 4. Polar: z = 2(cos 120° + i·sen 120°).
> 5. Exponencial: z = 2·e^(i·2π/3).
> 6. z⁶ = 2⁶·e^(i·6·2π/3) = 64·e^(i·4π) = 64.

> [!EXAMPLE] Ejercicio 3 — Raíces n-ésimas
> Hallar las raíces cuartas de z = 16.
>
> **Guía:**
> 1. Expresá 16 en forma polar: r = 16, θ = 0.
> 2. Usá la fórmula wₖ = r^(1/4)·e^(i(θ + 2πk)/4), k = 0, 1, 2, 3.
> 3. r^(1/4) = 2.
> 4. Calculá cada raíz:
>    k=0: w₀ = 2·e^(i·0) = 2
>    k=1: w₁ = 2·e^(iπ/2) = 2i
>    k=2: w₂ = 2·e^(iπ) = -2
>    k=3: w₃ = 2·e^(i·3π/2) = -2i
> 5. Verificá: (2)⁴ = 16, (2i)⁴ = 16, (-2)⁴ = 16, (-2i)⁴ = 16.

> [!EXAMPLE] Ejercicio 4 — Ecuación polinómica
> Resolver x² - 2x + 5 = 0 en ℂ.
>
> **Guía:**
> 1. Discriminante: Δ = (-2)² - 4·1·5 = 4 - 20 = -16.
> 2. Δ < 0 → dos raíces complejas conjugadas.
> 3. Usá la fórmula resolvente: x = [2 ± √(-16)]/2 = [2 ± 4i]/2.
> 4. x₁ = 1 + 2i, x₂ = 1 - 2i.
> 5. Verificá: (1+2i)² - 2(1+2i) + 5 = 1+4i-4-2-4i+5 = 0 ✓

> [!EXAMPLE] Ejercicio 5 — Aplicación: fasores
> Un circuito de CA tiene voltaje V = 220·e^(i·30°) V y corriente I = 5·e^(-i·20°) A. Hallar:
> a) La impedancia Z = V/I.
> b) La potencia aparente S = V·I*.
>
> **Guía:**
> 1. Z = V/I = (220/5)·e^(i(30° - (-20°))) = 44·e^(i·50°) Ω.
> 2. I* es el conjugado de I: I* = 5·e^(i·20°).
> 3. S = V·I* = 220·5·e^(i(30°+20°)) = 1100·e^(i·50°) VA.
> 4. La potencia activa es Re(S) y la reactiva es Im(S).

---

## 📚 Referencias

- **Álgebra Lineal - Grossman** → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf|PDF]]
- **Álgebra Lineal - Kolman** → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Algebra Lineal - Kolman.pdf|PDF]]
- **Churchill** "Variable Compleja" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Variable Compleja - Churchill.pdf|PDF]]

> [!WARNING] Los números complejos no son "imaginarios" en el sentido de irreales. Son tan reales como los reales —solo que viven en un plano en vez de una recta. Son indispensables para entender polinomios, circuitos AC, control, ondas y mecánica cuántica.
