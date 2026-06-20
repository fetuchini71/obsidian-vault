1|# LÍMITES Y CONTINUIDAD (Funciones de Varias Variables)
2|
3|**Fuente:** *Cálculo Vectorial* — Bento de Jesus Caraça  
4|**Páginas de referencia:** 167–173 (sección 13.2)  

**Fuentes en el vault:** [[Libros/Analisis/cálculo-de-varias-variables|Caraça (Cálculo Vectorial)]]

5|**Tipo:** Resumen Ejecutivo
6|
7|---
8|
9|## 1. Terminología sobre conjuntos en el plano
10|
11|Antes de definir límites es necesario precisar algunos conceptos de conjuntos en $\mathbb{R}^2$ y $\mathbb{R}^3$.
12|
13|| Concepto | Definición | Pág. |
14||---|---|---|
15|| **Disco abierto** | $\{(x,y) \mid (x-x_0)^2 + (y-y_0)^2 < d^2\}$ | 168 |
16|| **Disco cerrado** | $\{(x,y) \mid (x-x_0)^2 + (y-y_0)^2 \le d^2\}$ | 168 |
17|| **Bola abierta** (en $\mathbb{R}^3$) | $\{(x,y,z) \mid (x-x_0)^2 + (y-y_0)^2 + (z-z_0)^2 < d^2\}$ | 168 |
18|| **Punto interior** | Existe un disco abierto centrado en él que contiene solo puntos de la región | 168 |
19|| **Punto frontera** | Todo disco abierto centrado en él contiene puntos de la región y puntos fuera de ella | 168 |
20|| **Región abierta** | No contiene puntos frontera | 168 |
21|| **Región cerrada** | Contiene todos sus puntos frontera | 168 |
22|| **Región acotada** | Puede contenerse en un rectángulo suficientemente grande | 168 |
23|
24|---
25|
26|## 2. Definición de Límite
27|
28|### 2.1 Noción intuitiva (pág. 168)
29|
30|Una función $f(x,y)$ tiene **límite $L$** cuando $(x,y)$ se aproxima a $(a,b)$ si los valores de $f$ se acercan a $L$ conforme $(x,y)$ se acerca a $(a,b)$. Se escribe:
31|
32|$$\lim_{(x,y) \to (a,b)} f(x,y) = L$$
33|
34|A diferencia de funciones de una variable (donde $x \to a$ solo puede darse por izquierda o derecha), **en el plano existen infinitas trayectorias** para aproximarse a $(a,b)$.
35|
36|> **Condición necesaria y suficiente:** Para que el límite exista, $f$ debe aproximarse al **mismo número $L$** a lo largo de *toda* trayectoria o curva posible que pase por $(a,b)$ (pág. 168).
37|
38|> **Criterio de no existencia:** Si $f(x,y)$ no se aproxima al mismo número por dos trayectorias diferentes hacia $(a,b)$, entonces $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y)$ **no existe** (pág. 168, regla (4)).
39|
40|### 2.2 Definición formal $\varepsilon\!-\!\delta$ (Definición 13.2.1, pág. 172)
41|
42|$$\lim_{(x,y) \to (a,b)} f(x,y) = L$$
43|
44|significa que para toda $\varepsilon > 0$ existe un $\delta > 0$ tal que
45|
46|$$|f(x,y) - L| < \varepsilon \quad \text{siempre que} \quad 0 < \sqrt{(x-a)^2 + (y-b)^2} < \delta.$$
47|
48|En palabras: los valores de $f$ pueden hacerse arbitrariamente cercanos a $L$ ($\varepsilon$) siempre que $(x,y)$ esté suficientemente cerca de $(a,b)$ ($\delta$), sin importar la dirección de aproximación.
49|
50|---
51|
52|## 3. Propiedades de los Límites
53|
54|### Teorema 13.2.1 — Tres límites fundamentales (pág. 170)
55|
56|| # | Límite |
57||---|---|
58|| i) | $\displaystyle\lim_{(x,y)\to(a,b)} c = c$ |
59|| ii) | $\displaystyle\lim_{(x,y)\to(a,b)} x = a$ |
60|| iii) | $\displaystyle\lim_{(x,y)\to(a,b)} y = b$ |
61|
62|### Teorema 13.2.2 — Suma, producto y cociente (pág. 170)
63|
64|Si $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y) = L_1$ y $\displaystyle\lim_{(x,y)\to(a,b)} g(x,y) = L_2$, entonces:
65|
66|| Operación | Resultado |
67||---|---|
68|| i) Suma/resta | $\displaystyle\lim [f(x,y) \pm g(x,y)] = L_1 \pm L_2$ |
69|| ii) Producto | $\displaystyle\lim [f(x,y) \cdot g(x,y)] = L_1 \cdot L_2$ |
70|| iii) Cociente | $\displaystyle\lim \frac{f(x,y)}{g(x,y)} = \frac{L_1}{L_2},\; L_2 \neq 0$ |
71|| iv) Múltiplo constante | $\displaystyle\lim [c\,f(x,y)] = c\,L_1$ |
72|
73|---
74|
75|## 4. Técnicas de Evaluación
76|
77|### 4.1 Coordenadas polares (pág. 170–171)
78|
79|Para límites en $(0,0)$, se puede usar el cambio:
80|
81|$$x = r\cos\theta,\quad y = r\sin\theta,\quad r^2 = x^2 + y^2$$
82|
83|Entonces:
84|
85|$$\lim_{(x,y)\to(0,0)} f(x,y) = L \iff \lim_{r\to0} f(r\cos\theta,\, r\sin\theta) = L$$
86|
87|> **Nota:** El resultado debe ser independiente de $\theta$; si depende de $\theta$, el límite no existe.
88|
89|### 4.2 Trayectorias (pág. 168–170)
90|
91|Para demostrar que un límite **no existe** basta encontrar dos trayectorias distintas hacia $(a,b)$ que den valores diferentes:
92|
93|- Eje $x$: $(x,0) \to (0,0)$
94|- Eje $y$: $(0,y) \to (0,0)$
95|- Rectas: $y = mx$
96|- Parábolas: $y = ax^2$, $y = x^3$, etc.
97|
98|---
99|
100|## 5. Definición de Continuidad
101|
102|### 5.1 Definición (pág. 171)
103|
104|Una función $z = f(x,y)$ es **continua en** $(a,b)$ si se cumplen **tres condiciones**:
105|
106|1. $f(a,b)$ está definida.
107|2. $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y)$ existe.
108|3. $\displaystyle\lim_{(x,y)\to(a,b)} f(x,y) = f(a,b)$.
109|
110|Si alguna falla, la función es **discontinua** en $(a,b)$.
111|
112|> La gráfica de una función continua en una región es una **superficie sin quiebres** (pág. 171).
113|
114|### 5.2 Propiedades de continuidad (pág. 171)
115|
116|- **Suma y producto** de funciones continuas son continuas.
117|- **Cociente** de funciones continuas es continuo excepto donde el denominador se anula.
118|- **Composición:** Si $g(x,y)$ es continua en $(a,b)$ y $F(u)$ es continua en $u = g(a,b)$, entonces $F(g(x,y))$ es continua en $(a,b)$.
119|
120|### 5.3 Funciones polinomiales y racionales (pág. 172)
121|
122|- **Funciones polinomiales** (ej. $f(x,y) = xy$) son **continuas en todo** $\mathbb{R}^2$.
123|- **Funciones racionales** (cociente de polinomios) son continuas **excepto en los puntos donde el denominador es cero**.
124|
125|### 5.4 Funciones de tres o más variables (pág. 172)
126|
127|Los conceptos se extienden naturalmente. Por ejemplo, $w = f(x,y,z)$ es continua en $(a,b,c)$ si:
128|
129|$$\lim_{(x,y,z)\to(a,b,c)} f(x,y,z) = f(a,b,c).$$
130|
131|---
132|
133|## 6. Teoremas Importantes
134|
135|| Teorema | Enunciado | Pág. |
136||---|---|---|
137|| **13.2.1** | $\lim c = c$, $\lim x = a$, $\lim y = b$ | 170 |
138|| **13.2.2** | Límite de suma, producto y cociente | 170 |
139|| **Def. 13.2.1** | Definición $\varepsilon\!-\!\delta$ del límite | 172 |
140|| **Continuidad por composición** | $F(g(x,y))$ es continua si $g$ lo es en $(a,b)$ y $F$ en $g(a,b)$ | 171 |
141|| **Continuidad de polinomiales** | Toda función polinomial es continua en $\mathbb{R}^2$ | 172 |
142|| **Continuidad de racionales** | Continuas salvo donde el denominador es cero | 172 |
143|
144|---
145|
146|## 7. Ejemplos Clave
147|
148|### Ejemplo 1 — Límite que no existe (pág. 169)
149|$$f(x,y) = \frac{x^2 + 3y^2}{x^2 - 2y^2},\quad \lim_{(x,y)\to(0,0)} f(x,y)$$
150|
151|- Por el eje $x$ ($y=0$): $\displaystyle\lim_{x\to0} \frac{x^2}{x^2} = 1$
152|- Por el eje $y$ ($x=0$): $\displaystyle\lim_{y\to0} \frac{3y^2}{-2y^2} = -\frac{3}{2}$
153|- **Conclusión:** El límite **no existe** (valores distintos).
154|
155|### Ejemplo 2 — Límite que no existe (trayectorias rectilíneas, pág. 169)
156|$$f(x,y) = \frac{xy}{x^2 + y^2},\quad \lim_{(x,y)\to(0,0)} f(x,y)$$
157|
158|- Por $y = mx$: $\displaystyle\frac{mx^2}{x^2 + m^2x^2} = \frac{m}{1+m^2}$, depende de $m$.
159|- **Conclusión:** El límite **no existe**.
160|
161|### Ejemplo 3 — Límite que no existe (trayectorias curvas, pág. 169–170)
162|$$f(x,y) = \frac{x^3 y}{x^6 + y^2},\quad \lim_{(x,y)\to(0,0)} f(x,y)$$
163|
164|- Por $y = mx$: $f = 0$; por $y = ax^2$: $f = 0$; por $y = x^3$: $f = 1/2$.
165|- **Conclusión:** Aunque infinitas trayectorias den 0, **el límite no existe** (basta una que dé otro valor).
166|
167|### Ejemplo 4 — Evaluación con propiedades (pág. 170)
168|$$\lim_{(x,y)\to(2,3)} (x + y^2) = \lim x + \left(\lim y\right)^2 = 2 + 3^2 = 11.$$
169|
170|### Ejemplo 5 — Coordenadas polares (pág. 170–171)
171|$$\lim_{(x,y)\to(0,0)} \frac{10xy^2}{x^2 + y^2} = \lim_{r\to0} \frac{10(r\cos\theta)(r^2\sin^2\theta)}{r^2} = \lim_{r\to0} 10r\cos\theta\sin^2\theta = 0.$$
172|
173|### Ejemplo 6 — Discontinuidad en $(0,0)$ (pág. 171)
174|$$f(x,y) = \frac{x^4 - y^4}{x^2 + y^2}$$
175|$f$ no está definida en $(0,0)$, luego es discontinua. Sin embargo, **la discontinuidad es removible** (ejemplo 7).
176|
177|### Ejemplo 7 — Continuidad en $(0,0)$ (pág. 171)
178|$$f(x,y) = \begin{cases}
179|\displaystyle\frac{x^4 - y^4}{x^2 + y^2}, & (x,y) \neq (0,0) \\
180|0, & (x,y) = (0,0)
181|\end{cases}$$
182|
183|Como $\displaystyle\lim_{(x,y)\to(0,0)} \frac{x^4 - y^4}{x^2 + y^2} = \lim_{(x,y)\to(0,0)} (x^2 - y^2) = 0 = f(0,0)$, la función es **continua en $(0,0)$**.
184|
185|### Ejemplo 8 — Demostración $\varepsilon\!-\!\delta$ (pág. 173)
186|Se demuestra formalmente que $\displaystyle\lim_{(x,y)\to(0,0)} \frac{10xy^2}{x^2+y^2} = 0$ usando $\delta = \varepsilon/10$.
187|
188|---
189|
190|## 8. Conexiones con Derivación (pág. 174–175, §13.3)
191|
192|Las **derivadas parciales** se definen mediante límites, por lo que la existencia del límite es un prerrequisito para la diferenciabilidad:
193|
194|| Derivada parcial | Definición como límite | Pág. |
195||---|---|---|
196|| $\displaystyle\frac{\partial z}{\partial x}$ | $\displaystyle\lim_{h\to0} \frac{f(x+h,\,y) - f(x,y)}{h}$ | 174 |
197|| $\displaystyle\frac{\partial z}{\partial y}$ | $\displaystyle\lim_{h\to0} \frac{f(x,\,y+h) - f(x,y)}{h}$ | 174 |
198|
199|**Reglas prácticas** (pág. 175):
200|- Para $\partial z/\partial x$: derivar tratando $y$ como constante.
201|- Para $\partial z/\partial y$: derivar tratando $x$ como constante.
202|
203|> **Relación clave:** La **continuidad** de $f$ en un punto **no garantiza** la existencia de sus derivadas parciales, pero la **diferenciabilidad** (existencia de derivadas parciales continuas) sí implica continuidad. El estudio de límites es, por tanto, la base sobre la que se construye todo el cálculo diferencial en varias variables.
204|
205|---
206|
207|## 9. Resumen Visual de Conceptos
208|
209|```
210|        LÍMITES Y CONTINUIDAD (varias variables)
211|                    │
212|        ┌───────────┴───────────┐
213|        ▼                       ▼
214|    LÍMITE                  CONTINUIDAD
215|    lim f(x,y)=L            lim f(x,y)=f(a,b)
216|        │                       │
217|    ┌───┴───┐               ┌───┴───┐
218|    ▼       ▼               ▼       ▼
219| Existe   No existe     Continua  Discontinua
220| (único L  (2 tray.    (sin       (con
221| por toda  distintas)   quiebres)  quiebres)
222| trayectoria)
223|        │                       │
224|        └───────────┬───────────┘
225|                    ▼
226|            DERIVADAS PARCIALES
227|        (definidas como límites)
228|```
229|
230|---
231|
232|*Resumen elaborado a partir de Cálculo Vectorial, Bento de Jesus Caraça, Sección 13.2 (pp. 167–173) y Sección 13.3 (pp. 174–175).*
233|