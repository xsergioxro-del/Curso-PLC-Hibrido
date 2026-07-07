# CURSO PLC HÍBRIDO - ÍNDICE COMPLETO

**Subtítulo:** De Electricista de Baja Tensión a Ingeniero de Automatización Senior  
**Objetivo:** Formación profesional integral en programación de PLCs Siemens y automatización industrial  
**Duración estimada:** 180-220 horas (equivalente a 6 meses a tiempo completo)  
**Nivel final:** Ingeniero Senior de Automatización Industrial certificado

---

## ESTRUCTURA DEL CURSO

El curso se divide en **6 BLOQUES TEMÁTICOS**, cada uno con **3-4 MÓDULOS**, para un total de **22 CAPÍTULOS**.

---

# 🔵 BLOQUE I: FUNDAMENTOS Y PREREQUISITOS (Nivel Principiante)
**Duración:** 40-50 horas | **Objetivo:** Establecer base sólida en electricidad y conceptos fundamentales

## MÓDULO 1: FUNDAMENTOS ELÉCTRICOS APLICADOS

### Capítulo 1: Conceptos Eléctricos Fundamentales
- Revisión de magnitudes eléctricas (voltaje, corriente, resistencia)
- Ley de Ohm y Leyes de Kirchhoff
- Potencia eléctrica (P, Q, S, Factor de Potencia)
- Circuitos AC vs DC
- Transformadores y su funcionamiento
- Motores eléctricos: tipos y características
- **Temas prácticos:** Mediciones con multímetro, cálculo de circuitos

### Capítulo 2: Componentes de Baja Tensión para Automatización
- Interruptores y pulsadores
- Relés electromagnéticos (funcionamiento y aplicaciones)
- Contactores y arrancadores suave (soft-starters)
- Protecciones: fusibles, interruptores automáticos, diferenciales
- Guardamotores (motor protectors)
- Varistores y supresores de picos
- Bobinas de desenganche (shunt coils)
- **Casos prácticos:** Diseño de tablero de control manual

### Capítulo 3: Señales Analógicas y Digitales
- Concepto de señal digital vs analógica
- Niveles lógicos (TTL, CMOS, 24VDC industrial)
- Conversión analógica-digital (A/D)
- Conversión digital-analógica (D/A)
- Ruido y EMI en sistemas industriales
- Blindaje y tierra de referencia
- Filtrado de señales
- **Ejercicios:** Adquisición y conversión de datos

### Capítulo 4: Sistemas de Seguridad Eléctrica
- Normas de seguridad (IEC 60204-1, IEC 61508)
- Categorías de seguridad (Cat 0-4)
- Parada de emergencia (E-Stop)
- Circuitos de seguridad redundantes
- Puesta a tierra y protección contra contacto indirecto
- Riesgos eléctricos en máquinas industriales
- **Práctica:** Diseño de circuito de parada de emergencia

---

## MÓDULO 2: LÓGICA Y AUTOMATIZACIÓN BÁSICA

### Capítulo 5: Álgebra de Boole y Lógica Digital
- Variables booleanas (TRUE/FALSE)
- Operaciones lógicas fundamentales (AND, OR, NOT)
- Compuertas lógicas digitales
- Expresiones booleanas y simplificación
- Tablas de verdad
- Mapas de Karnaugh
- Sistemas combinacionales vs secuenciales
- **Ejercicios:** Simplificación de expresiones lógicas

### Capítulo 6: Lógica Cableada vs Lógica Programable
- Historia de la automatización industrial
- Sistemas de relés electromecánicos
- Diagrama de contactos (esquemas de fuerza y mando)
- Ventajas y desventajas de lógica cableada
- Introducción a PLCs
- Comparativa histórica y técnica
- Casos de migración de lógica cableada a PLC
- **Estudio de caso:** Línea de producción clásica

### Capítulo 7: Máquinas de Estados y Secuencias
- Concepto de máquina de estados finitos
- Estados, transiciones y condiciones
- Diagrama de estados
- Implementación de máquinas simples
- GRAFCET (IEC 60848): etapas y transiciones
- Diagramas de Gantt para sincronización
- Aplicaciones industriales
- **Ejercicios:** Diseño de secuencias complejas

### Capítulo 8: Sistemas de Numeración y Códigos Industriales
- Sistemas numéricos: decimal, binario, octal, hexadecimal
- Conversiones entre sistemas
- Código BCD (Binary Coded Decimal)
- Código Gray
- ASCII e códigos alfanuméricos
- Paridad y detección de errores
- Aplicaciones en comunicación industrial
- **Práctica:** Conversiones y codificación

---

# 🟠 BLOQUE II: ENTORNO SIEMENS TIA PORTAL (Nivel Básico)
**Duración:** 35-45 horas | **Objetivo:** Dominar el entorno de desarrollo profesional Siemens

## MÓDULO 3: INTRODUCCIÓN A TIA PORTAL

### Capítulo 9: Instalación y Configuración del Entorno
- Requisitos del sistema
- Descarga e instalación de TIA Portal v16/v17
- Estructura del programa
- Licencias y métodos de activación
- Interfaz gráfica principal
- Personalización del workspace
- Configuración de herramientas
- Gestión de proyectos
- **Tarea práctica:** Crear primer proyecto

### Capítulo 10: Conceptos Fundamentales de TIA Portal
- Proyecto, dispositivos y bloques
- Estructura de carpetas en el proyecto
- Variables globales y locales
- Tipos de datos Siemens
- Importación de dispositivos del catálogo
- Configuración de dispositivos (hardware)
- Asignación de direcciones (I/O mapping)
- Backup y versionado de proyectos
- **Ejercicio:** Configurar proyecto base

### Capítulo 11: Programación en KOP (Ladder Diagram)
- Introducción al lenguaje KOP
- Terminología: redes, contactos, bobinas
- Contactos normalmente abiertos y cerrados
- Bobinas y bobinas negadas
- Bobinas de salida temporal (coil output)
- Funciones lógicas básicas en KOP
- Temporizadores (TON, TOF, TP)
- Contadores (contador adelante, atrás, bidireccional)
- **Ejercicios progresivos:** Desde AND simple hasta contadores

### Capítulo 12: Introducción a SCL (Structured Control Language)
- Sintaxis básica de SCL
- Variables y su declaración
- Tipos de datos fundamentales (INT, REAL, BOOL, STRING)
- Operadores aritméticos y lógicos
- Sentencias de asignación
- Comentarios y documentación
- Estructura de programas y funciones
- Compilación y errores comunes
- **Ejercicios:** Programas básicos en SCL

---

## MÓDULO 4: HARDWARE SIEMENS

### Capítulo 13: PLCs Siemens - Línea S7-1200
- Especificaciones técnicas detalladas
- Variantes: CPU 1211C, 1212C, 1214C, 1215C
- Módulos de expansión
- Capacidad de entradas/salidas
- Memoria (programa, datos, backup)
- Ciclo de exploración (scan cycle)
- Comunicación PROFINET integrada
- Puertos seriales y protocolos
- **Laboratorio:** Configurar y conectar CPU 1200

### Capítulo 14: PLCs Siemens - Línea S7-1500
- Especificaciones avanzadas
- Variantes: CPU 1511, 1512, 1514, 1515, 1516
- Módulos de ampliación de funciones
- Arquitectura multi-core
- Capacidades de comunicación avanzadas
- Memory image y particiones
- Redundancia y failover
- Comunicación OPC-UA nativa
- **Laboratorio:** Configurar y conectar CPU 1500

### Capítulo 15: Módulos de Entrada/Salida (I/O)
- Módulos digitales de entrada (DI)
- Módulos digitales de salida (DO)
- Módulos analógicos de entrada (AI)
- Módulos analógicos de salida (AO)
- Especificaciones técnicas
- Aislamiento galvánico
- Filtrado de entrada
- Capacidad de carga de salida
- **Laboratorio:** Instalar y configurar módulos I/O

### Capítulo 16: Fuentes de Alimentación y Componentes Auxiliares
- Fuentes de alimentación 24VDC
- Módulos de redundancia
- Baterías de respaldo (UPS)
- Protecciones contra sobrecorriente
- Dispositivos de monitoreo
- Cables y conectores industriales
- Estructuras de montaje (rail DIN)
- **Práctica:** Montaje físico de sistema completo

---

# 🟡 BLOQUE III: PROGRAMACIÓN EN SCL - NIVEL INTERMEDIO (Nivel Intermedio)
**Duración:** 50-60 horas | **Objetivo:** Dominar lenguaje SCL para aplicaciones profesionales

## MÓDULO 5: FUNDAMENTOS DE PROGRAMACIÓN ESTRUCTURADA EN SCL

### Capítulo 17: Tipos de Datos y Variables Avanzadas
- Tipos de datos elementales: BOOL, BYTE, INT, DINT, REAL, STRING
- Tipos de datos complejos: ARRAY, STRUCT
- Variables locales, globales y estáticas
- Variables de retención (RETAIN)
- Inicialización de variables
- Scope y visibilidad
- Conversión de tipos
- Validación de tipos (strong typing)
- **Ejercicios:** Declarar y usar diferentes tipos

### Capítulo 18: Operadores y Expresiones
- Operadores aritméticos (+, -, *, /, MOD, **)
- Operadores de comparación (<, >, =, <=, >=, <>)
- Operadores lógicos (AND, OR, XOR, NOT)
- Operadores de bit (operaciones bit a bit)
- Precedencia de operadores
- Expresiones complejas
- Evaluación de cortocircuito
- **Ejercicios:** Cálculos y expresiones

### Capítulo 19: Estructuras de Control - Condicionales
- Sentencia IF...THEN...ELSE
- IF anidados
- Sentencia CASE...OF...END_CASE
- Operador ternario (? :)
- Evaluación de condiciones múltiples
- Optimización de condiciones
- Errores comunes en condicionales
- **Ejercicios progresivos:** Desde simple hasta complejos

### Capítulo 20: Estructuras de Control - Bucles
- Bucle FOR...DO...END_FOR
- Bucle WHILE...DO...END_WHILE
- Bucle REPEAT...UNTIL...END_REPEAT
- Sentencias BREAK y CONTINUE
- Bucles anidados
- Contadores y acumuladores
- Validación de condiciones de salida
- **Ejercicios:** Implementar patrones comunes

### Capítulo 21: Funciones (FC) - Bloques de Función (FB)
- Diferencia entre FC y FB
- Declaración de funciones
- Parámetros: entrada (IN), salida (OUT), entrada-salida (IN_OUT)
- Valor de retorno
- Variables locales en funciones
- Recursión (y sus limitaciones)
- Bloques de función con estado
- Librerías estándar de Siemens
- **Ejercicios:** Crear funciones y bloques reutilizables

### Capítulo 22: Gestión de Errores y Excepciones
- Detección de errores
- Bloque TRY...CATCH...END_TRY
- Códigos de error
- Manejo de errores de I/O
- Validación de entrada
- Recuperación ante fallos
- Logging de errores
- Diagnóstico en tiempo de ejecución
- **Ejercicios:** Implementar manejo robusto de errores

---

## MÓDULO 6: ENTRADA/SALIDA DIGITAL EN SCL

### Capítulo 23: Lectura de Entradas Digitales
- Acceso a variables de entrada
- Lectura de un único bit
- Lectura de múltiples bits (acceso a palabra)
- Buffers de entrada
- Sincronización de lectura
- Anti-rebote (debouncing) en software
- Detección de flancos (rising/falling edge)
- Filtrado de entrada
- **Laboratorio:** Leer sensores reales

### Capítulo 24: Escritura de Salidas Digitales
- Acceso a variables de salida
- Escritura de un único bit
- Escritura de múltiples bits
- Órdenes pulso (pulse command)
- Control de carga
- Protección contra sobrecorriente
- Estados de reposo (fail-safe states)
- **Laboratorio:** Activar actuadores reales

### Capítulo 25: Patrones de Lectura/Escritura Profesionales
- Máquinas de estados para entrada
- Gestión de eventos mediante flancos
- Contador de ciclos de activación
- Histéresis en lecturas analógicas
- Acumuladores de eventos
- Estadísticas de operación
- Trazabilidad de cambios
- **Ejercicios:** Implementar patrones industria

### Capítulo 26: Integración Sensor-Actuador
- Secuencias sensor → PLC → actuador
- Verificación de ejecución
- Retroalimentación
- Tiempos de reacción
- Redundancia de sensores
- Diagnóstico de falta de sensor
- Casos reales: máquinas de producción
- **Laboratorio:** Sistema completo sensor-PLC-actuador

---

# 🔴 BLOQUE IV: ENTRADA/SALIDA ANALÓGICA Y CONTROL AVANZADO (Nivel Intermedio-Avanzado)
**Duración:** 45-55 horas | **Objetivo:** Implementar sistemas de control proporcional e integral

## MÓDULO 7: ENTRADA/SALIDA ANALÓGICA

### Capítulo 27: Fundamentos de Analógica en PLCs
- Rango de entrada típico (0-10V, 4-20mA)
- Resolución de conversión A/D
- Tiempo de conversión
- Errores de medición
- Calibración de entrada
- Offset y ganancia
- Linealidad y exactitud
- **Ejercicios:** Convertir valores 4-20mA

### Capítulo 28: Acondicionamiento de Señal Analógica
- Filtrado analógico vs digital
- Promediado de múltiples lecturas
- Filtro paso-bajo (low-pass filter)
- Detección de picos y valles
- Normalización de señal
- Mapeo de rangos
- Escalado de valores
- **Laboratorio:** Procesar señal ruidosa

### Capítulo 29: Salida Analógica y Control Proporcional
- Generación de 0-10V y 4-20mA
- Resolución de salida
- Estabilización de línea
- Control proporcional (accionamiento)
- Rampa de aceleración
- Control de variadores de velocidad
- Control de válvulas modulables
- **Laboratorio:** Control de motor con variador

### Capítulo 30: Sistemas de Control PID
- Conceptos de control: error, setpoint, proceso
- Control proporcional (P)
- Control integral (I)
- Control derivativo (D)
- Combinación: PID
- Tuning de parámetros (Kp, Ki, Kd)
- Métodos de sintonización (Ziegler-Nichols)
- Limitación de salida y anti-windup
- **Laboratorio:** Implementar control PID de temperatura

### Capítulo 31: Aplicaciones de Control Continuo
- Control de temperatura
- Control de presión
- Control de caudal
- Control de nivel
- Control de velocidad
- Cascadas de control
- Feedforward y retroalimentación
- **Casos reales:** Sistemas industriales

### Capítulo 32: Protección y Monitoreo de Procesos
- Límites máximo/mínimo
- Alarmas analógicas
- Detección de sensor roto
- Zona muerta (deadband)
- Validación de rango
- Comportamiento ante falla
- Diagnóstico automático
- **Ejercicios:** Implementar monitoreo completo

---

## MÓDULO 8: TEMPORIZADORES, CONTADORES Y SINCRONIZACIÓN

### Capítulo 33: Temporizadores Profesionales
- Temporizador ON-delay (TON)
- Temporizador OFF-delay (TOF)
- Temporizador de impulso (TP)
- Temporizador oscilante
- Cascada de temporizadores
- Precisión de temporizadores
- Acumulación de tiempos
- Tiempos críticos en procesos
- **Laboratorio:** Implementar temporizaciones complejas

### Capítulo 34: Contadores y Estadísticas
- Contador adelante (incremento)
- Contador atrás (decremento)
- Contador bidireccional
- Pre-carga de valor
- Reset selectivo
- Detección de overflow
- Acumuladores de ciclos
- Estadísticas de máquina
- **Ejercicios:** Contabilización en líneas de producción

### Capítulo 35: Sincronización de Procesos
- Sincronización síncrona
- Sincronización asíncrona
- Eventos y interrupciones
- Semáforos (aunque PLCs no usan)
- Coordenadas de tiempo global
- Sincronización de múltiples ejes
- Garantías de determinismo
- **Laboratorio:** Coordinar múltiples actuadores

### Capítulo 36: Detección de Flancos y Pulsos
- Flanco ascendente (rising edge detection)
- Flanco descendente (falling edge detection)
- Generación de pulsos
- Frecuencia y duty cycle
- Medición de duración de eventos
- Captura de eventos rápidos
- Funciones nativas de Siemens
- **Ejercicios:** Detectar y contar pulsos

---

# 🟢 BLOQUE V: COMUNICACIÓN INDUSTRIAL Y ARQUITECTURA (Nivel Avanzado)
**Duración:** 40-50 horas | **Objetivo:** Integrar PLCs en sistemas de red industrial

## MÓDULO 9: COMUNICACIÓN INDUSTRIAL - PROFINET

### Capítulo 37: Fundamentos de PROFINET
- Estándar PROFINET (IEC 61158, IEC 61784)
- Arquitectura en tiempo real
- Modelo cliente-servidor
- Tipos de comunicación: acíclica, cíclica, isócrona
- Configuración de dispositivos
- Asignación de direcciones IP
- Topología de red (linear, star, ring)
- **Laboratorio:** Configurar red PROFINET básica

### Capítulo 38: Comunicación PROFINET en TIA Portal
- Conexiones PROFINET en proyecto
- Direcciones IP y subredes
- Descubrimiento de dispositivos
- Configuración de variables remotas
- Transferencia de datos entre dispositivos
- Monitoreo de comunicación
- Diagnóstico de red
- **Laboratorio:** Comunicación maestro-esclavo

### Capítulo 39: Comunicación Modbus TCP/IP
- Protocolo Modbus (historia y versiones)
- Modbus TCP (RFC 1006)
- Estructura de trama
- Funciones Modbus principales
- Cliente Modbus en SCL
- Servidor Modbus en PLC
- Integración con dispositivos de terceros
- **Laboratorio:** Comunicación con VFD (variador)

### Capítulo 40: OPC-UA (Open Platform Communications)
- Estándar OPC-UA
- Arquitectura cliente-servidor
- Modelo de información
- Seguridad en OPC-UA
- Implementación en S7-1500
- Conexión a sistemas SCADA
- Interoperabilidad multiplataforma
- **Laboratorio:** Conectar PLC a SCADA mediante OPC-UA

### Capítulo 41: Ethernet Industrial y Seguridad de Red
- Ethernet industrial vs comercial
- Velocidades (Fast Ethernet, Gigabit)
- Switches industriales
- Redundancia de red (RSTP, MRP)
- Firewalls industriales
- Seguridad: encriptación y autenticación
- Aislamiento de redes
- Estándares IEC 62443
- **Laboratorio:** Diseñar red industrial segura

### Capítulo 42: Variadores de Frecuencia (VFD) y Comunicación
- Principios de variadores AC
- Comunicación con VFDs
- Protocolo MODBUS RTU
- Protocolo PROFINET en variadores
- Parámetros de configuración
- Control de velocidad remoto
- Retroalimentación de estado
- **Laboratorio:** Control de motor con variador por red

---

## MÓDULO 10: ARQUITECTURA DE SISTEMAS Y SCADA

### Capítulo 43: Arquitectura Jerárquica de Automatización
- Pirámide de automatización (niveles 0-4)
- Nivel de campo (sensores/actuadores)
- Nivel de control (PLCs)
- Nivel de supervisión (HMI/SCADA)
- Nivel de gestión (MES)
- Nivel empresarial (ERP)
- Flujo de datos entre niveles
- **Caso práctico:** Arquitectura completa de fábrica

### Capítulo 44: Sistemas HMI/SCADA
- Definición y diferencias
- SCADA arquitectura centralizada vs distribuida
- Pantallas táctiles Siemens (KTP)
- Software WinCC en PC
- Variables de conexión HMI-PLC
- Eventos y scripts en HMI
- Alarmas y trending
- **Laboratorio:** Crear HMI para aplicación

### Capítulo 45: Redundancia y Alta Disponibilidad
- Conceptos de redundancia
- Redundancia en PLCs
- Sincronización de CPU redundantes
- Failover automático
- Testing de redundancia
- Redundancia de comunicación
- Backup de configuración
- **Laboratorio:** Sistema redundante configurado

### Capítulo 46: Integración con ERP/MES
- Sistemas MES (Manufacturing Execution System)
- Trazabilidad de producción
- Recetas (recipes) y lotes
- Órdenes de producción
- Interfaces de datos
- XML y JSON en automación
- Cloud manufacturing
- **Caso práctico:** Integración MES-PLC-ERP

---

# 🟣 BLOQUE VI: APLICACIONES PROFESIONALES Y EXPERTO (Nivel Experto)
**Duración:** 50-60 horas | **Objetivo:** Desarrollar soluciones de clase mundial

## MÓDULO 11: SEGURIDAD FUNCIONAL Y CERTIFICACIÓN

### Capítulo 47: Normas de Seguridad Funcional
- IEC 61508: Seguridad funcional sistemas E/E/PE
- IEC 62061: Seguridad en maquinaria
- IEC 61131-2: Certificación PLC para seguridad
- Safety Integrity Level (SIL) 1-4
- Performance Level (PL) a-e
- Análisis de riesgos (FMEA, FTA)
- Documentación de seguridad
- **Estudio:** Análisis de SIL para sistema

### Capítulo 48: Implementación de Funciones de Seguridad
- Parada de emergencia certificada
- Función de supervisión de movimiento
- Detección de presencia
- Pulsadores de parada de emergencia
- Botones de enclavamiento de seguridad
- Válvulas de seguridad
- S7-1500F para funciones de seguridad
- **Laboratorio:** Implementar función de seguridad

### Capítulo 49: Certificación y Auditoría
- Proceso de certificación de máquinas
- Auditorías de seguridad
- Documentación técnica requerida
- Pruebas de funcionamiento
- CE marking (Directiva de máquinas)
- Responsabilidad legal del programador
- **Práctica:** Documentar máquina para certificación

### Capítulo 50: Ciberseguridad Industrial (OT)
- Amenazas en sistemas de automatización
- Protección contra malware
- Firewalls y segmentación
- Contraseñas y autenticación
- Actualizaciones de firmware
- Auditoría de seguridad
- NIST, IEC 62443
- **Ejercicio:** Auditoría de seguridad de sistema

---

## MÓDULO 12: CASOS INDUSTRIALES Y PROYECTOS COMPLEJOS

### Capítulo 51: Líneas de Producción Automatizadas
- Arquitectura de línea completa
- Integración de múltiples PLCs
- Coordinación maestro-esclavo
- Tracking de productos
- Control de calidad integrado
- Estadísticas y OEE (Overall Equipment Effectiveness)
- Diagnóstico de problemas
- **Proyecto:** Diseñar línea de 4 estaciones

### Capítulo 52: Sistemas de Procesamiento Continuo
- Reactores químicos
- Destilación
- Fermentación
- Tratamiento de agua
- Calderas de vapor
- Control de temperatura avanzado
- Seguridad en procesos exotérmicos
- **Caso real:** Planta química con control PID

### Capítulo 53: Sistemas de Manejo de Materiales
- Transportadores
- Grúas y polipastos
- Sistemas de almacenamiento
- Automatización de almacenes (AS/RS)
- Coordinación de múltiples equipos
- Seguridad en espacios cerrados
- **Proyecto:** Automatizar almacén pequeño

### Capítulo 54: Integración de Robótica
- Lenguaje RAPID vs SCL
- Comunicación con robots ABB/KUKA/Fanuc
- Sincronización PLC-robot
- Visión artificial integrada
- Cobots (robots colaborativos)
- Seguridad en espacios compartidos
- **Laboratorio:** Comunicación PLC-robot

### Capítulo 55: Máquinas Especiales y Custom
- Máquinas de impresión
- Máquinas de etiquetado
- Máquinas de corte
- Máquinas de embalaje
- Diseño modular
- Scalabilidad de soluciones
- **Proyecto:** Diseñar máquina especial

### Capítulo 56: Internet Industrial de las Cosas (IIoT)
- Edge Computing en automatización
- Conectividad 5G/4G
- Telemetría de máquinas
- Predictive Maintenance
- Machine Learning en PLCs
- Análisis de datos industrial
- Casos de uso IIoT
- **Proyecto:** Sistema IIoT simple

---

## MÓDULO 13: TROUBLESHOOTING, OPTIMIZACIÓN Y OPERACIÓN

### Capítulo 57: Diagnóstico y Depuración Avanzada
- Herramientas de debug en TIA Portal
- Breakpoints y watch lists
- Profiling de código
- Memory leak detection
- Análisis de rendimiento
- Herramientas de terceros
- Logging estructurado
- **Laboratorio:** Depurar programa con errores

### Capítulo 58: Optimización de Código
- Complejidad temporal vs espacial
- Algoritmos eficientes
- Gestión de memoria en PLCs
- Cycles time optimization
- Paralelización de procesos
- Best practices de codificación
- **Ejercicios:** Optimizar código existente

### Capítulo 59: Mantenimiento Preventivo y Predictivo
- Programas de mantenimiento
- Histórico de máquinas
- Predicción de fallos
- Sensores de diagnostico
- Vibración y temperatura de motor
- Análisis de tendencias
- **Proyecto:** Programa de mantenimiento

### Capítulo 60: Operación y Formación de Personal
- Interfaces de operador
- Manual de operación
- Señales y alarmas
- Procedimientos de inicio/parada
- Respuesta ante emergencias
- Formación de operadores
- Documentación técnica
- **Práctica:** Crear manual de operación

---

## MÓDULO 14: TEMAS AVANZADOS Y ESPECIALIZACIÓN

### Capítulo 61: Visión Artificial en Automatización
- Cámaras industriales
- Procesamiento de imagen básico
- Reconocimiento de objetos
- Control de calidad por visión
- Comunicación PLC-cámara
- Integración en línea
- Casos de uso reales
- **Laboratorio:** Sistema de inspección por visión

### Capítulo 62: Comunicación Inalámbrica Industrial
- WiFi industrial
- 5G/LTE en planta
- Bluetooth industrial
- Seguridad inalámbrica
- Redundancia de cobertura
- Casos de uso
- **Estudio:** Evaluar inalámbrico vs cableado

### Capítulo 63: Migración a Industria 4.0
- Conceptos de Industria 4.0
- Transformación digital
- Cloud manufacturing
- Digital twins
- Big data en manufactura
- Transición gradual
- ROI de Industria 4.0
- **Análisis:** Roadmap de transformación

### Capítulo 64: Emprendimiento y Consultoría
- Ser consultor de automatización
- Business model de proyectos
- Presupuestos y estimación
- Gestión de proyectos
- Cliente vs alcance
- Formación profesional
- **Caso:** Proyecto de consultoría simulado

---

## MÓDULO 15: CERTIFICACIÓN Y ESPECIALIZACIÓN FINAL

### Capítulo 65: Preparación para Certificación Oficial Siemens
- Exámenes disponibles
- Contenidos de evaluación
- Prácticas de laboratorio
- Simulación de examen
- **Taller:** Preparación intensiva

### Capítulo 66: Portfolio de Proyectos
- Selección de mejores proyectos
- Documentación profesional
- Presentación de casos
- GitHub/repositorios técnicos
- **Tarea:** Compilar portfolio

### Capítulo 67: Especialización Elegida (Opción A, B o C)

**Opción A: Experto en Procesos Continuos**
- Control avanzado de procesos
- Técnicas de optimización
- Diseño experimental DOE
- Casos en industria química/farmacéutica

**Opción B: Experto en Manufactura Discreta**
- Planificación de producción
- OEE y lean manufacturing
- Líneas de alta velocidad
- Casos automotriz/electrónica

**Opción C: Experto en Integración de Sistemas**
- Arquitectura empresarial
- Integración ERP-MES-PLC
- Proyectos de transformación digital
- Casos de grandes corporaciones

### Capítulo 68: Tendencias y Futuro de la Automatización
- Evolución tecnológica
- Edge AI en PLCs
- 5G y conectividad
- Sustentabilidad industrial
- Automatización verde
- Futuro de la programación PLC
- **Reflexión:** Carrera a largo plazo

---

# 📊 RESUMEN ESTRUCTURAL

## Por Nivel de Formación:

```
┌─────────────────────────────────────────────────────────┐
│ NIVEL PRINCIPIANTE (Capítulos 1-16)                    │
│ Duración: 75-95 horas                                   │
│ • Electricidad aplicada                                 │
│ • Lógica y conceptos fundamentales                      │
│ • Entorno TIA Portal y hardware Siemens                 │
│ Competencia: Entender sistemas de automatización       │
└─────────────────────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────────────────────┐
│ NIVEL INTERMEDIO (Capítulos 17-42)                     │
│ Duración: 95-125 horas                                  │
│ • Programación SCL avanzada                             │
│ • E/S digital y analógica                               │
│ • Control PID                                           │
│ • Comunicación industrial                               │
│ Competencia: Desarrollar aplicaciones moderadamente    │
│ complejas con comunicación en red                       │
└─────────────────────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────────────────────┐
│ NIVEL AVANZADO (Capítulos 43-60)                       │
│ Duración: 90-110 horas                                  │
│ • Arquitectura de sistemas                              │
│ • Seguridad funcional                                   │
│ • Casos industriales complejos                          │
│ • Troubleshooting y optimización                        │
│ Competencia: Ingeniero sénior capaz de diseñar         │
│ sistemas completos de automatización                    │
└─────────────────────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────────────────────┐
│ NIVEL EXPERTO (Capítulos 61-68)                        │
│ Duración: 50-80 horas                                   │
│ • Especialización elegida                               │
│ • Visión artificial                                     │
│ • Industria 4.0                                         │
│ • Consultoría                                           │
│ • Tendencias futuras                                    │
│ Competencia: Senior leader capaz de innovar y          │
│ liderar transformación digital en industria             │
└─────────────────────────────────────────────────────────┘
```

## Por Horas Totales:

```
Bloque I - Fundamentos:          40-50 horas
Bloque II - TIA Portal:          35-45 horas
Bloque III - SCL Intermedio:     50-60 horas
Bloque IV - Analógica/Control:   45-55 horas
Bloque V - Comunicación/Arq:     40-50 horas
Bloque VI - Profesional/Experto: 100-140 horas
────────────────────────────────────────
TOTAL:                           310-400 horas

Equivalencia:
→ 6-8 meses tiempo completo (40 horas/semana)
→ 12-16 meses tiempo parcial (20 horas/semana)
→ 18-24 meses tiempo muy parcial (10 horas/semana)
```

## Contenido por Tipo:

```
68 Capítulos
├── 68 Introducciones
├── 68 Secciones de objetivos
├── 136 Subsecciones de contenido técnico
├── ~300 Diagramas/esquemas ASCII
├── ~150 Tablas comparativas
├── ~200 Ejemplos de código (SCL/KOP)
├── ~50 Casos industriales reales
├── ~150 Ejercicios prácticos
├── ~150 Soluciones completamente desarrolladas
├── ~200 Errores comunes documentados
├── ~100 Buenas prácticas explicadas
├── 68 Resúmenes de capítulo
└── ~300 Preguntas tipo entrevista
```

---

# 🎯 FLUJO DE APRENDIZAJE

**Recomendación pedagógica:**

1. **Fase 1 (Semanas 1-4):** Completar Bloque I (Fundamentos)
   - Revisar conocimientos previos
   - Electricidad aplicada

2. **Fase 2 (Semanas 5-9):** Completar Bloque II (TIA Portal básico)
   - Instalación del software
   - Primeros programas en KOP

3. **Fase 3 (Semanas 10-16):** Completar Bloque III (SCL intermedio)
   - Transición a SCL
   - Ejercicios progresivos

4. **Fase 4 (Semanas 17-24):** Completar Bloque IV (Analógica/Control)
   - Control PID
   - Laboratorios con hardware real

5. **Fase 5 (Semanas 25-32):** Completar Bloque V (Comunicación/Arquitectura)
   - Redes industriales
   - Integración de sistemas

6. **Fase 6 (Semanas 33-40+):** Completar Bloque VI (Profesional/Experto)
   - Casos reales
   - Especialización elegida

---

# ✅ CRITERIOS DE COMPETENCIA FINAL

Al completar el curso, el egresado será capaz de:

✓ Diseñar y programar sistemas de automatización completos en TIA Portal
✓ Dominar lenguaje SCL a nivel profesional
✓ Implementar control analógico y PID
✓ Configurar comunicación industrial (PROFINET, Modbus, OPC-UA)
✓ Diseñar arquitectura de sistemas distribuidos
✓ Implementar funciones de seguridad certificadas
✓ Realizar troubleshooting y optimización
✓ Leadear proyectos de automatización
✓ Cumplir normas internacionales (IEC 61131-3, IEC 61508)
✓ Integrar sistemas con SCADA, HMI y ERP
✓ Capacitar y supervisar a otros programadores

---

# 📚 RECURSOS COMPLEMENTARIOS

Dentro del curso se incluyen:

- **Anexo A:** Referencia rápida SCL
- **Anexo B:** Tablas de tipos de datos Siemens
- **Anexo C:** Codes de error comunes
- **Anexo D:** Normas y estándares aplicables
- **Anexo E:** Templates y ejemplos reusables
- **Anexo F:** Glosario de términos técnicos
- **Anexo G:** URLs y referencias externas
- **Anexo H:** Proveedores y fabricantes recomendados

---

**Este índice completo constituye un programa de formación integral, equivalente a un diploma profesional en Automatización Industrial con especialización en Siemens TIA Portal.**

