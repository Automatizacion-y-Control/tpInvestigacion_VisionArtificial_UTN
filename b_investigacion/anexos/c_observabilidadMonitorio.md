# Observabilidad y monitoreo distribuido

## Introducción

En sistemas AIoT distribuidos, la observabilidad constituye un componente fundamental para comprender el comportamiento interno de la infraestructura y detectar anomalías operacionales antes de que impacten críticamente en el servicio.

Debido a que la arquitectura propuesta distribuye procesamiento entre Edge, Fog y Cloud, resulta insuficiente monitorear únicamente servidores centrales o aplicaciones aisladas.

La plataforma requiere capacidades integrales de observabilidad capaces de supervisar simultáneamente:

- infraestructura distribuida;
- transporte telecomputacional;
- inferencia IA;
- eventos operacionales;
- estado multimedia;
- recursos computacionales;
- sincronización entre capas.

## Diferencia entre monitoreo y observabilidad

### Monitoreo

El monitoreo responde preguntas conocidas.

Ejemplo:
¿el servicio está activo?

### Observabilidad

La observabilidad permite comprender comportamientos complejos emergentes.

Ejemplo:
¿por qué aumentó la latencia
entre Edge y Fog?

## Objetivo de observabilidad

El objetivo consiste en proporcionar visibilidad operacional completa del ecosistema AIoT distribuido.

### Principios

| Principio | Objetivo |
| :--- | :--- |
| trazabilidad | seguir recorrido dato |
| visibilidad | detectar fallos |
| diagnóstico | identificar causas |
| métricas | medir comportamiento |
| correlación | relacionar eventos |

## Observabilidad en EDGE

### EDGE

#### Objetivo

Monitorear estado operacional de nodos de percepción.

#### Métricas Edge

Recursos hardware:

| Métrica | Función |
| :--- | :--- |
| CPU | carga procesamiento |
| RAM | consumo memoria |
| temperatura | estabilidad térmica |
| FPS | rendimiento visual |

#### Estado cámaras

Variables:
- cámara activa;
- pérdida frames;
- errores captura;
- latencia adquisición.

#### Métricas inferencia

| Métrica | Función |
| :--- | :--- |
| inferencias/segundo | rendimiento IA |
| tiempo inferencia | latencia |
| confianza promedio | calidad detección |

#### Estado comunicación

Variables:
- conexión MQTT;
- latencia red;
- pérdida paquetes.

#### Logs Edge

Eventos registrados:
- reinicios;
- fallos cámara;
- errores inferencia;
- desconexiones.

#### Heartbeats

Los nodos pueden enviar señales periódicas.

Ejemplo:
```json
{
  "edge_id": "edge_01",
  "status": "online"
}
```

## Observabilidad en FOG

### FOG

#### Objetivo

Monitorear núcleo operacional distribuido.

#### Métricas procesamiento

| Métrica | Función |
| :--- | :--- |
| eventos/segundo | throughput |
| tiempo OCR | rendimiento |
| colas internas | saturación |

#### Métricas broker MQTT

Variables:
- mensajes/segundo;
- clientes conectados;
- tópicos activos;
- backlog.

#### Métricas multimedia

| Métrica | Función |
| :--- | :--- |
| streams activos | carga multimedia |
| bitrate | consumo red |
| latencia stream | calidad visual |

#### Estado persistencia

Variables:
- uso disco;
- velocidad escritura;
- tamaño bases datos.

#### Logs Fog

Eventos:
- errores correlación;
- fallos OCR;
- reconexiones;
- alertas críticas.

#### Observabilidad servicios

Cada microservicio debe reportar estado.

Ejemplos:
- broker MQTT
- API local
- OCR service
- dashboard

## Observabilidad en CLOUD

### CLOUD

#### Objetivo

Supervisión global del ecosistema distribuido.

#### Métricas infraestructura

| Métrica | Función |
| :--- | :--- |
| CPU cloud | carga servicios |
| RAM | saturación |
| almacenamiento | crecimiento datos |
| red | tráfico global |

#### Métricas multi-sitio

Variables:
- FOGs online;
- Edge activos;
- tráfico regional.

#### Métricas IA

| Métrica | Función |
| :--- | :--- |
| inferencias totales | carga IA |
| precisión promedio | calidad |
| drift | degradación modelos |

#### Logs centralizados

El Cloud puede consolidar logs globales.

Beneficios:
- correlación;
- auditoría;
- análisis histórico.

#### Dashboards globales

Visualización:
- estado plataforma;
- alertas;
- tráfico;
- disponibilidad.

## Trazabilidad distribuida

### Introducción

La trazabilidad permite seguir recorrido completo del dato.

Ejemplo recorrido:
1. Edge detecta vehículo
2. ↓
3. MQTT trigger
4. ↓
5. Fog procesa OCR
6. ↓
7. Cloud registra evento
8. ↓
9. dashboard muestra alerta

### Correlation IDs

Cada evento puede poseer identificador único.

Beneficio:
Permite reconstruir flujo completo.

## Logs distribuidos

### Objetivo

Registrar eventos técnicos y operacionales.

### Tipos logs

| Tipo | Ejemplo |
| :--- | :--- |
| sistema | reinicios |
| IA | errores inferencia |
| telecomunicaciones | desconexiones |
| seguridad | accesos |
| operacional | eventos críticos |

### Centralización logs

Los logs pueden consolidarse en Cloud.

## Alertas operacionales

### Objetivo

Detectar anomalías automáticamente.

### Ejemplos alertas

- nodo offline;
- latencia alta;
- pérdida streams;
- saturación CPU.

### Priorización

| Nivel | Ejemplo |
| :--- | :--- |
| baja | warning |
| media | degradación |
| alta | fallo crítico |

## Herramientas observabilidad

### Métricas

| Tecnología | Función |
| :--- | :--- |
| Prometheus | métricas |
| Telegraf | recolección |

### Visualización

| Tecnología | Función |
| :--- | :--- |
| Grafana | dashboards |
| Kibana | logs |

### Logs

| Tecnología | Función |
| :--- | :--- |
| Loki | logs |
| ELK Stack | análisis distribuido |

## Observabilidad IA

### Objetivo

Supervisar comportamiento modelos IA.

Variables:
- precisión;
- confianza;
- drift;
- tiempos inferencia.

### Detección degradación

Ejemplo:
precisión OCR disminuye
↓
alerta automática

## Observabilidad telecomputacional

### Variables monitoreadas

| Variable | Función |
| :--- | :--- |
| latencia MQTT | comunicación |
| pérdida paquetes | estabilidad |
| throughput | rendimiento |

### Streams

Monitoreo:
- FPS;
- bitrate;
- jitter.

## Observabilidad seguridad

### Eventos seguridad

- intentos acceso;
- autenticaciones;
- conexiones sospechosas.

### Auditoría

Toda acción crítica debe registrarse.

## Beneficios observabilidad distribuida

| Beneficio | Resultado |
| :--- | :--- |
| detección temprana | menos fallos críticos |
| debugging | diagnóstico rápido |
| análisis histórico | optimización |
| resiliencia | recuperación rápida |

## Conclusión

La observabilidad distribuida constituye un componente esencial dentro de la arquitectura AIoT propuesta.

Debido a la complejidad operacional y telecomputacional del sistema Edge–Fog–Cloud, resulta imprescindible contar con mecanismos capaces de proporcionar trazabilidad, monitoreo y diagnóstico integral sobre toda la infraestructura distribuida.

La combinación de métricas, logs, trazabilidad y alertas permite construir una plataforma operacionalmente observable, resiliente y mantenible en escenarios reales de percepción visual distribuida