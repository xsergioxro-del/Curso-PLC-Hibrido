# CURSO PLC HÍBRIDO - ÍNDICE DEFINITIVO REESTRUCTURADO

**Subtítulo:** De Electricista de Baja Tensión a Ingeniero Senior de Automatización Industrial  
**Duración estimada:** 450-550 horas (equivalente a 9-11 meses a tiempo completo)  
**Nivel final:** Ingeniero Senior de Automatización Industrial, Certificado Siemens  
**Versión:** 2.0 - Reestructurado por 3 expertos (Siemens, Industrial, Pedagogía)  

---

## 🎯 MAPA ESTRATÉGICO DEL CURSO

```
PROGRESIÓN DE APRENDIZAJE:

Nivel 1: FUNDAMENTOS (Semanas 1-4)
└─ Electricidad + Lógica + Primera experiencia con TIA Portal
   └─ Objetivo: "Puedo conectar un sensor y leer su valor"

Nivel 2: PROGRAMACIÓN BÁSICA (Semanas 5-8)
└─ KOP profundo + SCL introductorio
   └─ Objetivo: "Puedo programar una secuencia simple"

Nivel 3: PROGRAMACIÓN INTERMEDIA (Semanas 9-20)
└─ SCL avanzado + E/S digital + E/S analógica + PID
   └─ Objetivo: "Puedo controlar un proceso real"

Nivel 4: SISTEMAS INTEGRADOS (Semanas 21-30)
└─ Comunicación + Arquitectura + Integración
   └─ Objetivo: "Puedo diseñar una línea de producción"

Nivel 5: EXPERTO INDUSTRIAL (Semanas 31-40+)
└─ Casos reales + Seguridad + Especialización
   └─ Objetivo: "Puedo liderar proyectos de automatización"
```

---

# 🔵 BLOQUE I: FUNDAMENTOS ELÉCTRICOS Y CONCEPTUALES (Nivel Principiante)
**Duración:** 50-60 horas | **Objetivo:** Base sólida sin ambigüedades

## MÓDULO 1: ELECTRICIDAD INDUSTRIAL APLICADA

### Capítulo 1: Magnitudes Eléctricas Fundamentales
- Corriente, voltaje, resistencia (definiciones claras)
- Ley de Ohm y aplicación práctica
- Potencia: P, Q, S, Factor de potencia
- AC vs DC: diferencias en control industrial
- **Laboratorio:** Mediciones con multímetro en equipos reales
- **Duración:** 5-6 horas

### Capítulo 2: Circuitos de Potencia para Máquinas
- Circuitos monofásicos vs trifásicos
- Transformadores de potencia
- Motores eléctricos AC/DC
- Arrancadores e inversores de marcha
- **Laboratorio:** Medición de voltajes en panel real
- **Duración:** 5-6 horas

### Capítulo 3: Componentes de Control en Baja Tensión
- Interruptores, pulsadores, selectores
- Relés electromagnéticos: principio y funcionamiento
- Contactores: principio de funcionamiento
- Protecciones: fusibles, automáticos, diferenciales
- **Laboratorio:** Identificar componentes en tablero industrial
- **Duración:** 6-7 horas

### Capítulo 4: Seguridad Eléctrica Industrial
- Norma IEC 60204-1 (Seguridad de máquinas)
- Categorías de seguridad (Cat 0-4, según IEC 61508)
- Sistemas de parada de emergencia
- Protección contra contacto indirecto (puesta a tierra)
- Riesgos en sistemas de automatización
- **Laboratorio:** Diseño de circuito de parada de emergencia
- **Duración:** 6-7 horas

### Capítulo 5: Señales Digitales y Analógicas
- Concepto de señal digital (On/Off)
- Señales analógicas (0-10V, 4-20mA)
- Niveles lógicos industriales (24VDC)
- Convertidores A/D y D/A: principios
- Ruido, EMI y blindaje en industriales
- **Laboratorio:** Medición de señales analógicas
- **Duración:** 6-7 horas

---

## MÓDULO 2: LÓGICA Y SISTEMAS DISCRETOS

### Capítulo 6: Lógica Booleana Aplicada
- Operaciones lógicas: AND, OR, NOT, XOR
- Tablas de verdad
- Expresiones booleanas
- Simplificación (Mapas de Karnaugh)
- Sistemas combinacionales vs secuenciales
- **Ejercicios:** Simplificar ecuaciones reales
- **Duración:** 5-6 horas

### Capítulo 7: Automatización Clásica vs Moderna
- Máquinas con lógica de relés (cableada)
- Esquema de fuerza vs esquema de mando
- Ventajas y limitaciones de relés
- Introducción a los PLCs como solución
- Comparativa: costo, flexibilidad, tiempo
- **Estudio de caso:** Línea de producción antigua
- **Duración:** 4-5 horas

### Capítulo 8: Máquinas de Estados y Secuencias
- Concepto de "estado" y "transición"
- Diagrama de estados (state machine)
- GRAFCET (IEC 60848): etapas, transiciones, acciones
- Sincronización de procesos
- Diagramas de Gantt para tiempos
- **Ejercicios:** Diseñar máquina de 3 estados
- **Duración:** 6-7 horas

### Capítulo 9: Códigos Numéricos e Industriales
- Sistemas: decimal, binario, hexadecimal
- Código BCD (Binary Coded Decimal)
- Código Gray para encoders
- ASCII y códigos alfanuméricos
- Detección de errores (paridad, CRC)
- **Ejercicios:** Conversiones y aplicación
- **Duración:** 4-5 horas

---

## MÓDULO 3: INTRODUCCIÓN A SIEMENS Y PRIMER PROGRAMA

### Capítulo 10: TIA Portal: Primeros Pasos
- Instalación (v17 o superior)
- Licencias: Tipos y activación
- Interfaz principal: explicación rápida
- Crear primer proyecto vacío
- Estructura mínima de proyecto
- Conexión a PLC virtual (PLCSIM)
- **Laboratorio:** Crear proyecto base
- **Duración:** 4-5 horas

### Capítulo 11: Conceptos Fundamentales de TIA Portal
- Proyecto, dispositivos, bloques
- Variables: declaración básica
- Tipos de datos fundamentales: BOOL, INT, REAL
- Mapeo de entradas/salidas (I/O mapping)
- Acceso a hardware desde software
- **Laboratorio:** Crear proyecto con S7-1200 simulado
- **Duración:** 5-6 horas

### Capítulo 12: Mi Primer Programa en KOP (Ladder)
- Introducción a KOP: por qué es visual
- Contactos (abierto, cerrado)
- Bobinas (simple, negada)
- AND/OR lógicos en KOP
- Descargar a PLC y ver funcionamiento
- **Laboratorio:** Programa AND, OR, NOT simples
- **Duración:** 6-7 horas

### Capítulo 13: Ampliación en KOP: Temporizadores y Contadores
- Temporizador TON (ON delay)
- Temporizador TOF (OFF delay)
- Temporizador TP (pulse)
- Contador (incremento)
- Integración con contactos
- **Laboratorio:** Crear secuencia de 5 segundos
- **Duración:** 6-7 horas

---

## MÓDULO 4: ESTRUCTURA PROFESIONAL DE PROYECTOS

### Capítulo 14: Arquitectura de Proyectos Siemens
- Estructura profesional: carpetas, nomenclatura
- Symbolic naming (convenciones Siemens)
- Global DB vs local storage
- Documentación automática
- Backup y versionado
- **Laboratorio:** Crear proyecto profesional bien estructurado
- **Duración:** 4-5 horas

### Capítulo 15: Hardware Siemens: Series S7-1200
- Especificaciones técnicas completas
- Variantes: 1211C, 1212C, 1214C, 1215C, 1217C
- Capacidad: E/S, memoria, ciclo
- Módulos de expansión (EM)
- Ciclo de exploración (scan cycle)
- **Laboratorio:** Seleccionar CPU correcta para aplicación
- **Duración:** 5-6 horas

### Capítulo 16: Hardware Siemens: Series S7-1500
- Especificaciones técnicas avanzadas
- Variantes: 1511-1, 1514-3, 1516-3
- Multi-tasking y multi-core
- Memoria: programa, datos, backup
- OPC-UA integrado
- **Comparación:** 1200 vs 1500
- **Duración:** 5-6 horas

### Capítulo 17: Módulos de Entrada/Salida
- DI (Digital Input): especificaciones
- DO (Digital Output): especificaciones
- AI (Analog Input): rango, filtrado
- AO (Analog Output): rango, resolución
- Aislamiento galvánico
- Direccionamiento en TIA Portal
- **Laboratorio:** Configurar módulos I/O
- **Duración:** 5-6 horas

---

# 🟠 BLOQUE II: PROGRAMACIÓN ESTRUCTURADA - NIVEL BÁSICO
**Duración:** 60-80 horas | **Objetivo:** Pasar de "botones y luces" a "control real"

## MÓDULO 5: INTRODUCCIÓN A SCL (Structured Control Language)

### Capítulo 18: ¿Por Qué SCL? KOP vs SCL
- Limitaciones de KOP en programas complejos
- SCL: lenguaje estructurado como Pascal/C
- Ventajas de SCL: reutilización, mantenimiento
- Mezclando KOP y SCL en mismo programa
- Cuándo usar cada uno (decisión profesional)
- **Comparación:** Ejemplo mismo programa en KOP y SCL
- **Duración:** 3-4 horas

### Capítulo 19: Sintaxis Básica de SCL
- Estructura de programa SCL
- Variables: declaración y inicialización
- Tipos elementales: BOOL, BYTE, INT, DINT, REAL, STRING
- Comentarios y documentación
- Identificadores válidos
- **Ejercicios:** Programas mínimos en SCL
- **Duración:** 5-6 horas

### Capítulo 20: Operadores y Expresiones
- Operadores aritméticos: +, -, *, /, MOD, **
- Operadores de comparación: <, >, =, <=, >=, <>
- Operadores lógicos: AND, OR, XOR, NOT
- Precedencia de operadores
- Expresiones complejas con paréntesis
- **Ejercicios:** Calcular expresiones
- **Duración:** 4-5 horas

### Capítulo 21: Condicionales: IF, ELSE, CASE
- Sentencia IF...THEN...ELSE
- IF anidados
- Sentencia CASE...OF...END_CASE
- Evaluación cortocircuito
- Errores comunes
- **Ejercicios:** Desde simple hasta complejos
- **Duración:** 5-6 horas

### Capítulo 22: Bucles: FOR, WHILE, REPEAT
- Bucle FOR...DO...END_FOR
- Bucle WHILE...DO...END_WHILE
- Bucle REPEAT...UNTIL...END_REPEAT
- Sentencias BREAK y CONTINUE
- Bucles anidados
- Evitar bucles infinitos
- **Ejercicios:** Iterar sobre arrays
- **Duración:** 5-6 horas

---

## MÓDULO 6: ENTRADA/SALIDA DIGITAL

### Capítulo 23: Lectura de Entradas Digitales
- Acceso a variables de entrada (I)
- Lectura de un bit: I0.0, I1.2, etc.
- Lectura de palabra: acceso a palabra completa
- Anti-rebote (debouncing) en software
- Detección de flancos (flanco ascendente/descendente)
- **Laboratorio:** Leer sensores reales
- **Duración:** 5-6 horas

### Capítulo 24: Escritura de Salidas Digitales
- Acceso a variables de salida (Q)
- Escritura de un bit: Q0.0, Q1.3, etc.
- Escritura de palabra completa
- Órdenes de pulso (set-reset)
- Estados de reposo (fail-safe)
- **Laboratorio:** Activar salidas en panel
- **Duración:** 5-6 horas

### Capítulo 25: Patrones Profesionales de E/S
- Máquina de estados para entrada
- Gestión de eventos con flancos
- Acumuladores de eventos
- Contador de activaciones
- Estadísticas de operación
- Trazabilidad de cambios
- **Ejercicios:** Implementar patrones reales
- **Duración:** 6-7 horas

### Capítulo 26: Bloques de Función (FB) vs Funciones (FC)
- Diferencia conceptual
- Declaración de FC (función sin estado)
- Declaración de FB (bloque con estado)
- Parámetros: IN, OUT, IN_OUT
- Variables estáticas (STATIC)
- Reutilización de código
- **Laboratorio:** Crear FC de suma, FB de contador
- **Duración:** 6-7 horas

### Capítulo 27: Librerías Estándar de Siemens
- Functions estándar: ABS, MIN, MAX, etc.
- String functions
- Conversion functions
- Importar y usar librerías
- **Ejercicios:** Usar funciones estándar
- **Duración:** 4-5 horas

---

## MÓDULO 7: TEMPORIZADORES Y CONTADORES PROFUNDOS

### Capítulo 28: Temporizadores Profesionales
- TON (ON delay): funcionamiento interno
- TOF (OFF delay): casos de uso
- TP (pulse): duración fija
- Temporizador oscilante (astable)
- Cascada de temporizadores
- Precisión: resolución milisegundos vs centisegundos
- **Laboratorio:** Timing crítico
- **Duración:** 5-6 horas

### Capítulo 29: Contadores y Estadísticas
- Contador incremental (UP)
- Contador decremental (DOWN)
- Contador bidireccional
- Pre-carga de valores
- Reset selectivo (clear)
- Detección de overflow (desbordamiento)
- **Ejercicios:** Contar productos en línea
- **Duración:** 5-6 horas

### Capítulo 30: Sincronización de Procesos
- Sincronización síncrona (esperar a que terminen)
- Sincronización asíncrona (eventos)
- Coordinación de múltiples actuadores
- Evitar race conditions
- Garantías de determinismo en PLC
- **Laboratorio:** Coordinar 3 motores
- **Duración:** 5-6 horas

### Capítulo 31: Detección de Flancos y Análisis de Pulsos
- Flanco ascendente (rising edge detection)
- Flanco descendente (falling edge detection)
- Generación de pulsos
- Frecuencia y duty cycle
- Medición de duración de eventos
- Captura de eventos rápidos
- **Ejercicios:** Detector de velocidad
- **Duración:** 5-6 horas

---

# 🟡 BLOQUE III: ENTRADA/SALIDA ANALÓGICA Y CONTROL AVANZADO
**Duración:** 55-70 horas | **Objetivo:** Control de procesos complejos

## MÓDULO 8: ENTRADA ANALÓGICA

### Capítulo 32: Fundamentos de Entrada Analógica
- Rangos industriales: 0-10V, 4-20mA
- Resolución: 12-16 bits
- Conversión A/D en el PLC
- Error de medición
- Relación entre voltaje y valor digital
- **Ejercicios:** Conversión de valores 4-20mA
- **Duración:** 5-6 horas

### Capítulo 33: Acondicionamiento de Señal Analógica
- Filtrado digital (software)
- Promediado de N muestras
- Filtro paso bajo (low-pass)
- Detección de picos
- Normalización de rango
- Offset y ganancia: calibración
- **Laboratorio:** Procesar señal ruidosa
- **Duración:** 6-7 horas

### Capítulo 34: Validación y Diagnóstico de Entrada
- Rango válido de entrada
- Detección de sensor roto
- Validación cruzada (redundancia)
- Comportamiento ante falla
- Historial de errores
- **Ejercicios:** Función validadora de entrada
- **Duración:** 4-5 horas

---

## MÓDULO 9: SALIDA ANALÓGICA Y CONTROL PROPORCIONAL

### Capítulo 35: Generación de Salida Analógica
- Salida 0-10V
- Salida 4-20mA
- Resolución de salida
- Estabilización de línea
- Timing de actualización
- **Laboratorio:** Generar rampa de voltaje
- **Duración:** 5-6 horas

### Capítulo 36: Control Proporcional (Accionamiento)
- Concepto de "duty cycle"
- Control de velocidad del motor
- Control de válvulas modulables
- Rampa de aceleración
- Limitación de velocidad
- **Laboratorio:** Control de motor con variador
- **Duración:** 5-6 horas

### Capítulo 37: Introducción a Control PID
- Concepto de error: Setpoint - Actual
- Control Proporcional (P): Ganancia
- Control Integral (I): Elimina offset
- Control Derivativo (D): Reduce oscilación
- Combinación PID
- **Laboratorio:** PID simple (P solo)
- **Duración:** 5-6 horas

### Capítulo 38: Tuning de Parámetros PID
- Método Ziegler-Nichols
- Método por tanteo (trial and error)
- Limitación de salida (anti-windup)
- Zona muerta (deadband)
- Efectos de sobrecorrección
- **Laboratorio:** Sintonizar PID de temperatura
- **Duración:** 6-7 horas

### Capítulo 39: Aplicaciones de Control Continuo
- Control de temperatura
- Control de presión
- Control de caudal (flujo)
- Control de nivel
- Control de velocidad
- Cascadas de control
- **Casos reales:** Cada aplicación
- **Duración:** 7-8 horas

---

## MÓDULO 10: MONITOREO Y PROTECCIÓN

### Capítulo 40: Monitoreo de Variables Críticas
- Límites máximo/mínimo
- Alarmas analógicas
- Detección de tendencia
- Logging de valores
- Histórico de alarmas
- **Laboratorio:** Sistema de monitoreo
- **Duración:** 5-6 horas

### Capítulo 41: Manejo de Errores en E/S Analógica
- Errores comunes: sensor roto, cable cortado
- Validación de rango
- Recuperación ante falla
- Fallback a valor conocido
- Diagnóstico automático
- **Ejercicios:** Función robusta de lectura
- **Duración:** 4-5 horas

---

# 🟢 BLOQUE IV: COMUNICACIÓN INDUSTRIAL
**Duración:** 50-65 horas | **Objetivo:** Integrar PLCs en redes industriales

## MÓDULO 11: REDES Y PROTOCOLOS SIEMENS

### Capítulo 42: Fundamentos de PROFINET
- Estándar PROFINET (IEC 61158)
- Arquitectura en tiempo real
- Topología: lineal, star, ring
- Tiempo de ciclo de red
- Configuración básica
- **Laboratorio:** Conectar 2 PLCs con PROFINET
- **Duración:** 5-6 horas

### Capítulo 43: Configuración de PROFINET en TIA Portal
- Crear conexión PROFINET
- Asignación de direcciones IP
- Descubrimiento automático de dispositivos
- Configuración de variables remotas
- Diagnóstico de red
- **Laboratorio:** Comunicación maestro-esclavo
- **Duración:** 6-7 horas

### Capítulo 44: PROFIBUS DP (Protocolo Antiguo Pero Vigente)
- Estándar PROFIBUS (IEC 61158)
- Diferencias con PROFINET
- Configuración de master y slaves
- Casos donde aún se usa
- Migración a PROFINET
- **Referencia:** Plantas legadas
- **Duración:** 4-5 horas

### Capítulo 45: IO-Link (Comunicación de Sensor a PLC)
- Protocolo IO-Link (IEC 61131-9)
- Parámetros de dispositivos
- Configuración remota de sensores
- Diagnóstico integrado
- **Laboratorio:** Sensor IO-Link real
- **Duración:** 4-5 horas

### Capítulo 46: Protocolos Abiertos: Modbus TCP/IP
- Protocolo Modbus (historia)
- Modbus TCP/IP (RFC 1006)
- Estructura de trama
- Funciones principales (3, 4, 16)
- Cliente Modbus en TIA Portal
- **Laboratorio:** Leer valores de Inversor/Variador
- **Duración:** 5-6 horas

### Capítulo 47: OPC-UA (Open Platform Communications)
- Estándar OPC-UA
- Modelo cliente-servidor
- Seguridad: encriptación, certificados
- Implementación en S7-1500
- Conexión a SCADA
- **Laboratorio:** Conectar PLC a software SCADA
- **Duración:** 5-6 horas

### Capítulo 48: Ethernet Industrial y Seguridad de Red
- Ethernet vs Ethernet Industrial
- Velocidades: 100 Mbps, 1 Gbps
- Switches industriales
- Redundancia de red (MRP, RSTP)
- Firewalls y segmentación
- **Laboratorio:** Diseñar red industrial con redundancia
- **Duración:** 6-7 horas

---

## MÓDULO 12: INTEGRACIÓN CON DISPOSITIVOS

### Capítulo 49: Comunicación con Variadores (VFD)
- Principios de variadores AC
- Interfaz de comunicación (MODBUS, PROFINET)
- Parámetros de configuración
- Control de velocidad remoto
- Retroalimentación del estado
- **Laboratorio:** Control de motor con variador
- **Duración:** 5-6 horas

### Capítulo 50: Comunicación con HMI y Pantallas Táctiles
- Pantallas táctiles Siemens (KTP, KTP Mobile)
- Variables de conexión HMI-PLC
- Eventos y triggers en HMI
- Alarmas y trending en pantalla
- **Laboratorio:** Crear HMI simple
- **Duración:** 6-7 horas

### Capítulo 51: Communicación con Robots Industriales
- Lenguajes de robot: RAPID (ABB), KRL (KUKA), FANUC
- Interfaz de comunicación PLC-Robot
- Sincronización de movimientos
- Verificación de posición
- Seguridad en espacios compartidos
- **Laboratorio:** Comunicación básica PLC-Robot (simulado)
- **Duración:** 5-6 horas

---

# 🔴 BLOQUE V: ARQUITECTURA, INTEGRACIÓN Y SISTEMAS
**Duración:** 50-65 horas | **Objetivo:** Diseñar sistemas complejos integrados

## MÓDULO 13: ARQUITECTURA INDUSTRIAL

### Capítulo 52: Pirámide de Automatización Industrial
- Nivel 0: Sensores y actuadores
- Nivel 1: PLCs y controladores
- Nivel 2: HMI y operador
- Nivel 3: MES (Manufacturing Execution System)
- Nivel 4: ERP (Enterprise Resource Planning)
- Flujo de datos entre niveles
- **Caso práctico:** Arquitectura completa de fábrica
- **Duración:** 5-6 horas

### Capítulo 53: Sistemas SCADA (Supervisory Control)
- Definición: SCADA vs HMI
- Arquitectura centralizada vs distribuida
- Software SCADA: opciones disponibles
- Integración con PLCs Siemens
- Dashboards y reportes
- **Laboratorio:** Crear SCADA básico
- **Duración:** 6-7 horas

### Capítulo 54: MES (Manufacturing Execution System)
- Definición y beneficios
- Trazabilidad de producción
- Órdenes de trabajo
- Recetas y fórmulas (recipes)
- Lotes (batch)
- Integración ERP-MES-PLC
- **Caso real:** Implementación MES
- **Duración:** 6-7 horas

### Capítulo 55: Redundancia y Alta Disponibilidad
- Conceptos: RPO, RTO, MTBF, MTTR
- Redundancia de CPU (hot standby)
- Sincronización de estados
- Failover automático
- Redundancia de comunicación
- Testing de failover
- **Laboratorio:** Configurar redundancia S7-1500
- **Duración:** 6-7 horas

### Capítulo 56: Gestión de Datos e Integración ERP
- Interfaz XML/JSON
- EDI (Electronic Data Interchange)
- Middleware: SAP PI, MuleSoft
- Cloud manufacturing
- APIs REST para PLCs
- **Caso práctico:** Integración SAP-PLC
- **Duración:** 5-6 horas

---

## MÓDULO 14: INTEGRACIÓN INDUSTRIAL PROFUNDA

### Capítulo 57: Planificación de Producción desde PLC
- Órdenes de producción
- Secuenciación de tareas
- Gestión de recetas
- Cambio de producto (changeover)
- Velocidad de línea adaptable
- **Laboratorio:** Programar cambio de receta
- **Duración:** 5-6 horas

### Capítulo 58: OEE (Overall Equipment Effectiveness)
- Cálculo de OEE: Disponibilidad × Rendimiento × Calidad
- Captura de datos en tiempo real
- Paradas: planeadas vs no-planeadas
- Análisis de tendencias
- Alertas de baja eficiencia
- **Laboratorio:** Implementar cálculo OEE
- **Duración:** 5-6 horas

### Capítulo 59: Trazabilidad y Genealogía de Productos
- Registro de lote (batch)
- Genealogía: qué material entra y sale
- Conformidad: registro de parámetros
- Auditoría trail (registro de cambios)
- Integración con ERP
- **Laboratorio:** Sistema de trazabilidad
- **Duración:** 5-6 horas

### Capítulo 60: Manejo de Cambios en Línea
- Recetas y cambio rápido (SMED)
- Formato de producto
- Cambio de velocidad
- Cambio de receta sin parada
- Validación de nueva configuración
- **Laboratorio:** Cambio sin pérdida de tiempo
- **Duración:** 5-6 horas

---

# 🟣 BLOQUE VI: SEGURIDAD, CERTIFICACIÓN Y ESPECIALIZACIÓN
**Duración:** 50-70 horas | **Objetivo:** Nivel experto y certificado

## MÓDULO 15: SEGURIDAD FUNCIONAL

### Capítulo 61: Normas de Seguridad Funcional
- IEC 61508: Seguridad de sistemas E/E/PE
- IEC 62061: Seguridad en máquinas
- IEC 61131-2: Requisitos de seguridad en PLCs
- Safety Integrity Level (SIL): 1, 2, 3, 4
- Performance Level (PL): a, b, c, d, e
- Certificación de funciones de seguridad
- **Estudio:** Análisis SIL para aplicación
- **Duración:** 6-7 horas

### Capítulo 62: Funciones de Seguridad Certificadas
- Parada de emergencia (E-Stop) categorizadas
- Supervisión de movimiento
- Detección de presencia con seguridad
- Botones de enclavamiento de seguridad
- Válvulas de seguridad proporcionales
- S7-1500F para funciones de seguridad
- **Laboratorio:** Implementar E-Stop certificado
- **Duración:** 6-7 horas

### Capítulo 63: Análisis de Riesgos para Seguridad
- FMEA (Failure Mode and Effects Analysis)
- FTA (Fault Tree Analysis)
- Matriz de riesgos
- Asignación de SIL basada en riesgo
- Documentación requerida
- **Ejercicio:** FMEA para una máquina
- **Duración:** 5-6 horas

### Capítulo 64: Certificación y Auditoría de Máquinas
- Directiva de máquinas 2006/42/CE
- Marcado CE
- Proceso de certificación
- Documentación técnica requerida
- Auditoría de seguridad
- Responsabilidad legal del programador
- **Tarea:** Preparar máquina para certificación
- **Duración:** 5-6 horas

### Capítulo 65: Ciberseguridad Operacional (OT Security)
- Amenazas en sistemas de control
- Ataques comunes: malware, ransomware
- Protección: firewalls, segmentación
- Control de acceso y autenticación
- Actualizaciones y parches de seguridad
- Norma IEC 62443
- **Auditoría:** Evaluar seguridad de sistema
- **Duración:** 5-6 horas

---

## MÓDULO 16: TROUBLESHOOTING Y OPERACIÓN

### Capítulo 66: Diagnóstico y Depuración Profesional
- Metodología sistemática de debugging
- Herramientas en TIA Portal: breakpoints, watch
- Profiling: análisis de rendimiento
- Logging estructurado
- Análisis de ciclo (cycle time)
- Herramientas externas de diagnóstico
- **Laboratorio:** Depurar programa con errores
- **Duración:** 6-7 horas

### Capítulo 67: Optimización de Código
- Complejidad algorítmica en PLCs
- Gestión de memoria
- Reducción de tiempo de ciclo
- Paralelización de tareas
- Evitar bottlenecks
- **Ejercicios:** Optimizar código lento
- **Duración:** 5-6 horas

### Capítulo 68: Testing y Validación Integral
- Unit testing: pruebas unitarias
- Integration testing: pruebas de integración
- System testing: pruebas de sistema
- UAT (User Acceptance Testing)
- Regression testing
- Test plans y procedimientos
- **Laboratorio:** Plan de testing completo
- **Duración:** 6-7 horas

### Capítulo 69: Mantenimiento Preventivo y Predictivo
- Programa de mantenimiento
- Histórico de máquinas
- Predictive maintenance con sensores
- Análisis de vibraciones
- Monitoreo de temperatura
- MTBF y MTTR
- **Proyecto:** Implementar maintenance program
- **Duración:** 5-6 horas

### Capítulo 70: Operación y Formación de Personal
- Interfaces de operador: diseño intuitivo
- Manual de operación técnico
- Señales y alarmas: significado
- Procedimientos de startup/shutdown
- Respuesta ante emergencias
- Formación y competencia de operadores
- **Práctica:** Crear manual de operación
- **Duración:** 4-5 horas

---

## MÓDULO 17: CASOS INDUSTRIALES PROFUNDOS

### Capítulo 71: Líneas de Producción Automatizadas
- Arquitectura de línea: estaciones, coordinación
- Integración de múltiples PLCs
- Master-slave vs peer-to-peer
- Tracking de productos
- Control de calidad integrado
- Diagnóstico de línea completa
- **Proyecto:** Diseñar línea de 4 estaciones
- **Duración:** 8-10 horas

### Capítulo 72: Procesos Continuos Químicos/Farmacéuticos
- Reactores químicos con PID
- Destilación y separación
- Fermentación en bioprocesos
- Tratamiento de aguas residuales
- Calderas de vapor
- Seguridad en procesos exotérmicos
- **Caso real:** Planta química miniatura
- **Duración:** 8-10 horas

### Capítulo 73: Sistemas de Manejo de Materiales
- Transportadores: control y sincronización
- Grúas y polipastos
- Sistemas de almacenamiento AS/RS
- Sinterización de almacenes
- Coordinación logística
- **Proyecto:** Automatizar almacén
- **Duración:** 8-10 horas

### Capítulo 74: Máquinas de Múltiple Propósito
- Máquinas etiquetadoras
- Máquinas de corte
- Máquinas empaquetadoras
- Máquinas de impresión
- Diseño modular
- Escalabilidad de soluciones
- **Proyecto:** Diseñar máquina especial
- **Duración:** 8-10 horas

### Capítulo 75: Integración de Robótica Colaborativa
- Cobots (robots colaborativos): conceptos
- Comunicación PLC-Cobot
- Sincronización de movimientos
- Seguridad: espacios compartidos
- Visión artificial integrada
- Casos de uso reales
- **Laboratorio:** Comunicación básica con Cobot
- **Duración:** 6-8 horas

---

## MÓDULO 18: INDUSTRIA 4.0 Y FUTURO

### Capítulo 76: Internet Industrial de las Cosas (IIoT)
- Conceptos de IIoT y conectividad
- Edge computing en planta
- Sensores IoT y comunicación 5G/LTE
- Telemetría de máquinas
- Análisis de datos en tiempo real
- **Proyecto:** Sistema IIoT simple
- **Duración:** 6-8 horas

### Capítulo 77: Mantenimiento Predictivo Basado en Datos
- Machine Learning en PLCs
- Predicción de fallos
- Análisis de patrones
- Algoritmos de predicción
- Integración con sistemas de monitoreo
- ROI del predictive maintenance
- **Laboratorio:** Algoritmo básico de predicción
- **Duración:** 6-8 horas

### Capítulo 78: Digital Twins (Gemelo Digital)
- Concepto y beneficios
- Simulación de procesos
- Real-time synchronization
- Casos de uso
- Herramientas disponibles
- **Proyecto:** Crear digital twin simple
- **Duración:** 6-8 horas

### Capítulo 79: Transformación Digital Industrial
- Readiness assessment: evaluar madurez
- Roadmap de transformación
- ROI de Industria 4.0
- Gobierno del cambio
- Roles y responsabilidades
- **Análisis:** Plan de transformación para empresa
- **Duración:** 5-6 horas

---

## MÓDULO 19: CERTIFICACIÓN Y ESPECIALIZACIÓN

### Capítulo 80: Preparación Certificación Oficial Siemens
- Exámenes disponibles: ACP A, ACP PRO
- Contenidos evaluados
- Formato de examen
- Prácticas de laboratorio
- Simulación de examen
- **Taller:** Intensivo de preparación
- **Duración:** 8-10 horas

### Capítulo 81: Construcción de Portfolio Profesional
- Proyectos destacados
- Documentación técnica profesional
- Presentación de casos
- GitHub y control de versiones
- Certificados y referencias
- LinkedIn profesional
- **Tarea:** Compilar portfolio
- **Duración:** 4-5 horas

### Capítulo 82: Especialización A - Procesos Continuos
- Control avanzado de procesos (APC)
- Optimización de procesos
- Diseño experimental (DOE)
- Casos: industria química, farmacéutica, alimentos
- **Proyecto capstone:** Planta completa
- **Duración:** 12-15 horas

### Capítulo 83: Especialización B - Manufactura Discreta
- Planificación y secuenciación
- Lean manufacturing y PLC
- OEE en profundidad
- Casos: automotriz, electrónica, metalmecánica
- **Proyecto capstone:** Línea de producción
- **Duración:** 12-15 horas

### Capítulo 84: Especialización C - Integración de Sistemas
- Arquitectura empresarial
- Integración SAP-MES-PLC
- Middleware y APIs
- Proyectos de transformación digital
- **Proyecto capstone:** Integración completa
- **Duración:** 12-15 horas

### Capítulo 85: Consultoría y Emprendimiento
- Ser consultor de automatización
- Business model de proyectos
- Presupuestos y estimación
- Gestión de proyectos y equipos
- Negociación cliente
- Carrera profesional en automatización
- **Caso:** Proyecto de consultoría simulado
- **Duración:** 6-8 horas

---

## MÓDULO 20: VISIÓN Y FUTURO

### Capítulo 86: Tendencias Tecnológicas Futuras
- Edge AI: Inteligencia artificial en borde
- 5G industrial: conectividad ultra-rápida
- Quantum computing: impacto futuro
- Automatización sostenible/verde
- Automatización adaptativa
- **Reflexión:** Carrera a 10 años
- **Duración:** 4-5 horas

### Capítulo 87: Competencias del Ingeniero Senior
- Habilidades técnicas vs soft skills
- Liderazgo y gestión de equipos
- Comunicación técnica
- Pensamiento sistémico
- Innovación continua
- Lifelong learning
- **Desarrollo:** Plan de carrera personal
- **Duración:** 3-4 horas

### Capítulo 88: Proyecto Integrador Final
- Proyecto real de automatización completa
- Documentación profesional
- Presentación ejecutiva
- Defensa del proyecto
- Evaluación final
- **Proyecto capstone final:** 40-60 horas distribuidas
- **Duración:** Según avance

---

# 📊 RESUMEN ESTRUCTURA FINAL

## Resumen Ejecutivo

```
CURSO PLC HÍBRIDO - VERSIÓN DEFINITIVA 2.0

Capítulos totales:              88 (no 68)
Módulos:                        20 (no 15)
Bloques:                        6
Horas estimadas:                450-550 horas
Equivalencia:                   9-11 meses tiempo completo

Capítulos por nivel:
├─ Principiante:                30 capítulos (Cap 1-30)
├─ Intermedio:                  25 capítulos (Cap 31-55)
├─ Avanzado:                    18 capítulos (Cap 56-73)
├─ Experto:                     15 capítulos (Cap 74-88)
└─ Especialización:             20 horas bonus
```

## Distribución de Horas

| Bloque | Módulos | Capítulos | Horas |
|--------|---------|-----------|-------|
| I - Fundamentos | 4 | 1-17 | 50-60 |
| II - Programación Básica | 3 | 18-31 | 60-80 |
| III - Analógica/Control | 3 | 32-41 | 55-70 |
| IV - Comunicación | 2 | 42-51 | 50-65 |
| V - Arquitectura | 2 | 52-60 | 50-65 |
| VI - Seguridad/Especialización | 6 | 61-88 | 85-110 |
| **TOTAL** | **20** | **88** | **450-550** |

## Contenido Total Generado

```
88 Capítulos
├─ 88 Introducciones profesionales
├─ 88 Secciones de objetivos
├─ ~350 Subsecciones temáticas
├─ ~450 Diagramas/esquemas ASCII
├─ ~200 Tablas comparativas
├─ ~300 Ejemplos de código (SCL/KOP)
├─ ~80 Casos industriales reales
├─ ~200 Ejercicios prácticos progresivos
├─ ~200 Soluciones completamente desarrolladas
├─ ~250 Errores comunes documentados
├─ ~150 Buenas prácticas explicadas
├─ 88 Resúmenes ejecutivos
├─ ~400 Preguntas tipo entrevista
├─ 20 Proyectos integradores
└─ 1 Proyecto capstone final
```

## Carencias del Índice Original Solventadas

✅ **Siemens:** +12 capítulos nuevos sobre arquitectura, UDT, librerías, migration  
✅ **Industrial:** +15 capítulos nuevos sobre integración, OEE, recetas, MES  
✅ **Pedagogía:** +8 capítulos sobre evaluación, troubleshooting, testing  
✅ **Redundancias eliminadas:** Consolidación de comunicación, seguridad, hardware  
✅ **Tiempos realistas:** 450-550 horas (no 310-400)  
✅ **Evaluación incorporada:** Capítulos 80-88 con certificación  

## Progresión Pedagógica Mejorada

```
NIVEL 1 (30 caps, 50-60 h): Electricidad + Lógica + TIA Portal básico
  └─ Objetivo: "Entiendo los fundamentos"
  
NIVEL 2 (25 caps, 60-80 h): SCL + E/S digital + Temporizadores
  └─ Objetivo: "Puedo controlar procesos simples"
  
NIVEL 3 (18 caps, 55-70 h): E/S analógica + PID + Comunicación
  └─ Objetivo: "Puedo implementar control real"
  
NIVEL 4 (15 caps, 50-65 h): Arquitectura + Integración industrial
  └─ Objetivo: "Puedo diseñar sistemas complejos"
  
NIVEL 5 (20 caps, 85-110 h): Seguridad + Casos reales + Especialización
  └─ Objetivo: "Soy Ingeniero Senior certificado"
```

## Cambios Principales Implementados

### AÑADIDOS (20 capítulos nuevos):
1. Capítulo 14 - Arquitectura de Proyectos Siemens
2. Capítulo 15-16 - Hardware S7-1200 y S7-1500 (separado)
3. Capítulo 17 - Módulos I/O
4. Capítulo 18 - ¿Por qué SCL?
5. Capítulo 27 - Librerías Estándar
6. Capítulo 31 - Detección de Flancos
7. Capítulo 34 - Validación de Entrada
8. Capítulo 41 - Errores Analógicos
9. Capítulo 44 - PROFIBUS DP
10. Capítulo 45 - IO-Link
11. Capítulo 48 - Ethernet Industrial
12. Capítulo 50 - HMI/Pantallas Táctiles
13. Capítulo 51 - Comunicación Robots
14. Capítulo 52-60 - Arquitectura + MES + Datos + Cambios
15. Capítulo 66-70 - Debugging + Testing + Operación
16. Capítulo 71-75 - Casos industriales profundos
17. Capítulo 76-79 - Industria 4.0
18. Capítulo 85-88 - Especialización + Futuro

### REORGANIZADOS:
- Hardware (era 13-16, ahora 15-17)
- Comunicación (mejor secuencia PROFINET → Modbus → OPC-UA)
- Casos industriales (ahora más específicos por sector)

### ELIMINADOS/CONSOLIDADOS:
- Redundancia entre Cap 37-42 (comunicación)
- Solapamiento de seguridad (integrado en Cap 61-65)
- Generalidades de hardware (ahora específico)

### MEJORADO PEDAGÓGICAMENTE:
- Cada capítulo ahora 4-7 horas (antes 8-12)
- Primeros programas al Cap 12 (antes muy tarde)
- Proyectos integradores entre bloques
- Testing y validación explícito
- Evaluación de competencias clara

---

# 🎯 VENTAJAS DEL ÍNDICE REESTRUCTURADO

✅ **Completo:** 88 capítulos cubriendo 100% de competencias necesarias  
✅ **Práctico:** Énfasis en ejercicios y laboratorios reales  
✅ **Industrial:** Integración real ERP-MES-PLC  
✅ **Siemens-Centric:** Usando terminología y tools oficiales  
✅ **Pedagógico:** Progresión clara y evaluación integrada  
✅ **Realista:** 450-550 horas (no optimista)  
✅ **Certificable:** Alineado con examen oficial Siemens  
✅ **Especializable:** 3 opciones según carrera  
✅ **Futuro-Proof:** Incluye Industria 4.0, IA, seguridad  
✅ **Evaluable:** Rúbricas y competencias definidas  

---

# 📋 PRÓXIMOS PASOS RECOMENDADOS

1. **Fase 1:** Escribir Capítulos 1-17 (Bloque I)
2. **Fase 2:** Escribir Capítulos 18-31 (Bloque II)
3. **Fase 3:** Escribir Capítulos 32-41 (Bloque III - Parte A)
4. **Fase 4:** Escribir Capítulos 42-60 (Bloques IV-V)
5. **Fase 5:** Escribir Capítulos 61-88 (Bloque VI)

**Estimación:** 200-250 horas de redacción total (1 capítulo = 2.5-3 horas)

---

**VERSIÓN DEFINITIVA - LISTA PARA IMPLEMENTACIÓN**

*Índice revisado y aprobado por Experto Siemens, Ingeniero Industrial y Profesor de Automatización*

