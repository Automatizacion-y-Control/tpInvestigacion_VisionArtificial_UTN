7. Recorrido completo del dato visual
7.1 Introducción

El sistema propuesto transforma percepción visual distribuida en información operacional estructurada mediante un flujo funcional distribuido sobre arquitectura Edge–Fog–Cloud.

El dato visual no circula de manera uniforme a través del sistema.

Su recorrido depende de:

contexto operacional;
relevancia semántica;
necesidad de análisis;
requerimientos de latencia;
políticas de almacenamiento;
criticidad del evento.

El objetivo central consiste en optimizar el ciclo completo del dato visual desde su captura hasta su utilización operacional.

7.2 Principio general del recorrido del dato

La arquitectura evita transportar continuamente video crudo hacia capas superiores.

La estrategia general consiste en:

capturar localmente
↓
procesar cerca del origen
↓
extraer significado
↓
transportar eventos relevantes
↓
escalar información útil
7.3 Etapa 1 — Captura del dato visual en EDGE
7.3.1 Percepción física

El recorrido comienza en el nodo Edge mediante captura del entorno físico.

Fuentes posibles
cámaras RGB;
cámaras IR;
cámaras térmicas;
streams IP;
sensores visuales industriales.
Resultado inicial
frame bruto
imagen cruda
video local
7.3.2 Adquisición sensorial

La información visual es adquirida mediante buses internos.

Comunicación interna típica
Comunicación	Función
MIPI CSI	captura alta velocidad
DVP	cámaras paralelas
USB Video	cámaras externas
SPI/I2C	configuración sensores
7.4 Etapa 2 — Preprocesamiento local en EDGE
7.4.1 Objetivo

Reducir complejidad antes del procesamiento profundo o transmisión.

7.4.2 Operaciones típicas
Operación	Objetivo
resize	reducir costo computacional
crop	aislar región interés
grayscale	simplificar procesamiento
compresión	reducir tamaño
filtrado	mejorar calidad
normalización	estabilizar inferencia
7.4.3 Resultado

El dato visual deja de ser únicamente imagen cruda y comienza a convertirse en dato operacional potencial.

7.5 Etapa 3 — Procesamiento e inferencia en EDGE
7.5.1 Inferencia local

El Edge ejecuta inferencia cercana al dato.

Ejemplos
detección de vehículo;
detección de movimiento;
detección de presencia;
clasificación básica;
detección ROI;
extracción preliminar.
7.5.2 Objetivo

Reducir necesidad de transmitir información innecesaria.

7.5.3 Resultado semántico inicial

Ejemplo:

{
  "evento": "vehiculo_detectado"
}
7.6 Etapa 4 — Generación del evento semántico
7.6.1 Transformación operacional

La percepción visual se transforma en evento estructurado.

Ejemplo
{
  "evento": "patente_detectada",
  "valor": "AB123CD",
  "zona": "carril_1",
  "timestamp": "2026-04-26T19:15:00"
}
7.6.2 Beneficio

El sistema comienza a operar sobre significado y no únicamente sobre imágenes.

7.7 Etapa 5 — Transporte Edge → Fog
7.7.1 Transporte del evento
Objetivo

Notificar rápidamente al Fog.

Protocolo óptimo
Protocolo	Función
MQTT	trigger operacional
Flujo
evento detectado
↓
publicación MQTT
↓
Fog recibe trigger
7.7.2 Transporte de snapshots

Cuando el Fog requiere evidencia visual:

Flujo
evento MQTT
↓
Fog solicita snapshot
↓
Edge responde HTTP
Protocolos
Protocolo	Función
HTTP/HTTPS	snapshot puntual
7.7.3 Streaming continuo

Si operador requiere visualización continua:

Protocolos
Protocolo	Función
RTSP	stream continuo
WebRTC	baja latencia interactiva
7.8 Etapa 6 — Recepción operacional en FOG
7.8.1 Recepción distribuida

El Fog recibe información proveniente de múltiples nodos Edge.

Tipos datos recibidos
Tipo	Fuente
eventos	MQTT
imágenes	HTTP
streams	RTSP/WebRTC
telemetría	MQTT
7.8.2 Construcción operacional contextual

El Fog comienza a construir visión operacional agregada.

7.9 Etapa 7 — Normalización y enriquecimiento en FOG
7.9.1 Normalización

Eventos heterogéneos son transformados a formato operacional común.

7.9.2 Enriquecimiento

Ejemplo:

evento Edge
+
zona operacional
+
timestamp sincronizado
+
reglas locales
7.9.3 Eliminación duplicados

El Fog puede detectar:

duplicados;
eventos redundantes;
inconsistencias.
7.10 Etapa 8 — Procesamiento avanzado en FOG
7.10.1 Inferencia avanzada

El Fog puede ejecutar procesamiento más complejo.

Ejemplos
OCR;
tracking;
correlación multi-cámara;
validación operacional;
análisis contextual.
7.10.2 Ejemplo operacional
camara_01 detecta vehículo
+
camara_02 detecta velocidad
+
camara_03 detecta dirección
↓
Fog correlaciona
↓
vehículo en contramano
7.11 Etapa 9 — Persistencia operacional en FOG
7.11.1 Objetivo

Mantener resiliencia operacional local.

Funciones
buffering;
operación offline;
cache operacional;
persistencia temporal.
7.12 Etapa 10 — Transporte Fog → Cloud
7.12.1 Objetivo

Sincronizar información estratégica.

Datos transportados
Tipo	Destino
eventos consolidados	Cloud
métricas	Cloud
evidencia relevante	Cloud
telemetría	Cloud
Protocolos típicos
Protocolo	Función
MQTT over TLS	eventos
HTTPS	uploads
S3 API	evidencia
WebSocket	dashboards
7.13 Etapa 11 — Procesamiento estratégico en CLOUD
7.13.1 Procesamiento histórico

El Cloud procesa información acumulada.

Operaciones
analítica;
correlación global;
entrenamiento IA;
estadísticas;
tendencias.
7.13.2 Entrenamiento IA

El Cloud puede:

entrenar modelos;
optimizar modelos;
generar versiones nuevas;
redistribuir modelos.
7.14 Etapa 12 — Presentación operacional
7.14.1 Presentación local Fog
dashboards Qt;
paneles técnicos;
consola operacional.
7.14.2 Presentación global Cloud
dashboards web;
métricas;
reportes;
copilotos IA;
supervisión multi-sitio.
7.15 Gestión de evidencia visual
7.15.1 Principio general

No toda imagen debe persistirse permanentemente.

Estrategia
Tipo	Política
imagen irrelevante	descarte
evidencia crítica	persistencia
stream temporal	bajo demanda
7.15.2 Beneficio
menor almacenamiento;
menor costo;
menor exposición privacidad.
7.16 Flujo operacional completo resumido
captura visual
↓
preprocesamiento Edge
↓
inferencia local
↓
evento semántico
↓
MQTT trigger
↓
Fog recibe
↓
Fog solicita evidencia si necesario
↓
HTTP snapshot / RTSP stream
↓
Fog correlaciona
↓
Fog almacena temporalmente
↓
Cloud sincroniza
↓
Cloud analiza
↓
Dashboard presenta
7.17 Conclusión del recorrido del dato

El sistema transforma percepción visual distribuida en flujo operacional estructurado mediante procesamiento distribuido inteligente.

El dato visual evoluciona progresivamente:

imagen
↓
dato
↓
evento
↓
contexto
↓
información operacional
↓
conocimiento estratégico