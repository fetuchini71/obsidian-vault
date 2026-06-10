> [!NOTE] Navegación
> **Anterior:** [[Anm_Funciones]] • **Siguiente:** [[Anm_Derivadas]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Límites y Continuidad

## Índice

==toc==

---

> [!INFO]
> El límite es el concepto fundacional del cálculo — la idea de "acercarse tanto como quieras" sin llegar. Con límites definimos derivada, integral y continuidad.
> *"Los límites son la máquina; las derivadas y las integrales son lo que fabrica la máquina."*
>
> En ingeniería, los límites aparecen en: velocidad instantánea (derivada), área bajo curvas (integral), comportamiento asintótico de circuitos, y estabilidad de sistemas de control.

---

## Límite de una función

$$\lim_{x \to a} f(x) = L$$

Significa que $f(x)$ se acerca arbitrariamente a $L$ cuando $x$ se acerca a $a$ (sin ser igual a $a$).

```
        f(x)
          ▲
        L ────────•════════════════════
          │      ╱
          │    ╱
          │  ╱
          │╱
          ──•─────────────────▶ x
            a
       A medida que x → a,
       f(x) → L
```

> [!WARNING] Error común: el límite NO es f(a)
> El límite cuando $x \to a$ existe aunque $f(a)$ no esté definida. El límite mira el **comportamiento alrededor** de $a$, no el valor **en** $a$. Esta distinción es clave para entender la continuidad.

### Límites laterales

- **Límite por izquierda**: $\displaystyle \lim_{x \to a^-} f(x)$ (valores menores que $a$)
- **Límite por derecha**: $\displaystyle \lim_{x \to a^+} f(x)$ (valores mayores que $a$)
- El límite **existe** si y solo si ambos laterales existen y son iguales:

$$\lim_{x \to a} f(x) = L \iff \lim_{x \to a^-} f(x) = \lim_{x \to a^+} f(x) = L$$

```
          f(x)
           ▲
           │    ╱╲
           │   ╱  ╲
         L │══╝    ╚══
           │        ╲
           │         ╲
           ─────────────────▶ x
                a
        x → a⁻ (por izquierda): f(x) → L
        x → a⁺ (por derecha):   f(x) → L
        El límite existe porque ambos convergen a L
```

> [!EXAMPLE] Límite con función a trozos
> Dada $f(x) = \begin{cases} x^2, & x < 1 \\ 2x - 1, & x \geq 1 \end{cases}$, hallar $\lim_{x \to 1} f(x)$.
>
> **Paso 1:** Límite por izquierda ($x \to 1^-$).
> Usamos $f(x) = x^2$ porque $x < 1$:
> $$\lim_{x \to 1^-} f(x) = \lim_{x \to 1^-} x^2 = 1^2 = 1$$
>
> **Paso 2:** Límite por derecha ($x \to 1^+$).
> Usamos $f(x) = 2x - 1$ porque $x \geq 1$:
> $$\lim_{x \to 1^+} f(x) = \lim_{x \to 1^+} (2x - 1) = 2(1) - 1 = 1$$
>
> **Paso 3:** Comparar laterales.
> $\lim_{x \to 1^-} f(x) = 1$ y $\lim_{x \to 1^+} f(x) = 1$. Son iguales.
>
> **Resultado:** $\lim_{x \to 1} f(x) = 1$.
>
> > [!TIP]
> > Cuando trabajes con funciones a trozos, **siempre** calculá los límites laterales por separado. Si coinciden, el límite existe.

---

### Propiedades algebraicas

Si $\lim_{x \to a} f(x) = L$ y $\lim_{x \to a} g(x) = M$:

| Propiedad | Fórmula |
|:----------|:--------|
| Suma | $\lim [f \pm g] = L \pm M$ |
| Producto | $\lim [f \cdot g] = L \cdot M$ |
| Cociente | $\lim [f/g] = L/M$ (si $M \neq 0$) |
| Potencia | $\lim [f(x)]^n = L^n$ |
| Raíz | $\lim \sqrt[n]{f(x)} = \sqrt[n]{L}$ (si $L \geq 0$ para $n$ par) |
| Constante por función | $\lim [c \cdot f(x)] = c \cdot L$ |

> [!WARNING] Cuidado con la propiedad del cociente
> Solo funciona si $\lim g(x) \neq 0$. Si el denominador tiende a 0, tenés una **indeterminación** y necesitás técnicas especiales (factorización, racionalización, L'Hôpital).

### Límites notables

Estos límites aparecen constantemente en [[Anm_Derivadas]] y [[Anm_Integrales]]:

$$\displaystyle \lim_{x \to 0} \frac{\sin x}{x} = 1$$

$$\displaystyle \lim_{x \to 0} \frac{1 - \cos x}{x} = 0$$

$$\displaystyle \lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e$$

$$\displaystyle \lim_{x \to 0} \frac{e^x - 1}{x} = 1$$

$$\displaystyle \lim_{x \to 0} \frac{\ln(1+x)}{x} = 1$$

> [!EXAMPLE] Aplicación de límite notable
> Hallar $\displaystyle \lim_{x \to 0} \frac{\sin(3x)}{2x}$.
>
> **Paso 1:** Reescribir para aplicar el límite notable.
> $$\frac{\sin(3x)}{2x} = \frac{3}{2} \cdot \frac{\sin(3x)}{3x}$$
>
> **Paso 2:** Sustituir $u = 3x$. Cuando $x \to 0$, $u \to 0$.
> $$\lim_{x \to 0} \frac{\sin(3x)}{2x} = \frac{3}{2} \cdot \lim_{u \to 0} \frac{\sin u}{u} = \frac{3}{2} \cdot 1 = \frac{3}{2}$$
>
> **Resultado:** $\displaystyle \lim_{x \to 0} \frac{\sin(3x)}{2x} = \frac{3}{2}$.

---

### Límites infinitos y en el infinito

| Tipo | Notación | Significado |
|:-----|:---------|:------------|
| Límite infinito | $\lim_{x \to a} f(x) = \infty$ | $f(x)$ crece sin cota cerca de $a$ |
| Límite en el infinito | $\lim_{x \to \infty} f(x) = L$ | $f(x)$ se acerca a $L$ cuando $x$ crece |
| Asíntota vertical | $\lim_{x \to a^{\pm}} f(x) = \pm\infty$ | Recta $x = a$ |
| Asíntota horizontal | $\lim_{x \to \pm\infty} f(x) = L$ | Recta $y = L$ |

---

## Indeterminaciones

Son expresiones que no pueden evaluarse directamente:

| Indeterminación | Ejemplo | Técnica común |
|:----------------|:--------|:--------------|
| $0/0$ | $\frac{x^2-1}{x-1}$ en $x=1$ | Factorizar y simplificar |
| $\infty/\infty$ | $\frac{3x^2+1}{2x^2-x}$ | Dividir por mayor potencia |
| $0 \cdot \infty$ | $x \cdot \ln x$ en $x=0^+$ | Convertir a $0/0$ o $\infty/\infty$ |
| $\infty - \infty$ | $\sqrt{x^2+x} - x$ | Racionalizar |
| $1^\infty$ | $(1+1/x)^x$ | Aplicar límite de $e$ |
| $0^0$ | $x^x$ en $x=0^+$ | Usar logaritmo |
| $\infty^0$ | $(1+1/x)^{\sqrt{x}}$ | Usar logaritmo |

> [!EXAMPLE] Indeterminación $0/0$ por factorización
> Hallar $\displaystyle \lim_{x \to 2} \frac{x^2 - 5x + 6}{x^2 - 4}$.
>
> **Paso 1:** Evaluar directamente (da $0/0$).
>
> **Paso 2:** Factorizar numerador y denominador.
> $$x^2 - 5x + 6 = (x-2)(x-3)$$
> $$x^2 - 4 = (x-2)(x+2)$$
>
> **Paso 3:** Simplificar el factor $(x-2)$.
> $$\lim_{x \to 2} \frac{(x-2)(x-3)}{(x-2)(x+2)} = \lim_{x \to 2} \frac{x-3}{x+2}$$
>
> **Paso 4:** Evaluar.
> $$\frac{2-3}{2+2} = \frac{-1}{4}$$
>
> **Resultado:** $\displaystyle \lim_{x \to 2} \frac{x^2 - 5x + 6}{x^2 - 4} = -\frac{1}{4}$.
>
> > [!TIP]
> > Cuando veas $0/0$ con polinomios, **factorizá**. El factor que anula es siempre un divisor del polinomio (Teorema del Factor).

---

## Continuidad

Una función es **continua en $x = a$** si:

1. $f(a)$ está definida
2. $\displaystyle \lim_{x \to a} f(x)$ existe
3. $\displaystyle \lim_{x \to a} f(x) = f(a)$

```
Función CONTINUA:            Función DISCONTINUA:
      f(x)                       f(x)
        ▲                          ▲
        │      •                    │      •  hueco
        │    ╱                      │    ╱╲
        │  ╱                        │  ╱  ╲
        │╱ •                        │╱    •───
        ──────────▶ x                ──────────▶ x
    Todo conectado              Hay un salto/hueco
```

### Tipos de discontinuidad

| Tipo | Descripción | Ejemplo |
|:-----|:------------|:--------|
| **Evitable** | $\lim$ existe pero $\neq f(a)$ o $f(a)$ no definida | $(\sin x)/x$ en $x=0$ |
| **Salto** | Límites laterales finitos pero distintos | Función parte entera $\lfloor x \rfloor$ |
| **Asintótica / esencial** | Al menos un límite lateral es infinito | $1/x$ en $x=0$ |

> [!EXAMPLE] Continuidad de una función a trozos
> Determinar si $f(x) = \begin{cases} \frac{x^2 - 4}{x-2}, & x \neq 2 \\ 4, & x = 2 \end{cases}$ es continua en $x=2$.
>
> **Paso 1:** Verificar que $f(2)$ está definida.
> $f(2) = 4$ ✓
>
> **Paso 2:** Calcular $\lim_{x \to 2} f(x)$.
> $$\lim_{x \to 2} \frac{x^2 - 4}{x-2} = \lim_{x \to 2} \frac{(x-2)(x+2)}{x-2} = \lim_{x \to 2} (x+2) = 4$$
>
> **Paso 3:** Comparar.
> $\lim_{x \to 2} f(x) = 4 = f(2)$. Se cumplen las 3 condiciones.
>
> **Resultado:** $f$ es continua en $x=2$.
>
> > [!WARNING]
> > En el paso 2, simplificamos $(x-2)$ porque $x \neq 2$ en el límite. El límite mira el comportamiento **alrededor** de 2, no en 2.

---

### Propiedades de funciones continuas

Si $f$ y $g$ son continuas en $x = a$, también lo son:
- $f \pm g$, $f \cdot g$, $f/g$ (si $g(a) \neq 0$)
- $f \circ g$ (composición)
- $f^{-1}$ (si $f$ es biyectiva cerca de $a$)

**Funciones continuas en todo su dominio:**
- Polinómicas
- Racionales (donde el denominador no se anula)
- Trigonométricas
- Exponenciales y logarítmicas
- Raíces (en su dominio)

### Teorema del valor intermedio (TVI)

Si $f$ es continua en $[a,b]$ y $k$ está entre $f(a)$ y $f(b)$, entonces existe $c \in [a,b]$ tal que $f(c) = k$.

```
      f(x)
        ▲
     f(b)┤              •───
        │          ╱  ╱
        │      ╱  ╱
       k ─────────•───────  (existe c tal que f(c) = k)
        │    ╱ ╱
     f(a)•───
        └─────────────────▶ x
            a   c     b
```

> [!EXAMPLE] Aplicación del TVI
> Demostrar que $f(x) = x^3 - 4x + 1$ tiene al menos una raíz real en $[0, 1]$.
>
> **Paso 1:** Verificar continuidad.
> $f$ es polinómica → continua en todo $\mathbb{R}$.
>
> **Paso 2:** Evaluar en los extremos.
> $f(0) = 0^3 - 4(0) + 1 = 1 > 0$
> $f(1) = 1^3 - 4(1) + 1 = -2 < 0$
>
> **Paso 3:** Aplicar TVI.
> Como $f(0) > 0$ y $f(1) < 0$, y $0$ está entre ellos, existe $c \in (0,1)$ tal que $f(c) = 0$.
>
> **Resultado:** Existe al menos una raíz en $(0,1)$.
>
> > [!TIP] Aplicación en ingeniería
> > El TVI se usa en **métodos numéricos** (bisección) para encontrar raíces de ecuaciones. Es la base del método de bisección que usarás en Análisis Numérico.

---

## Asíntotas

### Asíntotas verticales (AV)
Ocurren cuando el denominador se anula y el numerador no:

$$x = a \text{ es AV si } \lim_{x \to a^{\pm}} f(x) = \pm\infty$$

### Asíntotas horizontales (AH)
$$y = L \text{ es AH si } \lim_{x \to \pm\infty} f(x) = L$$

### Asíntotas oblicuas (AO)
Cuando el grado del numerador es exactamente uno más que el denominador:

$$y = mx + b \quad \text{donde} \quad m = \lim_{x \to \infty} \frac{f(x)}{x}, \quad b = \lim_{x \to \infty} (f(x) - mx)$$

---

## Tabla resumen de límites

| Situación | Resultado | Ejemplo |
|:----------|:----------|:--------|
| $\lim_{x \to a} c$ | $c$ | $\lim_{x \to 3} 5 = 5$ |
| $\lim_{x \to a} x^n$ | $a^n$ | $\lim_{x \to 2} x^3 = 8$ |
| $\lim_{x \to 0} \frac{\sin x}{x}$ | $1$ | $\lim_{x \to 0} \frac{\sin(5x)}{x} = 5$ |
| $\lim_{x \to 0} \frac{1-\cos x}{x}$ | $0$ | $-$ |
| $\lim_{x \to \infty} \frac{1}{x^p}$, $p>0$ | $0$ | $\lim_{x \to \infty} \frac{1}{\sqrt{x}} = 0$ |
| $\lim_{x \to \infty} \frac{a_n x^n + \dots}{b_m x^m + \dots}$ | $0$ si $n<m$, $a_n/b_m$ si $n=m$, $\infty$ si $n>m$ | $\lim_{x \to \infty} \frac{2x^2}{3x^2+1} = \frac{2}{3}$ |

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Apunte U2 (Ocampo) — Límites | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Ocampo/Unidad 2.pdf` |
| Teoría límite y continuidad (Peréz) | `Raw/.../1 matematica/TEORIA/Análisis matemático I/teoria Peréz/limite y continuidad.pdf` |
| Apunte Límites (profes) | `Raw/.../AnM1/Teorías/Límites.pdf` |
| Apunte Continuidad (profes) | `Raw/.../AnM1/Teorías/Continuidad.pdf` |
| Material teórico U2 (Límite y continuidad) | `Raw/.../AnM1/Teorías/Material teórico/Unidad 2 Límite y continuidad.pdf` |
| Clases U2 (4 clases) | `Raw/.../AnM1/Teorías/Apuntes de clase UNIDAD 2/` |
| Presentaciones teóricas U2 | `Raw/.../AnM1/Teorías/Presentaciores de clases teoricas/Unidad 2 -*` |
| Clase 4 - 17-3 — Límites | `Raw/.../AnM1/Teorías/Unidad 2 Limite - Continuidad/clase 4- 17-3-2026 Limite , limites laterales, ejemplos.pdf` |
| Clase 5 - 26-3 — Límites infinitos | `Raw/.../AnM1/Teorías/Unidad 2 Limite - Continuidad/clase5 26-3-26 limites infinitos, limites en el infirnito, asintotas y lim especial e.pdf` |
| Clase 6 - 31-3 — Continuidad | `Raw/.../AnM1/Teorías/Unidad 2 Limite - Continuidad/clase6 31-3-26continuidad.pdf` |
| TPN°2 Límites 2026 | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TPN°2 Limites_1°C_2026.pdf` |
| TPN°3 Continuidad 2026 | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/TPN°3 Continuidad_1°C_2026 - - copia.pdf` |
| Ejercicios adicionales - Límites y continuidad | `Raw/.../AnM1/Trabajos Prácticos comunes a todos los módulos/Ejercicios adicionales/Ejercicios adicionales - Límites y continuidad.pdf` |
| Autoevaluación límite y continuidad (y resolución) | `Raw/.../1 matematica/PRACTICA/Análisis matemático I/autoevaluaciones/autoevaluación - limites y continuidad .pdf` |

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Funciones]] • **Siguiente:** [[Anm_Derivadas]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
