> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Cambio_Base]] ← Anterior • Siguiente: [[Alg_Transformaciones_Lineales]]

# Producto Interno

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Cambio_Base]] (tema anterior)**
> **→ [[Alg_Transformaciones_Lineales]] (siguiente tema)**

También: [[Alg_Vectores]] | [[Eje_Fisica]] | [[Alg_Espacios_Vectoriales]] | [[Alg_Autovalores_Autovectores]]

---

## 1. Definición

Un **producto interno** es una función ⟨·,·⟩: V×V → ℝ que cumple:

1. **Lineal en 1er argumento:** ⟨au+bv, w⟩ = a⟨u,w⟩ + b⟨v,w⟩
2. **Simetría:** ⟨u,v⟩ = ⟨v,u⟩
3. **Definido positivo:** ⟨v,v⟩ ≥ 0, y ⟨v,v⟩ = 0 ⇔ v = 0

> [!WARNING] ¡No confundir! El producto interno NO es lo mismo que el producto escalar clásico. El producto escalar (o punto) en ℝⁿ es un caso particular de producto interno. Un producto interno puede definirse en cualquier espacio vectorial, incluso en ℙₙ (polinomios) o Mₘₓₙ (matrices).

> [!TIP] De las tres propiedades, la más importante para los cómputos es la linealidad en el primer argumento. La simetría permite "mover" términos en las cuentas. La positividad permite definir norma y ángulo.

> [!EXAMPLE] **Ejemplo 1: Producto interno en ℙ₂ (polinomios de grado ≤ 2)**
>
> Definimos ⟨p,q⟩ = ∫₋₁¹ p(x)q(x) dx para p,q ∈ ℙ₂.
>
> Verificación para p(x) = x y q(x) = 1 + x²:
>
> ⟨p,q⟩ = ∫₋₁¹ x·(1+x²) dx = ∫₋₁¹ (x + x³) dx = [x²/2 + x⁴/4]₋₁¹
> = (1/2 + 1/4) - (1/2 + 1/4) = 0

---

## 2. Ejemplos de productos internos

| Espacio | Producto interno usual | Observación |
|---|---|---|
| ℝⁿ | ⟨u,v⟩ = u₁v₁ + u₂v₂ + ... + uₙvₙ | Producto escalar (punto) |
| ℝⁿ (ponderado) | ⟨u,v⟩ = w₁u₁v₁ + ... + wₙuₙvₙ | Pesos wᵢ > 0 |
| ℙₙ | ⟨p,q⟩ = ∫ₐᵇ p(x)q(x) dx | Producto interno integral |
| ℙₙ (discreto) | ⟨p,q⟩ = Σᵢ p(xᵢ)q(xᵢ) | Evaluación en puntos |
| Mₘₓₙ | ⟨A,B⟩ = tr(AᵀB) | Traza del producto |
| C[a,b] | ⟨f,g⟩ = ∫ₐᵇ f(x)g(x) dx | Funciones continuas |

> [!EXAMPLE] **Ejemplo 2: Producto interno de matrices**
>
> Sean A = `[[1, 2], [3, 4]]` y B = `[[0, 1], [1, 0]]` en M₂ₓ₂.
>
> ⟨A,B⟩ = tr(AᵀB) = tr(`[[1,3],[2,4]]`·`[[0,1],[1,0]]`) = tr(`[[3,1],[4,2]]`) = 3 + 2 = 5
>
> Interpretación: mide qué tan "alineadas" están las matrices como vectores en ℝ⁴.

---

## 3. Norma inducida

`||v|| = √(⟨v,v⟩)`

Satisface:
- ||v|| ≥ 0
- ||c·v|| = |c|·||v||
- ||u+v|| ≤ ||u|| + ||v|| (desigualdad triangular)
- |⟨u,v⟩| ≤ ||u||·||v|| (desigualdad de Cauchy-Schwarz)

> [!WARNING] Cauchy-Schwarz es la desigualdad más usada en álgebra lineal:
> |⟨u,v⟩| ≤ ||u||·||v||
> La igualdad se da solo cuando u y v son **linealmente dependientes** (uno es múltiplo del otro). Sirve para acotar productos internos sin calcularlos explícitamente.

> [!TIP] La desigualdad de Cauchy-Schwarz es la razón por la que el ángulo está bien definido:
> |⟨u,v⟩|/(||u||·||v||) ≤ 1 → podemos definir cos θ = ⟨u,v⟩/(||u||·||v||)
> Si no existiera esta cota, ¡el "coseno" podría ser mayor que 1!

---

## 4. Ángulo y ortogonalidad

**Ángulo:** `cos θ = ⟨u,v⟩ / (||u||·||v||)`

**Ortogonalidad:** u ⟂ v si ⟨u,v⟩ = 0

**Teorema de Pitágoras:** si u ⟂ v → ||u+v||² = ||u||² + ||v||²

```
Diagrama: Descomposición ortogonal en ℝ²

            v
            ↑
            │ ⟨u,v⟩
        ────┼──────────→ u
            │
            │
            ▼ proy_u(v)

  ⟨u,v⟩ = 0  →  u ⟂ v  →  forman un ángulo recto
```

> [!WARNING] En espacios de funciones (ℙₙ, C[a,b]), la ortogonalidad depende del producto interno elegido. Dos polinomios pueden ser ortogonales con el producto integral pero no con el discreto. Siempre especificar qué producto interno se está usando.

---

## 5. Conjuntos ortogonales y ortonormales

**Ortogonal:** todos los vectores son ortogonales entre sí (⟨vᵢ, vⱼ⟩ = 0 si i ≠ j)
**Ortonormal:** ortogonal + cada vector tiene norma 1

**Ventajas de una base ortonormal:**
- Las coordenadas se calculan como ⟨v, bᵢ⟩
- La matriz de cambio de base es ortogonal (P⁻¹ = Pᵀ)
- La norma se preserva (‖P·v‖ = ‖v‖)
- Los cómputos son mucho más simples

> [!EXAMPLE] **Ejemplo 3: Polinomios de Legendre**
>
> En ℙₙ con producto interno ⟨p,q⟩ = ∫₋₁¹ p(x)q(x) dx, los **polinomios de Legendre** forman una base ortogonal:
>
> P₀(x) = 1
> P₁(x) = x
> P₂(x) = (3x² - 1)/2
> P₃(x) = (5x³ - 3x)/2
>
> Verificación: ∫₋₁¹ P₁(x)·P₂(x) dx = ∫₋₁¹ x·(3x²-1)/2 dx = (1/2)∫₋₁¹ (3x³ - x) dx = 0 ✓
>
> Se usan en métodos numéricos, series de Fourier-Legendre y análisis de vibraciones.

---

## 6. Proceso de Gram-Schmidt

Transforma cualquier base en una base **ortonormal**:

```
Entrada:           Salida:
{v₁, v₂, ..., vₙ}  {e₁, e₂, ..., eₙ}
(base cualquiera)   (base ortonormal)

Paso 1: u₁ = v₁
Paso 2: u₂ = v₂ - ⟨v₂, u₁⟩/⟨u₁,u₁⟩ · u₁
Paso 3: u₃ = v₃ - ⟨v₃, u₁⟩/⟨u₁,u₁⟩ · u₁ - ⟨v₃, u₂⟩/⟨u₂,u₂⟩ · u₂
   ...
Paso n: uₙ = vₙ - Σᵢ₌₁ⁿ⁻¹ ⟨vₙ, uᵢ⟩/⟨uᵢ,uᵢ⟩ · uᵢ

Final: normalizar eᵢ = uᵢ/||uᵢ|| para cada i
```

```
Diagrama: Gram-Schmidt en ℝ²

    v₂                    u₂ = v₂ - proy_{u₁}(v₂)
    ↑                     ↑
    │                     │  ⟂
    │  v₁  ⟶  u₁ = v₁    │     u₁ = v₁
    │                     │
    └─────────→           └─────────→

  Base original {v₁, v₂}    Base ortogonal {u₁, u₂}
  (no ortogonal)            (u₁ ⟂ u₂)
```

> [!EXAMPLE] **Ejemplo 4: Gram-Schmidt en ℝ³**
>
> Base original: v₁ = (1,1,0), v₂ = (1,0,1), v₃ = (0,1,1)
>
> **Paso 1:** u₁ = v₁ = (1,1,0), ||u₁|| = √2
>
> **Paso 2:** u₂ = v₂ - ⟨v₂,u₁⟩/⟨u₁,u₁⟩ · u₁
> ⟨v₂,u₁⟩ = 1·1 + 0·1 + 1·0 = 1
> ⟨u₁,u₁⟩ = 2
> u₂ = (1,0,1) - (1/2)·(1,1,0) = (1/2, -1/2, 1)
>
> **Paso 3:** u₃ = v₃ - ⟨v₃,u₁⟩/⟨u₁,u₁⟩·u₁ - ⟨v₃,u₂⟩/⟨u₂,u₂⟩·u₂
> ⟨v₃,u₁⟩ = 1, ⟨v₃,u₂⟩ = -1/2 + 0 + 1 = 1/2, ⟨u₂,u₂⟩ = 1/4+1/4+1 = 3/2
> u₃ = (0,1,1) - (1/2)·(1,1,0) - (1/2)/(3/2)·(1/2,-1/2,1)
> = (0,1,1) - (1/2,1/2,0) - (1/3)·(1/2,-1/2,1)
> = (0-1/2-1/6, 1-1/2+1/6, 1-0-1/3) = (-2/3, 2/3, 2/3)
>
> Normalizando: e₁ = (1,1,0)/√2, e₂ = (1,-1,2)/√6, e₃ = (-1,1,1)/√3

> [!TIP] El proceso de Gram-Schmidt es **numéricamente inestable** para vectores casi paralelos. En la práctica computacional se usa la **factorización QR** (equivalente pero más estable). La idea conceptual es la misma: ortogonalizar paso a paso.

---

## 7. Proyección ortogonal

**Proyección de v sobre un subespacio S:**
Si {u₁, …, uₖ} es base ortonormal de S:
`proy_S(v) = ⟨v,u₁⟩·u₁ + ⟨v,u₂⟩·u₂ + ... + ⟨v,uₖ⟩·uₖ`

**Complemento ortogonal:** S⟂ = {v ∈ V | ⟨v, s⟩ = 0 ∀ s ∈ S}

**Descomposición ortogonal:** V = S ⊕ S⟂ (todo vector se descompone únicamente como suma de una componente en S y otra en S⟂)

```
Diagrama: Proyección ortogonal en ℝ³

                    v
                   ↗
                  /                  S = plano XY
                 /                  (todo vector z=0)
                /
               /  proy_S(v) = (x,y,0)
              /  ↑
             /   |
     ───────/────┼──────────→  y
            /    |
           /     | v - proy_S(v) = (0,0,z) ∈ S⟂
          /      |
         /       ↓
        x

  Todo v ∈ ℝ³ se escribe como proy_S(v) + (v - proy_S(v))
  donde proy_S(v) ∈ S y el resto está en S⟂ (eje Z).
```

> [!WARNING] La proyección ortogonal sobre un subespacio es la **mejor aproximación** en el sentido de mínimos cuadrados: proy_S(v) es el vector de S más cercano a v. Esto es la base del método de **mínimos cuadrados** (regresión lineal).

---

## 8. Mínimos cuadrados

Cuando un sistema A·x = b no tiene solución (más ecuaciones que incógnitas), buscamos x que minimice ‖A·x - b‖²:

`Aᵀ·A·x = Aᵀ·b`  ← **Ecuaciones normales**

**Interpretación:** estamos proyectando b sobre el espacio columna de A. La solución x da la combinación lineal de columnas que mejor aproxima a b.

> [!EXAMPLE] **Ejemplo 5: Regresión lineal (recta de mínimos cuadrados)**
>
> Datos: (0,1), (1,2), (2,4). Buscar recta y = a + bx.
>
> Planteamos el sistema sobredeterminado:
> `[[1,0],[1,1],[1,2]]`·[a,b]ᵀ = [1,2,4]ᵀ   (3 ecuaciones, 2 incógnitas)
>
> Ecuaciones normales:
> AᵀA = `[[3,3],[3,5]]`,  Aᵀb = [7,10]ᵀ
>
> Resolver: `[[3,3],[3,5]]`·[a,b]ᵀ = [7,10]ᵀ
> → a = 5/6, b = 3/2
>
> Recta: y = 0.833 + 1.5x
>
> Verificar: ‖A·x - b‖² = ‖(0.833-1, 2.333-2, 3.833-4)‖² = 0.167² + 0.333² + 0.167² ≈ 0.167

---

## 9. Aplicaciones de ingeniería

### 9.1 Procesamiento de señales (bases ortonormales)
Las series de Fourier usan la base ortonormal {sen(nx), cos(nx)} con producto interno ⟨f,g⟩ = ∫₀²π f(x)g(x) dx. Las componentes de Fourier son las coordenadas en esta base ortonormal. La **transformada de Fourier** es una proyección sobre esta base.

### 9.2 Compresión de datos (JPEG)
La compresión JPEG usa la **transformada coseno discreta** (DCT), que es un cambio de base ortonormal en el espacio de imágenes 8×8 píxeles. Las componentes de alta frecuencia (coeficientes pequeños) se descartan, logrando compresión con pérdida mínima.

### 9.3 Mecánica cuántica
El producto interno de funciones de onda ⟨ψ|φ⟩ determina la probabilidad de transición entre estados. Las bases ortonormales (autoestados de energía) son la representación más conveniente.

### 9.4 Geolocalización y GPS
Los sistemas de coordenadas locales se ortogonalizan mediante Gram-Schmidt para evitar distorsiones en distancias y ángulos.

### 9.5 Machine Learning (kernel trick)
Los kernels (como el RBF o polinomial) definen productos internos en espacios de características de alta dimensión, permitiendo que algoritmos lineales (SVM, PCA) capturen relaciones no lineales en los datos originales.

> [!TIP] El producto interno y la ortogonalidad son el lenguaje natural para hablar de **aproximación**: proyectar un vector complicado sobre un subespacio manejable es la idea detrás de series de Fourier, regresión, compresión y reducción de dimensionalidad.

---

## 10. Conexiones con otras áreas

| Conexión | Descripción | Wikilink |
|---|---|---|
| Espacios vectoriales | El producto interno se define sobre EV | [[Alg_Espacios_Vectoriales]] |
| Vectores en ℝ²/ℝ³ | Producto escalar clásico | [[Alg_Vectores]] |
| Cambio de base | Bases ortonormales simplifican el cambio | [[Alg_Cambio_Base]] |
| Transformaciones lineales | TL preservan o no el producto interno | [[Alg_Transformaciones_Lineales]] |
| Autovalores | Diagonalización ortogonal de matrices simétricas | [[Alg_Autovalores_Autovectores]] |
| Análisis II | Ortogonalidad de funciones (Fourier) | [[Eje_Analisis_Matematico]] |
| Física | Trabajo como producto interno (F·dr) | [[Eje_Fisica]] |
| Probabilidad | Covarianza como producto interno | [[Eje_Analisis_Matematico]] |

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---|---|
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Ariela Garcés/U6 producto interno.pdf` | Apunte Ariela: producto interno |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría II/cursado Muñoz Santis/producto interno.pdf` | Apunte Muñoz: producto interno |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf` | Larson Cap. 5: ortogonalidad |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/1.- Álgebra Lineal (MathRocks) - Friedberg.pdf` | Friedberg Cap. 6: PI y ortogonalidad |

## 📝 Ejercicios

### TPs
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Muñoz Santis/TP6 Producto Interno.pdf|TP6 Producto Interno (Muñoz)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/TP N°6 Producto Interno.pdf|TP N°6 Producto Interno]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/cursado Ariela Garcés/TP 6.pdf|TP6 Producto Interno (Ariela)]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría II/Trabajos prácticos/Práctica/Práctica producto interno_231029_195916.pdf|Práctica: producto interno]]

---

## Ejercicios modelados

### Ejercicio 1: Verificar que es producto interno
Determinar si ⟨u,v⟩ = u₁v₁ - 2u₁v₂ - 2u₂v₁ + 5u₂v₂ define un producto interno en ℝ².

**Guía:** Verificar las tres propiedades. Para la positividad, escribir ⟨u,u⟩ = u₁² - 4u₁u₂ + 5u₂² = (u₁ - 2u₂)² + u₂².
**Respuesta:** SÍ es producto interno porque se puede escribir como suma de cuadrados ≥ 0 y = 0 solo si u₁ = u₂ = 0.

### Ejercicio 2: Gram-Schmidt en ℝ³
Aplicar Gram-Schmidt a v₁ = (1,2,-1), v₂ = (0,3,1), v₃ = (2,-1,0).

**Guía:** Seguir los pasos: u₁ = v₁; u₂ = v₂ - ⟨v₂,u₁⟩/⟨u₁,u₁⟩·u₁; u₃ = v₃ - ⟨v₃,u₁⟩/⟨u₁,u₁⟩·u₁ - ⟨v₃,u₂⟩/⟨u₂,u₂⟩·u₂. Luego normalizar.
**Respuesta:** Base ortonormal: e₁ = (1,2,-1)/√6, e₂ = (2,1,3)/√14, e₃ = (1,-1,-1)/√3.

### Ejercicio 3: Proyección ortogonal
Hallar la proyección de v = (3,4,5) sobre el subespacio S = gen{(1,1,0), (0,1,1)}.

**Guía:**
1. Ortogonalizar la base de S (Gram-Schmidt) o usar la fórmula directa con base no ortogonal.
2. proy_S(v) = suma de ⟨v,eᵢ⟩·eᵢ con base ortonormal de S.

**Respuesta:** Base ortonormal de S: e₁ = (1,1,0)/√2, e₂ = (-1,1,2)/√6.
proy_S(v) = (7/√2)·e₁ + (9/√6)·e₂ = (4, 5, 3). Verificar: (3,4,5) - (4,5,3) = (-1,-1,2) ⟂ S ✓.

### Ejercicio 4: Mínimos cuadrados (regresión cuadrática)
Ajustar un polinomio de grado 2 y = a + bx + cx² a los puntos: (-1, 0), (0, 1), (1, 2), (2, 9).

**Guía:** Armar sistema con Vandermonde y resolver ecuaciones normales AᵀA·x = Aᵀb.
**Respuesta:** y = 1 + 1.5x + 1.5x².
Verificar: en x=0 → 1 ✓, en x=1 → 4 (vs 2, aproximación), en x=-1 → 1 (vs 0).

### Ejercicio 5: Ortogonalidad de funciones
Verificar que f(x) = x y g(x) = x² - 1/3 son ortogonales en ℙ₂ con ⟨p,q⟩ = ∫₋₁¹ p(x)q(x) dx.

**Guía:** Calcular ∫₋₁¹ x·(x² - 1/3) dx.
**Respuesta:** ∫₋₁¹ (x³ - x/3) dx = [x⁴/4 - x²/6]₋₁¹ = (1/4-1/6) - (1/4-1/6) = 0 ✓

---

> [!NOTE] El producto interno es la generalización del producto escalar que viste en AyG I. La misma idea, aplicada a espacios vectoriales abstractos. Gram-Schmidt es uno de los algoritmos más útiles de todo el álgebra lineal. Con producto interno y ortogonalidad entendés desde regresión lineal hasta series de Fourier y compresión JPEG.
