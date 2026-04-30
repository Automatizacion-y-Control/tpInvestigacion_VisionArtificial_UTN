# Anexos Técnicos de Investigación

## Descripción General

La carpeta `anexos/` contiene documentación técnica complementaria utilizada para expandir, reforzar y profundizar distintos aspectos críticos del sistema AIoT distribuido desarrollado durante la investigación.

Estos documentos no forman parte del núcleo secuencial principal del informe, pero constituyen extensiones fundamentales para comprender propiedades avanzadas de la arquitectura propuesta, especialmente en relación con:

- escalabilidad distribuida;
- resiliencia operacional;
- tolerancia a fallos;
- observabilidad integral;
- evolución futura del ecosistema AIoT.

La función de estos anexos consiste en aportar una capa adicional de análisis técnico y arquitectónico que permita validar la robustez conceptual y operacional del sistema más allá del caso base presentado en el informe principal.

---

# Objetivo de los Anexos

Los anexos fueron desarrollados para documentar capacidades estructurales necesarias en sistemas AIoT reales de gran complejidad operacional.

Particularmente, buscan responder preguntas como:

- ¿Cómo crece la arquitectura sin colapsar?
- ¿Cómo continúa operando ante fallos parciales?
- ¿Cómo puede monitorearse un sistema distribuido?
- ¿Cómo evoluciona la plataforma en el tiempo?
- ¿Qué límites posee la infraestructura?
- ¿Cómo se evita dependencia excesiva de componentes centralizados?

---

# Relación con el Modelo AIoT

Los documentos presentes en esta carpeta se encuentran alineados con los principios del modelo AIoT distribuido basado en:

- Edge;
- Fog;
- Cloud;
- procesamiento distribuido;
- desacoplamiento funcional;
- inteligencia distribuida;
- resiliencia operacional;
- observabilidad transversal.

Cada anexo aborda propiedades emergentes del sistema cuando la infraestructura comienza a crecer en escala, complejidad y criticidad operacional.

---

# Estructura de la Carpeta

```text
anexos/
├── a_escalabilidad.md
├── b_toleranciaFallos.md
├── c_observabilidadMonitorio.md
├── d_roadmapEvolutivo.md
└── README.md
```

---

# Documentos Incluidos

## a_escalabilidad.md

Desarrolla estrategias de crecimiento distribuido de la arquitectura AIoT.

Incluye:

- escalabilidad horizontal;
- crecimiento Edge;
- federación Fog;
- escalabilidad Cloud;
- distribución de carga;
- crecimiento geográfico;
- limitaciones operacionales;
- estrategias futuras de expansión.

También analiza cómo el transporte selectivo del dato y la inferencia local permiten reducir saturación telecomputacional.

---

## b_toleranciaFallos.md

Describe mecanismos de resiliencia y continuidad operacional frente a fallos distribuidos.

Incluye:

- buffering local;
- operación offline parcial;
- reintentos automáticos;
- redundancia;
- rollback;
- recuperación distribuida;
- resiliencia telecomputacional;
- resiliencia IA;
- tolerancia a desconexiones.

El documento enfatiza la importancia del desacoplamiento entre capas Edge–Fog–Cloud para evitar puntos únicos de fallo.

---

## c_observabilidadMonitorio.md

Define mecanismos de monitoreo y observabilidad para sistemas AIoT distribuidos.

Incluye:

- métricas Edge;
- métricas Fog;
- métricas Cloud;
- trazabilidad distribuida;
- correlation IDs;
- monitoreo IA;
- monitoreo multimedia;
- observabilidad telecomputacional;
- logs distribuidos;
- alertas operacionales.

El documento diferencia explícitamente monitoreo y observabilidad como conceptos distintos dentro de sistemas complejos.

---

## d_roadmapEvolutivo.md

Presenta una estrategia evolutiva para la expansión progresiva de la plataforma.

Incluye:

- fases evolutivas;
- automatización operacional;
- IA distribuida;
- federated learning;
- percepción colaborativa;
- evolución telecomputacional;
- evolución multimedia;
- evolución de seguridad;
- evolución observabilidad;
- expansión multi-dominio.

El roadmap plantea una transición desde una infraestructura funcional inicial hacia un ecosistema AIoT distribuido inteligente y adaptativo.

---

# Importancia Arquitectónica

Estos anexos representan una parte crítica del proyecto porque permiten demostrar que la arquitectura propuesta no fue concebida únicamente para funcionar en condiciones ideales o de laboratorio.

La documentación aquí presente aborda explícitamente:

- crecimiento real;
- fallos reales;
- saturación real;
- operación multi-sitio;
- mantenimiento distribuido;
- evolución tecnológica.

Esto aporta mayor solidez técnica y conceptual al proyecto de investigación.

---

# Relación con la Tesina

Gran parte de los conceptos desarrollados en estos anexos se relacionan directamente con los principios estructurales de la futura tesina sobre infraestructura informacional AIoT distribuida.

Especialmente en temas vinculados a:

- desacoplamiento;
- distribución funcional;
- resiliencia sistémica;
- observabilidad transversal;
- expansión multi-capa;
- automatización cognitiva distribuida.

---

# Consideraciones Finales

Los anexos constituyen documentación técnica de soporte destinada a fortalecer la validez operacional y arquitectónica del sistema propuesto.

Su contenido permite extender el alcance del trabajo desde una implementación puntual hacia una visión de plataforma distribuida escalable, resiliente y evolutiva.

En conjunto, estos documentos complementan el cuerpo principal de investigación proporcionando profundidad técnica sobre aspectos críticos necesarios para sistemas AIoT modernos de percepción distribuida.