> [!NOTE] Navegación
> **Anterior:** [[Anm_Campos_Integrales_Linea]] • **Siguiente:** [[Anm_Ecuaciones_Diferenciales]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Integrales de Superficie y Teoremas

## Índice

==toc==

---

> [!INFO]
> Pasamos de integrar sobre curvas a integrar sobre **superficies**. Los teoremas de Stokes y Gauss (divergencia) son los equivalentes en 3D del teorema de Green — conectan integrales de superficie con integrales de volumen y de línea. En ingeniería: calcular el flujo de un campo electromagnético a través de una superficie, el caudal de un fluido, el flujo de calor a través de una pared.

---

## Integral de superficie (campo escalar)

$$ \iint_S f(x,y,z) \, dS = \iint_D f(\mathbf{r}(u,v)) \, \|\mathbf{r}_u \times \mathbf{r}_v\| \, dA $$

**Interpretación**: masa de una lámina curva con densidad $f$.

**Elemento de área**: $dS = \|\mathbf{r}_u \times \mathbf{r}_v\| \, du \, dv$

> [!TIP] Cómo parametrizar una superficie
> | Superficie | Parametrización natural |
> |:-----------|:------------------------|
> | **Gráfica $z = g(x,y)$** | $\mathbf{r}(x,y) = (x, y, g(x,y))$ |
> | **Cilindro $x^2+y^2=a^2$** | $\mathbf{r}(\theta,z) = (a\cos\theta, a\sin\theta, z)$ |
> | **Esfera $x^2+y^2+z^2=a^2$** | $\mathbf{r}(\theta,\phi) = (a\sin\phi\cos\theta, a\sin\phi\sin\theta, a\cos\phi)$ |
> | **Cono $z = \sqrt{x^2+y^2}$** | $\mathbf{r}(r,\theta) = (r\cos\theta, r\sin\theta, r)$ |

> [!EXAMPLE] Masa de una superficie curva
> Hallar la masa del casquete esférico $x^2 + y^2 + z^2 = a^2$ con $z \geq 0$, si la densidad superficial es $\rho(x,y,z) = z^2$.
>
> **Solución:**
>
> **Paso 1** — Parametrización esférica:
> $\mathbf{r}(\theta,\phi) = (a\sin\phi\cos\theta, a\sin\phi\sin\theta, a\cos\phi)$
> $0 \leq \theta \leq 2\pi$, $0 \leq \phi \leq \pi/2$
>
> **Paso 2** — Norma del producto vectorial:
> $\mathbf{r}_\theta = (-a\sin\phi\sin\theta, a\sin\phi\cos\theta, 0)$
> $\mathbf{r}_\phi = (a\cos\phi\cos\theta, a\cos\phi\sin\theta, -a\sin\phi)$
> $\|\mathbf{r}_\theta \times \mathbf{r}_\phi\| = a^2\sin\phi$
>
> **Paso 3** — Masa:
> $\rho = z^2 = (a\cos\phi)^2 = a^2\cos^2\phi$
>
> $m = \iint_S z^2 \, dS = \int_0^{2\pi} \int_0^{\pi/2} a^2\cos^2\phi \cdot a^2\sin\phi \, d\phi \, d\theta$
> $= a^4 \int_0^{2\pi} d\theta \int_0^{\pi/2} \cos^2\phi \sin\phi \, d\phi$
> $= a^4 \cdot 2\pi \cdot \left[-\frac{\cos^3\phi}{3}\right]_0^{\pi/2} = 2\pi a^4 \cdot \frac{1}{3} = \frac{2\pi a^4}{3}$

---

## Integral de superficie (campo vectorial — flujo)

$$ \iint_S \mathbf{F} \cdot d\mathbf{S} = \iint_S \mathbf{F} \cdot \mathbf{n} \, dS $$

**Interpretación**: **flujo** del campo $\mathbf{F}$ a través de la superficie $S$ (cuánto "atraviesa" la superficie).

**Orientación**: $d\mathbf{S} = \mathbf{n} \, dS = \pm (\mathbf{r}_u \times \mathbf{r}_v) \, du \, dv$

```
           Flujo a través de una superficie
           
                ████████████
              ██  ↑   ↑   ██        ← Campo F (flechas)
             █   ↑   ↑   ↑  █
            █   ↑   ↑   ↑   █        ← Superficie S
            █   ↑   ↑   ↑   █
            █   ↑   ↑   ↑   █
             █   ↑   ↑   ↑  █
              ██ ↑   ↑   ██
                ████████████
                
   Flujo = ∫∫ F·n dS = ∑ (componente normal × área)
```

> [!WARNING] Orientación de la superficie
> El signo del flujo depende de la orientación (qué lado de la superficie consideramos "exterior").
> - **Superficie cerrada**: por convención, $\mathbf{n}$ apunta hacia **afuera**
> - **Superficie abierta**: la orientación se elige según el problema
> - **Error común**: olvidar que $d\mathbf{S}$ NO es un escalar — es un **vector** con dirección normal

> [!EXAMPLE] Flujo a través de una superficie
> Calcular $\iint_S \mathbf{F} \cdot d\mathbf{S}$ para $\mathbf{F}(x,y,z) = (0,0,z)$ a través de la superficie del cubo $[0,1] \times [0,1] \times [0,1]$, con normal exterior.
>
> **Solución:**
>
> El cubo tiene 6 caras. Sobre cada cara, $\mathbf{F} \cdot \mathbf{n}$ es constante o se simplifica:
>
> | Cara | $\mathbf{n}$ | $\mathbf{F} \cdot \mathbf{n}$ | Flujo parcial |
> |:-----|:------------:|:----------------------------:|:-------------:|
> | $x=0$ | $(-1,0,0)$ | $0$ | $0$ |
> | $x=1$ | $(1,0,0)$ | $0$ | $0$ |
> | $y=0$ | $(0,-1,0)$ | $0$ | $0$ |
> | $y=1$ | $(0,1,0)$ | $0$ | $0$ |
> | $z=0$ | $(0,0,-1)$ | $0$ | $0$ |
> | $z=1$ | $(0,0,1)$ | $1$ | $\iint 1 \, dA = 1$ |
>
> **Resultado:** flujo total = 1.
>
> **Interpretación:** el campo $\mathbf{F} = (0,0,z)$ solo tiene componente vertical. El flujo neto hacia afuera es 1 porque solo la cara superior contribuye. Esto puede verificarse con el teorema de la divergencia: $\nabla \cdot \mathbf{F} = 1$, $\iiint_V 1 \, dV = 1$. ✓

---

## Teorema de Stokes

Conecta la integral de superficie del **rotor** de un campo con la integral de línea del campo sobre el borde:

$$ \oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_S (\nabla \times \mathbf{F}) \cdot d\mathbf{S} $$

**Interpretación**: la circulación del campo alrededor del borde $C$ es igual al flujo del rotor a través de la superficie $S$.

```
Stokes: ∮ F·dr = ∬ (∇×F)·dS

  z
  ▲
  │       ╱╲    Superficie S
  │      ╱  ╲        con bord
  │     ╱    ╲         ↕
  │    ╱      ╲
  │   ╱        ╲      Curva C (borde de S)
  │  ╱          ╲
  │ ╱            ╲
  │╱______________╲___► y
  └──────────────────► x
```

> [!TIP] Cuándo usar Stokes
> Stokes es útil cuando:
> 1. La integral de línea es complicada pero el rotor es simple
> 2. Querés calcular una integral de superficie de un rotor sin parametrizar la superficie
> 3. Tenés una curva cerrada y cualquier superficie que tenga esa curva como borde sirve
>
> **Estrategia**: elegí la superficie más simple que tenga a $C$ como borde. Para una curva plana, usá el propio plano.

> [!EXAMPLE] Aplicar Stokes
> Calcular $\oint_C \mathbf{F} \cdot d\mathbf{r}$ donde $\mathbf{F} = (y, -x, z)$ y $C$ es la circunferencia $x^2 + y^2 = 1$, $z = 0$ orientada positivamente.
>
> **Solución:**
>
> **Paso 1** — Calcular el rotor:
> $\nabla \times \mathbf{F} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ \partial_x & \partial_y & \partial_z \\ y & -x & z \end{vmatrix} = (0-0, 0-0, -1-1) = (0,0,-2)$
>
> **Paso 2** — Elegir superficie: el disco $x^2 + y^2 \leq 1$, $z = 0$, con normal $\mathbf{n} = (0,0,1)$ (hacia arriba).
>
> **Paso 3** — Aplicar Stokes:
> $\displaystyle \oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_S (0,0,-2) \cdot (0,0,1) \, dS = \iint_S -2 \, dS = -2 \cdot \text{área}(S) = -2\pi$
>
> **Verificación directa:** parametrizando $C$: $\mathbf{r}(t) = (\cos t, \sin t, 0)$, $\mathbf{F} = (\sin t, -\cos t, 0)$, $\mathbf{r}' = (-\sin t, \cos t, 0)$. Producto: $-\sin^2 t - \cos^2 t = -1$. Integral: $\int_0^{2\pi} -1 \, dt = -2\pi$. ✓

---

## Teorema de la divergencia (Gauss)

Conecta la integral de superficie del campo con la integral de volumen de su divergencia:

$$ \iint_S \mathbf{F} \cdot d\mathbf{S} = \iiint_V (\nabla \cdot \mathbf{F}) \, dV $$

**Interpretación**: el flujo neto hacia afuera de una superficie cerrada es igual a la integral de la divergencia dentro del volumen.

> [!WARNING] Superficie cerrada vs. abierta
> Gauss se aplica **solo** a superficies **cerradas** (que encierran un volumen). Para superficies abiertas, usás Stokes o calculás directamente. Error común: aplicar Gauss a una semiesfera sin su tapa.

> [!EXAMPLE] Aplicar el teorema de la divergencia
> Calcular el flujo de $\mathbf{F} = (x^3, y^3, z^3)$ a través de la esfera $x^2 + y^2 + z^2 = a^2$.
>
> **Solución:**
>
> **Paso 1** — Calcular la divergencia:
> $\nabla \cdot \mathbf{F} = \frac{\partial}{\partial x}(x^3) + \frac{\partial}{\partial y}(y^3) + \frac{\partial}{\partial z}(z^3) = 3x^2 + 3y^2 + 3z^2 = 3(x^2 + y^2 + z^2)$
>
> **Paso 2** — Aplicar Gauss:
> $\displaystyle \iint_S \mathbf{F} \cdot d\mathbf{S} = \iiint_V 3(x^2 + y^2 + z^2) \, dV$
>
> **Paso 3** — Usar coordenadas esféricas:
> $x^2 + y^2 + z^2 = \rho^2$, $dV = \rho^2\sin\phi \, d\rho \, d\theta \, d\phi$
> $0 \leq \rho \leq a$, $0 \leq \theta \leq 2\pi$, $0 \leq \phi \leq \pi$
>
> $\displaystyle = 3 \int_0^{2\pi} \int_0^\pi \int_0^a \rho^2 \cdot \rho^2\sin\phi \, d\rho \, d\phi \, d\theta$
> $\displaystyle = 3 \int_0^{2\pi} d\theta \int_0^\pi \sin\phi \, d\phi \int_0^a \rho^4 \, d\rho$
> $\displaystyle = 3 \cdot (2\pi) \cdot (2) \cdot \left(\frac{a^5}{5}\right) = \frac{12\pi a^5}{5}$
>
> Sin Gauss, habría que parametrizar la esfera y calcular la integral de superficie — mucho más trabajo.

---

## Operadores diferenciales

| Operador | Definición | Símbolo | Resultado |
|:---------|:-----------|:-------:|:---------:|
| **Gradiente** | $\nabla f = (f_x, f_y, f_z)$ | $\nabla$ | Vector |
| **Divergencia** | $\nabla \cdot \mathbf{F} = P_x + Q_y + R_z$ | $\nabla \cdot$ | Escalar |
| **Rotor** | $\nabla \times \mathbf{F} = (R_y - Q_z, P_z - R_x, Q_x - P_y)$ | $\nabla \times$ | Vector |
| **Laplaciano** | $\nabla^2 f = f_{xx} + f_{yy} + f_{zz}$ | $\nabla^2$ | Escalar |

### Identidades vectoriales útiles

1. $\nabla \times (\nabla f) = \mathbf{0}$ (el rotor de un gradiente es cero — campos conservativos)
2. $\nabla \cdot (\nabla \times \mathbf{F}) = 0$ (la divergencia de un rotor es cero)
3. $\nabla \times (\nabla \times \mathbf{F}) = \nabla(\nabla \cdot \mathbf{F}) - \nabla^2\mathbf{F}$
4. $\nabla \cdot (f\mathbf{F}) = f\nabla \cdot \mathbf{F} + \nabla f \cdot \mathbf{F}$

### Tabla resumen de teoremas

| Teorema | Conecta | Fórmula |
|:--------|:--------|:--------|
| **Green** (circulación) | Integral de línea ↔ Integral doble | $\oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_R (Q_x - P_y) \, dA$ |
| **Green** (flujo) | Integral de línea ↔ Integral doble | $\oint_C \mathbf{F} \cdot \mathbf{n} \, ds = \iint_R (P_x + Q_y) \, dA$ |
| **Stokes** | Integral de línea ↔ Integral de superficie | $\oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_S (\nabla \times \mathbf{F}) \cdot d\mathbf{S}$ |
| **Gauss** (divergencia) | Integral de superficie ↔ Integral triple | $\iint_S \mathbf{F} \cdot d\mathbf{S} = \iiint_V (\nabla \cdot \mathbf{F}) \, dV$ |

```
Teoremas del cálculo vectorial (jerarquía):

    Análisis I:       ∫ F'(x) dx = F(b) - F(a)    (TFC)
                           ↓ generaliza
    Análisis II:      ∮ F·dr = ∬ (∇×F)·dS         (Stokes)
                      ∮ F·dr = ∬ (Q_x-P_y) dA     (Green)
                      ∬ F·dS = ∭ (∇·F) dV         (Gauss)
```

---

## Aplicaciones en ingeniería

| Contexto | Teorema | Aplicación |
|:---------|:--------|:-----------|
| **Electromagnetismo** | Gauss | Ley de Gauss: $\iint \mathbf{E} \cdot d\mathbf{S} = Q/\varepsilon_0$ |
| **Electromagnetismo** | Stokes | Ley de Faraday: $\oint \mathbf{E} \cdot d\mathbf{r} = -\frac{d\Phi_B}{dt}$ |
| **Mecánica de fluidos** | Divergencia | Caudal neto a través de una superficie cerrada |
| **Transferencia de calor** | Divergencia | Balance de energía: flujo de calor = generación interna |
| **Dinámica de fluidos** | Stokes | Circulación y vorticidad: $\Gamma = \iint \omega \cdot d\mathbf{S}$ |
| **Acústica** | Gradiente | Propagación de ondas sonoras |

---

## Conexiones con otras áreas

- **[[Anm_Campos_Integrales_Linea]]**: prerrequisito — campos, integrales de línea, Green
- **[[Anm_Integrales_Multiples]]**: integrales triples y jacobianos
- **[[Anm_Derivadas_Parciales]]**: divergencia, rotor, gradiente son operadores diferenciales
- **[[Eje_Fisica]]**: leyes de Maxwell, conservación de la masa, ecuación de continuidad
- **[[Ecuaciones Diferenciales]]**: ecuaciones de Laplace y Poisson: $\nabla^2 u = 0$, $\nabla^2 u = f$

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Clase 12 — Integrales de Superficie (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 12-ING-Integrales de Superficie_...pdf` |
| Clase 13 — Stokes y Divergencia (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 13-ING-Teoremas Stokes y Divergencia_...pdf` |
| ING 2024 4 — Green (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/2024 ING 4-Green.pdf` |
| ING 2024 5 — Integrales de superficie (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/ING 2024 5-Integrales de superficie.pdf` |
| ING 2024 6 — Stokes y Divergencia (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/2024 ING 6-Teorema de Stokes y Divergencia.pdf` |
| U12 Integrales de Superficie (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U12 Integrales de Superficie.pdf` |
| U13 Stokes y Divergencia (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U13 Teoremas Stokes y Divergencia.pdf` |

---

## Ejercicios modelados

1. **Integral escalar de superficie**: Calcular $\iint_S (x^2 + y^2) \, dS$ donde $S$ es el cono $z = \sqrt{x^2 + y^2}$ con $0 \leq z \leq 1$.
2. **Flujo directo**: Calcular el flujo de $\mathbf{F} = (x, y, 2z)$ a través del paraboloide $z = x^2 + y^2$, $0 \leq z \leq 1$, con normal hacia arriba.
3. **Stokes**: Usar Stokes para calcular $\oint_C \mathbf{F} \cdot d\mathbf{r}$ con $\mathbf{F} = (z, x, y)$ y $C$ el triángulo con vértices $(1,0,0)$, $(0,1,0)$, $(0,0,1)$.
4. **Gauss**: Verificar el teorema de la divergencia para $\mathbf{F} = (x, y, z)$ a través de la esfera unitaria $x^2 + y^2 + z^2 = 1$.
5. **Identidad**: Demostrar que $\nabla \times (\nabla f) = \mathbf{0}$ para $f(x,y,z) = x^2yz + \sin(xy)$.

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Campos_Integrales_Linea]] • **Siguiente:** [[Anm_Ecuaciones_Diferenciales]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
