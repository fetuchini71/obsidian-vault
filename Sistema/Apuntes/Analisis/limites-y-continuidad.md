# LÍMITES Y CONTINUIDAD (Funciones de Varias Variables)

**Fuente:** *Cálculo Vectorial* — Bento de Jesus Caraça  
**Páginas de referencia:** 167–173 (sección 13.2)  
**Tipo:** Resumen Ejecutivo

---

## 1. Terminología sobre conjuntos en el plano

Antes de definir límites es necesario precisar algunos conceptos de conjuntos en $\mathbb{R}^2$ y $\mathbb{R}^3$.

| Concepto | Definición | Pág. |
|---|---|---|
| **Disco abierto** | $\{(x,y) \mid (x-x_0)^2 + (y-y_0)^2 < d^2\}$ | 168 |
| **Disco cerrado** | $\{(x,y) \mid (x-x_0)^2 + (y-y_0)^2 \le d^2\}$ | 168 |
| **Bola abierta** (en $\mathbb{R}^3$) | $\{(x,y,z) \mid (x-x_0)^2 + (y-y_0)^2 + (z-z_0)^2 < d^2\}$ | 168 |
| **Punto interior** | Existe un disco abierto centrado en él que contiene solo puntos de la región | 168 |
| **Punto frontera** | Todo disco abierto centrado en él contiene puntos de la región y puntos fuera de ella | 168 |
| **Región abierta** | No contiene puntos frontera | 168 |
| **Región cerrada** | Contiene todos sus puntos frontera | 168 |
| **Región acotada** | Puede contenerse en un rectángulo suficientemente grande | 168 |

---

## 2. Definición de Límite

### 2.1 Noción intuitiva (pág. 168)

Una función $f(x,y)$ tiene **límite $L$** cuando $(x,y)$ se aproxima a $(a,b)$ si los valores de $f$ se acercan a $L$ conforme $(x,y)$ se acerca a $(a,b)$. Se escribe:

$$\lim_{(x,y) \to (a,b)} f(x,y) = L$$

A diferencia de funciones de una variable (donde $x \to a$ solo puede darse por izquierda o derecha), **en el plano existen infinitas trayectorias** para aproximarse a $(a,b)$.

> **Condición necesaria y suficiente:** Para que el límite exista, $f$ debe aproximarse al **mismo número $L$** a lo largo de *toda* trayectoria o curva posible que pase por $(a,b)$ (pág. 168).

> **Criterio de no existencia:** Si $f(x,y)$ no se aproxima al mismo número por dos trayectorias diferentes hacia $(a,b)$, entonces $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y)$ **no existe** (pág. 168, regla (4)).

### 2.2 Definición formal $\varepsilon\!-\!\delta$ (Definición 13.2.1, pág. 172)

$$\lim_{(x,y) \to (a,b)} f(x,y) = L$$

significa que para toda $\varepsilon > 0$ existe un $\delta > 0$ tal que

$$|f(x,y) - L| < \varepsilon \quad \text{siempre que} \quad 0 < \sqrt{(x-a)^2 + (y-b)^2} < \delta.$$

En palabras: los valores de $f$ pueden hacerse arbitrariamente cercanos a $L$ ($\varepsilon$) siempre que $(x,y)$ esté suficientemente cerca de $(a,b)$ ($\delta$), sin importar la dirección de aproximación.

---

## 3. Propiedades de los Límites

### Teorema 13.2.1 — Tres límites fundamentales (pág. 170)

| # | Límite |
|---|---|
| i) | $\displaystyle\lim_{(x,y)\to(a,b)} c = c$ |
| ii) | $\displaystyle\lim_{(x,y)\to(a,b)} x = a$ |
| iii) | $\displaystyle\lim_{(x,y)\to(a,b)} y = b$ |

### Teorema 13.2.2 — Suma, producto y cociente (pág. 170)

Si $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y) = L_1$ y $\displaystyle\lim_{(x,y)\to(a,b)} g(x,y) = L_2$, entonces:

| Operación | Resultado |
|---|---|
| i) Suma/resta | $\displaystyle\lim [f(x,y) \pm g(x,y)] = L_1 \pm L_2$ |
| ii) Producto | $\displaystyle\lim [f(x,y) \cdot g(x,y)] = L_1 \cdot L_2$ |
| iii) Cociente | $\displaystyle\lim \frac{f(x,y)}{g(x,y)} = \frac{L_1}{L_2},\; L_2 \neq 0$ |
| iv) Múltiplo constante | $\displaystyle\lim [c\,f(x,y)] = c\,L_1$ |

---

## 4. Técnicas de Evaluación

### 4.1 Coordenadas polares (pág. 170–171)

Para límites en $(0,0)$, se puede usar el cambio:

$$x = r\cos\theta,\quad y = r\sin\theta,\quad r^2 = x^2 + y^2$$

Entonces:

$$\lim_{(x,y)\to(0,0)} f(x,y) = L \iff \lim_{r\to0} f(r\cos\theta,\, r\sin\theta) = L$$

> **Nota:** El resultado debe ser independiente de $\theta$; si depende de $\theta$, el límite no existe.

### 4.2 Trayectorias (pág. 168–170)

Para demostrar que un límite **no existe** basta encontrar dos trayectorias distintas hacia $(a,b)$ que den valores diferentes:

- Eje $x$: $(x,0) \to (0,0)$
- Eje $y$: $(0,y) \to (0,0)$
- Rectas: $y = mx$
- Parábolas: $y = ax^2$, $y = x^3$, etc.

---

## 5. Definición de Continuidad

### 5.1 Definición (pág. 171)

Una función $z = f(x,y)$ es **continua en** $(a,b)$ si se cumplen **tres condiciones**:

1. $f(a,b)$ está definida.
2. $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y)$ existe.
3. $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y) = f(a,b)$.

Si alguna falla, la función es **discontinua** en $(a,b)$.

> La gráfica de una función continua en una región es una **superficie sin quiebres** (pág. 171).

### 5.2 Propiedades de continuidad (pág. 171)

- **Suma y producto** de funciones continuas son continuas.
- **Cociente** de funciones continuas es continuo excepto donde el denominador se anula.
- **Composición:** Si $g(x,y)$ es continua en $(a,b)$ y $F(u)$ es continua en $u = g(a,b)$, entonces $F(g(x,y))$ es continua en $(a,b)$.

### 5.3 Funciones polinomiales y racionales (pág. 172)

- **Funciones polinomiales** (ej. $f(x,y) = xy$) son **continuas en todo** $\mathbb{R}^2$.
- **Funciones racionales** (cociente de polinomios) son continuas **excepto en los puntos donde el denominador es cero**.

### 5.4 Funciones de tres o más variables (pág. 172)

Los conceptos se extienden naturalmente. Por ejemplo, $w = f(x,y,z)$ es continua en $(a,b,c)$ si:

$$\lim_{(x,y,z)\to(a,b,c)} f(x,y,z) = f(a,b,c).$$

---

## 6. Teoremas Importantes

| Teorema | Enunciado | Pág. |
|---|---|---|
| **13.2.1** | $\lim c = c$, $\lim x = a$, $\lim y = b$ | 170 |
| **13.2.2** | Límite de suma, producto y cociente | 170 |
| **Def. 13.2.1** | Definición $\varepsilon\!-\!\delta$ del límite | 172 |
| **Continuidad por composición** | $F(g(x,y))$ es continua si $g$ lo es en $(a,b)$ y $F$ en $g(a,b)$ | 171 |
| **Continuidad de polinomiales** | Toda función polinomial es continua en $\mathbb{R}^2$ | 172 |
| **Continuidad de racionales** | Continuas salvo donde el denominador es cero | 172 |

---

## 7. Ejemplos Clave

### Ejemplo 1 — Límite que no existe (pág. 169)
$$f(x,y) = \frac{x^2 + 3y^2}{x^2 - 2y^2},\quad \lim_{(x,y)\to(0,0)} f(x,y)$$

- Por el eje $x$ ($y=0$): $\displaystyle\lim_{x\to0} \frac{x^2}{x^2} = 1$
- Por el eje $y$ ($x=0$): $\displaystyle\lim_{y\to0} \frac{3y^2}{-2y^2} = -\frac{3}{2}$
- **Conclusión:** El límite **no existe** (valores distintos).

### Ejemplo 2 — Límite que no existe (trayectorias rectilíneas, pág. 169)
$$f(x,y) = \frac{xy}{x^2 + y^2},\quad \lim_{(x,y)\to(0,0)} f(x,y)$$

- Por $y = mx$: $\displaystyle\frac{mx^2}{x^2 + m^2x^2} = \frac{m}{1+m^2}$, depende de $m$.
- **Conclusión:** El límite **no existe**.

### Ejemplo 3 — Límite que no existe (trayectorias curvas, pág. 169–170)
$$f(x,y) = \frac{x^3 y}{x^6 + y^2},\quad \lim_{(x,y)\to(0,0)} f(x,y)$$

- Por $y = mx$: $f = 0$; por $y = ax^2$: $f = 0$; por $y = x^3$: $f = 1/2$.
- **Conclusión:** Aunque infinitas trayectorias den 0, **el límite no existe** (basta una que dé otro valor).

### Ejemplo 4 — Evaluación con propiedades (pág. 170)
$$\lim_{(x,y)\to(2,3)} (x + y^2) = \lim x + \left(\lim y\right)^2 = 2 + 3^2 = 11.$$

### Ejemplo 5 — Coordenadas polares (pág. 170–171)
$$\lim_{(x,y)\to(0,0)} \frac{10xy^2}{x^2 + y^2} = \lim_{r\to0} \frac{10(r\cos\theta)(r^2\sin^2\theta)}{r^2} = \lim_{r\to0} 10r\cos\theta\sin^2\theta = 0.$$

### Ejemplo 6 — Discontinuidad en $(0,0)$ (pág. 171)
$$f(x,y) = \frac{x^4 - y^4}{x^2 + y^2}$$
$f$ no está definida en $(0,0)$, luego es discontinua. Sin embargo, **la discontinuidad es removible** (ejemplo 7).

### Ejemplo 7 — Continuidad en $(0,0)$ (pág. 171)
$$f(x,y) = \begin{cases}
\displaystyle\frac{x^4 - y^4}{x^2 + y^2}, & (x,y) \neq (0,0) \\
0, & (x,y) = (0,0)
\end{cases}$$

Como $\displaystyle\lim_{(x,y)\to(0,0)} \frac{x^4 - y^4}{x^2 + y^2} = \lim_{(x,y)\to(0,0)} (x^2 - y^2) = 0 = f(0,0)$, la función es **continua en $(0,0)$**.

### Ejemplo 8 — Demostración $\varepsilon\!-\!\delta$ (pág. 173)
Se demuestra formalmente que $\displaystyle\lim_{(x,y)\to(0,0)} \frac{10xy^2}{x^2+y^2} = 0$ usando $\delta = \varepsilon/10$.

---

## 8. Conexiones con Derivación (pág. 174–175, §13.3)

Las **derivadas parciales** se definen mediante límites, por lo que la existencia del límite es un prerrequisito para la diferenciabilidad:

| Derivada parcial | Definición como límite | Pág. |
|---|---|---|
| $\displaystyle\frac{\partial z}{\partial x}$ | $\displaystyle\lim_{h\to0} \frac{f(x+h,\,y) - f(x,y)}{h}$ | 174 |
| $\displaystyle\frac{\partial z}{\partial y}$ | $\displaystyle\lim_{h\to0} \frac{f(x,\,y+h) - f(x,y)}{h}$ | 174 |

**Reglas prácticas** (pág. 175):
- Para $\partial z/\partial x$: derivar tratando $y$ como constante.
- Para $\partial z/\partial y$: derivar tratando $x$ como constante.

> **Relación clave:** La **continuidad** de $f$ en un punto **no garantiza** la existencia de sus derivadas parciales, pero la **diferenciabilidad** (existencia de derivadas parciales continuas) sí implica continuidad. El estudio de límites es, por tanto, la base sobre la que se construye todo el cálculo diferencial en varias variables.

---

## 9. Resumen Visual de Conceptos

```
        LÍMITES Y CONTINUIDAD (varias variables)
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
    LÍMITE                  CONTINUIDAD
    lim f(x,y)=L            lim f(x,y)=f(a,b)
        │                       │
    ┌───┴───┐               ┌───┴───┐
    ▼       ▼               ▼       ▼
 Existe   No existe     Continua  Discontinua
 (único L  (2 tray.    (sin       (con
 por toda  distintas)   quiebres)  quiebres)
 trayectoria)
        │                       │
        └───────────┬───────────┘
                    ▼
            DERIVADAS PARCIALES
        (definidas como límites)
```

---

*Resumen elaborado a partir de Cálculo Vectorial, Bento de Jesus Caraça, Sección 13.2 (pp. 167–173) y Sección 13.3 (pp. 174–175).*
