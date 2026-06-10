> [!INFO] Conexiones de la Red
> Eje: [[Eje_Quimica]] • Anterior: [[Quim_Sistemas_Materiales]] • Siguiente: [[Quim_Tabla_Periodica]]

# Estructura Atómica

## Índice

==toc==

---

Átomo, partículas subatómicas, modelos atómicos (Bohr, mecánica cuántica), isótopos, números cuánticos, orbitales atómicos, configuraciones electrónicas.

---

## Conceptos clave

### Partículas subatómicas

| Partícula | Símbolo | Carga eléctrica | Masa (kg) | Masa (u) | Ubicación |
|-----------|---------|----------------|-----------|----------|-----------|
| **Protón** | $p^+$ | $+1$ ($+1.602 \times 10^{-19} \text{ C}$) | $1.673 \times 10^{-27}$ | $1.0073$ | Núcleo |
| **Neutrón** | $n^0$ | $0$ | $1.675 \times 10^{-27}$ | $1.0087$ | Núcleo |
| **Electrón** | $e^-$ | $-1$ ($-1.602 \times 10^{-19} \text{ C}$) | $9.109 \times 10^{-31}$ | $0.0005485$ | Corteza (orbitales) |

> [!NOTE]
> La masa de protones y neutrones es ~1840 veces mayor que la del electrón. Por eso prácticamente toda la masa del átomo está en el núcleo.

### Modelos atómicos históricos

| Modelo | Año | Científico | Aportes clave | Limitaciones |
|--------|-----|------------|---------------|--------------|
| **Dalton** | 1808 | John Dalton | Átomos como esferas indivisibles e indestructibles. Cada elemento tiene átomos iguales. | No explica la existencia de partículas subatómicas ni isótopos |
| **Thomson** | 1897 | J.J. Thomson | Descubrimiento del electrón. Modelo del "pudín de pasas" (esfera positiva con electrones incrustados). | No explica la dispersión de Rutherford |
| **Rutherford** | 1911 | Ernest Rutherford | Núcleo pequeño y denso con carga positiva. Electrones orbitando alrededor. Átomo mayormente vacío. | No explica estabilidad del átomo ni espectros discretos |
| **Bohr** | 1913 | Niels Bohr | Electrones en órbitas circulares con energía cuantizada ($E_n = -R_H / n^2$). Explica espectro del H. | Solo funciona para átomos con 1 electrón |
| **Mecánica cuántica** | 1926 | Schrödinger, Heisenberg, Dirac | Orbitales (regiones de probabilidad). Ecuación de onda. Números cuánticos. | Requiere matemática avanzada; no hay "trayectoria" del electrón |

#### Detalles de cada modelo

- **Dalton**: basado en la ley de conservación de la masa (Lavoisier) y las proporciones definidas (Proust). Postuló que los átomos de un mismo elemento son idénticos entre sí.
- **Thomson**: descubrió el electrón mediante experimentos con tubos de rayos catódicos. Determinó la relación $e/m$ del electrón.
- **Rutherford**: experimento de la lámina de oro (partículas $\alpha$). La mayoría atravesaba, algunas se desviaban y muy pocas rebotaban, lo que indicaba un núcleo pequeño y denso.
- **Bohr**: los electrones solo pueden estar en ciertas órbitas permitidas ($n=1,2,3,...$). Al "saltar" de una órbita a otra emiten o absorben fotones de energía específica: $\Delta E = h\nu = R_H \left( \frac{1}{n_f^2} - \frac{1}{n_i^2} \right)$.
- **Mecánica cuántica**: el principio de incertidumbre de Heisenberg ($\Delta x \cdot \Delta p \ge h/4\pi$) establece que no se puede conocer simultáneamente la posición y el momento del electrón con precisión arbitraria.

### Números cuánticos

Los números cuánticos son los "valores permitidos" que describen el estado energético de un electrón en un átomo.

| Número cuántico | Símbolo | Significado | Valores permitidos | Relación |
|-----------------|---------|-------------|-------------------|----------|
| **Principal** | $n$ | Nivel de energía / tamaño del orbital | $1, 2, 3, 4, ...$ (entero positivo) | $n = 1, 2, 3...$ |
| **Secundario o azimutal** | $l$ | Subnivel / forma del orbital | $0, 1, 2, ..., n-1$ | $0 \le l \le n-1$ |
| **Magnético** | $m_l$ | Orientación del orbital en el espacio | $-l, ..., 0, ..., +l$ | $-l \le m_l \le +l$ |
| **Espín** | $m_s$ | Sentido de rotación del electrón | $+\frac{1}{2}$ o $-\frac{1}{2}$ | Dos valores posibles |

#### Correspondencia $l$ - subnivel

| $l$ | Letra | Forma del orbital | Capacidad (orbitales) | Capacidad (electrones) |
|-----|-------|-------------------|----------------------|------------------------|
| $0$ | $s$ | Esférica | 1 | 2 |
| $1$ | $p$ | Lóbulos (tres direcciones) | 3 | 6 |
| $2$ | $d$ | Trébol (cuatro lóbulos) | 5 | 10 |
| $3$ | $f$ | Compleja (7 orbitales) | 7 | 14 |

### Orbitales atómicos

Un **orbital atómico** es una región del espacio donde la probabilidad de encontrar al electrón es máxima (generalmente >90%).

- **Orbital $s$**: forma esférica. Simetría radial. Existe para $n \ge 1$.
- **Orbital $p$**: forma de lóbulos (dos lóbulos por orbital). Existe para $n \ge 2$. Tres orientaciones: $p_x$, $p_y$, $p_z$.
- **Orbital $d$**: formas más complejas (cuatro lóbulos). Existe para $n \ge 3$. Cinco orbitales: $d_{xy}$, $d_{xz}$, $d_{yz}$, $d_{x^2-y^2}$, $d_{z^2}$.
- **Orbital $f$**: formas aún más complejas. Existe para $n \ge 4$. Siete orbitales.

### Configuraciones electrónicas

Se rigen por tres principios fundamentales:

1. **Principio de Aufbau (construcción)**: los electrones llenan primero los orbitales de menor energía. Orden de llenado:
   $$1s, 2s, 2p, 3s, 3p, 4s, 3d, 4p, 5s, 4d, 5p, 6s, 4f, 5d, 6p, 7s, 5f, 6d, 7p$$

2. **Principio de exclusión de Pauli**: en un átomo, no pueden existir dos electrones con los cuatro números cuánticos iguales. Cada orbital puede contener **máximo 2 electrones** con espines opuestos ($m_s = +1/2$ y $m_s = -1/2$).

3. **Regla de Hund (máxima multiplicidad)**: al llenar orbitales de igual energía (degenerados), los electrones se colocan primero uno en cada orbital (todos con el mismo espín) antes de aparearse.

#### Ejemplos de configuraciones electrónicas

| Elemento | Símbolo | Z | Configuración electrónica |
|----------|---------|---|--------------------------|
| Hidrógeno | H | 1 | $1s^1$ |
| Helio | He | 2 | $1s^2$ |
| Carbono | C | 6 | $1s^2 2s^2 2p^2$ |
| Nitrógeno | N | 7 | $1s^2 2s^2 2p^3$ |
| Neón | Ne | 10 | $1s^2 2s^2 2p^6$ |
| Sodio | Na | 11 | $1s^2 2s^2 2p^6 3s^1$ o $[Ne] 3s^1$ |
| Hierro | Fe | 26 | $1s^2 2s^2 2p^6 3s^2 3p^6 4s^2 3d^6$ o $[Ar] 4s^2 3d^6$ |
| Bromo | Br | 35 | $[Ar] 4s^2 3d^{10} 4p^5$ |

> [!WARNING]
> Hay excepciones importantes por estabilidad adicional: el $Cr$ (Z=24) es $[Ar] 4s^1 3d^5$ (no $4s^2 3d^4$) y el $Cu$ (Z=29) es $[Ar] 4s^1 3d^{10}$ (no $4s^2 3d^9$), porque los orbitales $d$ semillenos o llenos son más estables.

### Isótopos

Los **isótopos** son átomos del mismo elemento (mismo número de protones $Z$) con diferente número de neutrones ($N$). Por lo tanto, tienen distinto número másico ($A = Z + N$).

Se representan como: $\displaystyle ^A_Z\text{X}$ donde X es el símbolo del elemento.

| Elemento | Isótopo | $Z$ | $N$ | $A$ | Abundancia natural |
|----------|---------|-----|-----|-----|--------------------|
| Hidrógeno | $^1_1H$ (protio) | 1 | 0 | 1 | 99.985% |
| | $^2_1H$ (deuterio) | 1 | 1 | 2 | 0.015% |
| | $^3_1H$ (tritio) | 1 | 2 | 3 | Trazas (radiactivo) |
| Carbono | $^{12}_6C$ | 6 | 6 | 12 | 98.89% |
| | $^{13}_6C$ | 6 | 7 | 13 | 1.11% |
| | $^{14}_6C$ | 6 | 8 | 14 | Trazas (radiactivo) |
| Cloro | $^{35}_{17}Cl$ | 17 | 18 | 35 | 75.78% |
| | $^{37}_{17}Cl$ | 17 | 20 | 37 | 24.22% |

#### Masa atómica promedio

La masa atómica que aparece en la tabla periódica es el **promedio ponderado** de las masas de todos los isótopos según su abundancia natural:

$$\text{Masa atómica} = \sum_{i} (m_i \times \%_i)$$

**Ejemplo (Cloro)**: 
$$\text{Masa atómica del Cl} = (34.969 \text{ u} \times 0.7578) + (36.966 \text{ u} \times 0.2422) = 35.45 \text{ u}$$

### Iones

Un **ion** es un átomo o grupo de átomos con carga eléctrica neta por haber ganado o perdido electrones.

- **Catión**: ion con carga positiva (perdió electrones). Ej: $Na^+$, $Ca^{2+}$, $Al^{3+}$, $Fe^{2+}$, $Fe^{3+}$.
- **Anión**: ion con carga negativa (ganó electrones). Ej: $Cl^-$, $O^{2-}$, $N^{3-}$, $S^{2-}$.

> [!TIP]
> Los metales tienden a formar cationes (pierden electrones), mientras que los no metales tienden a formar aniones (ganan electrones). Esto está relacionado con la energía de ionización y la afinidad electrónica.

---

## Fórmulas importantes

- **Número másico**: $A = Z + N$
- **Energía del electrón en el átomo de H** (modelo de Bohr): $\displaystyle E_n = -\frac{R_H}{n^2} = -\frac{2.18 \times 10^{-18} \text{ J}}{n^2}$
- **Transición electrónica**: $\displaystyle \Delta E = h\nu = R_H \left( \frac{1}{n_f^2} - \frac{1}{n_i^2} \right)$
- **Constante de Rydberg**: $R_H = 2.18 \times 10^{-18} \text{ J} = 109678 \text{ cm}^{-1}$
- **Relación longitud de onda - energía**: $\displaystyle E = h\nu = \frac{hc}{\lambda}$
- **Principio de incertidumbre**: $\displaystyle \Delta x \cdot \Delta p \ge \frac{h}{4\pi}$

---

## Teoría

- **Unidad 2 (primera parte)** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/UNIDAD 2 (PRIMERA PARTE) - 2025.pdf`
- **Unidad 2 (segunda parte)** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/UNIDAD 2 (SEGUNDA PARTE).pdf`
- **Teoría hasta modelo de Bohr** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/Teoría para el evaluable -Unidad II - Hasta modelo de Bohr (1).pdf`
- **Teoría modelo atómico mecánica cuántica** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/Teoría para el evaluable unidad II modelo atómico de la mecánica cuántica.pdf`
- **Estructura electrónica y Bohr (Brown)** → `Raw/material y ejercicios (profes)/InQ/Unidad 2 Estructura Electronica de los atomos y modelo de Bohr Autor Brown.pdf`
- **Brown - Unidad 1 y 2** → `Raw/material y ejercicios (profes)/InQ/Unidad 1 y 2  Química Brown.pdf`
- **Enriquecimiento de isótopos de Silicio** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/enriquecimiento de isótopos de Silicio artículo 2016.pdf`
- **U2 clase I y II** (Chang) → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U2 clase I.pdf` y `U2 clase II.pdf`
- **U2 estructura atómica I y II** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U2 estructura atómica I.pdf` y `U2 estructura atómica II.pdf`

### Libros de referencia
- **Brown** Capítulos 2 (Átomos, moléculas e iones) y 6 (Estructura electrónica de los átomos)
- **Chang** Capítulos 2 (Átomos, moléculas e iones) y 7 (Estructura electrónica de los átomos)

---

## Ejercicios

- **Ejercicios Unidad II Parte 1** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/IQ EJERCICIOS  Unidad II. Parte 1.pdf`
- **Ejercicios Unidad II Parte 1 (resuelto)** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/Ejercicios  - Unidad II. Parte 1 Resuelto (1).pdf`
- **Ejercicios Unidad II Parte 2** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/IQEJERCICIOS UNIDAD 2Parte 2.pdf`
- **Resolución Unidad II Parte 2** → `Raw/material y ejercicios (profes)/InQ/Unidad 2/Unidad II. Parte 2 - resolución (2).pdf`
- **TP 2 I** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 2 I.pdf`
- **TP 2 I soluciones** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 2 I soluciones .pdf`
- **TP 2 II** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 2 II.pdf`
- **TP 2 II soluciones** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 2 II soluciones .pdf`

---

> [!NOTE] 📍 Navegación del tema
> **Tema anterior:** [[Quim_Sistemas_Materiales]]
> **Tema siguiente:** [[Quim_Tabla_Periodica]]
