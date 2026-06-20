# Extracción: Kolman - Algebra Lineal
**Páginas:** 34-60
**Fuente:** Algebra\Bernard_Kolman_David_R_762p_7.0MB.pdf
---


## Página 34

1.2 MATRICES
Si analizamos el método de eliminación descrito en la sección 1.1, observaremos lo si-
guiente. Al realizar los pasos necesarios, sólo modificamos los números que aparecen
junto a las incógnitas x1, x2, . . . , xn. En consecuencia, podríamos buscar una forma de
escribir un sistema lineal sin tener que mantener las incógnitas. En esta sección defini-
remos un objeto, una matriz, que nos permite hacer precisamente eso: escribir sistemas
lineales de una manera compacta que facilite la automatización del método de elimina-
ción en una computadora, dándonos un procedimiento rápido y eficaz para determinar
las soluciones. Su uso, sin embargo, no nos proporciona solamente la oportunidad de
contar con una notación conveniente, sino también —como veremos a continuación—
resolver sistemas de ecuaciones lineales y otros problemas computacionales de manera
rápida y eficiente, desarrollando operaciones sobre las matrices y trabajando con ellas
de acuerdo con las reglas que cumplen. Por supuesto, como debe hacer cualquier bue-
na definición, la del concepto de matriz no sólo permite mirar de otra forma los proble-
mas existentes, sino que, además, da lugar a muchas nuevas preguntas, algunas de las
cuales estudiaremos en este libro.
DEFINICIÓN
Una matriz A de m × n es un arreglo rectangular de mn números reales (o complejos)
ordenados en m filas (renglones) horizontales y n columnas verticales:
La i-ésima fila de A es
La j-ésima columna de A es
Diremos que A es m por n (que se escribe m × n). Si m = n, decimos que A es una
matriz cuadrada de orden n, y que los números a11, a22, . . . , ann forman la diagonal
principal de A. Nos referimos al número aij, que está en la i-ésima fila (renglón) y la
j-ésima columna de A, como el i, j-ésimo elemento de A, o la entrada (i, j) de A, y so-
lemos escribir (1) como
A = [aij].
Para simplificar, en este libro restringiremos nuestra atención (salvo en el apéndi-
ce A) al análisis de las matrices cuyas entradas son números reales. Sin embargo, también
se estudian las matrices con entradas complejas, mismas que tienen gran importancia
en muchas aplicaciones.
⎡
⎢⎢⎣
a1 j
a2 j
...
amj
⎤
⎥⎥⎦
(1 ≤j ≤n).
ai1
ai2
· · ·
ain
(1 ≤i ≤m);
A =
⎡
⎢⎢⎢⎢⎢⎢⎢⎣
a11
a12
· · ·
· · ·
a1 j
· · ·
a1n
a21
a22
· · ·
· · ·
a2 j
· · ·
a2n
...
...
· · ·
· · ·
...
· · ·
...
ai1
ai2
· · ·
· · ·
columna j
(renglón) i
fila
ai j
· · ·
ain
...
...
...
...
am1
am2
· · ·
· · ·
amj
· · ·
amn
⎤
⎥⎥⎥⎥⎥⎥⎥⎦
.
10
Capítulo 1
Ecuaciones lineales y matrices
(1)


## Página 35

EJEMPLO 1
Sean
Entonces, A es una matriz de 2 × 3 con a12 = 2, a13 = 3, a22 = 0 y a23 = 1; B es una
matriz de 2 × 2, con b11 = 1, b12 = 4, b21 = 2 y b22 = −3; C es una matriz de 3 × 1,
con c11 = 1, c21 = −1 y c31 = 2; D es una matriz de 3 × 3; E es una matriz de 1 × 1, y F
es una matriz de 1 × 3. En D, los elementos d11 = 1, d22 = 0 y d33 = 2 forman la dia-
gonal principal.
■
Por conveniencia, en los ejemplos y ejercicios ilustrativos de los capítulos 1 a
7 centramos gran parte de nuestra atención en matrices y expresiones que sólo tienen
números reales. Por otra parte, aunque aparecen en algunos ejemplos de los capítulos 8 y
9, es en el apéndice A donde puede encontrarse una introducción a los números com-
plejos y a sus propiedades, así como ejemplos y ejercicios que muestran cómo se utili-
zan estos números en álgebra lineal.
Las matrices de 1 × n o n × 1 también se denominan un n-vectores, y lo denota-
remos mediante letras minúsculas en negritas. Cuando se sobreentienda el valor de n,
nos referiremos a los n-vectores sólo como vectores. En el capítulo 4 analizaremos los
vectores a detalle.
EJEMPLO 2
■
Si todas las entradas de un n-vector son iguales a cero, se denota con 0.
Observe que si A es una matriz de n × n, los renglones de A son matrices de 1 × n.
El conjunto de todos los n-vectores con entradas reales se denota con Rn. De manera si-
milar, el conjunto de todos los n-vectores con entradas complejas se denota mediante
Cn. Como se indicó anteriormente, en los primeros siete capítulos de este libro trabaja-
remos casi por completo con vectores en Rn.
EJEMPLO 3
(Despliegue de valores en forma de tabla) La matriz siguiente proporciona las dis-
tancias entre las ciudades indicadas (en millas terrestres).
■
EJEMPLO 4
(Producción) Suponga que un fabricante tiene cuatro plantas, en cada una de las cua-
les se manufacturan tres productos. Si denotamos con aij el número de unidades del pro-
ducto i elaboradas por la planta j en una semana, la matriz de 4 × 3
⎡
⎢⎣
Producto 1  Producto 2  Producto 3
Planta1
560
340
280
Planta2
360
450
270
Planta3
380
420
210
Planta4
0
80
380
⎤
⎥⎦
⎡
⎢⎣
Londres 
 
Londres
0
785
3,469
5,959
Madrid
785
0
3,593
6,706
Nueva York
3,469
3,593
0
6,757
Tokio
5,959
6,706
6,757
0
⎤
⎥⎦
Nueva York
Tokio
Madrid
u = 1
2
−1
0 es un 4-vector y v =
⎡
⎣
1
−1
3
⎤
⎦es un 3-vector.
A =
1
2
3
−1
0
1 ,
B =
1
4
2
−3 ,
C =
⎡
⎣
1
−1
2
⎤
⎦,
D =
⎡
⎣
1
1
0
2
0
1
3
−1
2
⎤
⎦,
E = 3 ,
F = −1
0
2 .
Sec. 1.2
Matrices
11


## Página 36

proporciona la producción semanal del fabricante. Por ejemplo, en una semana, la plan-
ta 2 produce 270 unidades del producto 3.
■
EJEMPLO 5
La tabla siguiente, en donde se lista el factor de congelación del viento, muestra cómo
una combinación de la temperatura y la velocidad del viento hace que un cuerpo se
sienta más frío que la temperatura real. Por ejemplo, cuando la temperatura es de 10 °F
y el viento es de 15 millas por hora, el cuerpo pierde la misma cantidad de calor que la
que perdería si la temperatura fuera de −18 °F sin viento.
Esta tabla puede representarse como la matriz
■
EJEMPLO 6
Con el sistema lineal considerado en el ejemplo 5 de la sección 1.1,
podemos asociar las matrices siguientes:
En la sección 1.3, llamaremos A a la matriz de coeficientes del sistema lineal.
■
DEFINICIÓN
Una matriz cuadrada A = [aij], en donde cada término fuera de la diagonal principal es
igual a cero, es decir, aij = 0 para i  j, es una matriz diagonal.
EJEMPLO 7
son matrices diagonales.
■
G =
4
0
0
−2
y
H =
⎡
⎣
−3
0
0
0
−2
0
0
0
4
⎤
⎦
A =
⎡
⎣
1
2
2
−2
3
5
⎤
⎦,
x =
x
y ,
b =
⎡
⎣
10
−4
26
⎤
⎦.
x + 2y = 10
2x −2y = −4
3x + 5y = 26,
A =
⎡
⎢⎣
5
12
7
0
−5
−10
−15
10
−3
−9
−15
−22
−27
−34
15
−11
−18
−25
−31
−38
−45
20
−17
−24
−31
−39
−46
−53
⎤
⎥⎦.
◦F
15
10
5
0
−5
−10
mph
5
12
7
0
−5
−10
−15
10
−3
−9
−15
−22
−27
−34
15
−11
−18
−25
−31
−38
−45
20
−17
−24
−31
−39
−46
−53
12
Capítulo 1
Ecuaciones lineales y matrices


## Página 37

DEFINICIÓN
Una matriz diagonal A = [aij], en donde todos los términos de la diagonal principal son
iguales, es decir, aij = c para i = j y aij = 0 para i  j, es una matriz escalar.
EJEMPLO 8
Las siguientes son matrices escalares:
■
Los motores de búsqueda para localización y recuperación de información en In-
ternet, utilizan matrices para seguir el rastro de las ubicaciones en donde ésta se en-
cuentra, el tipo de información que se halla en cada ubicación, las palabras clave que
aparecen en ellas, e incluso la manera en que los sitios Web se vinculan entre sí con
otros. En gran medida, la eficacia de Google© estriba en la manera en que utiliza las
matrices para determinar cuáles sitios están referenciados en otros sitios. Esto es, en lu-
gar de mantener de manera directa el rastro del contenido de la información de una pá-
gina Web real o de un tema de búsqueda individual, la estructura de la matriz de Google
determina las páginas Web que coinciden con el tema de búsqueda, y luego presenta
una lista de tales páginas en un orden de “importancia”.
Suponga que existen n páginas Web accesibles durante cierto mes. Una manera
sencilla de comprender las matrices que conforman el esquema de Google, consiste en
imaginar una matriz A de n × n, denominada “matriz de conectividad”, la cual sólo con-
tiene ceros al principio. Para construir las conexiones se procede como sigue. Cuando
se detecta que el sitio Web j está vinculado con el sitio Web i, la entrada aij se hace igual
a uno. Como n es muy grande —su valor se calculaba en alrededor de 3 mil millones
en diciembre de 2002—, casi todas las entradas de la matriz de conectividad A son ce-
ro. (Las matrices como ésta se denominan esparcidas, ralas o poco densas.) Si la fila
(renglón) i de A contiene muchos unos, significa que existen muchos sitios vinculados
al sitio i. El software que controla el motor de búsqueda de Google considera que los
sitios que están vinculados con muchos otros son más “importantes” (en otras palabras,
les da una calificación más alta). Por lo tanto, tales sitios aparecerían al principio de la
lista de resultados de búsqueda que generaría Google cuando el usuario solicitara temas
relacionados con la información del sitio i. Ya que Google actualiza su matriz de conec-
tividad cada mes, n aumenta con el paso del tiempo, al agregarse nuevos enlaces y si-
tios.
La técnica fundamental que utiliza Google© para calificar los sitios, emplea con-
ceptos de álgebra lineal que están fuera del alcance de este curso. Información adicio-
nal sobre el tema puede encontrarse en las fuentes siguientes.
1. Berry, Michael W. y Murray Browne. Understanding Search Engines—Mathematical
Modeling and Text Retrieval. Filadelfia: Siam, 1999.
2. www.google.com/technology/index.html
3. Moler, Cleve. “The World’s Largest Matrix Computation: Google’s Page Rank Is an
Eigenvector of a Matrix of Order 2.7 Billion”, MATLAB News and Notes, octubre de
2002, páginas 12-13.
En matemáticas, siempre que se presenta un nuevo objeto es preciso definir cuan-
do dos de ellos son iguales. Por ejemplo, en el conjunto de todos los números raciona-
les, decimos que los números 
y 
son iguales, aunque no se representen de la misma
manera. Lo que tenemos en mente es la definición según la cual 
es igual a 
cuando
ad = bc. De acuerdo con esto, tenemos la siguiente definición.
DEFINICIÓN
Dos matrices de m × n, A = [aij] y B = [bij], son iguales si aij = bij, 1 ≤i ≤m, 1 ≤j
≤n, es decir, si los elementos correspondientes son iguales.
c
d
a
b
4
6
2
3
I3 =
⎡
⎣
1
0
0
0
1
0
0
0
1
⎤
⎦,
J =
−2
0
0
−2 .
Sec. 1.2
Matrices
13


## Página 38

EJEMPLO 9
Las matrices
son iguales si w = −1, x = −3, y = 0 y z = 5.
■
A continuación definiremos varias operaciones que producirán nuevas matrices a
partir de otras. Estas operaciones son útiles en las aplicaciones que involucran matrices.
SUMA DE MATRICES
DEFINICIÓN
Si A = [aij] y B = [bij] son matrices de m × n, la suma de A y B da por resultado la
matriz C = [cij] de m × n, definida por
cij = aij + bij
(i ≤i ≤m, 1 ≤j ≤n).
Es decir, C se obtiene sumando los elementos correspondientes de A y B.
EJEMPLO 10
Sean
Entonces
■
Observe que la suma de las matrices A y B sólo se define cuando A y B tienen el
mismo número de filas (renglones) y el mismo número de columnas; es decir, sólo
cuando A y B son del mismo tamaño.
establecemos la convención, al escribir A + B entendemos que A y B tienen el mis-
mo tamaño.
Hasta el momento, la suma de matrices sólo se ha definido para dos matrices. En
ocasiones, sin embargo, nuestro trabajo exigirá que sumemos más de dos matrices. El
teorema 1.1 de la sección siguiente muestra que la suma de matrices satisface la propie-
dad asociativa. A + (B + C) = (A + B) + C. En la sección 1.4 se consideran más pro-
piedades de las matrices, mismas que son similares a que satisfacen los números reales.
EJEMPLO 11
(Producción) Un fabricante de cierto producto realiza tres modelos, A, B y C. Algunas
partes artes de cada uno se elaboran en la fábrica F1, ubicada en de Taiwán, y después
se terminan en la fábrica F2, de Estados Unidos. El costo total de cada producto consta
de los costos de manufactura y de embarque. En consecuencia, los costos (en dólares) de
cada fábrica pueden describirse mediante las matrices F1 y F2 de 3 × 2:
14
Capítulo 1
Ecuaciones lineales y matrices
A =
⎡
⎣
1
2
−1
2
−3
4
0
−4
5
⎤
⎦
y
B =
⎡
⎣
1
2
w
2
x
4
y
−4
z
⎤
⎦
A =
1
−2
4
2
−1
3
y
B =
0
2
−4
1
3
1 .
F1 =
⎡
⎣
Costo de
 manufactura
Costo de
 embarque
32
40
50
80
70
20
⎤
⎦
Modelo A
Modelo B
Modelo C
A + B =
1 + 0
−2 + 2
4 + (−4)
2 + 1
−1 + 3
3 + 1
=
1
0
0
3
2
4 .


## Página 39

La matriz F1 + F2 proporciona los costos totales de manufactura y embarque de cada
producto. Así, los costos totales de un producto del modelo C son $200 y $40, respec-
tivamente.
■
MULTIPLICACIÓN POR UN ESCALAR
DEFINICIÓN
Si A = [aij] es una matriz de m × n y r es un número real, el múltiplo escalar de A por
r, rA, es la matriz B = [bij] de m × n, donde
bij = raij
(i ≤i ≤m, 1 ≤j ≤n).
Es decir, B se obtiene multiplicando cada elemento de A por r.
Si A y B son matrices de m × n, escribimos A +(−1)B como A −B, y denomina-
mos a esto diferencia de A y B.
EJEMPLO 12
Sean
Entonces
■
EJEMPLO 13
Sea p = [18.95
14.75
8.60] un 3-vector que representa los precios actuales de tres
artículos almacenados en una bodega. Suponga que el almacén anuncia una venta en
donde cada uno de estos artículos tiene un descuento de 20 por ciento.
(a) Determine un 3-vector que proporcione el cambio en el precio de cada uno de los
tres artículos.
(b) Determine un 3-vector que proporcione los precios nuevos de los artículos.
Solución
(a) Como el precio de cada artículo se reduce 20%, el 3-vector
proporciona la reducción de los precios para los tres artículos.
(b) Los precios nuevos de los artículos están dados mediante la expresión
Observe que esta expresión también puede escribirse como
p −0.20p = 0.80p.
■
Sec. 1.2
Matrices
15
F2 =
⎡
⎣
Costo de 
manufactura
Costo de 
embarque
40
60
50
50
130
20
⎤
⎦
Modelo A
Modelo B
Modelo C
A =
2
3
−5
4
2
1
y
B =
2
−1
3
3
5
−2 .
A −B =
2 −2
3 + 1
−5 −3
4 −3
2 −5
1 + 2
=
0
4
−8
1
−3
3 .
0.20p = (0.20)18.95
(0.20)14.75
(0.20)8.60
= 3.79
2.95
1.72
p −0.20p = 18.95
14.75
8.60 −3.79
2.95
1.72
= 15.16
11.80
6.88 .


## Página 40

Si A1, A2, . . . , Ak son matrices de m × n y c1, c2, . . . , ck son números reales, enton-
ces una expresión de la forma
c1A1 + c2A2 + · · · + ckAk
(2)
se denomina combinación lineal de A1, A2, . . . , Ak, y c1, c2, . . . , ck se llaman coe-
ficientes.
EJEMPLO 14
(a) Si
entonces 
es una combinación lineal de A1 y A2. Por medio de la
multiplicación por un escalar y la suma de matrices, podemos calcular C:
(b) 2[3
−2] – 3[5
0] + 4[−2
5] es una combinación lineal de [3
−2], [5
0] y
[−2
5]. Puede calcularse (verifíquelo) para obtener [−17
16].
(c)
LA TRANSPUESTA DE UNA MATRIZ
DEFINICIÓN
Si A = [aij] es una matriz de m × n, la matriz 
de n × m, donde
es la transpuesta de A. En consecuencia, las entradas en cada fila de AT son las entra-
das correspondientes en la columna de A.
EJEMPLO 15
Sean
aT
i j = a ji
(1 ≤i ≤n, 1 ≤j ≤m)
AT = aT
i j
C = 3A1 −1
2 A2
16
Capítulo 1
Ecuaciones lineales y matrices
A1 =
⎡
⎣
0
−3
5
2
3
4
1
−2
−3
⎤
⎦
y
A2 =
⎡
⎣
5
2
3
6
2
3
−1
−2
3
⎤
⎦,
C = 3
⎡
⎣
0
−3
5
2
3
4
1
−2
−3
⎤
⎦−1
2
⎡
⎣
5
2
3
6
2
3
−1
−2
3
⎤
⎦
=
⎡
⎢⎢⎣
−5
2
−10
27
2
3
8
21
2
7
2
−5
−21
2
⎤
⎥⎥⎦.
−0.5
⎡
⎣
1
−4
−6
⎤
⎦+ 0.4
es una combinación lineal de
⎡
⎣
0.1
−4
0.2
⎤
⎦
⎡
⎣
1
−4
−6
⎤
⎦y
⎡
⎣
0.1
−4
0.2
⎤
⎦.
⎡
⎣
−0.46
0.4
3.08
⎤
⎦.
Puede calcularse para obtener (verifíquelo)
A =
4
−2
3
0
5
−2 ,
B =
⎡
⎣
6
2
−4
3
−1
2
0
4
3
⎤
⎦,
C =
⎡
⎣
5
4
−3
2
2
−3
⎤
⎦,
D = 3
−5
1 ,
E =
⎡
⎣
2
−1
3
⎤
⎦.
■


## Página 41

Entonces
MATRICES DE BINARIAS (OPCIONAL)
En gran parte de nuestro trabajo con álgebra lineal utilizaremos matrices y vectores cu-
yas entradas son números reales o complejos. Por lo que los cálculos, como combinaciones
lineales, se determinan utilizando propiedades de las matrices y la aritmética estándar de
base 10. Sin embargo, el continuo desarrollo de la tecnología de cómputo ha traído al
primer plano el uso de la representación binaria (base 2) de la información. En casi to-
das las aplicaciones de cómputo, como juegos de vídeo, comunicaciones mediante fax,
transferencia electrónica de dinero, comunicaciones satelitales, DVD o la generación de
música en CD, la matemática subyacente es invisible y por completo transparente para
el espectador o el usuario. La información codificada en representación binaria está tan
extendida y desempeña un papel tan importante que estudiaremos brevemente algunas
de sus características. Iniciaremos con un análisis general de la suma y multiplicación
binarias, y luego hablaremos de una clase especial de matrices binarias, que tiene un lu-
gar clave en la teoría de la información y la comunicación.
La representación binaria de la información sólo utiliza dos símbolos, 0 y 1. La in-
formación está codificada en términos de 0 y 1 en una cadena de bits*. Por ejemplo, en
lenguaje binario, el número decimal 5 se representa mediante la cadena 101, que se in-
terpreta en términos de base 2 como sigue:
5 = 1(22) + 0(21) + 1(20).
Los coeficientes de las potencias de 2 determinan la cadena de bits, 101, que pro-
porciona la representación binaria de 5.
Al igual que utilizamos aritmética de base 10 cuando tratamos con números reales
y complejos, en otros escenarios empleamos aritmética de base 2, es decir, aritmética
binaria. La tabla 1.1 muestra la estructura de la suma binaria, y la tabla 1.2 la estructu-
ra de la multiplicación binaria.
Las propiedades de la aritmética binaria permiten la representación de combinacio-
nes de números reales en forma binaria, suele estudiarse en cursos básicos de ciencias
de la computación, o en cursos de matemáticas finitas o discretas. No desviaremos
nuestra atención para analizar tales temas en este momento. En cambio, nuestro objeti-
vo se centrará en un tipo particular de matrices y vectores cuyas entradas son dígitos bi-
narios. Esta clase de matrices y vectores es importante en el estudio de la teoría de la
información y en el campo de matemáticas de códigos de corrección de errores (tam-
bién llamado teoría de codificación).
Tabla 1.1
+
0
1
0
0
1
1
1
0
Tabla 1.2
×
0
1
0
0
0
1
0
1
Sec. 1.2
Matrices
17
AT =
⎡
⎣
4
0
−2
5
3
−2
⎤
⎦,
BT =
⎡
⎣
6
3
0
2
−1
4
−4
2
3
⎤
⎦,
CT =
5
−3
2
4
2
−3 ,
DT =
⎡
⎣
3
−5
1
⎤
⎦,
y
E T = 2
−1
3 .
*Un bit es un dígito binario (del inglés binary digit); esto es, un 0 o un 1.
■


## Página 42

DEFINICIÓN
Una matriz binaria† de m × n, es una matriz en que todas las entradas son bits. Esto
es, cada una de sus entradas es ya sea 0 o 1.
Un n-vector (o vector) binario es una matriz de 1 × n o de n × 1, todas cuyas en-
tradas son bits.
EJEMPLO 16
EJEMPLO 17
Las definiciones de suma de matrices y multiplicación por un escalar se aplican
también a las matrices binarias, siempre y cuando utilicemos aritmética binaria (de ba-
se 2) para todos los cálculos, y 0 y 1 como únicos escalares posibles.
EJEMPLO 18
Por medio de la definición de la suma de matri-
ces y con ayuda de la tabla 1.1, tenemos
Las combinaciones lineales de matrices binarias o n-vectores binarios son muy fá-
ciles de calcular con ayuda de las tablas 1.1 y 1.2, si se toma en cuenta el hecho de que
los únicos escalares son 0 y 1.
EJEMPLO 19
De acuerdo con la tabla 1.1, tenemos que 0 + 0 = 0 y 1 + 1 = 0. Por lo tanto, el
inverso aditivo de 0 es 0 (como es usual), y el inverso aditivo del 1 es 1. De aquí que,
para calcular la diferencia de matrices binarias A y B, procedemos como sigue:
Como podemos ver, la diferencia de matrices binarias no aporta nada nuevo a las rela-
ciones algebraicas entre matrices binarias.
A −B = A + (inverso de 1) B = A + 1B = A + B.
c1u1 + c2u2 + c3u3 = 1 1
0 + 0 0
1 + 1 1
1
=
1
0 + 0
0 + 1
1
=
(1 + 0) + 1
(0 + 0) + 1
=
1 + 1
0 + 1
=
0
1 .
Sean c1 = 1, c2 = 0, c3 = 1, u1 =
1
0 , u2 =
0
1
y u3 =
1
1 . Entonces
A + B =
⎡
⎣
1 + 1
0 + 1
1 + 0
1 + 1
0 + 1
1 + 0
⎤
⎦=
⎡
⎣
0
1
1
0
1
1
⎤
⎦.
Sean A =
⎡
⎣
1
0
1
1
0
1
⎤
⎦y B =
⎡
⎣
1
1
0
1
1
0
⎤
⎦.
v =
⎡
⎢⎢⎢⎣
1
1
0
0
1
⎤
⎥⎥⎥⎦es un 5-vector binario, y u = 0
0
0
0 es un 4-vector binario.
A =
⎡
⎣
1
0
0
1
1
1
0
1
0
⎤
⎦es una matriz binaria de 3 × 3.
18
Capítulo 1
Ecuaciones lineales y matrices
†Las matrices binarias también se llaman matrices booleanas.
■
■
■
■


## Página 43

Términos clave
Sec. 1.2
Matrices
19
Matriz
Filas (renglones)
Columnas
Tamaño de una matriz
Matriz cuadrada
Diagonal principal de una matriz
Elemento (o entrada) de una matriz
ij-ésimo elemento
entrada (i, j)
n-vector (o vector)
Matriz diagonal
Matriz escalar
0, vector cero
Rn, el conjunto de todos los n-vectores
Google©
Matrices iguales
Suma de matrices
Múltiplo escalar
Múltiplo escalar de una matriz
Diferencia de matrices
Combinación lineal de matrices
Transpuesta de una matriz
Bit
Matriz binaria (o booleana)
Matriz triangular superior
Matriz triangular inferior
1.2 Ejercicios
1. Sean
y
(a) ¿Cuáles son los valores de a12, a22, a23?
(b) ¿Cuáles son los valores de b11, b31?
(c) ¿Cuáles son los valores de c13, c31, c33?
2. Si
determine a, b, c y d.
3. Si
determine a, b, c y d.
En los ejercicios 4 a 7, sean
4. De ser posible, calcule la combinación lineal que se indica
en cada caso:
(a) C + E y E + C
(b) A + B
(c) D −F
(d) −3C + 5O
(e) 2C −3E
(f) 2B + F
5. De ser posible, calcule la combinación lineal que se indica
en cada caso:
(a) 3D + 2F
(b) 3(2A) y 6A
(c) 3A + 2A y 5A
(d) 2(D + F) y 2D + 2F
(e) (2 + 3)D y 2D + 3D
(f) 3(B + D)
6. De ser posible, calcule:
(a) AT y (AT)T
(b) (C + E)T y CT + ET
(c) (2D + 3F)T
(d) D −DT
(e) 2AT + B
(f) (3D – 2F)T
7. De ser posible, calcule:
(a) (2A)T
(b) (A – B)T
(c) (3BT – 2A)T
(d) (3AT – 5BT)T
(e) (−A)T y −(AT)
(f) (C + E + FT)T
8. ¿La matriz 
es una combinación lineal de las matri-
ces 
? Justifique su respuesta.
9. ¿La matriz 
es una combinación lineal de las 
matrices 
? Justifique su respuesta.
10. Sean
Si  es un número real, calcule  I3 −A.
A =
⎡
⎣
1
2
3
6
−2
3
5
2
4
⎤
⎦
y
I3 =
⎡
⎣
1
0
0
0
1
0
0
0
1
⎤
⎦.
1
0
0
1 y 1
0
0
0
4
1
0
−3
1
0
0
1 y 1
0
0
0
3
0
0
2
A =
2
−3
5
6
−5
4 ,
B =
⎡
⎣
4
−3
5
⎤
⎦,
C =
⎡
⎣
7
3
2
−4
3
5
6
1
−1
⎤
⎦.
a + b
c + d
c −d
a −b
=
4
6
10
2 ,
a + 2b
2a −b
2c + d
c −2d
=
4
−2
4
−3 ,
A =
1
2
3
2
1
4 ,
B =
⎡
⎣
1
0
2
1
3
2
⎤
⎦,
C =
⎡
⎣
3
−1
3
4
1
5
2
1
3
⎤
⎦,
D =
3
−2
2
4 ,
E =
⎡
⎣
2
−4
5
0
1
4
3
2
1
⎤
⎦,
F =
−4
5
2
3 ,
y 
O =
⎡
⎣
0
0
0
0
0
0
0
0
0
⎤
⎦.


## Página 44

Los ejercicios 11 a 15 tienen que ver con matrices binarias.
11. Sean 
Calcule cada una de las expresiones 
siguientes:
(a) A + B
(b) B + C
(c) A + B + C
(d) A + CT
(e) B −C.
12. Sean 
Calcule cada una de las expresiones siguientes:
(a) A + B
(b) C + D
(c) A + B + (C + D)T
(d) C −B
(e) A −B + C −D.
13. Sea 
14. Sea u = [1   1   0   0]. Determine el 4-vector v tal que 
u + v = [1   1   0   0].
15. Sea u = [0   1   0   1]. Determine el 4-vector v tal que 
u + v = [1   1   1   1].
A + B =
0
0
0
0 .
A + C =
1
1
1
1 .
(a)  Determine B de manera que    
(b)  Determine C de manera que    
A =
1
0
0
0 .
D =
0
0
1
0 .
A +
1
0
1
0 , B =
1
0
0
1 , C =
1
1
0
0 , y
C =
⎡
⎣
1
1
0
0
1
1
1
0
1
⎤
⎦.
A =
⎡
⎣
1
0
1
1
1
0
0
1
1
⎤
⎦, B =
⎡
⎣
0
1
1
1
0
1
1
1
0
⎤
⎦, y
20
Capítulo 1
Ecuaciones lineales y matrices
T.1. Demuestre que la suma y la diferencia de dos matrices
diagonales es una matriz diagonal.
T.2. Demuestre que la suma y la diferencia de dos matrices es-
calares es una matriz escalar.
T.3. Sea
(a) Calcule A – AT.
(b) Calcule A + AT.
(c) Calcule (A + AT)T.
T.4. Sea 0 la matriz de n × n tal que todas sus entradas son
cero. Demuestre que si k es un número real y A es una
matriz de n × n tal que kA = O, entonces k = 0 o A = O.
T.5. Una matriz A = [aij] se denomina triangular superior si
aij = 0 para i > j. Se llama triangular inferior si aij = 0
para i < j.
Matriz triangular superior
(Los elementos que están debajo de la diagonal 
principal son cero.)
Matriz triangular inferior
(Los elementos que están arriba de la diagonal principal son cero.)
(a) Demuestre que la suma y la diferencia de dos matri-
ces triangulares superiores es una matriz triangular
superior.
(b) Demuestre que la suma y la diferencia de dos matri-
ces triangulares inferiores es una matriz triangular in-
ferior.
(c) Demuestre que si una matriz es al mismo tiempo
triangular superior y triangular inferior, entonces es
una matriz diagonal.
T.6. (a) Demuestre que si A es una matriz triangular superior,
entonces AT es triangular inferior.
(b) Demuestre que si A es una matriz triangular inferior,
entonces AT es triangular superior.
T.7. Si A es una matriz de n × n, ¿cuáles son las entradas de
la diagonal principal de A −AT? Justifique su respuesta.
T.8. Si x es un n-vector, demuestre que x + 0 = x.
Los ejercicios T.9 a T.18 tienen que ver con matrices binarias.
T.9. Haga una lista de todos los posibles 2-vectores binarios.
¿Cuántos hay?
T.10. Haga una lista de todos los posibles 3-vectores binarios.
¿Cuántos hay?
T.11. Haga una lista de todos los posibles 4-vectores binarios.
¿Cuántos hay?
⎡
⎢⎢⎢⎢⎢⎢⎢⎢⎣
a11
0
0
· · ·
· · ·
0
a21
a22
0
· · ·
· · ·
0
a31
a32
a33
0
· · ·
0
...
...
...
...
...
...
...
...
...
0
an1
an2
an3
· · ·
· · ·
ann
⎤
⎥⎥⎥⎥⎥⎥⎥⎥⎦
⎡
⎢⎢⎢⎢⎢⎢⎢⎢⎣
a11
a12
· · ·
· · ·
· · ·
a1n
0
a22
· · ·
· · ·
· · ·
a2n
0
0
a33
· · ·
· · ·
a3n
...
...
...
...
...
...
...
...
...
...
0
0
0
· · ·
0
ann
⎤
⎥⎥⎥⎥⎥⎥⎥⎥⎦
A =
⎡
⎣
a
b
c
c
d
e
e
e
f
⎤
⎦.
Ejercicios teóricos


## Página 45

T.12. ¿Cuántos 5-vectores binarios hay? ¿Cuántos n-vectores
binarios existen?
T.13. Haga una lista de todas las posibles matrices binarias de 
2 × 2. ¿Cuántas hay?
T.14. ¿Cuántas matrices binarias de 3 × 3 hay?
T.15. ¿Cuántas matrices binarias de n × n existen?
T.16. Represente con 0 la palabra OFF y con 1 la palabra ON
(los términos de muchos aparatos electrónicos para “apa-
gado” y “encendido”, respectivamente), y sea
Determine la matriz B de ON/OFF tal que A + B sea una
matriz con cada entrada igual a OFF.
T.17. Represente con 0 la palabra OFF y con 1 la palabra ON, y
sea
Determine la matriz B de ON/OFF tal que A + B sea una
matriz con cada entrada igual a ON.
T.18. Un interruptor de luz normal tiene dos posiciones (o esta-
dos) encendido y apagado. Suponga que la matriz binaria
representa un conmutador de interruptores en donde 0 re-
presenta apagado y 1 representa encendido.
(a) Determine una matriz B tal que A + B represente el
conmutador de interruptores con el estado de cada in-
terruptor ”invertido”.
(b) Sea
¿La matriz B del inciso (a) también “invertirá” los es-
tados del conmutador de interruptores representado
por C? Verifique su respuesta.
(c) Si A es cualquier matriz binaria de m × n que repre-
senta un conmutador de interruptores, determine una
matriz binaria B de m × n tal que A + B “invierta”
todos los estados de los interruptores en A. Justifique
por qué B “invertirá” los estados de A.
C =
⎡
⎣
1
1
0
0
1
0
⎤
⎦.
A =
⎡
⎣
1
0
0
1
1
1
⎤
⎦
A =
⎡
⎣
ON
ON
OFF
OFF
ON
OFF
OFF
ON
ON
⎤
⎦.
A =
⎡
⎣
ON
ON
OFF
OFF
ON
OFF
OFF
ON
ON
⎤
⎦.
Sec. 1.3
Producto punto y multiplicación de matrices
21
Para utilizar MATLAB en esta sección, primero deberá leer las
secciones 12.1 y 12.2, las cuales proporcionan información básica
acerca del programa así como de las operaciones matriciales con
el mismo. Le pedimos que siga con cuidado los ejemplos o ilustra-
ciones de las instrucciones de MATLAB que aparecen en las 
secciones 12.1 y 12.2 antes de intentar realizar estos ejercicios.
ML.1. Introduzca las siguientes matrices en MATLAB.
Utilice los comandos apropiados de MATLAB para desple-
gar lo siguiente:
(a) a23, b23, b12.
(b) fila1(A), columna3(A), fila2(B).
(c) Escriba el comando format long de MATLAB y des-
pliegue la matriz B. Compare los elementos de B in-
dicados en el inciso (a) y los del despliegue actual.
Observe que el comando format short despliega los
valores redondeados a cuatro decimales. Restablezca
el formato a format short.
ML.2. Escriba el comando H = hilb(5) en MATLAB; (Observe
que el último carácter es un punto y coma, el cual sirve
para suprimir el despliegue del contenido de la matriz H;
vea la sección 12.1.). Para obtener más información acerca
del comando hilb, escriba help hilb. Utilice los coman-
dos apropiados de MATLAB para hacer lo siguiente:
(a) Determine el tamaño de H.
(b) Despliegue el contenido de H.
(c) Despliegue el contenido de H como números racio-
nales.
(d) Extraiga las tres primeras columnas como una matriz.
(e) Extraiga las dos últimas filas (renglones) como una
matriz.
Los ejercicios ML.3 a ML.5 emplean matrices binarias y los co-
mandos complementarios descritos en la sección 12.9.
ML.3. Utilice bingen para resolver los ejercicios T.10 y T.11.
ML.4. Utilice bingen para resolver el ejercicio T.13. (Sugeren-
cia: una matriz de n × n contiene el mismo número de
entradas que un n2-vector.)
ML.5. Resuelva el ejercicio 11 utilizando binadd.
A =
⎡
⎣
5
1
2
−3
0
1
2
4
1
⎤
⎦,
B =
⎡
⎣
4 ∗2
2/ 3
1/ 201
5 −8.2
0.00001
(9 + 4)/ 3
⎤
⎦.
1.3 PRODUCTO PUNTO Y MULTIPLICACIÓN DE MATRICES
En esta sección presentaremos la operación de multiplicación de matrices. A diferencia
de la suma, algunas de las propiedades de la multiplicación de matrices la distinguen de
la multiplicación de números reales.
Ejercicios con MATLAB


## Página 46

DEFINICIÓN
El producto punto o producto interior de los n-vectores a y b es la suma de los pro-
ductos de las entradas correspondientes. En consecuencia, si
entonces
(1)
De manera similar, si a o b (o ambas) son n-vectores escritos como una matriz de 1 × n,
el producto punto a · b está dado por (1). El producto punto de los vectores en Cn se
define en el apéndice A.2.
El producto punto es una operación importante que usaremos tanto en ésta como
en secciones posteriores.
EJEMPLO 1
El producto punto de
es
u · v = (1)(2) + (−2)(3) + (3)(−2) + (4)(1) = −6.
■
EJEMPLO 2
Sean a = [x
2
3] y 
Si a · b = −4, determine x.
Solución
Tenemos
a · b = 4x + 2 + 6 = −4
4x + 8 = −4
x = −3.
■
EJEMPLO 3
(Aplicación: cálculo de la calificación promedio de un curso) Suponga que un pro-
fesor utiliza cuatro notas para determinar la calificación promedio que obtiene un estu-
diante en un curso: cuestionarios, dos exámenes de una hora y un examen final. Cada
una de estas notas tiene una ponderación de 10, 30, 30 y 30%, respectivamente. Si las
calificaciones de un estudiante son, en cada rubro, 78, 84, 62 y 85, podemos calcular el
promedio del curso haciendo
y calculando
w · g = (0.10)(78) + (0.30)(84) + (0.30)(62) + (0.30)(85) = 77.1. 
Así, el promedio del curso del estudiante es 77.1.
■
w =
⎡
⎢⎣
0.10
0.30
0.30
0.30
⎤
⎥⎦
y
g =
⎡
⎢⎣
78
84
62
85
⎤
⎥⎦
b =
⎡
⎣
4
1
2
⎤
⎦.
u =
⎡
⎢⎣
1
−2
3
4
⎤
⎥⎦
y
v =
⎡
⎢⎣
2
3
−2
1
⎤
⎥⎦
a · b = a1b1 + a2b2 + · · · + anbn =
n
i=1
aibi.*
a =
⎡
⎢⎢⎣
a1
a2
...
an
⎤
⎥⎥⎦
y
b =
⎡
⎢⎢⎣
b1
b2
...
bn
⎤
⎥⎥⎦,
22
Capítulo 1
Ecuaciones lineales y matrices
*Tal vez ya esté familiarizado con esta útil notación, la notación de suma. De cualquier manera, la analizare-
mos con detalle al final de esta sección.


## Página 47

A
B
=
AB
m
n
p
p
iguales
m     n
MULTIPLICACIÓN DE MATRICES
DEFINICIÓN
Si A = [aij] es una matriz de m × p, y B = [bij] es una matriz de p × n, el producto de
A y B, que se denota mediante AB, es la matriz C = [cij] de m × n, definida como
(2)
La ecuación (2) dice que el i, j-ésimo elemento de la matriz producto es el produc-
to punto de la i-ésima fila, fili(A) y la j-ésima columna, colj(B) de B; esto se muestra
en la figura 1.4.
ci j = ai1b1 j + ai2b2 j + · · · + aipbpj
=
p
k=1
aikbkj
(1 ≤i ≤m, 1 ≤j ≤n).
Sec. 1.3
Producto punto y multiplicación de matrices
23
Observe que el producto de A y B sólo está definido cuando el número de filas de
B es exactamente igual al número de columnas de A, como se indica en la figura 1.5.
EJEMPLO 4
Sean
Entonces
AB =
(1)(−2) + (2)(4) + (−1)(2)
(1)(5) + (2)(−3) + (−1)(1)
(3)(−2) + (1)(4) + (4)(2)
(3)(5) + (1)(−3) + (4)(1)
=
4
−2
6
16 .
A =
1
2
−1
3
1
4
y
B =
⎡
⎣
−2
5
4
−3
2
1
⎤
⎦.
Figura 1.4 
colj(B)
b11
bp1
b21
...
b12
bp2
b22
...
b1j
bpj
b2j
...
b1n
bpn
b2n
...
. . .
. . .
. . .
. . .
. . .
. . .
fili(A)
a11
ai1
am1
a21
...
...
a12
ai2
am2
a22
...
...
a1p
aip
amp
a2p
...
...
. . .
. . .
. . .
. . .
c11
cm1
c21
...
c12
cm2
c22
...
c1n
cmn
c2n
...
cij
. . .
. . .
. . .
=
.
p

k = 1
  fili(A) . colj(B) =        aik bkj
■
Figura 1.5 
tamaño de AB


## Página 48

EJEMPLO 5
Sean
Calcule la entrada (3, 2) de AB.
Solución
Si AB = C, la entrada (3, 2) de AB es c32, que es fil3(A) · col2(B). Ahora tenemos
EJEMPLO 6
El sistema lineal
puede escribirse (verifíquelo) por medio del producto de matrices como
EJEMPLO 7
Sean
Si 
determine x y y.
Solución
Tenemos
Entonces
2 + 4x + 3y = 12
y = 6,
por lo que x = −2 y y = 6.
■
Las propiedades básicas de la multiplicación de matrices se estudiarán en la sec-
ción siguiente. Por lo pronto, diremos que la multiplicación de matrices requiere mu-
cho más cuidado que la suma, ya que las propiedades algebraicas de la multiplicación
de matrices difieren de las que satisfacen los números reales. Parte del problema se de-
be al hecho de que AB se define sólo cuando el número de columnas de A es igual al
número de filas de B. En consecuencia, si A es una matriz de m × p y B es una matriz
de p × n, AB es una matriz de m × n. ¿Qué ocurre con BA? Pueden suceder cuatro si-
tuaciones diferentes:
1. Es posible que BA no esté definido; esto pasará si n  m.
2. Si BA está definida, lo que significa que m = n, entonces BA es de p × p, mientras
que AB es de m × m; de esta manera, si m  p, AB y BA son de tamaños diferentes.
AB =
1
x
3
2
−1
1
⎡
⎣
2
4
y
⎤
⎦=
2 + 4x + 3y
4 −4 + y
=
12
6 .
AB =
12
6 ,
A =
1
x
3
2
−1
1
y
B =
⎡
⎣
2
4
y
⎤
⎦.
1
2
−1
3
0
4
⎡
⎣
x
y
z
⎤
⎦=
2
5 .
x + 2y −z = 2
3x
+ 4z = 5
fil3(A) · col2(B) = 0
1
−2 ·
⎡
⎣
4
−1
2
⎤
⎦= −5.
A =
⎡
⎣
1
−2
3
4
2
1
0
1
−2
⎤
⎦
y
B =
⎡
⎣
1
4
3
−1
−2
2
⎤
⎦.
24
Capítulo 1
Ecuaciones lineales y matrices
■
■


## Página 49

3. Si AB y BA son del mismo tamaño, pueden ser iguales.
4. Si AB y BA son del mismo tamaño, pueden ser diferentes.
EJEMPLO 8
Si A es una matriz de 2 × 3 y B es una matriz de 3 × 4, AB es una matriz de 2 × 4,
mientras que BA no está definida.
■
EJEMPLO 9
Sean A de 2 × 3 y B de 3 × 2. Entonces AB es de 2 × 2, mientras que BA es de 
3 × 3.
■
EJEMPLO 10
Sean
Entonces
En consecuencia, AB  BA.
■
Uno se preguntaría por qué la igualdad y la suma de matrices se definen de mane-
ra natural, mientras que la multiplicación de matrices parece mucho más complicada.
El ejemplo 11 nos proporciona una idea al respecto.
EJEMPLO 11
(Ecología) Una siembra se rocía con pesticidas para eliminar insectos dañinos; sin em-
bargo, las plantas absorben parte de las sustancias. Luego, los animales herbívoros de
la zona comen las plantas contaminadas y absorben los pesticidas. Para determinar la
cantidad de pesticida absorbida por uno de esos animales, procedemos de la manera si-
guiente. Suponga que tenemos tres pesticidas y cuatro plantas. Sea aij la cantidad de
pesticida i (en miligramos) absorbida por la planta j. Esta información puede represen-
tarse mediante la matriz
Imagine ahora, que tenemos tres animales herbívoros, y sea  bij la cantidad de plantas
del tipo i que uno de ellos, de tipo j, come mensualmente. La información puede repre-
sentarse mediante la matriz
La entrada (i, j) de AB proporciona la cantidad de pesticida del tipo i que ha absorbido
el animal j. En consecuencia, si i = 2 y j = 3, la entrada (2, 3) de AB es
3(8) + 2(15) + 2(10) + 5(20)
= 174 mg de pesticida, 2 absorbidos por el herbívoro 3.
Ahora bien, si tuviéramos p animales carnívoros (como el hombre) que se comen a los
herbívoros, podríamos repetir el análisis para determinar cuánto pesticida absorbe cada
uno.
■
B =
⎡
⎢⎣
Herbívoro 1
Herbívoro 2
Herbívoro 3
20
12
8
28
15
15
30
12
10
40
16
20
⎤
⎥⎦
Planta 1
Planta 2
Planta 3
Planta 4
A =
⎡
⎣
Planta 1 Planta 2 Planta 3 Planta 4
2
3
4
3
3
2
2
5
4
1
6
4
⎤
⎦
Pesticida 1
Pesticida 2
Pesticida 3
AB =
2
3
−2
2
mientras que B A =
1
7
−1
3 .
A =
1
2
−1
3
y
B =
2
1
0
1 .
Sec. 1.3
Producto punto y multiplicación de matrices
25


## Página 50

A veces es útil poder determinar una columna en el producto matricial AB sin te-
ner que multiplicar las dos matrices. Puede demostrarse (ejercicio T.9) que la j-ésima
columna del producto matricial AB es igual al producto matricial Acolj(B).
EJEMPLO 12
Sean
Entonces, la segunda columna de AB es
Observación
Si u y v son n-vectores, puede demostrarse (ejercicio T.14) que si los consideramos
como matrices de n × 1,
u · v = uT v.
Esta observación nos servirá en el capítulo 3. De manera similar, si u y v se consideran
matrices de 1 × n, entonces
u · v = uvT.
Por último, si u es una matriz de 1 × n y v es una matriz de n × 1, u · v = uv.
EJEMPLO 13
Sean 
Entonces
u · v = 1(2) + 2(−1) + (−3)(1) = −3.
Además,
EL PRODUCTO MATRIZ-VECTOR ESCRITO EN TÉRMINOS 
DE COLUMNAS
Sea
una matriz de m × n, y sea
c =
⎡
⎢⎢⎣
c1
c2
...
cn
⎤
⎥⎥⎦
A =
⎡
⎢⎢⎣
a11
a12
· · ·
a1n
a21
a22
· · ·
a2n
...
...
...
am1
am2
· · ·
amn
⎤
⎥⎥⎦
uT v = 1
2
−3
⎡
⎣
2
−1
1
⎤
⎦= 1(2) + 2(−1) + (−3)(1) + −3.
u =
⎡
⎣
1
2
−3
⎤
⎦y v =
⎡
⎣
2
−1
1
⎤
⎦.
Acol2(B) =
⎡
⎣
1
2
3
4
−1
5
⎤
⎦3
2
=
⎡
⎣
7
17
7
⎤
⎦.
A =
⎡
⎣
1
2
3
4
−1
5
⎤
⎦
y
B =
−2
3
4
3
2
1 .
26
Capítulo 1
Ecuaciones lineales y matrices
■
■


## Página 51

un n-vector, es decir una matriz de n × 1. Como A es de m × n y c es de n × 1, el pro-
ducto matricial Ac es la matriz de m × 1
El lado derecho de esta expresión puede escribirse como
= c1col1(A) + c2col2(A) + · · · + cncoln(A).
En consecuencia, el producto Ac de una matriz A de m × n y una matriz c de n × 1 pue-
de escribirse como una combinación lineal de las columnas de A, en las que los coefi-
cientes son las entradas en c.
EJEMPLO 14
Sean
Entonces, el producto Ac escrito como una comunicación lineal de las columnas de
A es
Si A es una matriz de m × p y B es una matriz de p × n, podemos concluir que la
j-ésima columna del producto AB se puede escribir como una combinación lineal de las
columnas de la matriz A, en la que los coeficientes son las entradas en la j-ésima co-
lumna de la matriz B:
colj(AB) = Acolj(B) = b1j col1(A) + b2jcol2(A) + · · · + bpjcolp(A).
EJEMPLO 15
Si A y B son las matrices definidas en el ejemplo 12, entonces
AB =
⎡
⎣
1
2
3
4
−1
5
⎤
⎦−2
3
4
3
2
1
=
⎡
⎣
4
7
6
6
17
16
17
7
1
⎤
⎦.
Ac =
2
−1
−3
4
2
−2
⎡
⎣
2
−3
4
⎤
⎦= 2 2
4 −3 −1
2 + 4 −3
−2
=
−5
−6 .
A =
2
−1
−3
4
2
−2
y
c =
⎡
⎣
2
−3
4
⎤
⎦.
c1
⎡
⎢⎢⎣
a11
a21
...
am1
⎤
⎥⎥⎦+ c2
⎡
⎢⎢⎣
a12
a22
...
am2
⎤
⎥⎥⎦+ · · · + cn
⎡
⎢⎢⎣
a1n
a2n
...
amn
⎤
⎥⎥⎦
Ac =
⎡
⎢⎢⎣
a11
a12
· · ·
a1n
a21
a22
· · ·
a2n
...
...
...
am1
am2
· · ·
amn
⎤
⎥⎥⎦
⎡
⎢⎢⎣
c1
c2
...
cn
⎤
⎥⎥⎦=
⎡
⎢⎢⎣
renglón1(A) · c
renglón2(A) · c
...
renglónm(A) · c
⎤
⎥⎥⎦
=
⎡
⎢⎢⎣
a11c1 + a12c2 + · · · + a1ncn
a21c1 + a22c2 + · · · + a2ncn
...
am1c1 + am2c2 + · · · + amncn
⎤
⎥⎥⎦.
Sec. 1.3
Producto punto y multiplicación de matrices
27
(3)
(4)
■


## Página 52

Las columnas de AB como combinaciones lineales de las columnas de A están dadas por
SISTEMAS LINEALES
A continuación generalizaremos el ejemplo 6. Consideremos el sistema lineal de m
ecuaciones en n incógnitas,
Ahora definamos las siguientes matrices:
Entonces
Las entradas en el producto Ax son sólo los lados izquierdos de las ecuaciones en
(5). Por lo tanto, el sistema lineal (5) puede escribirse en forma matricial como
Ax = b.
La matriz A es la matriz de coeficientes del sistema lineal (5), y la matriz
obtenida al agregar la columna b a A, se denomina matriz aumentada del sistema li-
neal (5). La matriz aumentada de (5) se escribe como 
Recíprocamente, cual-
quier matriz con más de una columna puede considerarse la matriz aumentada de un
sistema lineal. La matriz de coeficientes y la matriz aumentada tienen una función esen-
cial en nuestro método de solución de sistemas lineales.
A
b .
⎡
⎢⎢⎣
a11
a12
· · ·
a1n
b1
a21
a22
· · ·
a2n
b2
...
...
...
...
am1
am2
· · ·
amn
bm
⎤
⎥⎥⎦,
Ax =
⎡
⎢⎢⎣
a11
a12
· · ·
a1n
a21
a22
· · ·
a2n
...
...
...
am1
am2
· · ·
amn
⎤
⎥⎥⎦
⎡
⎢⎢⎣
x1
x2
...
xn
⎤
⎥⎥⎦=
⎡
⎢⎢⎣
a11x1 + a12x2 + · · · + a1nxn
a21x1 + a22x2 + · · · + a2nxn
...
...
...
am1x1 + am2x2 + · · · + amnxn
⎤
⎥⎥⎦.
A =
⎡
⎢⎢⎣
a11
a12
· · ·
a1n
a21
a22
· · ·
a2n
...
...
...
am1
am2
· · ·
amn
⎤
⎥⎥⎦,
x =
⎡
⎢⎢⎣
x1
x2
...
xn
⎤
⎥⎥⎦,
b =
⎡
⎢⎢⎣
b1
b2
...
bm
⎤
⎥⎥⎦.
a11x1 + a12x2 + · · · + a1nxn = b1
a21x1 + a22x2 + · · · + a2nxn = b2
...
...
...
...
am1x1 + am2x2 + · · · + amnxn = bm.
col1(AB) =
⎡
⎣
4
6
17
⎤
⎦= Acol1(B) = −2
⎡
⎣
1
3
−1
⎤
⎦+ 3
⎡
⎣
2
4
5
⎤
⎦
col2(AB) =
⎡
⎣
7
17
7
⎤
⎦= Acol2(B) = 3
⎡
⎣
1
3
−1
⎤
⎦+ 2
⎡
⎣
2
4
5
⎤
⎦
col3(AB) =
⎡
⎣
6
16
1
⎤
⎦= Acol3(B) = 4
⎡
⎣
1
3
−1
⎤
⎦+ 1
⎡
⎣
2
4
5
⎤
⎦.
28
Capítulo 1
Ecuaciones lineales y matrices
(5)
■


## Página 53

EJEMPLO 16
Considere el sistema lineal
Si hacemos
podemos escribir el sistema lineal dado en forma matricial, como
Ax = b.
La matriz de coeficientes es A y la matriz aumentada es
EJEMPLO 17
La matriz
es la matriz aumentada del sistema lineal
Con base en el análisis anterior, se desprende que el sistema lineal en (5) puede es-
cribirse como una combinación lineal de las columnas de A, como
Recíprocamente, una ecuación las de (6) siempre describe un sistema lineal como en (5).
PARTICIÓN DE MATRICES (OPCIONAL)
Si comenzamos con una matriz A = [aij] de m × n, y eliminamos algunas filas (renglo-
nes) o columnas (pero no todos), obtenemos una submatriz de A.
EJEMPLO 18
Sea
Si eliminamos la segunda fila y la tercera columna, obtenemos la submatriz
1
2
4
3
0
−3 .
A =
⎡
⎣
1
2
3
4
−2
4
−3
5
3
0
5
−3
⎤
⎦.
x1
⎡
⎢⎢⎣
a11
a21
...
am1
⎤
⎥⎥⎦= x2
⎡
⎢⎢⎣
a12
a22
...
am2
⎤
⎥⎥⎦+ · · · + xn
⎡
⎢⎢⎣
a1n
a2n
...
amn
⎤
⎥⎥⎦=
⎡
⎢⎢⎣
b1
b2
...
bm
⎤
⎥⎥⎦.
2x −y + 3z = 4
3x
+ 2z = 5.
,
2
−1
3
4
3
0
2
5
⎡
⎣
−2
0
1
5
2
3
−4
7
3
2
2
3
⎤
⎦.
A =
⎡
⎣
−2
0
1
2
3
−4
3
2
2
⎤
⎦,
x =
⎡
⎣
x
y
z
⎤
⎦
y
b =
⎡
⎣
5
7
3
⎤
⎦,
−2x
+ z = 5
2x + 3y −4z = 7
3x + 2y + 2z = 3.
Sec. 1.3
Producto punto y multiplicación de matrices
29
■
■
(6)
■


## Página 54

Para subdividir una matriz en submatrices, se pueden trazar rectas horizontales en-
tre las filas (renglones) y rectas verticales entre las columnas. Por supuesto, la partición
se puede realizar de muchas formas distintas.
EJEMPLO 19
La matriz
se puede separar como
También podríamos escribir
lo cual da otra partición de A. En consecuencia, podemos hablar de particiones de una
matriz.
■
EJEMPLO 20
La matriz aumentada de un sistema lineal es una matriz con una partición. Así, si Ax =
b, podemos escribir la matriz aumentada de este sistema como    
■
Si A y B son matrices de m × n que tienen una partición de la misma forma, A +
B se obtiene simplemente sumando las submatrices correspondientes de A y B. De ma-
nera análoga, si A es una matriz con una partición, el múltiplo escalar cA se obtiene for-
mando el múltiplo escalar de cada submatriz.
Si A se divide como en (7) y
entonces un cálculo directo nos muestra que
EJEMPLO 21
Sea
A =
⎡
⎢⎢⎢⎣
1
0
1
0
0
2
3
−1
2
0
−4
0
0
1
0
3
⎤
⎥⎥⎥⎦=
A11
A12
A21
A22
AB =
⎡
⎢⎣
(A11B11 + A12B21 + A13B31)
( A11B12 + A12B22 + A13B32)
(A21B11 + A22B21 + A23B31)
(A21B12 + A22B22 + A23B32)
⎤
⎥⎦.
B =
⎡
⎢⎢⎢⎢⎢⎢⎣
b11
b12
b13
b14
b21
b22
b23
b24
b31
b32
b33
b34
b41
b42
b43
b44
b51
b52
b53
b54
⎤
⎥⎥⎥⎥⎥⎥⎦
=
⎡
⎢⎣
B11
B12
B21
B22
B31
B32
⎤
⎥⎦,
A
b .
A =
⎡
⎢⎣
a11
a12
a13
a14
a15
a21
a22
a23
a24
a25
a31
a32
a33
a34
a35
a41
a42
a43
a44
a45
⎤
⎥⎦=
⎡
⎣A11
A12
A13
A21
A22
A23
⎤
⎦,
A =
A11
A12
A21
A22 .
A =
⎡
⎢⎣
a11
a12
a13
a14
a15
a21
a22
a23
a24
a25
a31
a32
a33
a34
a35
a41
a42
a43
a44
a45
⎤
⎥⎦
30
Capítulo 1
Ecuaciones lineales y matrices
(7)


## Página 55

y sea
Entonces
donde C11 debe ser A11B11 + A12B21. Verificamos como sigue que C11 es esta expre-
sión:
Este método de multiplicación de matrices con una partición también se conoce co-
mo multiplicación por bloques. Las matrices con partición son útiles al trabajar con
matrices que exceden la capacidad de memoria de una computadora. De esta manera,
al multiplicar dos matrices con partición se pueden conservar las matrices en un disco
y llevar a la memoria solamente las submatrices necesarias para formar sus productos.
Por supuesto, el resultado puede guardarse en el disco conforme se vaya calculando. La
partición de las matrices debe hacerse de modo que los productos de las matrices corres-
pondientes estén definidos. Gracias a la tecnología de cómputo actual, las computado-
ras con procesamiento paralelo utilizan las particiones para realizar más rápidamente
los cálculos con matrices.
La partición de una matriz implica una subdivisión de la información en bloques o
unidades. El proceso inverso consiste en considerar matrices individuales como bloques
y unirlas para formar una matriz por bloques. El único requisito es que, después de unir
los bloques, todas las filas y todas las columnas tengan el mismo número de entradas.
EJEMPLO 22
Sean
Entonces tenemos
y
D
C
CT
=
⎡
⎣
9
8
−4
1
6
7
5
−1
1
−1
0
0
⎤
⎦.
B
D =
2
9
8
−4
3
6
7
5 ,
D
C
=
⎡
⎣
9
8
−4
6
7
5
1
−1
0
⎤
⎦,
B =
2
3 ,
C = 1
−1
0
y
D =
9
8
−4
6
7
5 .
A11B11 + A12B21 =
1
0
0
2
2
0
0
0
1
1 + 1
0
3
−1
1
3
0
−3
−1
2
=
2
0
0
0
2
2 + 1
3
0
6
10
−2
=
3
3
0
6
12
0
= C11.
AB = C =
⎡
⎢⎢⎢⎣
3
3
0
1
2
−1
6
12
0
−3
7
5
0
−12
0
2
−2
−2
−9
−2
7
2
2
−1
⎤
⎥⎥⎥⎦=
C11
C12
C21
C22 ,
B =
⎡
⎢⎢⎢⎣
2
0
0
1
1
−1
0
1
1
−1
2
2
1
3
0
0
1
0
−3
−1
2
1
0
−1
⎤
⎥⎥⎥⎦=
B11
B12
B21
B22 .
Sec. 1.3
Producto punto y multiplicación de matrices
31
■
■


## Página 56

Una práctica común en muchas aplicaciones, consiste en hacer la unión de matri-
ces en bloques para extender las estructuras de información. Por ejemplo, suele conser-
varse la información de las ventas mensuales de cada año en una matriz de 1 × 12, y
luego unir tales matrices para construir la matriz de ventas históricas de varios años. De
manera similar, los resultados de nuevos experimentos de laboratorio se adjuntan a la
información existente para actualizar una base de datos en una investigación.
En el ejemplo 20 se dijo ya que la matriz aumentada del sistema lineal Ax = b es
una matriz por bloques. En ocasiones necesitaremos resolver varios sistemas lineales en
los que la matriz de coeficientes A es la misma, pero son diferentes los lados derechos
de los sistemas, digamos b, c y d. En estos casos, encontramos conveniente considerar
la matriz por bloques 
(Vea la sección 6.7.)
NOTACIÓN DE SUMA (OPCIONAL)
Habrá ocasiones en que será necesario emplear la notación de suma. Por ello, a conti-
nuación revisaremos esta útil y compacta notación que se utiliza ampliamente en mate-
máticas.
La expresión 
significa
a1 + a2 + · · · + an.
La letra i es el índice de la suma; se trata de una variable muda o arbitraria que puede
remplazarse por otra letra. Por lo tanto, podemos escribir
EJEMPLO 23
Si
a1 = 3,
a2 = 4,
a3 = 5
y
a4 = 8,
entonces
EJEMPLO 24
La expresión 
significa
r1a1 + r2a2 + · · · + rnan.
Es fácil demostrar (ejercicio T.11) que la notación de suma satisface las siguientes pro-
piedades:
EJEMPLO 25
Si
a =
⎡
⎢⎢⎣
a1
a2
...
an
⎤
⎥⎥⎦
y
b =
⎡
⎢⎢⎣
b1
b2
...
bn
⎤
⎥⎥⎦,
(i)
n
i=1
(ri + si)ai =
n
i=1
riai +
n
i=1
siai.
(ii)
n
i=1
c(riai) = c
n
i=1
riai
.
n
i=1
riai
           
4
i=1
ai = 3 + 4 + 5 + 8 = 20.
n
i=1
ai =
n
j=1
a j =
n
k=1
ak.
n
i=1
ai
A
b
c
d .
32
Capítulo 1
Ecuaciones lineales y matrices
■
■


## Página 57

el producto punto a · b se puede expresar mediante notación de suma como
EJEMPLO 26
En términos de la notación de suma, podemos escribir la ecuación (2), para el i,
j-ésimo elemento del producto de las matrices A y B, como
También es posible formar sumas dobles. Así, la expresión 
significa que
primero sumamos sobre i y luego sumamos la expresión resultante sobre j.
EJEMPLO 27
Si n = 2 y m = 3, tenemos
= lado derecho de (8).
■
Resulta fácil demostrar (ejercicio T.12) que, en general,
(9)
La ecuación (9) puede interpretarse como sigue. Sea A = [aij] la matriz de m × n.
Si sumamos las entradas de cada fila (renglón) de A y sumamos luego los números re-
sultantes, obtenemos el mismo resultado que si sumáramos las entradas de cada colum-
na de A y luego sumáramos los números resultantes.
EJEMPLOS CON MATRICES BINARIAS (OPCIONAL)
En el caso de las matrices binarias, el producto punto y el producto matricial se calcu-
lan de la manera usual, pero sin olvidar que debe usarse aritmética de base 2.
EJEMPLO 28
Sean 
vectores binarias. Entonces
a · b = (1)(1) + (0)(1) + (1)(0) = 1 + 0 + 0 = 1.
■
a =
⎡
⎣
1
0
1
⎤
⎦y b =
⎡
⎣
1
1
0
⎤
⎦
n
i=1
m
j=1
ai j =
m
j=1
n
i=1
ai j.
3
j=1
2
i=1
ai j =
3
j=1
(a1 j + a2 j)
= (a11 + a21) + (a12 + a22) + (a13 + a23)
2
i=1
3
j=1
ai j =
2
i=1
(ai1 + ai2 + ai3)
= (a11 + a12 + a13) + (a21 + a22 + a23)
m
j=1
n
i=1
ai j
ci j =
p
k=1
aikbkj
(1 ≤i ≤m, 1 ≤j ≤n).
a · b = a1b1 + a2b2 + · · · + anbn =
n
i=1
aibi.
Sec. 1.3
Producto punto y multiplicación de matrices
33
■
■
(8)


## Página 58

EJEMPLO 29
Sean 
matrices binarias. Entonces
EJEMPLO 30
Sean 
matrices binarias. Si 
, determine
x y y.
Solución
Tenemos
Entonces y + 1 + x = 1 y y + 1 = 1. Empleando la aritmética de base 2, resulta que
y = 0 y x = 0.
■
AB =
1
1
1
x
1
1
0
1
⎡
⎢⎣
y
0
1
1
⎤
⎥⎦=
y + 1 + x
y + 1
=
1
1 .
AB =
1
1
A =
1
1
1
x
1
1
0
1 y B =
⎡
⎢⎣
y
0
1
1
⎤
⎥⎦
AB =
(1)(0) + (1)(1)
(1)(1) + (1)(1)
(1)(0) + (1)(0)
(0)(0) + (1)(1)
(0)(1) + (1)(1)
(0)(0) + (1)(0)
=
1
0
0
1
1
0 .
A =
1
1
0
1 y B =
0
1
0
1
1
0
34
Capítulo 1
Ecuaciones lineales y matrices
Producto punto (producto interior)
Producto de matrices
Matriz de coeficientes
Matriz aumentada
Submatriz
Particiones de una matriz
Multiplicación por bloques
Notación de suma
Términos clave
1.3 Ejercicios
En los ejercicios 1 y 2, calcule a · b.
3. Sean a = [−3
2
x] y 
Si a · b = 17, deter- 
mine x.
4. Sea 
Calcule w · w.
5. Determine todos los valores de x tales que v · v = 1, donde
6. Sean 
Si 
de-
termine x y y.
AB =
6
8 ,
A =
1
2
x
3
−1
2 y B =
⎡
⎣
y
x
1
⎤
⎦.
v =
⎡
⎢⎢⎣
1
2
−1
2
x
⎤
⎥⎥⎦.
w =
sen θ
cos θ .
b =
⎡
⎣
−3
2
x
⎤
⎦.
(d) a = 1
0
0 , b =
⎡
⎣
1
0
0
⎤
⎦
1. (a) a = 1
2 , b =
4
−1
(b) a = −3
−2 , b =
1
−2
(c) a = 4
2
−1 , b =
⎡
⎣
1
3
6
⎤
⎦
(d) a = 1
1
0 , b =
⎡
⎣
1
0
1
⎤
⎦
2. (a) a = 2
−1 , b =
3
2
(b) a = 1
−1 , b =
1
1
(c) a = 1
2
3 , b =
⎡
⎣
−2
0
1
⎤
⎦
■


## Página 59

En los ejercicios 7 y 8, sean
7. De ser posible, calcule:
(a) AB
(b) BA
(c) CB + D
(d) AB + DF
(e) BA + FD
8. De ser posible, calcule:
(a) A(BD)
(b) (AB)D
(c) A(C + E)
(d) AC + AE
(e) (D + F)A
9. Sean 
Calcule las siguientes entradas de AB:
(a) La entrada (1, 2)
(b) La entrada (2, 3).
(c) La entrada (3, 1)
(d) La entrada (3, 3).
10. Si 
calcule DI2 e I2D.
11. Sean
Demuestre que AB  BA.
12. Si A es la matriz del ejemplo 4 y O es la matriz de 3 × 2
en la cual todas las entradas son cero, calcule AO.
En los ejercicios 13 y 14, sean
y
13. Utilice el método del ejemplo 12 para calcular las siguientes
columnas de AB.
(a) La primera columna
(b) La tercera columna.
14. Utilice el método del ejemplo 12 para calcular las siguientes
columnas de AB:
(a) La segunda columna 
(b) La cuarta columna.
15. Sean
Exprese Ac como una combinación lineal de las columnas
de A.
16. Sean
Exprese las columnas de AB como una combinación lineal
de las columnas de A.
17. Sean 
(a) Verifique que AB = 3a1 + 5a2 + 2a3, donde aj es
la j-ésima columna de A para j = 1, 2, 3.
(b) Verifique que 
18. Escriba la combinación lineal
como un producto de una matriz de 2 × 3 y un 3-vector.
19. Considere el siguiente sistema lineal
(a) Determine la matriz de coeficientes.
(b) Escriba el sistema lineal en forma matricial.
(c) Determine la matriz aumentada.
20. Escriba el sistema lineal con matriz aumentada
21. Escriba el sistema lineal con matriz aumentada
22. Considere el siguiente sistema lineal:
3x – y + 2z = 4
2x + y
= 2
y + 3z = 7
4x
−z = 4.
(a) Determine la matriz de coeficientes.
(b) Escriba el sistema lineal en forma matricial.
(c) Determina la matriz aumentada.
⎡
⎣
2
0
−4
3
0
1
2
5
1
3
4
−1
⎤
⎦.
⎡
⎢⎣
−2
−1
0
4
5
−3
2
7
8
3
1
0
0
2
4
3
0
1
3
6
⎤
⎥⎦.
2x +
w =
7
3x + 2y + 3z
= −2
2x + 3y −4z
=
3
x +
3z
=
5.
3 −2
3 + 4 2
5 + 2
3
−1
AB =
(fil
fil
1 (A)) B
(
2 (A)) B .
A =
2
−3
1
1
2
4 y B =
⎡
⎣
3
5
2
⎤
⎦.
A =
⎡
⎣
1
−2
−1
2
4
3
3
0
−2
⎤
⎦
y
B =
⎡
⎣
1
−1
3
2
2
4
⎤
⎦.
A =
⎡
⎣
2
−3
4
−1
2
3
5
−1
−2
⎤
⎦
y
c =
⎡
⎣
2
1
4
⎤
⎦.
B =
⎡
⎣
1
0
−1
2
3
3
−3
4
4
2
5
1
⎤
⎦.
A =
⎡
⎢⎣
1
−1
2
3
2
4
4
−2
3
2
1
5
⎤
⎥⎦
A =
1
2
3
2
y
B =
2
−1
−3
4 .
I2 =
1
0
0
1 y D =
2
3
−1
−2 ,
A =
⎡
⎣
2
3
−1
4
0
3
⎤
⎦y B =
3
−1
3
1
2
4 .
A =
1
2
−3
4
0
−2 ,
B =
⎡
⎣
3
1
2
4
−1
5
⎤
⎦,
C =
⎡
⎣
2
3
1
3
−4
5
1
−1
−2
⎤
⎦,
D =
2
3
−1
−2 ,
E =
⎡
⎣
1
0
−3
−2
1
5
3
4
2
⎤
⎦,
y 
F =
2
−3
4
1 .
Sec. 1.3
Producto punto y multiplicación de matrices
35


## Página 60

23. ¿Cuál es la relación entre los sistemas lineales cuyas matri-
ces aumentadas son las siguientes?
24. Escriba cada una de las siguientes matrices como un siste-
ma lineal en forma matricial.
25. Escriba cada uno de los siguientes sistemas lineales como
una combinación lineal de las columnas de la matriz de
coeficientes.
(a) 2x + 2y = 3
2x −2y = 5
(b) 2x −3y + 5z = −2
2x + 4y −2z = −3
26. Sean A una matriz de m × n y B una matriz de n × p. ¿Qué
podría decir acerca del producto matricial AB si:
(a) A tiene una columna que consta únicamente de ceros?
(b) B tiene una fila (renglón) que consta únicamente de ceros?
27. (a) Determine un valor de r tal que ABT = 0, donde:
A = [r
1
−2]
y
B = [1
3
−1].
(b) Mencione una forma alternativa de escribir este producto.
28. Determine un valor de r y un valor de s tales que ABT = 0,
donde
A = [1
r
1]
y
B = [−2
2
s].
29. Formule el método para sumar matrices que estén divididas
en bloques, y verifíquelo estableciendo dos particiones dis-
tintas de las matrices
y determinando su suma.
30. Sean A y B las siguientes matrices:
y
Determine AB mediante dos particiones distintas de A y B.
31. (Costos de producción) Un fabricante de muebles produce
sillas y mesas que deben pasar por un proceso de armado y
uno de acabado. Los tiempos necesarios para estos proce-
sos están dados (en horas) por la matriz
El fabricante tiene una planta en Salt Lake City y otra en
Chicago. Las tarifas por hora de cada proceso están dadas
(en dólares) por matriz
¿Qué interpretación puede dar el fabricante a las entradas
del producto de matrices AB?
32. (Ecología: contaminación) Un fabricante elabora los pro-
ductos P y Q en dos plantas, X y Y. Durante la fabricación
emiten los contaminantes bióxido de azufre, óxido nítrico y
partículas suspendidas. Las cantidades de cada contaminan-
te están dadas (en kilogramos) por la matriz
Los reglamentos estatales y federales exigen la eliminación
de estos contaminantes. El costo diario por deshacerse de
cada kilogramo de contaminante está dado (en dólares) por
la matriz
¿Qué interpretación puede dar el fabricante a las entradas
del producto de matrices AB?
33. (Medicina) Un proyecto de investigación nutricional tiene
como base de estudio a adultos y niños de ambos sexos. La
composición de los participantes está dada por la matriz
El número de gramos diarios de proteínas, grasa y carbo-
hidratos que consume cada niño y adulto está dado por la
matriz
B =
Proteínas    Grasa
Carbo-
hidratos
20
20
20
10
20
30
Adultos
Niños
A =
Adultos
Niños
80
120
100
200
Hombres
Mujeres
B =
⎡
⎣
Planta X
Planta Y
8
12
7
9
15
10
⎤
⎦
Bióxido de azufre
Óxido nítrico
Partículas suspendidas
A =
300
100
150
200
250
400
Producto P
Producto Q
Bióxido 
de azufre
Óxido
nítrico
Partículas 
suspendidas
B =
Salt Lake
City
Chicago
9
10
10
12
Proceso de armado
Proceso de acabado
A =
2
2
3
4
Silla
Mesa
 Proceso 
de armado
Proceso 
de acabado
B =
⎡
⎢⎢⎢⎣
1
2
3
4
1
2
1
3
2
−1
1
5
4
2
3
2
1
3
5
7
3
2
4
6
1
⎤
⎥⎥⎥⎦.
A =
⎡
⎢⎢⎢⎢⎢⎣
2
1
3
4
2
1
2
3
−1
4
2
3
2
1
4
5
−1
3
2
6
3
1
2
4
6
2
−1
3
5
7
⎤
⎥⎥⎥⎥⎥⎦
A =
⎡
⎣
1
3
−1
2
1
0
2
−3
1
⎤
⎦
y
B =
⎡
⎣
3
2
1
−2
3
1
4
1
5
⎤
⎦
(a) x
1
2 + y 2
5 + z 0
3
=
1
1
(b) x
⎡
⎣
1
1
2
⎤
⎦+ y
⎡
⎣
2
1
0
⎤
⎦+ z
⎡
⎣
1
2
2
⎤
⎦=
⎡
⎣
0
0
0
⎤
⎦
1
2
3
−1
2
3
6
2
y
⎡
⎣
1
2
3
−1
2
3
6
2
0
0
0
0
⎤
⎦
36
Capítulo 1
Ecuaciones lineales y matrices
