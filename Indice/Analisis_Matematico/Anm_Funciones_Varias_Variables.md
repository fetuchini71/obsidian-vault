> [!NOTE] Navegación
> **Anterior:** [[Anm_Sucesiones_Series]] • **Siguiente:** [[Anm_Derivadas_Parciales]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.
>
> ⚠️ **Requisito**: tener claros los conceptos de vectores y geometría en ℝ³ (ver [[Eje_Algebra]] — [[Alg_Vectores]] y [[Alg_Rectas_Plano]]).

# Funciones de Varias Variables

## Índice

==toc==

---

> [!INFO]
> Pasamos de $y = f(x)$ a $z = f(x,y)$ y $w = f(x,y,z)$. El mundo real tiene más de una dimensión — temperatura en un punto del espacio, presión en un fluido, potencial eléctrico. En ingeniería, TODO depende de múltiples variables: la tensión en un puente depende de la posición $(x,y,z)$ y del tiempo $t$; el campo de velocidades del viento también.

---

## Curvas paramétricas y ecuaciones polares

Una curva paramétrica en ℝ²: $(x(t), y(t))$ con $t \in [a,b]$.

Vector tangente: $\mathbf{r}'(t) = (x'(t), y'(t))$

**Longitud de arco** de una curva paramétrica:
$$L = \int_a^b \|\mathbf{r}'(t)\| \, dt = \int_a^b \sqrt{(x'(t))^2 + (y'(t))^2} \, dt$$

> [!EXAMPLE] Longitud de una hélice
> Calcular la longitud de una vuelta de la hélice $\mathbf{r}(t) = (\cos t, \sin t, t)$ para $t \in [0, 2\pi]$.
>
> **Solución:**
> $\mathbf{r}'(t) = (-\sin t, \cos t, 1)$
> $\|\mathbf{r}'(t)\| = \sqrt{(-\sin t)^2 + (\cos t)^2 + 1^2} = \sqrt{1 + 1} = \sqrt{2}$
> $L = \int_0^{2\pi} \sqrt{2} \, dt = 2\pi\sqrt{2}$
>
> La hélice da una vuelta completa y sube $2\pi$ en $z$, la longitud es $2\pi\sqrt{2}$.

---

## Funciones de varias variables

- $f: \mathbb{R}^n \to \mathbb{R}$ asigna un escalar a cada punto en ℝⁿ
- **Dominio**: conjunto de puntos donde $f$ está definida
- **Gráfica**: conjunto $\{(x,y,f(x,y))\} \subset \mathbb{R}^3$ — es una **superficie**
- **Curvas de nivel**: $f(x,y) = c$ — proyecciones en el plano $xy$
- **Superficies de nivel**: $f(x,y,z) = c$ — para funciones de 3 variables

> [!TIP] Visualizar funciones de 2 variables
> Pensá en la gráfica como una **sábana** sobre el plano $xy$. Las curvas de nivel son como las curvas de altitud de un mapa topográfico: donde están muy juntas, la pendiente es empinada; donde están separadas, la superficie es plana.

```
          z
          ▲
          │   /‾‾‾‾‾‾\
          │  /         \      ← superficie z = f(x,y)
          │ /           \
          │/_____________\___► y
         /              /
        /   curvas de  /
       /   nivel en   /
      /   el plano   /
     /     xy       /
    /              /
   /______________/ ► x
```

### Dominio de funciones de varias variables

El dominio se describe típicamente como una **región** en ℝ² o ℝ³:

| Tipo de restricción | Ejemplo | Dominio |
|:--------------------|:--------|:--------|
| Denominador no nulo | $f(x,y) = \frac{1}{x-y}$ | $x \neq y$ (recta excluida) |
| Raíz par | $f(x,y) = \sqrt{1 - x^2 - y^2}$ | $x^2 + y^2 \leq 1$ (disco) |
| Logaritmo | $f(x,y) = \ln(x + y)$ | $x + y > 0$ (semiplano) |

> [!WARNING] Errores comunes con el dominio
> **Error:** Confundir $x^2 + y^2 \leq 1$ (disco **lleno**) con $x^2 + y^2 = 1$ (**solo el borde**). El dominio de $\sqrt{1 - x^2 - y^2}$ es todo el disco, no solo la circunferencia. El dominio de $\frac{1}{\sqrt{1 - x^2 - y^2}}$ es el **interior** del disco ($x^2 + y^2 < 1$), porque en el borde el denominador se anula.

---

## Coordenadas polares, cilíndricas y esféricas

| Coordenadas | Relación con cartesianas |
|-------------|-------------------------|
| **Polares**: $(r,\theta)$ | $x = r\cos\theta$, $y = r\sin\theta$, $r = \sqrt{x^2+y^2}$ |
| **Cilíndricas**: $(r,\theta,z)$ | $x = r\cos\theta$, $y = r\sin\theta$, $z = z$ |
| **Esféricas**: $(\rho,\theta,\phi)$ | $x = \rho\sin\phi\cos\theta$, $y = \rho\sin\phi\sin\theta$, $z = \rho\cos\phi$ |

### Relación entre sistemas

```
Cartesianas (x,y,z)          Cilíndricas (r,θ,z)          Esféricas (ρ,θ,φ)
                              ┌─ r = √(x²+y²)             ┌─ ρ = √(x²+y²+z²)
(x,y,z) ──────────────────► (r,θ,z) ──────────────────► (ρ,θ,φ)
                              └─ θ = atan2(y,x)           └─ φ = arccos(z/ρ)
```

> [!TIP] Cuándo usar cada sistema
> - **Polares/cilíndricas**: regiones con simetría circular (círculos, cilindros, conos)
> - **Esféricas**: regiones con simetría esférica (esferas, semiesferas, cascos esféricos)
> - Pregunta guía: "¿la región es más fácil de describir con $r$ y $\theta$ o con $x$ e $y$?"

### Ecuaciones notables en coordenadas polares

| Figura | Ecuación polar |
|:-------|:---------------|
| Circunferencia radio $a$, centro origen | $r = a$ |
| Circunferencia radio $a$, centro $(a,0)$ | $r = 2a\cos\theta$ |
| Circunferencia radio $a$, centro $(0,a)$ | $r = 2a\sin\theta$ |
| Cardioide | $r = a(1 \pm \cos\theta)$ |
| Rosa de 4 pétalos | $r = a\sin(2\theta)$ |
| Espiral de Arquímedes | $r = a\theta$ |

---

## Límite y continuidad en ℝⁿ

$$\lim_{(x,y)\to(a,b)} f(x,y) = L$$

- El límite debe ser el mismo **por cualquier camino**
- Si por dos caminos distintos obtenés límites diferentes → el límite **no existe**

**Continuidad**: $\displaystyle \lim_{(x,y)\to(a,b)} f(x,y) = f(a,b)$

> [!EXAMPLE] Demostrar que un límite NO existe
> Verificar que $\displaystyle \lim_{(x,y)\to(0,0)} \frac{x^2}{x^2 + y^2}$ no existe.
>
> **Solución:**
> **Camino 1** — eje $x$ ($y=0$):
> $\displaystyle \lim_{x\to 0} \frac{x^2}{x^2 + 0} = \lim_{x\to 0} 1 = 1$
>
> **Camino 2** — eje $y$ ($x=0$):
> $\displaystyle \lim_{y\to 0} \frac{0}{0 + y^2} = \lim_{y\to 0} 0 = 0$
>
> Como $1 \neq 0$, el límite **no existe**.
>
> [!WARNING] Cuidado con caminos rectos
> Que todos los caminos rectos den el mismo límite **no es suficiente**. Hay que verificar también caminos curvos ($y=x^2$, $y=x^3$, etc.). Ejemplo clásico: $\frac{x^2y}{x^4+y^2}$ tiene límite 0 por cualquier recta, pero por $y=x^2$ el límite es $\frac{1}{2}$.

### Técnicas para calcular límites en ℝⁿ

| Técnica | Cuándo usarla | Ejemplo |
|:--------|:--------------|:--------|
| Sustitución directa | Función continua en el punto | $\lim_{(x,y)\to(1,2)} (x+y) = 3$ |
| Coordenadas polares | Límite en $(0,0)$ con expresiones $x^2+y^2$ | $\lim_{r\to 0} \frac{r^2\cos^2\theta}{r^2} = \cos^2\theta$ (depende de $\theta$ → no existe) |
| Teorema del sandwich | Función acotada × algo que tiende a 0 | $\left\|\frac{x^2y}{x^2+y^2}\right\| \leq \frac{x^2\|y\|}{x^2} = \|y\| \to 0$ |

> [!TIP] Estrategia para límites
> 1. **Primero**: probar sustitución directa (si la función es continua, listo)
> 2. **Segundo**: si hay indeterminación, probar caminos rectos ($y=mx$)
> 3. **Tercero**: si todos los caminos rectos coinciden, probar caminos curvos ($y=x^2$, $y=x^3$)
> 4. **Cuarto**: usar el teorema del sandwich o coordenadas polares
> 5. Si ningún camino da distinto, probablemente el límite existe — hay que acotar

---

## Superficies cuádricas comunes

Son las análogas 3D de las cónicas en 2D. Aparecen al graficar funciones de dos variables.

| Superficie | Ecuación (forma canónica) | Aspecto |
|:-----------|:--------------------------|:--------|
| **Paraboloide elíptico** | $z = \frac{x^2}{a^2} + \frac{y^2}{b^2}$ | Tazón hacia arriba/abajo |
| **Paraboloide hiperbólico** | $z = \frac{x^2}{a^2} - \frac{y^2}{b^2}$ | Silla de montar |
| **Cono elíptico** | $\frac{x^2}{a^2} + \frac{y^2}{b^2} = \frac{z^2}{c^2}$ | Dos conos opuestos |
| **Hiperboloide de una hoja** | $\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = 1$ | "Torre" con cintura |
| **Hiperboloide de dos hojas** | $-\frac{x^2}{a^2} - \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$ | Dos "tazones" separados |
| **Elipsoide** | $\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$ | Esfera achatada/estirada |

---

## Conexiones con otras áreas

- **[[Alg_Vectores]]**: producto escalar, norma, vectores en ℝ³ — base para parametrizar curvas
- **[[Alg_Rectas_Plano]]**: ecuaciones de rectas y planos — necesarias para plano tangente más adelante
- **[[Anm_Derivadas_Parciales]]**: el paso siguiente — ahora que describimos superficies, vamos a derivarlas
- **[[Anm_Limites_Continuidad]]** (Análisis I): el concepto de límite se extiende a ℝⁿ
- **Física**: campos de temperatura $T(x,y,z)$, presión $P(x,y,z,t)$, potencial $V(x,y,z)$

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Clase 1 — FVV (David Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 1-ING-FVV_...pdf` |
| Curvas paramétricas (teoría) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Ecuaciones Param y Vectoriales.pdf` |
| Coordenadas polares (teoría) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/coord polares1.pdf` |
| Gráficos polares | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Gráficos Polares.pdf` |
| Funciones y Superficies | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Funciones y Superficies.pdf` |
| Límites y continuidad (David Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Limites y continuidad.pdf` |
| U1 Curvas y superficies de nivel (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U1 Curvas y superficies de nivel.pdf` |
| U2 Límite y continuidad (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U2 Límite y continuidad.pdf` |
| Apunte ecuaciones paramétricas y polares | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/Apunte Ecuaciones paramétricas y polares.pdf` |
| TP1 Funciones paramétricas | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP1 Funciones Parametricas.pdf` |
| TP2 Curvas y superficies de nivel | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP2 Curvas y superficies de nivel.pdf` |
| TP3 Límite y Continuidad | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP3 Limite y Continuidad.pdf` |

---

## Ejercicios modelados

1. **Curvas paramétricas**: Hallar la ecuación cartesiana de la curva $x = 2\cos t$, $y = 2\sin t$, $t \in [0,2\pi]$.
2. **Dominio**: Determinar y dibujar el dominio de $f(x,y) = \sqrt{y - x^2} + \ln(x)$.
3. **Límites**: Calcular $\displaystyle \lim_{(x,y)\to(0,0)} \frac{xy}{x^2 + y^2}$ (respuesta: no existe) y $\displaystyle \lim_{(x,y)\to(0,0)} \frac{x^2 y}{x^2 + y^2}$ (respuesta: 0).
4. **Curvas de nivel**: Dibujar curvas de nivel de $f(x,y) = x^2 + y^2$ para $c = 0, 1, 4, 9$.

> [!NOTE] 📍 Navegación del tema
> **Tema anterior:** [[Anm_Sucesiones_Series]]
> **Tema siguiente:** [[Anm_Derivadas_Parciales]]

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Sucesiones_Series]] • **Siguiente:** [[Anm_Derivadas_Parciales]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
