9. Seguridad distribuida
9.1 Introducción

La seguridad dentro del sistema propuesto no se implementa como un componente agregado posteriormente.

Debido a la naturaleza distribuida de la arquitectura y a la sensibilidad potencial de los datos visuales procesados, la seguridad debe incorporarse desde el diseño inicial del sistema.

El sistema manipula:

eventos operacionales;
imágenes;
streams visuales;
datos vehiculares;
información de infraestructura;
credenciales distribuidas;
modelos IA.

Por esta razón, la seguridad se define como un parámetro transversal que atraviesa todas las áreas telecomputacionales y todas las fases funcionales del sistema.

9.2 Principio de seguridad distribuida

La arquitectura adopta el siguiente principio:

cada nodo debe asumir
que la red no es confiable

Esto implica:

autenticación explícita;
cifrado;
validación identidad;
segmentación;
auditoría;
control de acceso distribuido.
9.3 Seguridad como parámetro transversal

La seguridad atraviesa:

Área	Aplicación seguridad
Edge	protección dispositivos
Fog	protección operacional local
Cloud	protección infraestructura global

Además atraviesa las siete fases funcionales.

Ejemplo
Fase	Aplicación seguridad
percepción	control acceso sensores
comunicación	cifrado
almacenamiento	protección persistencia
presentación	control usuarios
9.4 Seguridad en EDGE
EDGE
9.4.1 Objetivo de seguridad en Edge

El Edge representa la capa más expuesta físicamente.

Los nodos pueden encontrarse:

en vía pública;
en infraestructura urbana;
en entornos industriales;
en ubicaciones remotas.

Esto introduce riesgos físicos y lógicos importantes.

9.4.2 Identidad de dispositivos

Cada nodo Edge debe poseer identidad única verificable.

Objetivos
evitar nodos falsificados;
autenticar dispositivos;
controlar acceso a infraestructura.
Mecanismos
Tecnología	Función
certificados X.509	identidad
claves únicas	autenticación
secure element	almacenamiento seguro
9.4.3 Secure Boot

El secure boot permite verificar integridad del firmware durante arranque.

Objetivo

Evitar ejecución de firmware alterado.

9.4.4 Firmware firmado

El firmware debe verificarse criptográficamente.

Beneficios
integridad;
autenticidad;
protección contra modificaciones maliciosas.
9.4.5 Hardening de nodos

El hardening busca reducir superficie de ataque.

Medidas
deshabilitar servicios innecesarios;
cerrar puertos no utilizados;
restringir acceso shell;
minimizar software instalado.
9.4.6 Protección física

Debido a despliegues distribuidos:

protección gabinete;
detección manipulación;
control acceso físico.
9.4.7 Seguridad operacional Edge

El Edge debe mantener funcionamiento seguro incluso bajo pérdida de conectividad.

9.4.8 Riesgos Edge
Riesgo	Impacto
acceso físico	compromiso nodo
firmware malicioso	falsificación eventos
robo credenciales	acceso infraestructura
interceptación tráfico	fuga información
9.5 Seguridad en FOG
FOG
9.5.1 Objetivo de seguridad en Fog

El Fog constituye núcleo operacional local del sistema.

Su compromiso podría afectar múltiples nodos Edge simultáneamente.

9.5.2 Segmentación de red

La infraestructura debe segmentarse.

Objetivo

Limitar propagación de ataques.

Estrategias
Estrategia	Función
VLAN	separación tráfico
subredes aisladas	contención
firewalls	filtrado
9.5.3 Autenticación

El Fog debe autenticar:

nodos Edge;
operadores;
servicios internos.
Métodos
Método	Aplicación
mTLS	nodos
SSH keys	administración
tokens	APIs
9.5.4 Auditoría

Toda operación relevante debe registrarse.

Eventos auditables
login;
despliegues;
cambios configuración;
reinicios servicios;
accesos streams.
9.5.5 Protección de streams

Los streams visuales representan activos sensibles.

Riesgos
espionaje;
acceso no autorizado;
captura ilegal.
Medidas
Medida	Función
autenticación stream	control acceso
expiración tokens	sesiones temporales
cifrado	protección tránsito
9.5.6 Seguridad dashboards locales

Los dashboards Fog requieren:

autenticación;
roles;
control sesiones;
logs acceso.
9.5.7 Seguridad servicios internos

Los microservicios Fog deben aislarse.

Estrategias
contenedores;
namespaces;
permisos mínimos;
segmentación interna.
9.6 Seguridad en CLOUD
CLOUD
9.6.1 Objetivo de seguridad Cloud

El Cloud concentra:

almacenamiento histórico;
modelos IA;
datos agregados;
administración global.

Esto lo convierte en objetivo crítico.

9.6.2 IAM

La gestión de identidades y accesos debe centralizarse.

Objetivos
control usuarios;
permisos diferenciados;
trazabilidad.
9.6.3 RBAC

El acceso debe organizarse por roles.

Ejemplo
Rol	Permisos
operador	monitoreo
supervisor	gestión operacional
auditor	lectura histórica
administrador	configuración global
9.6.4 Cifrado

Los datos deben protegerse:

en tránsito;
en reposo.
Aplicaciones
Tipo	Protección
bases datos	cifrado disco
object storage	cifrado objetos
backups	cifrado persistencia
9.6.5 Auditoría centralizada

El Cloud debe consolidar auditoría global.

Eventos
accesos;
modificaciones;
despliegues IA;
actividad operadores.
9.6.6 Protección APIs

Las APIs Cloud requieren:

autenticación;
rate limiting;
validación tokens;
protección abuso.
9.6.7 Seguridad multi-tenant

Si múltiples organizaciones utilizan la plataforma:

aislamiento lógico;
separación datos;
segmentación acceso.
9.7 Seguridad de comunicación
9.7.1 Objetivo

Proteger tráfico entre capas.

9.7.2 TLS

TLS protege comunicación cifrada.

Aplicaciones
MQTT over TLS;
HTTPS;
APIs;
dashboards.
9.7.3 mTLS

Mutual TLS permite autenticación mutua entre nodos.

Beneficio
cliente verifica servidor
+
servidor verifica cliente
9.7.4 VPN

Las VPN permiten túneles seguros entre sitios.

Aplicaciones
acceso remoto;
federación FOGs;
administración distribuida.
9.7.5 Certificados X.509

Los certificados permiten identidad distribuida verificable.

9.7.6 WireGuard

WireGuard permite VPN moderna liviana y eficiente.

9.8 Privacidad y cumplimiento
9.8.1 Introducción

El sistema puede procesar información sensible.

9.8.2 Ley 25.326

Debe considerarse cumplimiento de legislación argentina sobre protección datos personales.

Ley 25.326 de Protección de Datos Personales

9.8.3 Retención de imágenes

El sistema adopta principio de minimización.

Estrategia
Tipo dato	Política
imagen irrelevante	descarte
evidencia crítica	retención limitada
eventos estructurados	persistencia controlada
9.8.4 Anonimización

La plataforma puede anonimizar información sensible.

Ejemplos
hashing patentes;
ocultamiento parcial;
seudonimización.
9.8.5 Control de acceso

El acceso debe limitarse según necesidad operacional.

9.8.6 Minimización de exposición

La arquitectura reduce exposición mediante:

inferencia local;
reducción transmisión imagen cruda;
almacenamiento selectivo.
9.9 Seguridad IA
9.9.1 Riesgos IA
Riesgo	Impacto
modelo alterado	falsos eventos
adversarial attacks	evasión detección
drift	degradación precisión
9.9.2 Protección modelos

Los modelos IA deben:

versionarse;
firmarse;
validarse.
9.10 Estrategia integral de seguridad

La seguridad propuesta combina:

protección física;
protección lógica;
protección operacional;
protección comunicacional;
protección IA.
9.11 Conclusión

La seguridad dentro de la arquitectura AIoT distribuida constituye una capacidad transversal crítica.

El enfoque adoptado busca proteger simultáneamente:

dispositivos;
comunicaciones;
operadores;
modelos IA;
información operacional;
evidencia visual.

La distribución funcional del sistema obliga a implementar mecanismos de seguridad coherentes en todas las áreas telecomputacionales y en todas las fases funcionales del sistema.