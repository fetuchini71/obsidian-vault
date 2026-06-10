> [!NOTE] Navegación
> **Anterior:** [[Anm_Extremos]] • **Siguiente:** [[Anm_Campos_Integrales_Linea]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Integrales Múltiples

## Índice

==toc==

---

> [!INFO]
> Integrar en 2D y 3D para calcular volúmenes, áreas de superficies, masa, centro de masa, momentos de inercia. Es la extensión natural de la integral de Riemann a ℝⁿ. En ingeniería: calcular el centro de gravedad de una pieza, el momento de inercia de una sección transversal, la masa de un sólido con densidad variable.

---

## Integral doble

$$ \iint_R f(x,y) \, dA = \lim_{\Delta \to 0} \sum f(x_i^*, y_j^*) \Delta A $$

- **Interpretación**: volumen bajo la superficie $z = f(x,y)$ sobre la región $R$
- Se calcula como **integral iterada** (teorema de Fubini):
  $$ \iint_R f(x,y) \, dA = \int_a^b \int_{g_1(x)}^{g_2(x)} f(x,y) \, dy \, dx $$

> [!TIP] Orden de integración
> A veces conviene integrar primero respecto a $x$ y luego a $y$, o viceversa. Cambiar el orden de integración puede transformar una integral imposible en una elemental.
>
> **Pregunta guía:** "¿La región se describe mejor con $y$ en función de $x$ o con $x$ en función de $y$?"

### Tipos de regiones

| Tipo | Descripción | Límites |
|:-----|:------------|:--------|
| **Tipo I** | $a \leq x \leq b$, $g_1(x) \leq y \leq g_2(x)$ | Integral en $y$ primero |
| **Tipo II** | $c \leq y \leq d$, $h_1(y) \leq x \leq h_2(y)$ | Integral en $x$ primero |

```
Región Tipo I:                 Región Tipo II:
y                              y
▲                              ▲
│    ┌────────────┐            │     ╱╲
│   ╱ y = g₂(x)  ╲            │    ╱  ╲
│  ╱              ╲           │   ╱    ╲
│ ╱                ╲          │  ╱ x = h₁(y) ╲
│╱ y = g₁(x)       ╲         │ ╱              ╲
│                    └─       │╱ x = h₂(y)     ╲
└───────────► x               └──────────────────► y
  a         b                    c            d
```

> [!EXAMPLE] Integral doble básica
> Calcular $\iint_R (x + 2y) \, dA$ donde $R$ es el rectángulo $[0,2] \times [0,1]$.
>
> **Solución:**
> $\displaystyle \iint_R (x+2y) \, dA = \int_0^2 \int_0^1 (x+2y) \, dy \, dx$
>
> Primero integramos en $y$:
> $\displaystyle \int_0^1 (x+2y) \, dy = [xy + y^2]_0^1 = x + 1$
>
> Luego en $x$:
> $\displaystyle \int_0^2 (x+1) \, dx = \left[\frac{x^2}{2} + x\right]_0^2 = 2 + 2 = 4$
>
> **Interpretación:** el volumen bajo $z = x + 2y$ sobre el rectángulo es 4 unidades cúbicas.

> [!EXAMPLE] Cambiar orden de integración
> Calcular $\displaystyle \int_0^1 \int_{x^2}^x (x+y) \, dy \, dx$.
>
> **Solución:**
> Primero en $y$: $\int_{x^2}^x (x+y) \, dy = \left[xy + \frac{y^2}{2}\right]_{x^2}^x = (x^2 + \frac{x^2}{2}) - (x\cdot x^2 + \frac{x^4}{2})$
> $= \frac{3x^2}{2} - (x^3 + \frac{x^4}{2})$
>
> Luego en $x$: $\int_0^1 \left(\frac{3x^2}{2} - x^3 - \frac{x^4}{2}\right) dx = \left[\frac{x^3}{2} - \frac{x^4}{4} - \frac{x^5}{10}\right]_0^1$
> $= \frac{1}{2} - \frac{1}{4} - \frac{1}{10} = \frac{10-5-2}{20} = \frac{3}{20}$
>
> **Alternativa** (cambiando orden): La región es $0 \leq x \leq 1$, $x^2 \leq y \leq x$. Para Tipo II: $0 \leq y \leq 1$, $y \leq x \leq \sqrt{y}$. Verificar que da el mismo resultado.

---

### Cambio de variables

**Coordenadas polares**: $dA = r \, dr \, d\theta$

$$ \iint_R f(x,y) \, dA = \iint_{R'} f(r\cos\theta, r\sin\theta) \, r \, dr \, d\theta $$

> [!TIP] Cuándo usar polares en integrales dobles
> Usá coordenadas polares cuando la región o el integrando contenga $x^2 + y^2$. Ejemplos típicos:
> - Región: círculo, anillo, cardioide, sector circular
> - Integrando: $e^{-(x^2+y^2)}$, $\sqrt{x^2+y^2}$, $\frac{1}{x^2+y^2}$

> [!EXAMPLE] Integral en polares
> Calcular $\iint_R e^{-(x^2+y^2)} \, dA$ donde $R$ es el disco $x^2 + y^2 \leq a^2$.
>
> **Solución:**
> En polares: $x^2 + y^2 = r^2$, $dA = r\,dr\,d\theta$, $0 \leq r \leq a$, $0 \leq \theta \leq 2\pi$.
>
> $\displaystyle \iint_R e^{-(x^2+y^2)} \, dA = \int_0^{2\pi} \int_0^a e^{-r^2} r \, dr \, d\theta$
>
> $\displaystyle = \int_0^{2\pi} \left[-\frac{1}{2}e^{-r^2}\right]_0^a d\theta = \int_0^{2\pi} \frac{1}{2}(1 - e^{-a^2}) \, d\theta$
>
> $\displaystyle = \pi(1 - e^{-a^2})$
>
> **Nota:** esta integral es famosa porque en cartesianas no tiene primitiva elemental (la función error). En polares se vuelve trivial.
>
> Para $a \to \infty$: $\displaystyle \iint_{\mathbb{R}^2} e^{-(x^2+y^2)} \, dA = \pi \quad \Rightarrow \quad \int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$ (integral gaussiana).

---

## Integral triple

$$ \iiint_V f(x,y,z) \, dV $$

- **Coordenadas cilíndricas**: $dV = r \, dr \, d\theta \, dz$
- **Coordenadas esféricas**: $dV = \rho^2 \sin\phi \, d\rho \, d\theta \, d\phi$

### Jacobiano

Al cambiar variables $(x,y) \to (u,v)$:

$$ dA = |J(u,v)| \, du \, dv \quad \text{donde} \quad J = \det\begin{pmatrix} x_u & x_v \\ y_u & y_v \end{pmatrix} $$

Para integrales triples: $dV = |J(u,v,w)| \, du \, dv \, dw$

| Coordenadas | Jacobiano | $dV$ |
|:------------|:---------:|:----:|
| Polares $(r,\theta)$ | $r$ | $r\,dr\,d\theta$ |
| Cilíndricas $(r,\theta,z)$ | $r$ | $r\,dr\,d\theta\,dz$ |
| Esféricas $(\rho,\theta,\phi)$ | $\rho^2\sin\phi$ | $\rho^2\sin\phi\,d\rho\,d\theta\,d\phi$ |

> [!WARNING] No olvidar el Jacobiano
> **Error clásico:** hacer el cambio de variables y olvidar multiplicar por el Jacobiano. En polares, $dA$ NO es $dr\,d\theta$, es $r\,dr\,d\theta$. En esféricas, $dV$ NO es $d\rho\,d\theta\,d\phi$, es $\rho^2\sin\phi\,d\rho\,d\theta\,d\phi$.
>
> **Truco para recordar:** el Jacobiano es el "factor de estiramiento" del área/volumen al cambiar de coordenadas. En polares, un rectángulo $dr \times d\theta$ a distancia $r$ del origen equivale a un área $r\,dr\,d\theta$.

> [!EXAMPLE] Volumen con integral triple en cilíndricas
> Calcular el volumen del sólido limitado por $z = x^2 + y^2$ (paraboloide) y $z = 4$ (plano).
>
> **Solución:**
> El sólido está entre el paraboloide (abajo) y el plano $z=4$ (arriba).
>
> En cilíndricas: $x^2 + y^2 = r^2$, $z$ desde $r^2$ hasta $4$, $r$ desde $0$ hasta $2$ (donde $r^2 = 4$), $\theta$ de $0$ a $2\pi$.
>
> $V = \displaystyle \iiint_V dV = \int_0^{2\pi} \int_0^2 \int_{r^2}^4 r \, dz \, dr \, d\theta$
>
> $= \displaystyle \int_0^{2\pi} \int_0^2 r(4 - r^2) \, dr \, d\theta$
>
> $= \displaystyle \int_0^{2\pi} \left[2r^2 - \frac{r^4}{4}\right]_0^2 d\theta = \int_0^{2\pi} (8 - 4) \, d\theta = 4 \cdot 2\pi = 8\pi$
>
> **Verificación:** el volumen de un cilindro de radio 2 y altura 4 es $16\pi$. El paraboloide "come" la mitad del cilindro → $8\pi$. Correcto.

---

## Aplicaciones

| Magnitud | Fórmula 2D | Fórmula 3D |
|----------|-----------|-----------|
| **Masa** | $m = \iint_R \rho(x,y) \, dA$ | $m = \iiint_V \rho(x,y,z) \, dV$ |
| **Centro de masa $x$** | $\bar{x} = \frac{1}{m} \iint_R x \rho \, dA$ | $\bar{x} = \frac{1}{m} \iiint_V x \rho \, dV$ |
| **Centro de masa $y$** | $\bar{y} = \frac{1}{m} \iint_R y \rho \, dA$ | $\bar{y} = \frac{1}{m} \iiint_V y \rho \, dV$ |
| **Momento inercia $I_x$** | $I_x = \iint_R y^2 \rho \, dA$ | $I_x = \iiint_V (y^2+z^2) \rho \, dV$ |
| **Volumen** | $V = \iint_R 1 \, dA$ | $V = \iiint_V 1 \, dV$ |
| **Área superficial** | — | $A(S) = \iint_D \|\mathbf{r}_u \times \mathbf{r}_v\| \, dA$ |

> [!EXAMPLE] Centro de masa de una lámina
> Hallar el centro de masa de la lámina semicircular $x^2 + y^2 \leq a^2$, $y \geq 0$, con densidad $\rho(x,y) = y$.
>
> **Solución:**
>
> **Paso 1** — Masa:
> En polares: $x = r\cos\theta$, $y = r\sin\theta$, $\rho = r\sin\theta$, $0 \leq r \leq a$, $0 \leq \theta \leq \pi$.
>
> $m = \iint_R y \, dA = \int_0^\pi \int_0^a (r\sin\theta) \, r \, dr \, d\theta = \int_0^\pi \sin\theta \, d\theta \int_0^a r^2 \, dr$
>
> $m = [-\cos\theta]_0^\pi \cdot \left[\frac{r^3}{3}\right]_0^a = (1+1) \cdot \frac{a^3}{3} = \frac{2a^3}{3}$
>
> **Paso 2** — Momentos:
> $M_x = \iint_R y \cdot \rho \, dA = \iint_R y^2 \, dA = \int_0^\pi \int_0^a r^2\sin^2\theta \cdot r \, dr \, d\theta$
> $= \int_0^\pi \sin^2\theta \, d\theta \int_0^a r^3 \, dr = \int_0^\pi \frac{1-\cos 2\theta}{2} \, d\theta \cdot \frac{a^4}{4}$
> $= \frac{\pi}{2} \cdot \frac{a^4}{4} = \frac{\pi a^4}{8}$
>
> $M_y = \iint_R x \cdot \rho \, dA = \iint_R xy \, dA = \int_0^\pi \int_0^a r\cos\theta \cdot r\sin\theta \cdot r \, dr \, d\theta$
> $= \int_0^\pi \sin\theta\cos\theta \, d\theta \int_0^a r^3 \, dr = \frac{1}{2}\int_0^\pi \sin 2\theta \, d\theta \cdot \frac{a^4}{4} = 0$
>
> **Paso 3** — Centro de masa:
> $\bar{x} = M_y/m = 0$ (simetría)
> $\bar{y} = M_x/m = \frac{\pi a^4/8}{2a^3/3} = \frac{3\pi a}{16}$

---

## Conexiones con otras áreas

- **[[Anm_Extremos]]**: optimización de integrales (cálculo de variaciones)
- **[[Anm_Campos_Integrales_Linea]]**: teorema de Green conecta integrales dobles con integrales de línea
- **[[Anm_Integrales_Superficie]]**: integrales triples para flujo, teorema de Gauss
- **[[Anm_Aplicaciones_Integral]]** (Análisis I): sólidos de revolución son un caso particular
- **[[Eje_Fisica]]**: momento de inercia, centro de masa, campo gravitatorio
- **Probabilidad**: integrales dobles/triples para normalizar densidades conjuntas

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Clase 7 — Integrales Dobles (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 7-ING-Integrales Dobles_...pdf` |
| Clase 8 — Integrales Triples (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 8-ING-Integrales Triples_...pdf` |
| Integrales dobles (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Integrales doble.pdf` |
| Integrales dobles (Allmang ING2024) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Integrales Dobles ING2024.pdf` |
| Integrales triples 1 | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Integrales triples 1.pdf` |
| Integrales triples (ING2024) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Integrales Triples ING2024.pdf` |
| U7 Integrales dobles (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U7 integrales dobles.pdf` |
| U8 Integrales triples (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U8 integrales triples.pdf` |
| TP8 Coord. Polares — Integrales Dobles | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP8 Coord. Polares - Integrales Dobles.pdf` |
| TP9 Integrales Triples | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP9 Integrales Triples.pdf` |
| Solucionario TP2 (práctica) | `Raw/.../1 matematica/PRACTICA/Análisis matemático I/TP/solucionario_tp_2.pdf` |

---

## Ejercicios modelados

1. **Integral doble**: $\iint_R (x^2 + y) \, dA$ donde $R$ está limitado por $y = x^2$ e $y = 2x$.
2. **Cambio de orden**: Re-escribir $\int_0^1 \int_0^{\sqrt{y}} f(x,y) \, dx \, dy$ cambiando el orden.
3. **Polares**: $\iint_R \sqrt{x^2 + y^2} \, dA$ donde $R$ es el anillo $1 \leq x^2 + y^2 \leq 4$.
4. **Integral triple**: $\iiint_V z \, dV$ donde $V$ es el tetraedro con vértices $(0,0,0)$, $(1,0,0)$, $(0,1,0)$, $(0,0,1)$.
5. **Esféricas**: Volumen de la esfera $x^2 + y^2 + z^2 \leq a^2$ (verificar que da $\frac{4}{3}\pi a^3$).
6. **Centro de masa**: Lámina triangular con vértices $(0,0)$, $(2,0)$, $(0,1)$, densidad $\rho(x,y) = x$.

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Extremos]] • **Siguiente:** [[Anm_Campos_Integrales_Linea]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
