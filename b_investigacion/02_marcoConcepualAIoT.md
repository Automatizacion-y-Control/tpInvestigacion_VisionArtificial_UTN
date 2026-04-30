2. Marco conceptual AIoT
2.1 Definición de AIoT

El concepto AIoT surge de la convergencia entre Internet of Things (IoT) e Inteligencia Artificial (AI), integrando capacidades de percepción distribuida, procesamiento computacional y análisis inteligente sobre sistemas físicos conectados.

Mientras los sistemas IoT tradicionales se enfocan principalmente en captura y transmisión de datos, los sistemas AIoT incorporan capacidades de inferencia, interpretación y toma de decisiones distribuidas dentro de la propia infraestructura computacional.

Esto implica que el sistema no solo transporta información, sino que además:

interpreta contexto;
detecta patrones;
genera eventos semánticos;
ejecuta análisis distribuidos;
optimiza procesamiento según contexto operacional.

En un sistema AIoT, la inteligencia deja de estar concentrada exclusivamente en servidores centrales y pasa a distribuirse entre múltiples niveles computacionales.

2.2 Arquitectura Edge–Fog–Cloud

La arquitectura Edge–Fog–Cloud constituye el modelo estructural utilizado para distribuir funcionalmente capacidades computacionales dentro del sistema.

Cada capa posee responsabilidades específicas.

Edge

La capa Edge representa el nivel más cercano al origen físico del dato.

En esta capa ocurren tareas relacionadas con:

percepción;
captura;
preprocesamiento;
inferencia primaria;
generación inicial de eventos.

El objetivo principal consiste en reducir latencia y minimizar transmisión innecesaria de datos hacia capas superiores.

Fog

La capa Fog constituye el nivel intermedio de coordinación operacional distribuida.

Su función consiste en:

correlacionar eventos;
coordinar nodos Edge;
ejecutar procesamiento operacional;
mantener operación local autónoma;
administrar recursos distribuidos;
desacoplar Edge del Cloud.

El Fog actúa como núcleo operacional local del sistema.

Cloud

La capa Cloud concentra capacidades globales de:

almacenamiento histórico;
analítica masiva;
entrenamiento de modelos;
supervisión global;
administración multi-sitio;
integración corporativa.

La nube deja de ser el único punto de procesamiento y pasa a formar parte de un sistema distribuido jerárquico.

2.3 Diferencia entre IoT tradicional y AIoT

En arquitecturas IoT tradicionales, los dispositivos suelen limitarse a capturar y transmitir datos.

El procesamiento principal ocurre en servidores centrales o plataformas cloud.

En contraste, AIoT distribuye capacidades de procesamiento e inferencia a lo largo de múltiples capas.

IoT tradicional
Sensor → transmisión → servidor central → procesamiento

Características:

baja inteligencia local;
alta dependencia cloud;
transmisión masiva de datos;
procesamiento centralizado.
AIoT
Percepción → inferencia distribuida → eventos semánticos → análisis contextual

Características:

inteligencia distribuida;
procesamiento cercano al dato;
reducción de tráfico;
operación parcialmente autónoma;
análisis contextual distribuido.
2.4 Percepción visual como fuente operacional

La visión artificial permite transformar imágenes en información operacional interpretable.

Sin embargo, dentro del enfoque propuesto, la imagen no constituye el objetivo final del sistema.

El objetivo real consiste en generar información operacional estructurada.

Por ejemplo:

Imagen capturada	Evento operacional generado
vehículo detectado	registro de paso
patente reconocida	identificación vehicular
peatón en zona crítica	alerta operacional
humo detectado	incidente ambiental
vehículo detenido	posible emergencia

La percepción visual se convierte así en mecanismo de adquisición operacional del entorno.

2.5 Gestión operacional basada en eventos semánticos

Uno de los principios fundamentales del sistema consiste en transformar percepción visual en eventos semánticos estructurados.

En lugar de transmitir continuamente video crudo, el sistema genera eventos interpretables.

Ejemplo:

{
  "evento": "vehiculo_detectado",
  "patente": "AB123CD",
  "zona": "carril_2",
  "timestamp": "2026-04-26T18:40:00"
}

Esto permite:

reducir tráfico de red;
desacoplar procesamiento;
facilitar correlación operacional;
automatizar decisiones;
escalar horizontalmente.
2.6 Sistemas distribuidos orientados a percepción

El sistema propuesto puede interpretarse como un sistema distribuido orientado a percepción.

La percepción no ocurre en un único nodo central, sino en múltiples entidades distribuidas capaces de colaborar operacionalmente.

Cada nodo participa parcialmente en la construcción del estado operacional global.

Esto implica:

percepción distribuida;
procesamiento distribuido;
análisis contextual compartido;
coordinación operacional distribuida.
2.7 Concepto de percepción distribuida

La percepción distribuida implica que múltiples nodos capturan distintas partes del entorno físico y contribuyen colectivamente a construir representación operacional del sistema observado.

Ejemplo:

camara_01 → detecta vehículo
camara_02 → detecta velocidad
camara_03 → detecta dirección

Fog correlaciona:

vehículo detectado en contramano

La percepción emerge de múltiples nodos coordinados.

2.8 Eventos estructurados vs video crudo

Transmitir continuamente video crudo presenta múltiples limitaciones:

alto consumo de ancho de banda;
mayor latencia;
dificultad de escalabilidad;
almacenamiento excesivo;
saturación operacional.

El enfoque propuesto prioriza transmisión de eventos estructurados.

Video crudo
gran volumen
baja semántica
alto costo de red
Evento estructurado
bajo volumen
alta semántica
alto valor operacional

Esto permite construir sistemas operacionalmente escalables.

2.9 Distribución funcional del procesamiento

El modelo AIoT propuesto distribuye funciones según capacidades y contexto operacional.

Edge
percepción inmediata;
inferencia rápida;
generación primaria de eventos.
Fog
correlación;
validación;
coordinación local;
análisis operacional.
Cloud
análisis histórico;
entrenamiento;
supervisión global;
inteligencia estratégica.
2.10 Desacoplamiento arquitectónico

Uno de los objetivos centrales del sistema consiste en evitar dependencia rígida entre componentes.

El desacoplamiento se aplica sobre:

hardware;
protocolos;
modelos IA;
dominios de aplicación;
infraestructura.

Esto permite:

reemplazar componentes;
escalar capas independientemente;
adaptar tecnologías futuras;
mantener interoperabilidad.
2.11 AI como parámetro transversal

La inteligencia artificial no se implementa únicamente en una capa específica.

La IA atraviesa múltiples niveles del sistema:

Capa	Rol IA
Edge	inferencia primaria
Fog	correlación operacional
Cloud	entrenamiento y optimización

La IA se comporta como parámetro transversal distribuido.

2.12 Seguridad como parámetro transversal

La seguridad también se define como elemento transversal.

Cada capa implementa mecanismos específicos de protección:

autenticación;
cifrado;
control de acceso;
auditoría;
protección operacional.

La seguridad no se incorpora posteriormente, sino desde el diseño inicial del sistema distribuido.