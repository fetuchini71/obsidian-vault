> [!NOTE] Navegación
> **Anterior:** [[Anm_Aplicaciones_Derivada]] • **Siguiente:** [[Anm_Aplicaciones_Integral]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Integrales

## Índice

==toc==

---

> [!INFO]
> Si la derivada es "cambio instantáneo", la integral es **acumulación continua**. El Teorema Fundamental del Cálculo (TFC) conecta ambos mundos: derivar e integrar son operaciones inversas.
>
> En ingeniería: la integral es trabajo $W = \int F \, dx$, carga acumulada $Q = \int I \, dt$, centro de masa, momento de inercia, energía potencial, y mucho más.

---

## Conceptos fundamentales

### Integral indefinida

$$\int f(x) \, dx = F(x) + C \quad \text{donde} \quad F'(x) = f(x)$$

Es la **familia de primitivas** de $f$. La constante $C$ representa que cualquier constante desplaza verticalmente la primitiva.

```
     F(x) + C₁ ┐
     F(x) + C₂ ┼── Todas tienen la misma
     F(x) + C₃ ┘   derivada f(x)
```

> [!TIP] La constante C
> Siempre que resuelvas una integral indefinida, **no olvides el $+C$**. Perder la constante de integración es uno de los errores más comunes en exámenes. En problemas de valor inicial, la constante se determina con la condición dada.

### Integral definida (Riemann)

$$\int_a^b f(x) \, dx = \lim_{n \to \infty} \sum_{i=1}^n f(x_i^*) \Delta x$$

Es el **área neta** bajo la curva $f$ entre $a$ y $b$.

```
        f(x)
          ▲
          │    ┌────────────────┐
          │   ┌┘┌─────────┐┌───┘
          │  ┌┘┌┘         └┐└┐
          │ ┌┘┌┘           └┐└┐
          │┌┘┌┘             └┐└┐
          ─┴──┴───────────────┴──▶ x
           a                    b
          \____________________/
            Área ≈ Σ f(xᵢ)Δx
            Exacta cuando Δx → 0
```

> [!WARNING] Área neta vs. área total
> La integral definida da el **área neta** (positiva arriba del eje $x$, negativa abajo). Si querés el **área total** (sin signos), usá $\int_a^b |f(x)| \, dx$.

### Teorema Fundamental del Cálculo

- **Parte 1**: $\displaystyle \frac{d}{dx} \int_a^x f(t) \, dt = f(x)$
  (derivar una integral devuelve el integrando original)
- **Parte 2**: $\displaystyle \int_a^b f(x) \, dx = F(b) - F(a)$
  (la integral definida es la diferencia de primitivas en los extremos)

> [!EXAMPLE] TFC Parte 1
> Hallar $\displaystyle \frac{d}{dx} \int_0^{x^2} \sin(t^2) \, dt$.
>
> **Paso 1:** Identificar el límite superior variable.
> $F(x) = \int_0^{x^2} \sin(t^2) \, dt$
>
> **Paso 2:** Aplicar TFC Parte 1 con regla de la cadena.
> $F'(x) = \sin((x^2)^2) \cdot \frac{d}{dx}(x^2) = \sin(x^4) \cdot 2x$
>
> **Resultado:** $\displaystyle \frac{d}{dx} \int_0^{x^2} \sin(t^2) \, dt = 2x \sin(x^4)$

> [!EXAMPLE] TFC Parte 2
> Calcular $\displaystyle \int_1^2 (3x^2 + 2x) \, dx$.
>
> **Paso 1:** Hallar una primitiva.
> $\int (3x^2 + 2x) \, dx = x^3 + x^2 + C$
>
> **Paso 2:** Evaluar en los límites.
> $F(2) = 2^3 + 2^2 = 8 + 4 = 12$
> $F(1) = 1^3 + 1^2 = 1 + 1 = 2$
>
> **Resultado:** $\int_1^2 (3x^2 + 2x) \, dx = 12 - 2 = 10$.

---

## Integrales inmediatas básicas

| Integral | Resultado |
|:---------|:----------|
| $\int x^n \, dx$ | $\frac{x^{n+1}}{n+1} + C$, $n \neq -1$ |
| $\int \frac{1}{x} \, dx$ | $\ln|x| + C$ |
| $\int e^x \, dx$ | $e^x + C$ |
| $\int a^x \, dx$ | $\frac{a^x}{\ln a} + C$ |
| $\int \sin x \, dx$ | $-\cos x + C$ |
| $\int \cos x \, dx$ | $\sin x + C$ |
| $\int \sec^2 x \, dx$ | $\tan x + C$ |
| $\int \csc^2 x \, dx$ | $-\cot x + C$ |
| $\int \sec x \tan x \, dx$ | $\sec x + C$ |
| $\int \csc x \cot x \, dx$ | $-\csc x + C$ |
| $\int \frac{1}{\sqrt{1-x^2}} \, dx$ | $\arcsin x + C$ |
| $\int \frac{1}{1+x^2} \, dx$ | $\arctan x + C$ |
| $\int \frac{1}{x\sqrt{x^2-1}} \, dx$ | $\text{arcsec}\,|x| + C$ |

---

## Técnicas de integración

| Técnica | Cuándo usarla | Idea clave |
|:--------|:--------------|:-----------|
| **Sustitución simple** | $f(g(x)) \cdot g'(x)$ | $u = g(x)$, $du = g'(x)dx$ |
| **Por partes** | Producto de funciones | $\int u\,dv = uv - \int v\,du$ |
| **Fracciones simples** | $P(x)/Q(x)$, grado(P) < grado(Q) | Descomponer en fracciones parciales |
| **Sust. trigonométrica** | $\sqrt{a^2-x^2}$, $\sqrt{a^2+x^2}$, $\sqrt{x^2-a^2}$ | Usar identidades trigonométricas |
| **Sust. universal** | Integrales con seno y coseno | $t = \tan(x/2)$ |
| **Completar cuadrado** | $ax^2+bx+c$ en denominador | Completar y usar arcotangente o arcseno |

> [!EXAMPLE] Integración por sustitución simple
> Calcular $\displaystyle \int 2x \cdot e^{x^2} \, dx$.
>
> **Paso 1:** Elegir $u = g(x)$.
> $u = x^2$, entonces $du = 2x \, dx$ ✓ (está en el integrando)
>
> **Paso 2:** Reescribir la integral.
> $$\int 2x \cdot e^{x^2} \, dx = \int e^u \, du$$
>
> **Paso 3:** Integrar.
> $$\int e^u \, du = e^u + C = e^{x^2} + C$$
>
> **Resultado:** $\int 2x \cdot e^{x^2} \, dx = e^{x^2} + C$.
>
> **Verificación:** $\frac{d}{dx}(e^{x^2}) = e^{x^2} \cdot 2x$ ✓

> [!EXAMPLE] Integración por partes
> Calcular $\displaystyle \int x \cdot e^x \, dx$.
>
> **Paso 1:** Elegir $u$ y $dv$.
> LIATE: Log, Inversa, Algebraica, Trigonométrica, Exponencial.
> $u = x$ (algebraica), $dv = e^x \, dx$ (exponencial)
> $du = dx$, $v = e^x$
>
> **Paso 2:** Aplicar fórmula.
> $$\int u \, dv = uv - \int v \, du$$
> $$\int x e^x \, dx = x e^x - \int e^x \, dx$$
>
> **Paso 3:** Resolver la nueva integral.
> $$\int x e^x \, dx = x e^x - e^x + C = e^x(x - 1) + C$$
>
> **Resultado:** $\int x e^x \, dx = e^x(x - 1) + C$.
>
> > [!TIP] Regla LIATE
> > Para elegir $u$ en integración por partes, seguí este orden: **L**ogarítmicas, **I**nversas, **A**lgebraicas, **T**rigonométricas, **E**xponenciales. La que aparece primero va como $u$.

> [!EXAMPLE] Fracciones simples
> Calcular $\displaystyle \int \frac{2x+3}{x^2 - 3x + 2} \, dx$.
>
> **Paso 1:** Factorizar denominador.
> $x^2 - 3x + 2 = (x-1)(x-2)$
>
> **Paso 2:** Descomponer en fracciones simples.
> $$\frac{2x+3}{(x-1)(x-2)} = \frac{A}{x-1} + \frac{B}{x-2}$$
> $$2x+3 = A(x-2) + B(x-1)$$
>
> **Paso 3:** Hallar $A$ y $B$.
> $x=1$: $2(1)+3 = A(1-2) \Rightarrow 5 = -A \Rightarrow A = -5$
> $x=2$: $2(2)+3 = B(2-1) \Rightarrow 7 = B \Rightarrow B = 7$
>
> **Paso 4:** Integrar.
> $$\int \left(\frac{-5}{x-1} + \frac{7}{x-2}\right) dx = -5\ln|x-1| + 7\ln|x-2| + C$$
>
> **Resultado:** $\displaystyle \int \frac{2x+3}{x^2-3x+2} \, dx = \ln\left|\frac{(x-2)^7}{(x-1)^5}\right| + C$.

---

## Sustitución trigonométrica

| Expresión en el integrando | Sustitución | $dx$ | Identidad útil |
|:--------------------------|:------------|:-----|:---------------|
| $\sqrt{a^2 - x^2}$ | $x = a \sin \theta$ | $a\cos\theta\,d\theta$ | $1-\sin^2\theta = \cos^2\theta$ |
| $\sqrt{a^2 + x^2}$ | $x = a \tan \theta$ | $a\sec^2\theta\,d\theta$ | $1+\tan^2\theta = \sec^2\theta$ |
| $\sqrt{x^2 - a^2}$ | $x = a \sec \theta$ | $a\sec\theta\tan\theta\,d\theta$ | $\sec^2\theta-1 = \tan^2\theta$ |

> [!WARNING] No olvides volver a la variable original
> Después de integrar en $\theta$, tenés que **deshacer la sustitución** dibujando un triángulo rectángulo que represente la relación original.

---

## Aplicaciones en ingeniería (conexión)

| Aplicación | Expresión integral | Rama |
|:-----------|:------------------|:-----|
| Trabajo mecánico | $W = \int_{x_1}^{x_2} F(x) \, dx$ | Física/Mecánica |
| Carga en un capacitor | $Q = \int_0^t I(\tau) \, d\tau$ | Electrónica |
| Centro de masa | $\bar{x} = \frac{\int x \cdot \rho(x) \, dx}{\int \rho(x) \, dx}$ | Mecánica/Estática |
| Momento de inercia | $I = \int r^2 \, dm$ | Mecánica |
| Valor promedio | $\bar{f} = \frac{1}{b-a}\int_a^b f(x) \, dx$ | Estadística |
| Energía potencial | $U = -\int F(x) \, dx$ | Física |

---

## Tabla comparativa: derivada vs. integral

| Concepto | Derivada $d/dx$ | Integral $\int$ |
|:---------|:----------------|:----------------|
| Interpretación geométrica | Pendiente de la tangente | Área bajo la curva |
| Interpretación física | Velocidad (tasa de cambio) | Posición (acumulación) |
| Operación | Local (punto) | Global (intervalo) |
| Precisión | Instantánea | Acumulada |
| Relación | $\frac{d}{dx}\int_a^x f = f$ | $\int_a^b f' = f(b)-f(a)$ |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Apunte U5 (Ocampo) — Integrales | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 5.pdf` |
| Teoría integral indefinida (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/integral indefinida .pdf` |
| Teoría métodos de integración (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/métodos de integración .pdf` |
| Apunte Integrales (profes) | `Raw/.../AnM1/Teorías/Integrales.pdf` |
| Clase 11-5 — Integral indefinida y técnicas | `Raw/.../AnM1/Teorías/Unidad 5 Integrales/clase 11- 5-5-2026- Integral indefinida y tecnicas de integración.pdf` |
| Clase 12 — Integrales definidas | `Raw/.../AnM1/Teorías/Unidad 5 Integrales/Clase_12- 7-5-2026- Integrales_Definidas.pdf` |
| TP6 Integrales AnMat1 2026 | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TP6_Integrales_AnMat1_2026.pdf` |
| Ejercicios adicionales - Integrales (1ra parte) | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Integrales (Primera parte).pdf` |
| Tabla derivadas e integrales | `Raw/.../AnM1/Teorías/Tabla-Derivada-Integral.pdf` |
| Tabla integrales actualizada | `Raw/.../1 matematica/TEORIA/Tabla Integrales Actualizada_63edbeb899da0f577da6bfa69b07001a.pdf` |
| Hoja de Fórmulas (LaTeX) | `Raw/.../1 matematica/TEORIA/Hoja de Fórmulas (LaTeX).pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Aplicaciones_Derivada]] • **Siguiente:** [[Anm_Aplicaciones_Integral]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
