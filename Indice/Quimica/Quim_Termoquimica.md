> [!INFO] Conexiones de la Red
> Eje: [[Eje_Quimica]] • Anterior: [[Quim_Estequiometria]]
> Requisitos: [[Eje_Analisis_Matematico]] (integrales para calorimetría)

# Termoquímica

## Índice

==toc==

---

Calorimetría, entalpía, reacciones exotérmicas y endotérmicas, ley de Hess, primera ley de la termodinámica aplicada a sistemas químicos.

---

## Conceptos clave

### Calor y temperatura: diferencia fundamental

- **Calor ($Q$):** energía térmica en tránsito entre dos cuerpos a distinta temperatura. Es una forma de transferencia de energía.
- **Temperatura ($T$):** medida de la energía cinética promedio de las partículas de un sistema.

**Unidades de energía:**
- **Joule (J):** unidad SI. $1 \text{ J} = 1 \text{ kg} \cdot \text{m}^2/\text{s}^2$
- **Caloría (cal):** $1 \text{ cal} = 4.184 \text{ J}$ (exactamente)
- **Kilocaloría (kcal):** $1 \text{ kcal} = 1000 \text{ cal} = 4184 \text{ J}$

**Capacidad calorífica ($C$):** cantidad de calor necesaria para elevar 1°C (o 1 K) la temperatura de un cuerpo.
$$C = \frac{Q}{\Delta T} \quad [\text{J/°C}]$$

**Calor específico ($c$ o $c_e$):** capacidad calorífica por unidad de masa.
$$c = \frac{Q}{m \cdot \Delta T} \quad [\text{J/(g·°C)}]$$

| Sustancia | Calor específico (J/g·°C) |
|:----------|:-------------------------:|
| Agua ($l$) | 4.184 |
| Hielo ($s$) | 2.09 |
| Vapor ($g$) | 2.01 |
| Aluminio ($s$) | 0.90 |
| Hierro ($s$) | 0.45 |
| Cobre ($s$) | 0.39 |

> [!TIP] El agua como referencia
> El agua tiene el calor específico más alto entre los líquidos comunes (4.184 J/g·°C). Esto la hace ideal como refrigerante y explica por qué los climas costeros tienen temperaturas más moderadas.

---

### Calorimetría

La **calorimetría** es la medición experimental de los cambios de calor en procesos químicos y físicos.

**Ecuación fundamental:**
$$Q = m \cdot c \cdot \Delta T$$

Donde:
- $Q$ = calor transferido (J o cal)
- $m$ = masa de la sustancia (g)
- $c$ = calor específico (J/g·°C)
- $\Delta T = T_f - T_i$ = cambio de temperatura (°C o K)

**El calorímetro:** Dispositivo aislado térmicamente que mide el calor intercambiado. En un calorímetro ideal:

$$Q_{\text{absorbido}} + Q_{\text{cedido}} = 0$$

> [!EXAMPLE] Calorimetría
> Se calientan 50.0 g de hierro a 80°C y se introducen en 100 g de agua a 20°C en un calorímetro. La temperatura final de equilibrio es 22.5°C. Calcular el calor específico del hierro.
>
> **Solución:**
> $Q_{\text{ganado por agua}} = m_{\text{agua}} \cdot c_{\text{agua}} \cdot \Delta T_{\text{agua}}$
> $Q_{\text{agua}} = 100 \text{ g} \times 4.184 \text{ J/g·°C} \times (22.5 - 20)\text{°C} = 1046 \text{ J}$
>
> Por conservación de la energía: $Q_{\text{perdido por Fe}} = -Q_{\text{ganado por agua}} = -1046 \text{ J}$
>
> $c_{Fe} = \frac{Q_{Fe}}{m_{Fe} \cdot \Delta T_{Fe}} = \frac{-1046 \text{ J}}{50 \text{ g} \times (22.5 - 80)\text{°C}} = 0.364 \text{ J/g·°C}$

---

### Entalpía ($\Delta H$)

La **entalpía ($H$)** es una función de estado que representa el contenido calórico de un sistema a presión constante.

$$H = U + PV$$

Para procesos a **presión constante** (la mayoría de las reacciones químicas en laboratorio):

$$\Delta H = Q_p$$

Donde $Q_p$ es el calor intercambiado a presión constante.

**Reacciones exotérmicas ($\Delta H < 0$):** liberan calor al entorno.
- $CH_4 + 2O_2 \rightarrow CO_2 + 2H_2O \quad \Delta H = -890 \text{ kJ/mol}$

**Reacciones endotérmicas ($\Delta H > 0$):** absorben calor del entorno.
- $N_2 + O_2 \rightarrow 2NO \quad \Delta H = +180.5 \text{ kJ/mol}$

#### Diagramas entálpicos

```
Exotérmica (ΔH < 0):                Endotérmica (ΔH > 0):
                               
Reactivos                        Productos
   |                                |
   |    ΔH < 0                      |    ΔH > 0
   |    (libera calor)              |    (absorbe calor)
   ↓                                ↓
Productos                        Reactivos
```

---

### Ecuaciones termoquímicas

Una **ecuación termoquímica** incluye el cambio de entalpía asociado a la reacción. Debe indicar:

1. **Estado físico** de cada reactivo y producto (influye en $\Delta H$).
2. **Coeficientes estequiométricos** (el $\Delta H$ es proporcional a la cantidad de sustancia).
3. **Condiciones** de presión y temperatura (si no se especifica: 25°C y 1 atm = estado estándar).

**Ejemplos:**

$$2H_{2(g)} + O_{2(g)} \rightarrow 2H_2O_{(l)} \quad \Delta H = -571.6 \text{ kJ}$$
$$H_{2(g)} + \frac{1}{2}O_{2(g)} \rightarrow H_2O_{(l)} \quad \Delta H = -285.8 \text{ kJ}$$

> [!WARNING] Atención
> El $\Delta H$ depende de los coeficientes. La segunda ecuación tiene la mitad de $\Delta H$ porque usa la mitad de las cantidades. También depende del estado físico: $H_2O_{(l)} \rightarrow H_2O_{(g)}$ requiere energía adicional ($\Delta H_{vap} = +44 \text{ kJ/mol}$).

---

### Ley de Hess

> **"El cambio de entalpía de una reacción global es la suma de los cambios de entalpía de las etapas individuales, independientemente del camino seguido."**

Esto es posible porque $\Delta H$ es una **función de estado**: solo depende del estado inicial y final, no del camino.

**Reglas para aplicar la Ley de Hess:**
1. Si una ecuación se **invierte**, el signo de $\Delta H$ cambia.
2. Si una ecuación se **multiplica** por un factor, $\Delta H$ se multiplica por el mismo factor.
3. Las ecuaciones parciales se **suman** (reactivos + reactivos, productos + productos), y sus $\Delta H$ también.

> [!EXAMPLE] Ley de Hess
> Calcular $\Delta H$ para la reacción:
> $$C_{(s)} + \frac{1}{2}O_{2(g)} \rightarrow CO_{(g)}$$
>
> Conocidas:
> (1) $C_{(s)} + O_{2(g)} \rightarrow CO_{2(g)} \quad \Delta H_1 = -393.5 \text{ kJ}$
> (2) $CO_{(g)} + \frac{1}{2}O_{2(g)} \rightarrow CO_{2(g)} \quad \Delta H_2 = -283.0 \text{ kJ}$
>
> Invertimos (2): $CO_{2(g)} \rightarrow CO_{(g)} + \frac{1}{2}O_{2(g)} \quad \Delta H_2' = +283.0 \text{ kJ}$
>
> Sumando (1) + (2'): $C_{(s)} + O_2 + CO_2 \rightarrow CO_2 + CO + \frac{1}{2}O_2$
> Simplificando: $C_{(s)} + \frac{1}{2}O_{2(g)} \rightarrow CO_{(g)}$
> $\Delta H = -393.5 + 283.0 = -110.5 \text{ kJ}$

---

### Entalpías de formación estándar ($\Delta H_f^\circ$)

La **entalpía de formación estándar** ($\Delta H_f^\circ$) es el cambio de entalpía cuando se forma **1 mol de un compuesto** a partir de sus **elementos en su forma más estable** en condiciones estándar (1 atm, 25°C = 298.15 K).

- Los elementos en su forma más estable tienen $\Delta H_f^\circ = 0$ por definición.
  - $O_{2(g)}$, $H_{2(g)}$, $N_{2(g)}$, $C_{(grafito)}$, $Fe_{(s)}$

#### Tabla de entalpías de formación estándar (kJ/mol)

| Compuesto | $\Delta H_f^\circ$ (kJ/mol) |
|:----------|:---------------------------:|
| $H_2O_{(l)}$ | -285.8 |
| $H_2O_{(g)}$ | -241.8 |
| $CO_{2(g)}$ | -393.5 |
| $CO_{(g)}$ | -110.5 |
| $CH_{4(g)}$ | -74.8 |
| $C_2H_{6(g)}$ | -84.7 |
| $C_2H_{4(g)}$ | +52.3 |
| $C_2H_{2(g)}$ | +227.0 |
| $NH_{3(g)}$ | -46.1 |
| $HCl_{(g)}$ | -92.3 |
| $SO_{2(g)}$ | -296.8 |
| $SO_{3(g)}$ | -395.7 |
| $NO_{(g)}$ | +90.3 |

**Cálculo de $\Delta H^\circ$ de reacción a partir de $\Delta H_f^\circ$:**

$$\Delta H^\circ_{\text{reacción}} = \sum \Delta H_f^\circ(\text{productos}) - \sum \Delta H_f^\circ(\text{reactivos})$$

> [!EXAMPLE] Cálculo con $\Delta H_f^\circ$
> Calcular $\Delta H^\circ$ para la combustión del metano:
> $$CH_{4(g)} + 2O_{2(g)} \rightarrow CO_{2(g)} + 2H_2O_{(l)}$$
>
> $\Delta H_f^\circ(CH_4) = -74.8 \text{ kJ/mol}$
> $\Delta H_f^\circ(CO_2) = -393.5 \text{ kJ/mol}$
> $\Delta H_f^\circ(H_2O_{(l)}) = -285.8 \text{ kJ/mol}$
> $\Delta H_f^\circ(O_2) = 0 \text{ kJ/mol}$
>
> $\Delta H^\circ = [1 \times (-393.5) + 2 \times (-285.8)] - [1 \times (-74.8) + 2 \times 0]$
> $\Delta H^\circ = (-393.5 - 571.6) - (-74.8)$
> $\Delta H^\circ = -965.1 + 74.8 = -890.3 \text{ kJ}$
>
> La combustión del metano libera 890.3 kJ por cada mol de $CH_4$.

---

### Primera ley de la termodinámica

$$\Delta U = Q + W$$

Donde:
- $\Delta U$ = cambio en la energía interna del sistema
- $Q$ = calor intercambiado (positivo si el sistema absorbe calor)
- $W$ = trabajo realizado **sobre** el sistema (positivo si se comprime al sistema)

**Convención de signos:**

| Proceso | Signo | Ejemplo |
|:--------|:----:|:--------|
| Calor absorbido por el sistema | $Q > 0$ | Reacción endotérmica |
| Calor liberado por el sistema | $Q < 0$ | Reacción exotérmica |
| Trabajo realizado sobre el sistema | $W > 0$ | Compresión |
| Trabajo realizado por el sistema | $W < 0$ | Expansión |

**Relación entre $\Delta U$ y $\Delta H$:**

Para procesos a **presión constante** (la mayoría de las reacciones):

$$\Delta H = \Delta U + P\Delta V$$

Donde $P\Delta V$ es el trabajo de expansión/compresión. Para reacciones sin gases o con igual número de moles gaseosos, $\Delta V \approx 0$, entonces $\Delta H \approx \Delta U$.

---

## Fórmulas importantes

- **Calor transferido**: $Q = m \cdot c \cdot \Delta T$
- **Conservación en calorímetro**: $Q_{\text{abs}} + Q_{\text{ced}} = 0$
- **Entalpía a presión constante**: $\Delta H = Q_p$
- **Ley de Hess**: $\Delta H_{\text{total}} = \sum \Delta H_{\text{etapas}}$
- **Entalpía de reacción desde $\Delta H_f^\circ$**: $\Delta H^\circ_{\text{rxn}} = \sum n_p \Delta H_f^\circ(\text{prod}) - \sum n_r \Delta H_f^\circ(\text{react})$
- **Primera ley**: $\Delta U = Q + W$

---

## Teoría

- **Termoquímica (Brown)** → `Raw/material y ejercicios (profes)/InQ/Quimica la Ciencia Central (Brown - LeMay - Bursten) termoquímica.pdf`
- **Termoquímica primera parte** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/TERMOQUIMICA primera parte.pdf`
- **Termodinámica - Termoquímica** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/Termodinámica-Termoquimica.pdf`
- **CALORIMETRÍA FINAL** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/CALORIMETRÍA FINAL.pdf`
- **Ley de Hess** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/LEY de HESS.pdf`
- **Diapositivas termoquímica** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/Dispositivas sobre termoquímica  (1).pdf`
- **U8 termoquímica** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U8 termoquimica.pdf`
- **U8 calorimetría** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U8 calorimetría.pdf`
- **U8 ley de Hess** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/TEORIA/U8 ley de hess.pdf`

### Libros de referencia
- **Brown** Capítulo 5 (Termoquímica)
- **Chang** Capítulo 6 (Termoquímica)

---

## Ejercicios

- **Ejercicios Unidad VIII** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/EJERCICIOS IQ UNIDAD 8.pdf`
- **Respuestas Unidad VIII** → `Raw/material y ejercicios (profes)/InQ/Unidad 8/Ejercicios para resolver en Introducción a la química -RESPUESTAS - Unidad VIII.pdf`
- **TP 8** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 8.pdf`
- **TP 8 soluciones** → `Raw/material y ejercicios (randoms)/1 quimica/Introducción a la química/PRACTICA/tps y soluciones/TP 8 soluciones.pdf`

---

> [!NOTE] 📍 Navegación del tema
> **Tema anterior:** [[Quim_Estequiometria]]
> **Tema siguiente:** (último tema de la etapa 1 — siguientes: etapa de Química General e Inorgánica)

---

> [!WARNING] Conexión importante
> La termoquímica es el puente entre la química y la física. Los conceptos de energía, calor y trabajo que ves acá son la base de la termodinámica que vas a ver en [[Eje_Fisica]] y materias como Termodinámica y Máquinas Térmicas más adelante. También usa herramientas de [[Eje_Analisis_Matematico]] (integrales para capacidad calorífica).
