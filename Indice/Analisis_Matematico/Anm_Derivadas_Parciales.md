> [!NOTE] Navegación
> **Anterior:** [[Anm_Funciones_Varias_Variables]] • **Siguiente:** [[Anm_Extremos]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta del eje.

# Derivadas Parciales

## Índice

==toc==

---

> [!INFO]
> Cuando tenés varias variables, **derivás respecto a una mientras mantenés las otras constantes**. Así construís el gradiente, la diferenciabilidad y todo el cálculo vectorial. En ingeniería: la tasa de cambio de temperatura respecto a la posición ($\partial T/\partial x$), la variación de presión con la altura, la pendiente de un terreno en cada dirección.

---

## Derivada parcial

$$f_x(x,y) = \frac{\partial f}{\partial x} = \lim_{h \to 0} \frac{f(x+h,y) - f(x,y)}{h}$$

$$f_y(x,y) = \frac{\partial f}{\partial y} = \lim_{k \to 0} \frac{f(x,y+k) - f(x,y)}{k}$$

**Interpretación**: la derivada parcial respecto a $x$ es la pendiente de la recta tangente a la superficie en la dirección del eje $x$. Análogamente para $y$.

```
z
▲
│      /‾‾‾‾‾‾‾‾‾‾‾
│     /  superficie z = f(x,y)
│    /  /  /
│   /  /  /
│  /  /  /
│ /  /  /
│/  /  /
│  /  /
│ /  /
│/  /
│              ► y
► x
   └── recta tangente en dirección x (pendiente = ∂f/∂x)
```

> [!EXAMPLE] Calcular derivadas parciales
> Hallar $f_x$ y $f_y$ para $f(x,y) = x^2y + \sin(xy)$.
>
> **Solución:**
> **Respecto a $x$** (tratar $y$ como constante):
> $f_x = \frac{\partial}{\partial x}(x^2y) + \frac{\partial}{\partial x}(\sin(xy))$
> $f_x = 2xy + y\cos(xy)$
>
> **Respecto a $y$** (tratar $x$ como constante):
> $f_y = \frac{\partial}{\partial y}(x^2y) + \frac{\partial}{\partial y}(\sin(xy))$
> $f_y = x^2 + x\cos(xy)$
>
> Verificación: notar que $f_{xy} = 2x + \cos(xy) - xy\sin(xy)$ y $f_{yx}$ da lo mismo por Clairaut.

> [!TIP] Técnica de derivación parcial
> Tapá mentalmente la variable que no estás derivando. Si $f(x,y) = x^2y^3$, al derivar respecto a $x$ pensá "$y^3$ es una constante multiplicando a $x^2$", entonces $f_x = 2x \cdot y^3$. Simple.

---

## Diferenciabilidad

$f(x,y)$ es **diferenciable** en $(a,b)$ si las derivadas parciales existen **y** el plano tangente aproxima bien a la función cerca del punto. Condición suficiente: $f_x$ y $f_y$ existen y son continuas cerca de $(a,b)$.

### Plano tangente

$$z = f(a,b) + f_x(a,b)(x-a) + f_y(a,b)(y-b)$$

> [!WARNING] Existencia de derivadas parciales ≠ diferenciabilidad
> **Error clásico**: creer que si existen $f_x$ y $f_y$ en un punto, la función es diferenciable ahí. Contraejemplo:
> $f(x,y) = \begin{cases} \frac{xy}{x^2+y^2} & (x,y) \neq (0,0) \\ 0 & (x,y) = (0,0) \end{cases}$
> $f_x(0,0) = f_y(0,0) = 0$ existen, pero $f$ no es continua en $(0,0)$ (el límite no existe), por lo tanto no es diferenciable.
> **La diferenciabilidad requiere más**: que el plano tangente sea una **buena aproximación lineal**, no solo que existan las derivadas.

### Aproximación lineal

$$f(x,y) \approx f(a,b) + f_x(a,b)(x-a) + f_y(a,b)(y-b)$$

> [!EXAMPLE] Aproximación lineal
> Usar el plano tangente para aproximar $\sqrt{3.98^2 + 2.01^2}$.
>
> **Solución:** Sea $f(x,y) = \sqrt{x^2 + y^2}$. Punto base: $(4,2)$.
>
> $f(4,2) = \sqrt{16+4} = \sqrt{20} \approx 4.4721$
> $f_x(x,y) = \frac{x}{\sqrt{x^2+y^2}} \quad \Rightarrow \quad f_x(4,2) = \frac{4}{\sqrt{20}} \approx 0.8944$
> $f_y(x,y) = \frac{y}{\sqrt{x^2+y^2}} \quad \Rightarrow \quad f_y(4,2) = \frac{2}{\sqrt{20}} \approx 0.4472$
>
> $f(3.98, 2.01) \approx f(4,2) + f_x(4,2)(-0.02) + f_y(4,2)(0.01)$
> $\approx 4.4721 + 0.8944(-0.02) + 0.4472(0.01)$
> $\approx 4.4721 - 0.0179 + 0.0045 = 4.4587$
>
> Valor real: $\sqrt{3.98^2 + 2.01^2} = \sqrt{15.8404 + 4.0401} = \sqrt{19.8805} \approx 4.4590$. Error: $\sim 0.0003$ — muy buena aproximación.

---

## Regla de la cadena

Si $z = f(x,y)$ con $x = x(t)$, $y = y(t)$:

$$\frac{dz}{dt} = \frac{\partial f}{\partial x} \frac{dx}{dt} + \frac{\partial f}{\partial y} \frac{dy}{dt}$$

Para $z = f(x,y)$ con $x = x(u,v)$, $y = y(u,v)$:

$$\frac{\partial z}{\partial u} = \frac{\partial f}{\partial x} \frac{\partial x}{\partial u} + \frac{\partial f}{\partial y} \frac{\partial y}{\partial u}$$

> [!TIP] Diagrama de árbol para regla de la cadena
> ```
>           ┌── x ── t
>     ┌── f ┤
>     │     └── y ── t
> z ──┤
>     │     ┌── x ──┬── u
>     └── f ┤       └── v
>           └── y ──┬── u
>                   └── v
> ```
> **Cada camino** de $z$ a la variable independiente produce un término. Si $z \to x \to t$ y $z \to y \to t$, los dos términos se suman: $\frac{dz}{dt} = \frac{\partial f}{\partial x}\frac{dx}{dt} + \frac{\partial f}{\partial y}\frac{dy}{dt}$.

> [!EXAMPLE] Regla de la cadena
> Sea $f(x,y) = x^2y$ con $x(t) = \cos t$, $y(t) = e^t$. Hallar $\frac{dz}{dt}$.
>
> **Solución:**
> $\frac{\partial f}{\partial x} = 2xy$, $\frac{\partial f}{\partial y} = x^2$
> $\frac{dx}{dt} = -\sin t$, $\frac{dy}{dt} = e^t$
>
> $\frac{dz}{dt} = (2xy)(-\sin t) + (x^2)(e^t)$
> $\frac{dz}{dt} = 2(\cos t)(e^t)(-\sin t) + (\cos^2 t)(e^t)$
> $\frac{dz}{dt} = e^t(-2\cos t\sin t + \cos^2 t)$
> $\frac{dz}{dt} = e^t\cos t(\cos t - 2\sin t)$
>
> **Verificación** (sustitución directa): $z = \cos^2 t \cdot e^t$, derivando respecto a $t$: $z' = -2\cos t\sin t \cdot e^t + \cos^2 t \cdot e^t = e^t\cos t(\cos t - 2\sin t)$. ✓

---

## Derivada direccional y gradiente

**Gradiente**: $\nabla f = (f_x, f_y)$ — vector que apunta en la dirección de **máximo crecimiento**.

**Derivada direccional** en dirección del vector unitario $\mathbf{u}$:

$$D_{\mathbf{u}} f = \nabla f \cdot \mathbf{u}$$

- Máximo crecimiento: dirección del gradiente
- Mínimo crecimiento: dirección opuesta al gradiente
- Cero: dirección perpendicular al gradiente (curva de nivel)

> [!TIP] El gradiente es perpendicular a las curvas de nivel
> Esto es clave: el gradiente en un punto es **perpendicular** a la curva de nivel que pasa por ese punto. Por eso, si querés la dirección de máxima pendiente en un mapa topográfico, es perpendicular a las líneas de altitud constante.

> [!EXAMPLE] Derivada direccional
> Calcular $D_{\mathbf{u}} f$ en $(1,2)$ para $f(x,y) = x^2 + y^2$ en dirección $\mathbf{v} = (1,1)$.
>
> **Solución:**
> $\nabla f = (2x, 2y) \quad \Rightarrow \quad \nabla f(1,2) = (2,4)$
>
> Vector unitario: $\mathbf{u} = \frac{\mathbf{v}}{\|\mathbf{v}\|} = \frac{(1,1)}{\sqrt{2}} = \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)$
>
> $D_{\mathbf{u}} f = \nabla f \cdot \mathbf{u} = (2,4) \cdot \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right) = \frac{2+4}{\sqrt{2}} = \frac{6}{\sqrt{2}} = 3\sqrt{2}$
>
> Esto significa que en $(1,2)$, si nos movemos en la dirección $(1,1)$, la función crece a razón de $3\sqrt{2}$ unidades por unidad de distancia.

---

## Derivadas parciales de orden superior

$f_{xx} = \frac{\partial^2 f}{\partial x^2} \quad f_{xy} = \frac{\partial^2 f}{\partial y \partial x}$

**Teorema de Clairaut/Schwarz**: si las derivadas mixtas $f_{xy}$ y $f_{yx}$ son continuas, entonces $f_{xy} = f_{yx}$.

> [!WARNING] Orden de derivación
> $f_{xy}$ significa "derivar primero respecto a $x$, luego respecto a $y$". $f_{yx}$ es al revés. Por Clairaut, si las segundas derivadas mixtas son continuas, el orden no importa. Pero **si no son continuas**, puede haber diferencia.

### Tabla de notación

| Notación | Significado |
|:---------|:------------|
| $f_x$ o $\frac{\partial f}{\partial x}$ | Primera derivada parcial respecto a $x$ |
| $f_{xy}$ o $\frac{\partial^2 f}{\partial y \partial x}$ | Derivar respecto a $x$, luego $y$ |
| $f_{xx}$ o $\frac{\partial^2 f}{\partial x^2}$ | Derivar dos veces respecto a $x$ |
| $\nabla f$ | Gradiente: vector de primeras derivadas |
| $H_f$ | Hessiana: matriz de segundas derivadas |

---

## Aplicaciones en ingeniería

| Contexto | Qué se deriva | Interpretación física |
|:---------|:--------------|:---------------------|
| **Mecánica de sólidos** | $\frac{\partial \sigma_{xx}}{\partial x}$ | Gradiente de tensión en un material |
| **Transferencia de calor** | $\frac{\partial T}{\partial x}$ | Gradiente térmico → flujo de calor (ley de Fourier) |
| **Mecánica de fluidos** | $\frac{\partial v_x}{\partial y}$ | Tasa de deformación cortante en un fluido |
| **Electromagnetismo** | $\nabla V$ | Campo eléctrico $\mathbf{E} = -\nabla V$ |
| **Termodinámica** | $\left(\frac{\partial P}{\partial V}\right)_T$ | Compresibilidad isotérmica |

---

## Conexiones con otras áreas

- **[[Anm_Funciones_Varias_Variables]]**: prerrequisito — necesitás entender curvas y superficies
- **[[Anm_Extremos]]**: aplicación directa — usamos derivadas parciales y Hessiana para optimizar
- **[[Anm_Campos_Integrales_Linea]]**: el gradiente define campos conservativos
- **[[Anm_Integrales_Superficie]]**: divergencia y rotor se construyen con derivadas parciales
- **[[Alg_Vectores]]**: el gradiente es un vector, el producto punto da la derivada direccional
- **Física**: la ecuación de onda, ecuación de calor, ecuación de Laplace — todas usan derivadas parciales

---

## Material de estudio en el Raw

| Recurso | Ruta |
|---------|------|
| Clase 2 — FVV 2 (David Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 2-FVV_...pdf` |
| Clase 3 — Derivadas parciales (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 3-FVVDerivadasparciales_...pdf` |
| Clase 4 — Regla de la cadena (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/Clases_/Clase 4-ING-Regla de la cadena y TFI_...pdf` |
| Derivadas parciales (David Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Derivadas parciales (3).pdf` |
| Diferenciabilidad | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Diferenciabilidad 1.pdf` |
| Regla de la cadena (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/Regla de la cadena.pdf` |
| U3 Derivadas parciales (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U3 Derivadas parciales.pdf` |
| U4 Regla de la cadena (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U4 Regla de la cadena.pdf` |
| U5 Derivada direccional (Cecilia Ferrari) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/recursado Cecilia Ferrari/teoría_/U5 Derivada direccional.pdf` |
| Derivada direccional (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/derivada direccional.pdf` |
| Adicional derivadas parciales (Allmang) | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/adicional derivadas parciales.pdf` |
| Ejemplo 7 derivadas parciales | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/ejemplo 7 derivadas parciales teoría.pdf` |
| Ejercicio cierre | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/teoria/ejercicio cierre.pdf` |
| TP4 Derivadas Parciales — Diferenciabilidad — Plano Tangente | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP4 Derivadas Parciales- Diferenciabilidad- Plano Tangente.pdf` |
| TP5 Regla de la Cadena | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP5 Regla de la Cadena.pdf` |
| TP6 Derivada Direccional | `Raw/.../1 matematica/TEORIA/Análisis matemático II/cursado David Allmang/tps/TP6 Derivada Direccional.pdf` |

---

## Ejercicios modelados

1. **Derivadas parciales**: $f(x,y) = e^{xy}\cos(x+y)$. Hallar $f_x$, $f_y$, $f_{xx}$, $f_{xy}$.
2. **Plano tangente**: Hallar la ecuación del plano tangente a $z = \ln(1+x^2+y^2)$ en $(1,1,\ln 3)$.
3. **Regla de la cadena**: $z = u^2v + uv^2$ con $u = x\sin y$, $v = y\cos x$. Hallar $\partial z/\partial x$ y $\partial z/\partial y$.
4. **Derivada direccional**: Calcular la derivada direccional de $f(x,y,z) = x^2 + y^2 + z^2$ en $(1,1,1)$ en dirección hacia el origen.
5. **Aproximación**: Usar aproximación lineal para estimar $\sin(0.1)\cos(0.2)$.

---

> [!NOTE] Navegación
> **Anterior:** [[Anm_Funciones_Varias_Variables]] • **Siguiente:** [[Anm_Extremos]]
>
> 📌 [[Eje_Analisis_Matematico]] — volver a la hoja de ruta.
