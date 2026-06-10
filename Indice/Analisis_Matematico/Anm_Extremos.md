> [!NOTE] Navegación
> **Anterior:** [[Anm_Derivadas_Parciales]] • **Siguiente:** [[Anm_Integrales_Multiples]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Extremos de Funciones de Varias Variables

## Índice

==toc==

---

> [!INFO]
> Optimizar en ℝⁿ: encontrar máximos y mínimos de funciones de 2+ variables. Esto aparece en todas las ingenierías — minimizar costos, maximizar eficiencia, ajustar modelos. En mecánica: encontrar la configuración de equilibrio de un sistema, minimizar energía potencial, maximizar rigidez.

---

## Extremos locales

$f$ tiene un **máximo local** en $(a,b)$ si $f(x,y) \leq f(a,b)$ para todos los $(x,y)$ cerca de $(a,b)$.

$f$ tiene un **mínimo local** si $f(x,y) \geq f(a,b)$.

### Punto crítico

$(a,b)$ es punto crítico si $\nabla f(a,b) = \mathbf{0}$ (o alguna derivada parcial no existe).

```
                  Punto crítico
                  ──────────────
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
      ∇f = 0 (estacionario)    ∇f no existe (esquina, pico)
              │
     ┌────────┼────────┐
     ▼        ▼        ▼
  Mínimo   Máximo   Punto silla
  local    local
```

> [!WARNING] Punto crítico ≠ extremo
> **Error común:** encontrar $\nabla f = 0$ y asumir que es un máximo o mínimo. Un punto donde $\nabla f = 0$ puede ser un **punto silla** (como $z = x^2 - y^2$ en $(0,0)$). Siempre hay que aplicar el **criterio de la segunda derivada** para clasificarlo.

---

## Criterio de la segunda derivada (Hessiana)

Matriz Hessiana:

$$H(a,b) = \begin{pmatrix} f_{xx} & f_{xy} \\ f_{yx} & f_{yy} \end{pmatrix}$$

Determinante de la Hessiana: $D(a,b) = f_{xx}f_{yy} - (f_{xy})^2$

| Condición | Tipo de punto |
|-----------|--------------|
| $D > 0$ y $f_{xx} > 0$ | **Mínimo local** |
| $D > 0$ y $f_{xx} < 0$ | **Máximo local** |
| $D < 0$ | **Punto silla** (ni máximo ni mínimo) |
| $D = 0$ | El criterio no decide |

> [!NOTE]
> El punto silla es como el punto de inflexión en 1D — en una dirección es máximo, en otra es mínimo. Ejemplo clásico: $z = x^2 - y^2$ (forma de silla de montar).
>
> ```
>         z
>         ▲
>         │    /\    (dirección y → mínimo)
>         │   /  \
>         │  /    \
>         │ /      \
>         │/________\_______► y
>         │\        /
>         │ \      /
>         │  \    /
>         │   \  /    (dirección x → máximo)
>         │    \/
>         │           ► x
>         Punto silla en (0,0)
> ```

> [!EXAMPLE] Clasificar puntos críticos
> Encontrar y clasificar los extremos de $f(x,y) = x^3 - 3x + y^2$.
>
> **Solución:**
>
> **Paso 1** — Puntos críticos: $\nabla f = (3x^2 - 3, 2y) = (0,0)$
> $3x^2 - 3 = 0 \Rightarrow x = \pm 1$
> $2y = 0 \Rightarrow y = 0$
> Puntos críticos: $(1,0)$ y $(-1,0)$
>
> **Paso 2** — Segundas derivadas:
> $f_{xx} = 6x$, $f_{yy} = 2$, $f_{xy} = 0$
>
> **Paso 3** — Evaluar $D = f_{xx}f_{yy} - (f_{xy})^2 = 12x$
>
> En $(1,0)$: $D = 12 > 0$, $f_{xx} = 6 > 0$ → **Mínimo local**
> $f(1,0) = 1 - 3 + 0 = -2$
>
> En $(-1,0)$: $D = -12 < 0$ → **Punto silla**
> $f(-1,0) = (-1) + 3 + 0 = 2$
>
> **Verificación:** la función es un "valle" en $y$ (término $y^2$) y un polinomio cúbico en $x$.

---

## Multiplicadores de Lagrange

Para optimizar $f(x,y)$ sujeta a una **restricción** $g(x,y) = k$:

$$\nabla f = \lambda \nabla g$$

donde $\lambda$ es el **multiplicador de Lagrange**.

**Pasos:**
1. Resolvés el sistema $\nabla f = \lambda \nabla g$ y $g(x,y) = k$
2. Evaluás $f$ en todos los candidatos
3. El mayor es el máximo, el menor es el mínimo

Para dos restricciones: $\nabla f = \lambda \nabla g + \mu \nabla h$

> [!TIP] Interpretación geométrica
> En el punto óptimo con restricción, las curvas de nivel de $f$ son **tangentes** a la curva de la restricción $g(x,y) = k$. Esto significa que $\nabla f$ y $\nabla g$ son paralelos: $\nabla f = \lambda \nabla g$. El multiplicador $\lambda$ mide cuánto cambia el valor óptimo si la restricción se relaja un poco.

```
        y
        ▲
        │     ┌──────────────┐
        │    ╱                ╲
        │   ╱                  ╲
        │  ╱    ∇f = λ∇g        ╲   ← g(x,y) = k (restricción)
        │ ╱         *             ╲
        │╱      (x₀,y₀)           ╲
        │                          ╲
        │  ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─► x
        │   curvas de nivel f = c
```

> [!EXAMPLE] Multiplicadores de Lagrange
> Maximizar $f(x,y) = xy$ sujeta a $x + y = 10$ (con $x,y > 0$).
>
> **Solución:**
>
> **Paso 1** — Planteamos: $\nabla f = \lambda \nabla g$
> $\nabla f = (y, x)$, $\nabla g = (1, 1)$
> Sistema: $y = \lambda \cdot 1$, $x = \lambda \cdot 1$, $x + y = 10$
>
> **Paso 2** — De $y = \lambda$ y $x = \lambda$ tenemos $x = y$.
> $x + y = 10 \Rightarrow 2x = 10 \Rightarrow x = 5$, $y = 5$
>
> **Paso 3** — $f(5,5) = 25$
>
> ¿Es máximo o mínimo? Probamos puntos factibles cercanos: $(1,9) \to 9$, $(4,6) \to 24$, $(6,4) \to 24$. El máximo es 25 en $(5,5)$.
>
> **Interpretación:** de todos los rectángulos con perímetro 20 (si $x$ e $y$ son los lados), el cuadrado de lado 5 maximiza el área.

> [!WARNING] Casos donde Lagrange falla
> El método de Lagrange requiere que $\nabla g \neq 0$ en el punto óptimo. Si la restricción tiene un "pico" (como $g(x,y) = |x| + |y| = 1$ en $(1,0)$), $\nabla g$ no está definido y hay que analizar aparte. También pueden aparecer puntos donde la solución incluye $\lambda = 0$ (el óptimo está donde $\nabla f = 0$ sin importar la restricción).

---

## Extremos absolutos en regiones cerradas y acotadas

**Teorema de Weierstrass:** toda función continua en una región cerrada y acotada de ℝⁿ alcanza un máximo y un mínimo absolutos.

**Procedimiento:**
1. Encontrar puntos críticos dentro de la región
2. Analizar la frontera (parametrizar y optimizar)
3. Evaluar $f$ en todos los candidatos
4. El mayor es el máximo absoluto, el menor es el mínimo absoluto

| Tipo de región | Cómo analizar la frontera |
|:---------------|:--------------------------|
| **Rectangular** | 4 segmentos de recta, analizar cada uno |
| **Circular** | Parametrizar con $x = a\cos t$, $y = b\sin t$ |
| **Triangular** | 3 segmentos, analizar cada lado |
| **Poligonal** | Cada lado es un segmento paramétrico |

> [!EXAMPLE] Extremos absolutos en región cerrada
> Hallar extremos absolutos de $f(x,y) = x^2 + 2y^2 - x$ en el disco $x^2 + y^2 \leq 4$.
>
> **Solución:**
>
> **Paso 1** — Puntos críticos dentro:
> $\nabla f = (2x - 1, 4y) = (0,0) \Rightarrow x = \frac{1}{2}, y = 0$
> Punto $(\frac{1}{2}, 0)$ está dentro ($(\frac{1}{2})^2 + 0 = 0.25 \leq 4$ ✓)
> $f(\frac{1}{2}, 0) = \frac{1}{4} + 0 - \frac{1}{2} = -\frac{1}{4}$
>
> **Paso 2** — Frontera ($x^2 + y^2 = 4$):
> Parametrizamos: $x = 2\cos t$, $y = 2\sin t$, $t \in [0, 2\pi]$
> $f(t) = 4\cos^2 t + 2(4\sin^2 t) - 2\cos t$
> $f(t) = 4\cos^2 t + 8\sin^2 t - 2\cos t$
> $f(t) = 4(\cos^2 t + \sin^2 t) + 4\sin^2 t - 2\cos t$
> $f(t) = 4 + 4\sin^2 t - 2\cos t$
>
> Derivamos: $f'(t) = 8\sin t\cos t + 2\sin t = 2\sin t(4\cos t + 1) = 0$
> $\sin t = 0 \Rightarrow t = 0, \pi$
> $\cos t = -\frac{1}{4} \Rightarrow t = \arccos(-\frac{1}{4}), 2\pi - \arccos(-\frac{1}{4})$
>
> Evaluamos:
> $t=0$: $(2,0)$, $f = 4 + 0 - 2 = 2$
> $t=\pi$: $(-2,0)$, $f = 4 + 0 + 2 = 6$
> $t=\arccos(-1/4)$: $x = 2(-1/4) = -1/2$, $y = 2\sin t = \pm\sqrt{4 - 1/4} = \pm\sqrt{15/4} = \pm\sqrt{15}/2$, $f = 4 + 4(15/16) - 2(-1/4) = 4 + 15/4 + 1/2 = 4 + 3.75 + 0.5 = 8.25$
>
> **Resultado:**
> - Máximo absoluto: $f = 8.25$ en $(-1/2, \pm\sqrt{15}/2)$
> - Mínimo absoluto: $f = -0.25$ en $(1/2, 0)$

---

## Aplicaciones en ingeniería

| Problema | Modelo | Qué se optimiza |
|:---------|:-------|:----------------|
| **Diseño de vigas** | Resistencia $\propto$ ancho $\times$ alto$^2$ | Maximizar resistencia con perímetro fijo |
| **Tanque de costo mínimo** | Área superficial vs. volumen | Minimizar material para volumen dado |
| **Mecanismos** | Posición de articulaciones | Maximizar ventaja mecánica |
| **Electrostática** | Potencial eléctrico | Encontrar puntos de equilibrio del campo |
| **Ajuste de curvas** | Suma de cuadrados de residuos | Minimizar error (mínimos cuadrados) |

---

## Conexiones con otras áreas

- **[[Anm_Derivadas_Parciales]]**: prerrequisito — el gradiente y la Hessiana son derivadas parciales
- **[[Anm_Integrales_Multiples]]**: centros de masa usan optimización
- **[[Alg_Vectores]]**: el gradiente, Hessiana y producto escalar en Lagrange
- **[[Eje_Fisica]]**: equilibrio mecánico → mínimos de energía potencial
- **[[Eje_Algebra]] [[Alg_Autovalores]]**: los autovalores de la Hessiana determinan la naturaleza del punto crítico (todos positivos → mínimo, todos negativos → máximo, signos mixtos → punto silla)

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Clase 5 — Derivada Direccional (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 5-ING-Derivada Direccional_...pdf` |
| Clase 6 — Extremos (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 6-ING-Extremos_...pdf` |
| Extremos (David Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/extremos.pdf` |
| U6 Extremos (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U6 Extremos.pdf` |
| TP7 Extremos de Funciones de Varias Variables | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP7 Extremos de Funciones de Varias Variables.pdf` |
| Tiro Oblicuo (aplicación) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Tiro Oblicuo.pdf` |

---

## Ejercicios modelados

1. **Puntos críticos**: $f(x,y) = x^2 + y^2 - 2x + 4y + 1$. Encontrar y clasificar.
2. **Punto silla**: Verificar que $(0,0)$ es punto silla de $f(x,y) = x^3 - y^3$.
3. **Lagrange 1**: Maximizar $f(x,y) = 4x^2 + 9y^2$ sujeta a $x^2 + y^2 = 1$.
4. **Lagrange 2**: Encontrar las dimensiones de una caja rectangular (sin tapa) de volumen 4 m³ que minimice el material usado.
5. **Extremos absolutos**: Hallar extremos absolutos de $f(x,y) = x^2 - y^2$ en el cuadrado $0 \leq x \leq 2$, $0 \leq y \leq 2$.

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Derivadas_Parciales]] • **Siguiente:** [[Anm_Integrales_Multiples]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
