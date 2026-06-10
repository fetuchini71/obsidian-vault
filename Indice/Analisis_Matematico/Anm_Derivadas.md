> [!NOTE] Navegación
> **Anterior:** [[Anm_Limites_Continuidad]] • **Siguiente:** [[Anm_Aplicaciones_Derivada]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Derivadas

## Índice

==toc==

---

> [!INFO]
> La derivada mide **cómo cambia** una función en cada punto. Es la herramienta central del cálculo diferencial: velocidades, pendientes, tasas de crecimiento, optimización.
>
> En ingeniería: la derivada es la velocidad instantánea (Mecánica), la corriente $I = dQ/dt$ (Electrónica), la razón de deformación (Materiales), y la pendiente de la curva esfuerzo-deformación.

---

## Definición

$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

**Notaciones equivalentes:**

$$f'(x) = \frac{dy}{dx} = \frac{d}{dx}f(x) = \dot{y}(x) \quad \text{(Newton: } \dot{y} \text{ para derivada temporal)}$$

La derivada en un punto $a$, $f'(a)$, es la **pendiente de la recta tangente** a $f$ en $x = a$.

```
        f(x)
          ▲
          │          ╱ recta secante (h grande)
          │        ╱
          │      ╱
          │    ╱  recta tangente (h → 0)
          │  ╱┈┈┈┈┈┈┈┈┈┈┈
          │╱
          ──•─────────────────▶ x
            a
      Pendiente = f'(a) = tan(α)
```

> [!TIP] Interpretación geométrica
> La derivada es la **pendiente de la recta tangente** en ese punto. Si $f'(a) > 0$, la función crece en $a$; si $f'(a) < 0$, decrece; si $f'(a) = 0$, tiene un punto crítico (posible máximo, mínimo o punto de inflexión horizontal).

> [!EXAMPLE] Calcular derivada por definición
> Hallar $f'(x)$ para $f(x) = \sqrt{x}$ usando la definición de límite.
>
> **Paso 1:** Plantear el cociente incremental.
> $$f'(x) = \lim_{h \to 0} \frac{\sqrt{x+h} - \sqrt{x}}{h}$$
>
> **Paso 2:** Racionalizar el numerador.
> Multiplicamos numerador y denominador por $\sqrt{x+h} + \sqrt{x}$:
> $$f'(x) = \lim_{h \to 0} \frac{(\sqrt{x+h} - \sqrt{x})(\sqrt{x+h} + \sqrt{x})}{h(\sqrt{x+h} + \sqrt{x})}$$
> $$= \lim_{h \to 0} \frac{(x+h) - x}{h(\sqrt{x+h} + \sqrt{x})} = \lim_{h \to 0} \frac{h}{h(\sqrt{x+h} + \sqrt{x})}$$
>
> **Paso 3:** Simplificar $h$ y evaluar.
> $$f'(x) = \lim_{h \to 0} \frac{1}{\sqrt{x+h} + \sqrt{x}} = \frac{1}{\sqrt{x} + \sqrt{x}} = \frac{1}{2\sqrt{x}}$$
>
> **Resultado:** $f'(x) = \frac{1}{2\sqrt{x}}$.
>
> > [!WARNING]
> > El dominio de $f'(x)$ puede ser **más restrictivo** que el de $f(x)$. Acá $f(x) = \sqrt{x}$ tiene dominio $[0, \infty)$, pero $f'(x) = 1/(2\sqrt{x})$ no está definida en $x = 0$.

---

## Reglas de derivación

### Básicas

| Regla | Fórmula | Ejemplo |
|:------|:--------|:--------|
| Constante | $(c)' = 0$ | $(5)' = 0$ |
| Potencia | $(x^n)' = n x^{n-1}$ | $(x^5)' = 5x^4$ |
| Suma | $(f \pm g)' = f' \pm g'$ | — |
| Producto | $(f \cdot g)' = f'g + fg'$ | $(x^2 \sin x)' = 2x\sin x + x^2\cos x$ |
| Cociente | $(f/g)' = \frac{f'g - fg'}{g^2}$ | $\left(\frac{x}{\ln x}\right)' = \frac{\ln x - 1}{(\ln x)^2}$ |
| Cadena | $(f \circ g)' = f'(g(x)) \cdot g'(x)$ | $(\sin(x^2))' = \cos(x^2) \cdot 2x$ |

> [!WARNING] Error común: regla del producto
> $(fg)' \neq f' \cdot g'$ !!! **Nunca** derivás factor por factor. Tenés que usar $f'g + fg'$.

> [!EXAMPLE] Regla del producto y cadena combinadas
> Hallar $f'(x)$ para $f(x) = x^2 \cdot e^{\sin x}$.
>
> **Paso 1:** Aplicar regla del producto.
> $f'(x) = (x^2)' \cdot e^{\sin x} + x^2 \cdot (e^{\sin x})'$
>
> **Paso 2:** Derivar cada factor.
> $(x^2)' = 2x$
> $(e^{\sin x})' = e^{\sin x} \cdot (\sin x)' = e^{\sin x} \cdot \cos x$ (regla de la cadena)
>
> **Paso 3:** Combinar.
> $$f'(x) = 2x \cdot e^{\sin x} + x^2 \cdot e^{\sin x} \cdot \cos x = e^{\sin x}(2x + x^2 \cos x)$$
>
> **Resultado:** $f'(x) = e^{\sin x}(2x + x^2 \cos x)$.

### Trigonométricas

| Función | Derivada |
|:--------|:---------|
| $\sin x$ | $\cos x$ |
| $\cos x$ | $-\sin x$ |
| $\tan x$ | $\sec^2 x$ |
| $\sec x$ | $\sec x \tan x$ |
| $\csc x$ | $-\csc x \cot x$ |
| $\cot x$ | $-\csc^2 x$ |

> [!TIP] Patrón para recordar derivadas trigonométricas
> Las derivadas "co-" (coseno, cosecante, cotangente) llevan **signo negativo**. Las que no tienen "co-" (seno, secante, tangente) son positivas.

### Exponenciales y logarítmicas

| Función | Derivada |
|:--------|:---------|
| $e^x$ | $e^x$ |
| $a^x$ | $a^x \ln a$ |
| $\ln x$ | $1/x$ |
| $\log_a x$ | $1/(x \ln a)$ |

> [!TIP] La función más especial
> $e^x$ es la **única** función (salvo la constante $c \cdot e^x$) cuya derivada es ella misma. Por eso aparece en tantos modelos de crecimiento, decaimiento y circuitos.

### Hiperbólicas

| Función | Derivada |
|:--------|:---------|
| $\sinh x$ | $\cosh x$ |
| $\cosh x$ | $\sinh x$ |
| $\tanh x$ | $\text{sech}^2 x$ |

> [!NOTE] Conexión
> Las funciones hiperbólicas aparecen en la forma de un **cable colgante** (catenaria), usado en puentes colgantes y líneas de transmisión eléctrica.

---

## Derivación implícita

Cuando la función está definida implícitamente ($F(x,y) = 0$), derivamos ambos lados respecto a $x$ tratando $y$ como $y(x)$ y luego despejamos $y'$.

> [!EXAMPLE] Derivación implícita
> Hallar $y'$ si $x^2 + y^2 = 25$.
>
> **Paso 1:** Derivar ambos lados respecto a $x$.
> $$\frac{d}{dx}(x^2) + \frac{d}{dx}(y^2) = \frac{d}{dx}(25)$$
>
> **Paso 2:** Aplicar regla de la cadena en $y^2$.
> $$2x + 2y \cdot y' = 0$$
>
> **Paso 3:** Despejar $y'$.
> $$2y \cdot y' = -2x \implies y' = -\frac{x}{y}$$
>
> **Resultado:** $\displaystyle y' = -\frac{x}{y}$.
>
> > [!TIP]
> > La derivada implícita es clave cuando no podés (o no querés) despejar $y$ explícitamente. Se usa mucho en [[Anm_Aplicaciones_Derivada]] para tasas relacionadas.

---

## Derivación logarítmica

Útil para funciones del tipo $f(x)^{g(x)}$ o productos/cocientes largos: tomamos $\ln$ a ambos lados y derivamos implícitamente.

> [!EXAMPLE] Derivación logarítmica
> Hallar $y'$ si $y = x^{\sin x}$.
>
> **Paso 1:** Aplicar $\ln$ a ambos lados.
> $$\ln y = \ln(x^{\sin x}) = \sin x \cdot \ln x$$
>
> **Paso 2:** Derivar implícitamente.
> $$\frac{1}{y} \cdot y' = \cos x \cdot \ln x + \sin x \cdot \frac{1}{x}$$
>
> **Paso 3:** Despejar $y'$.
> $$y' = y \left(\cos x \ln x + \frac{\sin x}{x}\right) = x^{\sin x} \left(\cos x \ln x + \frac{\sin x}{x}\right)$$
>
> **Resultado:** $y' = x^{\sin x} \left(\cos x \ln x + \frac{\sin x}{x}\right)$.

---

## Derivadas de orden superior

La segunda derivada $f''(x)$ es la derivada de $f'(x)$. Mide la **tasa de cambio de la pendiente** — es decir, la **aceleración** si $f$ es posición.

$$f''(x) = \frac{d}{dx}[f'(x)] = \frac{d^2y}{dx^2}$$

- $f''(x) > 0$: función cóncava hacia arriba (∪)
- $f''(x) < 0$: función cóncava hacia abajo (∩)

| Orden | Notación | Interpretación física |
|:------|:---------|:---------------------|
| 0 | $f(t)$ | Posición |
| 1 | $f'(t)$ o $v(t)$ | Velocidad |
| 2 | $f''(t)$ o $a(t)$ | Aceleración |
| 3 | $f'''(t)$ | Jerk (sacudida) |

---

## Diferencial

$$dy = f'(x) \, dx$$

Es la **aproximación lineal** del cambio en $y$ cuando $x$ cambia en $dx$. Para pequeños cambios $\Delta x \approx dx$:

$$\Delta y \approx f'(x) \cdot \Delta x$$

> [!EXAMPLE] Aproximación lineal
> Aproximar $\sqrt{4.1}$ usando diferenciales.
>
> **Paso 1:** Elegir $f(x) = \sqrt{x}$, $x = 4$, $dx = 0.1$.
>
> **Paso 2:** $f'(x) = \frac{1}{2\sqrt{x}}$, entonces $f'(4) = \frac{1}{2\sqrt{4}} = \frac{1}{4}$.
>
> **Paso 3:** $dy = f'(4) \cdot dx = \frac{1}{4} \cdot 0.1 = 0.025$.
>
> **Resultado:** $\sqrt{4.1} \approx f(4) + dy = 2 + 0.025 = 2.025$.
>
> (Valor real: $\sqrt{4.1} \approx 2.0248$ — error de solo 0.0002)

---

## Tabla de derivadas (resumen rápido)

| $f(x)$ | $f'(x)$ |
|:-------|:--------|
| $c$ | $0$ |
| $x^n$ | $n x^{n-1}$ |
| $e^x$ | $e^x$ |
| $a^x$ | $a^x \ln a$ |
| $\ln x$ | $1/x$ |
| $\sin x$ | $\cos x$ |
| $\cos x$ | $-\sin x$ |
| $\tan x$ | $\sec^2 x$ |
| $\arcsin x$ | $1/\sqrt{1-x^2}$ |
| $\arccos x$ | $-1/\sqrt{1-x^2}$ |
| $\arctan x$ | $1/(1+x^2)$ |
| $\sinh x$ | $\cosh x$ |
| $\cosh x$ | $\sinh x$ |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Apunte U3 (Ocampo) — Derivadas | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 3.pdf` |
| Teoría derivadas (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/derivadas.pdf` |
| Apunte Derivadas (profes) | `Raw/.../AnM1/Teorías/Derivadas.pdf` |
| Material teórico U3 (Derivadas 1ra parte) | `Raw/.../AnM1/Teorías/Material teórico/Unidad 3 Derivadas (1º parte ).pdf` |
| Clase 7-4 — Derivadas motivación y reglas | `Raw/.../AnM1/Teorías/Unidad 3 Derivadas/clase 7-4- Derivadas motivacion y reglas de derivacion.pdf` |
| Clase 8-4 — Derivada implícita, logarítmica, razón de cambio | `Raw/.../AnM1/Teorías/Unidad 3 Derivadas/clase 8-4- Derivadas implicita, logaritmica y razon de cambio.pdf` |
| Apuntes de clase U3 (2 clases) | `Raw/.../AnM1/Teorías/Apuntes de clase UNIDAD 3/` |
| Presentaciones teóricas U3 | `Raw/.../AnM1/Teorías/Presentaciores de clases teoricas/Unidad 3 -*` |
| TP N° 4 - Derivadas | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TP N° 4 - Derivadas.pdf` |
| Ejercicios adicionales - Derivadas | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Derivadas.pdf` |
| Autoevaluación derivadas (y resolución) | `Raw/.../1 matematica/PRACTICA/Análisis matemático I/autoevaluaciones/3.1 Autoevaluación de derivadas (1).pdf` |
| Tabla de derivadas | `Raw/.../1 matematica/TEORIA/Análisis matemático I/Tabla de derivadas.pdf` |
| Tabla derivadas e integrales | `Raw/.../AnM1/Teorías/Tabla-Derivada-Integral.pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Limites_Continuidad]] • **Siguiente:** [[Anm_Aplicaciones_Derivada]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
