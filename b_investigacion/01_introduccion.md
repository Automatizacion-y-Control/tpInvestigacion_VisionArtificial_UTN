1. Introducción
1.1 Contexto del problema

La percepción visual se ha convertido en uno de los principales mecanismos de adquisición de información en entornos urbanos, industriales y operacionales. La creciente disponibilidad de cámaras, sensores visuales y dispositivos de captura distribuidos ha permitido ampliar significativamente la capacidad de observación sobre procesos físicos, infraestructura y comportamiento operacional.

Sin embargo, gran parte de las implementaciones actuales continúan desarrollándose bajo modelos centralizados, donde el procesamiento visual depende de servidores únicos o infraestructuras cloud remotas. Este enfoque genera múltiples limitaciones técnicas y operacionales:

incremento del consumo de ancho de banda debido al transporte continuo de video crudo;
aumento de latencia operacional;
dependencia crítica de conectividad permanente;
aparición de puntos únicos de falla;
baja reutilización arquitectónica entre dominios;
saturación humana ante grandes volúmenes de información visual.

En numerosos escenarios —como peajes, monitoreo vial, ciudades inteligentes, seguridad operacional o infraestructura crítica— el problema ya no consiste únicamente en capturar imágenes, sino en transformar percepción visual en información operacional útil, estructurada y accionable.

La dificultad principal no radica exclusivamente en detectar objetos mediante inteligencia artificial, sino en gestionar operacionalmente eventos distribuidos generados a partir de múltiples fuentes visuales heterogéneas.

En este contexto surge la necesidad de arquitecturas distribuidas capaces de:

procesar información cerca del origen del dato;
reducir transmisión innecesaria de video crudo;
operar parcialmente de forma autónoma;
distribuir inteligencia entre distintas capas computacionales;
escalar horizontalmente sin rediseñar completamente el sistema;
transformar percepción visual en eventos operacionales estructurados.
1.2 Problema de ingeniería

Los sistemas tradicionales de visión artificial suelen desarrollarse como soluciones aisladas y altamente acopladas a un único dominio de aplicación. Cada implementación redefine componentes de captura, procesamiento, comunicación y almacenamiento, generando arquitecturas rígidas y poco reutilizables.

Esta situación produce múltiples problemas de ingeniería:

Fragmentación arquitectónica

Cada nuevo escenario requiere rediseñar componentes completos del sistema:

infraestructura de captura;
procesamiento visual;
comunicación;
almacenamiento;
supervisión operacional.

La ausencia de un framework distribuido reutilizable impide consolidar conocimiento arquitectónico común.

Dependencia de procesamiento centralizado

Los modelos cloud-only trasladan continuamente imágenes o video hacia centros de procesamiento remotos.

Esto provoca:

aumento de tráfico de red;
dependencia permanente de conectividad;
incremento de latencia;
degradación operacional ante cortes de red;
escalabilidad limitada.
Saturación operacional humana

El crecimiento de dispositivos visuales distribuidos supera la capacidad humana de supervisión manual continua.

Los operadores no pueden interpretar simultáneamente grandes volúmenes de streams visuales en tiempo real.

El problema deja de ser únicamente tecnológico y pasa a ser operacional.

Acoplamiento tecnológico

Muchas soluciones quedan ligadas a:

un único fabricante;
una arquitectura específica;
un hardware particular;
un protocolo propietario.

Esto limita:

escalabilidad;
mantenibilidad;
portabilidad;
evolución tecnológica futura.
1.3 Hipótesis del proyecto

La distribución funcional del procesamiento visual mediante una arquitectura AIoT Edge–Fog–Cloud permite transformar percepción visual distribuida en información operacional estructurada, reduciendo latencia, consumo de red y dependencia centralizada, mientras mejora escalabilidad, resiliencia y capacidad de gestión operacional.

1.4 Objetivo general

Diseñar e implementar una plataforma AIoT distribuida de percepción visual capaz de transformar eventos detectados mediante visión artificial en información operacional estructurada y gestionable, utilizando una arquitectura Edge–Fog–Cloud desacoplada, escalable y multi-dominio.

1.5 Objetivos específicos
Objetivos arquitectónicos
Diseñar una arquitectura distribuida Edge–Fog–Cloud orientada a percepción visual.
Definir separación funcional entre Edge, Fog y Cloud.
Diseñar una arquitectura desacoplada y extensible.
Objetivos telecomputacionales
Definir mecanismos eficientes de transporte del dato visual.
Minimizar transmisión innecesaria de video crudo.
Optimizar protocolos según finalidad operacional.
Objetivos de inteligencia artificial
Implementar inferencia distribuida en múltiples capas.
Permitir despliegue de modelos IA adaptados a contexto operacional.
Incorporar capacidad futura de entrenamiento y distribución de modelos.
Objetivos operacionales
Transformar percepción visual en eventos operacionales estructurados.
Permitir supervisión distribuida mediante dashboards y herramientas administrativas.
Soportar operación autónoma parcial ante fallos de conectividad.
Objetivos de validación
Validar el framework mediante un caso aplicado de peaje inteligente.
medir latencia, disponibilidad y precisión operacional;
verificar escalabilidad arquitectónica;
validar distribución funcional AIoT.
1.6 Alcance conceptual del proyecto

El proyecto no se define como una aplicación puntual de visión artificial, sino como una plataforma distribuida de gestión operacional basada en percepción visual.

La arquitectura propuesta busca permanecer independiente del dominio específico de aplicación.

La variación entre escenarios ocurre principalmente en:

modelos de percepción visual;
reglas operacionales;
lógica contextual de análisis.

La infraestructura distribuida subyacente permanece constante.

Esto permite reutilizar la arquitectura en múltiples dominios sin rediseñar completamente el sistema.

1.7 Definición del sistema

Percepta, desarrollado sobre la plataforma VisioSphere, constituye un sistema de gestión AIoT basado en percepción visual distribuida.

El sistema transforma información visual capturada desde múltiples nodos distribuidos en eventos operacionales estructurados mediante procesamiento distribuido sobre arquitectura Edge–Fog–Cloud.

La plataforma integra:

percepción visual distribuida;
inferencia IA;
procesamiento operacional;
comunicación desacoplada;
gestión distribuida;
almacenamiento histórico;
supervisión operacional;
administración técnica distribuida.

El resultado es una infraestructura capaz de operar como sistema distribuido de percepción operacional inteligente.