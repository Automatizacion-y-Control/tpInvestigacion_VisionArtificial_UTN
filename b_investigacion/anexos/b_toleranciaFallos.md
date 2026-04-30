# Resiliencia y tolerancia a fallos

## Introducción

La arquitectura propuesta fue concebida como un sistema distribuido capaz de mantener operación parcial aun frente a fallos localizados.

Debido a que el sistema opera sobre múltiples capas telecomputacionales distribuidas, resulta inevitable que ocurran eventos como:

- pérdida conectividad;
- caída servicios;
- desconexión nodos;
- saturación infraestructura;
- fallos hardware;
- degradación IA;
- errores operacionales.

Por esta razón, la resiliencia constituye un principio arquitectónico fundamental.

## Definición de resiliencia operacional

Dentro del contexto AIoT distribuido, resiliencia implica:

capacidad del sistema
de continuar operando
parcial o totalmente
ante fallos

## Objetivos resiliencia

La arquitectura busca:

- evitar punto único fallo;
- mantener operación parcial;
- aislar fallos;
- recuperar servicios rápidamente;
- minimizar impacto operacional.

## Tipos de fallos considerados

| Tipo fallo | Ejemplo |
| :--- | :--- |
| conectividad | pérdida red |
| hardware | nodo Edge dañado |
| software | servicio caído |
| IA | modelo degradado |
| telecomputacional | congestión |
| energético | pérdida alimentación |

## Resiliencia en EDGE

### EDGE

#### Objetivo resiliencia Edge

Permitir continuidad mínima percepción local.

#### Operación autónoma parcial

El Edge puede continuar ejecutando inferencia local aun sin conectividad inmediata.

Ejemplo:
- Fog desconectado
- ↓
- Edge continúa detectando

#### Buffering local

El nodo puede almacenar temporalmente eventos.

Beneficio:
Evita pérdida inmediata información.

#### Reintento transmisión

Los eventos pueden reenviarse cuando conectividad retorna.

#### Watchdogs

Los watchdogs permiten recuperación automática ante bloqueos.

Función:
- reinicio automático;
- recuperación firmware;
- detección congelamiento.

#### Redundancia percepción

Múltiples cámaras pueden cubrir misma región crítica.

#### Limitaciones resiliencia Edge

| Riesgo | Impacto |
| :--- | :--- |
| pérdida energía | nodo offline |
| daño físico | pérdida percepción |
| memoria limitada | buffering reducido |

## Resiliencia en FOG

### FOG

#### Objetivo resiliencia Fog

Mantener operación local incluso ante caída parcial Cloud.

#### Operación desconectada

El Fog debe poder continuar operando autónomamente.

Ejemplo:
- Cloud offline
- ↓
- Fog continúa correlando eventos

#### Persistencia local

El Fog mantiene almacenamiento temporal.

Beneficios:
- buffering;
- eventos pendientes;
- evidencia temporal.

#### Reenvío diferido

Cuando conectividad retorna:
1. Fog sincroniza backlog
2. ↓
3. Cloud recibe eventos pendientes

#### Redundancia servicios

Los servicios críticos pueden replicarse.

Ejemplos:
- broker MQTT;
- persistencia;
- APIs locales.

#### Supervisión interna

El Fog puede monitorear salud servicios.

Métricas:
- CPU;
- memoria;
- latencia;
- disponibilidad servicios.

#### Reinicio automático servicios

Los servicios pueden reiniciarse automáticamente.

Tecnologías posibles:

| Tecnología | Función |
| :--- | :--- |
| systemd | restart servicios |
| Docker restart policies | resiliencia contenedores |

#### Aislamiento fallos

Un fallo local no debe comprometer todo el sistema.

## Resiliencia en CLOUD

### CLOUD

#### Objetivo resiliencia Cloud

Mantener continuidad infraestructura global.

#### Replicación servicios

Los servicios Cloud pueden replicarse horizontalmente.

Ejemplo:
- API_01 cae
- ↓
- API_02 continúa

#### Balanceadores carga

Permiten distribuir tráfico.

#### Replicación bases datos

Evita pérdida persistencia crítica.

#### Backups

Los backups deben ser periódicos.

Datos críticos:
- eventos;
- configuraciones;
- modelos IA;
- evidencia.

#### Recuperación desastres

La arquitectura debe contemplar disaster recovery.

## Resiliencia telecomputacional

### Introducción

La conectividad constituye uno de los factores más críticos.

### Tolerancia desconexiones

La arquitectura evita dependencia absoluta comunicación permanente.

### Buffering eventos

Los eventos pueden almacenarse temporalmente.

### Transporte desacoplado

MQTT favorece desacoplamiento productor-consumidor.

### Reintentos automáticos

La comunicación debe soportar reintentos.

### Multipath potencial

En escenarios críticos pueden existir múltiples rutas red.

## Resiliencia IA

### Objetivo

Mantener funcionamiento IA estable.

### Fallback modelos

Si modelo avanzado falla:
1. modelo complejo falla
2. ↓
3. modelo simple fallback

### Versionado modelos

Permite rollback rápido.

### Monitoreo precisión

Detectar degradación IA.

## Resiliencia operacional

### Operación degradada

El sistema puede operar parcialmente degradado.

Ejemplo:
- sin streams
- ↓
- solo eventos semánticos

### Priorización eventos

Eventos críticos poseen prioridad mayor.

### Continuidad operacional

El objetivo principal:
evitar pérdida total operación

## Estrategias de recuperación

### Reinicio automático

Servicios reiniciables automáticamente.

### Rollback

Configuraciones y modelos reversibles.

### Re-sincronización

Cuando conectividad retorna:
1. eventos pendientes
2. ↓
3. re-sincronización

## Observabilidad resiliente

La observabilidad permite detectar degradaciones tempranamente.

Métricas críticas:

| Métrica | Objetivo |
| :--- | :--- |
| disponibilidad | detectar caídas |
| latencia | detectar congestión |
| FPS | detectar degradación |
| backlog eventos | detectar saturación |

## Riesgos residuales

Aun con resiliencia distribuida existen riesgos inevitables:

- catástrofes físicas;
- cortes energéticos masivos;
- fallos simultáneos múltiples.

## Beneficios arquitectura distribuida

La distribución Edge–Fog–Cloud reduce dependencia absoluta centralizada.

Beneficio:
fallo local ≠ caída completa sistema

## Conclusión

La resiliencia constituye uno de los pilares fundamentales de la arquitectura AIoT distribuida propuesta.

La separación funcional entre Edge, Fog y Cloud, junto con buffering, desacoplamiento y operación parcialmente autónoma, permite construir un sistema capaz de tolerar múltiples tipos de fallos manteniendo continuidad operacional.

Esto resulta fundamental para sistemas críticos basados en percepción visual distribuida donde la disponibilidad operacional posee alta importancia.