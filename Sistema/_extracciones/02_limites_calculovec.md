# Extracción: Bento de Jesus Caraça - Cálculo Vectorial
**Páginas:** 167-190
**Fuente:** Analisis\Bento_de_Jesus_Caraça_Cálculo_Vectorial_3.pdf
---


## Página 167

dad cuadrada del costado, determine la función de costo
donde r es el radio de la lata y h es su altura.
52. Una caja rectangular cerrada va a construirse con 500 cm2
de cartón. Exprese el volumen V como una función de la
longitud x y el ancho y.
53. Como se muestra en la FIGURA 13.1.23, una tapa cónica des-
cansa sobre la parte superior de un cilindro circular. Si la
altura de la tapa es dos tercios de la altura del cilindro,
exprese el volumen del sólido como una función de las
variables indicadas.
54. A menudo una muestra de tejido es un cilindro que se corta
oblicuamente, como se muestra en la FIGURA 13.1.24. Exprese
el espesor t del corte como una función de x, y y z.
55. En medicina a menudo se emplean fórmulas para el área
de la superficie (vea el ejemplo 3b) para calibrar dosis de
fármacos, puesto que se supone que la dosis del fármaco
D y el área de la superficie S son directamente proporcio-
nales. La siguiente función simple puede utilizarse para
obtener una estimación rápida del área superficial del
cuerpo de un humano: S  2ht, donde h es la altura (en
cm) y t es la máxima circunferencia de músculo (en cm).
Estime el área de la superficie de una persona de 156 cm
de altura con una circunferencia de músculo máxima de
50 cm. Estime su propia área superficial.
Proyectos
56. Factor de enfriamiento
Durante su investigación del
invierno de 1941 en el Antártico, el doctor Paul A. Siple
ideó el siguiente modelo matemático para definir el fac-
tor de enfriamiento del viento:
donde H se mide en kcal/m2h, y es la velocidad del viento
en m/s y T es la temperatura en grados Celsius. Un ejem-
plo de este índice es: 1 000  muy frío, 1 200  implaca-
blemente frío y 1 400  congelamiento de la carne
expuesta. Determine el factor de enfriamiento en -6.67 C
(20 F) con una velocidad de viento de 20 m/s (45 mi/h).
Escriba un breve informe que defina con precisión el fac-
tor de enfriamiento. Encuentre al menos otro modelo
matemático para el factor de enfriamiento del viento.
57. Flujo de agua
Cuando el agua fluye de un grifo, como
se muestra en la FIGURA 13.1.25a), se contrae a medida que se
acelera hacia abajo. Eso ocurre debido a que la tasa de flujo
Q, la cual se define como la velocidad por el área de la sec-
ción transversal de la columna de agua, debe ser constante
en cada nivel. En este problema suponga que las secciones
transversales de la columna de fluido son circulares.
a) Considere la columna de agua que se muestra en la
figura 13.1.25b). Suponga que v es la velocidad del
agua en el nivel superior, V es la velocidad del agua en
el nivel inferior a una distancia h unidades por debajo
del nivel superior, R es el radio de la sección transver-
sal en el nivel superior y r es el radio de la sección
transversal en el nivel inferior. Muestre que la tasa de
flujo Q como una función de r y R es
donde g es la aceleración de la gravedad. [Sugerencia:
Empiece expresando el tiempo t que tarda la sección
transversal del agua en caer una distancia h en térmi-
nos de u y V. Por conveniencia considere la dirección
positiva hacia abajo.]
b) Determine la tasa de flujo Q (en cm3/s) si g  980
cm/s2, h  10 cm, R  1 cm y r  0.2 cm.
a)
b)
h
r
V
y
R
FIGURA 13.1.25
El agua fluye por el grifo del problema 57
H(y, T)  A101y  y  10.5B(33  T),
FIGURA 13.1.24
Muestra de tejido del problema 54
x
y
t
z

h
r
FIGURA 13.1.23
Cilindro con tapa cónica del problema 53
C(r, h),
688
CAPÍTULO 13 Derivadas parciales
13.2 Límites y continuidad
Introducción
En el caso de funciones de una variable, en muchos casos es factible hacer un
juicio acerca de la existencia de 
f(x) a partir de la gráfica de 
También se aprove-
cha que 
f(x) existe si y sólo si 
f(x) y 
f(x) existe y son iguales al mismo número L,
en cuyo caso 
f(x)  L. En esta sección veremos que la situación es más difícil en la consi-
deración de límites de funciones de dos variables.
lím
xSa
lím
xSa
lím
xSa
lím
xSa
y  f (x).
lím
xSa
Q
pr2R212gh
2R4
r4 ,


## Página 168

Terminología
Antes de proceder con la discusión sobre límites es necesario introducir cier-
ta terminología relativa a conjuntos que se utilizará en este apartado, así como en las secciones
y capítulos que siguen. El conjunto en el espacio bidimensional
(1)
consiste en todos los puntos en el interior de, pero no en, un círculo con centro 
y radio
El conjunto (1) se denomina disco abierto. Por otro lado, el conjunto
(2)
es un disco cerrado. Un disco cerrado incluye todos los puntos en el interior de y en un círculo
con centro 
y radio 
Vea la FIGURA 13.2.1a). Si R es cierta región del plano xy, enton-
ces un punto 
se dice que será un punto interior de R si hay algún disco abierto centrado
en 
que contiene sólo puntos de R. En contraste, afirmamos que 
es un punto fronte-
ra de R si el interior de cualquier disco abierto centrado en 
contiene tanto puntos en R como
puntos en no R. La región R se dice que será abierta si contiene puntos no frontera y cerrada si
contiene todos sus puntos frontera. Vea la figura 13.2.1b). Se dice que una región R está acotada
si puede estar contenida en un rectángulo suficientemente grande en el plano. La figura 13.2.1c)
ilustra una región acotada; el primer cuadrante ilustrado en la figura 13.2.1d) es un ejemplo de
una región no acotada. Estos conceptos se llevan de manera natural al espacio tridimensional. Por
ejemplo, el análogo de un disco abierto es una bola abierta. Una bola abierta consiste en todos
los puntos en el interior, pero no en, una esfera con centro 
y radio 
(3)
Una región en el espacio tridimensional está acotada si puede estar contenida en una caja rectan-
gular suficientemente grande.
{(x, y, z) 0 (x  x0)2  (y  y0)2  (z  z0) 6 d2}.
d 7 0:
(x0, y0)
(a, b)
(a, b)
(a, b)
(a, b)
d 7 0.
(x0, y0)
{(x, y) 0 (x  x0)2  (y  y0)2  d2}
d 7 0.
(x0, y0)
{(x, y) 0 (x  x0)2  (y  y0)2 6 d2}
13.2 Límites y continuidad
689
FIGURA 13.2.1
Varias regiones en el espacio bidimensional
y
R
a) Disco abierto
(x0,  y0) 
d
x
b) Región cerrada
punto
frontera
punto
interior
R
y
x
c) Región acotada
x
R
y
d) Región no acotada
R
x
y
Límites de funciones de dos variables
Analizar un límite dibujando la gráfica de 
no es conveniente ni es una rutina posible para la mayor parte de las funciones de dos variables.
Por intuición sabemos que f tiene un límite en un punto 
si los valores de la función 
se acercan a un número L conforme 
se acerca a 
Escribimos 
como
o
f(x, y)  L.
Para tener un poco más de precisión, f tiene un límite L en el punto 
si los puntos en el espa-
cio 
pueden hacerse arbitrariamente cercanos a 
siempre que 
sea sufi-
cientemente cercano a 
La noción de 
“aproximándose” a un punto 
no es tan simple como para funcio-
nes de una variable donde 
significa que x puede acercarse a a sólo desde la izquierda y
desde la derecha. En el plano xy hay un número infinito de maneras de aproximarse al punto
Como se muestra en la FIGURA 13.2.2, para que 
f(x, y) exista, requerimos ahora
que f se aproxime al mismo número L a lo largo de cualquier trayectoria o curva posible que
pase por
Si se pone lo anterior de manera negativa:
•
Si f(x, y) no se aproxima al mismo número L por dos trayectorias diferentes
a (a, b), entonces
f(x, y) no existe.
(4)
En la discusión de 
f(x, y) que sigue se supondrá que la función f está definida en todo
punto 
en un disco abierto centrado en 
pero no necesariamente en el propio 
.
(a, b)
(a, b)
(x, y)
lím
(x, y)S(a, b)
lím
(x, y)S(a, b)
(a, b).
lím
(x, y)S(a, b)
(a, b).
x S a
(a, b)
(x, y)
(a, b).
(x, y)
(a, b, L)
(x, y, f (x, y))
(a, b)
lím
(x, y)S(a, b)
(x, y) S (a, b),
f (x, y) S L
(a, b).
(x, y)
f (x, y)
(a, b)
z  f (x, y)


## Página 169

EJEMPLO  1
Un límite que no existe
Demuestre que 
no existe.
Solución
La función
se define en todas partes excepto en
Como se ilustra en la figura 13.2.2a), dos maneras de aproximarse a
son a lo largo
del eje x
y a lo largo del eje y
En
se tiene
donde 
En vista de (4), concluimos que el límite no existe.
EJEMPLO  2
Un límite que no existe
Demuestre que 
no existe.
Solución
En este caso los límites a lo largo de los ejes x y y son los mismos:
Sin embargo, esto no significa que 
f(x, y) exista, ya que no se ha examinado toda tra-
yectoria a (0, 0). Como se ilustra en la figura 13.2.2b), ahora intentaremos cualquier recta que
pase por el origen dada por 
Puesto que
f(x, y) depende de la pendiente m de la recta sobre la cual se hace la apro-
ximación al origen, concluimos que el límite no existe. Por ejemplo, en
y en
tene-
mos, respectivamente,
Una gráfica generada por computadora de la superficie se presenta en la FIGURA 13.2.3. Si tiene en
mente que el origen está en el centro de la caja, debe tener claro por qué diferentes trayectorias
a 
producen diferentes valores del límite.
EJEMPLO  3
Un límite que no existe
Demuestre que 
no existe.
Solución
Sea 
Se le pide al lector demostrar que a lo largo del eje x, el
eje y, cualquier recta 
que pasa por 
y a lo largo de cualquier parábola
(0, 0),
y  mx, m  0
f (x, y)  x3y>(x6  y2).
lím
(x, y)S(0, 0)
 
x3y
x6
y2
(0, 0)
y  2x,
y  x
lím
(x, y)S(0, 0)
y  mx:
lím
(x, y)S(0, 0)
lím
(x, y)S(0, 0)
 
xy
x2
y2
x  0,
y  0
(x  0).
(y  0)
(0, 0)
(0, 0).
f (x, y)  (x2  3y2)>(x2  2y2)
lím
(x, y)S(0, 0)
 x2
3y2
x2
2y2
690
CAPÍTULO 13 Derivadas parciales
y
x
(a, b)
a) A lo largo de las rectas
 
horizontal y vertical
 
que pasan por (a, b)
b) A lo largo de
 
toda recta que
 
pasa por (a, b)
y
x
(a, b)
c)  A lo largo de toda curva
 
que pasa por (a, b)
y
x
(a, b)
FIGURA 13.2.2
Tres de muchas maneras de aproximar el punto (a, b)
FIGURA 13.2.3
Gráfica de la
función del ejemplo 2
lím
(0, y)S(0, 0) f (0, y)
lím
(0, y)S(0, 0)
 0
3y2
0
2y2
3
2
.
lím
(x, 0)S(0, 0) f (x, 0)
lím
(x, 0)S(0, 0)
 x2
0
x2
0
1
f (x, 2x)
2x2
x2
4x2  y  
lím
(x, y)S(0, 0) f (x, 2x)
lím
(x, y)S(0, 0)
 
2x2
x2
4x2
2
5
.
f (x, x)
x2
x2
x2  y    
lím
(x, y)S(0, 0) f (x, x)
lím
(x, y)S(0, 0)
 
x2
x2
x2
1
2
,
lím
(x, y)S(0, 0) f (x, y)
lím
(x, y)S(0, 0)
 
mx2
x2
m2x2
m
1
m2.
lím
(x, 0)S(0, 0) f (x, 0)
lím
(x, 0)S(0, 0)
 0
x2
0  y  
lím
(0, y)S(0, 0) f (0, y)
lím
(0, y)S(0, 0)
 0
y2
0.
1
1
0
0.5
z
1
1
y
x


## Página 170

que pasa por (0, 0), 
f(x, y) = 0. Si bien esto constituye verdaderamen-
te un número infinito de trayectorias al origen, el límite sigue sin existir, ya que 
Propiedades de límites
En los siguientes dos teoremas se mencionan las propiedades de
límites para funciones de dos variables. Estos teoremas son las contrapartes en dos variables
de los teoremas 2.2.1, 2.2.2 y 2.2.3.
y  x3:
lím
(x, y)S(0, 0)
y  ax2, a  0,
13.2 Límites y continuidad
691
EJEMPLO  4
Límite de una suma
Evalúe 
f(x + y2).
Solución
De ii) del teorema 13.2.1 advertimos primero que
x = 2
y
y = 3.
Entonces de las partes i) y ii) del teorema 13.2.2 sabemos que el límite de una suma es la suma de
los límites y el límite de un producto es el producto de los límites siempre que exista el límite:
Uso de coordenadas polares
En algunos casos las coordenadas polares pueden ser de utili-
dad en la evaluación de un límite de la forma 
f(x, y). Si x = r cos u, y = r sen u y r2 =
x2 + y2, entonces 
si y sólo si 
EJEMPLO  5
Uso de coordenadas polares
Evalúe 
Solución
Al sustituir x = r cos u, y = r sen u en la función, obtenemos
lím
(x, y)S(0, 0)
10xy2
x2
y2.
r S 0.
(x, y) S (0, 0)
lím
(x, y)S(0, 0)
lím
(x, y)S(2, 3)
lím
(x, y)S(2, 3)
lím
(x, y)S(2, 3)
Teorema 13.2.1
Tres límites fundamentales
i)
ii)
iii)
Teorema 13.2.2
Límite de una suma, producto, cociente
Suponga que 
es un punto en el plano xy y que 
f(x, y) y 
g(x, y) existe.
Si
f(x, y)  L1 y 
g(x, y)  L2, entonces
i)
ii)
iii)
lím
(x, y)S(a, b)
lím
(x, y)S(a, b)
lím
(x, y)S(a, b)
lím
(x, y)S(a, b)
(a, b)
lím
(x, y)S(0, 0) f(x, y)
lím
(x, y)S(0, 0) f(x, x3)
lím
(x, y)S(0, 0)
x6
x6
x6
lím
(x, y)S(0, 0)
x6
2x6
1
2
.
10xy2
x2
y2
10r3 cos u sen2 u
r2
10r cos u sen2 u.
c una constante
lím
(x, y)S(a, b)cf(x, y)
c lím
(x, y)S(a, b) f(x, y)
lím
(x, y)S(a, b)y
b
lím
(x, y)S(a, b)x
a
lím
(x, y)S(a, b)c
c,
y
y
lím
(x, y)S(a, b)
f(x, y)
g(x, y)
L1
L2, L2
0.
lím
(x, y)S(a, b) f(x, y)g(x, y)
L1L2,
lím
(x, y)S(a, b)[ f(x, y)
g(x, y)]
L1
L2,
2
3 . 3
11.
lím
(x, y)S(2, 3)x
Q
lím
(x, y)S(2, 3)yRQ
lím
(x, y)S(2, 3)yR
 
lím
(x, y)S(2, 3)(x
y2)
lím
(x, y)S(2, 3)x
lím
(x, y)S(2, 3)y2


## Página 171

Puesto que 
r cos u sen2 u = 0, concluimos que
En el ejemplo 8 examinaremos de nuevo el límite del ejemplo 5.
Continuidad
Una función 
es continua en 
si 
está definida,
f(x, y) existe y el límite es el mismo que el valor de la función 
esto es,
f(x, y) = f(a, b).
(5)
Si f no es continua en
se afirma que es discontinua. La gráfica de una función continua
es una superficie sin quiebres. De la gráfica de la función
en la FIGURA 13.2.4
vemos que f tiene una discontinuidad infinita en (0, 0), esto es,
como 
Una función
es continua sobre un región R del plano xy si f es continua en cualquier
punto en R. La suma y el producto de dos funciones continuas también son continuas. El
cociente de dos funciones continuas es continuo, excepto en el punto donde el denominador es
cero. Además, si g es una función de dos variables continuas en
y F es una función de una
variable continua en
entonces la composición
es continua en
EJEMPLO  6
Función discontinua en (0, 0)
La función 
es discontinua en (0, 0), ya que 
no está definida. Sin embargo,
como puede observarse en el siguiente ejemplo, f tiene una discontinuidad removible en (0, 0).
EJEMPLO  7
Función continua en (0, 0)
La función f definida por
es continua en (0, 0), ya que 
y
Por consiguiente, advertimos que 
f(x, y) = f(0, 0).
Con la ayuda de un SAC vemos en la FIGURA 13.2.5 dos perspectivas diferentes (ViewPoint en
Mathematica) de la superficie definida por 
Note en los incisos a) y b) de la figura
13.2.5 la orientación del eje x y del eje y.
a) Viendo hacia abajo sobre la superficie
x
z
y
1
1
2
2
2
1
1
2
2
0
b) Viendo ligeramente hacia abajo y hacia el eje x
z
2
2
2
1
x
1
y
1
2
12
FIGURA 13.2.5
Gráfica de la función del ejemplo 7
z  f (x, y).
lím
(x, y)S(0, 0)
f (0, 0)  0
f (x, y)  •
x4  y4
x2  y2,
0,
(x, y)  (0, 0)
(x, y)  (0, 0)
f (0, 0)
f (x, y)  x4  y4
x2  y2
(a, b).
f (x, y)  F(g(x, y))
g(a, b),
(a, b)
z  f (x, y)
(x, y) S (0, 0).
f (x, y) S q
f (x, y)  1>(9x2  y2)
(a, b),
lím
(x, y)S(a, b)
f (a, b);
lím
(x, y)S(a, b)
f (a, b)
(a, b)
z  f (x, y)
lím
rS0
692
CAPÍTULO 13 Derivadas parciales
FIGURA 13.2.4
Función con una
discontinuidad infinita en (0, 0)
z
x
y
z 
1
9x2  y2
lím
(x, y)S(0, 0)
 10xy2
x2
y2
0.
lím
(x, y)S(0, 0)
 x4
y4
x2
y2
lím
(x, y)S(0, 0)
(x2
y2)(x2
y2)
x2
y2
lím
(x, y)S(0, 0)(x2
y2)
02
02
0.


## Página 172

Funciones polinomiales y racionales
En la sección 13.1 vimos que una función polinomial
de dos variables consiste en la suma de potencias 
donde m y n son enteros no negativos, y
que el cociente de dos funciones polinomiales recibe el nombre de función racional. Las fun-
ciones polinomiales, como 
son continuas por todo el plano xy. Las funciones racio-
nales son continuas salvo en puntos donde el denominador es cero. Por ejemplo, la función racio-
nal 
es continua salvo en puntos sobre la recta 
En la FIGURA 13.2.6 se
han ilustrado las gráficas de tres funciones que son discontinuas en puntos sobre una curva. En
los incisos a) y c) de la figura 13.2.6, la función racional es discontinua en todos los puntos sobre
la curva obtenida igualando a 0 el denominador. En la figura 13.2.6b) la función logarítmica es
discontinua donde 
esto es, sobre el círculo 
Funciones de tres o más variables
Las nociones de límite y continuidad para funciones de
tres o más variables son extensiones naturales de las que acaban de considerarse. Por ejemplo,
una función de tres variables 
es continua en 
si
La función polinomial en tres variables 
es continua a través del espacio tridi-
mensional. La función racional
es continua salvo en el punto 
La función racional
es continua excepto en los puntos 
sobre el plano 
Definición formal de un límite
La discusión anterior conduce a la definición formal del lími-
te de una función
en un punto
Esta definición
es análoga a la definición
2.6.1.
E-D
(a, b).
z  f (x, y)
2x  5y  z  0.
(x, y, z)
f (x, y, z) 
x  3y
2x  5y  z
(0, 0, 1).
f (x, y, z) 
xy2
x2  y2  (z  1)2
f (x, y, z)  xy2z3
(a, b, c)
w  f (x, y, z)
FIGURA 13.2.6
Tres funciones discontinuas
z 
4
6  x2 y2
a) Discontinua en x2  y2  6
x
y
z
x
y
z
z = ln| x2  y2  4 |
b) Discontinua en x2  y2  4
c) Discontinua en y     x2
4
1
2
1
z
y
x
z 
4
4y  x2  2
x2  y2  4.
x2  y2  4  0,
y  x.
f (x, y)  xy>(y  x)
f (x, y)  xy,
xmyn,
13.2 Límites y continuidad
693
Definición 13.2.1
Definición de un límite
Suponga que una función f de dos variables se define en cualquier punto 
en un disco
abierto centrado en 
salvo posiblemente en 
Entonces
f(x, y)  L
significa que para toda 
existe un número  
tal que
d 7 0
e 7 0,
lím
(x, y)S(a, b)
(a, b).
(a, b),
(x, y)
lím
(x, y, z)S(a, b, c) f(x, y, z)
f(a, b, c).
0 f(x, y)
L 0 6 e  siempre que  0 6 2(x
a)2
(y
a)2 6 d.


## Página 173

Como se ilustra en la FIGURA 13.2.7, cuando f tiene un límite en
para un
sin que
importe cuán pequeño, es posible encontrar un disco abierto de radio
centrado en
de
modo que
para todo punto
dentro del disco. El disco
abierto con radio
y su centro
eliminado se definen mediante la desigualdad
Como se mencionó antes, los valores de f son cercanos a L siempre que 
sea cercano a 
El concepto de “suficientemente cercano” se define mediante el número 
EJEMPLO  8
Repaso del ejemplo 5
Demuestre que 
Solución
De la definición 13.2.1, si  
está dado, se desea determinar un número 
tal que
La última línea es lo mismo que
Como 
puede escribirse 
y
Así,
De modo que si se elige 
tenemos
Por la definición 13.2.1, esto demuestra
` 10xy2
x2  y2  0 `  102x2  y2  10 . e
10  e.
d  e>10,
10 0x 0 y2
x2  y2  10 0x 0 .
y2
x2  y2  10 0x 0  102x2  102x2  y2.
y2
x2  y2  1.
y2  x2  y2
x2  0,
d 7 0
e 7 0
lím
(x, y)S(0, 0)
 10xy
x2
y2
0.
2
d.
(a, b).
(x, y)
0 6 2(x  a)2  (y  a)2 6 d.
(a, b)
d 7 0
(x, y)  (a, b)
L  e 6 f (x, y) 6 L  e
(a, b)
d
e 7 0,
(a, b),
694
CAPÍTULO 13 Derivadas parciales
FIGURA 13.2.7
Cuando
es un disco abierto,
f (x, y) está en el intervalo
(L  e, L  e)
(x, y)  (a, b)
z
x
y
f (x, y)
z  f (x, y)
L  
L  
(x, y)
(a, b)
0   (x  a)2  (y  b)2   
L
Ejercicios 13.2
Las respuestas de los problemas impares seleccionados comienzan en la página RES-41.
Fundamentos
En los problemas 1-30, evalúe el límite dado, si existe.
10 0x 0 y2
x2
y2 6 e  siempre que  0 6 2x2
y2 6 d.
` 10xy2
x2
y2
0 ` 6 e  siempre que  0 6 2x2
y2 6 d.
lím
(x, y)S(0, 0)
 
xy2
x2
y2
0.
.2
.1
.4
.3
.6
.5
.8
.7
.0
1
.9
lím
(x, y)S(2, 3)
 
xy
x2
y2
lím
(x, y)S(1, 2)
 x3y2(x
y)3
lím
(x, y)S(0, 0)
 6xy2
x2
y4
lím
(x, y)S(0, 0)
 
x2y
x4
y2
lím
(x, y)S(0, 0)
 2x2
y
x2
2y2
lím
(x, y)S(1, 1)
 4
x2
y2
x2
y2
lím
(x, y)S(1, 2)
 4x2
y2
16x4
y4
lím
(x, y)S(0, 0)
 5x2
y2
x2
y2
lím
(x, y)S(2, 1)
 x2
y
x
y
lím
(x, y)S(5, 
1) (x2
y2)
.2
1
.1
1
.4
1
.3
1
.6
1
.5
1
.8
1
.7
1
19.
20.
lím
(x, y)S(0, 3)
 
xy
3y
x2
y2
6y
9
lím
(x, y)S(1, 1)
 
xy
x
y
1
x2
y2
2x
2y
2
lím
(x, y)S(1, 0)
 
x2y
x3
y3
lím
(x, y)S(4, 3)
 xy2ax
2y
x
y b
lím
(x, y)S(0, 0)
 
x2y2
x4
5y4
lím
(x, y)S(0, 0)
 x2
3y
1
x
5y
3
lím
(x, y)S(p, p>4) cos (3x
y)
lím
(x, y)S(2, 2)
 
xy
x3
y2
lím
(x, y)S(0, 0)
 sen  xy
x2
y2
lím
(x, y)S(0, 0)
 
exy
x
y
1


## Página 174

En los problemas 31-34, determine dónde es continua la fun-
ción indicada.
31.
32.
33.
34.
En los problemas 35 y 36, determine si la función indicada es
continua en los conjuntos dados en el plano xy.
35.
a)
b)
c)
36.
a)
b)
c)
37. Determine si la función f definida por
es continua en (0, 0).
38. Muestre que
es continua en cada variable por separado en (0, 0), esto
es, que f (x, 0) y f(0, y) son continuas en
y 
respectivamente. Demuestre, sin embargo, que f es no
continua en (0, 0).
Piense en ello
En los problemas 39 y 40, emplee la definición 13.2.1 para
demostrar el resultado indicado; esto es, encuentre d para un
e 7 0 arbitrario.
41. Determine si existen puntos en los cuales la función
es discontinua.
42. Utilice la definición 13.2.1 para demostrar que 
y  b.
lím
(x, y)S(a, b)
f (x, y)  •
x3  y3
x  y ,
3x2,
y  x
y  x
y  0,
x  0
f (x, y)  •
xy
2x2  2y2,
0,
(x, y)  (0, 0)
(x, y)  (0, 0)
f (x, y)  •
6x2
 y3
(x2  y2)2,
0,
(x, y)  (0, 0)
(x, y)  (0, 0)
(x  2)2  y2 6 1
0 x 0  0 y 0 6 1
y  3
f (x, y) 
xy
2x2  y2  25
y 7 x
x  0
x2  y2 6 1
f (x, y)  ex  y,
0,
x  2
x 6 2
f (x, y)  ln (4x2  9y2  36)
f (x, y)  tan  x
y
f (x, y)  y2e1>xy
f (x, y)  1x  cos 1x  y
13.3 Derivadas parciales
695
13.3 Derivadas parciales
Introducción
La derivada de una función de una variable
está dada por el límite de
un cociente de diferencia
Exactamente de la misma manera, podemos definir la derivada de primer orden de una función
de dos variables
con respecto a cada variable.
z  f (x, y)
y  f (x)
Definición 13.3.1
Derivadas parciales de primer orden
Si 
es una función de dos variables, entonces la derivada parcial con respecto a x
en un punto 
es
(1)
y la derivada parcial con respecto a y es
(2)
siempre que exista el límite.
(x, y)
z  f (x, y)
21.
22.
.4
2
.3
2
.6
2
.5
2
.8
2
.7
2
.0
3
.9
2
lím
(x, y)S(0, 0)
x3
y3
x2
y2
lím
(x, y)S(0, 0)
x3
x2
y2
lím
(x, y)S(0, 0)
x2
y2
2x2
y2
lím
(x, y)S(0, 0)
6xy
2x2
y2
lím
(x, y)S(0, 0)
sen(3x2
3y2)
x2
y2
lím
(x, y)S(0, 0)
(x2
y2)2
x2
y2
lím
(x, y)S(1, 2)
sen
1(x>y)
cos
1(x
y)
lím
(x, y)S(1, 1)ln(2x2
y2)
lím
(x, y)S(
2, 2)
y3
2x3
x
5xy2
lím
(x, y)S(0, 0)
x3y
xy3
3x2
3y2
x2
y2
.0
4
.9
3
lím
(x, y)S(0, 0)
x2y2
x2
y2
0
lím
(x, y)S(0, 0)
3x2y
2x2
2y2
0
dy
dx
lím
hS0
f(x
h)
f(x)
h
.
0z
0y
lím
hS0
f(x, y
h)
f(x, y)
h
0z
0x
lím
hS0
f(x
h, y)
f(x, y)
h


## Página 175

Cálculo de una derivada parcial
En (1) observe que la variable y no cambia en el proceso
del límite, en otras palabras, y se mantiene fija. De manera similar, en la definición del límite (2)
la variable x se mantiene fija. Las dos derivadas parciales de primer orden (1) y (2) representan
entonces las tasas de cambio de f con respecto a x y y. En un nivel práctico tenemos las siguien-
tes guías simples.
696
CAPÍTULO 13 Derivadas parciales
Guías para la diferenciación parcial
Por reglas de la diferenciación ordinaria se entienden las reglas formuladas en el capí-
tulo 3: reglas del múltiplo constante, suma, producto, cociente, potencia y de la cadena.
• Para calcular 0z0x, emplee las leyes de la diferenciación ordinaria mientras trata a y
como una constante.
• Para calcular 0z0y, emplee las leyes de la diferenciación ordinaria mientras trata a x
como una constante.
EJEMPLO  1
Derivadas parciales
Si 
encuentre
a)
y
b)
Solución
a)
Diferenciamos z con respecto a x mientras y se mantiene fija y se tratan a las constan-
tes de la manera usual:
b)
Ahora tratando a x como constante, obtenemos
Símbolos alternos
Las derivadas parciales 
y 
a menudo se representan por medio
de símbolos alternos. Si 
entonces
Símbolos como 
y 
se denominan operadores de diferenciación parcial y denotan la
operación de tomar una derivada parcial, en este caso con respecto a x y y. Por ejemplo,
y
El valor de una derivada parcial en un punto 
se escribe de diversas maneras. Por ejem-
plo, la derivada parcial de 
con respecto a x para 
se escribe como
(x0, y0)
z  f (x, y)
(x0, y0)
0
0y
 ex4y5  ex4y5 . 0
0y
 x4y5  ex4y5x4 . 0
0y
  y5  ex4y5x4(5y4)  5x4y4ex4y5.
0
0x
 (x2  y2)  0
0x
 x2  0
0x
  y2  2x  0  2x
0>0y
0>0x
z  f (x, y),
0z>0y
0z>0x
0z
0y.
0z
0x
z  4x3y2  4x2  y6  1,
0z
0y
4x3(2y)
0
6y5
0
8x3y
6y5.
T
T
x es constante
0z
0x
(12x2)y2
8x
0
0
12x2y2
8x.
T
T
y es constante
0z
0x
0f
0x
zx
fx  y  0z
0y
0f
0y
zy
fy.
0z
0x `
(x0, y0), 0z
0x `
x
x0, y
y0
, 0z
0x (x0, y0) o fx(x0, y0).


## Página 176

EJEMPLO  2
Empleo de la regla del producto
Si f(x, y)  x5y10 cos(xy2), encuentre fy.
Solución
Cuando x se mantiene fija, observe que
Por consiguiente, por las reglas del producto y de la cadena la derivada parcial de f con respec-
to a y es,
EJEMPLO  3
Una tasa de cambio
La función 
relaciona el área superficial (en pies cuadrados) del cuerpo de
una persona como una función del peso w (en libras) y la altura h (en pulgadas). Encuentre
cuando 
y h  72. Interprete.
Solución
La derivada parcial de S respecto a w,
evaluada en 
es
La derivada parcial 
es la tasa a la cual el área superficial de una persona de altura fija h,
como un adulto, cambia con respecto al peso w. Puesto que las unidades para la derivada son
pies2/libra y 
advertimos que el aumento de 1 lb, mientras que h está fija en 72,
produce un aumento en el área de la piel de aproximadamente 0.058 
pie2.
Interpretación geométrica
Como advertimos en la FIGURA 13.3.1a), cuando y es constante, diga-
mos y  b, la traza de la superficie 
en el plano y  b es la curva azul C. Si definimos
la pendiente de una secante a través de los puntos 
y 
como
f (a  h, b)  f (a, b)
(a  h)  a
 f (a  h, b)  f (a, b)
h
R(a  h, b, f (a  h, b))
P(a, b, f (a, b))
z  f (x, y)
1
17
0S>0w 7 0,
0S>0w
0S
0w `
(150, 72)  (0.1091)(0.425)(150)0.575(72)0.725  0.058.
(150, 72)
0S
0w  (0.1091)(0.425)w0.575h0.725,
w  150
0S>0w
S  0.1091w0.425h0.725
13.3 Derivadas parciales
697
z
x (a, b)
y
z
C
P
R
Q
h
x
plano
 yb
a)
(a, b, 0)
(ah, b, 0)
zf(x, y)
z
y
x
b)
(a, b, 0) (a, b  h, 0)
z  f (x, y)
z
y (a, b)
plano
 x  a
P
C
Q
R
h
FIGURA 13.3.1
Las derivadas parciales 
y 
son pendientes de la recta tangente a la curva C de inter-
sección de la superficie y el plano paralelo a los ejes x o y.
0z>0y
0z>0x
producto de dos
funciones de y
f (x, y)
x5y10 cos(xy2).
⎞
⎪⎬
⎪
⎠
 
2x6y11 sen (xy2)
10x5y9 cos (xy2).
 fy(x, y)
x5[y10(
sen (xy2)) . 2xy
10y9 . cos (xy2)]


## Página 177

tenemos
En otras palabras, es posible interpretar
como la pendiente de la recta tangente en el punto
P (para la cual el límite existe) sobre la curva C de intersección de la superficie 
y el
plano y = b. A su vez, una inspección de la figura 13.3.1b) revela que
es la pendiente de
la recta tangente en el punto P sobre la curva C de intersección entre la superficie
y
el plano x = a.
EJEMPLO  4
Pendientes de rectas tangentes
Para 
encuentre la pendiente de la recta tangente en 
en
a)
el plano x  2
y
b)
el plano y  1.
Solución
a)
Al especificar el plano x  2, se mantienen todos los valores de x constantes. Por con-
siguiente, calculamos la derivada parcial de z con respecto a y:
En 
la pendiente es
b)
En el plano y  1, y es constante y por ello encontramos la derivada parcial de z con
respecto a x:
En 
la pendiente es
Vea la FIGURA 13.3.2.
Si 
entonces los valores de las derivadas parciales 
y 
en un punto
también se denominan pendientes de la superficie en las direcciones x y y, res-
pectivamente.
Funciones de tres o más variables
Las tasas de cambio de una función de tres variables
en las direcciones x, y y z son las derivadas parciales 0w 0x, 0w 0y y 
res-
pectivamente. La derivada parcial de f respecto a z se define como
(3)
siempre que el límite exista. Para calcular, por ejemplo, 
se deriva con respecto a x de la
manera usual mientras se mantienen constantes tanto y como z. De esta manera se extiende
el proceso de diferenciación parcial a funciones de cualquier número de variables. Si
es una función de n variables, entonces la derivada parcial de f con respec-
to a la variable i-ésima, 
se define como
(4)
Para calcular
se deriva con respecto a xi mientras se mantienen fijas las n - 1 variables
restantes.
EJEMPLO  5
Empleo de la regla del cociente
Si 
encuentre 0w
0z .
w  x2  z2
y2  z2,
0u>0xi
i  1, 2, . . . , n,
u  f (x1, x2, . . . , xn)
0w>0x,
0w>0z,
>
>
w  f (x, y, z)
(a, b, f (a, b))
0z>0y
0z>0x
z  f (x, y),
0z
0x `
(2, 1)  4.
(2, 1, 4)
0z
0x  2x.
0z
0y `
(2, 1)  2.
(2, 1, 4)
0z
0y  2y.
(2, 1, 4)
z  9  x2  y2,
z  f (x, y)
0z>0y
z  f (x, y)
0z>0x
698
CAPÍTULO 13 Derivadas parciales
z
x
y
plano y 1
plano x 2
(2, 1, 0)
(2, 1, 4)
pendiente  2
pendiente  4
z  9  x2 y2
FIGURA 13.3.2
Pendientes de las
rectas tangentes del ejemplo 4
0z
0x `
(a, b)
lím
hS0
f(a
h, b)
f(a, b)
h
.
0w
0z
lím
hS0
f(x, y, z
h)
f(x, y, z)
h
,
0u
0xi
lím
hS0
f(x1, x2, . . . , xi
h, . . . xn)
f(x1, x2, . . . xn)
h
.


## Página 178

Solución
Se emplea la regla del cociente mientras se mantiene constante x y y:
EJEMPLO  6
Tres derivadas parciales
Si f (x, y, t) = e-3pt cos 4x sen 6y, entonces las derivadas parciales con respecto a x, y y t son, a
su vez,
y
Derivadas de orden superior y mixtas
Para una función de dos variables 
las deri-
vadas parciales 
y 
son ellas mismas funciones de x y y. En consecuencia, se pueden
calcular las derivadas parciales de segundo orden y de orden superior. De hecho, se encuen-
tra la derivada parcial de 
con respecto a y, y la derivada parcial de 
con respecto a x.
Los últimos tipos de derivadas parciales se denominan derivadas parciales mixtas. En resumen,
las segundas, terceras derivadas parciales y la derivada parcial mixta de 
están defini-
das por:
Derivadas parciales de segundo orden:
Derivadas parciales de tercer orden:
Derivadas parciales de segundo orden mixtas:
Observe en el resumen que hay cuatro derivadas parciales de segundo orden. ¿Cuántas deri-
vadas parciales de tercer orden de 
hay? Las derivadas parciales de orden superior para
y para funciones de tres o más variables se definen de manera similar.
Símbolos alternos
Las derivadas parciales de segundo y tercer orden también se denotan
mediante
etcétera. La notación de subíndice para las derivadas parciales de segundo
orden mixtas es
o 
.
Nota
El orden de los símbolos en los subíndices de las parciales mixtas es justamente lo opues-
to al orden de los símbolos cuando se usa la notación de operador de diferenciación parcial:
y
Igualdad de parciales mixtas
Aunque no se demostrará, el siguiente teorema enuncia que
bajo ciertas condiciones es irrelevante el orden en el cual se efectúa una derivada parcial de
segundo orden mixta; esto es, las derivadas parciales mixtas 
y 
son iguales.
fyx
fxy
 fyx  ( fy)x  0
0x
  a 0z
0yb 
02z
0x 0y
.
 fxy  (  fx)y  0
0y
  a 0z
0xb 
02z
0y 0x
fyx
fxy
fxx, fyy, fxxx,
z  f (x, y)
z  f (x, y)
z  f (x, y)
0z>0y
0z>0x
0z>0y
0z>0x
z  f (x, y),
0w
0z  ( y2  z2)(2z)  (x2  z2)2z
( y2  z2)2
 2z(x2  y2)
( y2  z2)2 .
13.3 Derivadas parciales
699
ft(x, y, t)
3pe
3pt cos 4x sen 6y.
fy(x, y, t)
6e
3pt cos 4x cos 6y,
fx(x, y, t)
4e
3pt sen 4x sen 6y,
diferenciar
primero con
respecto a x
c
diferenciar
primero con
respecto a y
c
02z
0x 0y
0
0x a 0z
0yb  
y  
02z
0y 0x
0
0y a 0z
0xb.
03z
0x3
0
0x a 02z
0x2b  y  03z
0y3
0
0y a 02z
0y2b
02z
0x2
0
0x a 0z
0xb  y  02z
0y2
0
0y a 0z
0yb


## Página 179

Vea el problema 68 en los ejercicios 13.3.
EJEMPLO  7
Derivadas parciales de segundo orden
Si 
encuentre
a)
b)
y
c)
Solución
De las primeras derivadas parciales
obtenemos:
a)
b)
c)
Debemos verificar que
Si f es una función de dos variables y tiene derivadas parciales de primer, segundo y tercer
orden continuas sobre algún disco abierto, entonces las derivadas mixtas de tercer orden son
iguales; esto es,
Se sostienen comentarios similares para funciones de tres o más variables. Por ejemplo, si f es
una función de tres variables x, y y z que posee derivadas parciales continuas de cualquier orden
en alguna bola abierta, entonces las derivadas parciales como
son iguales en
cada punto en la bola.
EJEMPLO  8
Derivadas parciales mixtas de tercer orden
Si 
determine 
Solución
es una derivada parcial mixta de tercer orden. Primero se encuentra la derivada
parcial con respecto a y mediante la regla de potencias para funciones:
La derivada parcial con respecto a z de la función en la última línea es entonces
  6y3z5(x2  y4  z6)3>2.
 fyz  ( fy)z  2y3Q1
2R(x2  y4  z6)3>2 . 6z5
fy  1
2
 (x2  y4  z6)1>2 4y3  2y3(x 2  y4  z6)1>2.
fyzz
fyzz.
f (x, y, z)  2x2  y4  z6,
fxyz  fzyx  fyxz
02z
0y 0x  0
0y
  a 0z
0xb  4xy.
02z
0x 0y
.
02z
0x2, 
03z
0x3
z  x2y2  y3  3x4  5,
700
CAPÍTULO 13 Derivadas parciales
Teorema 13.3.2
Igualdad de parciales mixtas
Sea f una función de dos variables. Si las derivadas parciales fx, fy, fxy y 
son continuas en
algún disco abierto, entonces
fxy = fyx
en cada punto sobre el disco.
fyx
fxyy
fyxy
fyyx  y  fyxx
fxyx
fxxy.
02z
0x 0y
0
0x a 0z
0yb
4xy.
02z
0y2
0
0y a 0z
0yb
2x2
6y  y  03z
0y3
0
0y a 02z
0y2b
6,
02z
0x2
0
0x a 0z
0xb
2y2
36x2  y  03z
0x3
0
0x a 02z
0x2b
72x,
0z
0x
2xy2
12x3  y  0z
0y
2x2y
3y2
02z
0y2, 03z
0y3


## Página 180

Por último, por la regla del producto,
Se sugiere que el lector calcule 
y 
y verifique sobre cualquier disco abierto que no conten-
ga al origen que 
Diferenciación parcial implícita
La diferenciación parcial implícita se llevó a cabo de la
misma manera que en la sección 3.6.
EJEMPLO  9
Derivada parcial implícita
Suponga que la ecuación 
define a z implícitamente como una función de x y y.
Encuentre 
y 
Solución
Al mantener y constante,
Por la regla de potencia para funciones junto con la regla del producto:
Después de que resolvamos la última ecuación para 
Al mantener ahora x constante,
Al resolver para 
se obtiene
0z
0x 
2xyz
2z  xy2.
0z>0y
0z
0x  2x  y2z
2z  xy2.
0z>0x:
2z 0z
0x  2x  y2 Qx 0z
0x  zR.
0z>0y.
0z>0x
z2  x2  xy2z
fyzz  fzzy  fzyz.
fzyz
fzzy
  y3z4(x2  y4  z6)5>2(24z6  30x2  30y4).
 fyzz  ( fyz)z  6y3z5
 Q3
2R (x2  y4  z6)5>2 . 6z5  30y3z4(x2  y4  z6)3>2
13.3 Derivadas parciales
701
Ejercicios 13.3
Las respuestas de los problemas impares seleccionados comienzan en la página RES-41.
Fundamentos
En los problemas 1-4, emplee la definición 13.3.1 para calcu-
lar 
y 
con respecto a la función dada.
1.
2.
3.
4.
En los problemas 5-24, encuentre las primeras derivadas par-
ciales de la función dada.
5.
6.
7.
8.
9.
10.
11.
12.
13. z = cos2 5x + sen2 5y
14.
15.
17.
18.
19.
20.
21.
22.
23.
24.
En los problemas 25-26, suponga que 
25. Determine la pendiente de la recta tangente en 
en el plano 
26. Encuentre la pendiente de la recta tangente en 
en el plano y  1.
(1, 1, 4)
x  1.
(1, 1, 4)
z  4x3y4.
G (p, q, r, s)  (p2q3)e2r4s5
f (u, y, x, t)  u2w2  uy3  yw cos(ut2)  (2x2t)4
w  xy ln xz
w  21x y  yey>z
h(r, s)  1r
s
 1s
r
g(u, y)  ln (4u2  5y3)
f (x, y) 
xy
(x2  y2)2
f (x, y)  3x  y
x  2y
f (x, y)  xex3y
z  ex2
 tan1
 y2
z  (x4  7y2  3y)6
z  (x3  y2)1
z  4x3  5x2  8x
z 
41x
3y2  1
z  tan (x3y2)
z  5x4y3  x2y6  6x5  4y
z  x3  6x2y3  5y2
z  x2  xy2  4y5
z 
x
x  y
z  3x2y  4xy2
z  xy
z  7x  8y2
0z>0y
0z>0x
0
0y z2
0
0y (x2
xy2z)  implica  2z 0z
0y
xQy2 0z
0y
2yzR.
0
0x z2
0
0x (x2
xy2z)  implica  
0
0xz2
0
0xx2
y2 0
0x xz.
.6
1
f(u, f)
f2sen u
f


## Página 181

En los problemas 27 y 28, suponga que 
27. Determine las ecuaciones paramétricas para la recta tan-
gente en 
en el plano x  -1.
28. Encuentre ecuaciones simétricas para la recta tangente en
en el plano y  4.
En los problemas 29 y 30, suponga que 
29. ¿A qué tasa está cambiando z con respecto a x en el plano
y  2 en el punto 
30. ¿A qué tasa está cambiando z con respecto a y en el plano
en el punto 
En los problemas 31-38, encuentre la derivada parcial indicada.
En los problemas 39 y 40, verifique que 
39.
40.
En los problemas 41 y 42, verifique que las derivadas parcia-
les indicadas son iguales.
41.
42.
En los problemas 43-46, suponga que la ecuación dada defi-
ne a z como una función de las dos variables restantes.
Emplee diferenciación implícita para encontrar las primeras
derivadas parciales.
43.
44.
45.
46.
47. El área A de un paralelogramo con base x y altura y sen u
es A = xy sen u. Encuentre todas las primeras derivadas
parciales.
48. El volumen del cono truncado que se muestra en la FIGU-
RA 13.3.3 es 
Determine todas las
primeras derivadas parciales.
Aplicaciones
En los problemas 49 y 50, verifique que la distribución de
temperatura indicada satisface la ecuación de Laplace en dos
dimensiones
(5)
Una solución 
de la ecuación de Laplace (5) puede
interpretarse como la distribución de temperatura indepen-
diente del tiempo a través de una delgada placa bidimensio-
nal. Vea la FIGURA 13.3.4.
En los problemas 51 y 52, verifique que la función dada satis-
face la ecuación de Laplace (5).
51.
52.
En los problemas 53 y 54 verifique que la función dada satis-
face la ecuación de Laplace en tres dimensiones
(6)
En los problemas 55 y 56, verifique que la función dada satis-
face la ecuación de onda unidimensional
(7)
La ecuación de onda (7) ocurre en problemas que implican
fenómenos vibratorios.
57. La concentración molecular 
de un líquido está
dada por 
Verifique que esta función
satisface la ecuación de difusión unidimensional
58. La presión P ejercida por un gas ideal encerrado está
dada por 
donde k es una constante. T es la
temperatura y V es el volumen. Encuentre:
a) la tasa de cambio de P con respecto a V,
b) la tasa de cambio de V con respecto a T y
c) la tasa de cambio de T con respecto a P.
P  k(T>V),
k
4 02C
0x2  0C
0t
.
C(x, t)  t1>2ex2>kt.
C(x, t)
a2
 02u
0x2  02u
0t2 .
02u
0x2  02u
0y2  02u
0z2  0.
u(x, y)  tan 1 y
x
u(x, y)  ln (x2  y2)
W
H
D
x
y
termómetro
temperatura como función
de la posición sobre la
placa caliente
(x, y)
FIGURA 13.3.4
Placa caliente de los problemas 49 y 50
u(x, y)
02u
0x2  02u
0y2  0.
h
r
R
r
FIGURA 13.3.3
Cono truncado del problema 48
V  1
3ph(r2  rR  R2).
sez  est  4s3t  z
z2  u2y3  uyz  0
z2  x2  y2z
x2  y2  z2  25
F(h, j, t)  (h3  j2  t)2; Fhjh, Fjhh, Fhhj
w  u3y4  4u2y2t3  y2t; wuyt, wtyu, wyut
z  tan 1(2xy)
z  x6  5x4y3  4xy2
02z
0x 0y 
02z
0y 0x
.
(12, 13, 2)?
x  12
(2, 2, 1)?
z  29  x2  y2.
(1, 4, 24)
(1, 4, 24)
f (x, y)  18xy
x  y
.
702
CAPÍTULO 13 Derivadas parciales
49.
50.
n y L constantes
u(x, y)
e
(npx>L) sen(npy>L),
u(x, y)
(cosh 2py
senh 2py)sen 2px
53.
54. u(x, y, z)
e2m2
n2x cos my sen nz
u(x, y, z)
1
2x2
y2
z2
55.
56. u(x, t)
cos(x
at)
sen(x
at)
u(x, t)
cos at sen x
.2
3
.1
3
.4
3
.3
3
.6
3
.5
3
.8
3
.7
3
H(s, t)
s
t
s
t; Htts
F(r, u)
er2 cos u; Frur
w
cos(u2y)
t3
; wyyt
w
u2y3t3; wtuy
f(p, q)
ln p
q
q2
; fqp
f(x, y)
5x2y2
2xy3; fxy
z
x4y
2; 03z
0y3
z
exy; 02z
0x2


## Página 182

59. El desplazamiento vertical de una larga cuerda fija en el
origen pero cayendo bajo su propio peso está dado por
Vea la FIGURA 13.3.5.
a) Determine 
Interprete para 
b) Determine 
Interprete para 
60. Para la función de área de la piel
que se discutió en el ejemplo 3 encuentre
en
Si una niña crece de 36 a 37 pulg, mien-
tras su peso se mantiene en 60 lb, ¿cuál es el aumento
aproximado en el área de la piel?
Piense en ello
61. Formule una definición de límite que sea análoga a la
definición 13.3.1 para las derivadas parciales de segundo
orden
a)
b)
c)
62. Encuentre una función 
tal que
63. ¿Es posible que una función 
con derivadas
parciales continuas en un conjunto abierto, se encuentra
de manera tal que
64. a) Suponga que la función 
tiene derivadas
parciales de tercer orden continuas. ¿Cuántas deriva-
das parciales de tercer orden diferentes hay?
b) Suponga que la función 
tiene derivadas
parciales continuas de n-ésimo orden. ¿Cuántas deri-
vadas parciales diferentes de n-ésimo orden hay?
65. a) Suponga que 
tiene la propiedad de que
y 
para todo 
¿Qué puede
usted afirmar acerca de la forma de f?
b) Suponga que 
tiene derivadas parciales de
segundo orden continuas y 
¿Qué
puede usted afirmar acerca de la forma f?
66. Algunas curvas de nivel de una función 
se
muestran en la FIGURA 13.3.6. Emplee estas curvas de nivel
para conjeturar respecto a los signos algebraicos de las
derivadas parciales 
y 
en el punto que se indi-
ca en rojo en la figura.
67. Un clásico matemático
Una función 
quizá
no sea continua en un punto aunque es posible que siga
teniendo derivadas parciales en ese punto. La función
no es continua en 
(Vea el problema 38 en los ejer-
cicios 13.2.) Emplee (1) y (2) de la definición 13.3.1 para
mostrar que
68. Un clásico matemático
Considere la función z = f(x, y)
definida por
a) Calcule 
b) Muestre que 02z
0y 0x `
(0, 0) 
02z
0x 0y `
(0, 0).
f (x, y)  •
xy(y2  x2)
x2  y2
,
0,
(x, y)  (0, 0)
(x, y)  (0, 0).
(0, 0).
f (x, y)  •
xy
2x2  2y2,
0,
(x, y)  (0, 0)
(x, y)  (0, 0)
z  f (x, y)
10
18
16
14
10
x
y
20
FIGURA 13.3.6
Curvas de nivel del problema 66
0z>0y
0z>0x
z  f (x, y)
02z>0x 0y  0.
z  f (x, y)
(x, y).
0z>0y  0
0z>0x  0
z  f (x, y)
z  f (x, y)
w  f (x, y, z)
z  f (x, y),
z  f (x, y)
02z
0x 0y
02z
0y2
02z
0x2
w  60, h  36.
0S>0h
S  0.1091w0.425h0.725
x
u
cuerda
at,    gt 2
1
2
FIGURA 13.3.5
Cuerda que cae del problema 59
x 7 at.
0u>0x.
x 7 at.
0u>0t.
u (x, t)  •
 g
2a2
 (2axt  x2),
1
2 gt2,
0  x  at
x 7 at.
13.4 Linealización y diferenciales
703
13.4 Linealización y diferenciales
Introducción
En la sección 4.9 se vio que una linealización
de una función de una sola
variable
en un número x0 está dada por
Esta ecuación
puede utilizarse para aproximar los valores de la función
en la vecindad de x0, esto es,
para valores de x cercanos a x0. De manera similar puede definirse una linealización
L(x)  f (x)
f (x)
L (x)  f (x0)  f ¿(x0)(x  x0).
y  f (x)
L (x)
0z
0x
x2
y2  y  0z
0y
x2
y2?
0z
0x
2xy3
2y
1
x  y  0z
0y
3x2y2
2x
1.
0z
0x `
(0, 0)
0 y 0z
0y `
(0, 0)
0.
0z
0x `
(0, y) y 0z
0y `
(x, 0).


## Página 183

de una función de dos variables en un punto 
En el caso de una función de una
sola variable se asumió que 
era diferenciable en x0, esto es,
(1)
existe. Recuerde también que si f es diferenciable en x0, también es continua en ese número. Al
repetir la suposición en (1), deseamos que 
sea diferenciable en un punto 
Aunque hemos considerado lo que significa que 
posea derivadas parciales en un
punto, aún no formulamos una definición de diferenciabilidad de una función de dos variables f
en un punto.
Incremento de la variable dependiente
La definición de diferenciabilidad de una función de
cualquier número de variables independientes no depende de la noción de un cociente de dife-
rencia como en (1), sino más bien de la noción de un incremento de la variable dependiente.
Recuerde que para una función de una variable 
el incremento en la variable dependien-
te está dado por
De manera análoga, para una función de dos variables 
definimos el incremento de
la variable dependiente z como
(2)
La FIGURA 13.4.1 muestra que 
produce la cantidad de cambio en la función cuando 
cam-
bia a 
EJEMPLO  1
Determinando 
Encuentre 
para la función polinomial 
¿Cuál es el cambio en la función de
(1, 1) a 
Solución
De (2),
(3)
Con x = 1, y = 1, ¢x = 0.2 y 
Una fórmula de incremento fundamental
Una breve reinspección del incremento 
en (3)
muestra que en los primeros dos términos los coeficientes de 
y 
son 
y 
res-
pectivamente. El importante teorema que sigue muestra que esto no es un accidente.
0z>0y,
0z>0x
¢y
¢x
¢z
¢z  (1)(0.2)  (1)(0.3)  (0.2)2  (0.2)(0.3)  0.6.
¢y  0.3,
  (2x  y)¢x  x¢y  (¢x)2  ¢x¢y.
 ¢z  [(x  ¢x)2  (x  ¢x)(y  ¢y)]  (x2  xy)
(1.2, 0.7)?
z  x2  xy.
¢z
¢z
(x  ¢x, y  ¢y).
(x, y)
¢z
z  f (x, y),
¢y  f (x  ¢x)  f (x).
y  f (x)
z  f (x, y)
(x0, y0).
z  f (x, y)
y  f (x)
(x0, y0).
L(x, y)
704
CAPÍTULO 13 Derivadas parciales
FIGURA 13.4.1
Incremento en z
ƒ(x x, yy)
(x x, y y)
 y
 x
 x
zƒ(x, y)
y
z
(x, y)
ƒ(x, y)
z
Teorema 13.4.1
Una fórmula del incremento
Considere que 
tiene derivadas parciales continuas 
y 
en una región
rectangular abierta que está definida por 
Si (x, y) es cualquier punto
en esta región, entonces existen e1 y e2, las cuales son funciones de 
y 
tales que
(4)
donde 
y 
cuando 
y ¢y S 0.
¢x S 0
e2 S 0
e1 S 0
¢y,
¢x
a 6 x 6 b, c 6 y 6 d.
fy(x, y)
fx(x, y)
z  f (x, y)
DEMOSTRACIÓN
Al sumar y restar 
en (2), tenemos,
Al aplicar el teorema del valor medio (teorema 4.4.2) a cada conjunto de corchetes, se llega a
(5)
¢z  fx(x0, y  ¢y)¢x  fy(x, y0)¢y,
f (x, y  ¢y)
f¿(x0)
lím
¢xS0
f(x0
¢x)
f(x0)
¢x
¢z
f(x
¢x, y
¢y)
f(x, y).
¢z
fx(x, y)¢x
fy(x, y)¢y
e1¢x
e2¢y,
¢z
[ f(x
¢x, y
¢y)
f(x, y
¢y)]
[ f(x, y
¢y)
f(x, y)].


## Página 184

donde, como se muestra en la FIGURA 13.4.2, 
y 
En este caso,
definimos
(6)
Cuando 
y 
entonces, como se ilustra en la figura, 
y 
Puesto
que 
y 
se suponen continuas en la región, tenemos
Al resolver (6) para 
y 
y sustituir en (5), obtenemos (4).
Diferenciabilidad: funciones de dos variables
Ahora podemos definir la diferenciabilidad
de una función 
en un punto.
z  f (x, y)
fy(x, y0)
fx(x0, y  ¢y)
fy
fx
P3 S P1.
P2 S P1
¢y S 0,
¢x S 0
y 6 y0 6 y  ¢y.
x 6 x0 6 x  ¢x
13.4 Linealización y diferenciales
705
FIGURA 13.4.2
Región rectan-
gular en el teorema 13.4.1
y
x
P3(x0, y y)
P1(x, y)
P2(x, y0)
x x
b
x0
x
a
c
y
y0
y y
d
Definición 13.4.1
Función diferenciable
Una función 
es diferenciable en 
si el incremento 
puede escribirse como
donde e1 y e2 S 0 cuando (¢x, ¢y) S (0, 0).
¢z  fx(x0, y0)¢x  fy(x0, y0)¢y  e1¢x  e2¢y,
¢z
(x0, y0)
z  f (x, y)
Teorema 13.4.2
Condición suficiente para la diferenciabilidad
Si las primeras derivadas parciales 
y 
son continuas en un punto en una región abierta R,
entonces 
es diferenciable sobre R.
z  f (x, y)
fy
fx
Teorema 13.4.3
Diferenciabilidad implica continuidad
Si 
es diferenciable en el punto 
entonces f es continua en (x0, y0).
(x0, y0),
z  f (x, y)
Si la función 
es diferenciable en cada punto en una región R del plano xy, enton-
ces se dice que f es diferenciable en R. Si f es diferenciable sobre la región consistente en el
plano xy completo, se afirma entonces que es diferenciable en todas partes.
Es interesante notar que las derivadas parciales 
y 
quizás existan en un punto 
e
incluso f no sea diferenciable en ese punto. Desde luego, si 
y 
no existen en un punto 
entonces f no es diferenciable en ese punto. El siguiente teorema proporciona una condición sufi-
ciente bajo la cual la existencia de las derivadas parciales implica diferenciabilidad.
(x0, y0),
fy
fx
(x0, y0)
fy
fx
z  f (x, y)
DEMOSTRACIÓN
Suponga que f es diferenciable en un punto 
y que
Utilizando esta expresión en (4), obtenemos
Cuando 
, se deduce de la última línea que
Si se considera 
entonces el último resultado es equivalente a
f(x, y)  f(x0, y0).
Por (5) de la sección 13.2, f es continua en (x0, y0).
lím
(x, y)S(x0, y0)
x  x0  ¢x, y  y0  ¢y,
(¢x, ¢y) S (0, 0)
f (x0  ¢x, y0  ¢y)  f (x0, y0)  fx(x0, y0)¢x  fy(x0, y0)¢y  e1¢x  e2¢y.
¢z  f (x0  ¢x, y0  ¢y)  f (x0, y0).
(x0, y0)
El siguiente teorema es el análogo del teorema 3.1.1; establece que si 
es diferen-
ciable en un punto, entonces es continua en el punto.
z  f (x, y)
lím
(¢x, ¢y)S(0, 0)e1
0  y  
lím
(¢x, ¢y)S(0, 0)e2
0.
e1
fx(x0, y
¢y)
fx(x, y)  y  e2
fy(x, y0)
fy(x, y).
lím
(¢x, ¢y)S(0, 0) [f(x0
¢x, y0
¢y)
f(x0, y0)]
0 o 
lím
(¢x, ¢y)S(0, 0) f(x0
¢x, y0
¢y)
f(x0, y0).


## Página 185

EJEMPLO  2
Diferenciabilidad
Si (3) del ejemplo 1 se escribe como
podemos identificar 
= ¢x y 
= -¢x. Puesto que 
y 
cuando 
S
la función
es diferenciable en todo punto en el plano xy.
Como se advirtió en el ejemplo 2, la función dada es un polinomio. Cualquier función poli-
nomial de dos o más variables es diferenciable en todas partes.
Linealización
Si 
es diferenciable en 
y 
es un punto muy cercano a
se deduce de la definición 13.4.1 que ¢x = x - x0 y ¢y = y - y0 son ambas cercanas
a cero, e igualmente lo son 
y 
En vista de (4) esto significa que
Empleando 
la última línea es lo mismo que
Esto nos lleva a definir la linealización de f en 
de la siguiente manera.
(x0, y0)
f (x, y)  f (x0, y0)  fx(x0, y0)¢x  fy(x0, y0)¢y.
x  x0  ¢x, y  y0  ¢y
f (x0  ¢x, y0  ¢y)  f (x0, y0)  fx(x0, y0)¢x  fy(x0, y0)¢y.
e2¢y.
e1¢x
(x0, y0),
(x, y)
(x0, y0)
z  f (x, y)
z  x2  xy
(0, 0),
(¢x, ¢y)
e2 S 0
e1 S 0
e2
e1
706
CAPÍTULO 13 Derivadas parciales
Definición 13.4.2
Linealización
Si una función 
es diferenciable en un punto 
entonces la función
(7)
se dice que es una linealización de f en
Para un punto
cercano a
la apro-
ximación
(8)
se denomina una aproximación lineal local de f en (x0, y0).
(x0, y0),
(x, y)
(x0, y0).
(x0, y0),
z  f (x, y)
EJEMPLO  3
Linealización
Encuentre una linealización de 
en 
Solución
Las primeras derivadas parciales de f son
Utilizando los valores 
fx(4, 3) =
y 
se deduce de (7) que una linealiza-
ción de f en (4, 3) es
(9)
La última ecuación es equivalente a 
pero con fines de cálculo (9) es más con-
veniente.
EJEMPLO  4
Aproximación lineal local
Utilice la aproximación lineal local para aproximar 
Solución
Primero observe que se está pidiendo una aproximación del valor de la función
donde 
Debido a que el punto 
es razonablemente
cercano al punto (4, 3) es factible utilizar la linealización en (9) para formar una aproximación
lineal local 
De
L(4.01, 2.98)  5  4
5
 (4.01  4)  3
5
 (2.98  3)  4.996
f (x, y)  L(x, y).
(4.01, 2.98)
f (x, y)  2x2  y2.
f (4.01, 2.98),
2(4.01)2  (2.98)2.
L(x, y)  4
5 x  3
5 y
L(x, y)  5  4
5
 (x  4)  3
5
 (y  3).
fy(4, 3)  3
5,
4
5
f (4, 3)  5,
(4, 3).
f (x, y)  2x2  y2
¢z
(2x
y)¢x
(
x)¢y
(¢x)(¢x)
(
¢x)¢y,
e2
e1
f y
fx
r
r
r
s
f(x, y)
L(x, y)
L(x, y)
f(x0, y0)
fx(x0, y0)(x
x0)
fy(x0, y0)(y
y0)
fx(x, y)
x
2x2
y2  y  fy(x, y)
y
2x2
y2.


## Página 186

se sigue que la aproximación deseada es
o
Suponga que se deja 
y se reescribe (7) como
(10)
Al relacionar (10) término a término con (2) de la sección 11.6 se demuestra que una linealiza-
ción de una función 
en 
es una ecuación de un plano.
Plano tangente
En la sección 4.9 vimos que la linealización 
de
una función f de una sola variable en un número x0 no es más que una ecuación de la recta tan-
gente a la gráfica de 
en 
En tres dimensiones el análogo de una recta tangen-
te a una curva es un plano tangente a una superficie. Veremos en la sección 13.7 que la fórmula
de linealización 
en (7) es una ecuación del plano tangente a la gráfica de 
en el punto 
Diferenciales
Recuerde también que para una función f de una sola variable independiente
hay dos diferenciales 
y 
La diferencial dx es simplemente el cambio en la
variable independiente x. La diferencial dy es el cambio en la linealización 
en el número x0
tenemos
En el caso de una función f de dos variables tenemos naturalmente tres diferenciales. Los cam-
bios en las variables independientes x y y son dx y 
los cambios en la linealización 
se
denotan por medio de dz. En el punto 
el cambio en la linealización es
(11)
Empleando el resultado en (11) definimos a continuación la diferencial dz de una función f en
un punto arbitrario en el plano xy. Si 
denota el punto, entonces un punto cercano es
o 
La diferencial dz se llama comúnmente diferencial total
de la función.
(x  dx, y  dy).
(x  ¢x, y  ¢y)
(x, y)
  fx(x0, y0)¢x  fy(x0, y0)¢y.
  f (x0, y0)  fx(x0, y0)(x0  ¢x  x0)  fy(x0, y0)(y0  ¢y  y0)  f (x0, y0)
 ¢L  L(x0  ¢x, y0  ¢y)  L(x0, y0)
(x0, y0)
L(x, y)
dy;
  f ¿(x0) dx  dy.
  [ f (x0)  f ¿(x0)¢x]  [ f (x0)  f ¿(x0) . 0]
 ¢L  L(x0  ¢x)  L(x0)
L(x);
dy  f ¿(x) dx.
¢x  dx
(x0, y0, f (x0, y0)).
z  f (x, y)
z  L(x, y)
(x0, f (x0)).
y  f (x)
L(x)  f (x0)  f ¿(x0)(x  x0)
(x0, y0)
z  f (x, y)
fx(x0, y0)(x  x0)  fy(x0, y0)(y  y0)  (z  f (x0, y0))  0.
z  L(x, y)
2(4.01)2  (2.98)2  4.996.
f (4.01, 2.98)  L(4.01, 2.98)
13.4 Linealización y diferenciales
707
Definición 13.4.3
Diferenciales
Sea 
una función para la cual las primeras derivadas parciales fx y fy existen.
Entonces las diferenciales de x y y son 
y 
La diferencial de z,
(12)
también se denomina diferencial total de z.
dy  ¢y.
dx  ¢x
z  f (x, y)
EJEMPLO  5
Diferencial total
Si 
entonces
De (12) la diferencial total de la función es
dz  (2x  y) dx  x dy.
z  x2  xy,
dz
fx(x, y) dx
fy(x, y)dy
0z
0x dx
0z
0y dy,
0z
0x
2x
y y
0z
0y
x.


## Página 187

Concluimos de inmediato de (4) del teorema 13.4.1 que cuando y son continuas y cuan-
do 
y 
son cercanas a 0, entonces dz es una aproximación de 
esto es
(13)
La FIGURA 13.4.3 es una versión tridimensional de la figura 4.9.4. Los puntos en azul son los mis-
mos puntos que se muestran en la figura 13.4.1 y están sobre la superficie. El plano es tangente a
la superficie en 
y el punto marcado en café es un punto sobre el plano tangente.
EJEMPLO  6
Comparación de 
y dz
En el ejemplo 1 vimos que la función 
cambió en la cantidad exacta 
cuando hubo un desplazamiento del punto (1, 1) a (1.2, 0.7). Con las identificaciones x = 1,
y = 1, dx = 0.2 y 
se observa de (12) y (13) y el resultado del ejemplo 5 que el cam-
bio 
de la función puede aproximarse por medio de los cambios en la linealización:
EJEMPLO  7
Una aproximación de un error
El sistema cardiovascular humano es similar a circuitos eléctricos en serie y en paralelo. Por
ejemplo, cuando la sangre circula a través de dos resistencias en paralelo, como se muestra en la
FIGURA 13.4.4, entonces la resistencia equivalente R de la red es
Si los errores porcentuales en la medición de 
y 
son 
y 
respectivamente,
encuentre el error porcentual máximo aproximado en R.
Solución
Tenemos que  ¢R1 = 0.002R1 y  ¢R2 = 0.006R2. En este caso,
y por ello
Entonces el error relativo máximo está dado por la aproximación 
por tanto, el
error porcentual máximo es aproximadamente 0.6%.
Funciones de tres variables
Las definiciones 13.4.1, 13.4.2 y 13.4.3, así como los teoremas
13.4.1, 13.4.2 y 13.4.3, se generalizan de la manera esperada a funciones de tres o más variables.
A continuación se mencionan algunos puntos importantes. Si 
entonces el incre-
mento
está dado por
(14)
En este caso f es diferenciable en un punto 
si 
puede escribirse
(15)
donde e1, e2 y 
cuando ¢x, ¢y y ¢z S 0. Si f es diferenciable en 
entonces la
linealización de f se define como
(16)
(x0, y0, z0),
e3 S 0
¢w
(x0, y0, z0)
¢w
w  f (x, y, z),
dR>R  0.006;
  R c 0.006R2
R1  R2  0.006R1
R1  R2 d  (0.006)R.
  R c 0.002R2
R1  R2  0.006R1
R1  R2 d
 ¢R  dR  `
R2
2
(R1  R2)2
 (0.002R1) `  `
R2
1
(R1  R2)2
 (0.006R2) `
dR 
R2
2
(R1  R2)2
  dR1 
R2
1
(R1  R2)2
  dR2,
0.6%,
0.2%
R2
R1
dz  (1)(0.2)  (1)(0.3)  0.5.
¢z
dy  0.3,
¢z  0.6
z  x2  xy
¢z
(x0, y0, f (x0, y0))
¢z,
¢y
¢x
fy
fx
708
CAPÍTULO 13 Derivadas parciales
FIGURA 13.4.3
Interpretaciones
geométricas de dx, dy, ¢z y dz
FIGURA 13.4.4
Flujo de sangre a
través de las dos resistencias del
ejemplo 7
ƒ(x0 x, y0y)
(x0 x, y0 y)
 y
 x
 x
z ƒ(x, y)
z  L(x, y)
y
z
plano tangente
superficie
 z
dz
(x0, y0)
ƒ(x0, y0)
R1
R2
flujo de
sangre
dz
¢z.
1
R
1
R1
1
R2  o  R
R1R2
R1
R2.
fy(x0, y0, z0)(y
y0)
fz(x0, y0, z0)(z
z0).
L(x, y, z)
f(x0, y0, z0)
fx(x0, y0, z0)(x
x0)
¢w
fx¢x
fy¢y
fz¢z
e1¢x
e2¢y
e3¢z,
¢w
f(x
¢x, y
¢y, z
¢z)
f(x, y, z).


## Página 188

Por último, la diferencial total de f es
(17)
EJEMPLO  8
Diferencial total: función de tres variables
Si 
entonces las tres primeras derivadas parciales son
Por (17) la diferencial total es
dw  2x dx  6y2 dy  12z3 dz.
w  x2  2y3  3z4,
13.4 Linealización y diferenciales
709
NOTAS DESDE EL AULA
i) Puesto que 
siempre que 
exista y 
es cercana a 0, parece razonable espe-
rar que 
será una buena aproximación a 
cuando 
y 
son ambas cercanas a 0. Pero la vida no es tan sencilla para funciones de varias variables.
La garantía de que 
para incrementos cercanos a 0 proviene de la continuidad de
las derivadas parciales 
y fy(x, y) y no simplemente de su existencia.
ii) Cuando trabaje en los problemas 27-30 en los ejercicios 13.4 descubrirá que las funcio-
nes
y 
introducidas en (4) del teorema 13.4.1 no son únicas.
e2
e1
fx(x, y)
dz  ¢z
¢y
¢x
¢z
dz  fx(x, y)¢x  fy(x, y)¢y
¢x
f ¿(x)
dy  ¢y
z
x
Fundamentos
En los problemas 1-6, encuentre una linealización de la fun-
ción dada en el punto indicado.
En los problemas 7-10, emplee una aproximación lineal para
aproximar la cantidad indicada.
7.
8.
9.
para 
10.
para f(x, y)  cos pxy
En los problemas 11-22, calcule la diferencial total de la fun-
ción dada.
19.
20. G(r, u, f) = r sen f cos u
21.
22.
En los problemas 23-26, compare los valores de 
y dz para la
función dada cuando (x, y) varía del primero al segundo punto.
23.
24.
25.
26.
En los problemas 27-30, encuentre funciones 
y 
de 
como se define en (4) del teorema 13.4.1.
27.
28.
29.
30.
Aplicaciones
31. Cuando la sangre fluye a través de tres resistencias R1, R2,
R3, en paralelo, la resistencia equivalente R de la red es
Dado que el error porcentual en la medida de cada resis-
tencia es 0.9%, calcule el error porcentual máximo
aproximado en R.
1
R  1
R1  1
R2  1
R3.
z  x3  y3
z  x2y2
z  10y2  3x  x2
z  5x2  3y  xy
¢z
e2
e1
z  x2  x2y2  2; (1, 1), (0.9, 1.1)
z  (x  y)2; (3, 1), (3.1, 0.8)
z  2x2y  5y  8; (0, 0), (0.2, 0.1)
z  3x  4y  8; (2, 4), (2.2, 3.9)
¢z
w  2u2  s2t2  y2
w  ln auy
st b
F(r, s, t)  r3  s2  4t1>2
f (0.52, 2.96)
f (x, y)  (x2  y2)2
f (1.95, 2.01)
A
35
63
1102  1
4 80
Ejercicios 13.4
Las respuestas de los problemas impares seleccionados comienzan en la página RES-41.
dw
0w
0x dx
0w
0y dy
0w
0z dz.
0w
0x
2x, 0w
0y
6y2 y 0w
0z
12z3.
1.
2.
3.
4.
5.
6. f(x, y)
e
2ysen 3x; (0, p>3)
f(x, y)
ln(x2
y3); (
1, 1)
f(x, y)
3 sen x cos y; (p>4, 3p>4)
f(x, y)
x2x2
y2; (8, 15)
f(x, y)
2x3y; (2, 2)
f(x, y)
4xy2
2x3y; (1, 1)
11. z = x2 sen 4y
12.
.4
1
.3
1
.6
1
.5
1
.8
1
.7
1
w
e
z2 cos(x2
y4)
w
x2y4z
5
g(r, u)
r2 cos 3u
f(s, t)
2s
t
s
3t
z
(5x3y
4y5)3
z
22x2
4y3
z
xex2
y2


## Página 189

32. La presión P de un gas ideal confinado está dada por
donde V es el volumen, T es la temperatura
y k es una constante. Dado que los errores porcentuales al
medir T y V son a lo sumo 0.6 y 
respectivamente,
calcule el error porcentual máximo aproximado en P.
33. La tensión T en la cuerda del yo-yo que se muestra en la
FIGURA 13.4.5 es
donde mg es su peso constante. Determine el cambio
aproximado en la tensión si R y r se incrementan de 4 cm
y 0.8 cm a 4.1 cm y 0.9 cm, respectivamente. ¿La tensión
aumenta o disminuye?
34. Determine el incremento aproximado en el volumen de
un cilindro circular recto si su altura aumenta de 10 a
10.5 cm y su radio crece de 5 a 5.3 cm. ¿Cuál es el nuevo
volumen aproximado?
35. Si la longitud, ancho y altura de una caja rectangular cerra-
da aumentan, respectivamente, en 2, 5 y 
¿cuál es el
incremento porcentual aproximado en el volumen?
36. En el problema 35, si la longitud, ancho y altura origina-
les son, respectivamente, 3, 1 y 2 pies, ¿cuál es el incre-
mento aproximado en el área de la superficie de la caja?
¿Cuál es la nueva área aproximada de la superficie?
37. La función 
produce el área de la
superficie del cuerpo de una persona en términos de su peso
w y altura h. Si el error en la medición de w es a lo sumo 3%
y el error en la medición de h es a lo sumo 5%, ¿cuál es el
error porcentual máximo aproximado en la medición de S?
38. La impedancia Z del circuito en serie que se presenta en
la FIGURA 13.4.6 es 
donde R es la resisten-
cia, X = 1 000L - 1 (1 000C) es la reactancia neta, L es
la inductancia y C es la capacitancia. Si los valores de R,
L y C dados en la figura se incrementan, respectivamen-
te, a 425 ohms, 0.45 henrys y
farads, ¿cuál
es el cambio aproximado en la impedancia del circuito?
¿Cuál es el valor aproximado de la nueva impedancia?
Piense en ello
39. a) Dé una definición para la linealización de una función
de tres variables 
b) Emplee la linealización para encontrar una aproxima-
ción de 
40. En el problema 67 de los ejercicios 13.3 se vio que para
tanto 
como 
existen en (0, 0). Explique por
qué f no es diferenciable en (0, 0).
41. a) Dé una explicación intuitiva del porqué f(x, y) =
no es diferenciable en (0, 0).
b) Después de esto pruebe que f no es diferenciable en
(0, 0).
42. La longitud de los lados de la caja rectangular roja que se
muestra en la FIGURA 13.4.7 son 
y 
Considere que el
volumen de la caja roja es V. Cuando se incrementan los
lados de la caja en las cantidades ¢x, ¢y y 
obtenemos
la caja rectangular que se ilustra en la figura que se traza
en azul. Dibuje o trace la figura 13.4.7 sobre un pedazo
de papel. Identifique por medio de colores diferentes las
cantidades ¢x, ¢y, ¢z, ¢V, dV y 
Proyectos
43. Brazo robótico
Un brazo de robot bidimensional cuyo
hombro está fijo en el origen sigue el rastro de su posición
por medio de un ángulo del hombro u y un ángulo del co-
do f como se ilustra en la FIGURA 13.4.8. El ángulo del hom-
bro se mide en el sentido contrario de las manecillas del
reloj desde el eje x y el ángulo del codo se mide en esa
misma dirección desde el brazo superior hasta el brazo
inferior, los cuales tienen una longitud respectiva L y l.
a) La ubicación de la unión del codo está dada por
(xc, yc), donde
Encuentre fórmulas correspondientes para la ubica-
ción (xm, ym) de la mano.
b) Muestre que las diferenciales totales de xm y ym pue-
den escribirse como
c) Suponga que L  l y que el brazo está ubicado de
manera que alcanza el punto
Suponga también
(L, L).
FIGURA 13.4.7
Caja del problema 42
x
y
z
¢V  dV.
¢z
z.
x, y
2x2
y2
0z>0y
0z>0x
2(9.1)2  (11.75)2  (19.98)2.
w  f (x, y, z).
FIGURA 13.4.6
Circuito en serie del problema 38
E
R  400 ohms
C  105 f
L0.4 h
11.1  105
>
Z  2R2  X2,
S  0.1091w0.425h0.725
8%,
FIGURA 13.4.5
Yo-yo del problema 33
R
T
r
T  mg 
R
2r2  R2,
0.8%,
P  k(T>V),
710
CAPÍTULO 13 Derivadas parciales
f (x, y)  •
xy
2x2  2y2,
(x, y)  (0, 0)
0,
(x, y)  (0, 0)
xc
L cos u, yc
L sen u.
dym
xmdu
(xc
xm) df.
dxm
ymdu
(yc
ym) df


## Página 190

que el error en la medición de cada uno de los ángu-
los u y f es a lo más de 
Calcule el error máximo
aproximado en la coordenada x de la ubicación de la
mano para cada una de las dos posiciones posibles.
44. Movimiento de proyectiles
Se dispara un proyectil a
un ángulo u con velocidad y a través de un abismo de
ancho D hacia el muro del acantilado vertical que es
esencialmente infinito tanto en la altura como en profun-
didad. Vea la FIGURA 13.4.9.
a) Si el proyectil sólo está sujeto a la fuerza de la grave-
dad, demuestre que la altura H a la cual golpea el
muro del acantilado como una función de las variables
y y u está dada por
[Sugerencia: Vea la sección 10.2.]
b) Calcule la diferencial total de H.
c) Suponga que D  100 pies, g  32 pies/s2, y  100
pies/s y u  45°. Calcule H.
d) Suponga, para los datos del inciso c), que el error en
la medición de y es a lo sumo 1 pies/s y que el error
en la medición de u es a lo sumo 1	. Calcule el
error máximo aproximado en H.
e) Al dejar que D varíe, H también puede considerarse
como una función de tres variables. Encuentre la dife-
rencial total de H. Empleando los datos de los incisos
c) y d) y suponiendo que el error en la medición D es
a lo sumo 2 pies/s, calcule el error máximo aproxi-
mado en H.
FIGURA 13.4.9
Abismo del problema 44
D
H

y
FIGURA 13.4.8
Brazo robótico del problema 43


x
(xm, ym)
(xc, yc)
y
L
l
1°.
13.5 Regla de la cadena
711
13.5 Regla de la cadena
Introducción
La regla de la cadena para funciones de una sola variable indica que si 
es una función diferenciable de x, y 
es una función diferenciable de t, entonces la deri-
vada de la función compuesta es
En esta sección se extiende la regla de la cadena a funciones de varias variables.
Regla de la cadena para derivadas ordinarias
Si 
y x y y son funciones de una
sola variable t, entonces el siguiente teorema indica cómo calcular la derivada ordinaria dz>dt.
z  f (x, y)
dy
dt  dy
dx dx
dt
.
x  g(t)
y  f (x)
Teorema 13.5.1
Regla de la cadena
Suponga que 
es diferenciable en 
y 
y que 
son funciones dife-
renciables en t. Entonces 
es una función diferenciable de t y
(1)
z  f (g(t), h(t))
y  h(t)
x  g(t)
(x, y)
z  f (x, y)
EJEMPLO  1
Regla de la cadena
Si 
y 
calcule 
en t  1.
Solución
De (1)
En este caso, en
x(1) = 2 y y(1) = -1, por lo que
dz
dt `
t1  (3 . 4 . (1)) . 4  (8  4) . 4  0.
t  1,
  (3x2y)(4t)  (x3  4y3)(10t  6).
 dz
dt  0z
0x dx
dt  0z
0y dy
dt
dz>dt
y  5t2  6t,
x  2t2,
z  x3y  y4
dz
dt
0z
0x
dx
dt
0z
0y
dy
dt
.
H
D tan u
1
2 g D2
y2 sec2 u.
