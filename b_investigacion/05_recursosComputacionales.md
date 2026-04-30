5. Recursos computacionales por capa
5.1 Introducción

La arquitectura propuesta requiere distribuir capacidades computacionales entre distintas áreas telecomputacionales.

Cada capa posee restricciones y objetivos diferentes:

Área	Prioridad dominante
Edge	proximidad física y baja latencia
Fog	coordinación operacional
Cloud	escalabilidad y procesamiento intensivo

Por esta razón, la selección computacional no puede depender de una única arquitectura específica.

El sistema debe mantener un enfoque agnóstico respecto a:

fabricantes;
arquitecturas CPU;
sistemas operativos;
aceleradores IA;
plataformas hardware.
5.2 Recursos computacionales en EDGE
EDGE
5.2.1 Objetivo computacional del Edge

La capa Edge se ubica cerca del origen físico del dato.

Sus objetivos principales son:

captura inmediata;
inferencia local;
reducción de latencia;
reducción de tráfico;
autonomía operacional parcial.

Esto obliga a trabajar frecuentemente bajo restricciones de:

energía;
memoria;
capacidad computacional;
disipación térmica.
5.2.2 Familias microcontroladas

Los nodos Edge pueden implementarse utilizando múltiples familias de microcontroladores.

Microcontroladores 8-bit
Familia	Empresa
AVR	Microchip Technology
PIC 8-bit	Microchip Technology
STM8	STMicroelectronics
MSP430	Texas Instruments

Uso típico:

control básico;
adquisición simple;
soporte periférico.
Microcontroladores 32-bit
Familia	Arquitectura	Empresa
STM32	ARM Cortex-M	STMicroelectronics
LPC / Kinetis / i.MX RT	ARM Cortex-M	NXP Semiconductors
RA / RX	ARM / RX	Renesas Electronics
SAM / PIC32	ARM / MIPS	Microchip Technology
nRF52 / nRF53 / nRF54	ARM Cortex-M	Nordic Semiconductor
ESP32 family	Xtensa / RISC-V	Espressif Systems

Uso típico:

inferencia liviana;
conectividad;
gateways pequeños;
procesamiento embebido.
5.2.3 Edge AI y visión embebida

Existen plataformas específicas orientadas a visión artificial y TinyML.

Plataforma	Empresa / organización
ESP32-CAM	Espressif Systems
OpenMV	OpenMV
Kendryte K210	Canaan Inc.
Nicla Vision	Arduino
WiseEye	Himax Technologies
Spresense	Sony
5.2.4 SBCs Edge

Cuando la inferencia requiere mayor capacidad computacional, pueden utilizarse SBCs.

Plataforma	Empresa
Raspberry Pi	Raspberry Pi
BeagleBone	BeagleBoard.org
Orange Pi	Shenzhen Xunlong Software
Radxa	Radxa
Jetson Nano / Orin	NVIDIA
5.2.5 Sistemas operativos y RTOS en Edge

La elección depende del poder computacional disponible.

Bare-metal

Uso típico:

ultra bajo consumo;
control determinístico;
dispositivos simples.
RTOS
Sistema	Organización
FreeRTOS	Amazon
Zephyr	Linux Foundation
ThreadX	Microsoft
Linux embebido
Sistema	Organización
Ubuntu Core	Canonical
Yocto	Yocto Project
Debian Embedded	Debian Project
balenaOS	Balena
5.2.6 Aceleradores IA Edge
Tecnología	Empresa
CUDA Edge	NVIDIA
Coral TPU	Google
Ethos-U	Arm Holdings
Qualcomm AI Edge	Qualcomm
5.2.7 Restricciones típicas del Edge
Restricción	Impacto
memoria limitada	modelos pequeños
consumo energético	optimización inferencia
temperatura	throttling
red inestable	autonomía local
almacenamiento limitado	buffering reducido
5.3 Recursos computacionales en FOG
FOG
5.3.1 Objetivo computacional del Fog

La capa Fog constituye el núcleo operacional distribuido.

Debe permitir:

correlación;
inferencia avanzada;
buffering;
coordinación;
dashboards locales;
resiliencia operacional.
5.3.2 Plataformas Fog
Plataforma	Empresa
Raspberry Pi 4/5	Raspberry Pi
Intel NUC	Intel
AMD Embedded	Advanced Micro Devices
Jetson Xavier / Orin	NVIDIA
5.3.3 Gateways industriales
Plataforma	Empresa
PLCnext	Phoenix Contact
SIMATIC Industrial Edge	Siemens
Beckhoff IPC	Beckhoff Automation
WAGO Edge	WAGO
5.3.4 Sistemas operativos Fog
Sistema	Organización
Ubuntu Core	Canonical
Ubuntu Server	Canonical
Debian	Debian Project
Yocto Linux	Yocto Project
5.3.5 Capacidades Fog
Función	Recurso necesario
YOLO	GPU / CPU vectorial
OCR	CPU optimizada
buffering	almacenamiento local
dashboards	rendering local
broker MQTT	memoria persistente
5.3.6 Persistencia local Fog
Tecnología	Uso
SQLite	persistencia liviana
PostgreSQL	eventos estructurados
Redis	cache operacional
InfluxDB	series temporales
5.4 Recursos computacionales en CLOUD
CLOUD
5.4.1 Objetivo computacional del Cloud

La capa Cloud concentra capacidades globales y estratégicas.

Sus funciones incluyen:

almacenamiento masivo;
entrenamiento IA;
analítica;
supervisión multi-sitio;
administración global.
5.4.2 Infraestructura cloud
Plataforma	Empresa
AWS	Amazon Web Services
Azure	Microsoft
Google Cloud	Google
Oracle Cloud	Oracle Corporation
5.4.3 GPU cloud
Plataforma	Empresa
RunPod	RunPod
Lambda Labs	Lambda
Paperspace	DigitalOcean
5.4.4 Orquestación
Tecnología	Organización
Docker	Docker
Kubernetes	Cloud Native Computing Foundation
Terraform	HashiCorp
5.4.5 Almacenamiento distribuido
Tecnología	Uso
S3 object storage	evidencia visual
PostgreSQL	datos estructurados
MongoDB	documentos
Data lakes	analítica histórica
5.4.6 Procesamiento IA cloud
Función	Recursos
entrenamiento	GPU clusters
distillation	procesamiento intensivo
MLOps	pipelines automatizados
versionado modelos	registries IA
5.5 Relación entre poder computacional y arquitectura

El poder computacional disponible condiciona directamente:

arquitectura posible;
sistema operativo viable;
modelos IA desplegables;
protocolos eficientes;
autonomía operacional.
5.6 Principio de agnosticismo arquitectónico

La plataforma propuesta evita dependencia rígida respecto a:

fabricante;
CPU específica;
sistema operativo;
acelerador IA;
infraestructura cloud.

Esto permite evolución tecnológica futura sin rediseñar completamente el sistema.
