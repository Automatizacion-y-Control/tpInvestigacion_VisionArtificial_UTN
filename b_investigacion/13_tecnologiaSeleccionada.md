13. Tecnologías seleccionadas
13.1 Introducción

La arquitectura propuesta fue diseñada bajo un principio de agnosticismo tecnológico.

Esto implica que la plataforma no depende estrictamente de:

un fabricante específico;
una arquitectura computacional única;
un protocolo propietario;
un framework IA determinado;
un proveedor cloud particular.

Sin embargo, para validar operacionalmente el sistema y construir una implementación funcional madura, resulta necesario definir un conjunto inicial de tecnologías de referencia.

Las tecnologías seleccionadas deben satisfacer los siguientes criterios:

modularidad;
escalabilidad;
interoperabilidad;
soporte comunitario e industrial;
capacidad AIoT distribuida;
portabilidad arquitectónica.
13.2 Tecnologías seleccionadas para EDGE
EDGE
13.2.1 Objetivo tecnológico del Edge

La capa Edge requiere tecnologías capaces de:

capturar percepción visual;
ejecutar inferencia cercana al dato;
generar eventos semánticos;
operar bajo recursos limitados.
13.2.2 Plataformas hardware seleccionadas
Microcontroladores y nodos visuales
Plataforma	Función
ESP32-CAM	captura visual liviana
STM32 + cámara	procesamiento embebido
Raspberry Pi Zero / CM	Edge Linux
Jetson Nano	inferencia avanzada
Fabricantes involucrados
Empresa
Espressif Systems
STMicroelectronics
Raspberry Pi
NVIDIA
13.2.3 Sistemas operativos Edge
RTOS seleccionados
Sistema	Uso
FreeRTOS	Edge embebido
Zephyr	nodos IoT avanzados
Linux embebido
Sistema	Uso
Ubuntu Core	Edge Linux industrial
Debian Embedded	Edge flexible
13.2.4 Frameworks IA Edge
Tecnología	Uso
TensorFlow Lite Micro	TinyML
Edge Impulse	modelos Edge
OpenCV	visión básica
YOLO nano	detección ligera
13.2.5 Protocolos Edge seleccionados
Protocolo	Función
MQTT	eventos
HTTP/HTTPS	snapshots
RTSP	streaming
WebRTC	streaming interactivo
13.3 Tecnologías seleccionadas para FOG
FOG
13.3.1 Objetivo tecnológico del Fog

El Fog constituye el núcleo operacional local distribuido.

Debe permitir:

correlación;
inferencia avanzada;
dashboards locales;
buffering;
resiliencia operacional.
13.3.2 Hardware Fog seleccionado
Plataforma	Función
Raspberry Pi 5	Fog liviano
Intel NUC	Fog intermedio
Jetson Orin	inferencia acelerada
IPC industrial	despliegue industrial
13.3.3 Sistemas operativos Fog
Sistema	Función
Ubuntu Core	despliegue AIoT
Ubuntu Server	operación general
Debian	estabilidad
13.3.4 Frameworks IA Fog
Tecnología	Función
OpenCV	procesamiento visual
YOLO	detección objetos
ONNX Runtime	inferencia portable
TensorRT	aceleración NVIDIA
EasyOCR	OCR
13.3.5 Middleware Fog
Tecnología	Función
Mosquitto	broker MQTT
Redis	eventos internos
PostgreSQL	persistencia
InfluxDB	métricas
13.3.6 Dashboards Fog
Tecnologías posibles
Tecnología	Función
Qt C++	dashboard nativo
PySide / PyQt	dashboard Python
React web dashboard	interfaz web local
13.3.7 CLI administrativa
Tecnologías
Tecnología	Función
Python CLI	administración
Bash scripts	automatización
SSH	mantenimiento remoto
13.4 Tecnologías seleccionadas para CLOUD
CLOUD
13.4.1 Objetivo tecnológico del Cloud

El Cloud debe soportar:

escalabilidad;
almacenamiento masivo;
entrenamiento IA;
supervisión global;
administración distribuida.
13.4.2 Infraestructura cloud seleccionada
Plataforma	Función
AWS	infraestructura global
Google Cloud	IA y analítica
Azure	integración empresarial
RunPod	entrenamiento GPU
13.4.3 Orquestación
Tecnología	Función
Docker	contenedores
Kubernetes	orquestación
Terraform	infraestructura código
13.4.4 Bases de datos Cloud
Tecnología	Función
PostgreSQL	datos estructurados
MongoDB	eventos flexibles
InfluxDB	métricas
Object Storage S3	evidencia visual
13.4.5 IA Cloud
Tecnología	Función
PyTorch	entrenamiento
TensorFlow	modelos IA
MLflow	tracking modelos
Weights & Biases	experimentación
13.4.6 APIs y servicios
Tecnología	Función
FastAPI	APIs backend
gRPC	servicios eficientes
WebSocket	dashboards tiempo real
13.5 Tecnologías de comunicación seleccionadas
13.5.1 MQTT
Función

Eventos semánticos y telemetría.

13.5.2 HTTP/HTTPS
Función

Transferencia puntual de imágenes y APIs.

13.5.3 RTSP
Función

Streaming continuo CCTV.

13.5.4 WebRTC
Función

Streaming remoto interactivo baja latencia.

13.5.5 WebSocket
Función

Dashboards tiempo real.

13.5.6 gRPC
Función

Comunicación eficiente entre servicios.

13.6 Tecnologías de seguridad seleccionadas
Tecnología	Función
TLS	cifrado
mTLS	autenticación mutua
WireGuard	VPN distribuida
certificados X.509	identidad nodos
13.7 Tecnologías multimedia seleccionadas
Tecnología	Función
FFmpeg	procesamiento multimedia
GStreamer	pipelines video
OpenCV	captura/procesamiento
13.8 Tecnologías observabilidad
Tecnología	Función
Prometheus	métricas
Grafana	dashboards métricas
Loki	logs
ELK Stack	análisis logs
13.9 Tecnologías DevOps
Tecnología	Función
Git	control versiones
GitHub Actions	CI/CD
Docker Compose	despliegues locales
13.10 Criterios de selección tecnológica

Las tecnologías fueron seleccionadas considerando:

soporte AIoT;
capacidad distribuida;
interoperabilidad;
portabilidad;
soporte industrial;
madurez tecnológica.
13.11 Compatibilidad multi-arquitectura

La plataforma busca mantener compatibilidad con:

ARM;
x86;
RISC-V;
Linux embebido;
RTOS;
cloud híbrido.
13.12 Riesgos tecnológicos
Riesgo	Impacto
dependencia proveedor	lock-in
incompatibilidades	integración
limitaciones Edge	inferencia limitada
cambios frameworks	mantenimiento
13.13 Estrategia de desacoplamiento tecnológico

La arquitectura intenta desacoplar:

hardware;
IA;
protocolos;
almacenamiento;
infraestructura.

Esto permite evolución futura del sistema.

13.14 Conclusión

Las tecnologías seleccionadas permiten construir una implementación funcional madura alineada con los principios arquitectónicos definidos previamente.

La combinación de tecnologías Edge, Fog y Cloud permite validar operacionalmente la plataforma AIoT distribuida de percepción visual manteniendo flexibilidad, escalabilidad y capacidad evolutiva.