# Resumen Ejecutivo: Matrices

**Fuente:** *Álgebra Lineal* — Bernard Kolman & David R. Hill  
**Páginas de referencia:** 34–60 (Capítulo 1, secciones 1.2 y 1.3)  
**Tipo de apunte:** Resumen ejecutivo

---

## 1. Definición principal

> **Matriz:** Una matriz $A$ de $m \times n$ es un arreglo rectangular de $mn$ números reales (o complejos) ordenados en $m$ filas (renglones) horizontales y $n$ columnas verticales. Se denota como $A = [a_{ij}]$, donde $a_{ij}$ es la entrada $(i,j)$ (elemento en la fila $i$, columna $j$).  
> (*Kolman, pág. 34*)

- Si $m = n$, la matriz es **cuadrada de orden $n$**, y los elementos $a_{11}, a_{22}, \dots, a_{nn}$ forman la **diagonal principal**.  
  (*Kolman, pág. 34*)
- El conjunto de todos los $n$-vectores (matrices $1 \times n$ o $n \times 1$) con entradas reales se denota $\mathbb{R}^n$; con entradas complejas, $\mathbb{C}^n$.  
  (*Kolman, pág. 35*)

---

## 2. Tipos de matrices

| Tipo | Definición | Ejemplo (Kolman) |
|---|---|---|
| **Matriz cuadrada** | $m = n$ | $D$ de $3 \times 3$ (pág. 35) |
| **Matriz diagonal** | $a_{ij} = 0$ para $i \neq j$ | $G = \begin{bmatrix}4 & 0 \\ 0 & -2\end{bmatrix}$ (pág. 36) |
| **Matriz escalar** | Diagonal con todos los elementos de la diagonal iguales: $a_{ij} = c$ si $i=j$, $0$ si $i \neq j$ | $I_3$ (identidad) y $J = \begin{bmatrix}-2 & 0 \\ 0 & -2\end{bmatrix}$ (pág. 37) |
| **$n$-vector** | Matriz de $1 \times n$ (fila) o $n \times 1$ (columna) | $u = \begin{bmatrix}1 & 2 & -1 & 0\end{bmatrix}$ (pág. 35) |
| **Matriz nula ($O$)** | Todas sus entradas son $0$ | (pág. 35, 43) |
| **Matriz triangular superior** | $a_{ij} = 0$ para $i > j$ | (pág. 43, ej. T.5) |
| **Matriz triangular inferior** | $a_{ij} = 0$ para $i < j$ | (pág. 43, ej. T.5) |
| **Matriz binaria (booleana)** | Todas las entradas son $0$ o $1$ (bits); la aritmética usada es binaria (base 2) | $A = \begin{bmatrix}1 & 0 & 0 \\ 1 & 1 & 1 \\ 0 & 1 & 0\end{bmatrix}$ (pág. 42) |

---

## 3. Operaciones fundamentales

### 3.1 Igualdad de matrices  
Dos matrices $A = [a_{ij}]$ y $B = [b_{ij}]$ de $m \times n$ son iguales si $a_{ij} = b_{ij}$ para todo $i,j$ (elementos correspondientes iguales).  
(*Kolman, pág. 37*)

### 3.2 Suma de matrices  
Si $A$ y $B$ son del mismo tamaño $m \times n$, su suma $C = A + B$ se define como $c_{ij} = a_{ij} + b_{ij}$.  
(*Kolman, pág. 38*)

### 3.3 Multiplicación por un escalar  
Dada $A = [a_{ij}]$ de $m \times n$ y $r \in \mathbb{R}$, el múltiplo escalar es $rA = [r a_{ij}]$.  
(*Kolman, pág. 39*)

### 3.4 Diferencia de matrices  
$A - B = A + (-1)B$.  
(*Kolman, pág. 39*)

### 3.5 Combinación lineal  
$c_1 A_1 + c_2 A_2 + \cdots + c_k A_k$, con $c_i$ escalares.  
(*Kolman, pág. 40*)

### 3.6 Transpuesta  
La transpuesta de $A$ ($m \times n$) es $A^T$ ($n \times m$), donde $(A^T)_{ij} = a_{ji}$ (las filas de $A^T$ son las columnas de $A$).  
(*Kolman, pág. 40*)

### 3.7 Producto punto (producto interior)  
Dados $a = [a_1\ \dots\ a_n]^T$ y $b = [b_1\ \dots\ b_n]^T$,  

$$a \cdot b = \sum_{i=1}^n a_i b_i.$$

(*Kolman, pág. 46*)

### 3.8 Multiplicación de matrices  
Si $A$ es $m \times p$ y $B$ es $p \times n$, el producto $AB$ es $C$ de $m \times n$, con  

$$c_{ij} = \sum_{k=1}^p a_{ik} b_{kj} = \text{fila}_i(A) \cdot \text{col}_j(B).$$

(*Kolman, pág. 47*)

**Condición de existencia:** El número de columnas de $A$ debe ser igual al número de filas de $B$.

---

## 4. Propiedades clave

| Propiedad | Expresión | Observación |
|---|---|---|
| **Asociatividad de la suma** | $A + (B + C) = (A + B) + C$ | (*Kolman, pág. 38*, se menciona como preludio al Teorema 1.1) |
| **Asociatividad del producto** | $A(BC) = (AB)C$ | Se cumple cuando los tamaños son compatibles |
| **Distributividad** | $A(B + C) = AB + AC$ | — |
| **No conmutatividad del producto** | $AB \neq BA$ (en general) | (*Kolman, pág. 49*, ej. 10: $AB \neq BA$) |
| **Transpuesta de la suma** | $(A + B)^T = A^T + B^T$ | — |
| **Transpuesta del producto** | $(AB)^T = B^T A^T$ | — |
| **Transpuesta de la transpuesta** | $(A^T)^T = A$ | (*Kolman, pág. 40*, ej. 15) |
| **Columna $j$ de $AB$** | $\text{col}_j(AB) = A\ \text{col}_j(B)$ | Es una combinación lineal de las columnas de $A$ con coeficientes de la columna $j$ de $B$ (*Kolman, pág. 50*) |
| **Producto matriz-vector como combinación lineal** | $Ac = c_1 \text{col}_1(A) + \cdots + c_n \text{col}_n(A)$ | (*Kolman, pág. 51*) |

> **Nota:** La sección 1.4 del libro desarrolla formalmente todas las propiedades algebraicas de las operaciones matriciales (análogas en muchos aspectos a las de los números reales, excepto la conmutatividad del producto).  
> (*Kolman, pág. 38, referencia a sección 1.4*)

---

## 5. Sistemas lineales y matrices

Un sistema de $m$ ecuaciones lineales con $n$ incógnitas  

$$
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
\ \ \vdots \\
a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m
\end{cases}
$$

se escribe en **forma matricial** como $A\mathbf{x} = \mathbf{b}$, donde:

$$A = \begin{bmatrix} a_{ij} \end{bmatrix}\quad (\text{matriz de coeficientes}),\qquad
\mathbf{x} = \begin{bmatrix} x_1 \\ \vdots \\ x_n \end{bmatrix},\qquad
\mathbf{b} = \begin{bmatrix} b_1 \\ \vdots \\ b_m \end{bmatrix}.$$

(*Kolman, pág. 52*)

La **matriz aumentada** es $[\,A \mid \mathbf{b}\,]$.  
(*Kolman, pág. 52*)

Alternativamente, el sistema puede verse como una **combinación lineal de las columnas** de $A$:

$$x_1 \text{col}_1(A) + x_2 \text{col}_2(A) + \cdots + x_n \text{col}_n(A) = \mathbf{b}.$$

(*Kolman, pág. 53*)

---

## 6. Partición de matrices (por bloques)

Una matriz puede subdividirse en **submatrices** trazando líneas horizontales y verticales. La multiplicación por bloques sigue las mismas reglas que la multiplicación ordinaria, siempre que los productos de las submatrices estén definidos. Esto es útil para trabajar con matrices muy grandes en computación (procesamiento paralelo, manejo de memoria limitada).  
(*Kolman, págs. 53–56*)

---

## 7. Matrices binarias (booleanas)

- **Definición:** Matriz cuyas entradas son solo $0$ o $1$ (bits).  
  (*Kolman, pág. 42*)
- **Aritmética:** Se usa la aritmética binaria (base 2, tablas 1.1 y 1.2).  
  (*Kolman, pág. 41*)
- **Inverso aditivo:** En binario, $1 + 1 = 0$, por lo que el inverso aditivo de $1$ es $1$ mismo; luego $A - B = A + B$.  
  (*Kolman, pág. 42*)
- **Aplicación:** Códigos de corrección de errores, teoría de la información, interruptores ON/OFF.  
  (*Kolman, págs. 41–43*)

---

## 8. Aplicaciones destacadas

| Aplicación | Descripción (Kolman) |
|---|---|
| **Producción industrial** | Matriz $4 \times 3$ que registra unidades de 3 productos elaborados en 4 plantas (pág. 35) |
| **Factor de congelación del viento** | Tabla temperatura/velocidad del viento representada como matriz (pág. 36) |
| **Google® y PageRank** | Matriz de conectividad $n \times n$ que rastrea enlaces entre sitios web; las páginas con más enlaces obtienen mayor "importancia" (pág. 37) |
| **Cadenas ecológicas** | Cantidad de pesticida absorbido por plantas → herbívoros, modelado mediante multiplicación de matrices (pág. 49) |
| **Costos de manufactura** | Suma de matrices de costos de producción entre dos fábricas (pág. 38) |
| **Calificación promedio** | Producto punto entre vector de ponderaciones y vector de notas (pág. 46) |

---

## 9. Conexiones con otros temas

1. **Sistemas de ecuaciones lineales** (Cap. 1): Las matrices son la herramienta central para representar y resolver sistemas lineales mediante eliminación gaussiana.
2. **Vectores en $\mathbb{R}^n$** (Cap. 4): Los $n$-vectores son casos particulares de matrices; el producto punto y la combinación lineal son operaciones fundamentales compartidas.
3. **Espacios vectoriales** (Cap. 4): Las matrices forman espacios vectoriales bajo la suma y la multiplicación por escalares.
4. **Transformaciones lineales** (Cap. 4): Toda transformación lineal puede representarse mediante una matriz.
5. **Determinantes** (Cap. 2): Se definen solo para matrices cuadradas y están íntimamente ligados a la invertibilidad.
6. **Valores y vectores propios** (Cap. 7): El PageRank de Google® se reduce al cálculo del vector propio dominante de una matriz de orden $2.7 \times 10^9$ (pág. 37).
7. **Códigos de corrección de errores**: Las matrices binarias son esenciales en teoría de la información y codificación (pág. 42).
8. **Cómputo paralelo**: La multiplicación por bloques permite dividir el trabajo entre múltiples procesadores (pág. 55).

---

## 10. Notación importante

- **Notación de suma (sigma):** $\displaystyle\sum_{i=1}^n a_i$ representa $a_1 + a_2 + \cdots + a_n$.  
  (*Kolman, pág. 56*)
- **Elemento $(i,j)$ del producto:** $\displaystyle c_{ij} = \sum_{k=1}^p a_{ik} b_{kj}$.  
  (*Kolman, pág. 57*)
- **Suma doble:** $\displaystyle\sum_{j=1}^m \sum_{i=1}^n a_{ij} = \sum_{i=1}^n \sum_{j=1}^m a_{ij}$ (el orden no altera la suma total).  
  (*Kolman, pág. 57*)

---

*Resumen generado a partir de la extracción de Kolman & Hill, Álgebra Lineal (págs. 34–60).*
