# Escalabilidad y crecimiento distribuido

## Introducción

Uno de los principios fundamentales de la arquitectura propuesta consiste en permitir crecimiento progresivo del sistema sin necesidad de rediseñar completamente la infraestructura.

Debido a que el sistema fue concebido como una plataforma AIoT distribuida, la escalabilidad constituye un requisito estructural y no una capacidad secundaria.

La arquitectura debe soportar crecimiento en múltiples dimensiones simultáneamente:

- cantidad de nodos Edge;
- cantidad de FOGs;
- volumen de eventos;
- cantidad de streams;
- complejidad IA;
- expansión multi-sitio;
- crecimiento almacenamiento;
- incremento usuarios operacionales.

## Principio de escalabilidad distribuida

La arquitectura adopta el siguiente principio:

crecer agregando nodos
y no reemplazando
infraestructura completa

## Tipos de escalabilidad

| Tipo | Descripción |
| :--- | :--- |
| horizontal | agregar nodos |
| vertical | aumentar recursos |
| funcional | agregar capacidades |
| geográfica | expandir sitios |

## Escalabilidad en EDGE

### EDGE

#### Objetivo

Permitir incorporación progresiva de nuevos nodos de percepción.

#### Escalabilidad horizontal Edge

La arquitectura permite agregar nuevas cámaras o nodos visuales.

Ejemplo:
- Edge_01
- Edge_02
- Edge_03
- ↓
- todos reportan al mismo Fog

#### Registro dinámico

Los nodos pueden registrarse automáticamente.

Beneficios:
- despliegue rápido;
- integración automática;
- menor configuración manual.

#### Segmentación Edge

Los nodos pueden agruparse según:

- ubicación;
- dominio operacional;
- criticidad.

#### Escalabilidad IA Edge

La inferencia puede adaptarse según capacidad hardware.

Ejemplo:

| Hardware | Modelo |
| :--- | :--- |
| MCU básico | detección simple |
| SBC | YOLO nano |
| Jetson | modelos complejos |

#### Riesgos crecimiento Edge

| Riesgo | Impacto |
| :--- | :--- |
| exceso eventos | saturación Fog |
| demasiados streams | congestión red |
| administración masiva | complejidad operacional |

## Escalabilidad en FOG

### FOG

#### Objetivo

Permitir crecimiento operacional distribuido regional.

#### Escalabilidad horizontal Fog

La arquitectura soporta múltiples FOGs.

Ejemplo:
- Fog Norte
- Fog Centro
- Fog Sur

#### Federación de FOGs

Los FOGs pueden operar coordinadamente.

Beneficios:
- resiliencia;
- distribución carga;
- independencia regional.

#### Balance operacional

La carga puede redistribuirse.

Ejemplos:
- inferencia IA;
- procesamiento OCR;
- streams.

#### Escalabilidad broker MQTT

El crecimiento eventos requiere escalabilidad broker.

Estrategias:

| Estrategia | Función |
| :--- | :--- |
| clustering | distribución carga |
| partición tópicos | segmentación |
| brokers regionales | desacoplamiento |

#### Escalabilidad persistencia Fog

La persistencia local puede crecer mediante:

- almacenamiento distribuido;
- bases segmentadas;
- rotación datos.

#### Riesgos escalabilidad Fog

| Riesgo | Impacto |
| :--- | :--- |
| saturación OCR | retrasos |
| demasiados Edge | sobrecarga |
| almacenamiento excesivo | degradación |

## Escalabilidad en CLOUD

### CLOUD

#### Objetivo

Permitir crecimiento global del ecosistema AIoT.

#### Escalabilidad servicios

Los servicios Cloud pueden replicarse horizontalmente.

Ejemplo:
- API_01
- API_02
- API_03
- ↓
- balanceador carga

#### Escalabilidad almacenamiento

La evidencia visual puede crecer masivamente.

Estrategias:

| Estrategia | Función |
| :--- | :--- |
| object storage | escalabilidad objetos |
| tiering | almacenamiento jerárquico |
| archivado | reducción costo |

#### Escalabilidad IA

El entrenamiento puede escalar mediante:

- GPUs múltiples;
- clusters IA;
- procesamiento distribuido.

#### Escalabilidad dashboards

Los dashboards deben soportar:

- múltiples operadores;
- múltiples sitios;
- eventos simultáneos.

#### Escalabilidad multi-tenant

La plataforma puede soportar múltiples organizaciones.

Beneficios:
- aislamiento lógico;
- compartición infraestructura;
- expansión comercial.

## Escalabilidad telecomputacional

### Introducción

El crecimiento del sistema afecta directamente la red.

### Estrategia fundamental

Reducir transporte innecesario.

Principio:
transportar significado
antes que video continuo

### Optimización streams

Los streams deben activarse bajo demanda.

### Segmentación tráfico

Separación:

- eventos;
- multimedia;
- administración.

### Edge inference

La inferencia local reduce tráfico global.

## Escalabilidad operacional

### Gestión operadores

El sistema debe soportar múltiples operadores simultáneos.

### Jerarquías operacionales

Ejemplo:

| Nivel | Alcance |
| :--- | :--- |
| operador local | Fog específico |
| supervisor regional | múltiples FOGs |
| administrador global | plataforma completa |

### Automatización

La automatización reduce carga humana durante crecimiento.

## Escalabilidad IA

### Distribución modelos

Los modelos pueden desplegarse selectivamente.

Ejemplo:
- modelo tráfico
- ↓
- solo nodos urbanos

### Versionado distribuido

Cada capa puede ejecutar versiones distintas.

### Inferencia adaptativa

El sistema puede ajustar complejidad inferencia según recursos.

## Escalabilidad geográfica

### Expansión regional

La arquitectura permite múltiples regiones.

Ejemplo:
- Córdoba
- Rosario
- Mendoza
- Buenos Aires

### Sincronización distribuida

Los sitios pueden sincronizarse parcialmente.

## Límites de escalabilidad

Aunque la arquitectura es escalable, existen límites prácticos:

- ancho banda;
- almacenamiento;
- procesamiento IA;
- capacidad humana operacional.

## Estrategias futuras

Posibles mejoras:
- edge federado;
- IA colaborativa distribuida;
- federated learning;
- inferencia cooperativa.

## Beneficios de la escalabilidad distribuida

| Beneficio | Resultado |
| :--- | :--- |
| crecimiento modular | expansión gradual |
| resiliencia | aislamiento fallos |
| reducción tráfico | eficiencia |
| distribución carga | estabilidad |

## Conclusión

La arquitectura propuesta fue concebida desde su origen para soportar crecimiento distribuido progresivo.

La separación funcional entre Edge, Fog y Cloud permite escalar independientemente distintas capacidades del sistema según necesidades operacionales y tecnológicas.

El enfoque distribuido combinado con transporte selectivo del dato y procesamiento cercano al origen permite construir una plataforma AIoT escalable, resiliente y adaptable a escenarios de gran expansión operacional.