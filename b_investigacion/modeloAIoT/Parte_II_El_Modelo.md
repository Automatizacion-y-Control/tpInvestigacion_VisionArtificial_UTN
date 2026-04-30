**PARTE II**

**El Modelo**

*¿Cómo se estructura una infraestructura que gestiona información en sistemas AIoT?*
## **Capítulo 3  —  Definición del espacio paramétrico**

El modelo propuesto describe una infraestructura como un espacio definido por parámetros. Un parámetro es una magnitud que caracteriza el comportamiento del sistema respecto de la información en un punto o región del espacio. No todos los parámetros tienen el mismo tipo de relación con ese espacio: algunos tienen dirección y sentido a lo largo de un eje, otros lo atraviesan en su totalidad. Esta distinción es la base de la clasificación que se introduce a continuación.

### **3.1  Clasificación de parámetros: vectoriales y transversales**

**Parámetro vectorial.** *Parámetro que presenta una variación tendencial a lo largo del eje Edge–Fog–Cloud, con dirección y sentido definidos. Su valor en cualquier punto del eje es función de la posición en ese eje.*

**Parámetro transversal.** *Parámetro cuya validez se extiende al sistema completo, independientemente de su implementación específica en cada nodo. No varía por posición en el eje vertical, sino que tiene su propia dinámica de variación según el dominio de aplicación y la naturaleza del sistema. Actúa de forma ortogonal al eje principal.*

La distinción no es meramente clasificatoria. Tiene consecuencias directas sobre el diseño de la infraestructura: un parámetro vectorial define restricciones de posicionamiento — dónde debe ocurrir cada operación sobre la información —; un parámetro transversal define restricciones de consistencia — qué propiedades debe mantener la información en cualquier punto del sistema.

### **3.2  Propiedades formales: dirección, sentido y transversalidad**

**Dirección.** Un parámetro tiene dirección cuando su variación está asociada al eje Edge–Fog–Cloud. La dirección indica que el parámetro es sensible a la posición en ese eje.

**Sentido.** Un parámetro tiene sentido cuando puede determinarse si crece o decrece al desplazarse desde el Edge hacia el Cloud. Dos parámetros pueden compartir dirección pero tener sentidos opuestos.

**Transversalidad.** Un parámetro es transversal cuando su presencia no está condicionada a ninguna capa en particular. Es una propiedad del sistema en su totalidad, no de un nivel específico. Un parámetro transversal no puede ser asignado a una capa: debe ser atendido en todas.

Estas propiedades se distinguen conceptualmente como categorías diferenciadas, aunque pueden interactuar en la implementación del sistema.

### **3.3  Definiciones operacionales**

El modelo base identifica parámetros que configuran sus dimensiones. De ellos, dos son **vectoriales** y estructuran el espacio físico-lógico. Otros operan de forma ortogonal bajo el régimen de **transversales estrictos** (infraestructura, de presencia obligatoria en todo nodo) y **transversales ontológicos** (cognición, de cobertura variable). Finalmente, una secuencia progresiva conforma el eje funcional, que de manera lógica se abordará en el Capítulo 6. A continuación, se enuncia cada parámetro con su definición operacional:

**Poder de cómputo.** *Capacidad del nodo para ejecutar operaciones sobre la información por unidad de tiempo. Parámetro vectorial. Crece desde el Edge hacia el Cloud.*

**Latencia.** *Tiempo transcurrido entre la generación de un dato y su disponibilidad en el punto de uso. Parámetro vectorial. Decrece desde el Cloud hacia el Edge.*

**Seguridad.** *Conjunto de propiedades que garantizan la confidencialidad, integridad y disponibilidad de la información en cualquier punto del sistema. Parámetro transversal estricto.*

**Comunicación.** *Capacidad de interconexión e interoperabilidad entre todos los componentes y nodos internos. Es la infraestructura de flujo que permite la existencia del sistema distribuido. Parámetro transversal estricto.*

**Inteligencia Artificial.** *Capacidad del sistema para inferir, clasificar, predecir o decidir sobre la información sin instrucción explícita para cada caso. Parámetro transversal ontológico (presencia estructural con cobertura efectiva variable).*

**Nota:** El eje funcional —Percepción, Preprocesamiento, Transmisión, Almacenamiento, Procesamiento, Análisis y Presentación— constituye el flujo secuencial operativo del modelo. Por su relación con los estadios funcionales del ciclo de vida de la información, se trata en capítulo separado.

### **3.4  Definición operacional de capa computacional**

El modelo utiliza el concepto de "capa" como entidad estructural intermedia que agrupa nodos. Se define capa como una región del eje vertical cuyos nodos comparten un rango de perfil vectorial suficientemente homogéneo como para ser tratados como una categoría de diseño. Una capa se distingue de las adyacentes cuando la diferencia de perfil vectorial entre nodos de capas distintas es significativamente mayor que la diferencia entre nodos de la misma capa.

Esta agrupación permite responder axiomáticamente al requerimiento topológico del sistema. La pregunta **¿Dónde?** interroga la ubicación del proceso en el eje Edge–Fog–Cloud. Su respuesta está condicionada por dos parámetros vectoriales:

* **Poder de cómputo**: Capacidad de transformación disponible en el nodo.
* **Latencia de respuesta**: Velocidad de interacción del sistema con su entorno físico, distinta de la latencia de tránsito de datos.

La distinción en tres capas discretas (Edge, Fog, Cloud) constituye la partición más frecuente del eje vertical bajo las condiciones tecnológicas actuales. En este eje, el **Cloud** se define no solo por su potencia máxima, sino por su alcance de conectividad global. Es el nivel que habilita la transición de un sistema local a uno de escala global, cumpliendo con la visión de infraestructura del modelo. Independientemente de esta partición típica, el modelo admite granularidades distintas o el desvanecimiento de sus fronteras, escenario que el Capítulo 8 de la Parte III examina formalmente al tratar la atomización de los nodos.

## **Capítulo 4  —  Parámetros vectoriales**

Los parámetros vectoriales son los que articulan la dimensión vertical del modelo. Su comportamiento a lo largo del eje Edge–Fog–Cloud determina qué operaciones sobre la información son posibles —o convenientes— en cada nivel, y cuál es el costo de realizarlas en un nivel incorrecto.

### **4.1  Poder de cómputo: gradiente Edge–Cloud**

El poder de cómputo es la capacidad del nodo para ejecutar transformaciones sobre la información. En el extremo Edge, esta capacidad está condicionada por las restricciones del hardware que opera próximo al origen del dato: consumo energético acotado, tamaño físico reducido, costo unitario bajo, operación frecuentemente autónoma. En el extremo Cloud, estas restricciones desaparecen: el hardware es centralizado, escalable y dedicado al procesamiento.

Los parámetros vectoriales se comportan como gradientes estructurales del sistema, en los cuales el poder de cómputo tiende a incrementarse desde el Edge hacia el Cloud, mientras que la latencia tiende a incrementarse en sentido inverso, sin que estas relaciones constituyan invariantes estrictos en todas las implementaciones. El Fog suele ocupar la posición intermedia en arquitecturas típicas, con un rango de variación amplio según la implementación concreta del nodo.

Esta tendencia estructural tiene una consecuencia directa sobre el diseño: las operaciones que demandan mayor capacidad computacional —modelos de inferencia complejos, análisis histórico, entrenamiento— suelen posicionarse hacia el Cloud. Las operaciones que requieren poco cómputo pero alta velocidad de reacción tienden a posicionarse hacia el Edge. El Fog absorbe con frecuencia las operaciones de complejidad media.

### **4.2  Latencia: gradiente Cloud–Edge**

La latencia es el tiempo que transcurre entre la generación de un dato en el origen y su disponibilidad en el punto donde debe ser procesado o utilizado. Este parámetro tiene sentido inverso al del poder de cómputo: es mínima en el Edge —donde el punto de uso y el punto de origen son el mismo o están físicamente próximos— y máxima en el Cloud, donde la información debe recorrer la red de transporte completa antes de ser procesada.

La latencia no es simplemente un tiempo de transmisión. Es la suma de la latencia de red, la latencia de procesamiento en cada nodo intermedio y la latencia de almacenamiento cuando existe buffering. En el Edge puro, todos estos componentes tienden a cero. En el Cloud, cada componente acumula contribuciones a lo largo de toda la cadena.

El modelo identifica una tensión estructural entre poder de cómputo y latencia, donde la optimización de uno de estos parámetros suele implicar compromisos sobre el otro, dependiendo de la arquitectura adoptada. Esta tensión es la razón principal de existencia de distribuciones en múltiples capas y el problema central que el diseño de una infraestructura AIoT debe resolver para cada sistema concreto.

### **4.3  Relaciones y restricciones entre parámetros vectoriales**

Los dos parámetros vectoriales no son independientes: están ligados por la arquitectura física de cualquier sistema distribuido. Esta relación impone restricciones de diseño que el modelo hace explícitas.

**Restricción de posicionamiento.** Toda operación sobre la información tiene un perfil de requerimientos definido por dos valores: la capacidad mínima de cómputo que necesita y la latencia máxima que tolera. El modelo prescribe que esa operación debe ejecutarse en el nivel donde ambas condiciones se satisfacen simultáneamente. Si no existe tal nivel, la operación debe descomponerse.

**Condición de propagación.** En arquitecturas que incorporan una capa intermedia, la información puede ser procesada o agregada en el Fog antes de alcanzar el Cloud, sin que esto constituya una condición necesaria en todos los sistemas. El diseño del Fog frecuente determina en qué estado llega la información al Cloud, y por tanto la calidad del procesamiento que allí puede realizarse.

**Punto de equilibrio.** Para cada sistema existe un punto en el eje Edge–Cloud donde la suma ponderada de los costos asociados a la latencia y al poder de cómputo insuficiente es mínima. Este punto no es único ni fijo: varía según el tipo de operación, el volumen de datos y los requisitos de respuesta. El modelo no prescribe un punto de equilibrio universal; prescribe el método para encontrarlo en cada caso.

## **Capítulo 5  —  Dimensión Transversal: Infraestructura y Cognición**

Los parámetros abarcados en este eje responden a la pregunta axiomática del modelo: **¿Cómo?**. Operan ortogonalmente al gradiente vectorial garantizando las propiedades operativas de la infraestructura y la autonomía de la agencia. 

Para eliminar ambigüedades lógicas, el modelo introduce una distinción formal de nivel conceptual entre sus capacidades transversales:
- **Transversalidad estricta:** Parámetros de infraestructura cuya ausencia en cualquier nodo implica la falla estructural o aislamiento del sistema (Seguridad y Comunicación). Tienen presencia obligatoria en todos los nodos.
- **Transversalidad ontológica:** Parámetros de cognición que definen la naturaleza de pertenencia del sistema AIoT, pero cuya implementación efectiva o cobertura presenta distribución variable (Inteligencia Artificial).

Cada uno tiene su propio leitmotiv — su lógica interna y sus implicaciones de diseño — independiente del nivel o hardware topológico donde opere.

### **5.1  Seguridad**

**Naturaleza.** La seguridad es la propiedad que garantiza que la información conserva sus atributos esenciales —confidencialidad, integridad y disponibilidad— a lo largo de todo su ciclo de vida en el sistema. Estos tres atributos son indivisibles: una infraestructura que protege la confidencialidad pero no garantiza la integridad no es segura.

**Transversalidad efectiva.** La seguridad no puede ser delegada a una sola capa. Una cadena es tan segura como su eslabón más débil: si el nodo Edge no autentica el origen del dato, toda la información que fluye hacia el Cloud es potencialmente inválida, independientemente de los controles que existan en niveles superiores. La seguridad debe ser atendida en cada nodo, en cada canal de comunicación y en cada operación de almacenamiento.

**Gradiente de peso por dominio.** Aunque la seguridad es transversal, su peso relativo en cada capa varía según el dominio de aplicación. En sistemas donde el dato individual es sensible —salud, finanzas, infraestructura crítica— la capa Edge tiene un peso de seguridad alto porque el dato nace allí y una vulnerabilidad en ese punto compromete todo el sistema. En sistemas donde la información agregada es más valiosa que el dato individual, el peso se desplaza hacia el Cloud. El modelo no prescribe un gradiente universal: prescribe que el gradiente debe ser definido explícitamente para cada sistema.

**Leitmotiv.** El leitmotiv de la seguridad es la *confianza en la cadena*. Cada operación sobre la información supone que la información recibida es auténtica, íntegra y proviene de una fuente autorizada. Cuando esta suposición no puede sostenerse en algún punto, el sistema debe reaccionar: detener el flujo, alertar o degradar graciosamente.

### **5.2 Comunicación**

**Naturaleza.** La comunicación es la capacidad que entrelaza y conecta internamente a todos los componentes del sistema. Es la ruta de interconexión tecnológica por donde transitan los flujos informacionales garantizando la disponibilidad sistémica y la interoperabilidad, sea por medios cableados o inalámbricos.

**Transversalidad efectiva.** Así como la seguridad protege a la cadena, la comunicación permite que la cadena exista. Un componente totalmente aislado carece de significado dentro de este modelo de infraestructura global. Es un parámetro estricto porque, sin conectividad hacia algún vector del ecosistema, el AIoT pierde sustancia tecnológica.

**Leitmotiv.** Su premisa es la *fluidez del conducto* o *interoperabilidad del conjunto*, asegurando que la infraestructura siempre disponga de carriles adecuados para el constante tráfico de los datos. No debe confundirse con la *Transmisión*, la cual es un estadio operativo funcional orientado a transportar un dato de un nivel A hacia un punto B.

### **5.3  Inteligencia Artificial**

**Naturaleza.** La Inteligencia Artificial, en el contexto de este modelo, se define operacionalmente como el estudio y despliegue de **agentes computacionales** que operan sobre la información de forma autónoma: inferir estados no observados, clasificar condiciones, predecir comportamientos o tomar decisiones sin instrucción explícita. Es una propiedad ontológica del comportamiento integral de la infraestructura.

*(Nota metodológica: El término "ontológico" se utiliza a lo largo de este modelo en su acepción de ingeniería de sistemas, en donde refiere a la naturaleza constitutiva del sistema: qué es un sistema AIoT versus qué es un sistema pasivo IoT. No asume una postura filosófica fundacional sobre la naturaleza de la realidad. Se establece que la IA es ontológica en el sentido estricto de que su presencia o ausencia cambia la categoría identitaria del sistema general, no meramente su rendimiento o precisión funcional).*

**Transversalidad ontológica vs Cobertura efectiva.** La IA es transversal en términos ontológicos ya que define la capacidad del sistema AIoT para operar sobre la información con agencia. Sin embargo, a diferencia de los transversales estrictos, su implementación efectiva no es homogénea a lo largo del espacio paramétrico (cobertura variable). NO necesita estar embebida dentro de cada sensor periférico. Para que un sistema sea considerado AIoT, debe existir capacidad de agencia en al menos un nivel del sistema, sin requerir su presencia homogénea en todos los nodos.

**Agenciamiento distribuido.** La autonomía existe en diferentes escalas según donde se posicione la IA. En el nodo más próximo al origen (Edge AI), es rápida y localizada: detectar una anomalía industrial y tomar una acción inmediata. En las nubes de consolidación o nodos integrales (Fog/Cloud), la autonomía es sistémica y estructurada: descubrir variables complejas o generar conocimiento cruzado con gran exigencia de cómputo.

**Leitmotiv.** El leitmotiv de la IA es la *reducción de la dependencia de la síntesis humana*. En ausencia de IA, el ciclo de la información requiere que un agente humano interprete el estado del sistema y decida la acción. La IA cierra ese ciclo dotando de cognición funcional al ambiente.

### **5.4  Interdependencia y el abordaje de ejes**

La noción de leitmotiv no es retórica. Es la descripción de la lógica interna que gobierna el comportamiento de los parámetros del eje "¿Cómo?". Conocerlos permite al diseñador vislumbrar las consecuencias secundarias de sus decisiones arquitectónicas. 

Por ejemplo, una decisión de diseño enfocada estructuralmente a mitigar costos mediante la restricción del poder de cómputo asignado a un nodo Fog compromete de forma directa al parámetro vectorial, generando externalidades sistémicas ineludibles: restringe la envergadura de la Agencia (IA) que puede operar in situ y debilita la solidez criptográfica (Seguridad) al imponer cuellos de botella subyacentes sobre sus procedimientos de verificación y confianza de red. 

Esto refuerza la **Dualidad Analítica del Modelo**. El diseño de la infraestructura o la validación funcional de un componente particular no puede estudiarse en hardware aislado; exige una interrogación simultánea y entrelazada a partir de tres preguntas rectoras (Dónde opera, Cómo garantiza las normas y autonomía, y Para Qué estadio fue creado).

## **Capítulo 6  —  El eje funcional de la información**

Los parámetros vectoriales y transversales describen las propiedades del espacio en que opera la infraestructura. El eje funcional describe el recorrido que realiza la información dentro de ese espacio: los estadios por los que atraviesa desde su origen hasta su destino final.

Este eje no es paralelo al eje Edge–Cloud ni es ortogonal a él en sentido estricto. Es una secuencia ordenada de operaciones que se distribuye de forma natural a lo largo del espacio paramétrico, con cada estadio tendiendo a ejecutarse en el nivel cuyo perfil vectorial mejor se adecua a sus requisitos.

**Distinción Estructural:** La comunicación no forma parte del eje funcional de la información, sino que constituye la condición estructural que habilita la interconexión entre nodos, mientras que la transmisión pertenece al dominio funcional y describe el desplazamiento operativo de unidades informacionales.

### **6.1  Los siete estadios del ciclo de vida de la información**

**Percepción.** *Conversión de una variable del mundo físico o digital en una representación simbólica procesable por el sistema. Es el punto de entrada de la información al modelo. Opera sobre datos, no sobre información.*

**Preprocesamiento.** *Conjunto de operaciones que transforman el dato crudo en una forma adecuada para su transmisión y uso posterior: filtrado de ruido, normalización, validación de rango, compresión. El preprocesamiento no agrega significado; elimina lo que lo obstaculiza.*

**Transmisión.** *Acción funcional e intencional de desplazar la representación del dato procesado entre los diversos eslabones, estadios y capas topológicas para completar su ciclo. Da un sentido dinámico al flujo informacional valiéndose de la Comunicación.*

**Almacenamiento.** *Persistencia de la información en un soporte que permite su recuperación posterior. El almacenamiento puede ser volátil —para operación en tiempo real— o persistente —para análisis histórico y generación de conocimiento.*

**Procesamiento.** *Aplicación de operaciones de transformación sobre la información almacenada o en tránsito, con el objeto de extraer propiedades, correlaciones o estados que no eran directamente observables en el dato original.*

**Análisis.** *Interpretación de los resultados del procesamiento en el contexto del sistema y su dominio de aplicación. El análisis produce conocimiento operativo: inferencias, predicciones, diagnósticos o prescripciones sobre el estado o el comportamiento del sistema.*

**Presentación.** *Entrega del conocimiento producido al agente —humano o autónomo— que debe actuar sobre él. La presentación no es un paso pasivo: determina si el conocimiento es accesible, interpretable y accionable en el tiempo requerido.*

### **6.2  Distribución natural de los estadios en el espacio paramétrico**

Cada estadio del eje funcional tiene un perfil de requerimientos expresable en términos de los parámetros vectoriales: cuánto poder de cómputo necesita y cuánta latencia tolera. Este perfil determina en qué región del eje Edge–Cloud el estadio se ejecuta con mayor eficiencia.

La Percepción y el Preprocesamiento requieren **mínimo poder de cómputo y mínima latencia**: ocurren naturalmente en el Edge. La Transmisión es el estadio de transporte intermedio: no posee asiento o posición estática propia en un nodo, puesto que materializa el salto espacial entre niveles apoyándose sobre la infraestructura de conectividad. El Almacenamiento es dual: su forma volátil vive en el Edge y el Fog; su forma persistente vive en el Cloud. El Procesamiento y el Análisis requieren mayor poder de cómputo y toleran mayor latencia: gravitan hacia el Fog y el Cloud según la complejidad del modelo. La Presentación tiene una posición determinada por el agente receptor: si el receptor es humano en un sistema centralizado, la presentación vive en el Cloud; si el receptor es autónomo o local, vive en el Fog o el Edge.

Esta distribución no es una prescripción rígida. Es la tendencia natural que emerge de aplicar los parámetros vectoriales a los requisitos funcionales de cada estadio. En sistemas concretos, las restricciones de conectividad, costo o seguridad pueden desplazar un estadio de su posición natural — y el modelo permite formalizar ese desplazamiento y evaluar su costo.

La secuencia de los siete estadios es invariante: la información no puede ser analizada antes de ser procesada, ni procesada antes de ser almacenada o recibida. Sin embargo, los estadios no están necesariamente separados por fronteras físicas entre capas: en un nodo de capacidad suficiente, varios estadios pueden ejecutarse en el mismo hardware. La secuencia es lógica; la distribución física es una decisión de diseño.

## **Capítulo 7  —  El modelo completo**

Los capítulos anteriores han definido los componentes del modelo de forma independiente: el eje Edge–Cloud con sus parámetros vectoriales, los parámetros transversales con sus leitmotivs, y el eje funcional con sus siete estadios. Este capítulo integra esos componentes en un modelo único y describe las propiedades que emergen de esa integración.

### **7.1  Integración de los tres ejes**

El presente modelo no se postula como una taxonomía rígida de componentes, sino como un **marco de trabajo (framework) de gestión informacional**. Su validez reside en la capacidad del arquitecto para interrogar la infraestructura a través de tres ejes ortogonales. Estos ejes no son compartimentos estáticos; son modos de abstracción que evolucionan con la madurez del sistema.

Bajo una perspectiva de análisis tecnológico crítico, el modelo reconoce que el diseño de sistemas AIoT hoy exige una distinción clara entre la **función** (el dato transformado), la **capacidad** (la propiedad del flujo) y la **estrategia** (la posición del cómputo). Así, este modelo se interroga mediante tres preguntas ortogonales: ¿Dónde? (topología del continuum), ¿Cómo? (capacidades transversales) y ¿Para Qué? (finalidad funcional).

El modelo completo es un espacio tridimensional en el que cualquier operación sobre la información puede posicionarse:

**Eje vertical Edge–Cloud (¿Dónde?):** define el nivel computacional en que opera la infraestructura. Sus parámetros vectoriales — poder de cómputo y latencia — determinan qué es posible en cada punto.

**Eje de Capacidades u Ortogonal (¿Cómo?):** Integrado por Infraestructura (Seguridad y Comunicación) y Cognición (IA). Define las condiciones operativas y las garantías técnicas y de agencia activa que dotan a la infraestructura de existencia propia.

**Eje Funcional (¿Para Qué?):** Constituido por la sucesión lógica de los siete estadios, desde la Percepción hasta la Presentación del reporte de valor. Define la causa operativa para la cual se desplazan los datos a través del espacio paramétrico vectorial.

La integración de los tres ejes produce un mapa completo de la infraestructura: dado un sistema, es posible ubicar cada componente, cada operación y cada flujo de información en el espacio, verificar que los parámetros vectoriales son satisfechos, y comprobar que los parámetros transversales son atendidos en cada nodo.

### **7.2  Propiedades emergentes del modelo integrado**

**Completitud funcional.** Un sistema AIoT es funcionalmente completo cuando los siete estadios del eje funcional están cubiertos en algún punto del eje vertical. La ausencia de cualquier estadio no es una limitación de implementación: es una brecha en el modelo que genera consecuencias predecibles en la calidad de la información disponible para la toma de decisiones.

**Consistencia paramétrica.** Un sistema es consistente cuando las operaciones de cada estadio están posicionadas en el nivel cuyo perfil vectorial satisface sus requisitos. Un sistema inconsistente no falla necesariamente, pero opera con un costo innecesario: procesamiento que podría hacerse cerca del dato se hace lejos, o información que requiere baja latencia espera en la cola del Cloud.

**Dualidad Analítica.** El modelo exige que la evaluación de cualquier componente sea simultánea en los tres ejes; un análisis parcial sobre un solo eje produce una descripción incompleta del sistema. Un mismo manejador (ej. un Gateway en el Fog) debe ser analizado desde su posición (**Dónde**), su capacidad de protocolos y agencia (**Cómo**) y su estadio funcional de normalización (**Para Qué**).

**Garantía de Cohabitación.** La Garantía de Cohabitación es la propiedad del sistema completo que certifica su identidad como AIoT. Esta propiedad se satisface mediante una condición doble, necesaria y suficiente: la presencia de las transversales estrictas (Seguridad y Comunicación) aseguradas uniformemente en todos los nodos de la infraestructura, sumado a la presencia de la transversal ontológica (Inteligencia Artificial) operando en al menos un nivel. Resulta capital distinguirla de la *Transversalidad Efectiva*: mientras que la Transversalidad Efectiva opera como un criterio de verificación evaluado nivel a nivel, la Garantía de Cohabitación es una propiedad emergente y unificadora del sistema en su totalidad.

### **7.3  Capacidad prescriptiva: mapeo de un sistema arbitrario al modelo**

Una de las propiedades centrales del modelo es su capacidad prescriptiva: dado un sistema AIoT arbitrario, el modelo provee el método para evaluarlo y, si es necesario, corregirlo.

El procedimiento de mapeo consiste en identificar, para cada componente del sistema, qué estadio del eje funcional implementa, en qué nivel del eje vertical opera, y si los parámetros transversales están presentes con el peso adecuado. El resultado es una representación del sistema en el espacio del modelo que hace visibles tanto las consistencias como las brechas.

El modelo es tecnológicamente agnóstico en términos de implementación, aunque se apoya en una abstracción del espacio computacional basada en arquitecturas distribuidas. Cualquier sistema que gestione información de forma distribuida puede ser mapeado al modelo bajo estas condiciones. Los sistemas que no pueden ser mapeados — porque no tienen eje vertical reconocible, o porque no tienen un eje funcional identificable — habitualmente no se encuadran como sistemas AIoT en el sentido del presente modelo.

### **7.4  El continuum hacia la computación ubicua como caso límite**

El modelo describe una infraestructura con tres capas distinguibles: Edge, Fog y Cloud. Esta distinción es válida mientras los nodos tengan perfiles vectoriales suficientemente diferenciados como para ser tratados como categorías separadas.

A medida que la capacidad de cómputo de los nodos crece y su tamaño físico disminuye, los perfiles vectoriales de los niveles tienden a converger. El Edge gana poder de cómputo; el Cloud gana proximidad a través de infraestructura distribuida; el Fog se multiplica y se vuelve omnipresente. En el límite, la distinción entre capas se disuelve: el cómputo está disponible en cualquier punto del sistema con latencia tendiente a cero y poder de cómputo tendiente a ilimitado.

Este estado límite es la **computación ubicua**: la infraestructura desaparece como objeto de diseño porque está en todas partes. El modelo no deja de ser válido en este límite; sus ejes siguen existiendo. Lo que cambia es que la restricción de posicionamiento — la necesidad de elegir en qué capa ejecutar cada operación — pierde relevancia como criterio dominante de diseño. El eje funcional y los parámetros transversales permanecen.

Este caso límite no es una predicción sobre el estado futuro del arte. Es la descripción formal del punto de convergencia al que tiende el eje vertical del modelo cuando sus parámetros vectoriales se igualan en todos los nodos. Su valor es conceptual: define el horizonte del espacio de diseño y permite situar cualquier sistema concreto en relación a ese horizonte.
