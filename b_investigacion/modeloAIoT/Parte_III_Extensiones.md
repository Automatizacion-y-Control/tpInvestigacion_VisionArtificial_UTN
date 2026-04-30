**PARTE III**

**Extensiones del modelo**

*¿Qué condiciones modifican las propiedades del espacio paramétrico?*

El modelo definido en la Parte II describe una infraestructura con propiedades estables: tres capas distinguibles, parámetros vectoriales con gradientes definidos, parámetros transversales con presencia uniforme y un eje funcional con distribución natural. Estas propiedades son válidas bajo las condiciones en que el modelo fue formulado.

Esta parte examina qué ocurre cuando esas condiciones se relajan. No se trata de casos de falla ni de situaciones excepcionales: son direcciones de evolución natural del espacio de diseño. Comprenderlas es parte del modelo, porque un modelo que solo describe el estado presente y no puede razonar sobre sus propios límites tiene alcance restringido.

## **Capítulo 8  —  Relajación de fronteras entre capas**

El eje vertical del modelo asume que Edge, Fog y Cloud son regiones distinguibles del espacio, con perfiles vectoriales suficientemente diferenciados como para ser tratados como categorías separadas. Esta distinción es útil y válida en la mayoría de los sistemas actuales. Sin embargo, no es una propiedad intrínseca del modelo: es una consecuencia de las condiciones bajo las cuales opera.

### **8.1  Atomización del nodo computacional**

El nodo computacional es la unidad mínima del eje vertical: el elemento sobre el que se ejecutan operaciones, se almacena información y se establecen canales de comunicación. En el modelo base, el nodo tiene un perfil vectorial fijo que determina su posición en el eje Edge–Cloud.

La atomización es el proceso por el cual los nodos se vuelven más pequeños, más numerosos y más distribuidos, sin reducción proporcional de su capacidad. Un nodo atomizado tiene menor tamaño físico que su predecesor pero igual o mayor poder de cómputo, menor consumo energético y menor latencia de comunicación con sus vecinos.

A medida que los nodos se atomizan, la distinción entre niveles se vuelve menos nítida. Un nodo que antes pertenecía inequívocamente al Edge por sus limitaciones de cómputo puede, una vez atomizado, ejecutar operaciones que antes requerían el Fog. **La categoría del nodo ya no está determinada por su hardware, sino por su posición topológica en el sistema y por los estadios funcionales que tiene asignados.**

### **8.2  Desvanecimiento de la distinción Edge–Fog–Cloud**

Cuando la atomización avanza de forma generalizada en el sistema, los perfiles vectoriales de los niveles convergen. El gradiente de poder de cómputo, que en el modelo base es pronunciado entre Edge y Cloud, se aplana. El gradiente de latencia, que en el modelo base es igualmente pronunciado, también se reduce.

En este estado, la pregunta de diseño ya no es en qué capa debe ejecutarse una operación, sino en qué nodo específico, dentro de una red de nodos con capacidades homogéneas. La arquitectura de tres capas no desaparece como concepto: persiste como descripción del rol funcional de cada nodo. Pero pierde su carácter de restricción de posicionamiento.

**Condición formal de desvanecimiento.** Sean C\_E, C\_F, C\_C los poderes de cómputo del Edge, Fog y Cloud respectivamente, y L\_E, L\_F, L\_C sus latencias. El desvanecimiento de fronteras ocurre cuando la diferencia entre niveles consecutivos tiende a cero: |C\_F − C\_E| → 0, |C\_C − C\_F| → 0, |L\_F − L\_E| → 0, |L\_C − L\_F| → 0. En ese límite, la posición en el eje vertical deja de ser una variable relevante para el diseño.

### **8.3  Computación ubicua como convergencia formal**

El caso límite del desvanecimiento total de fronteras es la computación ubicua: el estado en que el cómputo está disponible en cualquier punto del sistema con latencia y restricciones de poder de cómputo tendientes a cero. En este estado, la infraestructura como objeto de diseño explícito desaparece.

La computación ubicua no elimina el modelo: elimina la relevancia de uno de sus ejes. El eje funcional — los siete estadios — sigue siendo válido porque la secuencia lógica de transformaciones de la información es independiente de dónde ocurran. Los parámetros transversales — Seguridad e IA — siguen siendo válidos porque sus leitmotivs no dependen de la distribución física del cómputo. **Lo que desaparece es la restricción de posicionamiento.** El diseñador ya no necesita decidir en qué capa ejecutar cada operación; puede decidir exclusivamente en función del eje funcional y de los parámetros transversales.

Este caso límite tiene valor conceptual preciso: define el horizonte del espacio de diseño y permite situar cualquier sistema concreto en relación a ese horizonte. Un sistema cuyas fronteras entre capas son rígidas y pronunciadas está lejos del límite; un sistema cuyas fronteras son difusas y sus nodos son homogéneos está próximo a él. El modelo describe el trayecto completo.

**Nota:** La computación ubicua fue formulada como paradigma por Mark Weiser en 1991 bajo el concepto de calm technology. El presente modelo no adopta esa formulación en su totalidad, sino que utiliza la condición de convergencia de parámetros vectoriales como definición operacional del estado límite, independientemente de su realización tecnológica.

## **Capítulo 9  —  Convergencia del parámetro transversal con la capa computacional**

El capítulo anterior examina qué ocurre cuando los parámetros vectoriales convergen entre sí. Este capítulo examina una condición diferente: qué ocurre cuando un parámetro transversal deja de ser una propiedad que atraviesa las capas y se convierte en la capa misma.

Esta distinción no es semántica. Tiene implicaciones arquitectónicas concretas que el modelo debe poder describir, porque se trata de una dirección de evolución observable en sistemas de complejidad creciente.

### **9.1  Condición de separabilidad entre parámetro y capa**

En el modelo base, los parámetros transversales y las capas computacionales son entidades separables: la capa es el sustrato sobre el que se ejecutan operaciones; el parámetro transversal es una propiedad que esa capa debe satisfacer. Una capa Edge tiene un perfil vectorial determinado y, además, debe implementar Seguridad e IA con el peso apropiado. La capa y el parámetro son conceptualmente independientes aunque físicamente coexistan.

**Condición de separabilidad.** *Un parámetro transversal P y una capa computacional C satisfacen la condición de separabilidad cuando es posible describir el comportamiento de C sin referencia a P, y el comportamiento de P sin referencia a C. P puede variar sin que cambie la definición de C, y C puede variar sin que cambie la definición de P.*

Esta condición se satisface en el modelo base. La definición del Edge no depende de qué modelo de IA se ejecute en él, ni la definición de la IA como parámetro transversal depende de que exista un nodo Edge en el sistema. Son entidades ortogonales.

### **9.2  El caso límite: la capa como parámetro**

La condición de separabilidad puede relajarse. Esto ocurre cuando la capacidad de inferencia, decisión y acción autónoma de un nodo alcanza un nivel tal que el comportamiento del nodo ya no puede describirse sin referencia a esa capacidad: la autonomía no es una propiedad del nodo, es su definición.

En ese estado, el nodo no aloja IA: el nodo es un agente. Su función en el sistema no es ejecutar operaciones sobre la información siguiendo instrucciones externas, sino percibir su entorno, razonar sobre él y actuar de forma autónoma en consecuencia. La distinción entre infraestructura y cognición colapsa en ese nodo.

**Capa cognitiva.** *Nivel del eje vertical en el que la condición de separabilidad entre el parámetro transversal de IA y la capa computacional no se satisface. La capa cognitiva no implementa IA: su definición funcional es indistinguible de la del parámetro transversal de IA en ese nivel.*

**Criterio operacional de falsabilidad.** Un nodo satisface la condición de capa cognitiva cuando, al retirar hipotéticamente la capacidad de inferencia o decisión autónoma del mismo, su descripción funcional en el modelo cambia de categoría (es decir, deja de cubrir los estadios de Análisis complejo o Presentación autónoma que tenía asignados). Si, por el contrario, al retirar la porción IA el nodo sigue cubriendo los mismos estadios bajo la misma descripción funcional, la separabilidad se sostiene firmemente y el nodo no constituye una capa cognitiva.

La emergencia de una capa cognitiva no invalida el modelo. Lo extiende: el eje vertical pasa a incluir un nivel cuyo perfil no se describe solo en términos de poder de cómputo y latencia, sino también en términos de capacidad de agencia. **El espacio paramétrico gana una dimensión.** Los parámetros vectoriales siguen siendo válidos para describir las capacidades físicas del nodo; el parámetro transversal de IA, al converger con la capa, pasa a ser también un parámetro de posicionamiento.

El mismo razonamiento aplica, en principio, al parámetro transversal de Seguridad. Un nodo cuya función principal es garantizar la confianza en la cadena informacional —autenticar, validar, aislar— y cuyo comportamiento no puede describirse sin referencia a esa función, satisface la condición análoga para Seguridad. Este caso es menos frecuente en la arquitectura actual de sistemas distribuidos, pero el modelo lo contempla como posibilidad formal.

### **9.3  Implicaciones arquitectónicas**

La emergencia de capas cognitivas tiene consecuencias directas sobre el diseño de la infraestructura.

**Redefinición del rol del Fog.** El Fog es, en el modelo base, la capa de integración: su función es acoplar el Edge con el Cloud. En un sistema con capa cognitiva en el Fog, ese nodo no solo integra: razona, decide y actúa localmente con autonomía. Esto modifica el patrón de flujo de la información: parte de las decisiones que antes requerían el Cloud pueden ahora tomarse en el Fog, reduciendo la dependencia de conectividad y latencia.

**Orquestación distribuida.** Cuando múltiples nodos del sistema tienen capacidad de agencia, surge la necesidad de coordinar sus decisiones. Esta coordinación no puede resolverse con los mecanismos de control clásico, que asumen nodos pasivos que ejecutan instrucciones. Requiere protocolos de comunicación entre agentes que permitan negociar objetivos, delegar tareas y resolver conflictos de manera distribuida.

**Desplazamiento del eje funcional.** En un sistema con capas cognitivas, los estadios de Análisis y Presentación pueden ocurrir en nodos que antes estaban reservados para Percepción y Preprocesamiento. El eje funcional mantiene su secuencia lógica, pero su distribución natural en el eje vertical se modifica: los estadios cognitivamente intensivos migran hacia los nodos con capacidad de agencia, independientemente de su posición en el eje Edge–Cloud.

**Consistencia de los parámetros transversales.** La convergencia de la IA con una capa no libera a esa capa de la responsabilidad sobre la Seguridad. Un nodo cognitivo sigue siendo un nodo del sistema y debe satisfacer los requisitos de confidencialidad, integridad y disponibilidad que corresponden a su posición. La emergencia de agencia no sustituye la transversalidad de la Seguridad: la exige con mayor rigor, porque un agente comprometido tiene mayor capacidad de daño que un nodo pasivo.

Estas implicaciones no son especulativas. Son consecuencias formales de la relajación de la condición de separabilidad aplicada a los parámetros del modelo. Su realización concreta en sistemas específicos depende de condiciones externas al modelo — disponibilidad tecnológica, requisitos del dominio, restricciones de costo — pero su estructura lógica es derivable desde los axiomas de la Parte II.
