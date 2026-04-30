3. Arquitectura general del sistema
3.1 Visión general de VisioSphere / Percepta

Percepta, desarrollado sobre la plataforma VisioSphere, constituye un sistema de gestión AIoT orientado a percepción visual distribuida.

El sistema fue concebido como una infraestructura operacional capaz de transformar percepción visual en información estructurada mediante procesamiento distribuido sobre arquitectura Edge–Fog–Cloud.

A diferencia de sistemas tradicionales centrados exclusivamente en visión artificial o videovigilancia, la propuesta se orienta a gestión operacional distribuida.

La percepción visual actúa como mecanismo de adquisición del estado del entorno físico.

El objetivo del sistema no consiste únicamente en detectar objetos dentro de imágenes, sino en generar eventos operacionales interpretables y utilizables dentro de procesos de supervisión, monitoreo y toma de decisiones.

3.2 Principio arquitectónico fundamental

El sistema se basa en un principio central:

procesar cerca del dato
coordinar localmente
centralizar estratégicamente

Esto implica distribuir capacidades funcionales según contexto operacional y recursos disponibles.

3.3 Arquitectura lógica

La arquitectura lógica se organiza en tres capas funcionales principales:

Capa	Función principal
Edge	percepción y generación primaria de eventos
Fog	coordinación y gestión operacional distribuida
Cloud	supervisión global y analítica estratégica
Relación entre capas
EDGE
captura + inferencia primaria
        ↓
FOG
coordinación + validación + correlación
        ↓
CLOUD
analítica + gestión global + entrenamiento
3.4 Arquitectura física

La arquitectura física define los recursos computacionales reales desplegados en cada capa.

Edge

La capa Edge puede implementarse mediante múltiples tipos de dispositivos:

microcontroladores con capacidades visuales;
SBCs embebidos;
cámaras inteligentes;
nodos AI Edge;
gateways visuales especializados.

Ejemplos posibles:

plataformas basadas en ARM Cortex;
ESP32 visuales;
Jetson;
Raspberry Pi;
dispositivos AI acelerados;
hardware industrial especializado.
Fog

La capa Fog opera sobre recursos computacionales intermedios capaces de ejecutar procesamiento operacional distribuido.

Puede implementarse mediante:

mini PCs industriales;
servidores locales;
SBCs avanzados;
gateways industriales;
nodos Linux especializados.
Cloud

La infraestructura Cloud concentra recursos de:

almacenamiento distribuido;
cómputo escalable;
entrenamiento IA;
servicios distribuidos;
analítica avanzada.
3.5 Arquitectura funcional

La arquitectura funcional distribuye responsabilidades específicas entre capas.

Edge — percepción distribuida

Funciones principales:

captura visual;
preprocesamiento;
inferencia primaria;
generación de eventos;
reducción de datos.

Objetivo:

evitar transportar información innecesaria
Fog — núcleo operacional distribuido

Funciones principales:

correlación de eventos;
validación;
enriquecimiento semántico;
buffering;
coordinación Edge;
operación local autónoma.

El Fog constituye el núcleo operacional del sistema distribuido.

Cloud — inteligencia estratégica

Funciones principales:

almacenamiento histórico;
entrenamiento IA;
dashboards globales;
analítica;
administración multi-sitio;
integración externa.
3.6 Arquitectura operacional

La arquitectura operacional define cómo el sistema se comporta durante operación real.

Operación distribuida

Cada capa posee autonomía parcial.

Ejemplo:

Capa	Capacidad autónoma
Edge	detección local
Fog	operación local ante caída cloud
Cloud	coordinación global
Resiliencia operacional

El sistema busca minimizar dependencia crítica entre capas.

Ejemplo:

si Cloud falla
↓
Fog continúa operando

si Fog falla
↓
Edge continúa detectando
Desacoplamiento operacional

Los componentes se comunican mediante eventos y protocolos desacoplados.

Esto evita dependencias rígidas.

3.7 Arquitectura telecomputacional

La arquitectura telecomputacional define cómo se distribuyen:

recursos computacionales;
procesamiento;
transporte del dato;
comunicación;
sincronización.
Distribución del procesamiento
Área	Procesamiento dominante
Edge	inferencia inmediata
Fog	correlación operacional
Cloud	procesamiento estratégico
Distribución del dato visual
Tipo dato	Destino ideal
imagen cruda	permanece preferentemente en Edge
evento semántico	Edge → Fog
evidencia relevante	Fog → Cloud
stream visual	bajo demanda
3.8 Flujo general del sistema

El flujo operacional general puede resumirse como:

captura visual
        ↓
preprocesamiento local
        ↓
inferencia IA
        ↓
generación evento semántico
        ↓
transporte hacia Fog
        ↓
correlación operacional
        ↓
persistencia
        ↓
analítica global
        ↓
presentación operacional
3.9 Arquitectura basada en eventos

El sistema adopta paradigma orientado a eventos.

Esto implica que los componentes reaccionan ante ocurrencias operacionales específicas.

Ejemplo:

vehículo detectado
↓
evento generado
↓
Fog reacciona
↓
Cloud registra
↓
dashboard actualiza
3.10 Separación entre percepción y gestión

Un principio fundamental del sistema consiste en separar:

Función	Responsable
percepción	Edge
gestión operacional	Fog
supervisión estratégica	Cloud

Esto permite escalabilidad y reutilización arquitectónica.

3.11 Escalabilidad horizontal

La arquitectura permite incorporar nuevos nodos sin rediseñar completamente el sistema.

Ejemplo:

nuevo nodo Edge
↓
registro en Fog
↓
integración automática operacional

La arquitectura crece horizontalmente mediante incorporación de nodos distribuidos.

3.12 Multi-dominio

La arquitectura permanece constante independientemente del dominio de aplicación.

Lo que cambia entre escenarios es:

modelo IA;
reglas operacionales;
contexto semántico.

La infraestructura permanece estable.

3.13 Visión arquitectónica final

La plataforma puede interpretarse como un sistema distribuido de percepción operacional inteligente capaz de:

observar;
interpretar;
correlacionar;
gestionar;
presentar información operacional derivada de percepción visual distribuida.

El sistema transforma cámaras y nodos visuales pasivos en entidades activas dentro de una infraestructura AIoT operacional distribuida.