10. Gestión operacional distribuida
10.1 Introducción

Uno de los objetivos centrales del sistema propuesto consiste en transformar percepción visual distribuida en capacidad operacional gestionable.

La arquitectura no fue diseñada únicamente para ejecutar visión artificial, sino para permitir administración, supervisión y operación distribuida sobre múltiples nodos Edge y múltiples entornos Fog.

Esto implica que la plataforma debe proporcionar mecanismos para:

monitoreo operacional;
administración técnica;
supervisión distribuida;
diagnóstico;
control remoto;
observabilidad;
gestión de infraestructura;
administración IA;
gestión de eventos;
operación multi-sitio.
10.2 Principio operacional

La plataforma adopta el siguiente principio:

la percepción distribuida
debe transformarse
en operación distribuida

Esto implica que la gestión debe distribuirse coherentemente entre:

Edge;
Fog;
Cloud.
10.3 Gestión operacional por capas
Área	Gestión dominante
Edge	estado dispositivo
Fog	operación local
Cloud	supervisión global
10.4 Dashboard operacional
10.4.1 Objetivo

Permitir supervisión operacional en tiempo real.

10.4.2 Funciones
monitoreo eventos

Visualización de:

detecciones;
alertas;
incidentes;
eventos críticos.
monitoreo visual

Visualización:

snapshots;
streams activos;
cámaras online/offline.
métricas operacionales

Ejemplos:

eventos por minuto;
cámaras activas;
latencia promedio;
uso ancho banda.
10.4.3 Actualización tiempo real

La actualización puede implementarse mediante:

Tecnología	Función
WebSocket	tiempo real bidireccional
SSE	eventos live
MQTT dashboard bridge	eventos en vivo
10.4.4 Niveles visualización
Nivel	Alcance
local	Fog específico
regional	múltiples FOGs
global	infraestructura completa
10.5 Dashboard técnico
10.5.1 Objetivo

Permitir supervisión técnica de infraestructura.

10.5.2 Estado nodos

Visualización de:

Edge online/offline;
FOGs activos;
latencia conexión;
consumo recursos.
10.5.3 Estado IA

Visualización de:

modelos desplegados;
versiones activas;
inferencias por segundo;
precisión estimada.
10.5.4 Estado telecomputacional

Visualización:

tráfico;
throughput;
uso red;
streams activos.
10.5.5 Observabilidad

La plataforma debe permitir observabilidad distribuida.

Métricas posibles
Métrica	Aplicación
CPU	carga procesamiento
RAM	saturación
temperatura	estabilidad
FPS	rendimiento visión
latencia	calidad operacional
10.6 Consola CLI administrativa
10.6.1 Objetivo

Permitir administración técnica avanzada.

10.6.2 Funciones CLI
gestión nodos

Ejemplo:

visiosphere node list
estado nodos
visiosphere node status edge-01
despliegue modelos
visiosphere model deploy yolo-v5
logs
visiosphere logs fog-02
10.6.3 Beneficios CLI
Beneficio	Resultado
automatización	scripting
diagnóstico rápido	soporte
operación remota	administración distribuida
10.7 Gestión de nodos EDGE
10.7.1 Objetivo

Administrar dispositivos distribuidos.

10.7.2 Registro nodos

Cada nodo debe registrarse dentro del sistema.

Información mínima
Campo	Descripción
ID nodo	identidad única
tipo hardware	plataforma
versión firmware	estado software
ubicación	contexto operacional
10.7.3 Descubrimiento

La plataforma puede incorporar mecanismos automáticos de descubrimiento.

10.7.4 Estado operacional

El sistema debe monitorear:

disponibilidad;
temperatura;
conectividad;
carga.
10.7.5 OTA

Los nodos Edge deben permitir actualización remota.

Componentes actualizables
firmware;
configuración;
modelos IA.
10.8 Gestión de FOGs
10.8.1 Objetivo

Administrar infraestructura operacional distribuida.

10.8.2 Registro FOGs

Cada Fog debe registrarse.

Información
Campo	Descripción
ID Fog	identidad
capacidad computacional	recursos
ubicación	sitio físico
Edge asociados	nodos conectados
10.8.3 Federación de FOGs

La arquitectura puede soportar múltiples FOGs coordinados.

Ejemplo
FOG Norte
FOG Centro
FOG Sur
↓
sincronización Cloud
10.8.4 Balance operacional

La plataforma puede redistribuir carga.

Ejemplos
inferencia;
almacenamiento;
streams.
10.8.5 Resiliencia Fog

El sistema puede tolerar desconexión parcial.

Ejemplo
Cloud offline
↓
Fog continúa operando
10.9 Gestión de eventos
10.9.1 Objetivo

Administrar flujo operacional generado por percepción visual.

10.9.2 Clasificación eventos
Tipo	Prioridad
informativo	baja
advertencia	media
crítico	alta
10.9.3 Pipeline operacional
evento detectado
↓
clasificación
↓
correlación
↓
alerta
↓
persistencia
10.9.4 Correlación

El sistema puede relacionar eventos múltiples.

10.9.5 Alertas

Las alertas pueden distribuirse mediante:

dashboard;
email;
MQTT;
notificaciones;
APIs externas.
10.10 Gestión multimedia
10.10.1 Objetivo

Administrar recursos visuales distribuidos.

10.10.2 Streams

Gestión de:

activación;
cierre;
autorización;
consumo.
10.10.3 Snapshots

Políticas:

bajo demanda;
persistencia selectiva;
evidencia crítica.
10.10.4 Evidencia visual

Administración:

retención;
clasificación;
indexación;
acceso controlado.
10.11 Observabilidad distribuida
10.11.1 Introducción

La plataforma debe permitir comprender estado interno del sistema.

10.11.2 Logs
Tipo log	Aplicación
Edge	eventos locales
Fog	correlación
Cloud	auditoría global
10.11.3 Métricas

Ejemplos:

FPS;
latencia inferencia;
uso CPU;
tráfico red.
10.11.4 Trazabilidad

Debe poder reconstruirse recorrido operacional del dato.

Ejemplo
Edge detecta
↓
Fog correlaciona
↓
Cloud registra
↓
Dashboard presenta
10.12 Operación multi-sitio
10.12.1 Objetivo

Administrar múltiples despliegues distribuidos.

10.12.2 Ejemplo
sitio Córdoba
sitio Rosario
sitio Mendoza
↓
gestión centralizada
10.12.3 Beneficios
escalabilidad;
administración central;
resiliencia regional.
10.13 Integración externa
10.13.1 Objetivo

Permitir interoperabilidad.

Integraciones posibles
SCADA;
ERP;
MES;
plataformas urbanas;
APIs externas.
10.14 Conclusión

La gestión operacional distribuida constituye uno de los pilares fundamentales de la arquitectura propuesta.

La plataforma no se limita a ejecutar modelos de visión artificial, sino que proporciona mecanismos completos de:

administración;
supervisión;
operación;
observabilidad;
coordinación distribuida.

Esto transforma la infraestructura en un verdadero sistema AIoT operacional distribuido de percepción visual inteligente.