**PARTE V**

**Cierre**

## **Capítulo 12  —  Conclusiones**

### **12.1  Lo que el modelo demuestra**

El trabajo ha propuesto y validado un modelo de infraestructura informacional para sistemas AIoT estructurado en tres ejes: un eje vertical con parámetros vectoriales de dirección y sentido definidos, dos parámetros transversales con leitmotiv propio, y un eje funcional de siete estadios que describe el ciclo de vida completo de la información. El modelo es tecnológicamente agnóstico en términos de implementación, aunque se apoya en una abstracción del espacio computacional basada en arquitecturas distribuidas.

La validación mediante el procedimiento de instanciación demuestra tres cosas:

**Primero, que el modelo tiene capacidad descriptiva.** Cualquier sistema AIoT puede ser mapeado al espacio paramétrico mediante el concepto de manejador y las fichas de instanciación. El mapeo produce una representación que es más precisa que una descripción tecnológica, porque hace explícitas las relaciones entre componentes, las restricciones de posicionamiento y las brechas de cobertura.

**Segundo, que el modelo tiene capacidad prescriptiva.** Dado un sistema con brechas funcionales o inconsistencias vectoriales, el modelo indica dónde están y en qué dirección deben resolverse. No prescribe la solución tecnológica; prescribe las propiedades que esa solución debe satisfacer. Esto lo hace aplicable a cualquier dominio y escala.

**Tercero, que el modelo tiene capacidad extensible.** Las condiciones de relajación examinadas en la Parte III — desvanecimiento de fronteras entre capas y convergencia del parámetro transversal de IA con la capa computacional — son derivables desde los axiomas del modelo sin modificar su estructura. El modelo no se rompe ante la evolución del espacio tecnológico: la incorpora como casos del mismo espacio formal.

Las implementaciones de validación en entornos industriales (tales como casos de sistemas F2J, SVA, etc.) confirman, además, que la brecha estructural que el modelo identifica como desacople evolutivo — la ausencia del Fog como capa de integración abstracta — es la causa raíz de la incapacidad de los sistemas preexistentes para soportar autonomía cognitiva. La vinculación semántica hacia un agente orquestador es la instanciación concreta de la solución que el modelo prescribe para ese tipo de brecha.

### **12.2  Lo que el modelo no pretende resolver**

La precisión de un modelo incluye la delimitación explícita de su alcance. El modelo propuesto no pretende resolver los siguientes problemas:

**El diseño de los manejadores.** El modelo describe qué propiedades debe tener cada manejador en el espacio paramétrico, pero no prescribe cómo implementarlo. La elección del hardware, el protocolo, el sistema operativo o el framework de desarrollo es una decisión de ingeniería que el modelo no determina ni restringe más allá de los requisitos de perfil vectorial y cobertura transversal.

**La optimización de parámetros.** El modelo identifica el punto de equilibrio entre poder de cómputo y latencia como el problema central del posicionamiento, pero no provee un algoritmo de optimización. La determinación del punto óptimo para un sistema concreto requiere datos empíricos del sistema y criterios de costo que son externos al modelo.

**La seguridad como disciplina.** El modelo trata la Seguridad como parámetro transversal con presencia obligatoria en todos los nodos, pero no desarrolla los mecanismos específicos que la implementan. La criptografía, la gestión de identidades, los protocolos de autenticación y las políticas de acceso son disciplinas con cuerpo propio que el modelo convoca pero no reemplaza.

**La validación de los modelos de IA.** El modelo trata la IA como parámetro transversal con gradiente de peso variable, pero no evalúa la calidad, precisión o sesgo de los modelos de inferencia que se despliegan en cada nodo. Esa evaluación es responsabilidad de la disciplina de aprendizaje automático y está fuera del alcance de este trabajo.

### **12.3  Líneas de trabajo derivadas del modelo**

Las siguientes líneas de trabajo se derivan formalmente de propiedades o extensiones del modelo que han sido identificadas pero no desarrolladas en este trabajo:

**L1.**  Formalización del procedimiento de optimización de posicionamiento. El modelo establece la existencia de un punto de equilibrio entre poder de cómputo y latencia para cada operación, pero no provee el método para calcularlo. Una línea de trabajo natural es desarrollar ese procedimiento como extensión cuantitativa del modelo.

**L2.**  Caracterización formal de la capa cognitiva. El Capítulo 9 define la capa cognitiva como el caso límite donde la condición de separabilidad entre el parámetro transversal de IA y la capa computacional no se satisface. Una extensión del modelo podría formalizar las propiedades de esa capa: sus interfaces, sus restricciones de consistencia con los parámetros transversales y sus patrones de coordinación con otros nodos.

**L3.**  Extensión del modelo a sistemas multiagente. Cuando múltiples nodos de un sistema satisfacen la condición de capa cognitiva, emergen problemas de coordinación entre agentes que el modelo actual no aborda. La extensión del espacio paramétrico para incluir relaciones horizontales entre nodos cognitivos es una línea de trabajo con fundamento directo en el Capítulo 9.

**L4.**  Aplicación del modelo a dominios no industriales. El caso de aplicación de este trabajo es un sistema industrial. El modelo es agnóstico al dominio, pero su validación en un solo dominio deja abierta la verificación en otros: salud, infraestructura urbana, sistemas distribuidos de consumo, redes de sensores ambientales. Cada dominio puede revelar gradientes transversales distintos que enriquecen la comprensión del espacio paramétrico.

**L5.**  Métrica de madurez AIoT basada en el modelo. El procedimiento de instanciación produce una descripción estructurada de cualquier sistema. A partir de esa descripción es posible derivar una métrica de madurez: qué fracción del espacio paramétrico está cubierta, con qué nivel de consistencia vectorial y qué brechas transversales persisten. Esa métrica sería una herramienta de evaluación y planificación aplicable a organizaciones que gestionan múltiples sistemas AIoT.



El modelo propuesto en este trabajo es una herramienta de diseño, análisis y comunicación para sistemas que gestionan información de forma distribuida con participación de inteligencia artificial. Su valor no reside en describir el estado actual del arte, sino en proveer un marco formal que permanece válido a medida que ese arte evoluciona. Los sistemas cambiarán; los parámetros que los describen, no.
