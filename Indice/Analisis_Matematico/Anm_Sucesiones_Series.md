> [!NOTE] Navegación
> **Anterior:** [[Anm_Aplicaciones_Integral]] • **Siguiente:** [[Anm_Funciones_Varias_Variables]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Sucesiones y Series

## Índice

==toc==

---

> [!INFO]
> Las series permiten **sumar infinitos términos** y obtener un resultado finito. Son la puerta de entrada a las series de potencias, Taylor y las aproximaciones de funciones.
>
> En ingeniería: las series de Fourier (análisis de señales), series de potencias (soluciones de EDOs), series de Taylor (aproximaciones numéricas en calculadoras y software de ingeniería).

---

## Sucesiones

Una **sucesión** es una lista ordenada $\{a_n\}_{n=1}^\infty$ donde $a_n$ es una expresión en $n$.

```
     a₁, a₂, a₃, a₄, ..., aₙ, ...
      ↓   ↓   ↓   ↓        ↓
     1/2 2/3 3/4 4/5 ...  n/(n+1) ... → 1
```

| Propiedad | Definición |
|:----------|:-----------|
| **Convergente** | $\lim_{n \to \infty} a_n = L$ (existe finito) |
| **Divergente** | El límite no existe o es $\pm\infty$ |
| **Acotada** | $\exists M > 0: |a_n| \leq M$ para todo $n$ |
| **Monótona creciente** | $a_{n+1} \geq a_n$ para todo $n$ |
| **Monótona decreciente** | $a_{n+1} \leq a_n$ para todo $n$ |

> [!TIP] Toda sucesión monótona y acotada converge
> Este es el **Teorema de convergencia monótona** para sucesiones. Es la herramienta teórica más usada para probar convergencia cuando no se puede calcular el límite explícitamente.

> [!EXAMPLE] Convergencia de sucesión
> Determinar si $a_n = \frac{3n^2 + 2n}{5n^2 - 1}$ converge.
>
> **Paso 1:** Calcular el límite cuando $n \to \infty$.
> $$\lim_{n \to \infty} \frac{3n^2 + 2n}{5n^2 - 1} = \lim_{n \to \infty} \frac{3 + \frac{2}{n}}{5 - \frac{1}{n^2}}$$
>
> **Paso 2:** Evaluar.
> $$\frac{3 + 0}{5 - 0} = \frac{3}{5}$$
>
> **Resultado:** La sucesión converge a $\frac{3}{5}$.
>
> > [!WARNING]
> > Que una sucesión **converja** significa que sus términos se acercan a un número fijo. No confundir con la **serie** asociada (la suma de esos términos), que puede diverger incluso si la sucesión converge a 0.

> [!EXAMPLE] Sucesión no acotada
> $a_n = n^2$: $\lim_{n \to \infty} n^2 = \infty$ → **diverge** (no acotada).
>
> $a_n = (-1)^n$: oscila entre $-1$ y $1$ → **diverge** (oscilante).

---

## Series numéricas

$$\sum_{n=1}^\infty a_n = a_1 + a_2 + a_3 + \dots$$

La serie **converge** si la sucesión de sumas parciales $S_N = \sum_{n=1}^N a_n$ tiene límite finito.

### Serie geométrica

$$\sum_{n=0}^\infty r^n = \frac{1}{1-r} \quad \text{si } |r| < 1 \quad (\text{diverge si } |r| \geq 1)$$

```
    S = 1 + r + r² + r³ + ...
    
    |r| < 1 → ✓ converge
    r = 1/2: S = 1 + 1/2 + 1/4 + 1/8 + ... = 2
    
    |r| ≥ 1 → ✗ diverge
    r = 2:  S = 1 + 2 + 4 + 8 + ... → ∞
```

> [!EXAMPLE] Serie geométrica
> Determinar si $\displaystyle \sum_{n=1}^\infty \left(\frac{2}{3}\right)^n$ converge y hallar su suma.
>
> **Paso 1:** Identificar $r$.
> $r = \frac{2}{3}$, $|r| = \frac{2}{3} < 1$ → **converge**.
>
> **Paso 2:** Aplicar fórmula (la serie empieza en $n=1$, no $n=0$).
> $$\sum_{n=1}^\infty r^n = \frac{r}{1-r} = \frac{2/3}{1 - 2/3} = \frac{2/3}{1/3} = 2$$
>
> **Resultado:** $\displaystyle \sum_{n=1}^\infty \left(\frac{2}{3}\right)^n = 2$.

### Serie armónica

$$\sum_{n=1}^\infty \frac{1}{n} \quad \text{— **diverge**} \quad (\text{aunque $a_n \to 0$!})$$

> [!WARNING] ¡La armónica diverge!
> La serie armónica es el **contraejemplo clásico**: aunque sus términos tienden a cero, la suma diverge (lentamente). Esto demuestra que $\lim a_n = 0$ es necesario pero **no suficiente** para la convergencia de una serie.

### Serie p

$$\sum_{n=1}^\infty \frac{1}{n^p}$$

| $p$ | Comportamiento |
|:---:|:---------------|
| $p > 1$ | **Converge** (ej: $p=2$ → $\sum 1/n^2 = \pi^2/6$) |
| $p = 1$ | Diverge (serie armónica) |
| $p < 1$ | Diverge |

### Serie armónica alternada

$$\sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots = \ln 2$$

> [!TIP] Alternadas: mucho ojo
> Las series alternadas son **más "dóciles"** que las positivas: pueden converger aunque la versión positiva diverja (como la armónica alternada). El criterio de Leibniz es tu mejor aliado.

---

## Criterios de convergencia

| Criterio | Dice que si... | Entonces... |
|:---------|:---------------|:------------|
| **Término n-ésimo** | $\lim a_n \neq 0$ | La serie **diverge** |
| **Comparación directa** | $0 \leq a_n \leq b_n$ y $\sum b_n$ converge | $\sum a_n$ converge |
| **Comparación al límite** | $\lim a_n/b_n = c > 0$ | Ambas convergen o divergen |
| **Razón (D'Alembert)** | $\lim |a_{n+1}/a_n| = L$ | $L < 1$ converge, $L > 1$ diverge |
| **Raíz (Cauchy)** | $\lim \sqrt[n]{|a_n|} = L$ | $L < 1$ converge, $L > 1$ diverge |
| **Integral** | $a_n = f(n)$ positiva y decreciente | $\sum a_n$ y $\int f(x) dx$ tienen mismo carácter |
| **Series alternadas (Leibniz)** | $a_n$ positiva, decreciente, $\to 0$ | $\sum (-1)^n a_n$ **converge** |

> [!EXAMPLE] Criterio de la razón
> Determinar la convergencia de $\displaystyle \sum_{n=1}^\infty \frac{n^2}{2^n}$.
>
> **Paso 1:** Calcular el límite del criterio.
> $$L = \lim_{n \to \infty} \left|\frac{a_{n+1}}{a_n}\right| = \lim_{n \to \infty} \frac{(n+1)^2/2^{n+1}}{n^2/2^n} = \lim_{n \to \infty} \frac{(n+1)^2}{n^2} \cdot \frac{2^n}{2^{n+1}}$$
>
> **Paso 2:** Simplificar.
> $$L = \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^2 \cdot \frac{1}{2} = 1 \cdot \frac{1}{2} = \frac{1}{2}$$
>
> **Paso 3:** Conclusión.
> $L = 1/2 < 1$ → la serie **converge**.
>
> > [!TIP]
> > El criterio de la razón es ideal para series con **factoriales** ($n!$), **exponenciales** ($2^n$, $e^n$) y **potencias mixtas**. Cuando $L=1$, el criterio no decide — probá con otro.

> [!EXAMPLE] Criterio integral
> Determinar si $\displaystyle \sum_{n=2}^\infty \frac{1}{n \ln n}$ converge.
>
> **Paso 1:** $a_n = f(n)$ con $f(x) = \frac{1}{x \ln x}$, positiva y decreciente para $x \geq 2$.
>
> **Paso 2:** Calcular la integral impropia.
> $$\int_2^\infty \frac{1}{x \ln x} \, dx = \lim_{t \to \infty} \int_2^t \frac{1}{x \ln x} \, dx$$
>
> Sustitución: $u = \ln x$, $du = dx/x$.
> $$= \lim_{t \to \infty} \int_{\ln 2}^{\ln t} \frac{1}{u} \, du = \lim_{t \to \infty} [\ln(\ln t) - \ln(\ln 2)] = \infty$$
>
> **Resultado:** La integral **diverge** → la serie **diverge**.

---

## Series de potencias

$$\sum_{n=0}^\infty c_n (x - a)^n$$

Tiene un **radio de convergencia** $R$: converge para $|x-a| < R$ y diverge para $|x-a| > R$.

```
        ────╋━━━━━━━━╋────
        ←── divergente
             ←── convergente
                 a-R   a   a+R
```

| Propiedad | Descripción |
|:----------|:------------|
| **Radio $R$** | $R = \lim_{n \to \infty} \left|\frac{c_n}{c_{n+1}}\right|$ o $R = \frac{1}{\lim \sqrt[n]{|c_n|}}$ |
| **Intervalo de convergencia** | $(a-R, a+R)$ más posibles extremos |
| **Derivación término a término** | Válida dentro del radio |
| **Integración término a término** | Válida dentro del radio |

> [!TIP] Las series de potencias son funciones
> Dentro del radio de convergencia, una serie de potencias define una función continua y derivable. Podés derivar e integrar término a término como si fuera un polinomio.

### Serie de Taylor / Maclaurin

$$f(x) = \sum_{n=0}^\infty \frac{f^{(n)}(a)}{n!} (x - a)^n$$

**Series importantes (Maclaurin, $a=0$):**

| Función | Serie | Intervalo |
|:--------|:------|:----------|
| $e^x$ | $\displaystyle \sum_{n=0}^\infty \frac{x^n}{n!}$ | $\mathbb{R}$ |
| $\sin x$ | $\displaystyle \sum_{n=0}^\infty (-1)^n \frac{x^{2n+1}}{(2n+1)!}$ | $\mathbb{R}$ |
| $\cos x$ | $\displaystyle \sum_{n=0}^\infty (-1)^n \frac{x^{2n}}{(2n)!}$ | $\mathbb{R}$ |
| $\frac{1}{1-x}$ | $\displaystyle \sum_{n=0}^\infty x^n$ | $(-1, 1)$ |
| $\ln(1+x)$ | $\displaystyle \sum_{n=1}^\infty (-1)^{n+1} \frac{x^n}{n}$ | $(-1, 1]$ |
| $\arctan x$ | $\displaystyle \sum_{n=0}^\infty (-1)^n \frac{x^{2n+1}}{2n+1}$ | $[-1, 1]$ |

> [!EXAMPLE] Serie de potencias a partir de una conocida
> Hallar la serie de potencias para $f(x) = \frac{x}{1+x^2}$.
>
> **Paso 1:** Usar la serie geométrica $\frac{1}{1-u} = \sum_{n=0}^\infty u^n$ (para $|u| < 1$).
>
> **Paso 2:** Sustituir $u = -x^2$.
> $$\frac{1}{1+x^2} = \frac{1}{1-(-x^2)} = \sum_{n=0}^\infty (-x^2)^n = \sum_{n=0}^\infty (-1)^n x^{2n}$$
>
> **Paso 3:** Multiplicar por $x$.
> $$\frac{x}{1+x^2} = x \cdot \sum_{n=0}^\infty (-1)^n x^{2n} = \sum_{n=0}^\infty (-1)^n x^{2n+1}$$
>
> **Resultado:** $f(x) = \sum_{n=0}^\infty (-1)^n x^{2n+1}$ para $|x| < 1$.
>
> > [!WARNING]
> > Multiplicar o dividir series término a término solo es válido **dentro del radio de convergencia**.

---

## Aplicaciones en ingeniería

| Aplicación | Serie usada | Campo |
|:-----------|:------------|:------|
| Señales periódicas | **Series de Fourier** (senos y cosenos) | Telecomunicaciones, Audio |
| Solución de EDOs | **Series de potencias** | Mecánica, Circuitos |
| Análisis de errores | **Serie de Taylor** (aproximación) | Métodos numéricos |
| Procesamiento de señales | **Serie geométrica** (filtros digitales) | Control, DSP |
| Cálculo de $\pi$ | $\pi = 4\sum_{n=0}^\infty \frac{(-1)^n}{2n+1}$ (Leibniz) | Matemática computacional |

---

## Tabla de criterios: cuándo usar cada uno

| Situación | Criterio recomendado |
|:----------|:---------------------|
| $a_n$ tiene factoriales ($n!$) o exponenciales ($a^n$) | **Razón (D'Alembert)** |
| $a_n$ tiene potencias $n$-ésimas ($a_n = (b_n)^n$) | **Raíz (Cauchy)** |
| $a_n$ es racional ($P(n)/Q(n)$) | **Comparación al límite** |
| $a_n = f(n)$ con $f$ integrable fácil | **Integral** |
| Términos alternan signo | **Leibniz (alternadas)** |
| $a_n \not\to 0$ | **Término n-ésimo** (diverge) |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Apunte U6 (Ocampo) — Sucesiones | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 6.pdf` |
| Apunte U7 (Ocampo) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 7.pdf` |
| Teoría sucesiones (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/sucesiones .pdf` |
| Teoría series y criterios (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/series y criterios de convergencia .pdf` |
| Apunte Sucesiones (profes) | `Raw/.../AnM1/Teorías/Sucesiones.pdf` |
| Apunte Sucesiones y Series | `Raw/.../AnM1/Teorías/APUNTE SUCESIONES Y SERIES  12-6-23.pdf` |
| Tabla criterios convergencia | `Raw/.../AnM1/Teorías/Tabla_de_criterios_de_convergencia.pdf` |
| Clase repaso integrales + sucesiones | `Raw/.../AnM1/Teorías/Unidad 6 Sucesiones y Series/clase_repaso_integrales_sucesiones.pdf` |
| Clase 15 — Sucesiones | `Raw/.../AnM1/Teorías/Unidad 6 Sucesiones y Series/clase15_sucesiones.pdf` |
| Presentaciones U5 | `Raw/.../AnM1/Teorías/Presentaciores de clases teoricas/Unidad 5 - *` |
| TP Nº8 — Trabajo Práctico Nº8 (series) | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Trabajo Practico Nº8.pdf` |
| Ejercicios adicionales - Sucesiones y Series | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Sucesiones y Series.pdf` |
| Tp series y sucesiones (resuelto) | `Raw/.../1 matematica/PRACTICA/Análisis matemático I/Tp series y sucesiones (resuelto).pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Aplicaciones_Integral]] • **Siguiente:** [[Anm_Funciones_Varias_Variables]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
