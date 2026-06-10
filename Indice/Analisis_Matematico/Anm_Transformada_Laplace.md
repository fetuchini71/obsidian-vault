> [!NOTE] Navegación
> **Anterior:** [[Anm_Ecuaciones_Diferenciales]] • **Siguiente:** [[Anm_Variable_Compleja_Fourier]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Transformada de Laplace

## Índice

==toc==

---

> [!INFO]
> La transformada de Laplace convierte ecuaciones diferenciales en **ecuaciones algebraicas**. Resolver una EDO se reduce a despejar y aplicar la transformada inversa — una herramienta poderosa para circuitos, control, vibraciones y sistemas dinámicos. Es el puente entre el dominio del tiempo y el dominio de la frecuencia compleja $s$.

---

## Definición

$$ \mathcal{L}\{f(t)\} = F(s) = \int_0^\infty e^{-st} f(t) \, dt $$

La función $f(t)$ (dominio del tiempo, $t \geq 0$) se transforma en $F(s)$ (dominio de la frecuencia compleja $s = \sigma + i\omega$).

### Condiciones de existencia

$F(s)$ existe si:
1. $f$ es **continua a trozos** en $[0, \infty)$
2. $f$ es de **orden exponencial**: $|f(t)| \leq M e^{ct}$ para $t > T$

Bajo estas condiciones, la integral converge para $\operatorname{Re}(s) > c$.

> [!TIP] ¿Por qué Laplace?
> 1. **Condiciones iniciales incorporadas automáticamente** — no hay que resolver el sistema homogéneo + particular por separado
> 2. **Transforma EDO en ecuaciones algebraicas** — se despeja $Y(s)$ y luego se aplica la inversa
> 3. **Maneja funciones discontinuas** (escalón, impulso) sin dificultad
> 4. **Base del análisis de sistemas** en control, procesamiento de señales, circuitos

---

## Transformadas básicas

| $f(t)$ | $F(s) = \mathcal{L}\{f(t)\}$ | Condiciones |
|--------|------------------------------|-------------|
| $1$ | $\frac{1}{s}$ | $s > 0$ |
| $t^n$ ($n$ entero) | $\frac{n!}{s^{n+1}}$ | $s > 0$ |
| $e^{at}$ | $\frac{1}{s-a}$ | $s > a$ |
| $\sin(at)$ | $\frac{a}{s^2 + a^2}$ | $s > 0$ |
| $\cos(at)$ | $\frac{s}{s^2 + a^2}$ | $s > 0$ |
| $\sinh(at)$ | $\frac{a}{s^2 - a^2}$ | $s > \|a\|$ |
| $\cosh(at)$ | $\frac{s}{s^2 - a^2}$ | $s > \|a\|$ |
| $t^n e^{at}$ | $\frac{n!}{(s-a)^{n+1}}$ | $s > a$ |
| $e^{at}\sin(bt)$ | $\frac{b}{(s-a)^2 + b^2}$ | $s > a$ |
| $e^{at}\cos(bt)$ | $\frac{s-a}{(s-a)^2 + b^2}$ | $s > a$ |
| $t\sin(at)$ | $\frac{2as}{(s^2 + a^2)^2}$ | $s > 0$ |
| $t\cos(at)$ | $\frac{s^2 - a^2}{(s^2 + a^2)^2}$ | $s > 0$ |
| $\delta(t-a)$ (Delta de Dirac) | $e^{-as}$ | $a \geq 0$ |
| $u(t-a)$ (función escalón) | $\frac{e^{-as}}{s}$ | $s > 0$ |

> [!WARNING] ❌ Errores comunes con la tabla
> - $\mathcal{L}\{t^n\}$ usa $n!$, no $n$. Para $t^3$, es $3! = 6$, no $3$.
> - $\mathcal{L}\{\sin(at)\} = \frac{a}{s^2 + a^2}$ — la $a$ va en el numerador, no la $s$.
> - $\mathcal{L}\{\cos(at)\} = \frac{s}{s^2 + a^2}$ — aquí la $s$ va arriba.
> - Las condiciones de convergencia ($s > a$, $s > 0$) importan para la transformada inversa.

---

## Propiedades importantes

| Propiedad | Fórmula |
|-----------|---------|
| **Linealidad** | $\mathcal{L}\{af + bg\} = aF(s) + bG(s)$ |
| **Derivada** | $\mathcal{L}\{f'\} = sF(s) - f(0)$ |
| **Derivada n-ésima** | $\mathcal{L}\{f^{(n)}\} = s^n F(s) - s^{n-1}f(0) - \dots - f^{(n-1)}(0)$ |
| **Integral** | $\mathcal{L}\left\{\int_0^t f(\tau) d\tau\right\} = \frac{F(s)}{s}$ |
| **Traslación en $s$** | $\mathcal{L}\{e^{at}f(t)\} = F(s-a)$ |
| **Traslación en $t$** | $\mathcal{L}\{u(t-a)f(t-a)\} = e^{-as}F(s)$ |
| **Convolución** | $\mathcal{L}\{f * g\} = F(s)G(s)$, $(f*g)(t) = \int_0^t f(\tau)g(t-\tau)d\tau$ |
| **Escalado** | $\mathcal{L}\{f(at)\} = \frac{1}{a}F\left(\frac{s}{a}\right)$ |
| **Multiplicación por $t$** | $\mathcal{L}\{t f(t)\} = -F'(s)$ |
| **División por $t$** | $\mathcal{L}\left\{\frac{f(t)}{t}\right\} = \int_s^\infty F(u)\,du$ |
| **Función periódica** ($T$ período) | $\mathcal{L}\{f(t)\} = \frac{\int_0^T e^{-st}f(t)dt}{1 - e^{-sT}}$ |

> [!TIP] Propiedades útiles
> - La **derivada en $t$** es **multiplicación por $s$** en el dominio de Laplace (con C.I.)
> - La **integral en $t$** es **división por $s$** en el dominio de Laplace
> - La **convolución en $t$** es **multiplicación** en el dominio de Laplace
> - La **traslación en $s$** permite obtener transformadas de $e^{at}f(t)$ directamente de la tabla

---

## Ejemplos resueltos de transformadas directas

> [!EXAMPLE] 📐 Calcular $\mathcal{L}\{e^{3t}\sin(2t)\}$
>
> **Paso 1**: Identificar en la tabla: $e^{at}\sin(bt)$ con $a=3$, $b=2$.
>
> **Paso 2**: Usar la fórmula: $\mathcal{L}\{e^{at}\sin(bt)\} = \frac{b}{(s-a)^2 + b^2}$
>
> **Paso 3**: Sustituir:
> $$\mathcal{L}\{e^{3t}\sin(2t)\} = \frac{2}{(s-3)^2 + 4}$$

> [!EXAMPLE] 📐 Calcular $\mathcal{L}\{t^2 + 3e^{-t} + 4\cos(5t)\}$
>
> **Paso 1**: Por linealidad: $\mathcal{L}\{t^2\} + 3\mathcal{L}\{e^{-t}\} + 4\mathcal{L}\{\cos(5t)\}$
>
> **Paso 2**: Aplicar tabla:
> $$\mathcal{L}\{t^2\} = \frac{2!}{s^3} = \frac{2}{s^3}$$
> $$3\mathcal{L}\{e^{-t}\} = 3 \cdot \frac{1}{s+1}$$
> $$4\mathcal{L}\{\cos(5t)\} = 4 \cdot \frac{s}{s^2 + 25}$$
>
> **Paso 3**: Sumar:
> $$F(s) = \frac{2}{s^3} + \frac{3}{s+1} + \frac{4s}{s^2 + 25}$$

> [!EXAMPLE] 📐 Calcular $\mathcal{L}\{t\sin(2t)\}$ usando la propiedad de multiplicación por $t$
>
> **Paso 1**: $\mathcal{L}\{\sin(2t)\} = \frac{2}{s^2 + 4}$
>
> **Paso 2**: $\mathcal{L}\{t f(t)\} = -F'(s)$:
> $$\mathcal{L}\{t\sin(2t)\} = -\frac{d}{ds}\left(\frac{2}{s^2 + 4}\right) = -\frac{2 \cdot (-2s)}{(s^2+4)^2} = \frac{4s}{(s^2+4)^2}$$

---

## Transformada inversa y fracciones simples

$$ \mathcal{L}^{-1}\{F(s)\} = f(t) $$

El método principal es **descomponer $F(s)$ en fracciones simples** para que cada término coincida con la tabla.

### Casos de fracciones simples

| Forma de $F(s)$ | Descomposición |
|-----------------|----------------|
| $\frac{A}{s - a}$ | $\mathcal{L}^{-1} = A e^{at}$ |
| $\frac{A}{(s - a)^n}$ | $\mathcal{L}^{-1} = A \frac{t^{n-1}}{(n-1)!} e^{at}$ |
| $\frac{As + B}{s^2 + a^2}$ | Separar: $A\frac{s}{s^2 + a^2} + \frac{B}{a}\frac{a}{s^2 + a^2}$ |
| $\frac{As + B}{(s - a)^2 + b^2}$ | Completar cuadrado y usar traslación en $s$ |
| $\frac{A}{s^2(s + a)}$ | $\frac{A}{a^2}\left(\frac{1}{s} - \frac{1}{s+a} - \frac{a}{s^2}\right)$ |

### Diagrama de flujo: solución de EDO con Laplace

```
    ┌───────────────────────────┐
    │  EDO + C.I. en t          │
    │  a y'' + b y' + c y = g(t)│
    └──────────┬────────────────┘
               │
               ▼
    ┌───────────────────────────┐
    │  Aplicar L{} a ambos      │
    │  lados (linealidad +      │
    │  propiedad derivada)      │
    └──────────┬────────────────┘
               │
               ▼
    ┌───────────────────────────┐
    │  Ecuación algebraica      │
    │  en Y(s):                 │
    │  a[s²Y - s y(0) - y'(0)] │
    │  + b[sY - y(0)] + cY     │
    │  = G(s)                   │
    └──────────┬────────────────┘
               │
               ▼
    ┌───────────────────────────┐
    │  Despejar Y(s)            │
    │  Y(s) = R(s) / Q(s)       │
    └──────────┬────────────────┘
               │
               ▼
    ┌───────────────────────────┐
    │  Fracciones simples       │
    │  Descomponer R(s)/Q(s)    │
    │  en términos de la tabla  │
    └──────────┬────────────────┘
               │
               ▼
    ┌───────────────────────────┐
    │  Aplicar L^{-1}           │
    │  y(t) = solución final    │
    └───────────────────────────┘
```

> [!EXAMPLE] 📐 Transformada inversa con fracciones simples
> Hallar $\mathcal{L}^{-1}\left\{\frac{3s - 2}{s^2 - 4}\right\}$.
>
> **Paso 1**: Factorizar denominador: $s^2 - 4 = (s-2)(s+2)$
>
> **Paso 2**: Descomponer:
> $$\frac{3s - 2}{(s-2)(s+2)} = \frac{A}{s-2} + \frac{B}{s+2}$$
>
> **Paso 3**: Hallar $A$ y $B$:
> $$3s - 2 = A(s+2) + B(s-2)$$
> $$s=2: 6-2 = 4A \implies A = 1$$
> $$s=-2: -6-2 = -4B \implies B = 2$$
>
> **Paso 4**: Aplicar inversa:
> $$\mathcal{L}^{-1}\left\{\frac{1}{s-2} + \frac{2}{s+2}\right\} = e^{2t} + 2e^{-2t}$$

---

## Solución de EDO con Laplace

### Metodología paso a paso

1. **Aplicar $\mathcal{L}$** a ambos lados de la EDO
2. **Usar las propiedades de la derivada** (con condiciones iniciales incluidas)
3. **Despejar $Y(s)$**
4. **Aplicar $\mathcal{L}^{-1}$** para obtener $y(t)$

> [!EXAMPLE] 📐 Resolver $y'' + 4y = 12t$, $y(0)=0$, $y'(0)=7$ con Laplace
>
> **Paso 1**: Aplicar $\mathcal{L}$:
> $$\mathcal{L}\{y''\} + 4\mathcal{L}\{y\} = 12\mathcal{L}\{t\}$$
>
> **Paso 2**: Usar propiedades de derivada y tabla:
> $$(s^2Y(s) - s\cdot0 - 7) + 4Y(s) = 12 \cdot \frac{1}{s^2}$$
> $$s^2Y(s) - 7 + 4Y(s) = \frac{12}{s^2}$$
>
> **Paso 3**: Despejar $Y(s)$:
> $$(s^2 + 4)Y(s) = \frac{12}{s^2} + 7 = \frac{12 + 7s^2}{s^2}$$
> $$Y(s) = \frac{7s^2 + 12}{s^2(s^2 + 4)}$$
>
> **Paso 4**: Fracciones simples:
> $$\frac{7s^2 + 12}{s^2(s^2 + 4)} = \frac{A}{s} + \frac{B}{s^2} + \frac{Cs + D}{s^2 + 4}$$
>
> Multiplicando: $7s^2 + 12 = A s(s^2+4) + B(s^2+4) + (Cs+D)s^2$
>
> $s=0$: $12 = 4B \implies B = 3$
>
> Coeficientes de $s^3$: $0 = A + C \implies C = -A$
>
> Coeficientes de $s^2$: $7 = B + D = 3 + D \implies D = 4$
>
> Coeficientes de $s$: $0 = 4A \implies A = 0$, entonces $C = 0$
>
> $$Y(s) = \frac{3}{s^2} + \frac{4}{s^2 + 4}$$
>
> **Paso 5**: Aplicar $\mathcal{L}^{-1}$:
> $$y(t) = 3t + 2\sin(2t)$$
>
> (pues $\mathcal{L}^{-1}\{\frac{4}{s^2+4}\} = 2\mathcal{L}^{-1}\{\frac{2}{s^2+4}\} = 2\sin(2t)$)

> [!EXAMPLE] 📐 Resolver $y'' + 6y' + 9y = e^{-3t}$, $y(0)=0$, $y'(0)=1$ con Laplace
>
> **Paso 1**: Aplicar $\mathcal{L}$:
> $$[s^2Y - s\cdot0 - 1] + 6[sY - 0] + 9Y = \frac{1}{s+3}$$
>
> **Paso 2**: Despejar:
> $$(s^2 + 6s + 9)Y - 1 = \frac{1}{s+3}$$
> $$(s+3)^2 Y = 1 + \frac{1}{s+3} = \frac{s+4}{s+3}$$
> $$Y(s) = \frac{s+4}{(s+3)^3}$$
>
> **Paso 3**: Fracciones simples:
> $$\frac{s+4}{(s+3)^3} = \frac{A}{s+3} + \frac{B}{(s+3)^2} + \frac{C}{(s+3)^3}$$
>
> $s+4 = A(s+3)^2 + B(s+3) + C$
>
> $s=-3$: $1 = C$
>
> $s^2$: $0 = A \implies A = 0$
>
> $s = 0$: $4 = 9A + 3B + C = 0 + 3B + 1 \implies B = 1$
>
> $$Y(s) = \frac{1}{(s+3)^2} + \frac{1}{(s+3)^3}$$
>
> **Paso 4**: $\mathcal{L}^{-1}$:
> $$y(t) = t e^{-3t} + \frac{t^2}{2} e^{-3t}$$

> [!WARNING] ❌ Errores comunes con Laplace
> - **No olvidar las C.I.**: la propiedad $\mathcal{L}\{y'\} = sY(s) - y(0)$ requiere el valor inicial
> - **Fracciones simples incompletas**: factorizar completamente el denominador antes de descomponer
> - **Raíces repetidas**: si el denominador tiene $(s-a)^n$, se necesitan $n$ términos: $\frac{A_1}{s-a} + \frac{A_2}{(s-a)^2} + \dots + \frac{A_n}{(s-a)^n}$
> - **La función escalón**: no olvidar la traslación en $t$ cuando aparecen términos con $e^{-as}$ en $F(s)$
> - **Verificar**: siempre derivar el resultado y volver a la EDO original

---

## Aplicaciones en ingeniería

### Control automático (función de transferencia)

Dado un sistema: $a y'' + b y' + c y = g(t)$ con C.I. cero:

$$G(s) = \frac{Y(s)}{G(s)} = \frac{1}{as^2 + bs + c}$$

La función de transferencia $H(s)$ caracteriza completamente al sistema. La respuesta es:

$$Y(s) = H(s) \cdot G(s)$$

### Circuitos RLC

| Elemento | Relación $v$-$i$ en el tiempo | Relación en $s$ (C.I.=0) |
|----------|------------------------------|--------------------------|
| Resistor $R$ | $v = Ri$ | $V(s) = R I(s)$ |
| Inductor $L$ | $v = L\frac{di}{dt}$ | $V(s) = sL I(s) - L i(0)$ |
| Capacitor $C$ | $i = C\frac{dv}{dt}$ | $I(s) = sC V(s) - C v(0)$ |

> [!EXAMPLE] 🔧 Circuito RL con escalón
> Un circuito RL serie con $R=2\,\Omega$, $L=1\,H$ se conecta a una fuente $E(t) = 10\,u(t)$ V. Hallar $I(t)$ si $I(0)=0$.
>
> **Ecuación**: $L I' + R I = E(t) \implies I' + 2I = 10u(t)$
>
> **Laplace**: $sI(s) - 0 + 2I(s) = \frac{10}{s}$
> $$I(s)(s+2) = \frac{10}{s}$$
> $$I(s) = \frac{10}{s(s+2)} = \frac{5}{s} - \frac{5}{s+2}$$
>
> **Inversa**: $I(t) = 5 - 5e^{-2t}$ (para $t \geq 0$)
>
> La corriente tiende a $5\,A$ en estado estacionario con constante de tiempo $\tau = 0.5\,s$.

### Vibraciones mecánicas

$$m x'' + c x' + kx = F(t)$$

Con Laplace (C.I. $x(0)=x_0$, $x'(0)=v_0$):

$$(ms^2 + cs + k)X(s) = F(s) + m x_0 s + m v_0 + c x_0$$

$$X(s) = \frac{F(s) + (ms + c)x_0 + m v_0}{ms^2 + cs + k}$$

La respuesta del sistema se compone de:
- **Respuesta transitoria**: dada por los polos de la función de transferencia
- **Respuesta estacionaria**: dada por la entrada $F(s)$ después de que los transitorios decaen

### Procesamiento de señales

La convolución en el tiempo $(f*g)(t)$ se convierte en multiplicación en $s$:

$$\mathcal{L}\{f * g\} = F(s)G(s)$$

Esto es fundamental para:
- **Filtrado**: la salida de un sistema LTI es la convolución de la entrada con la respuesta al impulso
- **Ecualización**: diseñar $H(s)$ para compensar la respuesta del canal

### Sistema masa-resorte con fuerza impulsiva

> [!EXAMPLE] 🔧 Respuesta a un martillazo (Delta de Dirac)
> Un sistema masa-resorte $x'' + 9x = 3\delta(t-2)$, $x(0)=0$, $x'(0)=0$.
>
> **Laplace**: $s^2X(s) + 9X(s) = 3e^{-2s}$
> $$X(s) = \frac{3e^{-2s}}{s^2 + 9}$$
>
> **Inversa** (con traslación en $t$):
> $$x(t) = \sin(3(t-2)) \cdot u(t-2)$$
>
> El sistema oscila solo después del impacto en $t=2$, con amplitud 1.

---

## Conexión con Álgebra Lineal

| Concepto en Laplace | Concepto en Álgebra Lineal |
|--------------------|---------------------------|
| $\mathcal{L}$ es un operador lineal | Transformación lineal entre espacios de funciones |
| $\mathcal{L}\{af + bg\} = aF + bG$ | Linealidad |
| Convolución $(f*g)(t)$ | Producto en el álgebra de convolución |
| Fracciones simples | Descomposición en suma de fracciones parciales (espacio de polinomios) |
| Polos de $F(s)$ | Raíces del denominador (autovalores del sistema) |
| Función de transferencia $H(s)$ | Operador inverso en dominio $s$ |

> [!TIP] Álgebra y Laplace
> Entender que $\mathcal{L}$ es una **transformación lineal** ayuda a ver por qué funciona la superposición. Además, los **polos** de $F(s)$ (raíces del denominador) son análogos a los **autovalores** en sistemas de EDO — determinan el comportamiento cualitativo de la solución.

---

## Consejos de estudio

> [!TIP] 📖 Cómo dominar Laplace
> 1. **Memoriza la tabla básica**: las 10 transformadas más comunes deberían saberse de memoria
> 2. **Practica fracciones simples**: es el paso más tedioso y donde más errores se cometen
> 3. **Completa cuadrados**: muchas $F(s)$ requieren completar cuadrados en el denominador para usar $\frac{b}{(s-a)^2 + b^2}$
> 4. **Verifica con C.I. nulas**: si todas las C.I. son cero, la transformada de la EDO es simplemente $H(s)G(s)$
> 5. **Dualidad**: aprender a ver la correspondencia: derivada ↔ $s$, integral ↔ $1/s$, convolución ↔ producto

> [!WARNING] ⚠️ Recordatorios importantes
> - La transformada de Laplace solo está definida para $t \geq 0$
> - Si la EDO tiene coeficientes **variables**, Laplace no es útil directamente (usar series de potencias)
> - La función de Heaviside $u(t-a)$ cambia el dominio de la función — cuidado con los límites de integración
> - Siempre verificar que el denominador esté **completamente factorizado** antes de descomponer en fracciones simples
> - La transformada inversa es **única** (salvo en puntos de discontinuidad) — si obtuviste algo que está en la tabla, es correcto

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Tabla de Transformada de Laplace | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Tabla de Transformada de Laplace (1)_...pdf` |
| Ecuación de calor y onda (EDP + Laplace) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/Teoria_/Ecuación de calor y onda_/ResoluciónEcOndayCalor.pdf` |
| U5 parte I y II (incluye Laplace) | `Raw/.../1 matematica/TEORIA/Análisis matemático III/teoría_/U5 parte I.pdf` y `U5 parte II.pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Ecuaciones_Diferenciales]] • **Siguiente:** [[Anm_Variable_Compleja_Fourier]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
