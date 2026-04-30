# Especificación Técnica: CLI Percepta (`per`)
**Versión:** 1.0 — VisionSphere Master Blueprint

## 1. Filosofía de Diseño
El CLI `per` no es una simple utilidad de configuración; es el motor que garantiza la paridad operativa y la **inmutabilidad** de la arquitectura VisionSphere en hardware real. Se inspira en el modelo transaccional de **Ubuntu Core**, asegurando que el sistema nunca quede en un estado roto.

### 1.1 Principios Fundamentales
- **Inmutabilidad:** Los componentes del sistema (IA, Config, Binarios) se tratan como snaps confinados o contenedores aislados.
- **Transaccionalidad:** Cualquier actualización (`update`) incluye un test de visión automático. Si el IoU (Intersection over Union) o la confianza cae, el sistema realiza un **rollback automático**.
- **Abstracción de Capa:** El técnico usa el mismo comando en Windows, Linux o macOS; el CLI gestiona las diferencias del sistema operativo subyacente.

---

## 2. Anatomía de Comandos
La sintaxis sigue el estándar de infraestructura moderna: `per <capa> <acción> [argumentos] [--banderas]`

### 2.1 Capas de Operación
| Capa | Alcance | Propósito |
| :--- | :--- | :--- |
| `cloud` | Centro de Datos / VPS | Despliegue de servicios centrales (Broker, InfluxDB, Grafana). |
| `fog` | Gateway Local | Configuración de brokers espejo, caché de modelos y dashboards de kiosco. |
| `edge` | Dispositivos de Borde | Gestión de nodos de percepción (SBCs o Microcontroladores). |
| `node` | Nodos Virtuales | Procesamiento batch de datos históricos o clusters de GPU. |
| `system` | Operación Global | Actualizaciones de perfil, certificados y estado del sistema. |

---

## 3. Comandos Principales (Índice Operativo)

### 3.1 Gestión Cloud
`per cloud deploy --domain <domain> [--secure]`
- Inicializa el motor de contenedores.
- Genera certificados X.509 para el Broker Maestro.
- Levanta la persistencia (InfluxDB) y dashboards (Grafana).

### 3.2 Gestión Fog
`per fog setup --link-cloud <api_url>`
- Configura el Local Bridge (MQTT espejo).
- Inicializa la Caché de Inteligencia para reducir uso de ancho de banda.
- Activa el dashboard local de baja latencia.

### 3.3 Gestión Edge (Multifamilia)
**Escenario A: Dispositivos con SO (Jetson, RPi, x86)**
`per edge join --profile <tipo> --fog <ip_fog>`
- Instala el Agente Percepta.
- Optimiza el pipeline de GStreamer según el hardware detectado (v4l2, nvargus, etc.).
- Descarga los pesos específicos (.engine para Jetson, .onnx para el resto).

**Escenario B: Dispositivos restringidos (ESP32-S3)**
`per edge gen-firmware --id <id> --wifi <ssid> --pass <pass>`
- Genera un binario `.bin` atómico.
- Incluye el modelo convertido a **TFLite Micro**.
- Inyecta certificados de seguridad para autenticación mTLS.

---

## 4. El "Git de la Visión" (Ciclo de Actualización)

El comando `per update` funciona como un `git push` con validación de CI/CD integrada en el hardware de destino.

### 4.1 Flujo de Actualización Crítica
`per update --profile peaje --model yolo_v11n_v2.onnx`

1. **Descarga:** El nodo descarga el nuevo modelo en una partición pasiva (Partición B).
2. **Inferencia de Prueba:** El sistema corre el modelo nuevo sobre los últimos frames capturados en memoria.
3. **Validación de Métricas:**
   - ¿Mantiene los FPS?
   - ¿La precisión de detección es igual o superior?
4. **Conmutación (Switch):** Si pasa el test, la Partición B se vuelve activa.
5. **Rollback:** Si falla, el sistema sigue operando con la Partición A y reporta el error al Cloud.

---

## 5. Gestión del Dato Visual
A diferencia de un CLI genérico, `per` entiende la semántica de la visión:
- **Contratos de Confiabilidad:** No se activa un cambio si el IoU (percepción de la plaga o patente) se degrada.
- **Optimización de Transporte:** El CLI configura qué se envía (Metadatos vs Snapshots vs Video) basándose en el perfil de red configurado.

---

## 6. Roadmap del CLI
- **Marketplace de Perfiles:** `per profile install agricola`
- **Diagnóstico de Salud:** `per status --all` (Muestra latencia, FPS y alertas de red).
- **Certificación de Hardware:** Validación automática de pipelines según el SoC detectado.
