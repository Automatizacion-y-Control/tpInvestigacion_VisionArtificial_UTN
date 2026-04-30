# **PRÓLOGO**

## **1. El modelo informacional**
Cada vez más, el desarrollo de productos, servicios y procesos requiere la integración de controladores telecomputacionales y embebidos para su implementación. Si a esto sumamos la escalabilidad de la infraestructura de computación y telecomunicación mundial y las implementaciones que ello permite, nos encontramos ante un escenario donde las posibilidades de automatización y control en muchas áreas son realmente amplias. Esta tesina define un marco para implementar soluciones basadas en un **modelo de gestión de la información**.

## **2. El Internet de las Cosas (IoT)**
Ante este escenario, se han planteado diversos modelos de integración con visiones que presentan similitudes, pero también diferencias sustanciales entre sí. Para efectos de este marco de trabajo, se consideran las siguientes definiciones fundamentales:

* **Definición de IoT según IEEE:** *"Una red de elementos —cada uno incrustado con sensores— que están conectados a internet"*. (IEEE, Institute of Electrical and Electronics Engineers).
* **Definición de dispositivo IoT según NIST:** *"Un dispositivo IoT tiene al menos un transductor (sensor o actuador) para interactuar directamente con el mundo físico y al menos una interfaz de red para interactuar con el mundo digital"*. (NIST, Documento: NISTIR 8200, 2018).
* **Definición de IoT según ITU-T:** *"Una infraestructura global para la sociedad de la información, que permite servicios avanzados interconectando cosas (físicas y virtuales) basándose en tecnologías de información y comunicación existentes y en evolución interoperables"*. (ITU-T, Recomendación Y.2060, 2012).

**Observaciones analíticas del modelo:**
1. Se reconoce una **infraestructura global**, cuya instancia telecomputacional más prominente es "Internet".
2. Se reconoce la existencia de **dispositivos** (sensores y actuadores) que vinculan el mundo físico con el digital mediante módulos de interconexión.
3. Esta tesina adopta formalmente la definición de la **ITU-T**, entendiendo al IoT como una infraestructura global de servicios avanzados e interoperables.

## **3. El AIoT (Artificial Intelligence of Things)**
El IoT construye una infraestructura global de telecomputación que puede modelarse según tres dimensiones:
* **Capacidad de cómputo y alcance:** Edge, Fog y Cloud.
* **Capacidades transversales:** Seguridad y Comunicación.
* **Capacidades funcionales:** Percepción, preprocesamiento, transmisión, almacenamiento, procesamiento, análisis y presentación.

En la última década, la **Inteligencia Artificial** ha emergido como una capacidad transversal crítica. Según la definición de **Poole y Mackworth**: *"La inteligencia artificial, o IA, es el campo que estudia la síntesis y el análisis de agentes computacionales que actúan inteligentemente"*.

Bajo este enfoque, un sistema actúa inteligentemente cuando es apropiado para sus metas, flexible al entorno, aprende de la experiencia y elige adecuadamente dadas sus limitaciones. Por lo tanto, el modelado completo del **AIoT** se representa mediante:
* **Capacidad de cómputo y alcance:** Edge, Fog y Cloud.
* **Capacidades transversales:** Seguridad, Comunicación e Inteligencia Artificial.
* **Capacidades funcionales:** Los siete estadios desde la percepción hasta la presentación.

---

## **4. Los Componentes del AIoT: Del Modelo a la Implementación**
Una vez comprendida la infraestructura informacional, el foco de interés se desplaza hacia los **componentes del AIoT**. La riqueza de este modelo no reside solo en su teoría, sino en la capacidad de identificar y desplegar "manejadores" específicos que dan vida al sistema.



Hablar de componentes permite granular la arquitectura y asignar responsabilidades claras en el espacio paramétrico. En una implementación real de AIoT, encontramos elementos con propiedades y comportamientos diferenciados:

* **Agentes de Borde y Algoritmos de IA:** No son meros scripts; son agentes computacionales que ejecutan inferencia local (Edge AI), dotando al sistema de capacidad de respuesta inmediata y autonomía funcional frente a metas específicas.
* **Sistemas de Interfaz y Visualización (Web/Dashboards):** Componentes del estadio de "Presentación" que permiten la interacción humano-máquina y la supervisión del conocimiento generado.
* **Infraestructura de Datos y Entrenamiento:** Centros de cómputo (Cloud) dedicados a la síntesis de grandes volúmenes de información para el reentrenamiento de modelos, garantizando que el sistema aprenda de la experiencia global.
* **Gateways y Orquestadores Semánticos:** Componentes que aseguran la capacidad transversal de Comunicación, permitiendo la interoperabilidad entre dispositivos físicos y representaciones virtuales (como los Gemelos Digitales).

**Restricción de Identidad:**
Para que un elemento sea considerado un **componente del AIoT** dentro de este marco, debe poder posicionarse en el eje vertical (indicando su nivel de cómputo/latencia), satisfacer las transversales de seguridad y comunicación, y cumplir una función específica dentro del ciclo de vida de la información. La riqueza de la implementación radica en esta **consistencia paramétrica**: asegurar que cada componente posea el comportamiento exacto que el manejo de su información requiere.

