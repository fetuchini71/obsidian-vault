> [!NOTE] Navegación
> **Anterior:** [[Anm_Transformada_Laplace]] • **Siguiente:** —
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.
>
> ⚠️ **Requisito**: números complejos (ver [[Alg_Numeros_Complejos]]), series de potencias, integrales.

# Variable Compleja y Series de Fourier

## Índice

==toc==

---

> [!INFO]
> La variable compleja extiende el cálculo a los números complejos, donde derivar e integrar tienen propiedades sorprendentes. Las series de Fourier descomponen cualquier señal en **senos y cosenos** — la base del procesamiento de señales, comunicaciones y la solución de EDP. Juntos forman el puente entre el análisis matemático y las aplicaciones de ingeniería modernas.

---

## Parte I: Variable Compleja

### Funciones analíticas

$f(z)$ es **analítica** (u **holomorfa**) en una región si es derivable en todo punto de esa región.

Ecuaciones de Cauchy-Riemann (condición **necesaria y suficiente** para la analiticidad, si las derivadas parciales son continuas):

$$ \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{y} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x} $$

donde $f(z) = u(x,y) + i\,v(x,y)$, con $z = x + iy$.

> [!EXAMPLE] 📐 Verificar analiticidad
> ¿$f(z) = z^2$ es analítica?
>
> **Paso 1**: $z^2 = (x+iy)^2 = x^2 - y^2 + i(2xy)$
>
> $u(x,y) = x^2 - y^2$, $v(x,y) = 2xy$
>
> **Paso 2**: Calcular derivadas parciales:
> $$\frac{\partial u}{\partial x} = 2x, \quad \frac{\partial u}{\partial y} = -2y$$
> $$\frac{\partial v}{\partial x} = 2y, \quad \frac{\partial v}{\partial y} = 2x$$
>
> **Paso 3**: Verificar Cauchy-Riemann:
> $$\frac{\partial u}{\partial x} = 2x = \frac{\partial v}{\partial y} \quad \checkmark$$
> $$\frac{\partial u}{\partial y} = -2y = -\frac{\partial v}{\partial x} \quad \checkmark$$
>
> $f(z) = z^2$ es analítica en **todo** $\mathbb{C}$ (es un polinomio).

> [!WARNING] ❌ Funciones no analíticas
> $f(z) = \bar{z} = x - iy$ **no** es analítica en ningún punto:
> $u = x$, $v = -y$
> $\frac{\partial u}{\partial x} = 1$, $\frac{\partial v}{\partial y} = -1$ → $1 \neq -1$, no cumple C-R.
> Las funciones que involucran $\bar{z}$ generalmente no son analíticas.

### Funciones elementales complejas

| Función real | Extensión compleja | Observaciones |
|-------------|-------------------|---------------|
| $e^x$ | $e^z = e^x(\cos y + i\sin y)$ | Entera (analítica en $\mathbb{C}$) |
| $\sin x$ | $\sin z = \frac{e^{iz} - e^{-iz}}{2i}$ | Entera |
| $\cos x$ | $\cos z = \frac{e^{iz} + e^{-iz}}{2}$ | Entera |
| $\ln x$ | $\ln z = \ln|z| + i\arg(z)$ | Analítica excepto en $z \leq 0$ (rama principal) |
| $x^a$ | $z^a = e^{a\ln z}$ | Analítica en el mismo dominio que $\ln z$ |

> [!TIP] Fórmula de Euler
> $$e^{i\theta} = \cos\theta + i\sin\theta$$
> Es la fórmula más importante para conectar variable compleja con Fourier. De aquí:
> $$\cos\theta = \frac{e^{i\theta} + e^{-i\theta}}{2}, \quad \sin\theta = \frac{e^{i\theta} - e^{-i\theta}}{2i}$$

### Integrales complejas

$$ \int_C f(z) \, dz $$

donde $C$ es un camino en el plano complejo, parametrizado por $z(t) = x(t) + iy(t)$, $a \leq t \leq b$:

$$ \int_C f(z) \, dz = \int_a^b f(z(t)) \, z'(t) \, dt $$

### Teorema de Cauchy

Si $f$ es analítica en una región **simplemente conexa** $D$ y $C$ es una curva cerrada dentro de $D$:

$$ \oint_C f(z) \, dz = 0 $$

### Fórmula integral de Cauchy

Si $f$ es analítica dentro y sobre $C$, entonces para cualquier $z_0$ interior a $C$:

$$ f(z_0) = \frac{1}{2\pi i} \oint_C \frac{f(z)}{z - z_0} \, dz $$

Y para derivadas:

$$ f^{(n)}(z_0) = \frac{n!}{2\pi i} \oint_C \frac{f(z)}{(z - z_0)^{n+1}} \, dz $$

> [!EXAMPLE] 📐 Aplicar la fórmula integral de Cauchy
> Calcular $\oint_C \frac{e^z}{z - 2} \, dz$ donde $C$ es $|z| = 3$ (círculo de radio 3 centrado en 0).
>
> **Paso 1**: $f(z) = e^z$ es analítica en todo $\mathbb{C}$ (entera)
>
> **Paso 2**: $z_0 = 2$ está dentro de $C$ (pues $|2| = 2 < 3$)
>
> **Paso 3**: Aplicar fórmula integral:
> $$\oint_C \frac{e^z}{z - 2} \, dz = 2\pi i \cdot f(2) = 2\pi i \cdot e^2$$

### Series de Taylor y Laurent

Toda función analítica en $|z - z_0| < R$ se puede expresar como serie de Taylor:

$$ f(z) = \sum_{n=0}^\infty a_n (z - z_0)^n, \quad a_n = \frac{f^{(n)}(z_0)}{n!} $$

Si $f$ tiene singularidades, se usa la **serie de Laurent** (incluye potencias negativas):

$$ f(z) = \sum_{n=-\infty}^\infty a_n (z - z_0)^n, \quad a_n = \frac{1}{2\pi i} \oint_C \frac{f(z)}{(z - z_0)^{n+1}} \, dz $$

### Teorema de los residuos

$$ \oint_C f(z) \, dz = 2\pi i \sum_{k} \text{Res}(f, z_k) $$

Los residuos son los coeficientes $a_{-1}$ de la serie de Laurent alrededor de cada singularidad $z_k$.

| Tipo de singularidad | Cálculo del residuo |
|---------------------|---------------------|
| **Polo simple** en $z_0$ | $\text{Res}(f,z_0) = \lim_{z \to z_0} (z - z_0)f(z)$ |
| **Polo de orden $m$** en $z_0$ | $\text{Res}(f,z_0) = \frac{1}{(m-1)!}\lim_{z \to z_0} \frac{d^{m-1}}{dz^{m-1}}\left[(z - z_0)^m f(z)\right]$ |
| **Singularidad esencial** | Desarrollar en serie de Laurent y leer $a_{-1}$ |

> [!EXAMPLE] 📐 Teorema de los residuos
> Calcular $\oint_C \frac{5z - 2}{z(z-1)} \, dz$ donde $C$ es $|z| = 2$.
>
> **Paso 1**: Identificar singularidades dentro de $C$: $z=0$ y $z=1$ (ambos dentro del círculo de radio 2)
>
> **Paso 2**: Residuo en $z=0$ (polo simple):
> $$\text{Res}(f, 0) = \lim_{z\to 0} z \cdot \frac{5z - 2}{z(z-1)} = \lim_{z\to 0} \frac{5z - 2}{z-1} = \frac{-2}{-1} = 2$$
>
> **Paso 3**: Residuo en $z=1$ (polo simple):
> $$\text{Res}(f, 1) = \lim_{z\to 1} (z-1) \cdot \frac{5z - 2}{z(z-1)} = \lim_{z\to 1} \frac{5z - 2}{z} = \frac{3}{1} = 3$$
>
> **Paso 4**: Aplicar teorema de residuos:
> $$\oint_C f(z)\,dz = 2\pi i (2 + 3) = 10\pi i$$

### Aplicación: integrales reales con residuos

El teorema de residuos permite calcular integrales reales que serían muy difíciles por métodos reales.

| Tipo de integral real | Sustitución/Fórmula |
|----------------------|---------------------|
| $\int_{-\infty}^\infty \frac{P(x)}{Q(x)} dx$ | Cerrar con semicírculo en el semiplano superior; sumar residuos de polos en $\text{Im}(z) > 0$ |
| $\int_0^{2\pi} R(\cos\theta, \sin\theta) d\theta$ | $z = e^{i\theta}$, $\cos\theta = \frac{z+z^{-1}}{2}$, $\sin\theta = \frac{z-z^{-1}}{2i}$, $dz = iz\,d\theta$ |
| $\int_{-\infty}^\infty f(x)e^{i\omega x} dx$ | Transformada de Fourier; cerrar según signo de $\omega$ |

> [!EXAMPLE] 📐 Integral real con residuos
> Calcular $\int_{-\infty}^\infty \frac{dx}{x^2 + 1}$.
>
> **Paso 1**: Considerar $f(z) = \frac{1}{z^2 + 1} = \frac{1}{(z-i)(z+i)}$
>
> **Paso 2**: Polos simples en $z = \pm i$. Solo $z = i$ está en el semiplano superior.
>
> **Paso 3**: Residuo en $z = i$:
> $$\text{Res}(f, i) = \lim_{z\to i} (z-i)\frac{1}{(z-i)(z+i)} = \frac{1}{2i}$$
>
> **Paso 4**: Integral = $2\pi i \cdot \frac{1}{2i} = \pi$
>
> **Resultado**: $\int_{-\infty}^\infty \frac{dx}{x^2 + 1} = \pi$

---

## Parte II: Series y Transformada de Fourier

### Series de Fourier

Toda función **periódica** $f(t)$ con período $T$ puede escribirse como:

$$ f(t) = a_0 + \sum_{n=1}^\infty \left[ a_n \cos\left(\frac{2\pi n t}{T}\right) + b_n \sin\left(\frac{2\pi n t}{T}\right) \right] $$

**Coeficientes de Fourier**:

$$ a_0 = \frac{1}{T} \int_0^T f(t) \, dt $$

$$ a_n = \frac{2}{T} \int_0^T f(t) \cos\left(\frac{2\pi n t}{T}\right) dt $$

$$ b_n = \frac{2}{T} \int_0^T f(t) \sin\left(\frac{2\pi n t}{T}\right) dt $$

### Convergencia (condiciones de Dirichlet)

La serie converge a $f(t)$ en los puntos de continuidad, y al promedio $[f(t^+) + f(t^-)]/2$ en saltos, si:
1. $f$ tiene un número finito de discontinuidades en un período
2. $f$ tiene un número finito de máximos y mínimos en un período
3. $\int_0^T |f(t)|\,dt$ existe

> [!WARNING] ❌ Fenómeno de Gibbs
> Cerca de una discontinuidad de salto, la serie de Fourier **sobrepasa** el valor de la función aproximadamente en un 9% del salto, sin importar cuántos términos se tomen. Esto es el fenómeno de Gibbs — no es un error de cálculo, es inherente a la serie.

> [!EXAMPLE] 📐 Serie de Fourier de una onda cuadrada
> $f(t) = \begin{cases} 0, & -\pi < t < 0 \\ 1, & 0 < t < \pi \end{cases}$, período $T = 2\pi$.
>
> **Paso 1**: Calcular $a_0$:
> $$a_0 = \frac{1}{2\pi}\int_{-\pi}^{\pi} f(t)\,dt = \frac{1}{2\pi}\int_0^{\pi} 1\,dt = \frac{1}{2}$$
>
> **Paso 2**: Calcular $a_n$:
> $$a_n = \frac{1}{\pi}\int_0^{\pi} \cos(nt)\,dt = \frac{1}{\pi}\left[\frac{\sin(nt)}{n}\right]_0^{\pi} = 0$$
>
> **Paso 3**: Calcular $b_n$:
> $$b_n = \frac{1}{\pi}\int_0^{\pi} \sin(nt)\,dt = \frac{1}{\pi}\left[-\frac{\cos(nt)}{n}\right]_0^{\pi} = \frac{1}{n\pi}(1 - \cos(n\pi))$$
> $$b_n = \begin{cases} \frac{2}{n\pi}, & n \text{ impar} \\ 0, & n \text{ par} \end{cases}$$
>
> **Paso 4**: Serie de Fourier:
> $$f(t) = \frac{1}{2} + \frac{2}{\pi}\sum_{k=0}^\infty \frac{\sin((2k+1)t)}{2k+1}$$
> $$f(t) = \frac{1}{2} + \frac{2}{\pi}\left(\sin t + \frac{\sin 3t}{3} + \frac{\sin 5t}{5} + \dots\right)$$

### Forma compleja de la serie de Fourier

Usando la fórmula de Euler, la serie se escribe más compactamente:

$$ f(t) = \sum_{n=-\infty}^\infty c_n e^{i n \omega_0 t} $$

donde $\omega_0 = \frac{2\pi}{T}$ es la frecuencia fundamental y:

$$ c_n = \frac{1}{T} \int_0^T f(t) e^{-i n \omega_0 t} \, dt $$

**Relación entre coeficientes**:
- $c_0 = a_0$
- $c_n = \frac{a_n - i b_n}{2}$ para $n > 0$
- $c_{-n} = \frac{a_n + i b_n}{2} = \overline{c_n}$ (si $f$ es real)

### Transformada de Fourier

Para funciones **no periódicas** (o como límite cuando $T \to \infty$):

$$ \hat{f}(\omega) = \mathcal{F}\{f(t)\} = \int_{-\infty}^\infty f(t) e^{-i\omega t} \, dt $$

**Transformada inversa**:

$$ f(t) = \mathcal{F}^{-1}\{\hat{f}(\omega)\} = \frac{1}{2\pi} \int_{-\infty}^\infty \hat{f}(\omega) e^{i\omega t} \, d\omega $$

### Propiedades de la Transformada de Fourier

| Propiedad | Dominio del tiempo | Dominio de la frecuencia |
|-----------|-------------------|--------------------------|
| **Linealidad** | $af + bg$ | $a\hat{f} + b\hat{g}$ |
| **Derivada** | $f'(t)$ | $i\omega \hat{f}(\omega)$ |
| **Derivada n-ésima** | $f^{(n)}(t)$ | $(i\omega)^n \hat{f}(\omega)$ |
| **Integral** | $\int_{-\infty}^t f(\tau)d\tau$ | $\frac{\hat{f}(\omega)}{i\omega} + \pi\hat{f}(0)\delta(\omega)$ |
| **Traslación en $t$** | $f(t-t_0)$ | $e^{-i\omega t_0}\hat{f}(\omega)$ |
| **Traslación en $\omega$** | $e^{i\omega_0 t}f(t)$ | $\hat{f}(\omega - \omega_0)$ |
| **Escalado** | $f(at)$ | $\frac{1}{|a|}\hat{f}\left(\frac{\omega}{a}\right)$ |
| **Convolución** | $(f*g)(t)$ | $\hat{f}(\omega)\hat{g}(\omega)$ |
| **Multiplicación** | $f(t)g(t)$ | $\frac{1}{2\pi}(\hat{f}*\hat{g})(\omega)$ |
| **Parseval** | $\int_{-\infty}^\infty |f(t)|^2 dt$ | $\frac{1}{2\pi}\int_{-\infty}^\infty |\hat{f}(\omega)|^2 d\omega$ |

### Pares de Fourier comunes

| $f(t)$ | $\hat{f}(\omega)$ |
|--------|-------------------|
| $\delta(t)$ | $1$ |
| $1$ | $2\pi\delta(\omega)$ |
| $u(t)$ | $\pi\delta(\omega) + \frac{1}{i\omega}$ |
| $e^{-at}u(t)$ ($a>0$) | $\frac{1}{a + i\omega}$ |
| $\frac{\sin(Wt)}{\pi t}$ (sinc) | $\chi_{[-W,W]}(\omega)$ (función rectángulo) |
| $\chi_{[-T,T]}(t)$ (rectángulo) | $\frac{2\sin(\omega T)}{\omega}$ |
| $e^{-a|t|}$ ($a>0$) | $\frac{2a}{a^2 + \omega^2}$ |
| $\cos(\omega_0 t)$ | $\pi[\delta(\omega - \omega_0) + \delta(\omega + \omega_0)]$ |
| $\sin(\omega_0 t)$ | $i\pi[\delta(\omega + \omega_0) - \delta(\omega - \omega_0)]$ |

> [!TIP] Series vs. Transformada
> - **Series de Fourier**: para funciones **periódicas** → espectro **discreto** (armónicos $n\omega_0$)
> - **Transformada de Fourier**: para funciones **no periódicas** → espectro **continuo** (todo $\omega$)
> - Ambas usan la misma idea: descomponer en senos y cosenos (o exponenciales complejas)

---

## Ecuaciones en Derivadas Parciales (EDP)

Usando series de Fourier y separación de variables se resuelven las EDP clásicas.

### Ecuación del calor (difusión)

$$ u_t = \alpha^2 u_{xx}, \quad 0 < x < L, \quad t > 0 $$

C.I.: $u(x,0) = f(x)$, C.F.: $u(0,t) = u(L,t) = 0$

**Separación de variables**: $u(x,t) = X(x)T(t)$

$$ \frac{T'}{\alpha^2 T} = \frac{X''}{X} = -\lambda $$

Resultan dos EDO:
- $X'' + \lambda X = 0$, con $X(0)=X(L)=0$
- $T' + \alpha^2 \lambda T = 0$

**Solución** (autovalores $\lambda_n = (n\pi/L)^2$):

$$ u(x,t) = \sum_{n=1}^\infty b_n \sin\left(\frac{n\pi x}{L}\right) e^{-\alpha^2 (n\pi/L)^2 t} $$

$$ b_n = \frac{2}{L} \int_0^L f(x) \sin\left(\frac{n\pi x}{L}\right) dx $$

### Ecuación de onda

$$ u_{tt} = c^2 u_{xx}, \quad 0 < x < L, \quad t > 0 $$

C.I.: $u(x,0) = f(x)$, $u_t(x,0) = g(x)$, C.F.: $u(0,t) = u(L,t) = 0$

**Solución**:

$$ u(x,t) = \sum_{n=1}^\infty \left[ A_n \cos\left(\frac{n\pi c t}{L}\right) + B_n \sin\left(\frac{n\pi c t}{L}\right) \right] \sin\left(\frac{n\pi x}{L}\right) $$

Los coeficientes $A_n$, $B_n$ se obtienen de las condiciones iniciales usando las series de Fourier de $f$ y $g$.

### Diagrama de flujo: Separación de variables

```
    ┌──────────────────────────────────┐
    │  EDP: u_t = α² u_xx             │
    │  + condiciones de borde e inicial│
    └──────────┬───────────────────────┘
               │
               ▼
    ┌──────────────────────────────────┐
    │  Proponer u(x,t) = X(x)T(t)      │
    │  Sustituir y separar variables   │
    │  X T' = α² X'' T                 │
    │  T'/(α²T) = X''/X = -λ           │
    └──────────┬───────────────────────┘
               │
               ▼
    ┌─────────────────┐    ┌─────────────────┐
    │  EDO en x:       │    │  EDO en t:       │
    │  X'' + λX = 0    │    │  T' + α²λT = 0   │
    │  X(0)=X(L)=0     │    │                   │
    └────────┬─────────┘    └────────┬─────────┘
             │                       │
             ▼                       ▼
    ┌─────────────────┐    ┌─────────────────┐
    │  Autovalores:    │    │  Solución:      │
    │  λ = (nπ/L)²     │    │  T = e^{-α²λt}  │
    │  Autofunciones:  │    │                  │
    │  X = sin(nπx/L)  │    │                  │
    └────────┬─────────┘    └────────┬─────────┘
             │                       │
             └───────────┬───────────┘
                         │
                         ▼
    ┌──────────────────────────────────┐
    │  Superposición:                  │
    │  u = Σ b_n X_n(x) T_n(t)        │
    │  b_n de la serie de Fourier      │
    │  de la condición inicial f(x)    │
    └──────────────────────────────────┘
```

---

## Conexión con Álgebra Lineal

| Concepto en Variable Compleja / Fourier | Concepto en Álgebra Lineal |
|----------------------------------------|---------------------------|
| Funciones $e^{i n \omega_0 t}$ como base | Base ortogonal en el espacio $L^2[0,T]$ |
| Coeficientes $c_n$ de Fourier | Coordenadas del vector $f$ en la base |
| Ortogonalidad: $\int e^{in\omega_0 t} e^{-im\omega_0 t} dt = T\delta_{nm}$ | Producto interno |
| Serie de Fourier = proyección | Proyección ortogonal sobre la base |
| Transformada de Fourier | Cambio de base (de posición a frecuencia) |
| Teorema de Parseval | Conservación de la norma |
| Ecuación de calor: $X'' + \lambda X = 0$, $X(0)=X(L)=0$ | Problema de autovalores: $L[X] = \lambda X$ |
| Solución por separación de variables | Descomposición espectral del operador $L = \frac{d^2}{dx^2}$ |

> [!TIP] Visión unificada
> Las series de Fourier, la transformada de Fourier, la separación de variables para EDP, y hasta los autovalores en álgebra lineal son **la misma idea**: descomponer un problema en una suma de piezas simples (modos, autofunciones, frecuencias). En todos los casos se busca una **base** adecuada que diagonalice el operador.

---

## Aplicaciones de ingeniería

### Procesamiento de señales

- **Filtrado**: multiplicar $\hat{f}(\omega)$ por una función ventana $H(\omega)$ elimina frecuencias no deseadas
- **Modulación**: $f(t)\cos(\omega_0 t)$ desplaza el espectro — base de la transmisión AM
- **Muestreo** (teorema de Nyquist-Shannon): una señal con ancho de banda limitado $B$ se reconstruye perfectamente si se muestrea a $f_s > 2B$

### Comunicaciones

- La serie de Fourier modela señales periódicas portadoras
- La transformada de Fourier describe el ancho de banda de una señal
- La modulación QAM usa senos y cosenos en cuadratura

### Vibraciones y acústica

- **Análisis modal**: las vibraciones de una estructura se descomponen en modos (autofunciones) mediante Fourier
- Una cuerda vibrante se describe con la ecuación de onda — las frecuencias naturales son $f_n = \frac{nc}{2L}$

> [!EXAMPLE] 🔧 Cuerda de guitarra pulsada
> Una cuerda de guitarra de longitud $L=0.65\,m$ se pulsa en el centro. La condición inicial es $f(x) = \begin{cases} \frac{2h}{L}x, & 0 \leq x \leq L/2 \\ \frac{2h}{L}(L-x), & L/2 \leq x \leq L \end{cases}$
>
> Los coeficientes $A_n$ de la serie (solo modos impares) son:
> $$A_n = \frac{8h}{n^2\pi^2}\sin\left(\frac{n\pi}{2}\right)$$
>
> La solución $u(x,t) = \sum_{n=1}^\infty A_n \sin\left(\frac{n\pi x}{L}\right)\cos\left(\frac{n\pi c t}{L}\right)$
>
> **Significado físico**: la vibración se compone del modo fundamental (440 Hz para LA4) más armónicos impares que decaen como $1/n^2$.

### Transferencia de calor

La ecuación del calor con condiciones de borde mixtas modela:
- Aletas de enfriamiento en motores
- Distribución de temperatura en barras metálicas
- Procesos de temple y recocido

### Mecánica de fluidos

- La ecuación de Laplace $\nabla^2 \phi = 0$ (potencial de velocidad) se resuelve con separación de variables y series de Fourier
- Flujo potencial alrededor de perfiles aerodinámicos usando **mapeo conforme** (variable compleja)

---

## Consejos de estudio

> [!TIP] 📖 Cómo dominar Variable Compleja y Fourier
> 1. **Practicar C-R**: verificar analiticidad es un ejercicio mecánico — hacer varios ejemplos hasta que salga automático
> 2. **Residuos en polos simples**: la fórmula $\lim (z-z_0)f(z)$ es la más usada; memorizarla
> 3. **Series de Fourier**: aprender a identificar simetrías (función par → solo cosenos, impar → solo senos)
> 4. **Ortogonalidad**: entender que $\int \sin(nx)\sin(mx)dx = 0$ si $n \neq m$ simplifica todo
> 5. **Separación de variables**: el método es siempre el mismo — proponer $u = XT$, separar, resolver dos EDO, superponer

> [!WARNING] ⚠️ Recordatorios importantes
> - Las ecuaciones de C-R son **necesarias y suficientes** solo si las derivadas parciales son continuas
> - El teorema de Cauchy requiere que la región sea **simplemente conexa** (sin agujeros)
> - El teorema de los residuos solo aplica a singularidades **aisladas**
> - Los coeficientes de Fourier $a_n$, $b_n$ se calculan sobre **un período completo**, no sobre medio período
> - En separación de variables, las **condiciones de borde** determinan los autovalores — si cambian las C.F., cambian las autofunciones (>: la serie de Fourier de senos ya no sirve, puede que necesites cosenos o ambas)
> - La transformada de Fourier puede no converger para funciones que no decaen suficientemente rápido (usar transformada de Laplace en ese caso)

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| **Libro**: Churchill — Complex Variables | `Raw/.../1 matematica/TEORIA/Análisis matemático IV/complex variables and applications.pdf` |
| **Libro**: Applied Complex Variables | `Raw/.../1 matematica/TEORIA/Análisis matemático IV/applied complex variables for engineers.pdf` |
| **Libro**: A First Course with Applications | `Raw/.../1 matematica/TEORIA/Análisis matemático IV/A_First_Course_in_with_Applications_Comp-53078713.pdf` |
| **Libro**: Fourier Transforms Principles and Applications | `Raw/.../1 matematica/TEORIA/Análisis matemático IV/Fourier/Fourier transforms Principles and Applications - PDF Room.pdf` |
| **Libro**: Fourier Series and Boundary Value Problems | `Raw/.../1 matematica/TEORIA/Análisis matemático IV/Fourier/Fourier-series-and-boundary-value-problems.pdf` |
| **EDP**: Ecuación del calor | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/Ecuación del calor.pdf` |
| **EDP**: Resolución ecuación de calor/onda | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Ecuación de calor y onda_/ResoluciónEcOndayCalor.pdf` |
| Identidades trigonométricas | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Identidades trigonométricas.pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Transformada_Laplace]] • **Siguiente:** —
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
