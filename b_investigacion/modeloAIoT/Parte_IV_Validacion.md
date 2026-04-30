**PARTE IV**

**Validación**

*¿El modelo es consistente con sistemas reales?*

La validación de un modelo formal requiere demostrar que sus estructuras conceptuales tienen correspondencia con entidades y relaciones observables en sistemas concretos. No es suficiente que el modelo sea internamente coherente: debe poder aplicarse a un sistema real y producir una descripción que sea a la vez más precisa y más útil que las descripciones disponibles sin el modelo.

Esta parte realiza esa demostración en dos pasos. El primero establece el procedimiento general de instanciación: una metodología reproducible para aplicar el modelo a cualquier sistema AIoT. El segundo aplica ese procedimiento a un sistema industrial real, verificando que el recorrido completo del modelo es consistente con la realidad del sistema.

## **Capítulo 10  —  Metodología de instanciación**

Instanciar el modelo significa aplicarlo a un sistema concreto: identificar sus manejadores, asignarlos al espacio paramétrico y verificar la consistencia del resultado. El procedimiento que se describe a continuación es aplicable a cualquier sistema que gestione información de forma distribuida, independientemente de su dominio, escala o tecnología de implementación.

### **10.1  El concepto de manejador**

El modelo describe una infraestructura en términos de parámetros y ejes. Un sistema concreto, en cambio, está compuesto por elementos físicos y lógicos: dispositivos, procesos, servicios, controladores, interfaces. Para aplicar el modelo a un sistema real es necesario un concepto que opere como unidad de mapeo entre ambos niveles de descripción.

**Manejador.** *Unidad funcional de un sistema AIoT que implementa uno o más estadios del eje funcional en un nivel definido del eje vertical, con un perfil vectorial determinado y responsabilidad sobre los parámetros transversales en su nodo. Un manejador puede ser un dispositivo físico, un proceso de software, un servicio, un controlador o cualquier combinación de estos, siempre que pueda caracterizarse por las dimensiones del modelo.*

El manejador no es una categoría tecnológica. No se define por el hardware que lo implementa ni por el protocolo que utiliza, sino por su función en el espacio paramétrico del modelo. El mismo estadio funcional puede ser implementado por manejadores radicalmente distintos en sistemas diferentes; lo que los hace equivalentes desde la perspectiva del modelo es que ocupan la misma posición en el espacio y cubren los mismos estadios.

### **10.2  Criterios de mapeo**

El mapeo de un sistema al modelo consiste en caracterizar cada manejador según las dimensiones del modelo. Para que el mapeo sea válido deben satisfacerse los siguientes criterios:

**Completitud funcional.** Los siete estadios del eje funcional deben estar cubiertos por al menos un manejador. Si algún estadio no tiene manejador asignado, el sistema tiene una brecha funcional que debe documentarse.

**Unicidad de posición.** Cada manejador debe poder asignarse a un nivel del eje vertical —Edge, Fog o Cloud— como posición primaria. Un manejador que opera en múltiples niveles debe descomponerse en sub-manejadores por nivel, o su posición debe definirse como el nivel donde se ejecuta la mayor parte de su lógica.

**Consistencia vectorial.** El perfil vectorial del nivel asignado a cada manejador debe satisfacer los requisitos de los estadios que implementa. Si un manejador requiere poder de cómputo superior al disponible en su nivel, o genera latencia superior a la que tolera su estadio, existe una inconsistencia que debe resolverse.

**Transversalidad efectiva.** Cada nivel del eje vertical debe tener cobertura de los dos parámetros transversales. La ausencia de Seguridad o de IA en cualquier nivel constituye una brecha transversal, independientemente de su cobertura en los demás niveles.

**Criterios de exclusión de mapeo.** El modelo asume inherentemente un ecosistema estructural de cargas distribuidas jerárquicamente a lo largo de un continuum físico-lógico. En consecuencia, existen tipologías formales que no son mapeables bajo este framework y quedan excluidas de su capacidad prescriptiva. En particular: a) *Sistemas monolíticos centralizados* que carecen completamente de un eje vertical reconocible (donde la totalidad absoluta del procesamiento, almacenamiento y presentación reside en un solo núcleo ineludible) y b) *Sistemas de automatismo mecatrónico puro* (autómatas lógicos desconectados o PLC aislados) que no gestionen la información de manera distribuida ni expongan sus datos hacia niveles superiores para entrelazarlos en ciclos cognitivos. Este conjunto responde a esquemas de control discreto clásico y no conforma un entorno AIoT.

### **10.3  Plantilla de definición de manejador**

Para estandarizar el procedimiento de mapeo y garantizar que cada manejador quede caracterizado de forma completa y comparable, se establece la siguiente plantilla. Su uso es obligatorio para cada manejador identificado en el sistema bajo análisis.

|**Dimensión**|**Descripción operacional requerida**|
| :- | :- |
|**Identificación**|Nombre del manejador. Rol en el eje funcional (estadio/s que implementa). Posición en el eje vertical (Edge / Fog / Cloud).|
|**Perfil vectorial**|Poder de cómputo disponible. Latencia de respuesta bajo condiciones nominales.|
|**Cobertura funcional**|Estadios del eje funcional que implementa. Estadios que delega al nivel superior o inferior.|
|**Interfaces**|Protocolo de entrada desde el nivel inferior. Protocolo de salida hacia el nivel superior. Mecanismos de sincronización.|
|**Cobertura transversal – Seguridad**|Mecanismos de autenticación, integridad y disponibilidad implementados en este nodo.|
|**Cobertura transversal – IA**|Capacidad de inferencia o agencia presente en el nodo. Modelo o lógica utilizada. Grado de autonomía.|
|**Condición de consistencia**|Verificación de que el perfil vectorial satisface los requisitos de los estadios asignados. Identificación de brechas si las hay.|

**Nota:** La plantilla no prescribe el nivel de detalle de cada campo. En la fase de mapeo inicial, una descripción de alto nivel es suficiente para verificar consistencia. El detalle se incrementa en fases posteriores de diseño o documentación del sistema.

### **10.4  Ficha de mapeo del sistema**

Una vez caracterizados todos los manejadores mediante la plantilla anterior, el mapeo del sistema completo se consolida en dos fichas. La primera asigna cada estadio funcional a su nivel y manejador responsable. La segunda verifica la cobertura de los parámetros transversales en cada nivel.

**Ficha 1  —  Asignación funcional:**

|**Estadio funcional**|**Nivel asignado**|**Manejador responsable**|**Observaciones**|
| :- | :- | :- | :- |
|**Percepción**||||
|**Preprocesamiento**||||
|**Transmisión**||||
|**Almacenamiento**||||
|**Procesamiento**||||
|**Análisis**||||
|**Presentación**||||

**Ficha 2  —  Verificación de transversalidad:**

|**Nivel**|**Seguridad presente**|**IA presente**|**Brechas identificadas**|
| :- | :- | :- | :- |
|**Edge**||||
|**Fog**||||
|**Cloud**||||

Un sistema cuya Ficha 1 tiene todos los estadios cubiertos y cuya Ficha 2 no presenta brechas satisface las condiciones de completitud funcional y transversalidad efectiva definidas en el Capítulo 7. Este es el criterio de consistencia del modelo aplicado a un sistema concreto.

## **Capítulo 11  —  Casos de aplicación e instanciación técnica**

El presente capítulo aplica el procedimiento de instanciación del Capítulo 10 utilizando como base a ecosistemas de gestión de información desplegados en entornos reales (tales como la planta de manufactura plástica TechPlast, el módulo Inst-2, o proyectos SVA). El objetivo no es describir al sistema físico base en sí, sino demostrar que el modelo agnóstico propuesto en la Parte II es capaz de representarlo de forma consistente y hacer visibles propiedades funcionales que una descripción tecnológica tradicional no revela.


### **11.1  Descripción del sistema y subsistemas relevados**

*(Nota metodológica sobre circularidad: El caso central industrial "TechPlast" exhibe circularidad constructiva subyacente, puesto que dicho sistema físico y lógico fue concebido inicialmente teniendo entendimiento previo de las reglas de este modelo. La exposición fáctica de este caso puntual no ambiciona clamar una universalidad absoluta del modelo, sino corroborar empíricamente que la metodología de instanciación y el despliegue iterativo a través del espacio paramétrico proceden exitosamente arrojando un marco lógico prescriptivo comprobable).*

El sistema gestiona la información generada por los subsistemas productivos y de servicios de la planta. Los subsistemas relevados son: sistema de enfriamiento y agua de proceso, red de aire comprimido, cabina de pintura, máquinas inyectoras, subestación eléctrica y sistema de calidad de agua. Cada subsistema genera variables de proceso, estado y calidad que constituyen el universo de datos del sistema.

El sistema preexistente a la intervención presentaba el patrón de desacople evolutivo descrito en el Capítulo 2: el Edge —instrumentación de campo y controladores— estaba consolidado y operativo; el Cloud —cuando existía— era externo y desconectado del proceso; el Fog era inexistente como capa de integración. La información generada en el Edge no llegaba al nivel de decisión de forma automática ni contextualizada.

El objetivo del sistema desarrollado es cerrar ese desacople mediante la implementación de una infraestructura AIoT que recorra el modelo de punta a punta: desde la percepción de variables físicas hasta la **presentación en lenguaje natural** a los responsables del proceso, con capacidad de análisis autónomo en el Fog.

### **11.2  Mapeo al espacio paramétrico**

Se identificaron siete manejadores principales en el sistema. La tabla siguiente los caracteriza según las dimensiones del modelo:

|**Manejador**|**Nivel**|**Estadios cubiertos**|**Perfil vectorial**|
| :- | :- | :- | :- |
|**Instrumentación de campo**|Edge|Percepción|Cómputo mínimo · Latencia mínima|
|**Controladores locales**|Edge|Preprocesamiento|Cómputo bajo · Latencia mínima · Determinista|
|**Gateway multiprotocolo + OPC UA Server**|Fog|Transmisión · Procesamiento|Cómputo medio · Latencia baja|
|**Gemelo digital (MCP Server)**|Fog|Almacenamiento operativo · Procesamiento contextual|Cómputo medio-alto · Estado persistente local|
|**Agente orquestador**|Fog|Análisis local · Decisión autónoma|Cómputo alto · Capacidad de agencia|
|**Plataforma Cloud**|Cloud|Almacenamiento histórico · Procesamiento avanzado · Análisis global|Cómputo máximo · Latencia tolerada|
|**Interfaz conversacional**|Cloud / Fog|Presentación · Interacción en lenguaje natural|Dependiente del agente subyacente|

El manejador de mayor relevancia para la validación del modelo es el Agente orquestador, posicionado en el Fog. Su perfil vectorial lo distingue de todos los demás manejadores en ese nivel: no solo ejecuta estadios funcionales, sino que tiene capacidad de decisión autónoma sobre el proceso. Este manejador satisface, en el sistema concreto, la condición de capa cognitiva definida en el Capítulo 9: su comportamiento no puede describirse sin referencia al parámetro transversal de IA.

### **11.3  Cadena de integración: del dato físico a la decisión autónoma**

La integración de los manejadores produce una cadena continua que recorre el modelo desde el extremo Edge hasta el extremo Cloud. Su descripción en términos del eje funcional es la siguiente:

**Percepción.** La instrumentación de campo convierte variables físicas — temperatura, presión, caudal, estado de máquina, consumo eléctrico, parámetros de calidad — en señales digitales. Cada subsistema genera su propio conjunto de variables con protocolos y formatos heterogéneos.

**Preprocesamiento.** Los controladores locales realizan el primer nivel de tratamiento: validación de rango, filtrado de ruido, normalización de unidades. En esta etapa la información adquiere coherencia interna dentro de cada subsistema, pero persiste la heterogeneidad entre subsistemas.

**Transmisión y procesamiento semántico.** El gateway multiprotocolo es el manejador crítico del Fog en esta etapa. El Gateway implementa el estadio de Transmisión (desplazamiento intencional del dato entre niveles) recibiendo datos de los controladores locales en sus protocolos nativos, y el estadio de Procesamiento (normalización a semántica OPC UA) exponiéndolos como un OPC UA Server unificado. El manejo armónico de estos dos estadios funcionales se apoya firmemente sobre la transversal de Comunicación operando como infraestructura de conectividad de la planta. Esta estructuración dinámica constituye la resolución técnica del desacople entre protocolos que representa la principal fricción estructural del sistema preexistente.

**Almacenamiento operativo y gemelo digital.** El MCP Server implementa el gemelo digital del sistema: una representación en tiempo real del estado de todos los subsistemas, accesible como conjunto de herramientas para el agente orquestador. El gemelo no es un archivo estático: es una interfaz de consulta y acción sobre el estado actual e histórico del proceso.

**Análisis y decisión autónoma.** El agente orquestador consume el gemelo digital como contexto y opera sobre él con capacidad de razonamiento. Puede detectar condiciones anómalas, correlacionar eventos entre subsistemas, proponer o ejecutar acciones correctivas y generar alertas contextualizadas. Su autonomía es graduable: desde la notificación pura hasta la actuación directa sobre el proceso, según la configuración del sistema y el dominio de la decisión.

**Presentación.** La interfaz conversacional expone el estado del sistema y las conclusiones del agente en lenguaje natural. El receptor — operador, supervisor, directivo — interactúa con el sistema sin necesidad de interpretar datos crudos ni navegar dashboards. La interfaz conoce el proceso, el contexto operativo y el dominio de negocio, lo que hace que sus respuestas sean pertinentes y accionables en el contexto de quien las recibe.

### **11.4  Verificación de consistencia paramétrica**

La tabla siguiente completa la Ficha 2 del procedimiento de instanciación para el sistema TechPlast:

|**Nivel**|**Seguridad**|**IA**|**Consistencia**|
| :- | :- | :- | :- |
|**Edge**|Autenticación de dispositivo · Integridad del dato en origen|Lógica de preprocesamiento determinista|Satisfecha|
|**Fog**|Validación semántica · Control de acceso al gemelo · Aislamiento de red local|Agente orquestador con capacidad de decisión autónoma sobre el proceso|Satisfecha · Capa cognitiva emergente|
|**Cloud**|Encriptación en tránsito y en reposo · Gestión de identidades · Auditoría|Modelos de análisis avanzado · Mantenimiento predictivo · Optimización global|Satisfecha|

Las tres condiciones de consistencia del modelo se satisfacen en el sistema:

**Completitud funcional.** Los siete estadios del eje funcional tienen manejador asignado. No hay brechas funcionales.

**Consistencia vectorial.** Cada manejador opera en el nivel cuyo perfil vectorial satisface los requisitos de los estadios que implementa. La cadena OPC UA → MCP Server → Agente resuelve específicamente la inconsistencia del sistema preexistente, donde el poder de cómputo requerido para el análisis no estaba disponible en el nivel donde la latencia era tolerable.

**Transversalidad efectiva.** Seguridad e IA están presentes en los tres niveles con gradiente de peso apropiado para el dominio industrial. La emergencia de la capa cognitiva en el Fog — el agente orquestador — es consistente con la extensión del modelo descrita en el Capítulo 9: el parámetro transversal de IA converge con la capa en ese nodo.

El sistema TechPlast no es el único sistema que el modelo puede representar. Es una instancia del procedimiento general. Cualquier sistema AIoT cuyo diseño parta de los criterios de mapeo del Capítulo 10 producirá una descripción igualmente consistente, con manejadores distintos, perfiles vectoriales distintos y gradientes transversales distintos, pero estructurada por los mismos parámetros y verificada por los mismos criterios.

**Demostración empírica referencial.** La consistencia paramétrica se traduce en optimizaciones de hardware medibles al resolver la tensión estructural Cómputo-Latencia. Por ejemplo, en la instancia industrial subyacente, la **decisión de posicionamiento** de radicar la agencia autónoma en el Fog en lugar del Cloud permitió una **distribución de carga** altamente eficiente: logró comprimir una telemetría cruda sostenida de *~15.5 Mbps* a un flujo de apenas *~45 Kbps* hacia la nube, al tiempo que garantizó una **latencia** de lazo cerrado estricta en el Edge (*< 20 milisegundos*). *(Nota metodológica: El requerimiento de ancho de banda se computó midiendo la sumatoria de las tasas binarias nativas transmitidas en régimen continuo por el bus de campo primario, y contrastándola cuantitativamente con la tasa neta del Payload interpretado y transmitido hacia la plataforma en la nube por el agente Fog. La medición arrojó una reducción de flujo a través de red troncal equivalente a 99.7%).* Esta métrica constata las diferencias en la distribución de la carga de red y documenta numéricamente la ventaja operativa frente a esquemas de telemetría ininterrumpida hacia servicios centralizados.

### **11.5  Instanciación teórica referencial: Gestión Urbana (Smart City)**

Para validar la aplicabilidad del procedimiento de instanciación en un caso ajeno al dominio manufacturero, se presenta el mapeo de un sistema representativo de telemetría distribuida pública: **Una Plataforma Metropolitana de Control de Tráfico**.

**Manejadores identificados en la red:**
1. **Lidars y detectores inductivos:** (*Edge*) - Ejecutan el estadio de Percepción, digitalizando el estado físico de la calzada temporalmente en el origen.
2. **Controladores locales de intersección:** (*Edge*) - Ejecutan el Preprocesamiento acoplando variables discretas y regulando actuación con latencia menor a un segundo.
3. **Concentradores dinámicos zonales:** (*Fog*) - Operan como nodos intermedios abarcando los estadios de Transmisión, Procesamiento distribuido y Análisis técnico local. Actúan como una capa cognitiva delegada capaz de priorizar dinámicamente cruces para flujos de vehículos de emergencia, relevando a la red troncal de decisiones tácticas inmediatas.
4. **Data Warehouse Metropolitano:** (*Cloud*) - Alberga el Almacenamiento histórico principal de la ciudad y el Procesamiento asincrónico a gran escala.
5. **Dashboard Urbano Institucional:** (*Cloud*) - Ejecuta los ciclos de Análisis predictivo demográfico y de Presentación para operadores orgánicos.

A los efectos de formalizar el mapeo bajo el método del modelo, se ejecutan las plantillas obligatorias (fichas) asociando estos manejadores funcionales al espacio paramétrico tridimensional:

**Ficha 1  —  Asignación funcional (Smart City)**

|**Estadio funcional**|**Nivel asignado**|**Manejador responsable**|**Observaciones**|
| :- | :- | :- | :- |
|**Percepción**|Edge|Lidars y detectores inductivos|Muestreo de presencia en terreno|
|**Preprocesamiento**|Edge|Controladores de intersección|Filtrado base y control discreto local|
|**Transmisión**|Fog|Concentradores dinámicos zonales|Encapsulamiento estandarizado de telemetría zonal|
|**Almacenamiento**|Cloud|Data Warehouse Metropolitano|Persistencia central corporativa|
|**Procesamiento**|Fog / Cloud|Concentradores zonales / Data Warehouse|Adecuación semántica y formateo asincrónico|
|**Análisis**|Fog / Cloud|Concentradores zonales / Dashboard Urbano|Inferencia zonal inmediata vs inferencia analítica global|
|**Presentación**|Cloud|Dashboard Urbano Institucional|Reporte paramétrico asimilable para operadores humanos|

**Ficha 2  —  Verificación de transversalidad (Smart City)**

|**Nivel**|**Seguridad presente**|**IA presente**|**Brechas identificadas**|
| :- | :- | :- | :- |
|**Edge**|Criptografía básica y listados MAC en hardware|Algoritmos primarios de visión por computadora para conteo vehicular||
|**Fog**|Seguridad perimetral y validación por tokens de sesión|Optimización predictiva de flujo y priorización de corredor (Capa Cognitiva)||
|**Cloud**|Arquitectura ISO 27001 e infraestructura segmentada Zero Trust|Simulaciones multivariables para proyección de volumen de tráfico e inferencia vial global||

El caso práctico documentado cumple la condición de Completitud Funcional (siete estadios cubiertos en la red) y la de Transversalidad Efectiva (presencia auditada de IA y Seguridad cruzados por nivel), demostrando sistemáticamente la aplicabilidad y flexibilidad del formato normativo sobre infraestructuras de escalas ajenas a entornos cerrados.
