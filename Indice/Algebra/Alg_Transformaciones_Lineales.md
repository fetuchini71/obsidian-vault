> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Producto_Interno]] ← Anterior • Siguiente: [[Alg_Autovalores_Autovectores]]

# Transformaciones Lineales

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Producto_Interno]] (tema anterior)**
> **→ [[Alg_Autovalores_Autovectores]] (siguiente tema)**

También: [[Eje_Fisica]] | [[Alg_Espacios_Vectoriales]] | [[Alg_Cambio_Base]] | [[Eje_Analisis_Matematico]]

---

## 1. Definición

Una **transformación lineal** T: V → W es una función entre espacios vectoriales tal que:

1. **T(u + v) = T(u) + T(v)** (preserva suma)
2. **T(c·u) = c·T(u)** (preserva producto escalar)

> [!WARNING] Una TL lleva vectores de un espacio a otro respetando la estructura de espacio vectorial. Si no cumple esas dos propiedades, NO es lineal. Verificar siempre con ambos axiomas, no solo con uno.

> [!TIP] Para comprobar si una función es TL, probá primero con T(0). Toda TL cumple T(0) = 0. Si T(0) ≠ 0, automáticamente no es lineal. Esto sirve como filtro rápido.

---

## 2. Ejemplos fundamentales

| T: V → W | Expresión | Lineal |
|---|---|---|
| Rotación en ℝ² (θ) | T(x,y) = (x·cosθ - y·senθ, x·senθ + y·cosθ) | ✓ |
| Reflexión en eje x | T(x,y) = (x, -y) | ✓ |
| Reflexión en y = x | T(x,y) = (y, x) | ✓ |
| Proyección sobre eje x | T(x,y) = (x, 0) | ✓ |
| Contracción/expansión | T(v) = c·v | ✓ |
| Derivada | T(f) = f' (de ℙₙ → ℙₙ₋₁) | ✓ |
| Integral definida | T(f) = ∫₀¹ f(x) dx (ℙₙ → ℝ) | ✓ |
| T(x) = x + 1 | en ℝ | ✗ (no preserva suma) |
| T(x) = x² | en ℝ | ✗ (no preserva producto escalar) |

> [!EXAMPLE] **Ejemplo 1: ¿Es lineal T(x,y) = (2x + y, x - 3y)?**
>
> Verificación paso a paso:
> 1. **Suma:** T(u+v) = T(u₁+v₁, u₂+v₂) = (2(u₁+v₁) + (u₂+v₂), (u₁+v₁) - 3(u₂+v₂))
>    = (2u₁+2v₁+u₂+v₂, u₁+v₁-3u₂-3v₂) = (2u₁+u₂, u₁-3u₂) + (2v₁+v₂, v₁-3v₂) = T(u) + T(v) ✓
> 2. **Escalar:** T(c·u) = T(cu₁, cu₂) = (2cu₁+cu₂, cu₁-3cu₂) = c·(2u₁+u₂, u₁-3u₂) = c·T(u) ✓
> **Conclusión:** SÍ es lineal. Es una TL de ℝ² → ℝ² con matriz asociada A = `[[2, 1], [1, -3]]`.

> [!EXAMPLE] **Ejemplo 2: TL de derivación en ℙ₃ → ℙ₂**
>
> Sea T: ℙ₃ → ℙ₂ definida por T(p) = p'(x).
> - Tomamos base estándar: {1, x, x², x³} para ℙ₃, {1, x, x²} para ℙ₂
> - T(1) = 0, T(x) = 1, T(x²) = 2x, T(x³) = 3x²
> - Matriz asociada (3×4):
>   ```
>          [0  1  0  0]
>   [T] =  [0  0  2  0]
>          [0  0  0  3]
>   ```
> - Ker T = polinomios constantes (grado 0) → dim = 1
> - Im T = ℙ₂ (todo polinomio de grado ≤ 2 tiene una antiderivada) → dim = 3
> - Verificación: dim(ℙ₃) = 4 = 1 + 3 = ν(T) + ρ(T) ✓

---

## 3. Núcleo e Imagen

**Núcleo (Ker T):** vectores v ∈ V tal que T(v) = 0
- Es un **subespacio** de V
- T es **inyectiva** ⇔ Ker T = {0}
- **Nulidad:** ν(T) = dim(Ker T)

**Imagen (Im T):** {T(v) | v ∈ V}
- Es un **subespacio** de W
- T es **sobreyectiva** ⇔ Im T = W
- **Rango:** ρ(T) = dim(Im T)

### Teorema de la dimensión

```
dim(V) = dim(Ker T) + dim(Im T)
   ↓            ↓              ↓
  ν(T)      +      ρ(T)

Ejemplo: T: ℝ³ → ℝ² con T(x,y,z) = (x-y, y-z)
  - Ker T: x-y=0, y-z=0 → x=y=z → {(t,t,t)} → dim=1
  - Im T: ℝ² completo → dim=2
  - dim(ℝ³)=3 = 1+2 ✓
```

> [!TIP] El teorema de la dimensión es la herramienta más versátil para determinar propiedades de una TL sin calcularla explícitamente. Si sabés la dimensión del núcleo, sabés el rango, y viceversa.

> [!WARNING] Error común: confundir núcleo con conjunto de vectores que van a cero en el codominio. Ker T ⊆ V (el dominio), NO ⊆ W. La imagen sí está en W.

---

## 4. Matriz asociada

Dada una base B = {v₁, …, vₙ} de V y C = {w₁, …, wₘ} de W:

`[T(v)]ᶜ = [T]ᶜ←ᴮ · [v]ᴮ`

Las columnas de `[T]ᶜ←ᴮ` son `[T(v₁)]ᶜ, [T(v₂)]ᶜ, …, [T(vₙ)]ᶜ`

**Caso especial:** si V = ℝⁿ y W = ℝᵐ (con base canónica), la matriz asociada tiene como columnas T(e₁), T(e₂), …, T(eₙ).

```
Diagrama: Construcción de la matriz asociada

                   T
        V ────────────────→ W
        ↑                    ↑
    [v]ᴮ   ──── [T]ᶜ←ᴮ ──→  [T(v)]ᶜ

  Base B = {v₁,...,vₙ}    Base C = {w₁,...,wₘ}

  Para cada vᵢ: calculamos T(vᵢ), lo expresamos en C
  y lo ponemos como columna i de la matriz.
```

> [!EXAMPLE] **Ejemplo 3: Matriz de una rotación en ℝ²**
>
> La TL T(x,y) = (x·cosθ - y·senθ, x·senθ + y·cosθ) tiene matriz:
> ```
> [T] = [cosθ  -senθ]
>       [senθ   cosθ]
> ```
>
> Verificación: T(e₁) = (cosθ, senθ) = 1ª columna ✓
> T(e₂) = (-senθ, cosθ) = 2ª columna ✓
>
> Para θ = 90°: matriz = `[[0, -1], [1, 0]]`
> Aplicada a v = (1,0): T(v) = (0, 1) → rotación antihoraria ✓

---

## 5. Composición y matriz inversa

**Composición:** (T∘S)(v) = T(S(v))
- Matriz: [T∘S] = [T]·[S]

**TL inversa:** T⁻¹: W → V si T es biyectiva
- Matriz: [T⁻¹] = [T]⁻¹

**Isomorfismo:** TL biyectiva (V y W son isomorfos si dim V = dim W)

> [!TIP] La composición de TL corresponde a multiplicación de matrices. Esto no es casualidad: la multiplicación de matrices se definió para que así fuera. Recordá que el orden importa: (T∘S)(v) = T(S(v)) → [T]·[S]·[v].

> [!WARNING] **No conmutan.** En general T∘S ≠ S∘T. Por ejemplo, rotar y luego reflejar no es lo mismo que reflejar y luego rotar. La diferencia es [T,S] = T·S - S·T (el **conmutador**), que es cero solo en casos especiales.

---

## 6. Cambio de base en TL

Si A es la matriz de T en base B, y queremos la matriz en base C:

`A' = P⁻¹·A·P`

Donde P es la matriz de cambio de base de C a B.

```
Diagrama: Cambio de base

          A (base B)
   V ────────────────→ V
   ↑                   ↑
   │                   │
  P·[v]               P·[T(v)]
   │                   │
   │    A' = P⁻¹·A·P   │
   └───────────────────┘

  [v] (en B) → A·[v] → [T(v)] (en B)
   ↓ P        ↓ P⁻¹·A·P  ↓ P
  [v] (en C) → A'·[v] → [T(v)] (en C)
```

> [!TIP] Las matrices A y P⁻¹·A·P se llaman **matrices semejantes**. Tienen los mismos autovalores, el mismo polinomio característico, la misma traza y el mismo determinante. Esto es clave para [[Alg_Autovalores_Autovectores]].

---

## 7. Clasificación de TL

| Tipo | Propiedad | Condición matricial |
|---|---|---|
| **Monomorfismo** | Inyectiva (Ker = {0}) | Columnas LI (rango = n) |
| **Epimorfismo** | Sobreyectiva (Im = W) | rango = dim(W) |
| **Isomorfismo** | Biyectiva | Matriz cuadrada invertible |
| **Endomorfismo** | V = W (TL de V en sí mismo) | Matriz cuadrada |
| **Automorfismo** | Isomorfismo con V = W | Matriz cuadrada invertible |

Relación entre tipos:
```
           Automorfismo
               ↓
         Endomorfismo  ←  Isomorfismo
               ↓              ↓
         (V = W)      (dim V = dim W, biyectiva)
               ↓              ↓
           Monomorfismo   Epimorfismo
               ↓              ↓
           Inyectiva     Sobreyectiva
```

---

## 8. Aplicaciones de ingeniería

### 8.1 Gráficos por computadora (rotaciones 3D)
Las transformaciones lineales son la base de los gráficos 3D. Una rotación alrededor del eje Z en ℝ³:
```
Rz(θ) = [cosθ  -senθ   0]
        [senθ   cosθ    0]
        [0      0       1]
```
Todas las transformaciones de modelado (rotar, escalar, trasladar con coordenadas homogéneas, sesgar) son TL o afines. En gráficos se usan **matrices 4×4** con coordenadas homogéneas para incluir traslaciones.

### 8.2 Procesamiento de imágenes (filtros lineales)
Un filtro de imagen es una TL entre espacios de píxeles:
- **Desenfoque:** cada píxel nuevo es un promedio ponderado de sus vecinos (convolución lineal)
- **Detección de bordes:** filtro Sobel como TL de gradiente
- **Ajuste de brillo/contraste:** T(x) = a·x + b (afín con componente lineal)

### 8.3 Robótica (cinemática directa)
Las transformaciones entre sistemas de coordenadas (base → brazo → efector final) se representan con matrices. La composición de rotaciones y traslaciones usa TL en coordenadas homogéneas.

### 8.4 Análisis estructural (método de rigidez)
Las deformaciones en una estructura se relacionan con las fuerzas mediante una TL (matriz de rigidez). Resolver el sistema K·u = f es aplicar la TL inversa.

> [!TIP] Las TL están en todas partes en ingeniería. Siempre que tengas una **relación lineal** entre entrada y salida (señal, fuerza, imagen, coordenada), estás usando TL aunque no las llames así.

---

## 9. Conexiones con otras áreas

| Conexión | Descripción | Wikilink |
|---|---|---|
| Espacios vectoriales | Las TL operan sobre EV | [[Alg_Espacios_Vectoriales]] |
| Cambio de base | Matrices semejantes | [[Alg_Cambio_Base]] |
| Autovalores | Diagonalización de TL | [[Alg_Autovalores_Autovectores]] |
| Producto interno | TL ortogonales | [[Alg_Producto_Interno]] |
| EDO lineales | Operadores diferenciales lineales | [[Anm_Ecuaciones_Diferenciales]] |
| Transformada de Laplace | TL de espacios de funciones | [[Anm_Transformada_Laplace]] |
| Física (óptica) | Matrices de transferencia de rayos | [[Eje_Fisica]] |
| Análisis II | Derivada como TL (linealización) | [[Eje_Analisis_Matematico]] |

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U7 transformaciones lineales.pdf` | Apunte Ariela: TL |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/transformaciones lineales.pdf` | Apunte Muñoz: TL |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf` | Larson Cap. 6: TL |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/1.- Álgebra Lineal (MathRocks) - Friedberg.pdf` | Friedberg Cap. 2: TL |

## 📝 Ejercicios

### TPs
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP7 Transformaciones Lineales.pdf|TP7 Transformaciones Lineales (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°7 Transformaciones Lineales.pdf|TP N°7 TL]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Ariela Garcés/TP 7.pdf|TP7 TL (Ariela)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica transformaciones lineales_231025_165345.pdf|Práctica: TL]]

---

## Ejercicios modelados

### Ejercicio 1: Núcleo e imagen de una proyección
Sea T: ℝ³ → ℝ³ definida por T(x,y,z) = (x, y, 0).
1. **a)** Mostrar que T es lineal.
2. **b)** Hallar Ker T y su dimensión.
3. **c)** Hallar Im T y su dimensión.
4. **d)** Verificar el teorema de la dimensión.

**Guía:** Para (a) usar las dos propiedades. Para (b) resolver T(v)=0. Para (c) identificar qué coordenadas se generan.
**Respuesta:** Ker T = {(0,0,z)} (eje Z, dim=1), Im T = {(x,y,0)} (plano XY, dim=2), dim(V)=3=1+2 ✓

### Ejercicio 2: Matriz asociada a una TL en ℙ₂
Sea T: ℙ₂ → ℙ₂ definida por T(p) = p'(x) + p(0).
1. **a)** Calcular T(1), T(x), T(x²).
2. **b)** Hallar la matriz asociada en base {1, x, x²}.
3. **c)** Hallar una base de Ker T.
4. **d)** Hallar una base de Im T.

**Respuesta:** Matriz = `[[0,1,0],[0,0,2],[0,0,0]]`.
Ker T = {polinomios constantes} = gen{1}. Im T = gen{x, x²} (polinomios con término independiente 0).

### Ejercicio 3: Composición de TL
Sean S: ℝ² → ℝ³ con S(x,y) = (x+y, x-y, y), y T: ℝ³ → ℝ² con T(u,v,w) = (u+v, v-w).
1. **a)** Hallar las matrices [S] y [T] en bases canónicas.
2. **b)** Calcular T∘S: ℝ² → ℝ² y su matriz.
3. **c)** Verificar que [T∘S] = [T]·[S].

**Guía:** Armar columnas aplicando S a e₁, e₂ y T a e₁, e₂, e₃. Multiplicar matrices.
**Respuesta:** T∘S(x,y) = ((x+y)+(x-y), (x-y)-y) = (2x, x-2y). Matriz = `[[2,0],[1,-2]]`.

### Ejercicio 4: ¿Es isomorfismo?
Sea T: ℝ³ → ℝ³ con T(x,y,z) = (x+2y, y-z, x+3y-z).
1. **a)** Hallar la matriz asociada.
2. **b)** Calcular el determinante.
3. **c)** Determinar si T es biyectiva.
4. **d)** Si lo es, hallar T⁻¹.

**Respuesta:** Det = 0 → T no es biyectiva (no es isomorfismo). Ker T = gen{(1,-1,-1)}, dim=1.

### Ejercicio 5: TL con cambio de base
Sea T: ℝ² → ℝ² con matriz en canónica A = `[[1,1],[0,2]]`.
1. **a)** Hallar la matriz de T en base B = {(1,1), (1,0)}.
2. **b)** Verificar que las matrices son semejantes (mismos autovalores).

**Guía:** Construir P cuyas columnas son la base B. Calcular A' = P⁻¹·A·P.
**Respuesta:** A' = `[[2,0],[1,1]]`. autovalores: 1 y 2 en ambas ✓.

---

> [!NOTE] Las TL son el concepto más importante de AyG II. Todo lo anterior (espacios vectoriales, bases, cambio de base) es herramienta para entender transformaciones lineales. La matriz asociada y el teorema de la dimensión son los dos resultados clave. Dominando TL, el salto a autovalores y diagonalización es natural.
