12. Caso de validación — Peaje inteligente distribuido
12.1 Introducción

Para validar operacional y arquitectónicamente la plataforma propuesta se selecciona como caso de aplicación un sistema de peaje inteligente distribuido basado en percepción visual AIoT.

El dominio de peajes representa un escenario adecuado debido a que combina:

percepción visual continua;
necesidad de baja latencia;
eventos críticos;
múltiples nodos distribuidos;
necesidad de correlación operacional;
generación permanente de eventos estructurados.

Además, permite validar simultáneamente:

distribución Edge–Fog–Cloud;
transporte eficiente del dato visual;
inferencia distribuida;
gestión operacional;
resiliencia;
escalabilidad.
12.2 Objetivo del caso de validación

El objetivo consiste en demostrar que la arquitectura propuesta puede:

detectar vehículos;
reconocer patentes;
generar eventos operacionales;
coordinar múltiples nodos;
minimizar tráfico innecesario;
operar distribuidamente.
12.3 Escenario operacional

El escenario simulado consiste en un conjunto de carriles de peaje monitoreados mediante nodos visuales distribuidos.

Cada carril posee capacidad de percepción autónoma local.

Componentes del escenario
Componente	Función
cámaras Edge	captura visual
nodo Fog local	correlación operacional
Cloud	supervisión global
dashboard	monitoreo operadores
12.4 Arquitectura aplicada
Edge

Cada carril posee uno o más nodos Edge responsables de:

captura visual;
inferencia primaria;
generación eventos;
snapshots bajo demanda.
Fog

El Fog opera localmente dentro de la estación de peaje.

Funciones:

OCR;
correlación;
validación;
buffering;
dashboards locales.
Cloud

El Cloud centraliza:

métricas globales;
histórico;
reportes;
entrenamiento IA;
supervisión multi-sitio.
12.5 Flujo operacional del caso
Etapa 1 — Captura

El nodo Edge captura frames vehiculares.

Etapa 2 — Inferencia local

El Edge ejecuta detección primaria.

Resultado
{
  "evento": "vehiculo_detectado"
}
Etapa 3 — Transporte evento

El evento se transmite mediante MQTT hacia Fog.

Etapa 4 — Solicitud evidencia

Fog solicita snapshot mediante HTTP.

Etapa 5 — OCR Fog

El Fog ejecuta OCR sobre patente.

Resultado
{
  "patente": "AB123CD"
}
Etapa 6 — Correlación operacional

Fog valida:

carril;
timestamp;
autorización;
estado vehículo.
Etapa 7 — Persistencia

Eventos relevantes son almacenados.

Etapa 8 — Sincronización Cloud

Eventos consolidados son enviados hacia Cloud.

12.6 Pipeline visual aplicado

El pipeline operacional del caso queda definido como:

captura vehículo
↓
detección local Edge
↓
evento MQTT
↓
Fog recibe trigger
↓
Fog solicita snapshot HTTP
↓
OCR Fog
↓
evento operacional estructurado
↓
persistencia
↓
Cloud sincroniza
↓
dashboard actualiza
12.7 Validación del modelo Edge–Fog–Cloud

El caso permite validar claramente distribución funcional.

Edge

Funciones validadas:

percepción;
inferencia primaria;
reducción tráfico.
Fog

Funciones validadas:

OCR;
correlación;
operación local autónoma.
Cloud

Funciones validadas:

supervisión;
histórico;
métricas.
12.8 Validación del transporte del dato

El caso demuestra diferenciación funcional de protocolos.

MQTT

Utilizado para:

triggers;
eventos;
telemetría.
HTTP

Utilizado para:

snapshots;
evidencia puntual.
RTSP/WebRTC

Utilizados para:

visualización operador;
streaming bajo demanda.
12.9 Validación del concepto de evento semántico

El sistema demuestra transición desde imagen hacia evento operacional.

Transformación
imagen vehículo
↓
OCR
↓
patente detectada
↓
evento operacional
12.10 Eventos operacionales generados

Ejemplos posibles:

Vehículo detectado
{
  "evento": "vehiculo_detectado"
}
Patente identificada
{
  "evento": "patente_identificada",
  "valor": "AB123CD"
}
Vehículo no autorizado
{
  "evento": "vehiculo_no_autorizado"
}
12.11 Gestión operacional local

El Fog permite operación local incluso bajo desconexión Cloud.

Escenario
Cloud offline
↓
Fog continúa validando vehículos
12.12 Gestión de evidencia visual

El sistema almacena únicamente evidencia relevante.

Política
Tipo	Acción
tránsito normal	descarte parcial
incidente	persistencia
error OCR	persistencia revisión
12.13 Dashboard operacional

El operador puede visualizar:

vehículos detectados;
estado carriles;
alertas;
snapshots;
streams activos.
12.14 Dashboard técnico

El sistema permite observar:

estado nodos;
latencia;
throughput;
estado IA.
12.15 Métricas evaluadas

El caso permite medir:

Métrica	Objetivo
latencia detección	tiempo reacción
uso ancho banda	eficiencia telecomputacional
precisión OCR	calidad IA
disponibilidad	resiliencia
throughput eventos	escalabilidad
12.16 Escalabilidad del caso

La arquitectura permite agregar nuevos carriles sin rediseñar sistema.

Flujo
nuevo Edge
↓
registro Fog
↓
integración automática
12.17 Resiliencia operacional

El caso valida operación distribuida resiliente.

Ejemplo
caída Cloud
↓
Fog continúa operando
↓
Edge continúa detectando
12.18 Validación del desacoplamiento

La arquitectura demuestra independencia relativa entre:

Edge;
Fog;
Cloud;
protocolos;
modelos IA.
12.19 Limitaciones observadas

Durante validación pueden surgir:

limitaciones Edge;
falsos positivos;
condiciones iluminación;
saturación red;
drift modelos.
12.20 Conclusión del caso de validación

El caso de peaje inteligente distribuido valida que la arquitectura propuesta puede transformar percepción visual distribuida en operación AIoT estructurada mediante distribución funcional Edge–Fog–Cloud.

La implementación demuestra:

reducción tráfico innecesario;
inferencia distribuida;
eventos semánticos;
resiliencia operacional;
escalabilidad;
desacoplamiento arquitectónico.

El caso confirma la viabilidad operacional del framework AIoT de percepción visual distribuida propuesto.