> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Transformaciones_Lineales]] ← Anterior • Siguiente: (último tema del eje)

# Autovalores, Autovectores y Formas Cuadráticas

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Transformaciones_Lineales]] (tema anterior)**
> **→ [[Eje_Algebra]] (volver al eje)**

También: [[Alg_Matrices_Determinantes]] | [[Eje_Analisis_Matematico]] | [[Eje_Fisica]] | [[Anm_Ecuaciones_Diferenciales]] | [[Anm_Transformada_Laplace]]

---

## Parte 1: Autovalores y autovectores

### 1. Definición

Sea T: V → V una TL (endomorfismo) con matriz asociada A. Un **autovector** v ≠ 0 y su **autovalor** λ cumplen:

`T(v) = λ·v`  o  `A·v = λ·v`

**Interpretación geométrica:** el autovector solo se estira/comprime (por λ) bajo la transformación, no cambia de dirección. Es la dirección "estable" de la TL.

```
Diagrama: Acción de una TL sobre un autovector

        Antes                     Después
     ┌──────┐                  ┌──────────┐
     │  v   │       T          │  λ·v     │
     │  →   │   ────────→      │  →→→     │
     └──────┘                  └──────────┘
     (original)               (estirado si |λ|>1,
                               comprimido si |λ|<1,
                               invertido si λ<0)
```

> [!WARNING] Por definición, **v ≠ 0**. El vector cero siempre cumple A·0 = λ·0 para cualquier λ, pero no se considera autovector. Los autovalores pueden ser cero: si λ = 0, entonces A·v = 0 y v está en el núcleo de A.

> [!EXAMPLE] **Ejemplo 1: Autovalores de una matriz diagonal**
>
> Sea A = `[[3, 0], [0, -2]]`.
> - A·(1,0) = (3,0) = 3·(1,0) → λ₁ = 3, v₁ = (1,0)
> - A·(0,1) = (0,-2) = -2·(0,1) → λ₂ = -2, v₂ = (0,1)
>
> Las matrices diagonales tienen como autovectores los vectores canónicos, y los autovalores son los elementos de la diagonal. ¡Por eso diagonalizar es tan conveniente!

### 2. Ecuación característica

`det(A - λ·I) = 0`

- El polinomio característico es de grado n
- Sus raíces son los autovalores
- La **multiplicidad algebraica** de λ es su multiplicidad como raíz del polinomio característico

> [!TIP] Para matrices 2×2, el polinomio característico se puede calcular como:
> λ² - tr(A)·λ + det(A) = 0
> Esto es mucho más rápido que expandir det(A - λI). Para 3×3, usá la fórmula: -λ³ + tr(A)·λ² - (suma de menores principales 2×2)·λ + det(A) = 0

> [!EXAMPLE] **Ejemplo 2: Cálculo completo para 2×2**
>
> A = `[[4, 1], [2, 3]]`
>
> Polinomio característico:
> det(A - λI) = det(`[[4-λ, 1], [2, 3-λ]]`)
> = (4-λ)(3-λ) - 2 = 12 - 7λ + λ² - 2 = λ² - 7λ + 10
> = (λ - 2)(λ - 5) → λ₁ = 2, λ₂ = 5
>
> Autovectores:
> Para λ = 2: (A - 2I)·v = `[[2,1],[2,1]]`·v = 0 → v₁ = (1, -2)
> Para λ = 5: (A - 5I)·v = `[[-1,1],[2,-2]]`·v = 0 → v₂ = (1, 1)
>
> Verificación: A·(1,-2) = (2,-4) = 2·(1,-2) ✓
> A·(1,1) = (5,5) = 5·(1,1) ✓

### 3. Espacio propio

Para cada autovalor λ:
`E(λ) = {v | (A - λ·I)·v = 0} = Ker(A - λ·I)`

**Multiplicidad geométrica:** dim(E(λ))
- Siempre: 1 ≤ dim(E(λ)) ≤ multiplicidad algebraica
- Si son iguales para todos los λ → A es diagonalizable

```
Diagrama: Espacios propios en ℝ³

        E(λ₁) = gen{v₁}          E(λ₂) = gen{v₂, v₃}
        (recta, dim=1)           (plano, dim=2)
             │                         │
             │                         │
             v₁                      v₂───v₃
             │                         │
             │                         │
             ▼                         ▼
        Autovalor λ₁               Autovalor λ₂
        (simple)                   (doble, diagonalizable)

La suma de dimensiones = 3 = dim(ℝ³) → diagonalizable ✓
```

### 4. Propiedades

| Propiedad | Fórmula | Condición |
|---|---|---|
| Determinante | det(A) = ∏ λᵢ | siempre |
| Traza | tr(A) = ∑ λᵢ | siempre |
| Inversa | λ⁻¹ es autovalor de A⁻¹ | A invertible |
| Potencia | λᵏ es autovalor de Aᵏ | k ∈ ℕ |
| Polinomio | p(λ) autovalor de p(A) | p polinomio cualquiera |
| Traspuesta | mismos autovalores que A | siempre |
| Simétrica | todos λ ∈ ℝ | A = Aᵀ |
| Ortogonal | todos |λ| = 1 | Aᵀ = A⁻¹ |

> [!WARNING] **Errores comunes con autovalores:**
> 1. λ = 0 es "autovalor nulo" pero SÍ es válido → significa que A es singular
> 2. Si λ es autovalor de A, NO es cierto que 1/λ sea autovalor de A a secas → solo vale para A⁻¹
> 3. Los autovalores pueden ser complejos (matrices no simétricas) → los autovectores también serán complejos
> 4. El polinomio característico de A y Aᵀ es el mismo → mismos autovalores
> 5. Autovalores repetidos NO siempre significan que no se puede diagonalizar (ej: identidad)

---

## Parte 2: Diagonalización

### 1. Condiciones para diagonalizar

A (n×n) es **diagonalizable** si existe P invertible tal que:
`P⁻¹·A·P = D` (matriz diagonal)

**Condiciones equivalentes:**
1. A tiene n autovectores linealmente independientes
2. La suma de las dimensiones de los espacios propios = n
3. Para cada λ: mult. geométrica = mult. algebraica

### 2. Procedimiento

```
        ┌─────────────────────────────┐
        │   Encontrar autovalores     │
        │   det(A - λI) = 0           │
        └──────────┬──────────────────┘
                   ↓
        ┌─────────────────────────────┐
        │ Para cada λ: resolver       │
        │ (A - λI)·v = 0              │
        │ → espacio propio E(λ)       │
        └──────────┬──────────────────┘
                   ↓
        ┌─────────────────────────────┐
        │  Juntar autovectores        │
        │  como columnas de P         │
        └──────────┬──────────────────┘
                   ↓
        ┌─────────────────────────────┐
        │  D = diag(λ₁, λ₂, ..., λₙ) │
        │  Verificar: P⁻¹·A·P = D     │
        └─────────────────────────────┘
```

> [!EXAMPLE] **Ejemplo 3: Diagonalización de una matriz 3×3**
>
> A = `[[2, 0, 0], [0, 3, -1], [0, -1, 3]]`
>
> **Paso 1:** det(A - λI) = (2-λ)((3-λ)² - 1) = (2-λ)(λ² - 6λ + 8) = (2-λ)(λ-2)(λ-4)
> → λ₁ = 2 (doble), λ₂ = 4
>
> **Paso 2:** Espacios propios:
> - λ = 2: (A - 2I) = `[[0,0,0],[0,1,-1],[0,-1,1]]` → v₁ = (1,0,0), v₂ = (0,1,1)
> - λ = 4: (A - 4I) = `[[-2,0,0],[0,-1,-1],[0,-1,-1]]` → v₃ = (0,1,-1)
>
> **Paso 3:** P = `[[1,0,0],[0,1,1],[0,1,-1]]` → det(P) = -2 ≠ 0 ✓
>
> **Paso 4:** D = diag(2, 2, 4)
> Verificación: P⁻¹·A·P = D ✓ (multiplicidad geométrica = algebraica para todos)

### 3. Diagonalización ortogonal

Si A es **simétrica** → diagonalizable ortogonalmente:
`Qᵀ·A·Q = D` con Q ortogonal (Q⁻¹ = Qᵀ)

Las columnas de Q son una base **ortonormal** de autovectores.

> [!TIP] Cuando diagonalizás ortogonalmente, no necesitás calcular P⁻¹. Como Qᵀ = Q⁻¹, la verificación Qᵀ·A·Q = D es inmediata. Las matrices simétricas son el caso más importante en aplicaciones (PCA, mecánica, formas cuadráticas).

---

## Parte 3: Formas cuadráticas

### 1. Definición

Una **forma cuadrática** en ℝⁿ es:
`Q(x) = xᵀ·A·x = Σᵢⱼ aᵢⱼ·xᵢ·xⱼ`

donde A es una matriz **simétrica**.

**Ejemplo en ℝ²:** Q(x,y) = ax² + 2bxy + cy²

### 2. Clasificación

| Tipo | Condición (Q(x)) | Autovalores de A | Aplicación |
|---|---|---|---|
| **Definida positiva** | Q(x) > 0 ∀ x ≠ 0 | Todos λ > 0 | Mínimos (optimización) |
| **Definida negativa** | Q(x) < 0 ∀ x ≠ 0 | Todos λ < 0 | Máximos (optimización) |
| **Semidefinida positiva** | Q(x) ≥ 0 | Todos λ ≥ 0 | Fronteras de región factible |
| **Semidefinida negativa** | Q(x) ≤ 0 | Todos λ ≤ 0 | Fronteras de región factible |
| **Indefinida** | Cambia de signo | λ > 0 y λ < 0 | Puntos silla |

**Criterio de Sylvester:** todos los menores principales > 0 ⇔ definida positiva.

> [!WARNING] El criterio de Sylvester solo clasifica definida positiva. Para saber si es definida negativa, aplicá Sylvester a -A. Para semidefinida, los menores principales pueden ser cero y la clasificación requiere analizar autovalores.

### 3. Diagonalización de formas cuadráticas

Mediante cambio de variable ortogonal x = P·y:

`Q(x) = xᵀ·A·x = yᵀ·D·y = λ₁·y₁² + λ₂·y₂² + ... + λₙ·yₙ²`

Esto elimina los términos cruzados y revela la naturaleza de la cuádrica asociada.

```
Diagrama: Forma cuadrática en ℝ²

    Antes (con términos cruzados)     Después (diagonalizada)
         ┌───┐                           ┌───┐
         │ x │                           │ y₁│
    Q = [x y]·A·[x]ᵀ              Q = λ₁·y₁² + λ₂·y₂²
         │ y │
         └───┘
                                 Si λ₁>0, λ₂>0: elipse
                                 Si λ₁>0, λ₂<0: hipérbola
                                 Si λ₁=0: parábola
```

### 4. Aplicaciones

- **Clasificación de cuádricas** (AyG I)
- **Optimización:** Hessiana como forma cuadrática → clasificación de puntos críticos ([[Eje_Analisis_Matematico]])
- **Mínimos cuadrados** y análisis de datos
- **Mecánica:** momentos de inercia, tensiones principales

---

## Parte 4: Aplicaciones de ingeniería

### 4.1 Vibraciones mecánicas (sistemas masa-resorte)
Un sistema de masas acopladas tiene ecuación M·x'' + K·x = 0. Buscando soluciones x = v·e^(iωt):
`(K - ω²·M)·v = 0`
Las **frecuencias naturales** ω² son los autovalores del problema generalizado. Cada autovector v es un **modo normal de vibración**: una configuración donde todas las masas vibran a la misma frecuencia.

```
Ejemplo: 2 masas, 3 resortes

    k₁      m₁      k₂      m₂      k₃
   ──┬──────┬──────┬──────┬──────┬────
     │  ██  │      │  ██  │
     └──────┘      └──────┘
       x₁             x₂

Modo 1 (ω₁): masas en fase → ambos se mueven juntos
Modo 2 (ω₂): masas en contrafase → se separan y acercan
```

### 4.2 Análisis de componentes principales (PCA)
PCA busca las direcciones de máxima varianza en un conjunto de datos. Es la diagonalización de la matriz de covarianza Σ:
- Los autovalores de Σ son las **varianzas explicadas** por cada componente
- Los autovectores son las **direcciones principales**
- Se retienen las componentes con mayor λ (mayor varianza) → **reducción de dimensionalidad**

### 4.3 Ecuaciones diferenciales lineales
Un sistema de EDO lineales x' = A·x se resuelve diagonalizando A:
- Si A = P·D·P⁻¹, entonces x(t) = P·e^(Dt)·P⁻¹·x₀
- e^(Dt) = diag(e^(λ₁t), e^(λ₂t), ..., e^(λₙt))
- Los autovalores determinan el **comportamiento asintótico**:
  - Re(λ) < 0 → estable (decaimiento)
  - Re(λ) > 0 → inestable (crecimiento exponencial)
  - λ imaginario → oscilaciones

> [!TIP] Conexión clave: los autovalores determinan la estabilidad de sistemas dinámicos lineales. Esto conecta directamente con [[Anm_Ecuaciones_Diferenciales]]. La transformada de Laplace también usa polos (raíces del denominador) que son autovalores de la matriz del sistema. Ver [[Anm_Transformada_Laplace]].

### 4.4 Procesamiento de señales (filtros digitales)
Los autovalores de la matriz de un filtro digital determinan su respuesta en frecuencia. La **transformada z** y el análisis de polos-ceros usan el mismo concepto de valores propios.

### 4.5 Tensor de inercia (mecánica)
El tensor de inercia I (matriz 3×3 simétrica) relaciona velocidad angular ω con momento angular L = I·ω. Los autovectores de I son los **ejes principales de inercia** y los autovalores son los **momentos de inercia principales**.

---

## 5. Conexiones con otras áreas

| Conexión | Descripción | Wikilink |
|---|---|---|
| TL y diagonalización | Los autovalores vienen de una TL | [[Alg_Transformaciones_Lineales]] |
| Matrices | Determinante y traza como productos/sumas de λ | [[Alg_Matrices_Determinantes]] |
| EDO lineales | Solución de sistemas x' = A·x | [[Anm_Ecuaciones_Diferenciales]] |
| Transformada de Laplace | Polos de la función de transferencia = autovalores | [[Anm_Transformada_Laplace]] |
| Análisis II | Hessiana, clasificación de puntos críticos | [[Eje_Analisis_Matematico]] |
| Mecánica | Tensor de inercia, ejes principales | [[Eje_Fisica]] |
| Producto interno | Diagonalización ortogonal | [[Alg_Producto_Interno]] |
| Cambio de base | Matrices semejantes | [[Alg_Cambio_Base]] |

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U8 autovalores y autovectores.pdf` | Apunte Ariela: autovalores y autovectores |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/autovalores y autovectores.pdf` | Apunte Muñoz: autovalores y autovectores |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/formas cuadraticas.pdf` | Muñoz: formas cuadráticas |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf` | Larson Cap. 7: autovalores |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/6.- Álgebra Lineal (MathRocks) - Anton.pdf` | Anton Cap. 7: diagonalización |

## 📝 Ejercicios

### TPs
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP8 Autovalores y Autovectores.pdf|TP8 Autovalores (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°8 Autovalores y Autovectores.pdf|TP N°8 Autovalores]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica autovalores y autovectores_231129_104039.pdf|Práctica: autovalores]]

### Parciales y finales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/2do parcial AyGII 27-11-2023.pdf|2do parcial AyG II]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/recuperatorio segundo parcial AyGII .pdf|Recuperatorio 2do parcial]]

---

## Ejercicios modelados

### Ejercicio 1: Autovalores y autovectores de una matriz 3×3
Sea A = `[[1, -1, 0], [-1, 2, -1], [0, -1, 1]]`.
1. **a)** Hallar el polinomio característico.
2. **b)** Encontrar todos los autovalores.
3. **c)** Para cada λ, hallar el espacio propio.
4. **d)** ¿Es diagonalizable? Justificar.

**Guía:** El determinante da -λ(λ-1)(λ-3) = 0. Usar propiedades de suma de filas para simplificar.
**Respuesta:** λ = 0, 1, 3. v₀ = (1,1,1), v₁ = (1,0,-1), v₃ = (1,-2,1). Tres autovalores distintos → diagonalizable ✓.

### Ejercicio 2: Diagonalización con autovalor repetido
A = `[[1, 1, 0], [0, 2, 0], [0, 0, 2]]`.
1. **a)** Calcular autovalores y multiplicidades.
2. **b)** Hallar espacios propios.
3. **c)** Determinar si diagonaliza.

**Respuesta:** λ = 1 (simple, v₁ = (1,0,0)), λ = 2 (doble). Espacio propio E(2): resolver `[[-1,1,0],[0,0,0],[0,0,0]]`·v = 0 → v = t·(1,1,0) + s·(0,0,1). dim(E(2)) = 2 = multiplicidad algebraica → diagonalizable ✓.

### Ejercicio 3: Aplicación a EDO
Resolver el sistema x' = A·x con A = `[[2, 1], [1, 2]]` y x(0) = (3, 1).

**Guía:**
1. Diagonalizar A: λ₁ = 1, λ₂ = 3; v₁ = (1,-1), v₂ = (1,1)
2. P = `[[1,1],[-1,1]]`, D = diag(1, 3)
3. x(t) = P·e^(Dt)·P⁻¹·x₀

**Respuesta:** x₁(t) = 2e^t + e^(3t), x₂(t) = -2e^t + e^(3t). Para t → ∞, domina e^(3t). **Conexión:** esto es exactamente lo que se ve en [[Anm_Ecuaciones_Diferenciales]] con sistemas lineales.

### Ejercicio 4: Clasificar una forma cuadrática
Q(x,y,z) = 2x² + 2y² + 2z² + 2xy + 2xz + 2yz.

1. **a)** Escribir la matriz simétrica A.
2. **b)** Calcular los autovalores.
3. **c)** Clasificar la forma cuadrática.

**Guía:** A = `[[2,1,1],[1,2,1],[1,1,2]]`. El polinomio característico viene de det(A - λI).
**Respuesta:** λ = 1 (doble), λ = 4 (simple). Todos λ > 0 → **definida positiva** → representa un elipsoide en ℝ³.

### Ejercicio 5: PCA conceptual
Un conjunto de datos tiene matriz de covarianza Σ = `[[4, 2], [2, 3]]`.
1. **a)** Hallar los autovalores y autovectores de Σ.
2. **b)** ¿Qué porcentaje de la varianza total explica la primera componente?

**Guía:** Varianza total = tr(Σ) = 7. λ₁ = 5.83, λ₂ = 1.17.
**Respuesta:** La primera CP explica 5.83/7 ≈ 83.3%. El autovector principal es v₁ ≈ (0.85, 0.53) — la dirección de máxima varianza en los datos.

---

> [!WARNING] Autovalores y diagonalización son el **punto más alto** de la materia. Los usás en Análisis II (Hessiana, clasificación de puntos críticos), Física (momentos de inercia, vibraciones), Ecuaciones Diferenciales (sistemas lineales, estabilidad), Métodos Numéricos (el algoritmo de potencias) y en la práctica profesional. Dominá el polinomio característico y el procedimiento de diagonalización.
