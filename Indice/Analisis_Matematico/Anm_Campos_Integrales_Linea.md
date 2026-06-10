> [!NOTE] Navegación
> **Anterior:** [[Anm_Integrales_Multiples]] • **Siguiente:** [[Anm_Integrales_Superficie]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Campos Vectoriales e Integrales de Línea

## Índice

==toc==

---

> [!INFO]
> Los campos vectoriales modelan **fuerzas, velocidades y flujos** en el espacio. Las integrales de línea miden **trabajo** (cuánto "empuja" un campo a lo largo de un camino). El teorema de Green conecta esto con las integrales dobles. En ingeniería: trabajo realizado por una fuerza variable a lo largo de una trayectoria, circulación de un fluido, campo eléctrico alrededor de un conductor.

---

## Campos vectoriales

Un **campo vectorial** en ℝ² ó ℝ³ asigna un vector a cada punto:

$$ \mathbf{F}(x,y) = (P(x,y), Q(x,y)) $$

**Ejemplos físicos**:
- **Campo gravitatorio**: $\mathbf{F}(x,y,z) = -\frac{GMm}{r^2} \hat{\mathbf{r}}$ (atracción radial)
- **Campo eléctrico** de una carga puntual: $\mathbf{E} = \frac{kq}{r^2} \hat{\mathbf{r}}$
- **Campo de velocidades** de un fluido: $\mathbf{v}(x,y,z)$
- **Campo de fuerzas** en un resorte 2D: $\mathbf{F} = -k(x,y)$

```
Campo radial F(x,y) = (x,y):        Campo rotacional F(x,y) = (-y,x):
      y                                y
      ▲                                ▲
      │  ↑↗→→↘↓                       │  ←←←↑
      │  ↑↑→•→↓↓                       │  ←←•→→
      │  ↑↖←←↘↓                       │  ↓→→→↑
      └──────────► x                   └──────────► x
```

> [!TIP] Visualizar campos vectoriales
> Para entender un campo, dibujá algunos vectores representativos o usá la idea de "flujo": ¿el campo apunta hacia adentro o hacia afuera de un punto? (divergencia) ¿Tiende a rotar alrededor de un punto? (rotor).

---

## Integral de línea de un campo escalar

$$ \int_C f(x,y) \, ds = \int_a^b f(x(t), y(t)) \, \sqrt{(x'(t))^2 + (y'(t))^2} \, dt $$

**Interpretación**: masa de un alambre con densidad $f$, área de una "cerca" sobre la curva $C$ con altura $f$.

> [!EXAMPLE] Masa de un alambre
> Hallar la masa de un alambre con forma de hélice $\mathbf{r}(t) = (\cos t, \sin t, t)$, $t \in [0, 2\pi]$, si la densidad lineal es $\rho(x,y,z) = z$.
>
> **Solución:**
> $\mathbf{r}'(t) = (-\sin t, \cos t, 1)$
> $\|\mathbf{r}'(t)\| = \sqrt{(-\sin t)^2 + (\cos t)^2 + 1^2} = \sqrt{2}$
> $\rho(\mathbf{r}(t)) = t$
>
> $m = \int_C \rho \, ds = \int_0^{2\pi} t \cdot \sqrt{2} \, dt = \sqrt{2}\left[\frac{t^2}{2}\right]_0^{2\pi} = \sqrt{2} \cdot 2\pi^2 = 2\sqrt{2}\pi^2$

---

## Integral de línea de un campo vectorial

$$ \int_C \mathbf{F} \cdot d\mathbf{r} = \int_a^b \mathbf{F}(\mathbf{r}(t)) \cdot \mathbf{r}'(t) \, dt $$

**Interpretación**: **trabajo** realizado por el campo $\mathbf{F}$ a lo largo de la curva $C$.

> [!WARNING] Orientación importa
> La integral de línea de un campo vectorial **cambia de signo** si recorrés la curva en sentido contrario:
> $$ \int_{-C} \mathbf{F} \cdot d\mathbf{r} = -\int_C \mathbf{F} \cdot d\mathbf{r} $$
> Esto NO pasa con la integral de línea de un campo escalar ($\int_C f \, ds$ es independiente de la orientación).

> [!EXAMPLE] Trabajo de un campo de fuerza
> Calcular el trabajo realizado por $\mathbf{F}(x,y) = (xy, x+y)$ a lo largo de la curva $C$: $\mathbf{r}(t) = (t, t^2)$ con $t \in [0, 1]$.
>
> **Solución:**
> $\mathbf{r}(t) = (t, t^2)$, $\mathbf{r}'(t) = (1, 2t)$
> $\mathbf{F}(\mathbf{r}(t)) = (t \cdot t^2, t + t^2) = (t^3, t + t^2)$
>
> $\displaystyle W = \int_0^1 (t^3, t + t^2) \cdot (1, 2t) \, dt$
> $\displaystyle = \int_0^1 (t^3 + 2t(t + t^2)) \, dt = \int_0^1 (t^3 + 2t^2 + 2t^3) \, dt$
> $\displaystyle = \int_0^1 (3t^3 + 2t^2) \, dt = \left[\frac{3t^4}{4} + \frac{2t^3}{3}\right]_0^1 = \frac{3}{4} + \frac{2}{3} = \frac{17}{12}$
>
> El trabajo realizado es $\frac{17}{12}$ unidades de energía.

---

## Campos conservativos y funciones potenciales

$\mathbf{F}$ es **conservativo** si $\mathbf{F} = \nabla \phi$ para alguna función potencial $\phi$.

**Propiedades equivalentes:**
- $\oint_C \mathbf{F} \cdot d\mathbf{r} = 0$ para toda curva cerrada $C$
- La integral de línea **no depende del camino**, solo de los puntos inicial y final: $\int_C \mathbf{F} \cdot d\mathbf{r} = \phi(B) - \phi(A)$
- En ℝ²: $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$ (condición necesaria y suficiente si el dominio es simplemente conexo)

| Propiedad | Campo conservativo | Campo no conservativo |
|:----------|:------------------:|:---------------------:|
| Dependencia del camino | No depende | Sí depende |
| Integral en lazo cerrado | Cero | Puede ser ≠ 0 |
| Existe potencial $\phi$ | Sí | No |
| $\nabla \times \mathbf{F}$ | $\mathbf{0}$ | ≠ $\mathbf{0}$ |

> [!TIP] Cómo verificar si un campo es conservativo
> **En ℝ²:** calcular $\partial P/\partial y$ y $\partial Q/\partial x$. Si son iguales y el dominio es simplemente conexo (sin agujeros), el campo es conservativo.
>
> **En ℝ³:** calcular $\nabla \times \mathbf{F}$. Si es $\mathbf{0}$ y el dominio es simplemente conexo, es conservativo.
>
> Para hallar el potencial $\phi$, integrá $P$ respecto a $x$ (sumando una función $g(y)$), luego derivá respecto a $y$ e igualá a $Q$ para encontrar $g(y)$.

> [!EXAMPLE] Campo conservativo — hallar el potencial
> Verificar que $\mathbf{F}(x,y) = (2xy, x^2 + \cos y)$ es conservativo y hallar su función potencial.
>
> **Solución:**
>
> **Paso 1** — Verificar: $P = 2xy$, $Q = x^2 + \cos y$
> $\frac{\partial P}{\partial y} = 2x$, $\frac{\partial Q}{\partial x} = 2x$ ✓ Es conservativo.
>
> **Paso 2** — Hallar $\phi$:
> $\frac{\partial \phi}{\partial x} = 2xy \Rightarrow \phi(x,y) = \int 2xy \, dx = x^2y + g(y)$
> $\frac{\partial \phi}{\partial y} = x^2 + g'(y) = x^2 + \cos y \Rightarrow g'(y) = \cos y \Rightarrow g(y) = \sin y + C$
>
> **Paso 3** — Potencial: $\phi(x,y) = x^2y + \sin y + C$
>
> **Verificación:** $\nabla \phi = (2xy, x^2 + \cos y) = \mathbf{F}$ ✓
>
> **Aplicación:** $\int_C \mathbf{F} \cdot d\mathbf{r} = \phi(B) - \phi(A)$. Por ejemplo, de $(0,0)$ a $(1,\pi)$: $\phi(1,\pi) - \phi(0,0) = (1^2 \cdot \pi + \sin\pi) - (0) = \pi$.

---

## Teorema de Green

Conecta una integral de línea sobre una curva cerrada con una integral doble sobre la región que encierra:

$$ \oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_R \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) \, dA $$

**Forma alternativa (flujo):**
$$ \oint_C \mathbf{F} \cdot \mathbf{n} \, ds = \iint_R \left( \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} \right) \, dA $$

```
Teorema de Green:
                                   
    ∮ F·dr = ∬ (Q_x - P_y) dA     
                                    
    y                               
    ▲                               
    │    ┌──────────────────┐       
    │   ╱       R          ╱│       
    │  ╱  ∬ (Q_x-P_y) dA ╱ │       
    │ ╱                  ╱  │       
    │╱ C (frontera)     ╱   │       
    │                   ╲   │       
    │                    ╲  │       
    │                     ╲ │       
    │                      ╲│       
    └──────────────────────────► x   
       ∮ F·dr a lo largo de C       
```

> [!EXAMPLE] Aplicar Green
> Calcular $\oint_C \mathbf{F} \cdot d\mathbf{r}$ donde $\mathbf{F} = (-y, x)$ y $C$ es la circunferencia $x^2 + y^2 = 1$ orientada positivamente.
>
> **Solución:**
>
> **Método directo:** Parametrizar $C$: $\mathbf{r}(t) = (\cos t, \sin t)$, $t \in [0, 2\pi]$
> $\mathbf{F}(\mathbf{r}(t)) = (-\sin t, \cos t)$, $\mathbf{r}'(t) = (-\sin t, \cos t)$
> $\displaystyle \oint_C \mathbf{F} \cdot d\mathbf{r} = \int_0^{2\pi} (-\sin t)(-\sin t) + (\cos t)(\cos t) \, dt = \int_0^{2\pi} (\sin^2 t + \cos^2 t) \, dt = 2\pi$
>
> **Con Green:** $P = -y$, $Q = x$
> $\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = 1 - (-1) = 2$
> $\displaystyle \oiint_R 2 \, dA = 2 \cdot \text{área}(R) = 2 \cdot \pi(1)^2 = 2\pi$ ✓
>
> **Interpretación física:** la circulación de $\mathbf{F} = (-y, x)$ alrededor de la circunferencia es $2\pi$, que es el flujo del rotor ($\nabla \times \mathbf{F} = 2\hat{\mathbf{k}}$) a través del disco.

> [!WARNING] Condiciones de Green
> **Ojo:** Green requiere que $P$, $Q$ y sus derivadas parciales sean continuas en toda la región $R$. Si hay un punto donde no son continuas (ej: $\mathbf{F} = \left(\frac{-y}{x^2+y^2}, \frac{x}{x^2+y^2}\right)$ en el origen), no podés aplicar Green directamente en una región que contenga ese punto. En ese caso, rodeás la singularidad con un círculo pequeño y aplicás Green en la región con el agujero.

---

## Aplicaciones en ingeniería

| Contexto | Campo $\mathbf{F}$ | Integral de línea mide |
|:---------|:-------------------|:-----------------------|
| **Mecánica** | Fuerza $\mathbf{F}$ | Trabajo $W = \int_C \mathbf{F} \cdot d\mathbf{r}$ |
| **Termodinámica** | Gradiente de temperatura | Flujo de calor |
| **Electrostática** | Campo eléctrico $\mathbf{E}$ | Diferencia de potencial $V_B - V_A = -\int_C \mathbf{E} \cdot d\mathbf{r}$ |
| **Mecánica de fluidos** | Velocidad $\mathbf{v}$ | Circulación $\Gamma = \oint_C \mathbf{v} \cdot d\mathbf{r}$ |
| **Electromagnetismo** | Campo magnético $\mathbf{B}$ | Ley de Ampère: $\oint \mathbf{B} \cdot d\mathbf{r} = \mu_0 I$ |

---

## Conexiones con otras áreas

- **[[Anm_Integrales_Multiples]]**: Green conecta integrales de línea con integrales dobles
- **[[Anm_Integrales_Superficie]]**: Stokes es la versión 3D de Green; Gauss conecta flujo y divergencia
- **[[Anm_Derivadas_Parciales]]**: rotor $(\partial Q/\partial x - \partial P/\partial y)$ son derivadas parciales
- **[[Eje_Fisica]]**: campos conservativos = fuerzas conservativas (gravedad, electrostática); trabajo = variación de energía potencial
- **[[Ecuaciones Diferenciales]]**: las ecuaciones diferenciales exactas son campos conservativos en el plano $(x,y)$

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Clase 9 — Campos vectoriales (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 9-ING-Campos vectoriales_...pdf` |
| Clase 10 — Integrales de línea (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 10-ING-Integrales de línea_...pdf` |
| Clase 11 — Green (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 11-ING-Green_...pdf` |
| ING 2024 3 — Campos (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/ING 2024 3-Campos.pdf` |
| U9 Campos vectoriales (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U9 Campos vectoriales.pdf` |
| U10 Integrales de línea (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U10 Integrales de línea.pdf` |
| U11 Teorema de Green (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U11 Teorema de Green.pdf` |
| TP10 Integrales de Línea | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP10 Integrales de Linea.pdf` |

---

## Ejercicios modelados

1. **Campo conservativo**: Verificar si $\mathbf{F} = (y^2, 2xy + e^y)$ es conservativo. Hallar el potencial si lo es.
2. **Trabajo**: Calcular el trabajo de $\mathbf{F} = (x, y)$ a lo largo de $y = x^2$ desde $(0,0)$ hasta $(1,1)$.
3. **Green**: Usar el teorema de Green para calcular $\oint_C (x^2y \, dx + xy^2 \, dy)$ donde $C$ es el cuadrado $[0,1] \times [0,1]$ orientado positivamente.
4. **Independencia del camino**: Calcular $\int_C (2x\sin y \, dx + x^2\cos y \, dy)$ de $(0,0)$ a $(2,\pi/2)$ usando el potencial.
5. **Aplicación flujo**: Usar la forma de flujo de Green para calcular el flujo de $\mathbf{F} = (x, y)$ a través de la circunferencia $x^2 + y^2 = 1$.

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Integrales_Multiples]] • **Siguiente:** [[Anm_Integrales_Superficie]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
