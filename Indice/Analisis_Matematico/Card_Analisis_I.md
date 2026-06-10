---
created: 2026-06-10
tags: [cheatsheet, analisis, formulas, repaso]
tipo: cheat-sheet
materia: AMI
temas: 7
---

# 📐 Análisis Matemático I — Cheat Sheet

> [!tip] Navegación rápida
> [[Anm_Funciones|Funciones]] → [[Anm_Limites_Continuidad|Límites]] → [[Anm_Derivadas|Derivadas]] → [[Anm_Aplicaciones_Derivada|Aplic. Derivada]] → [[Anm_Integrales|Integrales]] → [[Anm_Aplicaciones_Integral|Aplic. Integral]] → [[Anm_Sucesiones_Series|Series]]

---

## 1. Funciones

| Concepto | Fórmula |
|---|---|
| Dominio | Valores de $x$ donde $f(x)$ está definida |
| Imagen | Conjunto de todos los $f(x)$ posibles |
| **Par:** $f(-x) = f(x)$ | Simétrica respecto al eje $y$ |
| **Impar:** $f(-x) = -f(x)$ | Simétrica respecto al origen |
| **Composición:** $(f \circ g)(x)$ | $= f(g(x))$ |

### Funciones notables
| Función | Derivada | Integral |
|---|---|---|
| $\sin x$ | $\cos x$ | $-\cos x$ |
| $\cos x$ | $-\sin x$ | $\sin x$ |
| $\tan x$ | $\sec^2 x$ | $-\ln\|\cos x\|$ |
| $e^x$ | $e^x$ | $e^x$ |
| $\ln x$ | $\frac{1}{x}$ | $x\ln x - x$ |

---

## 2. Límites y Continuidad

### Definición
$$\lim_{x \to a} f(x) = L \iff \forall \varepsilon > 0, \exists \delta > 0: 0<|x-a|<\delta \implies |f(x)-L|<\varepsilon$$

### Límites notables
$$\lim_{x \to 0} \frac{\sin x}{x} = 1 \quad \lim_{x \to 0} \frac{1-\cos x}{x} = 0 \quad \lim_{x \to 0} \frac{e^x - 1}{x} = 1$$
$$\lim_{x \to \infty} \left(1+\frac{1}{x}\right)^x = e \quad \lim_{x \to 0} (1+x)^{\frac{1}{x}} = e$$

### Asíntotas
| Tipo | Condición | Ecuación |
|---|---|---|
| **Vertical** | $\lim_{x \to a} f(x) = \pm\infty$ | $x = a$ |
| **Horizontal** | $\lim_{x \to \pm\infty} f(x) = L$ | $y = L$ |
| **Oblicua** | $\lim_{x \to \infty} \frac{f(x)}{x} = m \neq 0,\infty$ | $y = mx + b$ ($b = \lim (f-mx)$) |

### Continuidad
- $f$ es continua en $a$ si $\lim_{x \to a} f(x) = f(a)$
- **Teorema de Bolzano:** Si $f(a) \cdot f(b) < 0$, existe $c \in (a,b)$ con $f(c)=0$

---

## 3. Derivadas

### Definición
$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

### Reglas de derivación
| Regla | Fórmula |
|---|---|
| Producto | $(fg)' = f'g + fg'$ |
| Cociente | $\left(\frac{f}{g}\right)' = \frac{f'g - fg'}{g^2}$ |
| Cadena | $(f \circ g)' = f'(g(x)) \cdot g'(x)$ |
| Inversa | $(f^{-1})'(y_0) = \frac{1}{f'(x_0)}$ con $y_0 = f(x_0)$ |
| Implícita | Derivar ambos lados respecto a $x$, despejar $y'$ |
| Logarítmica | Tomar $\ln$, derivar, despejar |

### Regla de L'Hôpital
Si $\lim \frac{f(x)}{g(x)} = \frac{0}{0}$ o $\frac{\pm\infty}{\pm\infty} \implies \lim \frac{f(x)}{g(x)} = \lim \frac{f'(x)}{g'(x)}$

---

## 4. Aplicaciones de la Derivada

### Teoremas fundamentales
| Teorema | Enunciado |
|---|---|
| **Rolle** | $f(a)=f(b) \implies \exists c \in (a,b): f'(c)=0$ |
| **TVM (Lagrange)** | $\exists c \in (a,b): f'(c) = \frac{f(b)-f(a)}{b-a}$ |
| **Cauchy** | $\frac{f(b)-f(a)}{g(b)-g(a)} = \frac{f'(c)}{g'(c)}$ |

### Crecimiento y extremos
- $f'(x) > 0 \implies f$ crece
- $f'(x) < 0 \implies f$ decrece
- **Punto crítico:** $f'(x)=0$ o no existe
- **Criterio 1ra derivada:** $f'$ cambia $+$ a $-$ → máximo; $-$ a $+$ → mínimo
- **Criterio 2da derivada:** $f''(x_0) > 0$ → mínimo; $f''(x_0) < 0$ → máximo
- **Concavidad:** $f''(x) > 0$ → cóncava hacia arriba; $f''(x) < 0$ → cóncava abajo
- **Punto de inflexión:** $f''(x)=0$ y cambia signo

### Polinomio de Taylor
$$f(x) \approx \sum_{k=0}^n \frac{f^{(k)}(a)}{k!}(x-a)^k$$

---

## 5. Integrales

### Definición
$$\int_a^b f(x)\,dx = \lim_{n \to \infty} \sum_{i=1}^n f(x_i^*)\Delta x$$

### Teorema Fundamental del Cálculo
- **Parte 1:** $\frac{d}{dx} \int_a^x f(t)\,dt = f(x)$
- **Parte 2:** $\int_a^b f(x)\,dx = F(b) - F(a)$ donde $F' = f$

### Técnicas de integración
| Técnica | Cuándo | Idea |
|---|---|---|
| **Sustitución** | $f(g(x))g'(x)$ | $u = g(x)$ |
| **Partes** | $u \cdot dv$ | $\int u\,dv = uv - \int v\,du$ ($\int f g' = fg - \int f' g$) |
| **Fracciones simples** | Polinomio/polinomio | Descomponer en fracciones parciales |
| **Trigonométricas** | $\sin^n, \cos^n$ | Identidades, reducir potencias |
| **Sust. trigonométrica** | $\sqrt{a^2-x^2}$, etc | $x = a\sin\theta$, $a\tan\theta$, $a\sec\theta$ |

### Integrales inmediatas
$$\int x^n\,dx = \frac{x^{n+1}}{n+1} + C \;(n\neq-1) \quad \int \frac{dx}{x} = \ln|x| + C$$
$$\int e^x\,dx = e^x + C \quad \int \sin x\,dx = -\cos x + C \quad \int \cos x\,dx = \sin x + C$$
$$\int \frac{dx}{\sqrt{1-x^2}} = \arcsin x + C \quad \int \frac{dx}{1+x^2} = \arctan x + C$$

---

## 6. Aplicaciones de la Integral

### Cálculo de áreas
$$\text{Área} = \int_a^b |f(x) - g(x)|\,dx$$

### Volúmenes
| Método | Fórmula |
|---|---|
| **Discos** (eje $x$) | $V = \pi \int_a^b [f(x)]^2\,dx$ |
| **Arandelas** | $V = \pi \int_a^b ([f(x)]^2 - [g(x)]^2)\,dx$ |
| **Capas cilíndricas** | $V = 2\pi \int_a^b x\,f(x)\,dx$ |

### Longitud de arco
$$L = \int_a^b \sqrt{1 + [f'(x)]^2}\,dx$$

### Integrales impropias
$$\int_a^\infty f(x)\,dx = \lim_{b \to \infty} \int_a^b f(x)\,dx$$

---

## 7. Sucesiones y Series

### Criterios de convergencia (series $\sum a_n$)
| Criterio | Condición |
|---|---|
| **Término general** | Si $\lim a_n \neq 0$ → **diverge** |
| **Series geométricas** | $\sum r^n$ converge si $|r| < 1$ |
| **Series $p$** | $\sum \frac{1}{n^p}$ converge si $p > 1$ |
| **Cociente (D'Alembert)** | $\lim \left|\frac{a_{n+1}}{a_n}\right| < 1$ → converge |
| **Raíz (Cauchy)** | $\lim \sqrt[n]{|a_n|} < 1$ → converge |
| **Comparación** | Si $0 \le a_n \le b_n$ y $\sum b_n$ converge → converge |

### Series de potencias
$$\sum_{n=0}^\infty c_n (x-a)^n \quad \text{Radio: } R = \frac{1}{\limsup \sqrt[n]{|c_n|}}$$

### Series de Taylor/Maclaurin
$$e^x = \sum_{n=0}^\infty \frac{x^n}{n!} \quad \sin x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$
$$\cos x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n}}{(2n)!} \quad \frac{1}{1-x} = \sum_{n=0}^\infty x^n \;(|x|<1)$$

---

> [!tip]- 💡 Cómo usar
> Hoja de referencia rápida para parciales y ejercicios. Cada sección linkea al tema completo en el vault.

> [!example]- Próximos pasos
> - [[Eje_Analisis_Matematico|Ver hoja de ruta completa de Análisis]]
> - [[Dashboard_Progreso|📊 Dashboard de progreso]]
