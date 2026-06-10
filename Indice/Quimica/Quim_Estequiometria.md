> [!INFO] Conexiones de la Red
> Eje: [[Eje_Quimica]] • Anterior: [[Quim_Teorias_Enlace]] • Siguiente: [[Quim_Termoquimica]]
> Requisitos: [[Eje_Algebra]] (sistemas de ecuaciones)

# Estequiometría

## Índice

==toc==

---

Reacciones químicas, ecuaciones químicas, el mol, masa molar, relaciones estequiométricas, reactivo limitante, rendimiento, pureza de reactivos.

---

## Conceptos clave

### Ecuaciones químicas

Una ecuación química representa una reacción usando símbolos y fórmulas.

**Forma general:**
$$aA + bB \rightarrow cC + dD$$

Donde $a$, $b$, $c$, $d$ son los **coeficientes estequiométricos** (números enteros que balancean la ecuación).

**Indicaciones de estado físico:**
- $(s)$ — sólido
- $(l)$ — líquido
- $(g)$ — gas
- $(ac)$ — acuoso (disuelto en agua)

**Ejemplo:**
$$2H_{2(g)} + O_{2(g)} \rightarrow 2H_2O_{(l)}$$

**Balanceo de ecuaciones:** Consiste en igualar el número de átomos de cada elemento en reactivos y productos. Métodos:
1. **Tanteo** (simple inspección)
2. **Algebraico** (sistema de ecuaciones)
3. **Ión-electrón** (para reacciones redox)

> [!EXAMPLE] Balanceo por tanteo
> Balancear $C_3H_8 + O_2 \rightarrow CO_2 + H_2O$:
> 1. Carbono: 3 C en reactivos → 3 $CO_2$
> 2. Hidrógeno: 8 H en $C_3H_8$ → 4 $H_2O$
> 3. Oxígeno: 3×2 + 4×1 = 10 O en productos → 5 $O_2$
> 4. Ecuación balanceada: $C_3H_8 + 5O_2 \rightarrow 3CO_2 + 4H_2O$

---

### El mol

El **mol** es la unidad de cantidad de sustancia en el SI. Un mol contiene exactamente $6.022 \times 10^{23}$ entidades elementales (átomos, moléculas, iones, etc.). Este número se conoce como **número de Avogadro** ($N_A$).

Relaciones fundamentales:

$$1 \text{ mol} = 6.022 \times 10^{23} \text{ partículas}$$

$$n = \frac{\text{número de partículas}}{N_A}$$

$$n = \frac{m}{M}$$

Donde:
- $n$ = cantidad de sustancia (mol)
- $m$ = masa de la muestra (g)
- $M$ = masa molar (g/mol)

**Masa molar ($M$):** masa de un mol de sustancia. Numéricamente igual a la masa atómica o molecular expresada en gramos.

| Sustancia | Masa molecular (uma) | Masa molar (g/mol) |
|:----------|:--------------------:|:------------------:|
| $H_2$ | 2.02 | 2.02 |
| $O_2$ | 32.00 | 32.00 |
| $H_2O$ | 18.02 | 18.02 |
| $CO_2$ | 44.01 | 44.01 |
| $NaCl$ | 58.44 | 58.44 |

**Volumen molar (STP):** Un mol de cualquier gas ideal ocupa **22.4 L** en condiciones normales de presión y temperatura (STP: 0°C = 273.15 K, 1 atm = 101.325 kPa).

$$V = n \times 22.4 \text{ L/mol (a STP)}$$

---

### Relaciones estequiométricas

A partir de una ecuación balanceada se pueden establecer relaciones entre reactivos y productos.

#### 1. Relación mol-mol

Usando los coeficientes de la ecuación:

$$2H_2 + O_2 \rightarrow 2H_2O$$

La relación es: 2 mol $H_2$ : 1 mol $O_2$ : 2 mol $H_2O$

**Ejemplo:** ¿Cuántos moles de $H_2O$ se producen con 4 moles de $H_2$?

$$4 \text{ mol } H_2 \times \frac{2 \text{ mol } H_2O}{2 \text{ mol } H_2} = 4 \text{ mol } H_2O$$

#### 2. Relación masa-masa

Se convierte masa a mol, se usa la relación estequiométrica y se vuelve a masa.

**Ejemplo:** ¿Qué masa de $H_2O$ se produce al reaccionar 8 g de $H_2$ con suficiente $O_2$?

$$8 \text{ g } H_2 \times \frac{1 \text{ mol } H_2}{2.02 \text{ g } H_2} \times \frac{2 \text{ mol } H_2O}{2 \text{ mol } H_2} \times \frac{18.02 \text{ g } H_2O}{1 \text{ mol } H_2O} = 71.37 \text{ g } H_2O$$

#### 3. Relación masa-volumen (gases)

**Ejemplo:** ¿Qué volumen de $O_2$ (STP) se necesita para reaccionar con 8 g de $H_2$?

$$8 \text{ g } H_2 \times \frac{1 \text{ mol } H_2}{2.02 \text{ g } H_2} \times \frac{1 \text{ mol } O_2}{2 \text{ mol } H_2} \times \frac{22.4 \text{ L } O_2}{1 \text{ mol } O_2} = 44.36 \text{ L } O_2$$

---

### Reactivo limitante

En una reacción, el **reactivo limitante** es el que se consume completamente primero y determina la cantidad de producto que se forma. Los demás son **reactivos en exceso**.

**Pasos para identificar el reactivo limitante:**

1. Balancear la ecuación química.
2. Convertir las masas (o volúmenes) de los reactivos a moles.
3. Dividir los moles de cada reactivo por su coeficiente estequiométrico.
4. El **menor resultado** corresponde al reactivo limitante.

> [!EXAMPLE] Reactivo limitante
> Se mezclan 10 g de $H_2$ con 10 g de $O_2$. ¿Cuál es el reactivo limitante?
> $$2H_2 + O_2 \rightarrow 2H_2O$$
>
> Moles de $H_2$: $10 \text{ g} / 2.02 \text{ g/mol} = 4.95 \text{ mol}$
> Moles de $O_2$: $10 \text{ g} / 32.00 \text{ g/mol} = 0.313 \text{ mol}$
>
> Dividiendo por coeficientes:
> - $H_2$: $4.95 / 2 = 2.48$
> - $O_2$: $0.313 / 1 = 0.313$ ← **menor**
>
> **Reactivo limitante: $O_2$**
>
> Cantidad de $H_2O$ producida (desde el limitante):
> $$0.313 \text{ mol } O_2 \times \frac{2 \text{ mol } H_2O}{1 \text{ mol } O_2} \times \frac{18.02 \text{ g } H_2O}{1 \text{ mol } H_2O} = 11.27 \text{ g } H_2O$$

---

### Rendimiento de reacción

En la práctica, las reacciones no producen el 100% del producto esperado.

- **Rendimiento teórico:** Cantidad máxima de producto que se obtendría si la reacción fuera perfecta (calculada estequiométricamente).
- **Rendimiento real:** Cantidad de producto realmente obtenida en el laboratorio.
- **Porcentaje de rendimiento:**

$$\% \text{ rendimiento} = \frac{\text{rendimiento real}}{\text{rendimiento teórico}} \times 100$$

> [!EXAMPLE] Rendimiento
> En la reacción anterior, se obtuvieron experimentalmente 9.50 g de $H_2O$. El rendimiento teórico era 11.27 g.
>
> $$\% \text{ rendimiento} = \frac{9.50 \text{ g}}{11.27 \text{ g}} \times 100 = 84.3\%$$

**Causas de bajo rendimiento:**
- Reacciones secundarias (no deseadas)
- Reversibilidad de la reacción
- Pérdidas durante la manipulación
- Reactivos impuros

---

### Pureza de reactivos

En la industria y el laboratorio, los reactivos rara vez son 100% puros. La **pureza** indica el porcentaje de la masa del reactivo que corresponde a la sustancia deseada.

$$\% \text{ pureza} = \frac{\text{masa de sustancia pura}}{\text{masa total de la muestra}} \times 100$$

**Cálculo ajustado:**

$$\text{masa real de reactivo puro} = \text{masa de muestra} \times \frac{\% \text{ pureza}}{100}$$

> [!EXAMPLE] Pureza
> Se dispone de 50 g de $CaCO_3$ con 80% de pureza. ¿Cuántos moles de $CaCO_3$ puro hay?
>
> Masa pura: $50 \text{ g} \times 0.80 = 40 \text{ g}$
> Moles: $40 \text{ g} / 100.09 \text{ g/mol} = 0.40 \text{ mol}$
>
> Esos 0.40 mol son los que se usan para los cálculos estequiométricos.

---

### Ejemplo resuelto paso a paso: Síntesis del amoníaco (Haber-Bosch)

$$N_2 + 3H_2 \rightarrow 2NH_3$$

**Datos:** Se hacen reaccionar 28 g de $N_2$ con 10 g de $H_2$. La pureza del $H_2$ es del 90%. El rendimiento de la reacción es del 75%.

**Paso 1: Moles reales de cada reactivo**
- $N_2$: $28 \text{ g} / 28.02 \text{ g/mol} = 1.00 \text{ mol}$
- $H_2$ (puro): $10 \text{ g} \times 0.90 = 9 \text{ g}$ → $9 \text{ g} / 2.02 \text{ g/mol} = 4.46 \text{ mol}$

**Paso 2: Identificar reactivo limitante**
- $N_2$: $1.00 / 1 = 1.00$
- $H_2$: $4.46 / 3 = 1.49$
- **Reactivo limitante: $N_2$**

**Paso 3: Rendimiento teórico de $NH_3$**
$$1.00 \text{ mol } N_2 \times \frac{2 \text{ mol } NH_3}{1 \text{ mol } N_2} \times \frac{17.03 \text{ g } NH_3}{1 \text{ mol } NH_3} = 34.06 \text{ g } NH_3$$

**Paso 4: Rendimiento real**
$$34.06 \text{ g} \times \frac{75}{100} = 25.55 \text{ g } NH_3$$

**Respuesta:** Se obtienen 25.55 g de $NH_3$.

---

## Fórmulas importantes

- **Cantidad de sustancia (mol)**: $n = \displaystyle\frac{m}{M}$
- **Número de Avogadro**: $1 \text{ mol} = 6.022 \times 10^{23} \text{ partículas}$
- **Volumen molar (STP)**: $V = n \times 22.4 \text{ L/mol}$
- **Reactivo limitante**: menor valor de $\displaystyle\frac{n_{\text{reactivo}}}{\text{coeficiente}}$
- **Porcentaje de rendimiento**: $\%R = \displaystyle\frac{\text{real}}{\text{teórico}} \times 100$
- **Pureza**: $\text{masa pura} = \text{masa muestra} \times \displaystyle\frac{\% \text{ pureza}}{100}$

---

## Teoría

- **Estequiometría (parte 1)** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/Estequiometría. Parte 1.pdf`
- **Estequiometría (parte 2)** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/Estequiometría - Parte 2 (3).pdf`
- **ESTEQUIOMETRÍA (general)** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/ESTEQUIOMETRÍA (1).pdf`
- **Reacciones químicas (1)** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/Reacciones químicas (1).pdf`
- **REACCIONES QUIMICAS** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/REACCIONES QUIMICAS.pdf`
- **Unidad VII Reacciones y estequiometría** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/UNIDAD VII REacciones químicas y estequiometría.pdf`
- **Mol** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/Mol.pdf`
- **U7 mol y masas I y II** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U7 mol y masas I.pdf` y `U7 mol y masas II.pdf`
- **U7 reacciones químicas** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U7 reacciones químicas.pdf`
- **U7 relaciones estequiométricas** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U7 relaciones estequiometricas.pdf`
- **U7 pureza y reactivos** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U7 pureza y reactivos.pdf`

### Libros de referencia
- **Brown** Capítulo 3 (Estequiometría: relaciones de masa en las reacciones) — en `Unidad 7/Quimica la Ciencia Central (Brown - LeMay - Bursten)-Cap 3 Estequiometria. 9°Ed.pdf`
- **Petrucci** Capítulo 4 (Las reacciones químicas) — en `Unidad 7/Quimica Gral Petrucci-Cap4 Las Reacciones Quimicas. 10°Ed.pdf`

---

## Ejercicios

- **Ejercicios Unidad VII** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/IQ UNIDAD VII EJERCICIOS f.pdf`
- **Respuestas Unidad VII** → `Raw/material y ejercicios (profes)/InQ/Unidad 7/IQ  RESPUESTAS  UNIDAD VII EJERCICIOS ESTEQUIOMETRIA (1).pdf`
- **TP 5** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 5.pdf`
- **TP 6** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 6.pdf`
- **TP 7** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 7.pdf`
- **TP 7 soluciones** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 7 soluciones .pdf`

---

> [!NOTE] 📍 Navegación del tema
> **Tema anterior:** [[Quim_Teorias_Enlace]]
> **Tema siguiente:** [[Quim_Termoquimica]]

---

> [!WARNING] Conexión importante
> La estequiometría requiere manejar sistemas de ecuaciones del [[Eje_Algebra]]. También es la base para los balances de materia que vas a usar en termoquímica y más adelante en materias como Termodinámica.
