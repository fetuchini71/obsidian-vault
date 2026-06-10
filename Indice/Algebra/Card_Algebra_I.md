---
created: 2026-06-10
tags: [cheatsheet, algebra, formulas, repaso]
tipo: cheat-sheet
materia: AGI
temas: 6
---

# 🔷 Álgebra y Geometría I — Cheat Sheet

> [!tip] Navegación rápida
> [[Alg_Numeros_Reales|Reales]] → [[Alg_Matrices_Determinantes|Matrices]] → [[Alg_Sistemas_Ecuaciones|SEL]] → [[Alg_Vectores|Vectores]] → [[Alg_Rectas_Plano|Rectas/Planos]] → [[Alg_Conicas_Cuadricas|Cónicas]]

---

## 1. Números Reales

| Concepto | Fórmula |
|---|---|
| Valor absoluto | $|x| = \begin{cases} x & x \ge 0 \\ -x & x < 0 \end{cases}$ |
| Propiedades | $|ab| = \!|a||b|,\; |a+b| \le |a|+|b|,\; |a-b| \ge ||a|-|b||$ |
| Distancia | $d(a,b) = |b-a|$ |
| Sumatoria | $\sum_{i=1}^n i = \frac{n(n+1)}{2}$ |
| | $\sum_{i=1}^n i^2 = \frac{n(n+1)(2n+1)}{6}$ |
| Binomio de Newton | $(a+b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k$ |
| Diferencia de cuadrados | $a^2 - b^2 = (a-b)(a+b)$ |
| Diferencia de cubos | $a^3 - b^3 = (a-b)(a^2 + ab + b^2)$ |
| Trinomio cuadrado | $(a \pm b)^2 = a^2 \pm 2ab + b^2$ |

**Intervalos:** $[a,b], (a,b), [a,b), (a,b], (-\infty, a], (b, \infty)$

---

## 2. Matrices y Determinantes

### Operaciones básicas
- **Suma:** $A+B = [a_{ij} + b_{ij}]$ (mismas dimensiones)
- **Producto escalar:** $kA = [k \cdot a_{ij}]$
- **Producto matricial:** $C_{m \times p} = A_{m \times n} \cdot B_{n \times p}$, $c_{ij} = \sum_{k=1}^n a_{ik}b_{kj}$
- **NO conmutativo:** $AB \neq BA$ (generalmente)

### Tipos de matrices
| Tipo | Propiedad |
|---|---|
| **Identidad** $I$ | $1$ en diagonal, $0$ fuera |
| **Transpuesta** $A^T$ | $(A^T)_{ij} = A_{ji}$ |
| **Simétrica** | $A^T = A$ |
| **Idempotente** | $A^2 = A$ |
| **Inversa** $A^{-1}$ | $AA^{-1} = A^{-1}A = I$ |

### Determinantes
- $|A|$ para $2\times2$: $\begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc$
- $|A|$ para $3\times3$: **Regla de Sarrus**
- **Propiedades:** $|AB| = |A||B|$, $|kA| = k^n|A|$, $|A^T| = |A|$, $|A^{-1}| = \frac{1}{|A|}$
- **Inversa por determinantes:** $A^{-1} = \frac{1}{|A|} \text{adj}(A) = \frac{1}{|A|} (\text{cof}(A))^T$

---

## 3. Sistemas de Ecuaciones Lineales

| Método | Cuándo usarlo |
|---|---|
| **Eliminación de Gauss** | Siempre — el más general |
| **Gauss-Jordan** | Cuando querés la solución explícita |
| **Matriz inversa** | $AX = B \implies X = A^{-1}B$ (solo si $|A| \neq 0$) |
| **Regla de Cramer** | $x_i = \frac{|A_i|}{|A|}$ (solo cuadrado, $|A| \neq 0$) |

### Clasificación (Teorema de Rouché-Frobenius)
| $rango(A) = rango(A\|B)$? | $rango = n$? | Tipo |
|---|---|---|
| Sí | Sí | **SCD** (solución única) |
| Sí | No | **SCI** (infinitas soluciones) |
| No | — | **SI** (sin solución) |

### Matriz ampliada: $(A|B)$

---

## 4. Vectores en R² y R³

### Operaciones
- $\vec{v} = (v_1, v_2, v_3)$
- **Norma:** $\|\vec{v}\| = \sqrt{v_1^2 + v_2^2 + v_3^2}$
- **Producto escalar:** $\vec{u} \cdot \vec{v} = \|u\|\|v\|\cos\theta = u_1v_1 + u_2v_2 + u_3v_3$
- **Producto vectorial:** $\vec{u} \times \vec{v} = \begin{vmatrix} \hat{i} & \hat{j} & \hat{k} \\ u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \end{vmatrix}$
- **Producto mixto:** $[\vec{u},\vec{v},\vec{w}] = \vec{u} \cdot (\vec{v} \times \vec{w})$

### Propiedades clave
- **Ángulo:** $\cos\theta = \frac{\vec{u}\cdot\vec{v}}{\|\vec{u}\|\|\vec{v}\|}$
- **Ortogonalidad:** $\vec{u} \perp \vec{v} \iff \vec{u}\cdot\vec{v} = 0$
- **⃝Paralelismo:** $\vec{u} \parallel \vec{v} \iff \vec{u} = k\vec{v}$
- **Coplanaridad:** $\vec{u},\vec{v},\vec{w}$ coplanares $\iff [\vec{u},\vec{v},\vec{w}] = 0$

---

## 5. Rectas y Planos

### Recta en R²
| Forma | Ecuación |
|---|---|
| Explícita | $y = mx + b$ |
| General | $ax + by + c = 0$ |
| Paramétrica | $(x,y) = (x_0,y_0) + t(a,b)$ |
| Segmentaria | $\frac{x}{a} + \frac{y}{b} = 1$ |
| **Pendiente:** $m = \frac{y_2 - y_1}{x_2 - x_1}$ | **Dist. punto-recta:** $d(P,r) = \frac{|ax_0+by_0+c|}{\sqrt{a^2+b^2}}$ |

### Recta en R³ (paramétrica)
$$\vec{r} = \vec{P_0} + t\vec{d} \quad (t \in \mathbb{R})$$

### Plano en R³
| Forma | Ecuación |
|---|---|
| General | $ax + by + cz + d = 0$ |
| Normal | $\vec{n} \cdot (\vec{r} - \vec{r_0}) = 0$ |
| Dist. punto-plano | $d(P,\pi) = \frac{|ax_0+by_0+cz_0+d|}{\sqrt{a^2+b^2+c^2}}$ |

### Posiciones relativas
- **Recta-recta:** paralelas, coincidentes, secantes, alabeadas
- **Recta-plano:** contenida, paralela, intersecta
- **Plano-plano:** paralelos, coincidentes, secantes (recta)

---

## 6. Cónicas y Cuádricas

### Cónicas (forma canónica centrada)

| Cónica | Ecuación | Excentricidad |
|---|---|---|
| **Circunferencia** | $x^2 + y^2 = r^2$ | $e=0$ |
| **Elipse** | $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ | $e = \frac{c}{a} < 1$ |
| **Hipérbola** | $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$ | $e = \frac{c}{a} > 1$ |
| **Parábola** | $y^2 = 4px$ (eje $x$) | $e=1$ |

> **Centro en $(h,k)$:** reemplazar $x \to x-h$, $y \to y-k$

### Cuádricas (superficies 3D)
| Superficie | Ecuación |
|---|---|
| **Elipsoide** | $\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$ |
| **Hiperboloide 1 hoja** | $\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = 1$ |
| **Hiperboloide 2 hojas** | $-\frac{x^2}{a^2} - \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$ |
| **Paraboloide elíptico** | $z = \frac{x^2}{a^2} + \frac{y^2}{b^2}$ |
| **Paraboloide hiperbólico** | $z = \frac{x^2}{a^2} - \frac{y^2}{b^2}$ (silla de montar) |

---

> [!tip]- 📝 Cómo usar esto
> Esta es tu hoja de referencia rápida. Si necesitás profundizar, cada sección linkea a la nota completa del tema en el vault.

> [!example]- Próximos pasos
> - [[Eje_Algebra|Ver hoja de ruta completa de Álgebra]]
> - [[Dashboard_Progreso|📊 Dashboard de progreso]]
