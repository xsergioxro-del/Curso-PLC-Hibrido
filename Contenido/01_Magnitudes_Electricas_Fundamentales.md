# 📖 CAPÍTULO 1: MAGNITUDES ELÉCTRICAS FUNDAMENTALES

> **🎯 Autor:** Especialista en Automatización Industrial  
> **⏱️ Duración:** 5-6 horas (teoría + ejercicios)  
> **📊 Nivel:** Principiante → Intermedio

---

## 📌 INTRODUCCIÓN

La comprensión profunda de los principios eléctricos es el fundamento indispensable para cualquier ingeniero de automatización. **Sin importar cuán avanzados sean los sistemas de control**, todos ellos operan bajo las leyes fundamentales de la electricidad descubiertas hace más de 200 años.

### El puente entre teoría y práctica

Un electricista que se transforma en programador PLC debe reconocer que:

> **El código que escribe en TIA Portal será interpretado, al final, como órdenes de voltaje y corriente en los componentes físicos de la máquina.**

No es posible diseñar un sistema de automatización robusto sin comprender cómo se comportan las magnitudes eléctricas bajo diferentes condiciones operativas.

### Propósito de este capítulo

Este no es una revisión superficial. Es una **construcción sólida de conceptos** que serán utilizados repetidamente en los capítulos posteriores. Cada ecuación, cada diagrama, cada tabla ha sido seleccionada porque tendrá **aplicación directa en el diseño de sistemas reales** en el ambiente industrial.

**Objetivo pedagógico:** Transformar conocimiento teórico en herramientas mentales aplicables.

---

## 🎓 OBJETIVOS DEL CAPÍTULO

Al finalizar este capítulo, serás capaz de:

- ✅ **Comprender** los conceptos fundamentales de voltaje, corriente y resistencia y su interrelación mediante la Ley de Ohm
- ✅ **Diferenciar** entre corriente continua (DC) y corriente alterna (AC), analizando sus características y aplicaciones en automatización
- ✅ **Calcular** potencia eléctrica (W, kW) y energía (kWh) en sistemas industriales
- ✅ **Identificar** los efectos del campo magnético en dispositivos electromagnéticos (relés, bobinas, transformadores)
- ✅ **Aplicar** las leyes de Kirchhoff para analizar circuitos simples con múltiples componentes
- ✅ **Dimensionar** correctamente calibres de conductor y protecciones para sistemas de control
- ✅ **Reconocer** y prevenir problemas de compatibilidad electromagnética (EMC) en sistemas PLC

---

## 📑 TABLA DE CONTENIDOS

1. [Conceptos Fundamentales](#sección-1-conceptos-fundamentales)
2. [Ley de Ohm y Análisis](#sección-2-ley-de-ohm-y-análisis-de-circuitos)
3. [DC vs AC](#sección-3-corriente-continua-dc-vs-corriente-alterna-ac)
4. [Potencia Eléctrica](#sección-4-potencia-eléctrica)
5. [Magnetismo](#sección-5-magnetismo-y-electromagnetismo)
6. [Cálculos Prácticos](#sección-6-cálculos-prácticos-en-sistemas-de-automatización)
7. [Ejercicios](#ejercicios-prácticos)
8. [Errores Habituales](#errores-habituales-y-soluciones)

---

# 🔌 SECCIÓN 1: CONCEPTOS FUNDAMENTALES

## 1.1 Voltaje Eléctrico (Tensión)

### Definición

> **El voltaje (o tensión o potencial eléctrico) es la diferencia de potencial eléctrico entre dos puntos de un circuito. Representa la energía por unidad de carga disponible para impulsar los electrones.**

**Unidad de medida:** Volt (V)  
**Símbolo:** $V$ o $E$

### Analogía hidráulica

Imagina una tubería con agua a diferentes alturas:

```
ALTURA (Presión)           VOLTAJE (Tensión)

  ┌────────────┐              ┌─────────┐
  │            │ h=10m        │ + 100V  │
  │   AGUA     │              │ (Batería)
  │            │              │         │
  └────────────┴──────        └─────────┴──────
              nivel = 0              GND (0V)
              
La diferencia de altura impulsa el agua
La diferencia de voltaje impulsa los electrones
```

**Tipos de voltaje en sistemas de automatización:**

| Tipo | Valor | Aplicación | Ejemplo |
|------|-------|-----------|---------|
| **Ultra-baja tensión** | < 24V | Señales de control seguras | Sensor inductivo M30 |
| **Baja tensión (Segment 1)** | 24-50V | Lógica de control | Fuente de alimentación PLC |
| **Baja tensión (Segment 2)** | 50-1000V | Circuitos de potencia | Motor de máquina herramienta |
| **Alta tensión** | > 1000V | Transmisión industrial | Línea de distribución |

**Ejemplo real - Sistema de control típico:**

```
SISTEMA DE DISTRIBUCIÓN INDUSTRIAL:

Línea de distribución (380V / 3 fases)
           │
           ▼
    ┌──────────────┐
    │ Transformador│  380V AC → 24V DC
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │ Rectificador │
    │  y Filtrado  │
    └──────┬───────┘
           │
           ▼
        24V DC
     (segura para PLC)
```

## 1.2 Corriente Eléctrica (Intensidad)

### Definición

> **La corriente eléctrica es el flujo de cargas eléctricas (electrones) a través de un conductor. Es la cantidad de carga que pasa por una sección transversal por unidad de tiempo.**

**Unidad de medida:** Ampere (A)  
**Símbolo:** $I$

### Fórmula fundamental

$$I = \frac{Q}{t}$$

Donde:
- $I$ = Corriente (A)
- $Q$ = Carga eléctrica (Culombios, C)
- $t$ = Tiempo (segundos, s)

**Orden de magnitud de corrientes típicas:**

| Componente | Corriente | Observación |
|-----------|-----------|---|
| LED indicador | 20 mA | Muy bajo |
| Sensor inductivo M30 | 100-200 mA | Bajo |
| Bobina de válvula solenoide | 0.5-1 A | Medio |
| Motor trifásico pequeño | 5-50 A | Alto |
| Horno industrial | 100-500 A | Muy alto |

**Ejemplo real - Dimensionamiento de fuente de alimentación:**

```
CÁLCULO DE CORRIENTE TOTAL:

Componentes a alimentar con 24V DC:
• PLC S7-1200:              1.5 A
• 4 × Sensores inductivos:  4 × 0.2 A = 0.8 A
• 3 × Válvulas solenoides:  3 × 0.8 A = 2.4 A
• Módulo de comunicación:   0.3 A
────────────────────────────────────
Corriente total:            5.0 A

Fuente seleccionada: 24V / 10A (con factor de seguridad 2x)
```

## 1.3 Resistencia Eléctrica

### Definición

> **La resistencia eléctrica es la oposición que presenta un material al paso de la corriente eléctrica. Es una propiedad intrínseca del material.**

**Unidad de medida:** Ohm (Ω)  
**Símbolo:** $R$

### Fórmula fundamental (Resistencia de material)

$$R = \rho \cdot \frac{L}{A}$$

Donde:
- $R$ = Resistencia (Ω)
- $\rho$ = Resistividad del material (Ω·mm²/m)
- $L$ = Longitud del conductor (m)
- $A$ = Área de sección transversal (mm²)

**Resistividad de materiales comunes:**

| Material | Resistividad (Ω·mm²/m) | Observación |
|----------|---|---|
| **Plata** | 0.016 | Mejor conductor (muy caro) |
| **Cobre** | 0.017 | Estándar industrial |
| **Aluminio** | 0.028 | Más económico, más voluminoso |
| **Acero** | 0.12 | Pobre conductor |
| **Carbón** | 35-45 | Semiconductor |
| **Vidrio** | 10^15 | Aislante prácticamente perfecto |

**Ejemplo real - Dimensionamiento de cables para un motor:**

```
CÁLCULO DE CALIBRE DE CONDUCTOR:

Motor trifásico:
• Potencia: 11 kW
• Voltaje: 380V
• Corriente (I = P/(√3·V·cosϕ)): 
  I = 11000/(1.732 × 380 × 0.9) ≈ 23 A

Criterio de dimensionamiento:
• Voltaje de caída máximo permitido: 3% de 380V = 11.4V
• Voltaje de caída por fase: 11.4V / √3 ≈ 6.6V

De tabla de conductores:
• Conductor: AWG 8 (8.4 mm²) → Corriente admisible: 40A ✓
• Resistencia del conductor: 2.1 Ω/km
• Con longitud 100m: R = 2.1 × 0.1 = 0.21 Ω

Verificación de caída de voltaje:
V_caída = I × R = 23 × 0.21 = 4.83V ✓ (menor a 6.6V)
```

---

# ⚡ SECCIÓN 2: LEY DE OHM Y ANÁLISIS DE CIRCUITOS

## 2.1 La Ley de Ohm

### Enunciado

> **La diferencia de potencial (voltaje) en un conductor es proporcional a la corriente que lo atraviesa, siendo la resistencia la constante de proporcionalidad.**

### Fórmula matemática

$$V = I \cdot R$$

O en sus variaciones equivalentes:

$$I = \frac{V}{R} \quad ; \quad R = \frac{V}{I}$$

**Representación gráfica (Triángulo de Ohm):**

```
     ┌─────────┐
     │    V    │
     │ = I × R │
     └────┬────┘
          │
    ┌─────┴──────┐
    │             │
    ▼             ▼
┌───────────┐ ┌───────────┐
│  I=V/R    │ │  R=V/I    │
└───────────┘ └───────────┘
```

**Aplicación práctica - Circuito de sensor inductivo:**

```
CIRCUITO CON SENSOR INDUCTIVO M30:

Fuente:
    24V DC
      │
      ├───┬─────────┐
      │   │         │
     [R] [M30]    [Protección]
      │   │         │
      └───┴─────────┘
          │
          0V (GND)

Análisis con Ley de Ohm:
• Voltaje de fuente: V = 24V
• Corriente nominal del sensor: I = 200 mA = 0.2A
• Resistencia equivalente: R = V/I = 24/0.2 = 120 Ω

Verificación:
Si el sensor se activa y su resistencia interna baja a 50 Ω:
• Nueva corriente: I = 24/50 = 0.48A (dentro del límite de 500mA)
```

## 2.2 Leyes de Kirchhoff

### Primera Ley de Kirchhoff (Ley de Corriente)

La suma de corrientes que entran a un nodo es igual a la suma de corrientes que salen del mismo nodo.

$$\sum I_{entrada} = \sum I_{salida}$$

**Aplicación - Análisis de línea de sensores:**

```
LÍNEA DE 3 SENSORES EN PARALELO:

         ┌── Sensor 1 (I₁=100mA) ──┐
Fuente──┤── Sensor 2 (I₂=150mA) ───┤── GND
         └── Sensor 3 (I₃=200mA) ──┘

Por Ley de Kirchhoff:
I_total = I₁ + I₂ + I₃ = 100 + 150 + 200 = 450 mA

Fuente requerida: 24V / 0.45A (mínimo 22.5W)
```

### Segunda Ley de Kirchhoff (Ley de Voltaje)

La suma algebraica de voltajes alrededor de cualquier malla cerrada es cero.

$$\sum V = 0$$

**Aplicación - Verificación de caída de voltaje:**

```
CIRCUITO CON RESISTENCIA SERIE:

    24V
     │
     ├─ Fuente
     │
    [R_cable] = 0.5 Ω
     │
    [Motor] = 20Ω
     │
     ├─ 0V (GND)

Circulación de corriente:
I = V_total / R_total = 24 / (0.5 + 20) = 1.14A

Voltajes en componentes:
• V_cable = I × R_cable = 1.14 × 0.5 = 0.57V
• V_motor = I × R_motor = 1.14 × 20 = 22.8V
• Total: 0.57 + 22.8 = 23.37V ≈ 24V ✓

El motor recibe solo 22.8V (95% de voltaje nominal)
```

---

# 🔄 SECCIÓN 3: CORRIENTE CONTINUA (DC) VS CORRIENTE ALTERNA (AC)

## 3.1 Corriente Continua (DC - Direct Current)

### Características

- Flujo de electrones en una única dirección
- Voltaje constante en el tiempo
- Típicamente generada por pilas, baterías o fuentes rectificadas

### Gráfica temporal

```
VOLTAJE DC (24V):

  V
  ▲
24│     ┌─────────────────────
  │     │
12│     │
  │     │
  0│─────┴─────────────────────────▶ t
 -12│
    └──────────────────────────
    
Características:
• Constante en tiempo
• Sin ondulación (idealmente)
• Fácil de usar en electrónica digital
```

### Aplicaciones en automatización

| Aplicación | Voltaje | Razón |
|-----------|---------|-------|
| Lógica de PLC | 24V DC | Seguro, compatible con sensores |
| Sensores inductivos | 24V DC | Detección digital |
| Válvulas solenoides | 24V DC | Bajo consumo, control preciso |
| Bobinas de relés | 24V DC | Seguridad, conmutación rápida |
| Circuitos de seguridad | 24V DC | Aislamiento galvánico |

## 3.2 Corriente Alterna (AC - Alternating Current)

### Características

- El flujo de electrones cambia de dirección periódicamente
- Voltaje varía sinusoidalmente en el tiempo
- Generada naturalmente por alternadores

### Gráfica temporal

```
VOLTAJE AC (220V RMS, 50 Hz):

  V
  ▲
311│        ╱╲        ╱╲
  │       ╱  ╲      ╱  ╲
220│      │    │    │    │   (Valor RMS)
  │      │    │    │    │
  0│─────┼────┼────┼────┼────▶ t
  │      │    │    │    │
 -220│      │    │    │    │
  │       ╲  ╱      ╲  ╱
 -311│        ╲╱        ╲╱
  
Características:
• Cambia de dirección periódicamente
• Frecuencia típica: 50 Hz (europeo) o 60 Hz (americano)
• Período T = 1/f = 1/50 = 20 ms
• Valor pico: 311V (para 220V RMS)
```

### Relación entre valor pico y valor RMS

$$V_{RMS} = \frac{V_{pico}}{\sqrt{2}} = \frac{V_{pico}}{1.414}$$

$$V_{pico} = V_{RMS} \times \sqrt{2} = V_{RMS} \times 1.414$$

### Ventajas de AC

1. Transmisión de energía eficiente a largas distancias
2. Transformación de voltaje mediante transformadores
3. Menores pérdidas en líneas de transmisión

### Desventajas para electrónica digital

1. Requiere rectificación para convertir a DC
2. Más sensible a interferencias electromagnéticas
3. Sincronización más compleja con lógica digital

## 3.3 Circuito Rectificador Típico de PLC

```
CONVERSIÓN AC → DC:

Línea de distribución (380V 3-fase)
      │
      ▼
┌──────────────┐
│ Transformador│ 380V → 24V
└────┬─────────┘
     │
     ▼
   24V AC (sinusoidal)
     │
     ▼
┌─────────────────┐
│ Rectificador de │ Convierte dos semi-ciclos
│ onda completa   │ en uno solo
└────┬────────────┘
     │
     ▼
   24V DC pulsante
     │
     ▼
┌──────────────────┐
│ Capacitor de     │ Suaviza las pulsaciones
│ Filtrado        │
└────┬─────────────┘
     │
     ▼
   24V DC puro (para PLC)

Voltaje de salida:
  V
  ▲
24│    ┌─┐     ┌─┐     ┌─┐
  │   ┌─ ┴─┐  ┌─ ┴─┐  ┌─ ┴─┐
  │   │   │  │   │  │   │
  0│───┼───┼──┼───┼──┼───┼───▶ t
```

---

# ⚙️ SECCIÓN 4: POTENCIA ELÉCTRICA

## 4.1 Potencia en Corriente Continua (DC)

### Definición

> **La potencia eléctrica es la velocidad de transferencia de energía. Es la cantidad de energía por unidad de tiempo.**

**Unidad de medida:** Watt (W), kilowatt (kW)  
**Símbolo:** $P$

### Fórmula fundamental

$$P = V \times I$$

Donde:
- $P$ = Potencia (W)
- $V$ = Voltaje (V)
- $I$ = Corriente (A)

### Variantes de la fórmula usando Ley de Ohm

$$P = I^2 \times R$$

$$P = \frac{V^2}{R}$$

**Ejemplo real - Cálculo de potencia en circuito de sensores:**

```
CIRCUITO CON 4 SENSORES:

Voltaje: 24V DC
Corriente total: 0.8A (4 sensores × 200mA)

Potencia total:
P = V × I = 24 × 0.8 = 19.2 W

Verificación por resistencia:
Resistencia equivalente: R = V/I = 24/0.8 = 30 Ω
P = V²/R = 24²/30 = 576/30 = 19.2 W ✓
```

## 4.2 Potencia en Corriente Alterna (AC)

En AC, la potencia es más compleja debido a la fase entre voltaje y corriente.

**Potencia Aparente:**

$$S = V_{RMS} \times I_{RMS}$$

Unidad: Volt-Ampere (VA)

**Potencia Reactiva:**

$$Q = S \times \sin(\phi)$$

Unidad: Volt-Ampere Reactivo (VAR)

**Potencia Activa (real):**

$$P = S \times \cos(\phi) = V_{RMS} \times I_{RMS} \times \cos(\phi)$$

Unidad: Watt (W)

**Factor de potencia:**

$$\cos(\phi) = \frac{P}{S}$$

**Ejemplo real - Motor industrial trifásico:**

```
ESPECIFICACIÓN DE MOTOR:
• Potencia nominal: 11 kW (en placa del motor)
• Voltaje de red: 380V (trifásico, 50Hz)
• Corriente nominal: 23A (en placa del motor)
• Factor de potencia: 0.92 (cos φ)
• Rendimiento del motor: 92% típico

ANÁLISIS DE POTENCIAS:
S = √3 × V × I = 1.732 × 380 × 23 = 15,200 VA = 15.2 kVA (aparente)
P_activa = S × cos(φ) = 15,200 × 0.92 = 13,984 W ≈ 14 kW (real)
Q_reactiva = S × sin(φ) = 15,200 × 0.391 = 5,942 VAR

DESGLOSE REAL:
• Potencia aparente demandada: 15.2 kVA
• Potencia activa (trabajo + pérdidas): 14 kW
• Potencia reactiva (magnetización): 5.9 kVAR
• Potencia mecánica en eje: 14 × 0.92 = 12.88 kW
• Pérdida térmica en bobinas: 14 - 12.88 = 1.12 kW

CONCLUSIÓN: Solo 12.88 kW de los 15.2 kVA demandados
se convierten en trabajo mecánico útil.
```

## 4.3 Energía Eléctrica

**Definición:**

La energía es la capacidad para realizar trabajo. Es la potencia integrada en el tiempo.

**Unidad de medida:** Joule (J), kilowatt-hora (kWh)  
**Símbolo:** $E$

**Fórmula fundamental:**

$$E = P \times t$$

Donde:
- $E$ = Energía (J o kWh)
- $P$ = Potencia (W o kW)
- $t$ = Tiempo (s u h)

**Conversión de unidades:**

$$1 \text{ kWh} = 1 \text{ kW} \times 1 \text{ h} = 3.6 \times 10^6 \text{ J}$$

**Ejemplo real - Consumo energético de máquina de producción:**

```
CÁLCULO DE CONSUMO DIARIO:

Máquina de etiquetado:
• Potencia: 5 kW
• Tiempo de operación por turno: 8 horas
• Turnos por día: 2

Energía diaria:
E = P × t = 5 kW × 16 h = 80 kWh

Costo energético (tarifa: $0.15/kWh):
Costo = 80 × 0.15 = $12 por día
       = $360 por mes (30 días)
       = $4,320 por año

Mejora propuesta: Reducir consumo 10% con motor de eficiencia
Ahorro: $432 por año
```

---

# 🧲 SECCIÓN 5: MAGNETISMO Y ELECTROMAGNETISMO

## 5.1 Campo Magnético Fundamental

**Definición:**

Un campo magnético es la región del espacio donde se ejerce una fuerza sobre cargas móviles o sobre materiales magnéticos.

**Unidad de medida:** Tesla (T)  
**Símbolo:** $B$

**Fuentes de campo magnético:**

1. **Imanes permanentes** - Estructuras de hierro con orientación molecular
2. **Corriente eléctrica** - Flujo de electrones crea campo magnético

**Regla de la mano derecha:**

Metodología para determinar dirección del campo magnético según corriente:

```
PARA CONDUCTOR RECTO:

Mano derecha:
- Pulgar: Dirección de corriente I
- Dedos curvados: Dirección de B (campo)

         I (corriente ↑)
         │
    ┌────┴────┐
    │ ALAMBRE │
    │         │  Campo B gira en círculos:
    └────┬────┘  ⊙ (hacia afuera de página)
         │       ⊗ (hacia adentro de página)
```

**APLICACIÓN IMPORTANTE - Bobinas (para relés):**

```
Bobina enrollada con N espiras:

         I ↓ (entrada)
         │
    ╔═══════════╗
    ║ ↻ ↻ ↻ ↻  ║  Método: Dedos rodean bobina
    ║ ↻ ↻ ↻ ↻  ║  siguiendo corriente
    ║ ↻ ↻ ↻ ↻  ║  Pulgar → POLO NORTE
    ║ ↻ ↻ ↻ ↻  ║
    ╚═══════════╝
         ↑ B
         ↑ (NORTE)

IMPORTANCIA CRÍTICA:
✓ Determina dirección de atracción del núcleo
✓ Explica funcionamiento de relés
✓ Esencial para inversión de rotación en motores
✓ Base para electromagnetos industriales
```

## 5.2 Bobina Electromagnética (Electroimán)

Cuando se enrolla un conductor alrededor de un núcleo de hierro, se forma una bobina que genera un campo magnético concentrado.

**Aplicación industrial: Bobina de Relé**

```
ESTRUCTURA DE BOBINA DE RELÉ:

        ╔═══════════════╗
        ║ Enrollamiento ║ (Alambre Cu esmaltado)
        ║   de alambre  ║ n = número de vueltas
        ╠═══════════════╣
        ║               ║
        ║    Núcleo     ║ (Hierro blando)
        ║    de Hierro  ║ μ_r ≈ 1000-2000
        ║               ║
        ╚═══════════════╝
        
PRINCIPIO DE FUNCIONAMIENTO:

Sin corriente (V = 0):
┌──────────┐
│ Contacto │  Abierto (No hay conexión)
│ móvil    │
└─────┬────┘

Con corriente (V = 24V):
┌──────────┐
│          │  Se atrae hacia imán
│ Contacto │
│ móvil    │
└─────┬────┘
      ▼
    ╔═══════╗
    ║ Imán  ║ (Campo magnético atrae)
    ╚═══════╝
```

**Parámetros típicos de bobina de relé:**

| Parámetro | Valor | Unidad |
|-----------|-------|--------|
| Voltaje nominal | 24 | VDC |
| Corriente nominal | 0.5 | A |
| Potencia nominal | 12 | W |
| Número de espiras | ~800 | spiras |
| Resistencia DC | 48 | Ω |
| Inductancia | ~50 | mH |
| Tiempo de conmutación | 10 | ms |
| Fuerza magnética máxima | 200 | N |

## 5.3 Inductor y Fenómeno de Autoinducción

**Concepto:**

Cuando cambia la corriente en una bobina, el campo magnético cambia, lo que induce un voltaje que se opone al cambio (Ley de Faraday).

**Ley de Faraday:**

$$V_{inducido} = -L \frac{dI}{dt}$$

Donde:
- $V_{inducido}$ = Voltaje inducido (V)
- $L$ = Inductancia de la bobina (H - Henry)
- $\frac{dI}{dt}$ = Velocidad de cambio de corriente (A/s)

**Constante de tiempo de bobina:**

$$\tau = \frac{L}{R}$$

Donde τ (tau) es la constante de tiempo en segundos. Define la velocidad de crecimiento/decrecimiento de corriente en la bobina. Ejemplos típicos:
- Bobinas de relé: τ = 1-5 ms
- Bobinas de contactores: τ = 5-50 ms

**Implicación práctica - Pico de voltaje al desconectar:**

```
SURGE (PICO) AL DESCONECTAR BOBINA:

Situación: Bobina de relé energizada con 24V, 0.5A

CONEXIÓN (t=0):
   ┌──────┐
   │Switch│ ON
   └───┬──┘
       │
       R (relé, L=50mH)
       │
      GND

Corriente sube gradualmente según ecuación exponencial:
$$I(t) = \frac{V}{R} \times (1 - e^{-t/\tau})$$

Donde:
- τ = L/R = 50mH/48Ω ≈ 1.04 ms (constante de tiempo)
- V/R = 24V/48Ω = 0.5 A (corriente final)

Tiempos característicos:
- t = τ (1 ms): I alcanza 63% de 0.5A = 0.315 A
- t = 3τ (3 ms): I alcanza 95% de 0.5A = 0.475 A  
- t = 5τ (5 ms): I alcanza 99% de 0.5A = 0.495 A ≈ establecida


DESCONEXIÓN (conmutador abierto):

ESCENARIO SIN PROTECCIÓN (PELIGROSO):
┌────────────────────────────────────────────────┐
│ Al abrir switch: L·dI/dt equilibra con fuente  │
│ V_inducido = -L × dI/dt                        │
│                                                │
│ Apertura lenta (~1ms):                         │
│   dI/dt = 500 A/s → V_pico = 25V               │
│   Aceptable si switch > 50V                    │
│                                                │
│ Apertura rápida (~0.1ms):                      │
│   dI/dt = 5,000 A/s → V_pico = 250V            │
│   ¡¡DESTRUCTIVO!!                             │
│                                                │
│ Apertura instantánea (~0.01ms):                │
│   dI/dt = 50,000 A/s → V_pico = 2,500V !!     │
│   ¡¡DAÑO CATASTRÓFICO!!                       │
└────────────────────────────────────────────────┘

SOLUCIÓN 1: Diodo de libre circulación (MÁS USADO EN DC)

    ┌──────┐
    │Switch│
    └───┬──┘
        │      D (Diodo 1N4007)
        ├─────⊳|─────┐
        │             │
        R (relé)     GND
        │             │
        └─────────────┘

Funcionamiento:
✓ Mientras switch cerrado: diodo bloqueado
✓ Al abrir: diodo conduce, bobina descarga lentamente
✓ Corriente disminuye en tiempo τ ≈ 1-5 ms
✓ Voltaje resultante: ~0.6V (caída diodo)
✓ Resultado: SWITCH PROTEGIDO

SOLUCIÓN 2: Varistor/Supresor de transitorios (MEJOR PARA AC)

    ┌──────┐
    │Switch│
    └───┬──┘
        │      MOV (Metal Oxide Varistor)
        ├─────[~~~]─────┐
        │               │
        R (relé)       GND
        │               │
        └───────────────┘

Ventajas vs diodo:
✓ Actúa en AMBAS direcciones (para AC)
✓ Respuesta MÁS RÁPIDA (ns vs ms)
✓ Sin corriente de descarga continua
✓ Más eficiente energéticamente

COMPARATIVA Y SELECCIÓN:

| Solución | DC | AC | Velocidad | Costo | Aplicación |
|----------|---|---|---|---|---|
| Diodo | ✓✓ | ✗ | Media | $ | PLCs, relés DC |
| Varistor | ✓ | ✓✓ | Rápida | $$ | Motores, contactores |
| Diodo+Varistor | ✓✓ | ✓✓ | Excelente | $$$ | Variadores, PWM |

**RECOMENDACIÓN:** 
- En DC (PLC): DIODO de libre circulación
- En AC (motor): VARISTOR
- En equipos críticos: DIODO + VARISTOR
```

---

# 🛠️ SECCIÓN 6: CÁLCULOS PRÁCTICOS EN SISTEMAS DE AUTOMATIZACIÓN

## 6.1 Dimensionamiento de Fuente de Alimentación

**Procedimiento paso a paso:**

**Paso 1:** Identificar todos los componentes a alimentar

```
LISTA DE CARGAS (24V DC):

1. PLC S7-1200:                1.5 A
2. Módulo de comunicación:     0.3 A
3. 5 × Sensores inductivos:    5 × 0.2 A = 1.0 A
4. 3 × Válvulas solenoides:    3 × 0.8 A = 2.4 A
5. Terminales de visualización:0.5 A
6. Reserva para futuras expansiones: 20% = ?

Corriente total (sin reserva): 1.5+0.3+1.0+2.4+0.5 = 5.7 A
```

**Paso 2:** Aplicar factor de seguridad

```
Factor de seguridad típico: 1.25 a 1.5

Con factor 1.25:
I_diseño = 5.7 × 1.25 = 7.1 A

Fuente seleccionada: 24V / 10A
Potencia requerida: P = V × I = 24 × 10 = 240 W
```

**Paso 3:** Considerar caída de voltaje en cables

```
Criterio: Caída máxima 5% de voltaje nominal

5% de 24V = 1.2V

La fuente debe proporcionar:
V_salida_fuente = V_carga + V_caída
                = 24 + 1.2 = 25.2V (mediante ajuste)
```

**Resultado final:**

```
ESPECIFICACIÓN DE FUENTE:
• Tensión nominal: 24V DC
• Potencia mínima: 240W
• Corriente mínima: 10A
• Tipo: Fuente conmutada (SMPS) o lineal
• Protección: Fusible de 10A, disyuntor
```

## 6.2 Cálculo de Calibre de Conductor (Norma IEC 60228)

**Criterios de diseño según aplicación:**

| Aplicación | Caída máxima | Notas |
|-----------|---|---|
| Motores y cargas altas | 3% | Evita sobrecalentamiento |
| Circuitos de control | 5% | Margen para sensibilidad |
| Circuitos de seguridad | 2% | Mayor seguridad |
| Distribución principal | 2-3% | Optimización de energía |

**Factores CRÍTICOS a considerar:**

1. **Temperatura ambiente** (factor corrección: 0.85-1.1)
2. **Método de instalación** (bandeja: ×1.0 | ducto: ×0.8 | enterrado: ×0.7)
3. **Agrupamiento de cables** (más cables = menos capacidad)

**Procedimiento completo con ejemplo 1:**

```
MOTOR AC 11kW @ 380V, 23A, Distancia 150m, Bandeja, 50°C

Paso 1: Voltaje máximo caída permitida (3% para motor)
V_caída_max = 0.03 × 380V = 11.4V

Paso 2: Resistencia máxima admisible
Para trifásica: V_caída = √3 × I × R_conductor × L
R_max = 11.4 / (1.732 × 23 × 0.15 km) = 11.4 / 5.98 = 1.90 Ω/km

Paso 3: Consultar IEC 60228 (cobre a 20°C):
┌──────────┬────────┬─────────┬────────────┐
│ Calibre  │ Área   │ R @ 20°C│ I_admisible│
├──────────┼────────┼─────────┼────────────┤
│ AWG 8    │ 8.4    │ 2.15    │ 35 A       │
│ AWG 6    │ 13.3   │ 1.44 ✓  │ 45 A       │
│ AWG 4    │ 21.2   │ 0.89    │ 60 A       │
└──────────┴────────┴─────────┴────────────┘

Paso 4: Verificación caída real (AWG 6)
V_caída = 1.732 × 23 × 1.44 × 0.15 = 8.63V
Porcentaje: 8.63/380 × 100 = 2.27% ✓ Excelente

Paso 5: Verificación corriente admisible
45A > 23A ✓ OK

RESULTADO: Usar AWG 6 (13.3 mm²) cobre
```

**Ejemplo 2: Circuito de control 24V DC**

```
CONTROL 24V DC, 10A, 50m, 40°C, bandeja

Caída máxima: 5% × 24V = 1.2V
R_requerida: 1.2V / 10A = 0.12 Ω
R_específica: 0.12 / 0.05 km = 2.4 Ω/km

Corregir por temperatura 40°C (factor ~1.05):
R_ajustada: 2.4 / 1.05 = 2.29 Ω/km

Seleccionar de tabla IEC 60228:
AWG 12 (3.3 mm², 5.2 Ω/km): NO - demasiada caída
AWG 10 (5.26 mm², 3.3 Ω/km): NO - marginal
AWG 8 (8.4 mm², 2.1 Ω/km): SÍ ✓

Verificación: V_caída = 10 × 2.1 × 0.05 = 1.05V ✓

RESULTADO: Usar AWG 8 (8.4 mm²)
```

---

# 📝 EJERCICIOS PRÁCTICOS

## Ejercicio 1: Análisis de Circuito Simple

**Enunciado:**

Un circuito de control contiene:
- Fuente: 24V DC
- Sensor inductivo: Resistencia interna 60 Ω
- Resistencia de protección serie: 10 Ω

Calcule:
a) Corriente máxima en el circuito
b) Potencia disipada en el sensor
c) Potencia disipada en la resistencia de protección

**Solución:**

a) Corriente máxima:

$R_{total} = R_{sensor} + R_{protección} = 60 + 10 = 70 \text{ Ω}$

$I = \frac{V}{R} = \frac{24}{70} = 0.343 \text{ A} \approx 343 \text{ mA}$

b) Potencia en sensor:

$P_{sensor} = I^2 \times R_{sensor} = (0.343)^2 \times 60 = 0.118 \times 60 = 7.06 \text{ W}$

c) Potencia en resistencia de protección:

$P_{protección} = I^2 \times R_{protección} = (0.343)^2 \times 10 = 0.118 \times 10 = 1.18 \text{ W}$

Verificación: $P_{total} = P_{sensor} + P_{protección} = 7.06 + 1.18 = 8.24 \text{ W}$

Alternativa: $P_{total} = V \times I = 24 \times 0.343 = 8.23 \text{ W}$ ✓

## Ejercicio 2: Dimensionamiento de Fuente

**Enunciado:**

Dimensione una fuente de alimentación 24V DC para los siguientes componentes:

- 1 PLC S7-1200: 2.0 A (máximo)
- 2 Módulos de comunicación: 0.5 A cada uno
- 8 Sensores inductivos: 0.15 A cada uno
- 4 Válvulas solenoides: 0.6 A cada una
- 2 Motores pequeños (24V): 1.0 A cada uno

Aplicar factor de seguridad de 1.3 y calcular potencia requerida.

**Solución:**

Corriente total sin factor:
```
PLC:              2.0 A
Módulos:          2 × 0.5 = 1.0 A
Sensores:         8 × 0.15 = 1.2 A
Válvulas:         4 × 0.6 = 2.4 A
Motores:          2 × 1.0 = 2.0 A
─────────────────────────
Subtotal:         8.6 A
```

Con factor de seguridad 1.3:

$I_{diseño} = 8.6 \times 1.3 = 11.18 \text{ A}$

Seleccionar fuente estándar: 24V / 15A

Potencia requerida:

$P = V \times I = 24 \times 15 = 360 \text{ W}$

**Especificación final:** Fuente conmutada 24V/15A (360W) con protección

## Ejercicio 3: Caída de Voltaje en Cable

**Enunciado:**

Dimensione el cable para alimentar un motor trifásico (AC 380V) con las siguientes características:
- Potencia: 7.5 kW
- Corriente: 15 A (aproximada)
- Distancia: 100 m
- Caída máxima permitida: 3%

**Solución:**

Voltaje de caída máximo permitido:

$V_{caída\,max} = 0.03 \times 380 = 11.4 \text{ V}$

Para sistema trifásico, la fórmula es:

$V_{caída} = \sqrt{3} \times I \times R \times \frac{L}{1000}$

Donde R es la resistencia específica del conductor (Ω/km)

$11.4 = 1.732 \times 15 \times R \times \frac{100}{1000}$

$11.4 = 0.2598 \times R$

$R = \frac{11.4}{0.2598} = 43.87 \text{ Ω/km}$ máximo

Verificación en tabla de conductores de cobre (IEC 60228):

| Calibre | Sección | Resistencia (Ω/km) | I_max (A) | Caída a 100m | Estado |
|---------|---------|---|---|---|---|
| AWG 10 | 5.26 mm² | 3.6 | 32 | 9.34V | ❌ Marginal |
| **AWG 6** | **13.3 mm²** | **1.44** | **55** | **3.73V** | **✓ Recomendado** |
| AWG 4 | 21.2 mm² | 0.89 | 70 | 2.31V | ✓ Sobredimensionado |

Con AWG 6: $V_{caída\,real} = 1.732 \times 15 \times 1.44 \times 0.1 = 3.73 \text{ V}$ (0.98%)

**Especificación final recomendada:**
- **Cable:** Cobre AWG 6 (13.3 mm²) según IEC 60228
- **Configuración:** 3 fases + neutro + tierra  
- **Protección:** Fusible 20A + Disyuntor 16A
- **Razón del cambio:** AWG 10 es insuficiente a 100m; AWG 6 proporciona seguridad operacional

---

# ⚠️ ERRORES HABITUALES Y SOLUCIONES

## Error 1: Confundir Voltaje y Corriente

**Descripción del error:**

Un técnico intenta aumentar "la potencia" de un motor aumentando el voltaje de suministro de 380V a 410V, esperando mejorar rendimiento.

**Problema:**

- Ley de Ohm: Si V aumenta y la resistencia del motor es aproximadamente constante, la corriente también aumentará
- Mayor corriente → Mayor calentamiento de bobinado
- El motor se daña por sobrecalentamiento

**Solución correcta:**

La potencia mecánica de un motor se controla mediante:
1. Corriente (por Ley de Ohm)
2. Factor de potencia (cosφ)
3. Velocidad (RPM)

Nunca debe aumentarse voltaje arbitrariamente. Los motores están diseñados para rango de voltaje específico (típicamente ±5%).

## Error 2: Olvidar Diodo de Protección en Bobinas

**Descripción del error:**

Se conecta una bobina de relé directamente a un switch de potencia sin protección, y al desconectar aparece un arco violento que daña el switch.

**Problema:**

Al desconectar, la inductancia de la bobina genera un pico de voltaje que puede alcanzar cientos de voltios (como se explicó en sección 5.3).

**Solución correcta:**

```
PROTECCIÓN CON DIODO (Método 1):

    ┌──────┐
    │Switch│
    └───┬──┘
        │      D (Diodo 1N4007)
        ├─────⊳|─────┐
        │             │
        R (relé)     GND
        │             │
        └─────────────┘

El diodo debe estar polarizado para permitir circulación
de corriente a través de la bobina cuando el switch se abre.
```

**Solución alternativa (Protección con resistencia):**

```
PROTECCIÓN CON RESISTENCIA (Método 2):

    ┌──────┐
    │Switch│
    └───┬──┘
        │      R_protect
        ├─────[~~~~~]─────┐
        │                 │
        R (relé)         GND
        │                 │
        └─────────────────┘
```

## Error 3: Ignorar Caída de Voltaje en Cables

**Descripción del error:**

Se alimenta una máquina located a 300 metros de distancia con cable de pequeño calibre. El PLC recibe solo 22V en lugar de 24V, causando comportamiento errático de sensores.

**Problema:**

Resistencia del cable × Corriente = Caída de voltaje

Con cable pequeño y distancia larga, la caída es considerable.

**Solución correcta:**

Siempre calcular caída de voltaje según la fórmula:

$V_{caída} = I \times R = I \times \rho \times \frac{L}{A}$

Y usar cable de calibre suficiente (generalmente +1 o +2 calibres del mínimo requerido por corriente).

## Error 4: No Diferenciar entre Voltaje Pico y RMS en AC

**Descripción del error:**

Se especifica un rectificador "para 220V AC" asumiendo que significa 220V pico, pero el componente falla porque en realidad significa 220V RMS.

**Problema:**

- 220V RMS = 311V pico (×1.414)
- Si se diseña para 220V pico, el componente solo soporta 155V RMS
- Sobrevoltaje causa falla

**Solución correcta:**

En especificaciones industriales, siempre AC se refiere a valor RMS, no pico.

Conversión: $V_{pico} = V_{RMS} \times 1.414$

## Error 5: Suponer Que Dos Circuitos en Paralelo "Suman" Poder de Forma Ilimitada

**Descripción del error:**

Se conectan dos fuentes de 5A en paralelo esperando obtener una fuente de 10A.

**Problema:**

Las dos fuentes deben tener exactamente el mismo voltaje de salida. Si hay diferencia, una fuente entregará potencia a la otra, causando daño.

Además, los capacitores internos de filtrado pueden descargarse uno en el otro.

**Solución correcta:**

No conectar fuentes en paralelo sin equipo especial de sincronización. 

Para obtener mayor capacidad de corriente, reemplazar con una fuente única de mayor capacidad.

---

# 📋 RESUMEN DE CONCEPTOS CLAVE

## Tabla de Referencia Rápida - Fórmulas Fundamentales

| Concepto | Fórmula | Unidades | Aplicación |
|----------|---------|----------|-----------|
| **Ley de Ohm** | $V = I \times R$ | V, A, Ω | Base de todo cálculo eléctrico |
| **Corriente** | $I = \frac{V}{R}$ | A = V/Ω | Dimensionar protecciones |
| **Resistencia** | $R = \rho \cdot \frac{L}{A}$ | Ω = Ω·m · m/m² | Calibre de conductor |
| **Potencia DC** | $P = V \times I = I^2 \times R = \frac{V^2}{R}$ | W | Consumo de componentes |
| **Potencia AC (activa)** | $P = V_{RMS} \times I_{RMS} \times \cos(\phi)$ | W | Motores y cargas |
| **Potencia AC (aparente)** | $S = V_{RMS} \times I_{RMS}$ | VA | Dimensionar fuente |
| **Energía** | $E = P \times t$ | J o kWh | Costo operacional |
| **Caída de voltaje** | $V_{caída} = I \times R = I \times \rho \times \frac{L}{A}$ | V | Dimensionamiento cable |
| **Inductancia** | $\tau = \frac{L}{R}$ | ms | Tiempo transitorio bobina |
| **Voltaje inducido** | $V = -L \frac{dI}{dt}$ | V | Picos de voltaje |

## Concepto Clave: El Triángulo de Potencias en AC

```
        S (Aparente)
        ╱|
       ╱ |
      ╱  | Q (Reactiva)
     ╱   |
    ╱    |
   ╱_____|
    P (Activa)
    
S² = P² + Q²
cos(φ) = P/S (Factor de potencia)
```

## Concepto Clave: Propiedades de Corriente vs Voltaje

| Aspecto | Corriente (I) | Voltaje (V) |
|--------|---|---|
| **Flujo en serie** | Se suma | Se divide |
| **Flujo en paralelo** | Se divide | Se mantiene |
| **Medición** | En serie con circuito | Entre dos puntos |
| **Peligro** | Determina calor/daño | Determina ruptura aislante |
| **En PLC 24V** | ~0.2A (sensores) | Constante 24V |

---

## 10 Conceptos Fundamentales - Resumen Ejecutivo

1. **Voltaje (V):** Diferencia de potencial que impulsa la corriente. Medida en Volts. En automatización: 24V (control) a 380V (potencia).

2. **Corriente (I):** Flujo de electrones a través de un conductor. Medida en Amperes. Crítica: causa calentamiento si excesiva.

3. **Resistencia (R):** Oposición al flujo de corriente. Medida en Ohms. Depende de material, longitud y sección.

4. **Ley de Ohm:** V = I × R. Relación fundamental: si aumenta voltaje y R es constante, aumenta corriente.

5. **Potencia (P):** Velocidad de transferencia de energía. P = V × I. Medida en Watts. Determina tamaño de fuente requerida.

6. **Corriente Continua (DC):** Flujo unidireccional constante. Usada en lógica de PLCs (24V DC estándar).

7. **Corriente Alterna (AC):** Flujo bidireccional sinusoidal. Usada en distribución industrial (380V, 50/60 Hz).

8. **Campo Magnético:** Creado por imanes permanentes o corriente eléctrica. Base de funcionamiento de relés y motores.

9. **Inductancia:** Propiedad de bobinas de almacenar energía magnética. Genera picos de voltaje destructivos al desconectar (requiere protección con diodo).

10. **Caída de Voltaje:** Pérdida de voltaje en cables por resistencia. Crítico: puede causar falla de sensores a distancia. Debe calcularse en diseño (máximo 3% para potencia, 5% para control).

---

# 🎤 PREGUNTAS DE ENTREVISTA

## Nivel Básico

**Pregunta 1:** Explique la relación entre voltaje, corriente y resistencia utilizando la Ley de Ohm con un ejemplo práctico de un sensor.

**Respuesta esperada:**
- Definición clara de Ley de Ohm (V = I × R)
- Ejemplo con números específicos (ej: sensor 24V, 200mA → 120Ω)
- Aplicación a componente real del que habla el candidato

**Pregunta 2:** ¿Cuál es la diferencia entre corriente continua y corriente alterna en sistemas de automatización?

**Respuesta esperada:**
- DC: unidireccional, constante, usada en lógica PLC
- AC: bidireccional sinusoidal, usada en potencia industrial
- Ventajas y desventajas de cada una
- Necesidad de rectificación para convertir AC a DC

## Nivel Intermedio

**Pregunta 3:** Una máquina industrial a 250 metros de distancia recibe solo 21V en lugar de 24V esperados. ¿Cuáles pueden ser las causas y cómo las diagnosticaría?

**Respuesta esperada:**
- Cálculo de caída de voltaje = 3V en 250m
- Posibles causas: cable muy pequeño, corriente excesiva, mala conexión
- Procedimiento de diagnóstico: medir voltaje en diferentes puntos, calcular corriente real, verificar calibre de cable
- Solución: reemplazar con cable de mayor sección

**Pregunta 4:** Describa qué sucede eléctricamente cuando se abre un switch conectado a una bobina de relé sin protección.

**Respuesta esperada:**
- Explicación de inductor y autoinducción
- Cálculo de pico de voltaje usando L × dI/dt
- Peligro de arco y daño de switch
- Solución con diodo de libre circulación

## Nivel Avanzado

**Pregunta 5 (Caso Real):** Diseñe la alimentación eléctrica para una estación de trabajo de embalaje con los siguientes requisitos:

Componentes:
- 1 PLC S7-1500: 3.5A máximo
- 2 Variadores de frecuencia (24V): 0.5A cada uno  
- 12 Sensores inductivos (24V): 0.2A cada uno
- 6 Válvulas solenoide: 0.8A cada una
- 2 Motores 24V: 2.0A cada uno

Ubicación: 150m del cuarto de distribución eléctrica

Calcule:
a) Corriente total requerida
b) Calibre de cables con caída máxima 3%
c) Especificación de fuente
d) Consideraciones de protección

**Respuesta esperada (Solución Técnica):**

a) Corriente total:
```
PLC:              3.5 A
Variadores:       2 × 0.5 = 1.0 A
Sensores:         12 × 0.2 = 2.4 A
Válvulas:         6 × 0.8 = 4.8 A
Motores:          2 × 2.0 = 4.0 A
─────────────────────────
Total:           15.7 A

Con factor de seguridad 1.25: 15.7 × 1.25 = 19.6 A → 20A
```

b) Dimensionamiento de cable:

```
Caída máxima permitida: 3% × 24V = 0.72V
Para cable de cobre a 150m con 20A:
R_máx = V_caída / (I × L/1000) = 0.72 / (20 × 0.15) = 0.24 Ω/km

Tabla de conductores: AWG 4 (21.2 mm²) con R = 0.177 Ω/km ✓
Verificación: V_caída = 20 × 0.177 × 0.15 = 0.53V ✓
```

c) Especificación de fuente:
```
• Voltaje: 24V DC
• Corriente: 20A (o próximo estándar disponible)
• Potencia: 24V × 20A = 480W
• Tipo: Fuente conmutada (SMPS) con entrada trifásica
• Protección: Fusible de 20A + disyuntor
• Respaldo: Considerar UPS si operación crítica
```

d) Consideraciones de protección:
```
• Diodos en todas las bobinas
• Supresores de transitorios en variadores
• Separación de circuitos: potencia vs control
• Tierra aislada de bobinas para reducir EMC
```

---

# 📚 REFERENCIAS Y NORMATIVAS

## Normas de instalación eléctrica

| Norma | Descripción | Aplicación |
|-------|-------------|-----------|
| **IEC 60364** | Instalaciones eléctricas de baja tensión (internacional) | Base regulatoria global |
| **IEC 60228** | Conductores de cables eléctricos (calibres, características) | Especificación de cables |
| **IEC 60269** | Fusibles de baja tensión (protección) | Protecciones |
| **IEC 60947** | Aparamenta de baja tensión (contactores, relevadores) | Componentes PLC |

## Normas de automatización y control

| Norma | Descripción | Aplicación |
|-------|-------------|-----------|
| **IEC 61131-3** | Lenguajes de programación para PLCs | Estándar de programming |
| **IEC 61000-6-2** | Compatibilidad electromagnética (EMC) en ambientes industriales | EMC industrial |
| **IEC 61508** | Seguridad funcional de sistemas de control (SIL 1-4) | Seguridad funcional |
| **IEC 62061** | Seguridad funcional de máquinas (PL a-e) | Maquinaria industrial |

## Estándares regionales

- 🇺🇸 **NEC (USA):** National Electrical Code - Artículos 300-700
- 🇬🇧 **BS 7909 (Reino Unido):** Instalaciones eléctricas temporales y móviles
- 🇧🇷 **NBR 5410 (Brasil):** Instalações elétricas de baixa tensão
- 🇦🇺 **AS/NZS 3008 (Australia/NZ):** Electrical installations
- 🇪🇺 **Regulación EU 2014/34/EU (ATEX):** Equipos para atmósferas explosivas

## Bibliografía recomendada

- **Siemens** (2020). "SIMATIC S7-1500 System Manual." [Publicación oficial](https://support.industry.siemens.com/)
- **Gill, P.** (2014). "Electrical Power Equipment Maintenance and Testing." CRC Press.
- **Neamen, D.** (2014). "Microelectronics Circuit Analysis and Design." McGraw-Hill.
- **IEEE Std 1100-2006** - Recommended Practice for Powering and Grounding Electronic Equipment

---

## ✨ CONCLUSIÓN

Este capítulo ha establecido los **fundamentos conceptuales indispensables** para cualquier ingeniero de automatización. Hemos recorrido desde la definición básica de voltaje, corriente y resistencia hasta los cálculos prácticos de dimensionamiento de cables y protecciones.

### Puntos clave a recordar

> **Los tres pilares:**  
> 1️⃣ La **Ley de Ohm** explica la relación entre V, I y R  
> 2️⃣ La **Potencia** determina el tamaño de componentes y fuentes  
> 3️⃣ La **Caída de voltaje** es crítica en distancias largas

### Próximos pasos

En los capítulos siguientes, aplicarás estos conceptos para:
- ✓ Diseñar circuitos de potencia para máquinas industriales
- ✓ Especificar protecciones (fusibles, disyuntores, diferenciales)
- ✓ Integrar PLCs en sistemas complejos con múltiples sensores y actuadores
- ✓ Resolver problemas de compatibilidad electromagnética
- ✓ Programar lógica de control segura y confiable

---

**🏁 FIN DEL CAPÍTULO 1**

**⏱️ Duración estimada:**
- Lectura teoría: 4-5 horas
- Ejercicios prácticos: 1-2 horas
- **Total recomendado: 5-7 horas**

**📊 Evaluación de comprendimiento:**
Antes de continuar al Capítulo 2, asegúrate de poder responder las **Preguntas de Entrevista (nivel básico)** sin consultar tus apuntes.

---

> **Recuerda:** *"Un ingeniero que comprende los principios eléctricos puede resolver problemas que otros creen imposibles. Un ingeniero que solo memoriza fórmulas estará perdido ante cualquier desviación de lo esperado."*

---

