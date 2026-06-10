> [!NOTE] Navegación
> **Anterior:** [[Anm_Integrales]] • **Siguiente:** [[Anm_Sucesiones_Series]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Aplicaciones de la Integral

## Índice

==toc==

---

> [!INFO]
> Con la integral podés calcular **áreas, volúmenes, longitudes, trabajo, centros de masa y mucho más**. Es la herramienta que vincula el cálculo con el mundo físico.
>
> En ingeniería: diseño de tanques (volúmenes de revolución), vigas (momento de inercia), trabajo en sistemas termodinámicos, longitud de cables colgantes, y modelos de probabilidad continua.

---

## Área entre curvas

$$A = \int_a^b [f(x) - g(x)] \, dx$$

donde $f(x) \geq g(x)$ en $[a, b]$.

```
        f(x)
          ▲
          │     ┌──────────────────────┐
          │    ┌┘  f(x) (superior)     │
          │   ┌┘┌──────────────────────┤
          │  ┌┘┌┘   ÁREA              └┐
          │ ┌┘┌┘                      └┐
          │┌┘┌┘  g(x) (inferior)      └┐
          ─┴──┴─────────────────────────▶ x
           a                           b
```

> [!EXAMPLE] Área entre curvas
> Calcular el área entre $f(x) = x^2$ y $g(x) = x + 2$.
>
> **Paso 1:** Hallar intersecciones.
> $x^2 = x + 2 \implies x^2 - x - 2 = 0 \implies (x-2)(x+1) = 0$
> $x = -1$ y $x = 2$
>
> **Paso 2:** Determinar cuál está arriba.
> En $[0, 1]$: $g(0) = 2 > f(0) = 0$ → $g(x)$ arriba.
>
> **Paso 3:** Calcular el área.
> $$A = \int_{-1}^2 [(x+2) - x^2] \, dx = \int_{-1}^2 (x + 2 - x^2) \, dx$$
>
> **Paso 4:** Integrar.
> $$A = \left[\frac{x^2}{2} + 2x - \frac{x^3}{3}\right]_{-1}^2$$
>
> **Paso 5:** Evaluar.
> En $x=2$: $2 + 4 - \frac{8}{3} = 6 - \frac{8}{3} = \frac{10}{3}$
> En $x=-1$: $\frac{1}{2} - 2 + \frac{1}{3} = \frac{3-12+2}{6} = -\frac{7}{6}$
> $$A = \frac{10}{3} - \left(-\frac{7}{6}\right) = \frac{20}{6} + \frac{7}{6} = \frac{27}{6} = \frac{9}{2}$$
>
> **Resultado:** $A = 4.5$ unidades cuadradas.

> [!WARNING] Siempre verificar cuál función está arriba
> Si $f$ y $g$ se cruzan en el intervalo, tenés que separar en subintervalos y sumar áreas parciales. Usá $|f(x)-g(x)|$ como integrando.

---

## Volúmenes de sólidos

### Método de discos (revolución alrededor del eje x)

$$V = \pi \int_a^b [R(x)]^2 \, dx$$

```
        f(x)
          ▲
          │       ┌─────┐
          │      ╱│     │╲
          │     ╱ │     │ ╲
          │    ╱  │     │  ╲
          │   ╱   │  R  │   ╲   ← f(x) es el radio
          │  ╱    │     │    ╲
          │ ╱     │     │     ╲
          ─┴─────────────────────▶ x
           a   ←── disco ──→  b
```

### Método de arandelas (revolución — con hueco)

$$V = \pi \int_a^b \big([R(x)]^2 - [r(x)]^2\big) \, dx$$

donde $R(x)$ es el radio exterior y $r(x)$ el radio interior.

```
        f(x) ── radio exterior R(x)
          ▲
          │     ╔═════════════╗
          │    ╔║┌───────────┐║╗
          │   ╔║│   HUECO    │║╗╗
          │  ╔║│   r(x)     │║╗╗╗
          │ ╔║└───────────┘║╗╗╗╗╗
          │╔╚═════════════╝╗╗╗╗╗╗
          ─┴────────────────────────▶ x
           a                        b
        g(x) ── radio interior r(x)
```

### Método de capas cilíndricas

$$V = 2\pi \int_a^b r(x) \cdot h(x) \, dx$$

> [!EXAMPLE] Volumen por discos
> Calcular el volumen generado al rotar $f(x) = \sqrt{x}$ alrededor del eje $x$ en $[0, 4]$.
>
> **Paso 1:** Identificar radio.
> $R(x) = f(x) = \sqrt{x}$
>
> **Paso 2:** Plantear la integral.
> $$V = \pi \int_0^4 (\sqrt{x})^2 \, dx = \pi \int_0^4 x \, dx$$
>
> **Paso 3:** Integrar.
> $$V = \pi \left[\frac{x^2}{2}\right]_0^4 = \pi \left(\frac{16}{2} - 0\right) = 8\pi$$
>
> **Resultado:** $V = 8\pi \approx 25.13$ unidades cúbicas.

> [!EXAMPLE] Volumen por arandelas
> Calcular el volumen al rotar la región entre $f(x)=x$ y $g(x)=x^2$ alrededor del eje $x$.
>
> **Paso 1:** Hallar intersecciones.
> $x = x^2 \implies x(x-1) = 0 \implies x = 0, 1$
>
> **Paso 2:** Identificar radios.
> Radio exterior $R(x) = x$ (arriba), radio interior $r(x) = x^2$ (abajo).
>
> **Paso 3:** Plantear integral.
> $$V = \pi \int_0^1 [x^2 - (x^2)^2] \, dx = \pi \int_0^1 (x^2 - x^4) \, dx$$
>
> **Paso 4:** Integrar.
> $$V = \pi \left[\frac{x^3}{3} - \frac{x^5}{5}\right]_0^1 = \pi \left(\frac{1}{3} - \frac{1}{5}\right) = \pi \cdot \frac{2}{15} = \frac{2\pi}{15}$$
>
> **Resultado:** $V = \frac{2\pi}{15} \approx 0.419$ unidades cúbicas.

---

## Longitud de arco

$$L = \int_a^b \sqrt{1 + [f'(x)]^2} \, dx$$

```
        f(x)
          ▲
          │         ╲
          │          ╲   ∆s
          │           ╲ ┌─┐
          │            ╲│ │
          │             ╲┘
          │
          ────────────────▶ x
           a            b
          \_____________/
          L = ∫ √(1+(f')²) dx
```

> [!EXAMPLE] Longitud de arco
> Calcular la longitud de $f(x) = \frac{2}{3}x^{3/2}$ en $[0, 3]$.
>
> **Paso 1:** Derivar.
> $f'(x) = \frac{2}{3} \cdot \frac{3}{2} x^{1/2} = \sqrt{x}$
>
> **Paso 2:** Armar el integrando.
> $\sqrt{1 + [f'(x)]^2} = \sqrt{1 + x}$
>
> **Paso 3:** Integrar.
> $$L = \int_0^3 \sqrt{1+x} \, dx = \int_0^3 (1+x)^{1/2} \, dx$$
> $$L = \left[\frac{2}{3}(1+x)^{3/2}\right]_0^3 = \frac{2}{3}(4^{3/2} - 1^{3/2}) = \frac{2}{3}(8 - 1) = \frac{14}{3}$$
>
> **Resultado:** $L = \frac{14}{3} \approx 4.667$ unidades.

> [!TIP] Longitud de arco en ingeniería
> La longitud de arco se usa para calcular la **longitud de cables**, **tuberías curvas**, y en diseño de **engranajes** y **levas**. También aparece en problemas de **trabajo** cuando la fuerza sigue una trayectoria curva.

---

## Integrales impropias

Cuando el intervalo es infinito o la función tiene una discontinuidad:

| Tipo | Definición | Convergencia |
|:-----|:-----------|:-------------|
| Intervalo infinito (tipo I) | $\int_a^\infty f(x) \, dx = \lim_{t \to \infty} \int_a^t f(x) \, dx$ | Límite finito → converge |
| Discontinuidad (tipo II) | $\int_a^b f(x) \, dx = \lim_{t \to b^-} \int_a^t f(x) \, dx$ | Límite finito → converge |

> [!EXAMPLE] Integral impropia convergente
> Determinar si $\displaystyle \int_1^\infty \frac{1}{x^2} \, dx$ converge o diverge.
>
> **Paso 1:** Plantear como límite.
> $$\int_1^\infty \frac{1}{x^2} \, dx = \lim_{t \to \infty} \int_1^t x^{-2} \, dx$$
>
> **Paso 2:** Integrar.
> $$\lim_{t \to \infty} \left[-x^{-1}\right]_1^t = \lim_{t \to \infty} \left(-\frac{1}{t} + 1\right)$$
>
> **Paso 3:** Evaluar el límite.
> $$\lim_{t \to \infty} \left(1 - \frac{1}{t}\right) = 1$$
>
> **Resultado:** La integral **converge** a $1$.
>
> ```
>        f(x) = 1/x²
>          ▲
>          │
>        1 ┤
>          │╲
>          │ ╲    ÁREA FINITA = 1
>          │  ╲    (aunque el dominio
>          │   ╲    es infinito)
>          ────╲───────▶ x
>          1        ∞
> ```

> [!WARNING] $1/x$ diverge, $1/x^2$ converge
> La integral $\int_1^\infty \frac{1}{x^p} \, dx$ converge si $p > 1$ y diverge si $p \leq 1$. Es un resultado clave que se relaciona con la convergencia de series $p$ en [[Anm_Sucesiones_Series]].

---

## Área en coordenadas polares

$$A = \frac{1}{2} \int_\alpha^\beta [r(\theta)]^2 \, d\theta$$

> [!TIP]
> Las coordenadas polares son especialmente útiles para regiones con simetría circular o espirales. Se relaciona con [[Anm_Funciones_Varias_Variables]] en el estudio de coordenadas curvilíneas.

---

## Aplicaciones avanzadas en ingeniería

| Aplicación | Fórmula | Descripción |
|:-----------|:--------|:------------|
| Valor promedio de una función | $\bar{f} = \frac{1}{b-a}\int_a^b f(x)\,dx$ | Útil para señales AC (valor medio) |
| Trabajo de una fuerza variable | $W = \int_{x_1}^{x_2} F(x)\,dx$ | Estirar un resorte, bombear agua |
| Centroide de una región plana | $\bar{x} = \frac{1}{A}\int x\,dA$, $\bar{y} = \frac{1}{A}\int y\,dA$ | Centro de masa en Estática |
| Teorema de Pappus | $V = A \cdot d$ (distancia recorrida por el centroide) | Volúmenes de sólidos de revolución |
| Superficie de revolución | $S = 2\pi \int_a^b f(x)\sqrt{1+[f'(x)]^2}\,dx$ | Área lateral al rotar una curva |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Teoría integral definida (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/integral definida.pdf` |
| Apunte Integrales (2da parte) (profes) | `Raw/.../AnM1/Teorías/Integrales (Segunda parte).pdf` |
| Clase 13 — Área y longitud de arco | `Raw/.../AnM1/Teorías/Unidad 5 Integrales/clase13 -12-5-26_area_longitud_arco.pdf` |
| Clase 14 — Integrales impropias | `Raw/.../AnM1/Teorías/Unidad 5 Integrales/clase14_integrales_impropias.pdf` |
| TP7 Aplicaciones Integrales AnMat1 2026 | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TP7_Ap.Integrales_AnMat1_2026.pdf` |
| Ejercicios adicionales - Integrales (2da parte) | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Integrales (Segunda parte).pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Integrales]] • **Siguiente:** [[Anm_Sucesiones_Series]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
