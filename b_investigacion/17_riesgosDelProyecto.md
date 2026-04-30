17. Riesgos del proyecto
17.1 Introducción

El desarrollo e implementación de una plataforma AIoT distribuida de percepción visual implica múltiples riesgos técnicos, operacionales, telecomputacionales y organizacionales.

Debido a la naturaleza distribuida del sistema, los riesgos no se concentran únicamente en software o infraestructura, sino que atraviesan simultáneamente:

hardware distribuido;
comunicación;
inferencia IA;
operación multi-capa;
seguridad;
almacenamiento;
disponibilidad;
evolución tecnológica.

El objetivo de esta sección consiste en identificar los principales riesgos asociados al proyecto y definir estrategias de mitigación.

17.2 Objetivo del análisis de riesgos

El análisis busca:

identificar riesgos críticos;
evaluar impacto operacional;
anticipar fallos potenciales;
definir mitigaciones;
aumentar resiliencia del sistema.
17.3 Riesgos técnicos
17.3.1 Complejidad distribuida
Riesgo

La arquitectura distribuida incrementa complejidad del sistema.

Impactos posibles
errores sincronización;
fallos integración;
debugging complejo;
inconsistencias estado.
Mitigación
modularidad estricta;
observabilidad;
logs distribuidos;
pruebas integración.
17.3.2 Limitaciones hardware Edge
Riesgo

Los nodos Edge pueden no poseer capacidad suficiente.

Impactos
baja inferencia;
pérdida frames;
latencia elevada.
Mitigación
modelos cuantizados;
inferencia simplificada;
preprocesamiento optimizado.
17.3.3 Saturación Fog
Riesgo

El Fog podría recibir más eventos de los soportables.

Impactos
retrasos;
colas saturadas;
pérdida eventos.
Mitigación
balance carga;
buffering;
escalamiento horizontal.
17.3.4 Drift modelos IA
Riesgo

Los modelos pueden degradarse temporalmente.

Impactos
falsos positivos;
falsos negativos;
pérdida precisión.
Mitigación
reentrenamiento;
monitoreo precisión;
datasets actualización.
17.3.5 Dependencia aceleradores IA
Riesgo

Dependencia excesiva hardware específico.

Mitigación
ONNX;
abstracción inferencia;
compatibilidad multi-backend.
17.4 Riesgos telecomputacionales
17.4.1 Pérdida conectividad
Riesgo

Desconexión entre capas.

Impactos
pérdida sincronización;
retraso eventos.
Mitigación
buffering local;
resiliencia Fog;
operación offline parcial.
17.4.2 Saturación ancho banda
Riesgo

Exceso transmisión multimedia.

Impactos
latencia;
pérdida streams.
Mitigación
transporte selectivo;
eventos semánticos;
streaming bajo demanda.
17.4.3 Latencia excesiva
Riesgo

Retrasos operacionales.

Mitigación
inferencia local;
procesamiento Edge/Fog;
optimización protocolos.
17.4.4 Congestión MQTT
Riesgo

Saturación broker eventos.

Mitigación
clustering;
balance carga;
segmentación tópicos.
17.5 Riesgos operacionales
17.5.1 Falsas alertas
Riesgo

Generación incorrecta eventos.

Impacto
fatiga operadores;
pérdida confianza sistema.
Mitigación
correlación Fog;
validación contextual;
thresholds adaptativos.
17.5.2 Pérdida evidencia
Riesgo

No persistir evidencia crítica.

Mitigación
políticas retención;
redundancia almacenamiento.
17.5.3 Dependencia operadores
Riesgo

Sobrecarga humana.

Mitigación
automatización;
clasificación alertas;
dashboards inteligentes.
17.5.4 Errores configuración
Riesgo

Configuraciones incorrectas distribuidas.

Mitigación
versionado configuración;
validación automática;
templates.
17.6 Riesgos de seguridad
17.6.1 Compromiso nodos Edge
Riesgo

Acceso físico o lógico.

Impacto
falsificación eventos;
espionaje visual.
Mitigación
secure boot;
certificados;
hardening.
17.6.2 Interceptación tráfico
Riesgo

Captura comunicaciones.

Mitigación
TLS;
VPN;
mTLS.
17.6.3 Acceso no autorizado streams
Riesgo

Visualización ilegal.

Mitigación
autenticación;
tokens temporales;
expiración sesiones.
17.6.4 Ataques infraestructura Cloud
Riesgo

Compromiso servicios centrales.

Mitigación
IAM;
RBAC;
segmentación;
auditoría.
17.7 Riesgos privacidad
17.7.1 Exposición datos visuales
Riesgo

Acceso indebido imágenes.

Mitigación
minimización persistencia;
anonimización;
control acceso.
17.7.2 Cumplimiento regulatorio
Riesgo

Incumplimiento normativas protección datos.

Mitigación
políticas retención;
auditoría acceso;
cumplimiento normativo.
17.8 Riesgos IA
17.8.1 Sesgo modelos
Riesgo

Modelos no generalizables.

Mitigación
datasets diversos;
validación continua.
17.8.2 Ataques adversariales
Riesgo

Manipulación inferencia visual.

Mitigación
validación múltiple;
correlación contextual.
17.8.3 Sobreajuste
Riesgo

Modelo especializado excesivamente.

Mitigación
validación cruzada;
datasets variados.
17.9 Riesgos escalabilidad
17.9.1 Crecimiento nodos
Riesgo

Arquitectura no soporte expansión.

Mitigación
diseño horizontal;
microservicios;
desacoplamiento.
17.9.2 Multiplicación streams
Riesgo

Saturación multimedia.

Mitigación
streams bajo demanda;
edge inference.
17.10 Riesgos mantenimiento
17.10.1 Actualizaciones distribuidas
Riesgo

Despliegues inconsistentes.

Mitigación
OTA controlado;
rollback.
17.10.2 Compatibilidad versiones
Riesgo

Incompatibilidades entre capas.

Mitigación
versionado APIs;
contratos protocolos.
17.11 Riesgos económicos
17.11.1 Costos Cloud
Riesgo

Escalamiento costos infraestructura.

Mitigación
procesamiento local;
almacenamiento selectivo.
17.11.2 Costos almacenamiento
Riesgo

Persistencia excesiva video.

Mitigación
retención inteligente;
persistencia selectiva.
17.12 Matriz resumida de riesgos
Riesgo	Impacto	Mitigación
pérdida conectividad	media	buffering Fog
drift IA	alta	reentrenamiento
saturación red	alta	eventos semánticos
acceso ilegal streams	alta	autenticación
Edge insuficiente	media	modelos optimizados
17.13 Estrategia general mitigación

La estrategia general combina:

desacoplamiento;
resiliencia distribuida;
redundancia;
observabilidad;
seguridad transversal;
procesamiento local.
17.14 Conclusión

El sistema AIoT distribuido propuesto introduce riesgos significativos debido a su complejidad operacional y arquitectónica.

Sin embargo, la correcta distribución funcional entre Edge, Fog y Cloud, junto con mecanismos adecuados de seguridad, resiliencia y desacoplamiento, permite reducir considerablemente dichos riesgos.

La identificación temprana y mitigación sistemática de estos factores resulta fundamental para construir una plataforma operacional robusta, escalable y sostenible.