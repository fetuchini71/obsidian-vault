1|# Resumen Ejecutivo: Matrices
2|
3|**Fuente:** *Álgebra Lineal* — Bernard Kolman & David R. Hill  
4|**Páginas de referencia:** 34–60 (Capítulo 1, secciones 1.2 y 1.3)  

**Fuentes en el vault:** [[Libros/Algebra/kolman-algebra-lineal|Kolman]]

5|**Tipo de apunte:** Resumen ejecutivo
6|
7|---
8|
9|## 1. Definición principal
10|
11|> **Matriz:** Una matriz $A$ de $m \times n$ es un arreglo rectangular de $mn$ números reales (o complejos) ordenados en $m$ filas (renglones) horizontales y $n$ columnas verticales. Se denota como $A = [a_{ij}]$, donde $a_{ij}$ es la entrada $(i,j)$ (elemento en la fila $i$, columna $j$).  
12|> (*Kolman, pág. 34*)
13|
14|- Si $m = n$, la matriz es **cuadrada de orden $n$**, y los elementos $a_{11}, a_{22}, \dots, a_{nn}$ forman la **diagonal principal**.  
15|  (*Kolman, pág. 34*)
16|- El conjunto de todos los $n$-vectores (matrices $1 \times n$ o $n \times 1$) con entradas reales se denota $\mathbb{R}^n$; con entradas complejas, $\mathbb{C}^n$.  
17|  (*Kolman, pág. 35*)
18|
19|---
20|
21|## 2. Tipos de matrices
22|
23|| Tipo | Definición | Ejemplo (Kolman) |
24||---|---|---|
25|| **Matriz cuadrada** | $m = n$ | $D$ de $3 \times 3$ (pág. 35) |
26|| **Matriz diagonal** | $a_{ij} = 0$ para $i \neq j$ | $G = \begin{bmatrix}4 & 0 \\ 0 & -2\end{bmatrix}$ (pág. 36) |
27|| **Matriz escalar** | Diagonal con todos los elementos de la diagonal iguales: $a_{ij} = c$ si $i=j$, $0$ si $i \neq j$ | $I_3$ (identidad) y $J = \begin{bmatrix}-2 & 0 \\ 0 & -2\end{bmatrix}$ (pág. 37) |
28|| **$n$-vector** | Matriz de $1 \times n$ (fila) o $n \times 1$ (columna) | $u = \begin{bmatrix}1 & 2 & -1 & 0\end{bmatrix}$ (pág. 35) |
29|| **Matriz nula ($O$)** | Todas sus entradas son $0$ | (pág. 35, 43) |
30|| **Matriz triangular superior** | $a_{ij} = 0$ para $i > j$ | (pág. 43, ej. T.5) |
31|| **Matriz triangular inferior** | $a_{ij} = 0$ para $i < j$ | (pág. 43, ej. T.5) |
32|| **Matriz binaria (booleana)** | Todas las entradas son $0$ o $1$ (bits); la aritmética usada es binaria (base 2) | $A = \begin{bmatrix}1 & 0 & 0 \\ 1 & 1 & 1 \\ 0 & 1 & 0\end{bmatrix}$ (pág. 42) |
33|
34|---
35|
36|## 3. Operaciones fundamentales
37|
38|### 3.1 Igualdad de matrices  
39|Dos matrices $A = [a_{ij}]$ y $B = [b_{ij}]$ de $m \times n$ son iguales si $a_{ij} = b_{ij}$ para todo $i,j$ (elementos correspondientes iguales).  
40|(*Kolman, pág. 37*)
41|
42|### 3.2 Suma de matrices  
43|Si $A$ y $B$ son del mismo tamaño $m \times n$, su suma $C = A + B$ se define como $c_{ij} = a_{ij} + b_{ij}$.  
44|(*Kolman, pág. 38*)
45|
46|### 3.3 Multiplicación por un escalar  
47|Dada $A = [a_{ij}]$ de $m \times n$ y $r \in \mathbb{R}$, el múltiplo escalar es $rA = [r a_{ij}]$.  
48|(*Kolman, pág. 39*)
49|
50|### 3.4 Diferencia de matrices  
51|$A - B = A + (-1)B$.  
52|(*Kolman, pág. 39*)
53|
54|### 3.5 Combinación lineal  
55|$c_1 A_1 + c_2 A_2 + \cdots + c_k A_k$, con $c_i$ escalares.  
56|(*Kolman, pág. 40*)
57|
58|### 3.6 Transpuesta  
59|La transpuesta de $A$ ($m \times n$) es $A^T$ ($n \times m$), donde $(A^T)_{ij} = a_{ji}$ (las filas de $A^T$ son las columnas de $A$).  
60|(*Kolman, pág. 40*)
61|
62|### 3.7 Producto punto (producto interior)  
63|Dados $a = [a_1\ \dots\ a_n]^T$ y $b = [b_1\ \dots\ b_n]^T$,  
64|
65|$$a \cdot b = \sum_{i=1}^n a_i b_i.$$
66|
67|(*Kolman, pág. 46*)
68|
69|### 3.8 Multiplicación de matrices  
70|Si $A$ es $m \times p$ y $B$ es $p \times n$, el producto $AB$ es $C$ de $m \times n$, con  
71|
72|$$c_{ij} = \sum_{k=1}^p a_{ik} b_{kj} = \text{fila}_i(A) \cdot \text{col}_j(B).$$
73|
74|(*Kolman, pág. 47*)
75|
76|**Condición de existencia:** El número de columnas de $A$ debe ser igual al número de filas de $B$.
77|
78|---
79|
80|## 4. Propiedades clave
81|
82|| Propiedad | Expresión | Observación |
83||---|---|---|
84|| **Asociatividad de la suma** | $A + (B + C) = (A + B) + C$ | (*Kolman, pág. 38*, se menciona como preludio al Teorema 1.1) |
85|| **Asociatividad del producto** | $A(BC) = (AB)C$ | Se cumple cuando los tamaños son compatibles |
86|| **Distributividad** | $A(B + C) = AB + AC$ | — |
87|| **No conmutatividad del producto** | $AB \neq BA$ (en general) | (*Kolman, pág. 49*, ej. 10: $AB \neq BA$) |
88|| **Transpuesta de la suma** | $(A + B)^T = A^T + B^T$ | — |
89|| **Transpuesta del producto** | $(AB)^T = B^T A^T$ | — |
90|| **Transpuesta de la transpuesta** | $(A^T)^T = A$ | (*Kolman, pág. 40*, ej. 15) |
91|| **Columna $j$ de $AB$** | $\text{col}_j(AB) = A\ \text{col}_j(B)$ | Es una combinación lineal de las columnas de $A$ con coeficientes de la columna $j$ de $B$ (*Kolman, pág. 50*) |
92|| **Producto matriz-vector como combinación lineal** | $Ac = c_1 \text{col}_1(A) + \cdots + c_n \text{col}_n(A)$ | (*Kolman, pág. 51*) |
93|
94|> **Nota:** La sección 1.4 del libro desarrolla formalmente todas las propiedades algebraicas de las operaciones matriciales (análogas en muchos aspectos a las de los números reales, excepto la conmutatividad del producto).  
95|> (*Kolman, pág. 38, referencia a sección 1.4*)
96|
97|---
98|
99|## 5. Sistemas lineales y matrices
100|
101|Un sistema de $m$ ecuaciones lineales con $n$ incógnitas  
102|
103|$$
104|\begin{cases}
105|a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
106|\ \ \vdots \\
107|a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m
108|\end{cases}
109|$$
110|
111|se escribe en **forma matricial** como $A\mathbf{x} = \mathbf{b}$, donde:
112|
113|$$A = \begin{bmatrix} a_{ij} \end{bmatrix}\quad (\text{matriz de coeficientes}),\qquad
114|\mathbf{x} = \begin{bmatrix} x_1 \\ \vdots \\ x_n \end{bmatrix},\qquad
115|\mathbf{b} = \begin{bmatrix} b_1 \\ \vdots \\ b_m \end{bmatrix}.$$
116|
117|(*Kolman, pág. 52*)
118|
119|La **matriz aumentada** es $[\,A \mid \mathbf{b}\,]$.  
120|(*Kolman, pág. 52*)
121|
122|Alternativamente, el sistema puede verse como una **combinación lineal de las columnas** de $A$:
123|
124|$$x_1 \text{col}_1(A) + x_2 \text{col}_2(A) + \cdots + x_n \text{col}_n(A) = \mathbf{b}.$$
125|
126|(*Kolman, pág. 53*)
127|
128|---
129|
130|## 6. Partición de matrices (por bloques)
131|
132|Una matriz puede subdividirse en **submatrices** trazando líneas horizontales y verticales. La multiplicación por bloques sigue las mismas reglas que la multiplicación ordinaria, siempre que los productos de las submatrices estén definidos. Esto es útil para trabajar con matrices muy grandes en computación (procesamiento paralelo, manejo de memoria limitada).  
133|(*Kolman, págs. 53–56*)
134|
135|---
136|
137|## 7. Matrices binarias (booleanas)
138|
139|- **Definición:** Matriz cuyas entradas son solo $0$ o $1$ (bits).  
140|  (*Kolman, pág. 42*)
141|- **Aritmética:** Se usa la aritmética binaria (base 2, tablas 1.1 y 1.2).  
142|  (*Kolman, pág. 41*)
143|- **Inverso aditivo:** En binario, $1 + 1 = 0$, por lo que el inverso aditivo de $1$ es $1$ mismo; luego $A - B = A + B$.  
144|  (*Kolman, pág. 42*)
145|- **Aplicación:** Códigos de corrección de errores, teoría de la información, interruptores ON/OFF.  
146|  (*Kolman, págs. 41–43*)
147|
148|---
149|
150|## 8. Aplicaciones destacadas
151|
152|| Aplicación | Descripción (Kolman) |
153||---|---|
154|| **Producción industrial** | Matriz $4 \times 3$ que registra unidades de 3 productos elaborados en 4 plantas (pág. 35) |
155|| **Factor de congelación del viento** | Tabla temperatura/velocidad del viento representada como matriz (pág. 36) |
156|| **Google® y PageRank** | Matriz de conectividad $n \times n$ que rastrea enlaces entre sitios web; las páginas con más enlaces obtienen mayor "importancia" (pág. 37) |
157|| **Cadenas ecológicas** | Cantidad de pesticida absorbido por plantas → herbívoros, modelado mediante multiplicación de matrices (pág. 49) |
158|| **Costos de manufactura** | Suma de matrices de costos de producción entre dos fábricas (pág. 38) |
159|| **Calificación promedio** | Producto punto entre vector de ponderaciones y vector de notas (pág. 46) |
160|
161|---
162|
163|## 9. Conexiones con otros temas
164|
165|1. **Sistemas de ecuaciones lineales** (Cap. 1): Las matrices son la herramienta central para representar y resolver sistemas lineales mediante eliminación gaussiana.
166|2. **Vectores en $\mathbb{R}^n$** (Cap. 4): Los $n$-vectores son casos particulares de matrices; el producto punto y la combinación lineal son operaciones fundamentales compartidas.
167|3. **Espacios vectoriales** (Cap. 4): Las matrices forman espacios vectoriales bajo la suma y la multiplicación por escalares.
168|4. **Transformaciones lineales** (Cap. 4): Toda transformación lineal puede representarse mediante una matriz.
169|5. **Determinantes** (Cap. 2): Se definen solo para matrices cuadradas y están íntimamente ligados a la invertibilidad.
170|6. **Valores y vectores propios** (Cap. 7): El PageRank de Google® se reduce al cálculo del vector propio dominante de una matriz de orden $2.7 \times 10^9$ (pág. 37).
171|7. **Códigos de corrección de errores**: Las matrices binarias son esenciales en teoría de la información y codificación (pág. 42).
172|8. **Cómputo paralelo**: La multiplicación por bloques permite dividir el trabajo entre múltiples procesadores (pág. 55).
173|
174|---
175|
176|## 10. Notación importante
177|
178|- **Notación de suma (sigma):** $\displaystyle\sum_{i=1}^n a_i$ representa $a_1 + a_2 + \cdots + a_n$.  
179|  (*Kolman, pág. 56*)
180|- **Elemento $(i,j)$ del producto:** $\displaystyle c_{ij} = \sum_{k=1}^p a_{ik} b_{kj}$.  
181|  (*Kolman, pág. 57*)
182|- **Suma doble:** $\displaystyle\sum_{j=1}^m \sum_{i=1}^n a_{ij} = \sum_{i=1}^n \sum_{j=1}^m a_{ij}$ (el orden no altera la suma total).  
183|  (*Kolman, pág. 57*)
184|
185|---
186|
187|*Resumen generado a partir de la extracción de Kolman & Hill, Álgebra Lineal (págs. 34–60).*
188|