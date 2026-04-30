6. Arquitectura de comunicación y transporte del dato
6.1 Introducción

Uno de los aspectos centrales del sistema propuesto consiste en definir correctamente cómo circula el dato visual dentro de la arquitectura distribuida.

El diseño de comunicación no puede tratarse como un único problema homogéneo.

Existen dos niveles distintos de comunicación:

Tipo	Función
comunicación interna	movimiento del dato dentro de una misma área telecomputacional
comunicación inter-área	transporte del dato entre Edge, Fog y Cloud

Aunque en ciertos casos puedan utilizarse protocolos similares, ambos niveles poseen:

propósitos distintos;
contextos distintos;
restricciones distintas;
requisitos operacionales distintos.
6.2 Principio general de comunicación

La arquitectura adopta un modelo desacoplado orientado a eventos.

El sistema evita transportar continuamente información visual completa cuando no resulta necesario.

La estrategia general consiste en:

evento liviano
↓
reacción operacional
↓
transferencia selectiva del dato visual
6.3 Clasificación del dato transportado

El sistema trabaja con múltiples tipos de datos.

Tipo dato	Característica
evento semántico	liviano
snapshot	pesado puntual
stream visual	pesado continuo
telemetría	liviana periódica
evidencia histórica	persistente
comandos	control operacional

Cada tipo requiere protocolos adecuados a su finalidad.

6.4 Comunicación interna en EDGE
6.4.1 Objetivo

Permitir circulación eficiente del dato dentro del nodo Edge.

6.4.2 Comunicación sensorial
Comunicación interna	Aplicación
I2C	configuración sensores
SPI	periféricos rápidos
UART	debugging / módulos externos
GPIO	señalización
PWM	control auxiliar
6.4.3 Comunicación visual
Tecnología	Aplicación
DVP	cámaras paralelas
MIPI CSI	cámaras alta velocidad
USB Video	cámaras externas
6.4.4 Movimiento interno de frames
Tecnología	Aplicación
DMA	transferencia eficiente
memoria compartida	buffers
colas RTOS	sincronización tareas
6.4.5 Comunicación entre módulos Edge

Ejemplo conceptual:

captura
↓
preprocesamiento
↓
inferencia
↓
generación evento

La circulación ocurre internamente mediante mecanismos locales del sistema operativo o RTOS.

6.5 Comunicación inter-área EDGE → FOG
6.5.1 Objetivo

Transportar únicamente información necesaria hacia capas superiores.

6.5.2 Eventos semánticos
Finalidad

Notificar ocurrencias operacionales.

Características
bajo tamaño;
alta semántica;
transmisión inmediata.
Protocolos óptimos
Protocolo	Finalidad
MQTT	eventos desacoplados
MQTT over TLS	eventos seguros
NATS	eventos distribuidos
Ejemplo
{
  "evento": "vehiculo_detectado",
  "zona": "carril_2"
}
6.5.3 Transferencia de snapshots
Finalidad

Enviar imágenes puntuales bajo demanda.

Características
dato pesado;
transmisión selectiva;
no continua.
Protocolos óptimos
Protocolo	Finalidad
HTTP/HTTPS	snapshots
gRPC	transferencia optimizada
TCP socket	canal dedicado
Flujo típico
MQTT trigger
↓
Fog solicita imagen
↓
HTTP snapshot
6.5.4 Streaming visual
Finalidad

Visualización continua o análisis persistente.

Características
transmisión continua;
alto consumo relativo;
requiere optimización.
Protocolos óptimos
Protocolo	Finalidad
RTSP	streaming CCTV
RTP	multimedia tiempo real
MJPEG	streaming simple
WebRTC	baja latencia interactiva
6.5.5 Diferenciación funcional de protocolos
Protocolo	Función
MQTT	“ocurrió algo”
HTTP	“aquí está el dato”
RTSP	“observá continuamente”
WebRTC	“observá interactuando en tiempo real”
6.6 Comunicación interna en FOG
6.6.1 Objetivo

Coordinar servicios operacionales distribuidos dentro del nodo Fog.

6.6.2 Comunicación entre servicios
Tecnología	Aplicación
TCP/IP local	servicios distribuidos
Unix sockets	IPC eficiente
Redis pub/sub	eventos internos
colas internas	desacoplamiento
6.6.3 Comunicación dashboards
Tecnología	Aplicación
WebSocket	dashboards tiempo real
SSE	eventos live
HTTP local	APIs internas
6.6.4 Comunicación procesamiento IA
Tecnología	Aplicación
gRPC	inferencia distribuida
colas internas	pipelines IA
shared memory	intercambio rápido
6.7 Comunicación inter-área FOG → CLOUD
6.7.1 Objetivo

Sincronizar información operacional global.

6.7.2 Eventos operacionales
Protocolos óptimos
Protocolo	Finalidad
MQTT over TLS	sincronización eventos
AMQP	colas empresariales
Kafka	eventos masivos
6.7.3 Evidencia visual
Finalidad

Persistencia histórica.

Protocolos óptimos
Protocolo	Finalidad
HTTPS	upload seguro
S3 API	object storage
gRPC	transferencia eficiente
6.7.4 Streaming remoto
Protocolo	Finalidad
WebRTC	acceso remoto tiempo real
HLS	distribución escalable
RTSP gateway	retransmisión
6.7.5 Telemetría
Protocolo	Finalidad
MQTT	métricas
HTTPS	reporting
WebSocket	dashboards live
6.8 Comunicación interna en CLOUD
6.8.1 Objetivo

Coordinar servicios distribuidos cloud.

6.8.2 Comunicación microservicios
Tecnología	Aplicación
TCP/IP	infraestructura base
gRPC	microservicios
REST APIs	integración
GraphQL	consultas agregadas
6.8.3 Comunicación orientada a eventos
Tecnología	Aplicación
Kafka	buses masivos
RabbitMQ	colas
NATS	eventos rápidos
6.8.4 Comunicación almacenamiento
Tecnología	Aplicación
S3 API	object storage
SQL protocol	bases relacionales
NoSQL APIs	documentos
6.9 Transporte selectivo del dato visual

Uno de los principios centrales del sistema consiste en evitar transmisión continua innecesaria.

Estrategia
Tipo dato	Estrategia
video continuo	solo bajo necesidad
snapshots	selectivos
eventos	prioritarios
evidencia	persistente selectiva
Beneficios
menor tráfico;
menor latencia;
mejor escalabilidad;
reducción costos red;
resiliencia operacional.
6.10 Arquitectura desacoplada de comunicación

La arquitectura evita dependencias rígidas entre productores y consumidores.

Ejemplo:

Edge publica evento
↓
Fog consume
↓
Cloud replica
↓
Dashboard escucha

Los componentes permanecen desacoplados.

6.11 Seguridad de comunicación

La comunicación debe protegerse transversalmente.

Mecanismos
Mecanismo	Aplicación
TLS	cifrado
mTLS	autenticación mutua
certificados X.509	identidad nodos
VPN	túneles seguros
WireGuard	acceso remoto seguro
6.12 Conclusión de arquitectura de comunicación

La arquitectura propuesta distribuye mecanismos de comunicación según:

tipo de dato;
criticidad;
latencia requerida;
volumen;
contexto operacional.

Esto permite optimizar simultáneamente:

rendimiento;
resiliencia;
escalabilidad;
desacoplamiento;
eficiencia operacional del sistema AIoT distribuido.