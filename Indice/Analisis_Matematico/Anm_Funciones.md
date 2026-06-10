> [!NOTE] Navegación
> **Anterior:** — • **Siguiente:** [[Anm_Limites_Continuidad]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Funciones

## Índice

==toc==

---

> [!INFO]
> Las funciones son el vocabulario del cálculo. Todo lo que sigue — límites, derivadas, integrales — opera sobre funciones. Sin dominar este tema el resto es cuesta arriba. En ingeniería, las funciones modelan todo: desde la descarga de un capacitor hasta la deformación de una viga.

---

## ¿Qué son?

Una **función** $f: A \to B$ es una regla que asigna a cada elemento de $A$ (dominio) **exactamente un** elemento de $B$ (codominio). En una variable: $y = f(x)$.

```
     Dominio (A)            Codominio (B)
   ┌──────────┐            ┌──────────┐
   │  x₁ ─────┼───────────▶│  y₁      │
   │  x₂ ─────┼─── f(x) ──▶│  y₂      │
   │  x₃ ─────┼───────────▶│  y₃      │
   └──────────┘            └──────────┘
   Cada x ∈ A → exactamente un y ∈ B
```

> [!TIP] Visualización mental
> Pensá una función como una **máquina**: metés un número $x$ por un extremo, la máquina aplica la regla $f$, y por el otro extremo sale $f(x)$. Si metés el mismo $x$ dos veces, siempre sale el mismo resultado.

---

## Conceptos clave

| Concepto | Definición |
|----------|-----------|
| **Dominio** | Conjunto de $x$ para los que $f(x)$ está definida |
| **Imagen/Rango** | Conjunto de todos los valores $f(x)$ que toma |
| **Función inyectiva** | $f(a) = f(b) \Rightarrow a = b$ (uno a uno) |
| **Función suryectiva** | $\forall y \in B, \exists x : f(x) = y$ (sobre todo el codominio) |
| **Función biyectiva** | Inyectiva + suryectiva (tiene inversa) |
| **Composición** | $(f \circ g)(x) = f(g(x))$ |
| **Función inversa** | $f^{-1}(y) = x \iff f(x) = y$ |
| **Paridad** | Par: $f(-x)=f(x)$ • Impar: $f(-x)=-f(x)$ |
| **Función periódica** | $f(x+T)=f(x)$ para todo $x$ |

> [!WARNING] Error común: dominio vs. imagen
> No confundir dominio con imagen. El dominio es el conjunto de **entradas** permitidas; la imagen es el conjunto de **salidas** que la función realmente produce. Ejemplo: $f(x)=x^2$ tiene dominio $\mathbb{R}$ pero imagen $[0,\infty)$.

---

## Tipos de funciones

- **Polinómicas**: $f(x) = a_n x^n + \dots + a_0$ (grado $n$)
- **Racionales**: $f(x) = P(x)/Q(x)$ (cociente de polinomios)
- **Trigonométricas**: $\sin x, \cos x, \tan x, \sec x, \csc x, \cot x$
- **Exponenciales**: $f(x) = a^x$ (con $a > 0$, $a \neq 1$)
- **Logarítmicas**: $f(x) = \log_a x$ (inversa de $a^x$)
- **Hiperbólicas**: $\sinh x, \cosh x, \tanh x$
- **A trozos (piecewise)**: definidas por intervalos
- **Paramétricas**: $(x(t), y(t))$
- **Polares**: $r = f(\theta)$
- **Valor absoluto**: $f(x)=|x|$ (función a trozos con esquina en $x=0$)

> [!TIP] Reconocimiento visual rápido
> - **Lineal** $ax+b$ → recta
> - **Cuadrática** $ax^2+bx+c$ → parábola
> - **Seno/Coseno** → ondas
> - **Exponencial** $a^x$ → crecimiento/decaimiento rápido
> - **Logarítmica** $\log x$ → crecimiento lento, nunca negativa en $x>0$

---

## Operaciones entre funciones

Dadas $f$ y $g$ con dominios $D_f$ y $D_g$:

| Operación | Definición | Dominio |
|-----------|-----------|---------|
| Suma | $(f+g)(x)=f(x)+g(x)$ | $D_f \cap D_g$ |
| Resta | $(f-g)(x)=f(x)-g(x)$ | $D_f \cap D_g$ |
| Producto | $(f \cdot g)(x)=f(x)\cdot g(x)$ | $D_f \cap D_g$ |
| Cociente | $(f/g)(x)=f(x)/g(x)$ | $D_f \cap D_g,\ g(x)\neq 0$ |
| Composición | $(f \circ g)(x)=f(g(x))$ | $x \in D_g,\ g(x)\in D_f$ |

> [!EXAMPLE] Composición de funciones
> Hallar $(f \circ g)(x)$ y su dominio:
> $$f(x) = \sqrt{x}, \quad g(x) = 2x - 1$$
>
> **Paso 1:** Escribir la composición.
> $$(f \circ g)(x) = f(g(x)) = f(2x-1) = \sqrt{2x - 1}$$
>
> **Paso 2:** Determinar el dominio.
> El dominio de $f$ es $x \geq 0$. Entonces necesitamos $2x-1 \geq 0$.
> $$2x - 1 \geq 0 \implies x \geq \frac{1}{2}$$
>
> **Resultado:** $(f \circ g)(x) = \sqrt{2x-1}$, con dominio $\left[\frac{1}{2}, \infty\right)$.
>
> ---
>
> Hallar $(g \circ f)(x)$ y su dominio:
> $$(g \circ f)(x) = g(f(x)) = g(\sqrt{x}) = 2\sqrt{x} - 1$$
>
> Dominio de $f$: $x \geq 0$, y $g$ acepta cualquier real.
> **Resultado:** $(g \circ f)(x) = 2\sqrt{x} - 1$, con dominio $[0, \infty)$.
>
> > [!WARNING] ¡Ojo!
> > La composición **no es conmutativa**: $(f \circ g)(x) \neq (g \circ f)(x)$ en general.

---

## Dominio de funciones: casos clave

Saber hallar el dominio es fundamental para [[Anm_Limites_Continuidad]] y [[Anm_Derivadas]].

| Tipo de función | Restricción para el dominio |
|:----------------|:---------------------------|
| Polinómica | $\mathbb{R}$ (todo real) |
| Racional $P/Q$ | $Q(x) \neq 0$ |
| Raíz par $\sqrt[n]{f(x)}$ | $f(x) \geq 0$ |
| Logarítmica $\log_a f(x)$ | $f(x) > 0$ |
| Tangente $\tan x$ | $x \neq \frac{\pi}{2} + k\pi$ |
| Arco seno $\arcsin x$ | $-1 \leq x \leq 1$ |
| Arco coseno $\arccos x$ | $-1 \leq x \leq 1$ |

> [!EXAMPLE] Cálculo de dominio
> Hallar el dominio de $f(x) = \frac{\sqrt{x-1}}{\ln(2-x)}$.
>
> **Paso 1:** Raíz en el numerador → $x - 1 \geq 0 \Rightarrow x \geq 1$.
>
> **Paso 2:** Logaritmo en el denominador → $2 - x > 0 \Rightarrow x < 2$.
>
> **Paso 3:** Denominador no nulo → $\ln(2-x) \neq 0 \Rightarrow 2-x \neq 1 \Rightarrow x \neq 1$.
>
> **Paso 4:** Intersección de condiciones:
> - $x \geq 1$
> - $x < 2$
> - $x \neq 1$
>
> **Resultado:** $D_f = (1, 2)$.
>
> ```
>   Condiciones:
>   x ≥ 1:     ███████████████████████████████████▶
>   x < 2:     ◀━━━━━━━━━━━━━━━━━━━━━━━━━
>   x ≠ 1:     ╳
>   Dominio:      (━━━━━━━━━━━)
>               1             2
> ```

---

## Gráfica de funciones

La gráfica de $f$ es el conjunto $\{(x, f(x)) : x \in D_f\}$ en el plano cartesiano.

### Transformaciones de gráficas

Partiendo de $y = f(x)$:

| Transformación | Nueva función | Efecto visual |
|:---------------|:-------------|:--------------|
| Desplazamiento vertical | $y = f(x) + k$ | Sube ($k>0$) o baja ($k<0$) |
| Desplazamiento horizontal | $y = f(x - h)$ | Se desplaza $h$ a la derecha |
| Reflexión en $x$ | $y = -f(x)$ | Invierte verticalmente |
| Reflexión en $y$ | $y = f(-x)$ | Invierte horizontalmente |
| Estiramiento vertical | $y = a f(x)$ | Estira ($a>1$) o comprime ($0<a<1$) |
| Estiramiento horizontal | $y = f(bx)$ | Comprime ($b>1$) o estira ($0<b<1$) |

```
                 f(x) + 2 (sube 2)
                 ┌┈┈┈┈┐
                ┌┈┈┈┈┐
               ┌┈┈┈┈┐ ─── f(x) (original)
              ┌┈┈┈┈┐
             ┌┈┈┈┈┐
             └┈┈┈┈┘ ─── f(x) - 2 (baja 2)
```

> [!TIP] Regla mnemotécnica
> Los desplazamientos **horizontales** son "contra-intuitivos": $f(x-2)$ desplaza la gráfica **a la derecha** (no a la izquierda). Pensá: para que la función "vea" el mismo valor que antes en $x$, necesitamos $x-2$ — o sea, movernos 2 a la derecha.

---

## Funciones inversas

Si $f$ es biyectiva, existe $f^{-1}$ tal que:

$$f^{-1}(f(x)) = x \quad \text{y} \quad f(f^{-1}(y)) = y$$

La gráfica de $f^{-1}$ es la reflexión de la gráfica de $f$ sobre la recta $y = x$.

> [!EXAMPLE] Función inversa
> Hallar $f^{-1}(x)$ para $f(x) = \frac{2x+1}{x-3}$.
>
> **Paso 1:** Escribir $y = f(x)$.
> $$y = \frac{2x+1}{x-3}$$
>
> **Paso 2:** Intercambiar $x$ e $y$.
> $$x = \frac{2y+1}{y-3}$$
>
> **Paso 3:** Despejar $y$.
> $$x(y-3) = 2y+1 \implies xy - 3x = 2y + 1$$
> $$xy - 2y = 3x + 1 \implies y(x-2) = 3x + 1$$
> $$y = \frac{3x+1}{x-2}$$
>
> **Resultado:** $f^{-1}(x) = \frac{3x+1}{x-2}$, con dominio $\mathbb{R} \setminus \{2\}$.
>
> **Verificación:**
> $$f(f^{-1}(x)) = \frac{2(\frac{3x+1}{x-2}) + 1}{(\frac{3x+1}{x-2}) - 3} = \frac{\frac{6x+2 + x-2}{x-2}}{\frac{3x+1 - 3x+6}{x-2}} = \frac{7x}{7} = x \; \checkmark$$

---

## Funciones en ingeniería

| Aplicación | Función típica | Rama |
|:-----------|:--------------|:-----|
| Decaimiento radiactivo | $N(t) = N_0 e^{-\lambda t}$ | Exponencial |
| Circuito RC (carga) | $V(t) = V_0(1 - e^{-t/RC})$ | Exponencial |
| Movimiento armónico | $x(t) = A \sin(\omega t + \phi)$ | Trigonométrica |
| Ley de enfriamiento de Newton | $T(t) = T_a + (T_0 - T_a) e^{-kt}$ | Exponencial |
| Esfuerzo-deformación | $\sigma = E \varepsilon$ (zona elástica) | Lineal |
| Resonancia en circuitos | $V(\omega) = \frac{V_0}{\sqrt{(1-\omega^2LC)^2 + (\omega RC)^2}}$ | Racional/polinómica |

---

## Tabla resumen: funciones elementales

| Nombre | Expresión | Dominio | Imagen | Asíntotas |
|:-------|:----------|:--------|:-------|:----------|
| Constante | $f(x)=c$ | $\mathbb{R}$ | $\{c\}$ | — |
| Lineal | $f(x)=mx+b$ | $\mathbb{R}$ | $\mathbb{R}$ | — |
| Cuadrática | $f(x)=ax^2+bx+c$ | $\mathbb{R}$ | $[k,\infty)$ o $(-\infty,k]$ | — |
| Exponencial | $f(x)=a^x$ | $\mathbb{R}$ | $(0,\infty)$ | $y=0$ (AH) |
| Logarítmica | $f(x)=\log_a x$ | $(0,\infty)$ | $\mathbb{R}$ | $x=0$ (AV) |
| Seno | $f(x)=\sin x$ | $\mathbb{R}$ | $[-1,1]$ | — |
| Coseno | $f(x)=\cos x$ | $\mathbb{R}$ | $[-1,1]$ | — |
| Tangente | $f(x)=\tan x$ | $\mathbb{R}\setminus\{\frac{\pi}{2}+k\pi\}$ | $\mathbb{R}$ | $x=\frac{\pi}{2}+k\pi$ (AV) |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Apunte Unidad 1 (Ocampo) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 1.pdf` |
| Teoría Funciones (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/funciones.pdf` |
| Apunte de clase Funciones (profes) | `Raw/.../AnM1/Teorías/Funciones.pdf` |
| Clase 1 funciones - 10-3 | `Raw/.../AnM1/Teorías/Unidad 1 Funciones/clase 1 funciones- 10-3.pdf` |
| Clase 2 - 12-3 | `Raw/.../AnM1/Teorías/Unidad 1 Funciones/clase 2- 12-3.pdf` |
| Clase 3 - parte 1 | `Raw/.../AnM1/Teorías/Unidad 1 Funciones/clase 3 - parte 1.pdf` |
| Clase 3 - parte 2 | `Raw/.../AnM1/Teorías/Unidad 1 Funciones/clase 3 - parte 2.pdf` |
| Apuntes de clase U1 (4 clases) | `Raw/.../AnM1/Teorías/Apuntes de clase UNIDAD 1/` |
| Presentaciones teóricas U1 | `Raw/.../AnM1/Teorías/Presentaciores de clases teoricas/Unidad 1 - *` |
| Material teórico Unidad 1 | `Raw/.../AnM1/Teorías/Material teórico/Unidad1_Funciones.pdf` |
| TP0 Análisis Matemático | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TP0 Análisis Matemático.pdf` |
| TP1 Funciones 2026 | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TP1_Funciones_2026.pdf` |
| Ejercicios adicionales - Funciones | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Funciones.pdf` |
| Autoevaluación de funciones (y resolución) | `Raw/.../1 matematica/PRACTICA/Análisis matemático I/autoevaluaciones/1.1 Autoevaluación de funciones.pdf` |
| Resumen unidad 1 (PPT) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/resumen unidad 1.pptx` |

---

> [!NOTE] Navegación
> **Anterior:** — • **Siguiente:** [[Anm_Limites_Continuidad]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
