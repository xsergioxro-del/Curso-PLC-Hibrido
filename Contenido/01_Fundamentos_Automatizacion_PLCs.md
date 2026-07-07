# CAPÍTULO 1: MAGNITUDES ELÉCTRICAS FUNDAMENTALES

## INTRODUCCIÓN

La comprensión profunda de los principios eléctricos es el fundamento indispensable para cualquier ingeniero de automatización. Sin importar cuán avanzados sean los sistemas de control, todos ellos operan bajo las leyes fundamentales de la electricidad descubiertas hace más de 200 años.

Un electricista que se transforma en programador PLC debe reconocer que el código que escribe en TIA Portal será interpretado, al final, como órdenes de voltaje y corriente en los componentes físicos de la máquina. No es posible diseñar un sistema de automatización robusto sin comprender cómo se comportan las magnitudes eléctricas bajo diferentes condiciones operativas.

Este capítulo no es una revisión superficial. Es una construección sólida de conceptos que serán utilizados repetidamente en los capítulos posteriores. Cada ecuación, cada diagrama, cada tabla ha sido seleccionada porque tendrá aplicación directa en el diseño de sistemas reales en el ambiente industrial.

**Objetivo pedagógico:** Transformar conocimiento teórico en herramientas mentales aplicables.

---

## OBJETIVOS DEL CAPÍTULO

Al finalizar este capítulo, el lector será capaz de:

1. **Comprender** la evolución histórica de los sistemas de control desde los relés electromecánicos hasta los PLCs modernos basados en TIA Portal.

2. **Identificar** los componentes fundamentales de un sistema de automatización industrial y explicar la función de cada uno en la arquitectura general.

3. **Diferenciar** entre el control basado en lógica cableada y el control programable, explicando las ventajas y limitaciones de ambos enfoques.

4. **Explicar** los principios de funcionamiento de un PLC, incluyendo el ciclo de exploración (scan cycle) y sus implicaciones en tiempo real.

5. **Reconocer** los diferentes tipos de PLCs disponibles en el mercado, con énfasis en la línea Siemens (S7-1200, S7-1500, etc.).

6. **Aplicar** conceptos de normalización industrial (IEC 61131-3) en el contexto de la programación de PLCs.

7. **Analizar** un caso industrial real e identificar la solución de automatización más apropiada.

---

## 1. EVOLUCIÓN HISTÓRICA DE LA AUTOMATIZACIÓN INDUSTRIAL

### 1.1 La Era de los Relés Electromecánicos (1900-1970)

La automatización industrial moderna nació con la invención del relé electromecánico en el siglo XIX. Un relé es un dispositivo electromagnético que permite controlar un circuito eléctrico de potencia utilizando una señal de control de bajo nivel. 

**Ventajas del sistema de relés:**
- Simplicidad conceptual
- Tecnología robusta y probada
- Bajo costo inicial
- Mantenimiento relativamente sencillo

**Limitaciones del sistema de relés:**

| Limitación | Impacto | Ejemplo |
|-----------|--------|---------|
| Poca flexibilidad | Modificaciones requieren recableado completo | Cambiar la lógica de un proceso toma semanas |
| Alto número de componentes | Mayor espacio físico requerido | Tablero de control de 2×2 metros para operaciones simples |
| Consumo de energía | Relés en reposo mantienen energía | 5-10% de pérdidas solo en relés |
| Mantenimiento frecuente | Contactos se oxidan, requieren limpieza | Fallas intermitentes difíciles de diagnosticar |
| Velocidad limitada | Tiempos de conmutación lentos (50-100 ms) | No apto para procesos rápidos |
| Falta de diagnostico | Sin información de estado del sistema | Ceguera operacional en procesos |

### Ejemplo de Lógica de Relés: Control de una Prensa Hidráulica

```
La prensa debe activarse cuando:
- Botón de inicio (B1) se presiona Y
- Sensor de seguridad (S1) detecta puerta cerrada Y
- Presión del sistema (P1) está dentro de rango

DIAGRAMA DE RELÉS CLÁSICO:
┌──────┬─────┬──────┬─────────┐
│  B1  │ S1  │  P1  │ Prensa  │
├──────┼─────┼──────┼─────────┤
│  •   │  •  │  •   │         │
│  |   │  |  │  |   │    ○    │
│  ◯───┴──◯──┴──◯───┴─── M1  │
└──────────────────────────────┘

Realización con relés: 3 relés + contactos auxiliares
```

### 1.2 La Revolución de los PLCs (1970-1990)

En 1968, la empresa estadounidense General Motors enfrentó un problema crítico: reprogramar sus líneas de producción mediante recableado de relés era lento y costoso. Dick Morley, ingeniero de Modicon, desarrolló el primer Controlador Lógico Programable comercial: el Modicon 084.

**Características revolucionarias del Modicon 084:**
- Memoria programable
- Interfaz simple mediante linguaje de escalera (Ladder/KOP)
- Ciclo de exploración de 100 milisegundos
- Capacidad de comunicación básica

Este invento transformó la industria. Paralelamente, en Alemania, Siemens desarrolló su propia línea de PLCs:

| Generación | Período | Modelo Siemens | Características |
|-----------|---------|----------------|-----------------|
| **Primera** | 1970-1980 | S3 | Memoria fija, sin comunicación |
| **Segunda** | 1980-1995 | S5 | Memoria expandible, PROFIBUS |
| **Tercera** | 1995-2010 | S7-300/400 | Microprocesadores, TCP/IP |
| **Cuarta** | 2010-2020 | S7-1200/1500 | Multi-core, comunicación industrial |
| **Quinta** | 2020-presente | S7-1500F/ET 200SP | Safety integrada, Edge Computing |

### 1.3 La Era de la Convergencia Digital (2010-presente)

Con la llegada de TIA Portal (Totally Integrated Automation Portal) en 2011, Siemens revolucionó el paradigma de desarrollo. Por primera vez, un ingeniero podía programar PLCs, HMIs (pantallas táctiles), sistemas SCADA y robots desde un único entorno integrado.

**Características de TIA Portal:**
- Plataforma de desarrollo única
- Acceso a librerías de funciones profesionales
- Integración con industria 4.0
- Comunicación OPC-UA nativa
- Simulación en tiempo real

---

## 2. ARQUITECTURA FUNDAMENTAL DE UN SISTEMA DE AUTOMATIZACIÓN

Un sistema de automatización industrial completo no consiste únicamente en un PLC. Es un ecosistema integrado donde cada componente juega un rol específico. Entender esta arquitectura es fundamental para diseñar soluciones robustas.

### 2.1 Diagrama de Arquitectura General

```
         ┌─────────────────────────────────────────────────┐
         │        NIVEL EMPRESARIAL (INFORMACIÓN)          │
         │  ERP, MES, SCADA, Business Intelligence        │
         └──────────────┬──────────────────────────────────┘
                        │ (OPC-UA, MQTT, REST APIs)
         ┌──────────────▼──────────────────────────────────┐
         │     NIVEL DE SUPERVISIÓN Y VISUALIZACIÓN        │
         │  HMI, Pantallas Táctiles, Sistemas de Control   │
         └──────────────┬──────────────────────────────────┘
                        │ (PROFINET, Ethernet Industrial)
         ┌──────────────▼──────────────────────────────────┐
         │    NIVEL DE AUTOMATIZACIÓN Y CONTROL            │
         │  PLC (S7-1200, S7-1500), Variadores, Drivers    │
         └──────────────┬──────────────────────────────────┘
                        │ (PROFIBUS, PROFINET, Señales 4-20mA)
         ┌──────────────▼──────────────────────────────────┐
         │     NIVEL DE CAMPO Y PROCESO                    │
         │  Sensores, Actuadores, Motores, Válvulas        │
         └─────────────────────────────────────────────────┘
```

### 2.2 Componentes Principales

#### **A. Sensores**

Los sensores son dispositivos que convierten magnitudes físicas en señales eléctricas que el PLC puede procesar.

**Clasificación de Sensores:**

| Tipo | Magnitud Medida | Señal de Salida | Ejemplo | Rango Típico |
|------|-----------------|-----------------|---------|--------------|
| **Posición Digital** | Presencia/Ausencia | On/Off | Sensor inductivo | Sí/No |
| **Presión** | Presión | 4-20 mA | Transductor de presión | 0-10 bar |
| **Temperatura** | Temperatura | 4-20 mA | RTD (Pt100) | -20 a +100°C |
| **Flujo** | Caudal | 0-10V | Medidor de turbina | 0-100 L/min |
| **Velocidad** | RPM | 0-10V | Encoder rotatorio | 0-3000 RPM |

**Ejemplo Real: Sensor Inductivo M30**

Un sensor inductivo Siemens M30 detecta la proximidad de objetos metálicos sin contacto físico.

```
PRINCIPIO DE FUNCIONAMIENTO:
┌──────────────────────────────┐
│   Coil Oscillator (Bobina)   │
│   (Oscila a ~200 kHz)        │
└────────────┬─────────────────┘
             │
             ▼
    ┌─────────────────────┐
    │  Demodulator        │
    │  (Detecta cambios)  │
    └─────────┬───────────┘
              │
              ▼
    ┌──────────────────────┐
    │ Output Stage         │
    │ (Amplifica señal)    │
    └──────┬───────────────┘
           │
           ▼
         OUTPUT (On/Off)
```

**Especificación técnica típica:**
- Rango de detección: 2-15 mm
- Tiempo de conmutación: < 1 ms
- Voltaje de suministro: 10-30 VDC
- Corriente de salida: 200 mA máximo

#### **B. PLC (Controlador Lógico Programable)**

El PLC es el "cerebro" del sistema de automatización. Su función es:

1. Leer continuamente el estado de los sensores de entrada
2. Ejecutar la lógica de control programada
3. Activar los actuadores de salida según los resultados

**Estructura Interna de un PLC:**

```
         ┌─────────────────────────────────────┐
         │  MÓDULO DE ENTRADAS (Input Module)   │
         │  • Aislamiento galvánico             │
         │  • Acondicionamiento de señal        │
         │  • Buffer de entrada                 │
         └────────────┬────────────────────────┘
                      │
                      ▼
         ┌─────────────────────────────────────┐
         │  BUS INTERNO                        │
         │  (Backplane, típicamente 32 bits)   │
         └────────────┬────────────────────────┘
                      │
           ┌──────────┼──────────┐
           │          │          │
           ▼          ▼          ▼
    ┌────────────┐ ┌──────────┐ ┌──────────────┐
    │   CPU      │ │ MEMORIA  │ │  INTERFACE   │
    │  (Micro-   │ │(RAM/ROM) │ │  (Ethernet)  │
    │  processor)│ │          │ │              │
    └────────────┘ └──────────┘ └──────────────┘
           │          │          │
           └──────────┼──────────┘
                      │
                      ▼
         ┌─────────────────────────────────────┐
         │  BUS INTERNO                        │
         └────────────┬────────────────────────┘
                      │
                      ▼
         ┌─────────────────────────────────────┐
         │  MÓDULO DE SALIDAS (Output Module)   │
         │  • Drivers de potencia               │
         │  • Aislamiento galvánico             │
         │  • Protección contra sobrecorriente  │
         └─────────────────────────────────────┘
```

#### **C. Actuadores**

Los actuadores son dispositivos que convierten las señales de control del PLC en acciones físicas.

**Tipos principales de actuadores:**

| Tipo | Función | Voltaje Típico | Corriente | Aplicación |
|------|---------|---|---|---|
| **Bobina electromagnética** | Activación on/off | 24 VDC | 0.5-2 A | Válvulas, contactores |
| **Motor AC** | Rotación trifásica | 380-400 VAC | 5-100 A | Bombas, compresores |
| **Motor DC** | Control de velocidad variable | 24-48 VDC | 1-50 A | Posicionamientos |
| **Cilindro neumático** | Movimiento lineal | Aire comprimido | 0.5-5 bar | Prensas, manipuladores |
| **Válvula solenoide** | Control de caudal/presión | 24 VDC | 0.3-1 A | Sistemas hidráulicos |

**Ejemplo: Bobina de Válvula Solenoide**

Una válvula solenoide Siemens NG6 típicamente tiene:
- Tensión nominal: 24 VDC
- Potencia: 8 W
- Tiempo de conmutación: 50-80 ms
- Presión de trabajo: 0-350 bar
- Caudal: hasta 60 L/min

---

## 3. PRINCIPIOS FUNDAMENTALES DE FUNCIONAMIENTO DE UN PLC

### 3.1 El Ciclo de Exploración (Scan Cycle)

La esencia del funcionamiento de un PLC reside en su ciclo de exploración o "scan cycle". A diferencia de un computador que ejecuta múltiples procesos simultáneamente, un PLC ejecuta un ciclo repetitivo predecible.

**Etapas del Scan Cycle:**

```
INICIO DEL CICLO
      │
      ▼
┌─────────────────────────────────────┐
│ LECTURA DE ENTRADAS (Input Scan)    │
│ • Lee todos los sensores            │
│ • Almacena valores en memoria       │
│ Tiempo típico: 1-10 ms              │
└─────────────┬───────────────────────┘
              │
              ▼
┌─────────────────────────────────────┐
│ EJECUCIÓN DE PROGRAMA (Logic Scan)  │
│ • Ejecuta el código SCL             │
│ • Procesa la lógica de control      │
│ • Genera nuevos valores de salida   │
│ Tiempo típico: 5-50 ms              │
└─────────────┬───────────────────────┘
              │
              ▼
┌─────────────────────────────────────┐
│ ESCRITURA DE SALIDAS (Output Scan)  │
│ • Escribe en todos los actuadores   │
│ • Actualiza el estado del sistema   │
│ Tiempo típico: 1-10 ms              │
└─────────────┬───────────────────────┘
              │
              ▼
┌─────────────────────────────────────┐
│ TAREAS DE MANTENIMIENTO             │
│ • Actualización de reloj             │
│ • Comunicación (Ethernet, PROFINET) │
│ • Diagnóstico interno                │
│ Tiempo típico: 2-5 ms               │
└─────────────┬───────────────────────┘
              │
              ▼
      FIN DEL CICLO
      │
      └─► Reinicia (típicamente cada 10-100 ms)
```

**Tiempo de Ciclo Total: Generalmente 10-100 ms**

### 3.2 Implicaciones del Scan Cycle

Esta estructura tiene profundas implicaciones en el diseño de sistemas de control:

#### **Implicación 1: Determinismo**

Un PLC es determinista. Dado un conjunto de entradas, siempre producirá el mismo resultado, en el mismo tiempo. Esto lo diferencia fundamentalmente de un computador personal donde la ejecución es no-determinista.

#### **Implicación 2: Retardo de Reacción**

Existe un retardo máximo (worst-case latency) entre la detección de un evento y la reacción del sistema. Este retardo es aproximadamente igual a 1 ciclo de exploración.

```
EJEMPLO CON CICLO DE 50 ms:
┌─────────────┐         ┌─────────────┐
│ Sensor se   │         │ Lectura     │
│ activa      │────────▶│ del sensor  │  Retardo máx: 50 ms
│ (evento)    │ 40 ms   │ en ciclo    │
└─────────────┘         └─────┬───────┘
                              │ 10 ms
                              ▼
                        ┌─────────────┐
                        │ Ejecución   │
                        │ de lógica   │
                        └─────┬───────┘
                              │ 40 ms
                              ▼
                        ┌─────────────┐
                        │ Actuador    │
                        │ se activa   │ Total: ~130 ms
                        └─────────────┘
```

**Implicación práctica:** Para sistemas de seguridad crítica (parada de emergencia), se requieren circuitos especiales de seguridad cableada que actúen independientemente del PLC.

#### **Implicación 3: Muestreo de Señales**

Las entradas se muestrean discretamente en puntos específicos del ciclo. Si un evento ocurre entre ciclos, podría perderse.

```
EVENTO PERDIDO:
Evento ocurre
aquí ▼
┌────────────┐         ┌────────────┐
│ CICLO 1    │         │ CICLO 2    │
│ Lectura    │────────▶│ Lectura    │
│ NO detecta │  50ms   │ Evento YA  │
│ evento     │         │ ha pasado  │
└────────────┘         └────────────┘
     ^
     evento muy corto (< 50 ms)
```

**Solución:** Filtrado de señales o tiempo de retención (latch).

### 3.3 Imagen de Entradas y Salidas (I/O Image)

Un concepto crítico en programación de PLCs es la separación entre el estado real de los sensores/actuadores y la imagen de estos en la memoria del PLC.

```
ESTADO REAL VS IMAGEN EN MEMORIA:

MUNDO FÍSICO:          MEMORIA DEL PLC:
Sensores ──┐          ┌─ Variables de entrada
Actuadores─┤ Scan────▶├─ Variables de salida
           └──Cycle───┘


DIAGRAMA TEMPORAL:
Tiempo     Sensor Real    Imagen en PLC    Actuador Real
  0 ms       OFF             OFF              OFF
 10 ms       ON              OFF              OFF
 20 ms       ON              ON               OFF
 30 ms       ON              ON               ON
 40 ms       OFF             ON               ON
 50 ms       OFF             OFF              ON
 60 ms       OFF             OFF              OFF
```

**Implicación:** El PLC siempre ve una versión "congelada" del mundo real que es válida solo al inicio de cada ciclo.

---

## 4. ARQUITECTURA INTERNA Y TIPOS DE PLCs SIEMENS

### 4.1 Línea de PLCs Siemens Actual (Generación 5)

Siemens ofrece diferentes líneas de PLCs optimizadas para distintas aplicaciones:

| Línea | Modelo | CPU | Memoria | Entrada/Salida | Aplicación | Precio |
|------|--------|-----|---------|---|---|---|
| **Compacta** | S7-1200 | Single-core 1.3 GHz | 1.5 MB | 16-128 I/O | Máquinas pequeñas | $ |
| **Estándar** | S7-1500 | Multi-core 3 GHz | 4-8 MB | 256-2048 I/O | Procesos complejos | $$ |
| **Seguridad** | S7-1500F | Multi-core 3 GHz | 4-8 MB | 256-2048 I/O | Funciones de seguridad | $$$ |
| **Edge** | ET 200SP | Modular | 2-4 MB | 128-512 I/O | Computación distribuida | $$ |

### 4.2 Comparación: S7-1200 vs S7-1500

**Caso de Uso para S7-1200:**
- Máquina de etiquetado automático
- Menos de 100 puntos de I/O
- Control relativamente simple
- Budget limitado

**Especificación:**
```
CPU 1214C:
• Entrada analógica: 2 canales (16 bits)
• Salida analógica: 2 canales (16 bits)
• Entradas digitales: 14
• Salidas digitales: 10
• Ciclo de exploración: 10 ms
• Memoria de programa: 75 KB
```

**Caso de Uso para S7-1500:**
- Línea de producción compleja
- Más de 500 puntos de I/O
- Control multitarea con sincronización crítica
- Comunicación industrial avanzada

**Especificación:**
```
CPU 1516-3 PN/DP:
• Entrada analógica: 32 canales (16 bits)
• Salida analógica: 32 canales (16 bits)
• Entradas digitales: 128
• Salidas digitales: 128
• Ciclo de exploración: 2-5 ms
• Memoria de programa: 4 MB
• Comunicación: PROFINET, PROFIBUS, Modbus TCP
```

---

## 5. NORMALIZACIÓN Y ESTÁNDARES: IEC 61131-3

### 5.1 Introducción a IEC 61131-3

La norma internacional IEC 61131-3 (International Electrotechnical Commission - Parte 3: Programming Languages) establece los estándares para la programación de controladores programables.

**Referencia Normativa:**
- Norma: **IEC 61131-3:2013 (Ed. 3.0)**
- Alcance: Lenguajes de programación para PLCs
- Ámbito: Internacional (ANSI, CSA, CEN, etc.)

### 5.2 Lenguajes Definidos por IEC 61131-3

```
IEC 61131-3 LENGUAJES ESTÁNDAR:

┌────────────────────────────────────────┐
│   LENGUAJES DE PROGRAMACIÓN PLC        │
├────────────────────────────────────────┤
│                                        │
│  1. LD (Ladder Diagram / KOP)         │
│     └─ Lenguaje gráfico                │
│     └─ Símbolos de relés y contactos  │
│                                        │
│  2. FBD (Function Block Diagram)       │
│     └─ Lenguaje gráfico                │
│     └─ Representación de bloques       │
│                                        │
│  3. ST (Structured Text / SCL)         │
│     └─ Lenguaje textual                │
│     └─ Similar a Pascal/C              │
│                                        │
│  4. IL (Instruction List)              │
│     └─ Lenguaje bajo nivel             │
│     └─ Similar a ensamblador           │
│                                        │
│  5. SFC (Sequential Function Chart)    │
│     └─ Lenguaje gráfico secuencial     │
│     └─ Máquinas de estados             │
│                                        │
└────────────────────────────────────────┘
```

**Terminología Oficial Siemens:**
- KOP = "Kontakt Plan" (Plan de Contactos) = LD (Ladder)
- SCL = "Structured Control Language" = ST (Structured Text)
- Awl = "Anweisungsliste" = IL (Instruction List)

### 5.3 Conformidad de Siemens TIA Portal con IEC 61131-3

Siemens TIA Portal implementa completamente los estándares IEC 61131-3, aunque utiliza nomenclatura propia:

| IEC 61131-3 | Siemens TIA Portal |
|---|---|
| Ladder Diagram (LD) | KOP |
| Function Block Diagram (FBD) | FUP |
| Structured Text (ST) | SCL |
| Instruction List (IL) | AWL |
| Sequential Function Chart (SFC) | GRAPH |

---

## 6. CASOS INDUSTRIALES REALES

### Caso 1: Línea de Envasado de Bebidas

**Descripción del Proceso:**
Una fábrica de refrescos necesita automatizar su línea de envasado. El proceso incluye:

1. Llenado de botellas (controlado por válvula solenoide)
2. Corroseal (tapa automática)
3. Etiquetado
4. Recuento y empaque

**Requisitos:**
- Velocidad: 120 botellas/minuto
- Ciclo: 500 ms por botella
- Precisión: ±2%
- Seguridad: parada de emergencia en < 100 ms

**Solución:**
```
ARQUITECTURA DEL SISTEMA:
┌─────────────────────────────────────┐
│          S7-1500 PLC                │
│  • Control de válvulas solenoide    │
│  • Monitoreo de sensores            │
│  • Comunicación HMI                 │
└──────────┬──────────────────────────┘
           │
    ┌──────┼──────┐
    │      │      │
    ▼      ▼      ▼
  Válv.  Conta.  HMI Pantalla
  Sole.  dores   Táctil
```

**Especificación del PLC:**
- CPU: S7-1500 1514C
- Entradas digitales: 32
- Salidas digitales: 32
- Entradas analógicas: 8 (para sensores de presión/caudal)
- Salidas analógicas: 4 (control de variadores de velocidad)

**Tiempo de Ciclo Requerido:**
```
Ciclo de 50 ms permite:
• Lectura de 16 sensores: 5 ms
• Lógica de control: 30 ms
• Escritura de 8 salidas: 5 ms
• Comunicación Ethernet: 10 ms
Total: 50 ms < 500 ms de ciclo de producción
```

### Caso 2: Sistema de Control de Temperatura en Reactor Químico

**Descripción:**
Un reactor químico debe mantener una temperatura entre 95°C y 105°C con tolerancia de ±1°C durante 8 horas de procesamiento.

**Sensores:**
- PT100 (RTD) que proporciona 4-20 mA proporcional a la temperatura
- Presión (0-350 bar)
- Nivel de líquido

**Actuadores:**
- Resistencia calefactora (On/Off)
- Válvula de circulación de agua de enfriamiento (Modulable 0-100%)

**Desafíos:**
- Inercia térmica alta (tardío cambios de temperatura)
- Necesidad de control proporcional/integral/derivado (PID)
- Seguridad: si T > 120°C, apertura de válvula de seguridad

**Solución SCL:**
El control PID se implementa mediante algoritmo en SCL que actualiza la posición de la válvula cada ciclo basándose en el error de temperatura.

---

## 7. DIFERENCIAS CLAVE: LÓGICA CABLEADA vs LÓGICA PROGRAMABLE

### 7.1 Comparativa Detallada

```
CARACTERÍSTICA         LÓGICA CABLEADA    LÓGICA PROGRAMABLE (PLC)
─────────────────────  ─────────────────  ────────────────────────
Flexibilidad           Baja               Alta
Modificaciones         Requiere recableado Cambio de programa
Costo inicial          Bajo               Medio-Alto
Tiempo de desarrollo   Semanas            Días
Diagnóstico            Difícil            Integrado
Complejidad máx.       Limitada           Muy Alta
Mantenimiento          Frecuente          Reducido
Redundancia            Difícil            Sencilla
Documentación          Por diagramas       Automática
Velocidad              Lenta (50-100ms)   Rápida (1-50ms)
```

### 7.2 Ejemplo Práctico: Control de Puerta Garage

**Requisitos:**
- Botón sube (BS)
- Botón baja (BB)
- Sensor fin de carrera arriba (FSA)
- Sensor fin de carrera abajo (FSB)
- Motor bidireccional (MOTOR_UP, MOTOR_DOWN)
- LED de indicación (LED)

**Lógica Cableada (tradicional):**

```
ESQUEMA EN LÓGICA CABLEADA:
┌───────────────────────────────────────────┐
│                                           │
│  BS ───┬─── FSA ────────► MOTOR_UP        │
│        │                                  │
│        │                                  │
│  BB ───┴─── FSB ────────► MOTOR_DOWN      │
│                                           │
│  MOTOR_UP ──────────────► LED_VERDE       │
│  MOTOR_DOWN ─────────────► LED_ROJO       │
│                                           │
└───────────────────────────────────────────┘

PROBLEMA: Sin protección contra simultáneo
Si BS y BB se presionan al mismo tiempo:
→ Cortocircuito de la alimentación
→ Daño del motor
```

**Lógica Programable (PLC):**

```
CÓDIGO SCL:
─────────────────────────────────────
IF (BS AND NOT FSA) THEN
    MOTOR_UP := 1;
    MOTOR_DOWN := 0;
    LED := 1;
ELSIF (BB AND NOT FSB) THEN
    MOTOR_UP := 0;
    MOTOR_DOWN := 1;
    LED := 0;
ELSE
    MOTOR_UP := 0;
    MOTOR_DOWN := 0;
END_IF;
─────────────────────────────────────

VENTAJAS:
✓ Protección lógica contra cortocircuito
✓ Condiciones complejas fácilmente
✓ Historial de operaciones
✓ Diagnóstico de fallos
```

---

## 8. EJERCICIOS PRÁCTICOS

### Ejercicio 1: Identificación de Componentes

**Enunciado:**
En una línea de producción de tuercas metálicas, se requiere:
- Transportador principal controlado por motor trifásico
- 5 estaciones de inspección con sensores inductivos
- Rechazo de piezas defectuosas mediante cilindro neumático
- Contador de piezas

**Preguntas:**
a) Identifique cada sensor y actuador del sistema
b) ¿Cuál sería el tipo de PLC mínimo recomendado?
c) ¿Cuáles serían los tiempos críticos del sistema?
d) ¿Qué información debería mostrar una pantalla HMI?

### Ejercicio 2: Análisis de Ciclo de Exploración

**Enunciado:**
Un PLC S7-1200 tiene un ciclo de exploración de 20 ms. En una aplicación de prensado se requiere detectar un evento de duración máxima de 5 ms.

**Preguntas:**
a) ¿Existe riesgo de pérdida de eventos?
b) ¿Qué soluciones propone?
c) Dibuje un diagrama temporal mostrando el peor caso
d) ¿Cuál sería el ciclo máximo aceptable para esta aplicación?

### Ejercicio 3: Conversión de Lógica Cableada a PLC

**Enunciado:**
El siguiente circuito de relés controla un motor:

```
Circuito original:
BS (pulsador) ──┬─── M (Motor)
                │
BR (pulsador) ──┤
                │
FSA (final carrera) ─┴── M (Motor)

Explicación: El motor arranca si:
- Se presiona BS O BR
- Y NO se presiona FSA
```

**Preguntas:**
a) Escriba la ecuación lógica correspondiente
b) Implemente la lógica en KOP (Ladder)
c) Implemente la lógica en SCL
d) ¿Qué mejoras de seguridad añadiría?

---

## 9. SOLUCIONES A LOS EJERCICIOS

### Solución Ejercicio 1

**a) Identificación de componentes:**

| Dispositivo | Tipo | Señal | Función |
|-----------|------|-------|---------|
| Motor trifásico | Actuador | 380 VAC | Movimiento del transportador |
| Sensores inductivos | Sensor Digital | 24 VDC | Detección de piezas |
| Cilindro neumático | Actuador | 6 bar | Eyección de piezas defectuosas |
| Contador | Entrada digital | 24 VDC | Contabilización de piezas |
| Variador de velocidad | Controlador | 0-10V | Control de RPM del motor |

**b) Tipo de PLC recomendado:**
```
Análisis de requisitos:
• Entradas: 5 sensores + contador = 6 entradas digital
• Salidas: Motor (ON/OFF) + cilindro = 2 salidas digital
• Comunicación: Posible HMI, PROFINET recomendado
• Complejidad: Media

Recomendación: S7-1200 CPU 1214C
Justificación:
- 14 entradas/10 salidas suficientes
- PROFINET integrado
- Buena relación costo/rendimiento
- Expansión posible
```

**c) Tiempos críticos:**

```
Ciclo de producción: 2 segundos por pieza
Distribución temporal:
├─ Transporte pieza: 1500 ms
├─ Detección: 100 ms
├─ Decisión (inspección): 200 ms
├─ Eyección (si defectuosa): 200 ms
└─ Total: 2000 ms

PLC ciclo de exploración: máx 20 ms
Seguridad: Ciclo << Tiempo de proceso ✓
```

**d) Información HMI:**

```
PANTALLA DE MONITOREO:
┌─────────────────────────────────────┐
│  LÍNEA DE TUERCAS - MONITOREO       │
├─────────────────────────────────────┤
│                                     │
│  Estado: EN FUNCIONAMIENTO          │
│  Velocidad: 30 piezas/min          │
│                                     │
│  Piezas totales:    5,342          │
│  Piezas aceptadas:  5,127 (95.9%)  │
│  Piezas rechazadas:   215 (4.1%)   │
│                                     │
│  ┌─ Sensores ─────────────────┐    │
│  │ S1: [●] OK                  │    │
│  │ S2: [○] No presencia       │    │
│  │ S3: [●] OK                  │    │
│  │ S4: [●] OK                  │    │
│  │ S5: [○] No presencia       │    │
│  └─────────────────────────────┘    │
│                                     │
│  [INICIO]  [PARADA]  [RESET]       │
│                                     │
└─────────────────────────────────────┘
```

### Solución Ejercicio 2

**a) ¿Existe riesgo de pérdida de eventos?**

Sí. Análisis:
```
Evento de 5 ms
Ciclo de exploración: 20 ms

Escenario más desfavorable:
Evento ocurre 1 ms después de lectura de entrada
→ Duración real: 5 ms
→ Próxima lectura: 19 ms después del inicio del evento
→ Evento no detectado ✗
```

**b) Soluciones propuestas:**

1. **Reducir ciclo de exploración:** No siempre posible (limitaciones de CPU)
2. **Usar interrupción externa:** 
   ```
   El PLC puede configurarse para interrumpirse
   ante eventos de corta duración
   ```
3. **Hardware de captura rápida:**
   ```
   Módulo de entrada rápida (Fast Input)
   Captura eventos con resolución < 1 ms
   ```
4. **Filtrado hardware:**
   ```
   Circuito RC o filtro digital en entrada
   Alarga la duración del evento
   Riesgo: Puede causar falsa detección
   ```

**Recomendación:** Usar módulo de entrada rápida integrado en S7-1200

**c) Diagrama temporal - Peor caso:**

```
ESCENARIO DESFAVORABLE:
Tiempo (ms)    Evento    Lectura Entrada  Acción
0              |         
5              |         
10             |         Lectura (NO ve evento)
15             |         
20                       
25             |         Lectura (Evento YA pasó)
30             |

DIAGRAMA VISUAL:
│ EVENTO
├─────┐
│     │ (duración 5 ms)
│     │ Lectura aquí NO lo capta
│     ▼
──────┼──────────────────────────── Lectura inicial
      └─────────────┐
                    │ Próxima lectura
                    │ Evento YA desapareció
                    ▼
──────────────────────────────────── Lectura 20 ms después
```

**d) Ciclo máximo aceptable:**

Para capturar eventos de 5 ms con certeza:
```
Ciclo máximo ≤ duración del evento / 2
Ciclo máximo ≤ 5 ms / 2 = 2.5 ms

Recomendación práctica: ciclo ≤ 1 ms
O usar entrada rápida con captura < 1 ms
```

### Solución Ejercicio 3

**a) Ecuación lógica:**

```
M = (BS OR BR) AND NOT FSA

Notación:
M    = Salida motor
BS   = Entrada pulsador sube
BR   = Entrada pulsador baja
FSA  = Entrada fin de carrera arriba
```

**b) Implementación en KOP (Ladder):**

```
Red 1:
┌─────┐     ┌─────┐     ┌──────────┐
│ BS  ├─┬─┬─┤ NOT ├─────┤ MOTOR    │
│     │ │ │ │ FSA │     │          │
└─────┘ │ │ └──────┘     └──────────┘
        │ │
┌─────┐ │ │
│ BR  ├─┘ │
│     │   │
└─────┘   │
          │
         [R] (conexión lógica OR)
```

**c) Implementación en SCL:**

```scl
PROGRAM MotorControl
VAR
    BS : BOOL;      // Pulsador sube (entrada)
    BR : BOOL;      // Pulsador baja (entrada)
    FSA : BOOL;     // Fin de carrera arriba (entrada)
    MOTOR : BOOL;   // Motor (salida)
END_VAR

BEGIN
    IF (BS OR BR) AND (NOT FSA) THEN
        MOTOR := 1;
    ELSE
        MOTOR := 0;
    END_IF;
END_PROGRAM
```

**d) Mejoras de seguridad:**

```scl
PROGRAM MotorControl_Mejorado
VAR
    BS : BOOL;      // Pulsador sube
    BR : BOOL;      // Pulsador baja
    FSA : BOOL;     // Fin de carrera arriba
    FSB : BOOL;     // Fin de carrera abajo
    MOTOR : BOOL;   // Salida motor
    contador_ciclos_botton : INT; // Anti-rebote
END_VAR

BEGIN
    // Anti-rebote: requiere 5 ciclos de presión
    IF BS THEN
        contador_ciclos_botton := contador_ciclos_botton + 1;
    ELSE
        contador_ciclos_botton := 0;
    END_IF;
    
    IF (contador_ciclos_botton >= 5 OR BR) AND NOT FSA AND NOT FSB THEN
        MOTOR := 1;
    ELSE
        MOTOR := 0;
    END_IF;
    
    // Parada de emergencia adicional
    IF FSA OR FSB THEN
        MOTOR := 0;
    END_IF;

END_PROGRAM
```

---

## 10. ERRORES HABITUALES Y CÓMO EVITARLOS

### Error 1: Ignorar el Ciclo de Exploración

**Descripción del error:**
Un programador novato asume que todas las entradas se leen continuamente, como en un programa de computador tradicional.

**Consecuencia:**
```
Implementación incorrecta:
WHILE TRUE DO
    IF sensor = 1 THEN
        // Espera a que sensor sea 0
        WHILE sensor = 1 DO
            WAIT 100 ms;
        END_WHILE;
        //Acciones...
    END_IF;
END_WHILE;

Problema: El PLC se bloquea en este bucle
No ejecuta el resto del programa
No actualiza el resto de salidas
El ciclo de exploración se rompe ✗
```

**Solución correcta:**
```scl
// Utilizar variables de estado (state machine)
VAR
    estado : INT := 0;
    sensor_anterior : BOOL := FALSE;
END_VAR

CASE estado OF
    0: // Esperar flanco ascendente
        IF sensor AND NOT sensor_anterior THEN
            // Acciones
            estado := 1;
        END_IF;
        
    1: // Esperar a que se suelte
        IF NOT sensor THEN
            sensor_anterior := FALSE;
            estado := 0;
        END_IF;
END_CASE;

sensor_anterior := sensor;
```

### Error 2: No Inicializar Variables

**Descripción del error:**
Al iniciar el PLC, las variables no inicializadas contienen valores aleatorios.

**Consecuencia:**
```
VAR
    contador : INT;  // ¿Qué valor tiene?
    bandera : BOOL;  // ¿TRUE o FALSE?
END_VAR

Primera ejecución:
contador podría ser 32,567 (¡valor aleatorio!)
bandera podría ser TRUE cuando debería ser FALSE
→ Comportamiento impredecible
```

**Solución correcta:**
```scl
VAR
    contador : INT := 0;      // Inicializar a 0
    bandera : BOOL := FALSE;  // Inicializar explícitamente
    temperatura : REAL := 20.0;
END_VAR
```

### Error 3: Olvidar Conversión de Tipos

**Descripción del error:**
Intentar mezclar tipos de datos sin conversión explícita.

**Consecuencia:**
```scl
VAR
    entrada_analogica : INT;   // 0-32767 (16 bits)
    salida_analogica : REAL;   // Rango real
END_VAR

// INCORRECTO:
salida_analogica := entrada_analogica;  
// El compilador da error

// CORRECTO:
salida_analogica := INT_TO_REAL(entrada_analogica);
salida_analogica := salida_analogica / 1024.0;  // Escalar 0-32767 → 0-32
```

### Error 4: Tiempos Críticos Ignorados

**Descripción del error:**
No considerar el tiempo de reacción requerido vs. el tiempo de ciclo del PLC.

**Consecuencia:**
```
Aplicación: Prensa de 100 ciclos/minuto = 600 ms por ciclo
PLC ciclo: 50 ms
Evento a detectar: 10 ms (apertura de puerta de seguridad)

Análisis:
Retardo máximo PLC: 50 ms
Evento: 10 ms < 50 ms
RIESGO: El evento podría no detectarse ✗

Solución: Usar entrada rápida (Fast Input)
Captura < 1 ms
Independiente del ciclo de exploración
```

### Error 5: Protección Contra Rebotes Inadecuada

**Descripción del error:**
Un sensor produce múltiples transiciones rápidas (rebote) que se interpretan como múltiples eventos.

**Consecuencia:**
```
Evento real: 1 presión de botón
Rebotes detectados: 5-10 transiciones
Resultado: Se cuenta como 5-10 presiones
Contador incrementa erróneamente
```

**Solución con filtrado de software:**
```scl
VAR
    boton_raw : BOOL;        // Entrada sin filtrar
    boton_filtrado : BOOL;   // Salida filtrada
    contador_filtro : INT := 0;
    UMBRAL_FILTRO : INT := 3; // Requiere 3 ciclos de estabilidad
END_VAR

// Detección de flanco con filtro
IF boton_raw THEN
    contador_filtro := contador_filtro + 1;
    IF contador_filtro > UMBRAL_FILTRO THEN
        boton_filtrado := TRUE;
    END_IF;
ELSE
    contador_filtro := 0;
    boton_filtrado := FALSE;
END_IF;
```

---

## 11. BUENAS PRÁCTICAS EN PROGRAMACIÓN DE PLCs

### Práctica 1: Documentación Inline

```scl
// BUENA DOCUMENTACIÓN:
// Función: Calcula la temperatura equivalente en Fahrenheit
// Entrada: temperatura_celsius (REAL) - Rango: -40 a +100 °C
// Salida: temperatura_fahrenheit (REAL)
// Referencia: Conversión según NIST (National Institute of Standards)
FUNCTION Celsius_To_Fahrenheit : REAL
VAR_INPUT
    temperatura_celsius : REAL;
END_VAR

BEGIN
    // Fórmula: °F = (°C × 9/5) + 32
    Celsius_To_Fahrenheit := (temperatura_celsius * 9.0 / 5.0) + 32.0;
END_FUNCTION
```

### Práctica 2: Nombrado Consistente de Variables

```scl
// MALO:
VAR
    t : REAL;       // ¿Qué es t?
    x : INT;        // ¿Qué es x?
    f1 : BOOL;      // ¿Qué significa f1?
END_VAR

// BUENO:
VAR
    temperatura_reactor : REAL;      // En °C
    nivel_tanque : INT;              // En cm
    bomba_principal_activa : BOOL;   // Estado
    contador_ciclos : INT;           // Unidad: ciclos
    tiempo_ultimo_evento_ms : INT;   // Unidad: milisegundos
END_VAR

// CONVENCIÓN SIEMENS (recomendado):
VAR
    gTemperatura : REAL;   // g = global
    lnivel : INT;          // l = local
    bEstado : BOOL;        // b = boolean (tipo)
    rTemperatura_SP : REAL; // SP = Setpoint
END_VAR
```

### Práctica 3: Manejo de Estados Discretos

```scl
// Máquina de estados para proceso de 3 fases
PROGRAM ProcesoContinuo
VAR
    estado_actual : INT := 0;
    entrada_sensor_inicio : BOOL;
    entrada_sensor_medio : BOOL;
    entrada_sensor_fin : BOOL;
    salida_actuador : BOOL;
    tiempo_fase_ms : INT;
    reloj_ms : INT := 0;
END_VAR

CONST
    ESTADO_REPOSO := 0;
    ESTADO_FASE_1 := 1;
    ESTADO_FASE_2 := 2;
    ESTADO_FASE_3 := 3;
    TIEMPO_FASE_1_MS := 2000;
    TIEMPO_FASE_2_MS := 3000;
    TIEMPO_FASE_3_MS := 1500;
END_CONST

BEGIN
    // Lógica de transición entre estados
    CASE estado_actual OF
        ESTADO_REPOSO:
            salida_actuador := 0;
            IF entrada_sensor_inicio THEN
                estado_actual := ESTADO_FASE_1;
                reloj_ms := 0;
            END_IF;
        
        ESTADO_FASE_1:
            salida_actuador := 1;
            reloj_ms := reloj_ms + 1; // Incrementa cada ms
            IF reloj_ms >= TIEMPO_FASE_1_MS THEN
                estado_actual := ESTADO_FASE_2;
                reloj_ms := 0;
            END_IF;
        
        ESTADO_FASE_2:
            salida_actuador := 0;
            reloj_ms := reloj_ms + 1;
            IF reloj_ms >= TIEMPO_FASE_2_MS THEN
                estado_actual := ESTADO_FASE_3;
                reloj_ms := 0;
            END_IF;
        
        ESTADO_FASE_3:
            salida_actuador := 1;
            reloj_ms := reloj_ms + 1;
            IF reloj_ms >= TIEMPO_FASE_3_MS THEN
                estado_actual := ESTADO_REPOSO;
                reloj_ms := 0;
            END_IF;
    END_CASE;

END_PROGRAM
```

### Práctica 4: Manejo de Errores

```scl
// Función con manejo de errores
FUNCTION Leer_Sensor_Seguro : REAL
VAR_INPUT
    id_sensor : INT;
    valor_minimo_valido : REAL;
    valor_maximo_valido : REAL;
END_VAR
VAR
    valor_leido : REAL;
    es_valido : BOOL;
    contador_errores : INT;
END_VAR

BEGIN
    // Intento de lectura
    TRY
        valor_leido := Leer_Sensor(id_sensor);
    CATCH
        contador_errores := contador_errores + 1;
        // Retornar último valor válido conocido
        RETURN gUltimo_Valor_Sensor_Valido;
    END_TRY;
    
    // Validación de rango
    IF (valor_leido < valor_minimo_valido) OR 
       (valor_leido > valor_maximo_valido) THEN
        // Valor fuera de rango
        contador_errores := contador_errores + 1;
        RETURN gUltimo_Valor_Sensor_Valido;
    ELSE
        gUltimo_Valor_Sensor_Valido := valor_leido;
        Leer_Sensor_Seguro := valor_leido;
    END_IF;

END_FUNCTION
```

---

## 12. RESUMEN DEL CAPÍTULO

### Puntos Clave

1. **Evolución:** De relés (1900) → PLCs (1970) → TIA Portal (2011) → Edge Computing (2020)

2. **Arquitectura:** Sensores → PLC → Actuadores, en ciclo determinista de exploración

3. **Ciclo de Exploración:** Estructura de 3 fases (lectura, procesamiento, escritura) que garantiza determinismo pero introduce latencia

4. **Normalización:** IEC 61131-3 define 5 lenguajes estándar; Siemens TIA Portal implementa todos ellos

5. **Líneas Siemens:**
   - **S7-1200:** Máquinas pequeñas, < 100 I/O
   - **S7-1500:** Procesos complejos, > 500 I/O
   - **S7-1500F:** Funciones de seguridad certificadas

6. **Ventajas del PLC sobre lógica cableada:**
   - Flexibilidad
   - Diagnóstico integrado
   - Comunicación industrial
   - Redundancia fácil
   - Documentación automática

7. **Conceptos críticos:**
   - Imagen de I/O (snapshot del estado)
   - Retardo de reacción máximo (1 ciclo)
   - Necesidad de inicialización
   - Manejo de rebotes

8. **Errores a evitar:**
   - Bloqueos en bucles infinitos
   - Variables no inicializadas
   - Ignorar conversiones de tipos
   - No considerar tiempos críticos

---

## 13. PREGUNTAS TIPO ENTREVISTA TÉCNICA

### Nivel Básico

**P1: ¿Cuál es la diferencia fundamental entre un PLC y un computador personal?**

Respuesta esperada:
```
Un PLC es determinista y ejecuta un ciclo predecible y repetitivo
(lectura → procesamiento → escritura), mientras que un computador
es no-determinista y puede ejecutar múltiples procesos concurrentemente.

Implicación: El PLC es predecible para sistemas de tiempo real,
pero el computador es más flexible.
```

**P2: ¿Qué es el ciclo de exploración y por qué es importante?**

Respuesta esperada:
```
El scan cycle es la secuencia repetitiva: lectura de entradas →
ejecución de programa → escritura de salidas. Es importante porque:

• Garantiza determinismo
• Permite cálculo de tiempos de reacción máximos
• Implica que hay un retardo de aproximadamente 1 ciclo
  entre evento y reacción
```

**P3: ¿Qué son sensores digitales y analógicos? Dé ejemplos de cada uno.**

Respuesta esperada:
```
Digitales (On/Off, 24 VDC):
• Sensor inductivo (proximidad)
• Pulsador
• Fin de carrera

Analógicos (Rango, 4-20 mA o 0-10V):
• Transductor de presión
• Termómetro (RTD)
• Medidor de caudal
```

### Nivel Intermedio

**P4: ¿Cómo seleccionaría entre S7-1200 y S7-1500 para una aplicación?**

Respuesta esperada:
```
Criterios de decisión:
1. Número de puntos de I/O
   - < 100 I/O → S7-1200
   - > 500 I/O → S7-1500

2. Complejidad del programa
   - Lógica simple → S7-1200
   - Múltiples variables de control → S7-1500

3. Velocidad requerida
   - Ciclo > 10 ms → S7-1200 suficiente
   - Ciclo < 5 ms → Necesita S7-1500

4. Comunicación industrial
   - PROFINET simple → S7-1200
   - PROFINET/PROFIBUS redundante → S7-1500

5. Budget disponible
```

**P5: ¿Cuál sería el retardo máximo de reacción ante un evento en un PLC con ciclo de 50 ms?**

Respuesta esperada:
```
El retardo máximo es aproximadamente 2 ciclos:

1. Ciclo 1: Evento ocurre después de lectura
   → No se ve en este ciclo (hasta 50 ms)

2. Ciclo 2: Lectura detecta evento
   → Procesamiento genera salida

3. Ciclo 3: Salida se actualiza
   → Actuador reacciona

Tiempo total máximo: 3 × 50 ms = 150 ms
(En la práctica, aproximadamente 2 ciclos = 100 ms)

Para eventos más rápidos: Usar entrada rápida con captura < 1 ms
```

### Nivel Avanzado

**P6: Explique cómo implementaría un sistema de seguridad para parada de emergencia en un PLC. ¿Cuáles son las limitaciones?**

Respuesta esperada:
```
Sistema seguro de parada de emergencia:

1. Botón de seguridad (NC - Normally Closed)
   Conectado directamente a relé de seguridad cableado
   (independiente del PLC)

2. Relé de seguridad:
   Corta la alimentación de emergencia (24 VDC)
   Tiempo de respuesta: < 100 ms

3. PLC monitorea estado de seguridad:
   IF NOT boton_emergencia THEN
       motor := 0;
       valvulas_control := 0;
   END_IF;

Limitaciones del PLC:
• No puede ser el elemento de seguridad primario
• Ciclo de exploración introduce retardo
• Requiere certificación de seguridad (IEC 61508/62061)
• Para sistemas Safety se usa S7-1500F certificado
```

**P7: Describa una arquitectura de sistema de automatización industrial completo para una fábrica de producción de textiles.**

Respuesta esperada: (respuesta larga, estructura en capas)
```
NIVEL 5: ERP (Enterprise Resource Planning)
├─ Gestión de producción
├─ Inventario
└─ Planificación

       ↕ (OPC-UA, MQTT, REST APIs)

NIVEL 4: SCADA/MES (Manufacturing Execution System)
├─ Supervisión de líneas
├─ Trazabilidad
├─ Alertas
└─ Reportes

       ↕ (PROFINET Industrial)

NIVEL 3: Control y Automatización (PLC)
├─ S7-1500 CPU (maestro)
├─ 3 × S7-1200 (esclavos para cada línea)
└─ Variadores de velocidad

       ↕ (PROFIBUS, 4-20 mA)

NIVEL 2: Visualización Local
├─ HMI Pantalla táctil
├─ Indicadores LED
└─ Pulsadores de operador

       ↕ (Señales digitales 24 VDC)

NIVEL 1: Campo y Proceso
├─ Motores AC (transportadores)
├─ Sensores inductivos
├─ Transductores de presión
├─ Cilindros neumáticos
└─ Bobinas solenoides
```

---

## 14. FUENTES Y REFERENCIAS

**Normas Citadas:**

1. **IEC 61131-3:2013** - Programmable controllers - Part 3: Programming languages
   - Especificación: Estándar internacional para lenguajes PLC
   - Emisor: International Electrotechnical Commission (IEC)

2. **IEC 60947:2009** - Low-voltage switchgear and control gear
   - Especificación: Componentes de baja tensión
   - Emisor: International Electrotechnical Commission (IEC)

3. **IEC 61508:2010** - Functional safety of electrical/electronic/programmable electronic safety-related systems
   - Especificación: Seguridad funcional de sistemas
   - Emisor: International Electrotechnical Commission (IEC)

**Documentación Siemens:**

- SIEMENS AUTOMATION COMMISSIONING SUPPORT (ACS)
- TIA Portal V16 User Guide
- S7-1200 System Manual
- S7-1500 System Manual

**Bibliografía Complementaria:**

- Morley, D. (1996). "The Design and Development of the Modicon 084 Programmable Controller"
- Bolton, W. (2015). "Programmable Logic Controllers" (6ª ed.)
- John, K. & Tiegelkamp, M. (2014). "IEC 61131-3: Programming Industrial Automation Systems" (4ª ed.)

---

## FIN DEL CAPÍTULO 1

**Páginas estimadas:** 18 páginas (A4, 1.5 espaciado, fuente Times New Roman 11)

**Tiempo de lectura estimado:** 120-150 minutos

**Próximo Capítulo:** Capítulo 2 - "Conceptos Eléctricos Fundamentales para Automatización"

---

*Este material es propiedad intelectual del autor. Se permite su uso educativo y no comercial. Se prohíbe su reproducción total o parcial sin autorización explícita del autor.*

**Versión del documento:** 1.0  
**Fecha de revisión:** 07 de Julio de 2026  
**Verificado por:** Formador Oficial Siemens

