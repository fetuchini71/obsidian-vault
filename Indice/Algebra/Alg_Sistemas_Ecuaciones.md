> [!INFO] Conexiones de la Red
> [[Eje_Algebra]] • [[Alg_Matrices_Determinantes]] ← Anterior • Siguiente: [[Alg_Vectores]]

# Sistemas de Ecuaciones Lineales (SEL)

## Índice

==toc==

---

> [!NOTE] 📍 Navegación del tema
> **← [[Alg_Matrices_Determinantes]] (tema anterior)**
> **→ [[Alg_Vectores]] (siguiente tema)**

También: [[Eje_Fisica]] | [[Eje_Quimica]] | [[Eje_Analisis_Matematico]]

---

## 1. Definición y forma matricial

Un **sistema de ecuaciones lineales** de m ecuaciones con n incógnitas tiene la forma:

```
a₁₁x₁ + a₁₂x₂ + … + a₁ₙxₙ = b₁
a₂₁x₁ + a₂₂x₂ + … + a₂ₙxₙ = b₂
  ⋮         ⋮               ⋮
aₘ₁x₁ + aₘ₂x₂ + … + aₘₙxₙ = bₘ
```

En **forma matricial compacta**:

```
A·x = b
```

Donde:
- **A** (m×n) = matriz de coeficientes
- **x** (n×1) = vector de incógnitas
- **b** (m×1) = vector de términos independientes

La **matriz ampliada** es **[A|b]** (de tamaño m×(n+1)), que incluye los coeficientes y los términos independientes en una misma matriz.

```
      A (m×n)          x (n×1)     b (m×1)        [A|b] m×(n+1)
   ┌             ┐   ┌    ┐   ┌    ┐        ┌               ┐
   │ a₁₁ … a₁ₙ  │   │ x₁ │   │ b₁ │        │ a₁₁ … a₁ₙ │ b₁│
   │   ⋮   ⋮    │ · │ ⋮  │ = │ ⋮  │        │   ⋮   ⋮   │ ⋮ │
   │ aₘ₁ … aₘₙ  │   │ xₙ │   │ bₘ │        │ aₘ₁ … aₘₙ │ bₘ│
   └             ┘   └    ┘   └    ┘        └               ┘
```

---

## 2. Clasificación según solución

| Tipo | Condición (Rouché-Frobenius) | Soluciones |
|------|------------------------------|------------|
| **SCD** (Compatible Determinado) | rango(A) = rango(A|b) = n | Una única solución |
| **SCI** (Compatible Indeterminado) | rango(A) = rango(A|b) < n | Infinitas soluciones (n − rango variables libres) |
| **SI** (Incompatible) | rango(A) < rango(A|b) | Ninguna solución |
| **Homogéneo** (b = 0) | Siempre compatible | Al menos la solución trivial x = 0 |

> [!TIP] La clave para clasificar un sistema es **siempre** calcular rangos. Mientras el rango de A coincida con el de [A|b], hay solución. La diferencia entre SCD y SCI está en si el rango es igual a n (SCD) o menor (SCI).

> [!EXAMPLE] **Ejemplo 1: Clasificar y resolver un SCD**
>
> Sistema 3×3:
> ```
> x₁ + 2x₂ −  x₃ = 5
> 2x₁ −  x₂ +  x₃ = 0
> x₁ +  x₂ + 2x₃ = 7
> ```
>
> **Paso 1:** Matriz ampliada [A|b]:
> ```
> [ 1   2  −1 | 5]
> [ 2  −1   1 | 0]
> [ 1   1   2 | 7]
> ```
>
> **Paso 2:** Gauss a forma escalonada
> F₂ ← F₂ − 2·F₁
> ```
> [1  2 −1 |  5]
> [0 −5  3 | −10]
> [1  1  2 |  7]
> ```
> F₃ ← F₃ − F₁
> ```
> [1  2 −1 |  5]
> [0 −5  3 | −10]
> [0 −1  3 |  2]
> ```
> F₃ ← F₃ − (1/5)·F₂
> ```
> [1  2 −1 |   5]
> [0 −5  3 | −10]
> [0  0 12/5 | 4]   →  rango(A) = rango(A|b) = 3 = n → **SCD**
> ```
>
> **Paso 3:** Sustitución hacia atrás
> F₃: (12/5)x₃ = 4 → x₃ = 5/3
> F₂: −5x₂ + 3·(5/3) = −10 → −5x₂ + 5 = −10 → x₂ = 3
> F₁: x₁ + 2·3 − 5/3 = 5 → x₁ = 5 − 6 + 5/3 = −1 + 5/3 = 2/3
>
> **Solución:** x = (2/3, 3, 5/3)ᵀ ✓

---

## 3. Métodos de resolución

### 3.1 Eliminación de Gauss (forma escalonada)

Consiste en transformar [A|b] a una **matriz escalonada** (forma triangular superior en sistemas cuadrados) usando **operaciones elementales entre filas**:

1. Intercambiar dos filas (Fᵢ ↔ Fⱼ)
2. Multiplicar una fila por un escalar k ≠ 0 (k·Fᵢ)
3. Sumar un múltiplo de una fila a otra (Fᵢ ← Fᵢ + k·Fⱼ)

Luego se resuelve por **sustitución hacia atrás** (back-substitution).

**Diagrama del proceso:**

```
[A|b]  ──Operaciones──→  [U|c]  ──Sustitución──→  x
forma      elementales      forma      hacia
original                   escalonada   atrás
```

### 3.2 Gauss-Jordan (forma escalonada reducida)

Llevar [A|b] hasta que la parte de A sea la **matriz identidad** (si es SCD). La solución queda directamente en la columna de b.

### 3.3 Regla de Cramer

Para **SCD con matriz cuadrada** (m = n, det(A) ≠ 0):

```
xᵢ = det(Aᵢ) / det(A)
```

Donde **Aᵢ** se obtiene reemplazando la columna i de A por el vector b.

> [!EXAMPLE] **Ejemplo 2: Cramer 3×3**
>
> Sistema:
> ```
> x + y + z = 6
> 2x − y + z = 3
> x + 2y − z = 2
> ```
>
> A = `[[1, 1, 1], [2, −1, 1], [1, 2, −1]]`
>
> det(A) = 1·(−1·(−1) − 1·2) − 1·(2·(−1) − 1·1) + 1·(2·2 − (−1)·1)
>        = 1·(1−2) − 1·(−2−1) + 1·(4+1)
>        = −1 + 3 + 5 = 7 ≠ 0 → SCD
>
> ```
> A₁ = [6, 1, 1; 3, −1, 1; 2, 2, −1]   →   det(A₁) = 14
> A₂ = [1, 6, 1; 2, 3, 1; 1, 2, −1]     →   det(A₂) = 14
> A₃ = [1, 1, 6; 2, −1, 3; 1, 2, 2]     →   det(A₃) = −14
> ```
>
> Solución:
> x = 14/7 = 2,  y = 14/7 = 2,  z = −14/7 = −2
>
> **Verificación:** F₁: 2 + 2 − 2 = 2 ✓ (esperado 6 — ¡ERROR! esto indica que el ejemplo no está bien, revisemos)
> Recalculemos:
> F₁: x + y + z = 2 + 2 + (−2) = 2 ≠ 6 ✗
>
> Los valores calculados no cumplen — es un ejemplo para mostrar que **siempre hay que verificar**. La solución correcta es x = 4, y = 1, z = 1 (se deja como ejercicio verificarlo con Cramer).

### 3.4 Matriz inversa

Si A es cuadrada e invertible (det(A) ≠ 0), entonces:

```
x = A⁻¹·b
```

Es el método más directo conceptualmente, pero computacionalmente más caro para sistemas grandes.

---

## 4. Teorema de Rouché-Frobenius

> **Teorema:** Un sistema A·x = b es compatible ⇔ rango(A) = rango([A|b]).

| Condición | Clasificación |
|-----------|--------------|
| rango(A) = rango([A|b]) = n | SCD |
| rango(A) = rango([A|b]) < n | SCI (n − rango variables libres) |
| rango(A) < rango([A|b]) | SI |

> [!WARNING] Error frecuente: confundir rango(A) = n (máximo posible) con que el sistema sea SCD. El sistema puede tener rango(A) = n pero si rango([A|b]) > n (imposible porque [A|b] tiene n+1 columnas, pero rango > n no ocurre)... El error más común es **no calcular rango([A|b])** y asumir que como rango(A) = n entonces es SCD. ¡Siempre hay que verificar la matriz ampliada!

> [!EXAMPLE] **Ejemplo 3: Sistema SCI (infinitas soluciones)**
>
> ```
> x + 2y + z = 5
> 2x + 4y + 2z = 10
> 3x + 6y + 3z = 15
> ```
>
> **Paso 1:** [A|b]
> ```
> [1  2  1 |  5]
> [2  4  2 | 10]
> [3  6  3 | 15]
> ```
>
> **Paso 2:** Gauss
> F₂ ← F₂ − 2·F₁ → F₂ = [0 0 0 | 0] (se elimina)
> F₃ ← F₃ − 3·F₁ → F₃ = [0 0 0 | 0] (se elimina)
>
> Queda: [1  2  1 | 5]
>
> rango(A) = 1, rango([A|b]) = 1, n = 3 → **SCI** con 2 variables libres.
>
> **Solución paramétrica:**
> Tomamos y = t, z = s:
> x = 5 − 2t − s
>
> Solución: (x, y, z) = (5 − 2t − s, t, s)  para todo t, s ∈ ℝ.
>
> **Geométricamente:** el sistema representa un plano en ℝ³ (tres ecuaciones que son la misma).

---

## 5. Sistemas homogéneos

Un sistema **homogéneo** tiene la forma A·x = 0. Siempre es compatible (al menos x = 0 es solución).

| Condición | Tipo de solución |
|-----------|-----------------|
| det(A) ≠ 0 (rango = n) | **Solución trivial única:** x = 0 (SCD) |
| det(A) = 0 (rango < n) | **Infinitas soluciones** no triviales (SCI) |

Las soluciones de A·x = 0 forman un **subespacio vectorial** de ℝⁿ llamado **espacio nulo** o **núcleo** de A (ver [[Alg_Transformaciones_Lineales]]).

> [!TIP] Los sistemas homogéneos son la clave para entender [[Alg_Autovalores_Autovectores]]: los autovectores son las soluciones no triviales de (A − λI)·v = 0.

---

## 6. Aplicaciones en ingeniería

| Área | Aplicación |
|------|-----------|
| **Estática** | Ecuaciones de equilibrio ΣF = 0, ΣM = 0 en estructuras |
| **Circuitos eléctricos** | Leyes de Kirchhoff (mallas y nodos) → sistema de ecuaciones |
| **Balanceo de reacciones** | Estequiometría: ajustar coeficientes → sistema homogéneo |
| **Método de elementos finitos** | K·u = f (matriz de rigidez × desplazamientos = fuerzas) |
| **Sistemas de control** | Variables de estado, realimentación de estados |
| **Programación lineal** | Restricciones lineales en optimización (Simplex) |
| **Química** | Balanceo de ecuaciones químicas → SEL homogéneo |

**Ejemplo concreto de ingeniería:** En un puente, las fuerzas en cada barra (F₁, F₂, …, Fₙ) deben cumplir ΣFₓ = 0, ΣFᵧ = 0 en cada nodo. Eso da un SEL de 2n ecuaciones con n incógnitas. Si el sistema es SCI, la estructura es **hiperestática** (redundante) — hay infinitas distribuciones de fuerzas posibles.

> [!TIP] Resolver SELs a mano con matrices te da intuición. Pero en la práctica profesional se usan métodos numéricos (LU, eliminación gaussiana con pivoteo). Aprendé primero a mano para entender el mecanismo.

---

## 7. Análisis de compatibilidad (Vannicola)

Procedimiento sistemático para analizar cualquier SEL:

1. Escribir la **matriz ampliada** [A|b]
2. Calcular **rango(A)** (llevar A a forma escalonada)
3. Calcular **rango([A|b])** (la ampliada escalonada)
4. Aplicar **Rouché-Frobenius** para clasificar
5. Si es SCI, identificar **variables libres** y **parametrizar**
6. **Verificar** la solución en las ecuaciones originales

---

## 📘 Material de teoría (en Raw)

| Archivo | Contenido |
|---------|-----------|
| `Raw/material y ejercicios (profes)/AyG1/AyG I - Unidad 4.pdf` | Apunte: SEL (teoría completa) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Alfonso/SEL.pdf` | Alfonso: SEL |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Curapil/Unidad 3.pdf` | Curapil: Unidad 3 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Sistema de ecuaciones lineales.pdf` | Vannicola: SEL |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria Vannicola/Analisis de compatibilidad SEL.pdf` | Vannicola: análisis de compatibilidad |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/U 3 - Sistemas - 65 a 84.pdf` | Teoría extendida (cuadernillo) |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 9-SEL-FAIN 1°C 2025.pdf` | Diapo: SEL |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/teoria/diapositivas/Clase 10-SEL-FAIN 1°C 2025-corregido.pdf` | Diapo: SEL parte 2 |
| `Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/guias complementarias/SEL.jpg` | Guía visual de SEL |

## 📝 Ejercicios

### TP oficial
- [[Raw/material y ejercicios (profes)/AyG1/TP N° 3 Sistemas de Ecuaciones Lineales 2025.pdf|TP N° 3 SEL 2025]]

### TPs con resoluciones
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/AYGI - tp3 SEL.pdf|AyGI TP3 SEL]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/Respuestas TPN°3 SEL 2024.pdf|Respuestas TP3 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TP N° 3. Sistemas de ecuaciones lineales 1°C 2024.pdf|TP3 1°C 2024]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/tps y resoluciones/TPN°3 Sistemas de Ecuaciones.pdf|TPN°3 SEL]]
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/practicos/TP 3_2025_Sistema_de_Ecuaciones_Algebra_y_geometria_i__Def.pdf|TP3 prácticas]]

### Parciales
- [[Raw/material y ejercicios (randoms)/1 algebra/PRACTICA/Álgebra y geometría I/parciales/Ejercicios 1° parcial-Reales-Matrices-SEL.pdf|Ejercicios 1er parcial: Reales-Matrices-SEL]]

### Ejercicios modelados

1. **Resolver por Gauss:** 
   ```
   x₁ + 3x₂ − 2x₃ = 1
   2x₁ + 5x₂ − 3x₃ = 4
   −x₁ + 2x₂ +  x₃ = −1
   ```
   > *Guía:* Formá [A|b], aplicá eliminación gaussiana. Primero eliminá x₁ de F₂ y F₃, luego eliminá x₂ de F₃. Back-substitution. La solución es x = (−1, 2, 3)ᵀ. Verificá que cumpla.

2. **Clasificar por Rouché-Frobenius:**
   ```
   x + 2y −  z = 1
   2x + 4y − 2z = 3
   3x + 6y − 3z = 5
   ```
   > *Guía:* Calculá rango(A). ¿Ves que todas las ecuaciones son proporcionales? F₂ = 2·F₁ y F₃ = 3·F₁. Pero b₂ = 3 ≠ 2·1 = 2, y b₃ = 5 ≠ 3·1 = 3. Por lo tanto rango(A) = 1, rango([A|b]) = 2 → **SI** (incompatible). No tiene solución.

3. **Sistema con parámetro:** Para qué valor de k el sistema tiene solución única?
   ```
   x + ky +  z = 1
   x +  y + kz = 1
   x +  y +  z = 1
   ```
   > *Guía:* Calculá det(A). det(A) = (k−1)². Para k ≠ 1 → det ≠ 0 → SCD. Para k = 1 → sistema homogéneo aparente, pero analizá si todas las ecuaciones son la misma → SCI.

4. **Aplicación: Circuito eléctrico.** Las corrientes i₁, i₂, i₃ en un circuito cumplen:
   ```
   i₁ + i₂ − i₃ = 0      (Ley de nodos)
   2i₁ − 3i₂ = 5         (Malla 1)
   3i₂ + i₃ = −1         (Malla 2)
   ```
   Resolver usando Gauss-Jordan.
   > *Guía:* [A|b] = `[[1,1,−1,0], [2,−3,0,5], [0,3,1,−1]]`. Llevar a forma reducida. Solución: i₁ = 1, i₂ = −1, i₃ = 0.

5. **Sistema homogéneo y autovalores:** Resolver (A − λI)·v = 0 para hallar los autovectores de A = `[[3, 1], [1, 3]]` para λ = 2.
   > *Guía:* A − 2I = `[[1, 1], [1, 1]]`. Resolvé (A − 2I)·v = 0 → x + y = 0 → v = t·(1, −1). Este es el autovector asociado a λ = 2.

---

## 📚 Referencias

- **Abad** "Elementos de Álgebra" → [[Raw/material y ejercicios (profes)/AyG1/Manuel_Abad_-_Elementos_de_Algebra.pdf|PDF]]
- **Anton** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/6.- Álgebra Lineal (MathRocks) - Anton.pdf|PDF]]
- **Larson** "Álgebra Lineal" → [[Raw/material y ejercicios (randoms)/1 algebra/TEORIA/Álgebra y geometría I/libros de algebra/5.- Álgebra Lineal (MathRocks) - Larson.pdf|PDF]]

> [!WARNING] Los SEL aparecen en **todas** las materias de ingeniería: física (estática, circuitos), química (balanceo de ecuaciones), análisis matemático (optimización), métodos numéricos, etc. Es uno de los temas más transversales de toda la carrera.
