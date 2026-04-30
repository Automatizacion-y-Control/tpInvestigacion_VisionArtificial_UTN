**PARTE I**

**Fundamentos**

*¿Sobre qué entidad opera esta infraestructura?*
## **Capítulo 1  —  La información como objeto de ingeniería**

### **1.1  Dato, información y conocimiento: distinción operacional**

En la práctica de la ingeniería de sistemas automatizados, los términos dato, información y conocimiento se usan con frecuencia como sinónimos. Esta ambigüedad no es inocua: conduce a decisiones arquitectónicas incorrectas, porque cada uno de estos conceptos tiene propiedades distintas que determinan cómo debe ser tratado, transportado y almacenado.

Se adoptan aquí las siguientes definiciones operacionales, construidas sobre la base de la teoría de la información de Shannon (1948) y extendidas al dominio de sistemas de control y automatización:

**Dato.** *Representación simbólica de una variable del mundo físico, sin interpretación asociada. Un dato tiene valor de señal pero no de significado. Ejemplo: el valor 73.4 emitido por un sensor de temperatura.*

**Información.** *Dato al que se ha asociado contexto suficiente para reducir incertidumbre en un receptor definido. Siguiendo a Shannon, la información es inversamente proporcional a la probabilidad del evento que describe: un dato predecible aporta poca información; un dato inesperado, mucha. Ejemplo: 73.4 °C en el tanque de enfriamiento cuando el rango operativo es 15–25 °C constituye información de alarma.*

**Conocimiento.** *Información integrada en un modelo que permite inferir estados no observados directamente o anticipar comportamientos futuros. El conocimiento es el producto de procesar información en el tiempo. Ejemplo: la correlación histórica entre temperatura del tanque y tasa de falla de las inyectoras constituye conocimiento operativo.*

Esta distinción no es filosófica sino **estructural**: el dato puede vivir en el Edge con recursos mínimos; la información requiere contexto y por tanto capacidad de preprocesamiento; el conocimiento requiere persistencia histórica y poder de cómputo. La arquitectura de un sistema AIoT debe reflejar esta jerarquía.

**Nota:** La definición de información adoptada es compatible con la formulación matemática de Shannon (H = −Σ pᵢ log₂ pᵢ) y con su interpretación semántica en el marco de Floridi (2005), quien define información como dato bien formado, con significado y verídico. Ambas perspectivas son consistentes con el uso que se hace del término a lo largo de este trabajo.

### **1.2  La información como recurso de gestión en sistemas automatizados**

La automatización industrial ha evolucionado en dos etapas distinguibles. En la primera, el objetivo era controlar variables físicas: temperatura, presión, caudal, posición. Los sistemas de control clásico —PID, lógica de relés, PLC— fueron diseñados con ese propósito y lo cumplen con excelencia. La información era un subproducto del control, no su objeto.

En la segunda etapa, impulsada por la conectividad y la reducción de costos de sensado y cómputo, el volumen de datos generados por los sistemas de control superó la capacidad de síntesis humana. Un operador puede interpretar diez variables en pantalla; no puede interpretar diez mil. En este punto la información deja de ser subproducto y se convierte en recurso crítico de gestión, con las mismas propiedades que cualquier otro recurso industrial: puede ser producida, transportada, almacenada, procesada, degradada y consumida.

Tratar la información como recurso implica que su gestión debe ser **automatizada**. Del mismo modo que un sistema de control automatiza la gestión de variables físicas, un sistema AIoT automatiza la gestión de la información que esas variables generan. Este es el dominio de problema que el presente modelo aborda.

### **1.3  Condiciones para que la información sea útil**

No toda información es útil en el contexto de un sistema automatizado. Para que lo sea, deben satisfacerse simultáneamente tres condiciones:

**Oportunidad.** La información debe estar disponible en el momento en que puede influir en una decisión. Información correcta entregada fuera de tiempo es, operativamente, equivalente a ausencia de información. Esta condición impone restricciones directas sobre la latencia del sistema.

**Pertinencia.** La información debe estar referida a la variable o estado que es relevante para la decisión a tomar. Esta condición impone restricciones sobre el preprocesamiento: un sistema que transporta todo dato sin filtrar hacia el nivel de decisión degrada la pertinencia por saturación.

**Confiabilidad.** La información debe representar fielmente el estado del sistema físico. Esta condición impone restricciones sobre la integridad de la cadena de adquisición, transmisión y almacenamiento, e introduce la seguridad como dimensión transversal ineludible.

Estas tres condiciones no son independientes entre sí ni son igualmente exigentes en todos los puntos de la infraestructura. Su distribución a lo largo de las capas computacionales es uno de los problemas que el modelo propuesto en la Parte II permite formalizar.

## **Capítulo 2  —  Modelos telecomputacionales existentes**

Se denominan modelos telecomputacionales a los paradigmas de distribución del cómputo a lo largo de una red, en función de la proximidad al origen del dato y de la capacidad de procesamiento disponible. Los tres modelos consolidados en la industria son Edge Computing, Fog Computing y Cloud Computing. Se describen a continuación de forma comparativa, con énfasis en su relación con la información como recurso.

### **2.1  Edge Computing**

**Definición.** Paradigma en el que el cómputo se ejecuta en el nodo más próximo al origen del dato, típicamente en el dispositivo sensor o en un controlador local de recursos limitados.

**Características determinantes.** Latencia mínima, ya que la distancia física y lógica entre el origen del dato y el punto de procesamiento es mínima. Poder de cómputo reducido, condicionado por restricciones de consumo energético, costo y tamaño físico del hardware embebido. Almacenamiento volátil o de capacidad muy limitada. Operación determinista, requisito en aplicaciones de control en tiempo real.

**Rol en la cadena de la información.** El Edge es el punto de percepción y preprocesamiento inicial. Transforma señales físicas en datos digitales y aplica el primer nivel de filtrado para reducir ruido y volumen antes de la transmisión. Es el umbral entre el mundo físico y el sistema informacional.

**Limitación principal.** Su capacidad de cómputo no permite ejecutar modelos de análisis complejos ni mantener contexto histórico. Las decisiones que toma son necesariamente locales y reactivas.

### **2.2  Fog Computing**

**Definición.** Paradigma introducido por Cisco (2012) que extiende los servicios de cómputo hacia la red intermedia, entre los dispositivos Edge y el Cloud. El nodo Fog es un recurso computacional de capacidad media, geográficamente distribuido y lógicamente próximo al Edge.

**Características determinantes.** Latencia intermedia, mayor que el Edge pero sustancialmente menor que el Cloud. Poder de cómputo moderado, suficiente para normalización de datos de múltiples fuentes, ejecución de lógica de control ante pérdida de conectividad con el Cloud, y modelos de inferencia de complejidad media. Capacidad de almacenamiento temporal.

**Rol en la cadena de la información.** El Fog actúa como capa de integración y acoplamiento. Recibe datos de múltiples nodos Edge con protocolos heterogéneos, los normaliza a una representación semántica común, y los entrega al Cloud en forma contextualizada. Es también el nivel donde se puede ejecutar lógica de autonomía local cuando la conectividad con el Cloud se interrumpe.

**Limitación principal.** Es el paradigma menos adoptado de los tres, en parte por la ausencia histórica de estándares de interoperabilidad consolidados entre Edge y Cloud. Esta brecha de integración es central en el problema que aborda el presente trabajo.

### **2.3  Cloud Computing**

**Definición.** Paradigma de provisión de recursos computacionales —cómputo, almacenamiento, red— como servicio remoto bajo demanda, sobre infraestructura centralizada de alta disponibilidad (NIST SP 800-145, 2011).

**Características determinantes.** Poder de cómputo máximo, virtualmente ilimitado bajo esquemas de escalado elástico. Latencia alta respecto al Edge, determinada por la distancia física a los centros de datos y por la red de transporte. Almacenamiento persistente de gran capacidad. Disponibilidad de modelos de IA de alta complejidad y herramientas de análisis avanzado.

**Rol en la cadena de la información.** El Cloud es el centro de inteligencia global del sistema. Gestiona la persistencia del historial de datos, ejecuta los modelos analíticos de mayor complejidad, aloja las aplicaciones de negocio y produce la presentación de resultados para la toma de decisiones. Es el nivel donde la información se convierte en conocimiento operativo.

**Limitación principal.** Su latencia lo excluye de aplicaciones que requieren respuesta en tiempo real. No puede ser el único nivel de procesamiento en sistemas donde la conectividad es intermitente o donde la seguridad exige que ciertos datos no abandonen el perímetro local.

### **2.4  Análisis comparativo y estado del arte**

Los tres modelos son complementarios por diseño. Sus parámetros más relevantes — poder de cómputo y latencia — varían en sentidos opuestos a lo largo del continuum Edge–Fog–Cloud, lo que los hace naturalmente adecuados para distintas etapas del ciclo de vida de la información.

La literatura especializada reconoce esta complementariedad y propone arquitecturas de tres capas que los integran (Cisco, 2012; OpenFog Consortium, 2017; ETSI MEC, 2022). Sin embargo, estas propuestas abordan el problema desde la perspectiva de la optimización de recursos computacionales — latencia, energía, costo de transferencia — y no desde la perspectiva de la información como recurso a gestionar de forma integral.

La ausencia de un modelo que formalice **cómo fluye y se transforma la información** a través de estas tres capas, con sus parámetros de calidad asociados, es la brecha que el presente trabajo propone cubrir. Los modelos existentes describen dónde se computa; el modelo propuesto describe **qué le ocurre a la información** en cada punto de esa computación.

**Nota:** Las referencias citadas en esta sección corresponden a documentos fundacionales de cada paradigma. Se listan completas en la sección de Referencias al final del trabajo.
