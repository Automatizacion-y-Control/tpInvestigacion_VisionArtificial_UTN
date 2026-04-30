4. Modelo funcional AIoT
4.1 Introducción al modelo funcional

El sistema propuesto se estructura mediante un modelo funcional compuesto por siete fases operacionales distribuidas.

Estas fases representan funciones fundamentales necesarias para transformar datos físicos provenientes del entorno en información operacional utilizable.

Las siete fases no pertenecen exclusivamente a una única capa del sistema.

Por el contrario:

cada área telecomputacional
implementa las siete fases
según su contexto operacional

Esto implica que:

Edge implementa las siete fases a nivel local;
Fog implementa nuevamente las siete fases a nivel operacional distribuido;
Cloud implementa nuevamente las siete fases a nivel estratégico y global.
4.2 Las siete fases funcionales
Fase	Función
Percepción	adquisición del dato desde el entorno
Preprocesamiento	adaptación inicial del dato
Comunicación	transferencia interna del dato
Almacenamiento	persistencia temporal o permanente
Procesamiento	transformación computacional
Análisis	interpretación contextual
Presentación	exposición operacional de información
4.3 Principio de distribución funcional

El modelo funcional distribuye capacidades según:

proximidad al dato;
capacidad computacional;
latencia requerida;
criticidad operacional;
contexto telecomputacional.
4.4 Aplicación del modelo funcional en EDGE
EDGE
4.4.1 Percepción en Edge
Función

Captura directa del entorno físico.

Recursos típicos
sensores CMOS;
cámaras inteligentes;
módulos visuales;
sensores auxiliares.
Resultado
frame bruto
imagen capturada
video local
4.4.2 Preprocesamiento en Edge
Función

Reducir complejidad del dato antes de transmitir o inferir.

Operaciones típicas
resize;
crop;
compresión;
normalización;
reducción de ruido;
extracción ROI.
Objetivo
reducir costo computacional
y tráfico de red
4.4.3 Comunicación en Edge
Función

Movimiento interno del dato dentro del nodo Edge.

Ejemplos
Comunicación interna	Aplicación
I2C	configuración sensores
SPI	transferencia periféricos
DMA	movimiento buffers
RTOS queues	sincronización tareas
memoria compartida	intercambio local
Observación

Esta comunicación corresponde al funcionamiento interno del nodo Edge y no al transporte Edge → Fog.

4.4.4 Almacenamiento en Edge
Función

Persistencia temporal local.

Recursos
RAM;
PSRAM;
Flash;
SD card;
buffers circulares.
Uso típico
cache temporal;
buffering;
snapshots temporales.
4.4.5 Procesamiento en Edge
Función

Procesamiento inmediato cercano al dato.

Operaciones
detección primaria;
motion detection;
inferencia local;
extracción básica.
Tecnologías posibles
TinyML;
TensorFlow Lite Micro;
modelos cuantizados;
inferencia acelerada.
4.4.6 Análisis en Edge
Función

Interpretación primaria del entorno.

Resultado típico
{
  "evento": "movimiento_detectado"
}

o

{
  "evento": "vehiculo_detectado"
}
4.4.7 Presentación en Edge
Función

Retroalimentación operacional mínima local.

Recursos
LEDs;
displays;
consola serial;
logs locales.
4.5 Aplicación del modelo funcional en FOG
FOG
4.5.1 Percepción en Fog
Función

Recepción contextualizada de eventos y datos provenientes de múltiples nodos Edge.

Fuentes
eventos MQTT;
snapshots;
streams;
telemetría.
Resultado
visión operacional agregada
4.5.2 Preprocesamiento en Fog
Función

Preparar datos provenientes de múltiples nodos para procesamiento operacional.

Operaciones
validación;
normalización;
sincronización temporal;
limpieza;
enriquecimiento semántico.
4.5.3 Comunicación en Fog
Función

Comunicación interna entre servicios y componentes Fog.

Ejemplos
Comunicación interna	Aplicación
TCP/IP local	microservicios
Redis pub/sub	eventos internos
Unix sockets	IPC local
WebSocket	dashboards
colas internas	procesamiento desacoplado
Observación

No corresponde aún al transporte Fog → Cloud.

4.5.4 Almacenamiento en Fog
Función

Persistencia operacional local.

Recursos
SQLite;
PostgreSQL local;
Redis;
SSD local;
bases temporales.
Objetivos
buffering;
resiliencia;
operación offline;
evidencia temporal.
4.5.5 Procesamiento en Fog
Función

Procesamiento operacional distribuido.

Operaciones
correlación;
OCR;
tracking;
inferencia avanzada;
validación operacional.
Tecnologías
OpenCV;
YOLO;
ONNX Runtime;
TensorRT.
4.5.6 Análisis en Fog
Función

Interpretación operacional contextual.

Ejemplo
{
  "evento": "vehiculo_contramano"
}

o

{
  "evento": "patente_no_autorizada"
}
4.5.7 Presentación en Fog
Función

Supervisión operacional local.

Recursos
dashboards Qt;
dashboards web locales;
CLI administrativa;
paneles técnicos.
4.6 Aplicación del modelo funcional en CLOUD
CLOUD
4.6.1 Percepción en Cloud
Función

Recepción global de información operacional proveniente de múltiples FOGs.

Fuentes
eventos;
imágenes;
métricas;
logs;
streams remotos.
4.6.2 Preprocesamiento en Cloud
Función

Preparar información para procesamiento masivo.

Operaciones
indexación;
limpieza datasets;
etiquetado;
deduplicación.
4.6.3 Comunicación en Cloud
Función

Comunicación interna entre servicios cloud.

Ejemplos
Comunicación interna	Aplicación
TCP/IP	microservicios
gRPC	servicios IA
Kafka	buses eventos
APIs REST	integración
colas distribuidas	sincronización
4.6.4 Almacenamiento en Cloud
Función

Persistencia global distribuida.

Recursos
object storage;
data lakes;
bases SQL;
bases NoSQL;
almacenamiento histórico.
4.6.5 Procesamiento en Cloud
Función

Procesamiento estratégico intensivo.

Operaciones
entrenamiento IA;
distillation;
analítica histórica;
procesamiento masivo;
optimización modelos.
4.6.6 Análisis en Cloud
Función

Interpretación estratégica global.

Resultado
tendencias;
patrones;
métricas;
predicciones;
comportamiento operacional histórico.
4.6.7 Presentación en Cloud
Función

Visualización y gestión global del sistema.

Recursos
dashboards web;
reportes;
copilotos IA;
supervisión multi-sitio;
administración centralizada.
4.7 Relación transversal entre capas

Aunque las fases funcionales existen en todas las áreas telecomputacionales, su implementación cambia según contexto y responsabilidad operacional.

Ejemplo conceptual
Fase	Edge	Fog	Cloud
percepción	captura física	recepción eventos	recepción global
procesamiento	inferencia local	correlación	analítica masiva
presentación	LEDs/logs	dashboard local	dashboard global
4.8 Distribución funcional del sistema

El modelo funcional permite distribuir inteligencia y procesamiento según necesidad operacional.

Edge
respuesta rápida
baja latencia
proximidad física
Fog
coordinación operacional
resiliencia local
gestión distribuida
Cloud
memoria histórica
analítica global
entrenamiento IA
4.9 Conclusión del modelo funcional

El modelo funcional AIoT permite estructurar el sistema como una infraestructura distribuida donde cada área telecomputacional implementa capacidades completas adaptadas a su contexto operacional.

Esto evita centralización excesiva y permite:

escalabilidad;
resiliencia;
desacoplamiento;
distribución inteligente de procesamiento;
optimización del flujo operacional del dato visual.