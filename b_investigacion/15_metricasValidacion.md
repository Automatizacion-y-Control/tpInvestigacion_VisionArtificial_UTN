15. Métricas operacionales y validación
15.1 Introducción

La validación del sistema propuesto requiere definir métricas capaces de evaluar el comportamiento operacional, telecomputacional y funcional de la arquitectura distribuida.

La evaluación no debe limitarse únicamente a precisión de modelos IA.

Debido a la naturaleza AIoT distribuida de la plataforma, la validación debe contemplar simultáneamente:

percepción;
transporte del dato;
inferencia distribuida;
resiliencia;
latencia;
escalabilidad;
operación distribuida;
consumo de recursos;
estabilidad operacional.
15.2 Objetivo de validación

El objetivo principal consiste en verificar que la arquitectura propuesta cumple los principios definidos durante el diseño conceptual.

Principios a validar
Principio	Validación
procesamiento distribuido	distribución Edge–Fog–Cloud
reducción tráfico	transporte selectivo
desacoplamiento	independencia capas
resiliencia	tolerancia fallos
escalabilidad	incorporación nodos
operación distribuida	autonomía parcial
15.3 Métricas de percepción visual
15.3.1 Objetivo

Evaluar calidad de percepción e inferencia visual.

15.3.2 Precisión detección
Métrica

Porcentaje de detecciones correctas.

Fórmula

Precisi
o
ˊ
n=
Detecciones Totales
Detecciones Correctas
	​


15.3.3 Recall
Objetivo

Medir capacidad de detectar eventos reales.

Fórmula

Recall=
Verdaderos Positivos+Falsos Negativos
Verdaderos Positivos
	​


15.3.4 Falsos positivos

Cantidad de eventos incorrectamente detectados.

15.3.5 Falsos negativos

Eventos reales no detectados.

15.3.6 Precisión OCR
Métrica

Evaluar reconocimiento de caracteres.

Fórmula

Precisi
o
ˊ
n
OCR
	​

=
Caracteres Totales
Caracteres Correctos
	​


15.4 Métricas de latencia
15.4.1 Introducción

La latencia constituye uno de los parámetros críticos del sistema distribuido.

15.4.2 Latencia Edge

Tiempo entre:

captura
↓
evento generado
15.4.3 Latencia Edge → Fog

Tiempo entre:

evento generado
↓
evento recibido Fog
15.4.4 Latencia Fog procesamiento

Tiempo requerido para:

OCR;
correlación;
validación.
15.4.5 Latencia total operacional

Tiempo completo desde percepción hasta presentación.

Fórmula conceptual

Latencia
Total
	​

=Latencia
Edge
	​

+Latencia
Transporte
	​

+Latencia
Fog
	​

+Latencia
Cloud
	​


15.5 Métricas telecomputacionales
15.5.1 Objetivo

Evaluar eficiencia del transporte distribuido del dato visual.

15.5.2 Consumo ancho banda
Medición

Cantidad de tráfico generado.

Comparación
Estrategia	Tráfico
video continuo	alto
eventos semánticos	bajo
15.5.3 Throughput eventos

Cantidad de eventos procesados por unidad temporal.

15.5.4 Streams simultáneos

Cantidad máxima de streams soportados.

15.5.5 Uso protocolos

Evaluación eficiencia:

MQTT;
HTTP;
RTSP;
WebRTC.
15.6 Métricas computacionales
15.6.1 CPU

Consumo procesamiento.

15.6.2 RAM

Uso memoria.

15.6.3 Temperatura

Importante especialmente en Edge y Fog.

15.6.4 FPS procesamiento

Frames procesados por segundo.

15.6.5 Uso GPU

En sistemas acelerados.

15.7 Métricas de resiliencia
15.7.1 Objetivo

Evaluar capacidad de operación ante fallos parciales.

15.7.2 Desconexión Cloud

Escenario:

Cloud offline
↓
Fog continúa operativo
15.7.3 Desconexión Edge

Evaluar comportamiento ante pérdida nodo.

15.7.4 Recuperación

Tiempo recuperación operacional.

15.8 Métricas de disponibilidad
15.8.1 Disponibilidad nodos

Porcentaje tiempo operativo.

Fórmula

Disponibilidad=
Tiempo Total
Tiempo Operativo
	​


15.8.2 Disponibilidad servicios

Evaluación:

broker MQTT;
APIs;
dashboards;
IA services.
15.9 Métricas de almacenamiento
15.9.1 Uso almacenamiento

Cantidad espacio consumido.

15.9.2 Persistencia evidencia

Relación:

eventos útiles
vs
datos descartados
15.9.3 Eficiencia retención

Evaluar política persistencia selectiva.

15.10 Métricas IA distribuidas
15.10.1 Inferencias por segundo

Cantidad inferencias ejecutadas.

15.10.2 Tiempo inferencia

Tiempo promedio inferencia IA.

15.10.3 Drift modelos

Evaluación degradación precisión temporal.

15.10.4 Comparación Edge vs Fog
Área	Precisión	Latencia
Edge	menor	baja
Fog	mayor	media
15.11 Métricas operacionales
15.11.1 Eventos procesados

Cantidad eventos operacionales gestionados.

15.11.2 Alertas generadas

Cantidad alertas válidas.

15.11.3 Tiempo respuesta operador

Tiempo reacción humana.

15.12 Validación Edge–Fog–Cloud
15.12.1 Objetivo

Validar distribución funcional real.

Validaciones
Área	Validación
Edge	inferencia local
Fog	correlación
Cloud	supervisión global
15.13 Validación desacoplamiento
15.13.1 Objetivo

Verificar independencia relativa entre capas.

Ejemplo
Fog continúa operando
sin Cloud
15.14 Validación escalabilidad
15.14.1 Objetivo

Evaluar crecimiento horizontal.

Escenario
1 Edge
↓
10 Edge
↓
100 Edge
Métricas
degradación latencia;
carga broker;
consumo red.
15.15 Validación multi-sitio
15.15.1 Escenario
sitio Córdoba
+
sitio Rosario
+
sitio Mendoza
Objetivo

Evaluar coordinación distribuida.

15.16 Benchmarking
15.16.1 Comparación arquitectónica

Comparar:

Arquitectura	Resultado
cloud-only	referencia
Edge–Fog–Cloud	propuesta
Variables
tráfico;
latencia;
resiliencia.
15.17 Riesgos observados
Riesgo	Impacto
saturación red	latencia
Edge insuficiente	pérdida FPS
drift IA	precisión
streams excesivos	congestión
15.18 Conclusión

Las métricas definidas permiten evaluar integralmente el comportamiento operacional y arquitectónico del sistema AIoT distribuido.

La validación propuesta no se limita únicamente a desempeño de modelos IA, sino que contempla el comportamiento completo del ecosistema distribuido Edge–Fog–Cloud.

Esto permite verificar operacionalmente los principios fundamentales del framework propuesto:

procesamiento distribuido;
transporte eficiente del dato;
resiliencia;
desacoplamiento;
escalabilidad;
gestión operacional distribuida.