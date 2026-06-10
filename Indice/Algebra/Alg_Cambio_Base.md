> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Espacios_Vectoriales]] ← Anterior • Siguiente: [[Alg_Producto_Interno]]

# Cambio de Base

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Espacios_Vectoriales]] (tema anterior)**
> **→ [[Alg_Producto_Interno]] (siguiente tema)**

También: [[Alg_Transformaciones_Lineales]] | [[Alg_Autovalores_Autovectores]]

---

## 1. Coordenadas respecto a una base (repaso)

Dada una base **B = {b₁, b₂, …, bₙ}** de un espacio vectorial V, todo vector **v ∈ V** se escribe de manera **única** como combinación lineal de los vectores de B:

```
v = c₁·b₁ + c₂·b₂ + … + cₙ·bₙ
```

Las **coordenadas** de v en la base B son el vector columna:

```
[v]ᴮ = (c₁, c₂, …, cₙ)ᵀ
```

> [!TIP] Las coordenadas **dependen de la base**. El vector v es el mismo objeto geométrico; solo cambia cómo lo describimos numéricamente. Pensalo como un punto en el plano: podés dar sus coordenadas cartesianas (x, y) o polares (r, θ) — el punto no se mueve.

---

## 2. Idea conceptual: ¿qué significa cambiar de base?

Un mismo vector v ∈ ℝ² se puede representar con coordenadas distintas según qué base usemos.

```
          Base canónica E = {e₁, e₂}          Base B = {b₁, b₂}
                
     y                                b₂
     ^                                ^
     |                                |
     |       • v = (3, 2)ᴱ           |      • v = (?, ?)ᴮ
     |                                |
     +-------> x                      +-------> b₁

```

**Ejemplo visual:** el vector v = (3, 2) en base canónica. Si B = {(1, 1), (1, -1)}, las coordenadas en B serán otras — aunque el vector sea el mismo.

> [!WARNING] Error clásico: confundir el vector con sus coordenadas. El vector v vive en V independientemente de la base. Las coordenadas son solo **etiquetas** que dependen de la base elegida.

---

## 3. Matriz de cambio de base

### 3.1 Definición

Dadas dos bases **B** y **C** de V, la **matriz de cambio de base** (o matriz de transición) **Pᶜ←ᴮ** transforma coordenadas de B a C:

```
[v]ᶜ = Pᶜ←ᴮ · [v]ᴮ
```

**Construcción:** las columnas de Pᶜ←ᴮ son las coordenadas de cada vector de B expresado en base C:

```
Pᶜ←ᴮ = [ [b₁]ᶜ  |  [b₂]ᶜ  |  …  |  [bₙ]ᶜ ]
```

> [!TIP] Regla nemotécnica: la base **de la que salís** (B) está abajo, la base **a la que llegás** (C) está arriba. Pᶜ←ᴮ lee "de B → C". Las columnas son los vectores de B vestidos en ropa de C.

### 3.2 Propiedad fundamental

La matriz inversa hace el camino inverso:

```
Pᴮ←ᶜ = (Pᶜ←ᴮ)⁻¹
```

### 3.3 Cálculo práctico en ℝⁿ

Cuando trabajamos en ℝⁿ con la base canónica **E**, el cálculo es directo:

1. Formamos la matriz **M** cuyas columnas son los vectores de la nueva base B
2. Formamos la matriz **N** cuyas columnas son los vectores de la base canónica E
3. La matriz de cambio de E → B es: **Pᴮ←ᴱ = M⁻¹** (pues N = I)

O equivalentemente: para cambiar de base canónica E a base B:
```
Pᴮ←ᴱ = B⁻¹    (B = matriz con vectores de B como columnas)
```

---

> [!EXAMPLE] **Ejemplo 1: Cambio de base en ℝ² (paso a paso)**
>
> Sean:
> - Base canónica **E = {e₁ = (1,0), e₂ = (0,1)}**
> - Base **B = {b₁ = (1,1), b₂ = (1,-1)}**
>
> **Problema:** Dado v = (5, 3) en base E, hallar [v]ᴮ.
>
> **Paso 1:** Construir la matriz B cuyas columnas son los vectores de B:
> ```
> B = [1  1]
>     [1 -1]
> ```
>
> **Paso 2:** La matriz de cambio de base E → B es Pᴮ←ᴱ = B⁻¹.
> Calculamos B⁻¹:
> ```
> det(B) = (1)(-1) - (1)(1) = -2
> B⁻¹ = (1/(-2)) · [-1 -1]   =   [1/2  1/2]
>                   [-1  1]       [1/2 -1/2]
> ```
>
> **Paso 3:** Aplicamos Pᴮ←ᴱ a las coordenadas en E:
> ```
> [v]ᴮ = B⁻¹ · [v]ᴱ = [1/2  1/2] · [5] = [ (5+3)/2 ] = [4]
>                    [1/2 -1/2]   [3]   [ (5-3)/2 ]   [1]
> ```
>
> **Verificación:** v = 4·b₁ + 1·b₂ = 4(1,1) + 1(1,-1) = (4+1, 4-1) = (5,3) ✓
>
> **Interpretación geométrica:** el mismo vector (5,3) en coordenadas cartesianas es (4,1) en la base B.

---

> [!EXAMPLE] **Ejemplo 2: Cambio entre dos bases no canónicas**
>
> Sean:
> - Base **B = {b₁ = (1,0), b₂ = (1,1)}**
> - Base **C = {c₁ = (2,0), c₂ = (0,3)}**
>
> **Problema:** Encontrar Pᶜ←ᴮ.
>
> **Paso 1:** Expresamos cada bᵢ en la base C.
> Para b₁ = (1,0) = α₁·c₁ + α₂·c₂:
> ```
> (1,0) = α₁·(2,0) + α₂·(0,3) = (2α₁, 3α₂)
> → 2α₁ = 1 ⇒ α₁ = 1/2
> → 3α₂ = 0 ⇒ α₂ = 0
> → [b₁]ᶜ = (1/2, 0)ᵀ
> ```
>
> Para b₂ = (1,1) = β₁·c₁ + β₂·c₂:
> ```
> (1,1) = β₁·(2,0) + β₂·(0,3) = (2β₁, 3β₂)
> → 2β₁ = 1 ⇒ β₁ = 1/2
> → 3β₂ = 1 ⇒ β₂ = 1/3
> → [b₂]ᶜ = (1/2, 1/3)ᵀ
> ```
>
> **Paso 2:** Armamos Pᶜ←ᴮ:
> ```
> Pᶜ←ᴮ = [1/2  1/2]
>        [ 0   1/3]
> ```
>
> **Paso 3:** Verificamos con un vector. Sea v = (3,2) en E. En B: v = 1·b₁ + 2·b₂ → [v]ᴮ = (1,2)ᵀ.
> ```
> [v]ᶜ = Pᶜ←ᴮ · [1] = [1/2·1 + 1/2·2] = [1.5]
>                 [2]   [ 0·1 + 1/3·2]   [2/3]
> ```
> Comprobación: v = 1.5·c₁ + (2/3)·c₂ = 1.5·(2,0) + (2/3)·(0,3) = (3, 2) ✓

---

## 4. Cambio de base en transformaciones lineales

Este es el vínculo directo con [[Alg_Transformaciones_Lineales]].

Si **T: V → V** es una transformación lineal, y **A** es su matriz asociada en base B, entonces la matriz asociada **A'** en base C es:

```
A' = P⁻¹ · A · P
```

donde **P = Pᴮ←ᶜ** (o equivalentemente **P = Pᶜ←ᴮ⁻¹** según convención — revisá qué definición usa tu cursada).

Esta operación se llama **similitud** o **conjugación** de matrices. Dos matrices relacionadas por A' = P⁻¹AP representan la misma transformación lineal en bases distintas.

> [!WARNING] ¡Cuidado con la dirección! Es muy fácil confundir P y P⁻¹. Siempre verificá con un vector de prueba: si [v]ᶜ = Pᶜ←ᴮ·[v]ᴮ, entonces A' = (Pᶜ←ᴮ)⁻¹ · A · Pᶜ←ᴮ. Hacé la prueba dimensional para confirmar.

> [!TIP] Acordate: [[Alg_Autovalores_Autovectores]] es justamente el problema de encontrar una base (la base de autovectores) donde la matriz de T sea **diagonal**, es decir, A' = D = P⁻¹AP. ¡Todo el tema de diagonalización es cambio de base!

---

> [!EXAMPLE] **Ejemplo 3: Cambio de base en una transformación lineal**
>
> Sea **T: ℝ² → ℝ²** con matriz en base canónica: **A = `[[3, 1], [0, 2]]`**.
> Sea **B = {b₁ = (1,0), b₂ = (1,1)}**.
>
> **Problema:** Hallar la matriz de T en base B.
>
> **Paso 1:** Matriz P = Pᴮ←ᴱ (de base canónica a base B):
> ```
> P = B⁻¹ donde B = [1  1]  →  det(B) = 1  →  B⁻¹ = [1 -1]
>                  [0  1]                           [0  1]
> ```
> Luego P = Pᴮ←ᴱ = `[[1, -1], [0, 1]]`.
>
> **Paso 2:** La matriz en base B es A' = P · A · P⁻¹.
> P⁻¹ = B = `[[1, 1], [0, 1]]`.
> ```
> A' = P · A · P⁻¹
>    = [1 -1] · [3 1] · [1 1]
>      [0  1]   [0 2]   [0 1]
>
> Primero: A·P⁻¹ = [3 1] · [1 1] = [3  3+1] = [3  4]
>                  [0 2]   [0 1]   [0   2 ]   [0  2]
>
> Luego: P·(A·P⁻¹) = [1 -1] · [3 4] = [3  4-2] = [3  2]
>                     [0  1]   [0 2]   [0   2 ]   [0  2]
> ```
>
> **Resultado:** A' = `[[3, 2], [0, 2]]`.
>
> **Verificación:** T(b₁) debería ser la primera columna de A' en base B.
> T(b₁) = T(1,0) = (3,0) = 3·(1,0) + 0·(1,1) → [3, 0]ᵀ = primera columna ✓

---

## 5. Diagrama conceptual del cambio de base

```
              T (transformación lineal)
    V (base B) ──────────────────────── V (base B)
        │                                    │
        │ P (cambio de base)                 │ P
        │                                    │
        ∨                                    ∨
    V (base C) ──────────────────────── V (base C)
              T' = P⁻¹·T·P
```

Este diagrama **conmuta**: da igual si primero transformás y luego cambiás de base, o primero cambiás de base y luego transformás (con la matriz en la nueva base). Eso es exactamente lo que significa A' = P⁻¹AP.

---

## 6. Aplicaciones en ingeniería

| Área | Aplicación |
|------|-----------|
| **Mecánica** | Cambio de coordenadas al rotar sistemas de referencia (fuerzas, momentos) |
| **Gráfica por computadora** | Transformaciones de cámara: coordenadas mundo → coordenadas cámara |
| **Robótica** | Cambio entre sistemas de coordenadas de eslabones (cinemática directa) |
| **Vibraciones** | Diagonalización de matrices de masa y rigidez → modos normales |
| **Mecánica cuántica** | Cambio entre base de posición y base de momento |
| **Teoría de control** | Cambio de base para llevar un sistema a forma canónica controlable |

> [!TIP] En [[Eje_Fisica]], los cambios de base aparecen en cada rotación de ejes coordenados. Cada vez que rotás un sistema de referencia, estás haciendo un cambio de base ortogonal (matriz de rotación).

---

## 7. Errores comunes y su detección

| Error | Consecuencia | Cómo detectarlo |
|-------|-------------|-----------------|
| Confundir P con P⁻¹ | Coordenadas incorrectas | Verificar con un vector conocido |
| Poner las coordenadas como filas en vez de columnas | La matriz no funciona | Las columnas deben ser [bᵢ]ᶜ |
| Olvidar que las columnas son en base destino | P pasa de base equivocada | Siempre: columnas = base origen en ropa de base destino |
| No verificar con un vector | Error sin detectar | Probar: P·[v]ᴮ debería dar [v]ᶜ |

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---------|-----------|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U5 cambios de base.pdf` | Apunte Ariela: cambio de base |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/cambios de base.pdf` | Apunte Muñoz: cambio de base |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf` | Larson: Álgebra Lineal, capítulo de cambio de base |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf` | Grossman: Álgebra Lineal, sección cambio de base |

## 📝 Ejercicios

### TPs oficiales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP5 Cambio de Base.pdf|TP5 Cambio de Base (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°5 Cambio de Base.pdf|TP N°5 Cambio de Base]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Ariela Garcés/TP 5.pdf|TP5 Cambio de Base (Ariela)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica cambio de base_230925_174025.pdf|Práctica: cambio de base]]

### Ejercicios modelados

1. **Cambio de base simple:** Sea B = {(2,0), (0,3)} y C = {(1,1), (1,-1)} en ℝ².
   a) Hallar Pᶜ←ᴮ
   b) Hallar Pᴮ←ᶜ
   c) Si [v]ᴮ = (4, -1)ᵀ, hallar [v]ᶜ
   > *Guía:* Seguí el método de los ejemplos 1 y 2. Expresá cada vector de B en base C resolviendo sistemas 2×2. Verificá que Pᴮ←ᶜ = (Pᶜ←ᴮ)⁻¹.

2. **Verificación de cambio de base:** Sea B = {(1,2), (2,1)} y la base canónica E.
   a) Hallar Pᴱ←ᴮ
   b) Verificar que Pᴱ←ᴮ · Pᴮ←ᴱ = I
   > *Guía:* Pᴱ←ᴮ es simplemente la matriz con b₁ y b₂ como columnas. Pᴮ←ᴱ es su inversa.

3. **Aplicación a transformaciones:** Sea T: ℝ² → ℝ² con matriz A = `[[4, 1], [2, 3]]` en base canónica.
   Sea B = {(-1, 1), (1, -2)}.
   a) Hallar Pᴮ←ᴱ y Pᴱ←ᴮ
   b) Encontrar la matriz A' de T en base B usando A' = Pᴮ←ᴱ · A · Pᴱ←ᴮ
   > *Guía:* Recordá que Pᴱ←ᴮ es la matriz con los vectores de B como columnas. Pᴮ←ᴱ = (Pᴱ←ᴮ)⁻¹. El orden de multiplicación es importante.

4. **Cambio de base en ℙ₂:** Sea V = ℙ₂ (polinomios de grado ≤ 2).
   Bases: B = {1, x, x²} y C = {1, 1+x, 1+x+x²}.
   a) Hallar Pᶜ←ᴮ
   b) Dado p(x) = 3 + 2x + x² en base B, hallar [p]ᶜ
   > *Guía:* Expresá 1, x, x² como combinación lineal de 1, 1+x, 1+x+x². Es un sistema 3×3.

5. **Matrices semejantes:** Sean A = `[[2, 0], [0, 5]]` y B = `[[3, 2], [2, 4]]`.
   a) ¿Son semejantes? Si lo son, hallar P tal que B = P⁻¹AP.
   *Sugerencia:* dos matrices son semejantes si representan la misma transformación lineal en distintas bases. Compará sus autovalores.

---

## 📚 Referencias

- **Larson** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf|PDF]]
- **Grossman** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/Álgebra lineal - Grossman.pdf|PDF]]
- **Anton** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/6.- Álgebra Lineal (MathRocks) - Anton.pdf|PDF]]
- **Friedberg** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/1.- Álgebra Lineal (MathRocks) - Friedberg.pdf|PDF]]

---

> [!NOTE] Cambio de base es el pegamento entre [[Alg_Espacios_Vectoriales]] y [[Alg_Transformaciones_Lineales]]. Se vuelve natural cuando lo ves como "cambiar el sistema de coordenadas". Y es la puerta de entrada a [[Alg_Autovalores_Autovectores]] y diagonalización. ¡Asegurate de entender bien los ejemplos 1 y 2 antes de pasar a diagonalización!
