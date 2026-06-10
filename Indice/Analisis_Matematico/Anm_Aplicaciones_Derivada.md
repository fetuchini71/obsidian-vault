> [!NOTE] Navegación
> **Anterior:** [[Anm_Derivadas]] • **Siguiente:** [[Anm_Integrales]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Aplicaciones de la Derivada

## Índice

==toc==

---

> [!INFO]
> Acá la derivada deja de ser teoría y empieza a **resolver problemas concretos**: máximos, mínimos, aproximaciones, gráficos de funciones y límites indeterminados.
>
> En ingeniería: optimización de formas estructurales, velocidad y aceleración en mecanismos, control de procesos, ajuste de parámetros en sistemas eléctricos.

---

## Teorema del Valor Medio (TVM)

Si $f$ es continua en $[a,b]$ y derivable en $(a,b)$, existe $c \in (a,b)$ tal que:

$$f'(c) = \frac{f(b) - f(a)}{b - a}$$

```
        f(x)
          ▲
        f(b)┤──────────────•
          │              ╱
          │            ╱
          │          ╱
          │        ╱
        f(a)•───╱──────────
          │  ╱
          │╱
          ──┴────┴─────────▶ x
            a    c     b
            \______/
         pendiente = f'(c)
```

Interpretación: existe al menos un punto donde la **tangente es paralela** a la **recta secante** que une $(a, f(a))$ y $(b, f(b))$.

**Casos particulares:**
- **Rolle**: si $f(a) = f(b)$ entonces $f'(c) = 0$ para algún $c \in (a,b)$.
- **Teorema del valor medio de Cauchy**: generalización para dos funciones.

> [!EXAMPLE] Aplicación del TVM de Rolle
> Verificar que $f(x) = x^3 - 3x$ cumple el Teorema de Rolle en $[-2, 2]$ y hallar $c$.
>
> **Paso 1:** Verificar hipótesis.
> $f$ es polinómica → continua en $[-2,2]$ y derivable en $(-2,2)$ ✓
>
> **Paso 2:** Verificar $f(a) = f(b)$.
> $f(-2) = (-2)^3 - 3(-2) = -8 + 6 = -2$
> $f(2) = 2^3 - 3(2) = 8 - 6 = 2$
> $f(-2) \neq f(2)$ → Rolle **no aplica**.
>
> > [!WARNING]
> > Rolle requiere **$f(a) = f(b)$**. Si no se cumple, el teorema no es aplicable (aunque igual puede haber un punto con derivada cero).

> [!EXAMPLE] TVM de Cauchy
> Aplicar el TVM a $f(x) = \sqrt{x}$ en $[1, 4]$ y hallar $c$.
>
> **Paso 1:** $f$ es continua en $[1,4]$ y derivable en $(1,4)$ ✓
>
> **Paso 2:** Calcular.
> $f(4) = 2$, $f(1) = 1$
> $$f'(c) = \frac{f(4) - f(1)}{4 - 1} = \frac{2 - 1}{3} = \frac{1}{3}$$
>
> **Paso 3:** $f'(x) = \frac{1}{2\sqrt{x}}$, igualamos:
> $$\frac{1}{2\sqrt{c}} = \frac{1}{3} \implies 2\sqrt{c} = 3 \implies c = \frac{9}{4} = 2.25$$
>
> **Resultado:** $c = 2.25 \in (1, 4)$ ✓

---

## Extremos de una función

| Concepto | Descripción |
|----------|-------------|
| **Máximo absoluto** | $f(c) \geq f(x)$ para todo $x$ en el dominio |
| **Mínimo absoluto** | $f(c) \leq f(x)$ para todo $x$ en el dominio |
| **Máximo local** | $f(c) \geq f(x)$ para $x$ cerca de $c$ |
| **Mínimo local** | $f(c) \leq f(x)$ para $x$ cerca de $c$ |
| **Punto crítico** | $f'(c) = 0$ o $f'(c)$ no existe |
| **Criterio 1ra derivada** | Signo de $f'$ alrededor del punto crítico |
| **Criterio 2da derivada** | $f''(c) > 0 \Rightarrow$ mínimo local; $f''(c) < 0 \Rightarrow$ máximo local |

```
            ▲ f(x)
            │    ╱⌢╲
            │  ╱╱    ╲╲        ← máximo local
            │╱╱        ╲╲
            ││          ││
            │╲╲        ╱╱
            │  ╲╲    ╱╱        ← mínimo local
            │    ╲⌣╱
            └─────────────────▶ x
```

> [!EXAMPLE] Hallar extremos con criterio de 2da derivada
> Encontrar los extremos de $f(x) = x^3 - 6x^2 + 9x + 1$.
>
> **Paso 1:** Hallar puntos críticos ($f'(x) = 0$).
> $f'(x) = 3x^2 - 12x + 9 = 3(x^2 - 4x + 3) = 3(x-1)(x-3)$
> $x = 1$ o $x = 3$
>
> **Paso 2:** Aplicar criterio de 2da derivada.
> $f''(x) = 6x - 12$
>
> En $x = 1$: $f''(1) = 6(1) - 12 = -6 < 0$ → **máximo local**
> En $x = 3$: $f''(3) = 6(3) - 12 = 6 > 0$ → **mínimo local**
>
> **Paso 3:** Hallar valores.
> $f(1) = 1 - 6 + 9 + 1 = 5$ → máximo local en $(1, 5)$
> $f(3) = 27 - 54 + 27 + 1 = 1$ → mínimo local en $(3, 1)$
>
> **Resultado:** Máximo local en $x=1$ ($f=5$), mínimo local en $x=3$ ($f=1$).

---

## Concavidad y puntos de inflexión

- $f''(x) > 0$ → cóncava hacia arriba (∪) — "la función acelera"
- $f''(x) < 0$ → cóncava hacia abajo (∩) — "la función frena"
- **Punto de inflexión**: donde $f''$ cambia de signo y $f$ es continua

```
    Cóncava arriba (∪)     Cóncava abajo (∩)
       ╱"""╲                   ╲"""╱
      ╱     ╲                 ╱     ╲
     ╱       ╲               ╱       ╲
    ╱         ╲             ╱         ╲
   ╲_ _ _ _ _ ╱           ╱_ _ _ _ _ ╲
   f''(x) > 0             f''(x) < 0
```

> [!TIP] Mnemotecnia
> Si $f''(x) > 0$, la curva **tiene forma de sonrisa** (∪). Si $f''(x) < 0$, **tristeza** (∩).

---

## Estudio completo de curvas

Para graficar $f(x)$ exhaustivamente:
1. **Dominio y simetrías** (pares, impares, periódicas)
2. **Intersecciones con ejes** ($x=0$ → ordenada; $y=0$ → raíces)
3. **Asíntotas** (verticales, horizontales, oblicuas)
4. **Intervalos de crecimiento** ($f' > 0$) y **decrecimiento** ($f' < 0$)
5. **Extremos locales**
6. **Concavidad y puntos de inflexión**
7. **Tabla de valores** y gráfico

> [!EXAMPLE] Estudio completo de curva
> Analizar y graficar $f(x) = \frac{x^2}{x^2 - 1}$.
>
> **Paso 1:** Dominio. $x^2 - 1 \neq 0 \Rightarrow x \neq \pm 1$. $D = \mathbb{R} \setminus \{-1, 1\}$.
>
> **Paso 2:** Simetría. $f(-x) = \frac{(-x)^2}{(-x)^2-1} = \frac{x^2}{x^2-1} = f(x)$ → **función par** (simétrica al eje $y$).
>
> **Paso 3:** Intersecciones. $x=0 \Rightarrow f(0)=0$ → $(0,0)$. $y=0 \Rightarrow x^2=0 \Rightarrow x=0$.
>
> **Paso 4:** Asíntotas verticales: $x = \pm 1$ (denominador = 0).
> $\lim_{x \to 1^-} f(x) = -\infty$, $\lim_{x \to 1^+} f(x) = +\infty$
>
> **Paso 5:** Asíntota horizontal: $\lim_{x \to \pm\infty} \frac{x^2}{x^2-1} = 1$ → $y=1$.
>
> **Paso 6:** Derivada primera.
> $f'(x) = \frac{2x(x^2-1) - x^2(2x)}{(x^2-1)^2} = \frac{-2x}{(x^2-1)^2}$
> Punto crítico: $x=0$.
>
> **Paso 7:** Crecimiento. $f'(x) > 0$ cuando $-2x > 0 \Rightarrow x < 0$. Crece en $(-\infty, -1) \cup (-1, 0)$. Decrece en $(0,1) \cup (1, \infty)$.
>
> **Paso 8:** Extremo. En $x=0$, $f'(0)=0$, $f''(0) = \frac{2(3x^2+1)}{(x^2-1)^3} = -2 < 0$ → máximo local en $(0,0)$.
>
> **Resultado:** Gráfico con AV en $x=\pm 1$, AH en $y=1$, máximo en $(0,0)$.

---

## Regla de L'Hôpital

Para límites indeterminados $0/0$ o $\infty/\infty$:

$$\lim_{x \to a} \frac{f(x)}{g(x)} = \lim_{x \to a} \frac{f'(x)}{g'(x)}$$

(si el nuevo límite existe o es $\pm\infty$)

> [!WARNING] Condiciones de L'Hôpital
> Solo aplica si el límite original es **indeterminado** ($0/0$ o $\infty/\infty$). No apliques L'Hôpital a límites que ya se pueden evaluar directamente.

> [!EXAMPLE] L'Hôpital
> Hallar $\displaystyle \lim_{x \to 0} \frac{\sin x - x}{x^3}$.
>
> **Paso 1:** Verificar indeterminación.
> $\frac{\sin 0 - 0}{0^3} = \frac{0}{0}$ ✓
>
> **Paso 2:** Aplicar L'Hôpital (1ra vez).
> $$\lim_{x \to 0} \frac{\cos x - 1}{3x^2}$$
>
> **Paso 3:** Sigue $0/0$. Aplicar L'Hôpital (2da vez).
> $$\lim_{x \to 0} \frac{-\sin x}{6x}$$
>
> **Paso 4:** Sigue $0/0$. Aplicar L'Hôpital (3ra vez).
> $$\lim_{x \to 0} \frac{-\cos x}{6} = -\frac{1}{6}$$
>
> **Resultado:** $\displaystyle \lim_{x \to 0} \frac{\sin x - x}{x^3} = -\frac{1}{6}$.

---

## Polinomio de Taylor

Aproxima $f(x)$ cerca de $x = a$ mediante un polinomio de grado $n$:

$$P_n(x) = \sum_{k=0}^{n} \frac{f^{(k)}(a)}{k!} (x - a)^k$$

**Series de Maclaurin** (Taylor con $a=0$):

| Función | Serie de Maclaurin |
|:--------|:-------------------|
| $e^x$ | $1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots$ |
| $\sin x$ | $x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dots$ |
| $\cos x$ | $1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots$ |
| $\frac{1}{1-x}$ | $1 + x + x^2 + x^3 + \dots$ (para $|x|<1$) |
| $\ln(1+x)$ | $x - \frac{x^2}{2} + \frac{x^3}{3} - \dots$ |

> [!EXAMPLE] Aproximación por Taylor
> Aproximar $f(x) = e^x$ con un polinomio de grado 3 alrededor de $x=0$, y estimar $e^{0.1}$.
>
> **Paso 1:** Calcular derivadas en $x=0$.
> $f(0)=1$, $f'(0)=1$, $f''(0)=1$, $f'''(0)=1$
>
> **Paso 2:** Construir $P_3(x)$.
> $$P_3(x) = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} = 1 + x + \frac{x^2}{2} + \frac{x^3}{6}$$
>
> **Paso 3:** Evaluar en $x=0.1$.
> $$P_3(0.1) = 1 + 0.1 + \frac{0.01}{2} + \frac{0.001}{6} = 1 + 0.1 + 0.005 + 0.000167 = 1.105167$$
>
> Valor real: $e^{0.1} \approx 1.105171$ — **error de solo $4 \times 10^{-6}$**.
>
> > [!TIP]
> > Los polinomios de Taylor son la base de las **aproximaciones numéricas** en calculadoras y computadoras — tu calculadora usa un polinomio de Taylor para calcular $e^x$, $\sin x$, etc.

---

## Problemas de optimización

Pasos: identificar variable a optimizar, expresarla en función de una variable, derivar, igualar a 0, verificar tipo de extremo con 2da derivada.

> [!EXAMPLE] Optimización — Caja de volumen máximo
> Se quiere construir una caja abierta a partir de una hoja rectangular de 30×20 cm, cortando cuadrados de lado $x$ en cada esquina y doblando. Hallar $x$ para maximizar el volumen.
>
> **Paso 1:** Expresar el volumen.
> Base: $(30-2x)(20-2x)$, altura: $x$
> $$V(x) = x(30-2x)(20-2x) = x(600 - 100x + 4x^2) = 4x^3 - 100x^2 + 600x$$
>
> Dominio: $0 < x < 10$ (el lado menor es 20, $2x < 20 \Rightarrow x < 10$).
>
> **Paso 2:** Derivar e igualar a 0.
> $$V'(x) = 12x^2 - 200x + 600 = 4(3x^2 - 50x + 150) = 0$$
> $$x = \frac{50 \pm \sqrt{2500 - 1800}}{6} = \frac{50 \pm \sqrt{700}}{6} = \frac{50 \pm 10\sqrt{7}}{6}$$
> $$x_1 \approx 3.92, \quad x_2 \approx 12.74 \text{ (fuera del dominio)}$$
>
> **Paso 3:** Verificar con 2da derivada.
> $V''(3.92) = 24(3.92) - 200 \approx -105.9 < 0$ → **máximo** ✓
>
> **Resultado:** Cortar cuadrados de $x \approx 3.92$ cm → volumen máximo $V(3.92) \approx 1056.3$ cm³.
>
> ```
>     ┌────┬──────────────┬────┐
>     │    │              │    │  x
>     ├────┼──────────────┼────┤
>     │    │              │    │
>     │    │              │    │  20-2x
>     │    │              │    │
>     ├────┼──────────────┼────┤
>     │    │              │    │  x
>     └────┴──────────────┴────┘
>          ←── 30-2x ──→
>     ┌─────────────────────┐
>     │  ┌───────────────┐  │
>     │  │               │  │  x
>     │  │               │  │
>     │  │    CAJA       │  │  20-2x
>     │  │               │  │
>     │  │               │  │
>     │  └───────────────┘  │
>     │←─── 30-2x ────────→│
>     └─────────────────────┘
> ```

---

## Tabla resumen de aplicaciones

| Aplicación | Concepto | Fórmula clave |
|:-----------|:---------|:--------------|
| TVM / Rolle | Existencia de $c$ con pendiente igual | $f'(c) = \frac{f(b)-f(a)}{b-a}$ |
| Extremos | Puntos críticos | $f'(x)=0$ |
| Crecimiento | $f' > 0$ crece, $f' < 0$ decrece | Signo de $f'$ |
| Concavidad | $f'' > 0$ ∪, $f'' < 0$ ∩ | Signo de $f''$ |
| L'Hôpital | Límites $0/0$, $\infty/\infty$ | $\lim \frac{f}{g} = \lim \frac{f'}{g'}$ |
| Taylor | Aproximación polinómica local | $P_n(x) = \sum \frac{f^{(k)}(a)}{k!} (x-a)^k$ |
| Optimización | Maximizar/minimizar cantidades | $f'(x)=0$, $f''(x)$ determina tipo |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Apunte U4 (Ocampo) — Ap. Derivada | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 4.pdf` |
| Teoría extremos (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/extremos.pdf` |
| Teoría L'Hôpital, Taylor (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/l_hopital - diferenciables - polinomio de Taylor .pdf` |
| Teoría estudio de curvas (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/teoremas y estudio de curvas.pdf` |
| Teoría optimización (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/optimización .pdf` |
| Apunte Aplicaciones derivada (profes) | `Raw/.../AnM1/Teorías/Aplicaciones de la derivada.pdf` |
| Aplicaciones 1ra parte | `Raw/.../AnM1/Teorías/Aplicaciones de la derivada (Primera parte).pdf` |
| Aplicaciones 2da parte | `Raw/.../AnM1/Teorías/Aplicaciones de la derivada (Segunda parte).pdf` |
| Apuntes de clase U4 (7 clases) | `Raw/.../AnM1/Teorías/Apuntes de clase UNIDAD 4/` |
| Presentaciones teóricas U4 | `Raw/.../AnM1/Teorías/Presentaciores de clases teoricas/Unidad 4 -*` |
| Clase 9 - Aplicaciones (Parte 1) | `Raw/.../AnM1/Teorías/Unidad 4 Aplicaciones de la Derivada/clase 9-Aplicaciones de la derivada (Parte 1).pdf` |
| Clase 10 - Aplicaciones (Parte 2) | `Raw/.../AnM1/Teorías/Unidad 4 Aplicaciones de la Derivada/clase 10-Aplicaciones de la derivada ultima(Parte 2).pdf` |
| Resumen análisis (bis) | `Raw/.../AnM1/Teorías/Unidad 4 Aplicaciones de la Derivada/resumen_analisis ultimo bis.pdf` |
| TP N° 5 - Aplicaciones de la derivada | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TP N° 5 - Aplicaciones de la derivada-1.pdf` |
| Ejercicios adicionales - Ap. derivada | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Aplicaciones de la derivada.pdf` |
| Autoevaluación ap. derivada (y resolución) | `Raw/.../1 matematica/PRACTICA/Análisis matemático I/autoevaluaciones/autoevaluación - ap derivadas.pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Derivadas]] • **Siguiente:** [[Anm_Integrales]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
