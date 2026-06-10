> [!NOTE] Navegación
> **Anterior:** [[Anm_Integrales_Superficie]] • **Siguiente:** [[Anm_Transformada_Laplace]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.
>
> ⚠️ **Requisito**: manejo sólido de integrales, derivadas y álgebra lineal (autovalores).

# Ecuaciones Diferenciales

## Índice

==toc==

---

> [!INFO]
> Las ecuaciones diferenciales son el **lenguaje de la física y la ingeniería**. Casi toda ley física se expresa como una relación entre una función y sus derivadas: $F = ma$ es una EDO de 2° orden, la conducción de calor es una EDP.
> *"Dios no escribió las leyes del universo en ecuaciones algebraicas, las escribió en ecuaciones diferenciales."*

---

## Conceptos básicos

- **EDO** (Ecuación Diferencial Ordinaria): involucra derivadas respecto a **una** variable independiente
- **EDP** (Ecuación en Derivadas Parciales): involucra derivadas parciales respecto a **varias** variables
- **Orden**: el de la derivada más alta
- **Lineal**: $a_n(x)y^{(n)} + \dots + a_1(x)y' + a_0(x)y = g(x)$
- **Homogénea**: $g(x) = 0$
- **Autónoma**: la variable independiente no aparece explícitamente, $y^{(n)} = f(y, y', \dots, y^{(n-1)})$
- **Solución general vs. particular**: la general contiene constantes arbitrarias; la particular se obtiene con condiciones iniciales (C.I.)

> [!TIP] Estrategia de clasificación
> Antes de resolver, **identificar el tipo** de EDO. Seguir este árbol de decisión:
> ```
> ┌─ ¿Es de 1er orden? ──── ¿Lineal? ── Sí → Factor integrante
> │                                       No → ¿Separable? → Separación
> │                                              ¿Exacta? → Diferencial exacta
> │                                              ¿Bernoulli? → Sustitución
> │                                              ¿Homogénea? → v = y/x
> │
> └─ ¿Es 2° orden o mayor? ─ ¿Coef. constantes? ─→ Ec. característica
>                                          No → Series / Frobenius
> ```

---

## EDO de primer orden

| Tipo | Forma | Método |
|------|-------|--------|
| **Variables separables** | $y' = f(x)g(y)$ | $\int \frac{dy}{g(y)} = \int f(x) dx$ |
| **Lineal** | $y' + P(x)y = Q(x)$ | Factor integrante $\mu = e^{\int P dx}$ |
| **Exacta** | $M dx + N dy = 0$, $M_y = N_x$ | Encontrar $F$ tal que $F_x = M$, $F_y = N$ |
| **Bernoulli** | $y' + P(x)y = Q(x)y^n$ | Sustitución $u = y^{1-n}$ |
| **Homogénea** | $y' = f(y/x)$ | Sustitución $v = y/x$ |

> [!EXAMPLE] 📐 Variables separables
> Resolver $y' = 2xy$, con $y(0) = 3$.
>
> **Paso 1**: Escribir como $\frac{dy}{dx} = 2xy$
>
> **Paso 2**: Separar: $\frac{dy}{y} = 2x\,dx$
>
> **Paso 3**: Integrar ambos lados:
> $$\int \frac{dy}{y} = \int 2x\,dx \implies \ln|y| = x^2 + C$$
>
> **Paso 4**: Despejar $y$:
> $$y = e^{x^2 + C} = C_1 e^{x^2}$$
>
> **Paso 5**: Aplicar $y(0)=3$: $3 = C_1 e^0 \implies C_1 = 3$
>
> **Solución**: $y(x) = 3e^{x^2}$

> [!EXAMPLE] 📐 Factor integrante (EDO lineal)
> Resolver $y' + 2y = e^{-x}$, $y(0) = 1$.
>
> **Paso 1**: Identificar $P(x)=2$, $Q(x)=e^{-x}$
>
> **Paso 2**: Factor integrante $\mu = e^{\int 2\,dx} = e^{2x}$
>
> **Paso 3**: Multiplicar la EDO por $\mu$:
> $$e^{2x}y' + 2e^{2x}y = e^{2x}e^{-x} = e^{x}$$
>
> **Paso 4**: Notar que $(e^{2x}y)' = e^{2x}y' + 2e^{2x}y$, entonces:
> $$(e^{2x}y)' = e^{x}$$
>
> **Paso 5**: Integrar: $e^{2x}y = \int e^{x}\,dx = e^{x} + C$
>
> **Paso 6**: Despejar: $y = e^{-x} + Ce^{-2x}$
>
> **Paso 7**: Usar $y(0)=1$: $1 = 1 + C \implies C = 0$
>
> **Solución**: $y(x) = e^{-x}$

> [!EXAMPLE] 📐 EDO exacta
> Resolver $(2xy + 1)dx + (x^2 + 2y)dy = 0$.
>
> **Paso 1**: Verificar exactitud: $M = 2xy + 1$, $N = x^2 + 2y$
> $$\frac{\partial M}{\partial y} = 2x, \quad \frac{\partial N}{\partial x} = 2x \quad \checkmark$$
>
> **Paso 2**: Hallar $F(x,y)$ tal que $F_x = M$:
> $$F = \int (2xy + 1)\,dx = x^2y + x + h(y)$$
>
> **Paso 3**: Derivar respecto a $y$ e igualar a $N$:
> $$\frac{\partial F}{\partial y} = x^2 + h'(y) = x^2 + 2y \implies h'(y) = 2y \implies h(y) = y^2$$
>
> **Solución implícita**: $x^2y + x + y^2 = C$

> [!WARNING] ❌ Errores comunes en EDO de 1er orden
> - **Olvidar la constante de integración**: siempre agregar $+C$ al integrar
> - **Separación incorrecta**: asegurarse de separar completamente $y$ de $x$ (un lado solo $y$, el otro solo $x$)
> - **Factor integrante**: no olvidar el factor $\mu$ en el lado derecho al multiplicar
> - **Exactitud**: verificar $M_y = N_x$ **antes** de empezar a integrar
> - **Condición inicial**: aplicarla siempre al **final**, después de obtener la solución general

---

## EDO lineales de orden superior

### Homogéneas con coeficientes constantes

$$ay'' + by' + cy = 0$$

Ecuación característica: $ar^2 + br + c = 0$

| Raíces | Solución general |
|--------|-----------------|
| Reales distintas $r_1 \neq r_2$ | $y = C_1 e^{r_1 x} + C_2 e^{r_2 x}$ |
| Raíz real doble $r$ | $y = (C_1 + C_2 x)e^{rx}$ |
| Complejas $r = \alpha \pm \beta i$ | $y = e^{\alpha x}(C_1 \cos\beta x + C_2 \sin\beta x)$ |

### Orden superior ($n$-ésimo orden)

$$a_n y^{(n)} + a_{n-1} y^{(n-1)} + \dots + a_1 y' + a_0 y = 0$$

Ecuación característica: $a_n r^n + a_{n-1} r^{n-1} + \dots + a_1 r + a_0 = 0$

Cada raíz $r_k$ aporta:
- **Real simple**: $e^{r_k x}$
- **Real múltiple** (multiplicidad $m$): $e^{r_k x}, x e^{r_k x}, \dots, x^{m-1} e^{r_k x}$
- **Par complejo** $\alpha \pm \beta i$ simple: $e^{\alpha x}\cos\beta x$, $e^{\alpha x}\sin\beta x$
- **Par complejo múltiple**: agregar $x, x^2, \dots$ multiplicando

### Independencia lineal y Wronskiano

Dos funciones $f$ y $g$ son linealmente independientes si el Wronskiano es distinto de cero:

$$W(f,g) = \begin{vmatrix} f & g \\ f' & g' \end{vmatrix} = fg' - f'g \neq 0$$

> [!TIP] Verificación de soluciones
> Siempre verificar que las soluciones obtenidas forman un **conjunto fundamental** chequeando que el Wronskiano sea no nulo.

> [!EXAMPLE] 📐 EDO homogénea de 2° orden
> Resolver $y'' + 4y' + 13y = 0$, $y(0)=1$, $y'(0) = -2$.
>
> **Paso 1**: Ecuación característica: $r^2 + 4r + 13 = 0$
>
> **Paso 2**: Raíces: $r = \frac{-4 \pm \sqrt{16 - 52}}{2} = \frac{-4 \pm \sqrt{-36}}{2} = -2 \pm 3i$
>
> **Paso 3**: Solución general ($\alpha=-2$, $\beta=3$):
> $$y = e^{-2x}(C_1 \cos 3x + C_2 \sin 3x)$$
>
> **Paso 4**: Aplicar $y(0)=1$: $1 = e^{0}(C_1 \cdot 1 + C_2 \cdot 0) \implies C_1 = 1$
>
> **Paso 5**: Derivar: $y' = -2e^{-2x}(\cos 3x + C_2 \sin 3x) + e^{-2x}(-3\sin 3x + 3C_2 \cos 3x)$
>
> **Paso 6**: Aplicar $y'(0) = -2$: $-2 = -2(1) + 3C_2 \implies 3C_2 = 0 \implies C_2 = 0$
>
> **Solución**: $y(x) = e^{-2x}\cos 3x$

### No homogéneas

$$a_n y^{(n)} + \dots + a_1 y' + a_0 y = g(x)$$

**Solución**: $y = y_h + y_p$

| Método | Cuándo usarlo | Cómo funciona |
|--------|--------------|--------------|
| **Coeficientes indeterminados** | $g(x)$ es polinomio, exponencial, seno/coseno, o suma/producto | Proponer $y_p$ con la misma forma que $g(x)$ y ajustar constantes |
| **Variación de parámetros** | **Cualquier** $g(x)$ (no requiere forma especial) | $y_p = y_1\int\frac{-y_2 g}{W}dx + y_2\int\frac{y_1 g}{W}dx$ |

> [!WARNING] ❌ Coeficientes indeterminados — términos repetidos
> Si el término propuesto para $y_p$ ya aparece en $y_h$, multiplicar por $x$ (o $x^2$, $x^3$...) hasta que sea linealmente independiente. **Olvidar esto es el error más común en EDO no homogéneas.**

> [!EXAMPLE] 📐 Coeficientes indeterminados
> Resolver $y'' - 3y' + 2y = 4x^2$.
>
> **Paso 1**: Homogénea: $r^2 - 3r + 2 = 0 \implies r_1=1, r_2=2$
> $$y_h = C_1 e^{x} + C_2 e^{2x}$$
>
> **Paso 2**: Como $g(x)=4x^2$ (polinomio de grado 2), proponer:
> $$y_p = Ax^2 + Bx + C$$
>
> **Paso 3**: Derivar: $y_p' = 2Ax + B$, $y_p'' = 2A$
>
> **Paso 4**: Sustituir en la EDO:
> $$2A - 3(2Ax + B) + 2(Ax^2 + Bx + C) = 4x^2$$
> $$2Ax^2 + (-6A + 2B)x + (2A - 3B + 2C) = 4x^2$$
>
> **Paso 5**: Igualar coeficientes:
> $$2A = 4 \implies A = 2$$
> $$-6A + 2B = 0 \implies -12 + 2B = 0 \implies B = 6$$
> $$2A - 3B + 2C = 0 \implies 4 - 18 + 2C = 0 \implies C = 7$$
>
> **Paso 6**: Solución general: $y = C_1 e^{x} + C_2 e^{2x} + 2x^2 + 6x + 7$

> [!EXAMPLE] 📐 Variación de parámetros
> Resolver $y'' + y = \sec x$.
>
> **Paso 1**: Homogénea: $r^2 + 1 = 0 \implies r = \pm i$
> $$y_h = C_1 \cos x + C_2 \sin x$$
>
> **Paso 2**: Soluciones fundamentales: $y_1 = \cos x$, $y_2 = \sin x$
>
> **Paso 3**: Wronskiano: $W = \cos x \cdot \cos x - (-\sin x) \cdot \sin x = \cos^2 x + \sin^2 x = 1$
>
> **Paso 4**: Solución particular:
> $$y_p = \cos x \int \frac{-\sin x \cdot \sec x}{1}dx + \sin x \int \frac{\cos x \cdot \sec x}{1}dx$$
> $$y_p = -\cos x \int \frac{\sin x}{\cos x}dx + \sin x \int 1\,dx$$
> $$y_p = -\cos x \int \tan x\,dx + \sin x \cdot x$$
> $$y_p = -\cos x \cdot (-\ln|\cos x|) + x\sin x$$
> $$y_p = \cos x \ln|\cos x| + x\sin x$$
>
> **Solución general**: $y = C_1 \cos x + C_2 \sin x + \cos x \ln|\cos x| + x\sin x$

---

## Métodos avanzados

### Solución por series de potencias

Para EDO con coeficientes variables donde los métodos anteriores no funcionan:

$$y'' + P(x)y' + Q(x)y = 0$$

Se propone $y = \sum_{n=0}^\infty a_n (x - x_0)^n$, se sustituye término a término y se igualan coeficientes.

> [!EXAMPLE] 📐 Series alrededor de $x_0=0$
> Resolver $y'' + x y' + y = 0$ por series.
>
> Sea $y = \sum_{n=0}^\infty a_n x^n$, $y' = \sum_{n=1}^\infty n a_n x^{n-1}$, $y'' = \sum_{n=2}^\infty n(n-1)a_n x^{n-2}$.
>
> Sustituyendo y reagrupando: $\sum_{n=0}^\infty [(n+2)(n+1)a_{n+2} + (n+1)a_n] x^n = 0$
>
> Relación de recurrencia: $a_{n+2} = -\frac{a_n}{n+2}$
>
> Solución general: $y = a_0\left(1 - \frac{x^2}{2} + \frac{x^4}{8} - \dots\right) + a_1\left(x - \frac{x^3}{3} + \frac{x^5}{15} - \dots\right)$

### Método de Frobenius (puntos singulares regulares)

Cuando $x_0$ es un punto singular regular, se busca $y = \sum_{n=0}^\infty a_n (x-x_0)^{n+r}$, donde $r$ satisface la **ecuación indicial**.

---

## Sistemas de EDO

Sistema lineal homogéneo:

$$\mathbf{x}' = A\mathbf{x}$$

**Solución usando autovalores y autovectores** de $A$ (ver [[Alg_Autovalores_Autovectores]]):

| Autovalores de $A$ | Solución $\mathbf{x}(t)$ |
|-------------------|--------------------------|
| Reales distintos $\lambda_1, \lambda_2$ | $\mathbf{x} = C_1 e^{\lambda_1 t}\mathbf{v}_1 + C_2 e^{\lambda_2 t}\mathbf{v}_2$ |
| Real repetido $\lambda$ (1 autovector) | $\mathbf{x} = C_1 e^{\lambda t}\mathbf{v} + C_2 e^{\lambda t}(t\mathbf{v} + \mathbf{w})$ |
| Complejos $\lambda = \alpha \pm \beta i$ | $\mathbf{x} = e^{\alpha t}[C_1(\cos\beta t\,\mathbf{a}-\sin\beta t\,\mathbf{b}) + C_2(\sin\beta t\,\mathbf{a}+\cos\beta t\,\mathbf{b})]$ |

> [!EXAMPLE] 📐 Sistema 2×2 con autovalores reales
> Resolver $\mathbf{x}' = \begin{pmatrix} 1 & 1 \\ 4 & 1 \end{pmatrix} \mathbf{x}$.
>
> **Paso 1**: Autovalores de $A$:
> $$\det(A - \lambda I) = \begin{vmatrix} 1-\lambda & 1 \\ 4 & 1-\lambda \end{vmatrix} = (1-\lambda)^2 - 4 = 0$$
> $$\lambda^2 - 2\lambda - 3 = 0 \implies \lambda_1 = 3, \lambda_2 = -1$$
>
> **Paso 2**: Autovector para $\lambda_1 = 3$:
> $$(A - 3I)\mathbf{v} = \begin{pmatrix} -2 & 1 \\ 4 & -2 \end{pmatrix}\begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = 0 \implies \mathbf{v}_1 = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$
>
> **Paso 3**: Autovector para $\lambda_2 = -1$:
> $$(A + I)\mathbf{v} = \begin{pmatrix} 2 & 1 \\ 4 & 2 \end{pmatrix}\begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = 0 \implies \mathbf{v}_2 = \begin{pmatrix} 1 \\ -2 \end{pmatrix}$$
>
> **Solución general**:
> $$\mathbf{x}(t) = C_1 e^{3t}\begin{pmatrix} 1 \\ 2 \end{pmatrix} + C_2 e^{-t}\begin{pmatrix} 1 \\ -2 \end{pmatrix}$$

### Diagrama de flujo del método

```
        ┌───────────────────────┐
        │   Sistema x' = Ax     │
        └────────┬──────────────┘
                 │
                 ▼
        ┌───────────────────────┐
        │ Calcular autovalores  │
        │ det(A - λI) = 0       │
        └────────┬──────────────┘
                 │
        ┌────────┴────────┐
        ▼                 ▼
  ┌───────────┐    ┌──────────────┐
  │Reales     │    │Complejos     │
  │distintos  │    │α ± βi        │
  └─────┬─────┘    └──────┬───────┘
        │                  │
        ▼                  ▼
  ┌───────────┐    ┌──────────────┐
  │Autovector │    │Parte real e  │
  │cada λ     │    │imaginaria de │
  └─────┬─────┘    │autovector    │
        │          └──────┬───────┘
        ▼                  ▼
  ┌───────────────────────────────┐
  │ Solución: combinación lineal  │
  │ de soluciones fundamentales   │
  └───────────────────────────────┘
```

> [!WARNING] ❌ Matriz no diagonalizable
> Si la matriz $A$ tiene autovalores repetidos pero menos autovectores linealmente independientes que el orden del sistema, se necesitan **autovectores generalizados** para completar la solución.

---

## Conexión con Álgebra Lineal

| Concepto en EDO | Concepto en Álgebra Lineal |
|----------------|---------------------------|
| Solución general $y_h$ | Espacio nulo del operador diferencial $L$
| Solución particular $y_p$ | Solución particular de $L[y] = g$ |
| Conjunto fundamental | Base del espacio de soluciones |
| Wronskiano no nulo | Independencia lineal |
| $y = e^{\lambda t}\mathbf{v}$ resuelve $\mathbf{x}'=A\mathbf{x}$ | $\lambda$ es autovalor, $\mathbf{v}$ es autovector |
| Ecuación característica $ar^2 + br + c = 0$ | $p(\lambda) = \det(A - \lambda I)$ |

La EDO lineal de 2° orden $ay'' + by' + cy = 0$ puede reescribirse como un sistema:

$$\begin{pmatrix} y' \\ y'' \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ -c/a & -b/a \end{pmatrix} \begin{pmatrix} y \\ y' \end{pmatrix}$$

Los autovalores de esta matriz son exactamente las raíces de $ar^2 + br + c = 0$.

---

## Aplicaciones de ingeniería

### Circuitos RLC (2° orden)

$$L I'' + R I' + \frac{1}{C} I = E'(t) \quad \text{o} \quad L Q'' + R Q' + \frac{1}{C} Q = E(t)$$

- $L$: inductancia [H], $R$: resistencia [Ω], $C$: capacitancia [F]
- $I(t)$: corriente, $Q(t)$: carga, $E(t)$: voltaje aplicado

> [!EXAMPLE] 🔧 Circuito RLC
> Un circuito RLC tiene $R = 4\,\Omega$, $L = 1\,H$, $C = 1/3\,F$, $E(t) = 12\,V$. Hallar $Q(t)$ con $Q(0)=0$, $I(0)=0$.
>
> **Ecuación**: $Q'' + 4Q' + 3Q = 12$
>
> **Homogénea**: $r^2 + 4r + 3 = 0 \implies r_1=-1, r_2=-3$
> $$Q_h = C_1 e^{-t} + C_2 e^{-3t}$$
>
> **Particular**: $Q_p = A \implies 0 + 0 + 3A = 12 \implies A = 4$
>
> **General**: $Q(t) = C_1 e^{-t} + C_2 e^{-3t} + 4$
>
> **C.I.**: $Q(0)=0 \implies C_1 + C_2 + 4 = 0$
> $I = Q' = -C_1 e^{-t} - 3C_2 e^{-3t}$, $I(0)=0 \implies -C_1 - 3C_2 = 0$
>
> **Solución**: $C_1 = -6$, $C_2 = 2$, $Q(t) = -6e^{-t} + 2e^{-3t} + 4$

### Sistema resorte-amortiguador

$$m x'' + c x' + kx = F(t)$$

- $m$: masa [kg], $c$: coeficiente de amortiguación [N·s/m], $k$: constante del resorte [N/m]
- $F(t)$: fuerza externa

| Amortiguación | Discriminante $\Delta = c^2 - 4mk$ | Comportamiento |
|---------------|-----------------------------------|----------------|
| **Sobreamortiguado** | $\Delta > 0$ | Dos raíces reales negativas, decaimiento exponencial |
| **Crítico** | $\Delta = 0$ | Raíz doble, retorno más rápido sin oscilar |
| **Subamortiguado** | $\Delta < 0$ | Raíces complejas, oscilaciones que decaen |
| **No amortiguado** | $c = 0$ | Oscilación pura, $x = A\cos(\omega_0 t + \phi)$ |

$$x(t) \text{ (masa)} \quad \text{—————} \quad k \text{ (resorte)}$$
$$ \downarrow $$
$$\text{Amortiguador } c \quad \text{—————} \quad F(t) \text{ (fuerza externa)}$$

```
Diagrama del sistema masa-resorte-amortiguador:

     ┌─────────────────────┐
     │        Masa         │
     │       ╔═══╗         │
     │       ║ m ║         │
     │       ╚═══╝         │
     └──┬─────────────┬────┘
        │             │
        ▼             ▼
   ═══╤═══      ┌────────┐
  ║ Resorte ║   │Amort.  │
  ║   k    ║    │   c    │
   ═══╧═══      └────────┘
        │             │
        └──────┬──────┘
               ▼
          ────────── Pared / Suelo
```

### Ley de enfriamiento de Newton

$$T'(t) = k(T - T_m)$$

$T(t)$: temperatura del cuerpo, $T_m$: temperatura del medio ambiente (constante)

**Solución**: $T(t) = T_m + (T_0 - T_m)e^{kt}$, con $k < 0$ (enfriamiento)

### Mezclas (tanques)

$$Q'(t) = r_{in} c_{in} - r_{out} \frac{Q(t)}{V(t)}$$

$Q(t)$: cantidad de soluto, $r$: caudales, $V$: volumen

### Transferencia de calor en estado estacionario (EDP → EDO)

La ecuación de calor en 1D: $u_t = \alpha^2 u_{xx}$. Con separación de variables $u(x,t) = X(x)T(t)$, se obtienen dos EDO:

$$T' + \alpha^2 \lambda T = 0 \quad \text{y} \quad X'' + \lambda X = 0$$

### Mecánica de fluidos

El perfil de velocidad en un fluido viscoso entre dos placas paralelas satisface:

$$\mu \frac{d^2 u}{dy^2} = \frac{dP}{dx} \quad \text{(ecuación de Poiseuille)}$$

Solución: $u(y) = \frac{1}{2\mu}\frac{dP}{dx}(y^2 - Hy)$, perfil parabólico.

---

## Consejos de estudio

> [!TIP] 📖 Cómo estudiar EDO
> 1. **Practicar la clasificación**: para cada EDO que veas, primero identifica tipo, orden, linealidad
> 2. **Tabla resumen**: tener siempre a mano una tabla con los métodos y cuándo aplicarlos
> 3. **Verificar soluciones**: siempre derivar tu solución y volver a la EDO original
> 4. **Condiciones iniciales**: las C.I. se aplican **siempre al final**, después de obtener la solución general
> 5. **EDO y Álgebra Lineal**: entender que $ay'' + by' + cy = 0$ es equivalente a un sistema 2×2 ayuda a ver la estructura

> [!WARNING] ⚠️ Recordatorios importantes
> - La **ecuación característica** solo funciona para coeficientes constantes
> - Para coeficientes variables, usar **series de potencias** o transformadas
> - El **Wronskiano** mide independencia lineal — calcularlo siempre que tengas dudas
> - En **variación de parámetros**, dividir la EDO por el coeficiente de $y''$ **primero**
> - La superposición aplica: si $y_{p1}$ resuelve $L[y]=g_1$ e $y_{p2}$ resuelve $L[y]=g_2$, entonces $y_{p1}+y_{p2}$ resuelve $L[y]=g_1+g_2$

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| U1 (teoría AnM III) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U1.pdf` |
| U2 (teoría AnM III) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U2.pdf` |
| U3 (teoría AnM III) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U3.pdf` |
| U4 (teoría AnM III) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U4.pdf` |
| U5 parte I | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U5 parte I.pdf` |
| U5 parte II | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U5 parte II.pdf` |
| U6 | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U6.pdf` |
| Teoría Unidad 1 (completa) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 1/Copia de Teoría_AMIII Unidad1.pdf` |
| Teoría Unidad 2 (completa) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 2/Teoría_AMIII Unidad2.pdf` |
| Teoría Unidad 3 (completa) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 3/Teoría_AMIII Unidad3.pdf` |
| Teoría Unidad 4 (completa) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 4/Teoría_AMIII unidad 4.pdf` |
| Teoría Unidad 5 parte 1 | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 5/Teoría_AMIII Unidad5(parte1).pdf` |
| Teoría Unidad 5 parte 2 | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 5/Teoría_AMIII Unidad 5(parte 2).pdf` |
| Teoría Unidad 6 (completa) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Unidad 6/Teoría_AMIII (10).pdf` |
| **Libro**: Zill — Ecuaciones diferenciales | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Ecuaciones-diferenciales-Dennis-G.-Zill.pdf` |
| **Libro**: Carmona Jover — Ecuaciones diferenciales | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Ecuaciones-diferenciales-Isabel-Carmona-Jover.pdf` |
| **Libro**: Edwards — Ecuaciones diferenciales | `Raw/.../1 matematica/TEORIA/Análisis matemático III/edwards-ecuaciones-diferenciales.pdf` |
| **Libro**: Fundamentals of Diff. Eqs 9ed | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Fundamentals of Differential Equations 9th Edition.pdf` |
| TP1-9 Resueltos (David Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/resolucion tps/Resolución TP1 - 2023.pdf` a `Resolución - TP°10.pdf` |
| Programa AnM III 2021 | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Programa_/Programa Análisis Matemático III-2021_...docx` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Integrales_Superficie]] • **Siguiente:** [[Anm_Transformada_Laplace]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
