> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Polinomios]] ← Anterior • Siguiente: [[Alg_Cambio_Base]]

# Espacios Vectoriales

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Polinomios]] (tema anterior)**
> **→ [[Alg_Cambio_Base]] (siguiente tema)**

También: [[Eje_Analisis_Matematico]] | [[Eje_Fisica]]

---

## 1. Definición y axiomas

Un **espacio vectorial** sobre ℝ (o ℝ-ev) es un conjunto **V** (cuyos elementos llamamos **vectores**) dotado de dos operaciones:

1. **Suma:** + : V × V → V
2. **Producto por escalar:** · : ℝ × V → V

Que cumplen 8 axiomas. Clasificados en dos grupos:

**Axiomas de la suma (∀ u, v, w ∈ V):**

| # | Axioma | Significado |
|---|--------|-------------|
| A1 | (u+v)+w = u+(v+w) | Asociativa |
| A2 | u+v = v+u | Conmutativa |
| A3 | ∃ 0 ∈ V : v+0 = v | Existencia de neutro |
| A4 | ∀ v ∈ V, ∃ (−v) ∈ V : v+(−v) = 0 | Existencia de inverso aditivo |

**Axiomas del producto escalar (∀ u, v ∈ V, ∀ c, d ∈ ℝ):**

| # | Axioma | Significado |
|---|--------|-------------|
| A5 | c·(d·v) = (cd)·v | Asociativa mixta |
| A6 | (c+d)·v = c·v + d·v | Distributiva escalar |
| A7 | c·(u+v) = c·u + c·v | Distributiva vectorial |
| A8 | 1·v = v | Neutro multiplicativo |

> [!TIP] No te aprendas los 8 axiomas de memoria **sin entenderlos**. Pensá en ℝ²: la suma de vectores es la que ya conocés (paralelogramo), y multiplicar por escalar es estirar/acortar. Los axiomas solo formalizan propiedades que ya sabés que funcionan en ℝ² y ℝ³. Los espacios vectoriales generalizan esas propiedades a objetos más abstractos: polinomios, matrices, funciones.

---

## 2. Ejemplos clásicos

| Espacio | Elementos | Operaciones | Dimensión |
|---------|-----------|-------------|-----------|
| **ℝⁿ** | n-tuplas (x₁, …, xₙ) | (xᵢ)+(yᵢ) = (xᵢ+yᵢ); c·(xᵢ) = (c·xᵢ) | n |
| **ℙₙ** | Polinomios grado ≤ n | Suma usual de polinomios; producto escalar usual | n+1 |
| **Mₘₓₙ** | Matrices de m×n | Suma elemento a elemento; c·A | m·n |
| **ℂ** (como ℝ-ev) | Números complejos | Suma usual; c·z = c·(a+bi) | 2 |
| **ℱ(ℝ)** | Funciones f: ℝ→ℝ | (f+g)(x); (c·f)(x) | ∞ |
| **ℙ** (todos los polinomios) | Polinomios cualquier grado | Suma usual; producto escalar | ∞ |

> [!TIP] Los tres ejemplos que tenés que dominar: **ℝⁿ, ℙₙ, Mₘₓₙ**. La mayoría de los problemas de examen usan estos tres espacios. Si entendés las operaciones en cada uno, el resto viene solo.

> [!EXAMPLE] **Ejemplo 1: Verificar que ℝ² es un espacio vectorial**
>
> Verifiquemos los 8 axiomas para V = ℝ².
>
> **Suma:** (x₁, y₁) + (x₂, y₂) = (x₁ + x₂, y₁ + y₂)
> - A1: (u+v)+w = ((x₁+x₂)+x₃, (y₁+y₂)+y₃) = (x₁+(x₂+x₃), y₁+(y₂+y₃)) = u+(v+w) ✓
> - A2: (x₁+x₂, y₁+y₂) = (x₂+x₁, y₂+y₁) ✓
> - A3: Neutro = (0, 0) → (x, y) + (0, 0) = (x, y) ✓
> - A4: −v = (−x, −y) → (x, y) + (−x, −y) = (0, 0) ✓
>
> **Producto escalar:** c·(x, y) = (c·x, c·y)
> - A5: c·(d·(x,y)) = c·(dx, dy) = (cdx, cdy) = (cd)·(x, y) ✓
> - A6: (c+d)·(x,y) = ((c+d)x, (c+d)y) = (cx+dx, cy+dy) = c·(x,y) + d·(x,y) ✓
> - A7: c·((x₁,y₁)+(x₂,y₂)) = c·(x₁+x₂, y₁+y₂) = (c(x₁+x₂), c(y₁+y₂)) = (cx₁, cy₁)+(cx₂, cy₂) ✓
> - A8: 1·(x, y) = (x, y) ✓
>
> Conclusión: ℝ² es un espacio vectorial (como sabíamos intuitivamente).

---

## 3. Subespacios vectoriales

Un **subespacio** S ⊆ V es un subconjunto que, con las mismas operaciones de V, es en sí mismo un espacio vectorial.

**Criterio de subespacio (teorema):** S ≠ ∅ y para todo u, v ∈ S y c ∈ ℝ:
1. **Cerradura en suma:** u + v ∈ S
2. **Cerradura producto escalar:** c·u ∈ S

> [!TIP] En la práctica, solo verificás dos condiciones (además de S ≠ ∅). Si la suma y el producto escalar no sacan a los vectores de S, entonces S es subespacio. No necesitás verificar los 8 axiomas de nuevo.

**Ejemplos geométricos en ℝ³:**

```
         ℝ³                 Subespacios:
        /|\
       / | \           • {0} (origen) — dimensión 0
      /  |  \          • Rectas por origen — dimensión 1
     /   |   \         • Planos por origen — dimensión 2
    /    |    \        • ℝ³ mismo — dimensión 3
   /     |     \
  /  Recta    Plano
 /    (dim 1)  (dim 2)
└───────────
```

> [!WARNING] No todo subconjunto de un espacio vectorial es subespacio. Condiciones necesarias (pero no suficientes):
> - ❌ **Debe contener al 0.** Si no pasa por el origen, no es subespacio.
> - ❌ **Debe ser cerrado.** Si una recta no pasa por el origen, sumar dos vectores puede sacarte de ella.
> - ❌ **Un subespacio de ℝ³ no puede ser una curva** (como una parábola). Las curvas no son cerradas bajo suma.

> [!EXAMPLE] **Ejemplo 2: ¿Es S = {(x, y) ∈ ℝ² | y = 2x} un subespacio?**
>
> S es la recta que pasa por el origen con pendiente 2.
>
> **Verificación:**
> 1. (0, 0) ∈ S porque 0 = 2·0 ✓ (S ≠ ∅)
> 2. Sean u = (x₁, 2x₁) y v = (x₂, 2x₂) ∈ S:
>    u + v = (x₁+x₂, 2x₁+2x₂) = (x₁+x₂, 2(x₁+x₂)) ∈ S ✓
> 3. c·u = (c·x₁, c·2x₁) = (c·x₁, 2(c·x₁)) ∈ S ✓
>
> **Conclusión:** S es subespacio de ℝ².
>
> **¿Qué pasa con T = {(x, y) ∈ ℝ² | y = 2x + 1}?**
> (0, 0) ∉ T porque 0 ≠ 2·0 + 1 = 1 → **No es subespacio**. Es una recta que no pasa por el origen.

---

## 4. Combinación lineal y conjunto generador

**Combinación lineal** de {v₁, …, vₖ} ⊆ V:

```
w = c₁·v₁ + c₂·v₂ + … + cₖ·vₖ   (c₁, …, cₖ ∈ ℝ)
```

**Conjunto generador:** {v₁, …, vₖ} **genera** V si todo vector de V se puede escribir como combinación lineal de ellos.

**Espacio generado (span):**

```
gen{v₁, …, vₖ} = { Σ cᵢ·vᵢ  |  cᵢ ∈ ℝ }
```

> [!TIP] Pensá en gen{v₁, …, vₖ} como "el subespacio más chico que contiene a todos los vᵢ". Es el conjunto de **todo lo que podés alcanzar** combinando linealmente los vectores.

**Geometría del span:**
- gen{v} con v ≠ 0 = recta por el origen
- gen{v₁, v₂} con v₁, v₂ LI = plano por el origen
- gen{v₁, v₂} con v₁, v₂ LD = recta (no generan un plano)

---

## 5. Dependencia e independencia lineal

**Definición:** {v₁, …, vₖ} es **linealmente independiente (LI)** si la única solución de:

```
c₁·v₁ + c₂·v₂ + … + cₖ·vₖ = 0
```

es c₁ = c₂ = … = cₖ = 0.

Si existe alguna combinación lineal no trivial que da 0 → son **linealmente dependientes (LD)**.

**Interpretación geométrica:**

```
LI (ℝ²):                           LD (ℝ²):
  b₂                                b₂ = 2·b₁
  ^                                 ^
  |                                 |   /
  |   • b₁                          |  /
  |  /                              | /
  | /                               |/
  └──────>                     b₁───┴──────>
  b₁ y b₂ no son colineales         b₂ es combinación de b₁
  → generan todo ℝ²                 → solo generan una recta
```

**Propiedades clave:**

| Propiedad | Explicación |
|-----------|-------------|
| Si 0 ∈ conjunto → LD | Siempre |
| Si |conjunto| > dim(V) → LD | No pueden ser más que la dimensión |
| Si |conjunto| = dim(V) y LI → Es base | Máximo conjunto LI |
| Si |conjunto| = dim(V) y genera → Es base | Mínimo conjunto generador |

> [!EXAMPLE] **Ejemplo 3: Determinar si vectores en ℝ³ son LI o LD**
>
> v₁ = (1, 2, 1), v₂ = (2, 1, 0), v₃ = (1, −1, −1)
>
> **Método 1:** Plantemos c₁·v₁ + c₂·v₂ + c₃·v₃ = 0:
> ```
> c₁ + 2c₂ + c₃ = 0
> 2c₁ + c₂ − c₃ = 0
> c₁ + 0c₂ − c₃ = 0
> ```
>
> Resolvemos el sistema homogéneo. La matriz es:
> ```
> A = [1  2  1]
>     [2  1 −1]
>     [1  0 −1]
> ```
>
> det(A) = 1·(1·(−1) − (−1)·0) − 2·(2·(−1) − (−1)·1) + 1·(2·0 − 1·1)
>        = 1·(−1) − 2·(−2+1) + 1·(−1)
>        = −1 − 2·(−1) − 1 = −1 + 2 − 1 = 0
>
> Como det(A) = 0 → los vectores son **LD**.
>
> **Método 2 (rápido):** Como v₃ = v₁ − v₂, hay dependencia inmediata.
> v₁ − v₂ = (1−2, 2−1, 1−0) = (−1, 1, 1) = −v₃ → v₃ = −(v₁−v₂) = v₂ − v₁ ✓

---

## 6. Bases y dimensión

**Base:** Un conjunto B ⊆ V es base si:
1. **B es LI** (independencia lineal)
2. **B genera a V** (todo vector de V se escribe como combinación lineal de B)

**Dimensión:** El número de vectores de **cualquier** base de V.

| Espacio | Base canónica | Dimensión |
|---------|---------------|-----------|
| ℝⁿ | {e₁=(1,0,…,0), …, eₙ=(0,…,0,1)} | n |
| ℙₙ | {1, x, x², …, xⁿ} | n+1 |
| Mₘₓₙ | {Eᵢⱼ (1 en i,j, 0 resto)} | m·n |

**Teoremas fundamentales:**
- Toda base de V tiene exactamente dim(V) vectores
- Cualquier conjunto LI puede **extenderse** a una base
- Cualquier conjunto generador puede **reducirse** a una base
- dim(subespacio) ≤ dim(V), con igualdad solo si el subespacio es V mismo

**Coordenadas en una base:**
Dada una base B = {b₁, …, bₙ} de V, todo v ∈ V se expresa de manera **única** como:

```
v = c₁·b₁ + c₂·b₂ + … + cₙ·bₙ
```

Y el vector de coordenadas es **[v]ᴮ = (c₁, c₂, …, cₙ)ᵀ**.

> [!TIP] Las coordenadas son el **puente** entre los espacios vectoriales abstractos y ℝⁿ. Si tenés un espacio abstracto V con base B, el vector de coordenadas [v]ᴮ es un vector concreto de ℝⁿ con el que podés hacer cuentas. Esto es la base de [[Alg_Cambio_Base]].

> [!EXAMPLE] **Ejemplo 4: Bases de ℙ₂ (polinomios de grado ≤ 2)**
>
> Base canónica: B = {1, x, x²}
>
> Un polinomio p(x) = 3 − 2x + 5x² tiene coordenadas [p]ᴮ = (3, −2, 5)ᵀ.
>
> **Otra base de ℙ₂:** C = {1, 1+x, 1+x+x²}
>
> ¿Son LI? Verificamos:
> c₁·1 + c₂·(1+x) + c₃·(1+x+x²) = 0
> (c₁ + c₂ + c₃) + (c₂ + c₃)x + (c₃)x² = 0
> → c₃ = 0, c₂ + c₃ = 0 → c₂ = 0, c₁ + c₂ + c₃ = 0 → c₁ = 0
> → Única solución trivial → **LI** ✓
>
>¿Generan ℙ₂? Cualquier polinomio a + bx + cx² se puede escribir como combinación de C (resolviendo un sistema 3×3). Como son 3 vectores LI en un espacio de dim 3, automáticamente generan → **Es base**. Este ejemplo es clave para [[Alg_Cambio_Base]].

---

## 7. Propiedades clave resumidas

| Propiedad | Enunciado |
|-----------|-----------|
| **Existencia de base** | Todo espacio vectorial (dimensión finita) tiene una base |
| **Unicidad de coordenadas** | En una base fija, cada vector tiene coordenadas únicas |
| **Completar base** | Todo conjunto LI se puede extender a una base |
| **Reducir generador** | Todo conjunto generador contiene una base |
| **Dimensión** | dim(V) = número de vectores en cualquier base |
| **Dimensión de subespacio** | dim(S) ≤ dim(V); igualdad solo si S = V |
| **Rango** | dim(gen{v₁, …, vₖ}) = rango de la matriz con esos vectores como filas/columnas |

---

## 8. Aplicaciones en ingeniería

| Área | Aplicación |
|------|-----------|
| **Teoría de señales** | Las señales forman un espacio vectorial de funciones; las bases de Fourier son un cambio de base |
| **Mecánica cuántica** | Los estados cuánticos viven en espacios vectoriales (espacios de Hilbert) |
| **Control** | El espacio de estados es un espacio vectorial de variables de estado |
| **Procesamiento de imágenes** | Las imágenes son vectores en ℝⁿ; compresión = cambio de base (DCT, wavelets) |
| **Gráfica 3D** | Los objetos 3D se manipulan mediante transformaciones lineales en ℝ⁴ (coordenadas homogéneas) |
| **Método de elementos finitos** | Las funciones de forma forman una base del espacio de soluciones aproximadas |

> [!WARNING] Este es el tema más abstracto de todo el álgebra. No te frustres si al principio no lo ves "útil" — los espacios vectoriales son la base de todo el álgebra lineal moderna. Acordate: **ℝⁿ, ℙₙ y Mₘₓₙ** son los tres ejemplos que tenés que dominar. Y no te olvides de conectar este tema con [[Alg_Transformaciones_Lineales]] y [[Alg_Cambio_Base]].

### Conexiones con otras áreas de la red
- [[Alg_Cambio_Base]]: las coordenadas [v]ᴮ son el punto de partida
- [[Alg_Transformaciones_Lineales]]: son funciones que preservan la estructura de espacio vectorial
- [[Alg_Producto_Interno]]: agrega geometría (ángulos, distancias) al espacio vectorial
- [[Alg_Autovalores_Autovectores]]: diagonalización = encontrar mejor base para una transformación
- [[Anm_Ecuaciones_Diferenciales]]: el espacio de soluciones de una EDO lineal es un espacio vectorial

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---------|-----------|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U4 espacios vectoriales.pdf` | Apunte Ariela: espacios vectoriales |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/espacios vectoriales.pdf` | Apunte Muñoz: espacios vectoriales |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf` | Larson: Álgebra Lineal, capítulos de EV |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf` | Grossman: Álgebra Lineal |

## 📝 Ejercicios

### TPs oficiales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP4 Espacios Vectoriales.pdf|TP4 Espacios Vectoriales (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°4 EV.pdf|TP N°4 EV]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Ariela Garcés/TP 4.pdf|TP4 Espacios Vectoriales (Ariela)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica espacios vectoriales _230921_125534.pdf|Práctica: espacios vectoriales]]

### Resúmenes
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Algebra y Geometria II RESUMEN PARCIAL 1.pdf|Resumen 1er parcial AyG II]]

### Ejercicios modelados

1. **¿Es subespacio?** Determinar si S = {(x, y, z) ∈ ℝ³ | x + y = 0, x − z = 0} es subespacio de ℝ³.
   > *Guía:* Verificá (0,0,0) ∈ S, luego suma y producto escalar. Resolvé las ecuaciones: y = −x, z = x. S = {(t, −t, t) | t ∈ ℝ} — es una recta por el origen → **Sí es subespacio**, dimensión 1.

2. **LI o LD en ℝ⁴:** v₁ = (1, 0, 2, 1), v₂ = (0, 1, −1, 3), v₃ = (2, −1, 5, −1). ¿Son LI o LD?
   > *Guía:* Formá la matriz con los vectores como filas (o columnas) y calculá el rango. Si rango = 3 → LI. Si rango < 3 → LD. Sugerencia: notá que v₃ = 2v₁ − v₂ → LD.

3. **Hallar una base de un subespacio:** Sea S = {(x, y, z) ∈ ℝ³ | x + y + z = 0}. Hallar una base de S y su dimensión.
   > *Guía:* Parametrizá: z = −x − y → (x, y, −x−y) = x·(1, 0, −1) + y·(0, 1, −1). Base: {(1, 0, −1), (0, 1, −1)}. dim(S) = 2 (es un plano por el origen).

4. **Cambio de base en ℝ³:** Dada la base canónica E y la base B = {(1, 1, 0), (0, 1, 1), (1, 0, 1)} de ℝ³:
   a) Demostrar que B es base.
   b) Hallar [v]ᴮ para v = (3, −2, 4)ᴱ.
   > *Guía:* a) Calculá el determinante de la matriz con los vectores como columnas. Si det ≠ 0 → son LI y como son 3 en ℝ³ → base. b) Resolvé el sistema M·[v]ᴮ = v (donde M = matriz de B) usando inversa (ver [[Alg_Cambio_Base]]).

5. **Completar a una base:** Completar el conjunto LI {(1, 2, 0, 1), (0, 0, 1, 3)} a una base de ℝ⁴.
   > *Guía:* Agregá e₁ = (1, 0, 0, 0) y e₂ = (0, 1, 0, 0). Verificá si los 4 vectores son LI. Si algún eᵢ es combinación de los anteriores, reemplazalo. El objetivo: tener 4 vectores LI en ℝ⁴.

---

## 📚 Referencias

- **Larson** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf|PDF]]
- **Grossman** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf|PDF]]
- **Friedberg** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/1.- Álgebra Lineal (MathRocks) - Friedberg.pdf|PDF]]
- **Kolman** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Algebra Lineal - Kolman.pdf|PDF]]

> [!WARNING] Este es el tema más abstracto de todo el álgebra. No te frustres si al principio no lo ves "útil" — los espacios vectoriales son la base de todo el álgebra lineal moderna. Acordate: **ℝⁿ, ℙₙ y Mₘₓₙ** son los tres ejemplos que tenés que dominar.
