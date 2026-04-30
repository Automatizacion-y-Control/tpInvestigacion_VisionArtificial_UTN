# Plan de Investigación — Proyecto Percepta (VisioSphere)

Este documento establece la estrategia de investigación para el proyecto **Percepta**, asegurando que el desarrollo técnico se traduzca fielmente en el informe final solicitado en `_tp_investigacion.md`.

## 1. Definición del Proyecto de Investigación
**Tema:** Implementación de una Plataforma AIoT de Percepción Visual Distribuida para el Control Automatizado de Peajes Inteligentes.

El proyecto aborda la problemática de la centralización del procesamiento de video, proponiendo una arquitectura distribuida **Edge-Fog-Cloud** que permite transformar imágenes en eventos operacionales estructurados.

---

## 2. Mapeo de Contenidos (Alineación con Requisitos del Docente)

Para cumplir con las pautas del informe, la investigación se estructurará de la siguiente manera:

| Sección del Informe | Contenido del Proyecto Percepta |
| :--- | :--- |
| **1. Portada** | Integrantes: Emiliano Casali, Juan Gustavo Del Soto, Facundo Jose Ferrero, Cristian Gonzalo Vera. |
| **2. Índice** | Estructura basada en la arquitectura distribuida y el flujo de control. |
| **3. Resumen (Abstract)** | Síntesis de la arquitectura AIoT, el uso de YOLO/OCR y la reducción de latencia en peajes. |
| **4. Introducción** | Contexto del tráfico vial, limitaciones del Cloud-only y la hipótesis de la percepción distribuida. |
| **5. Marco Teórico** | Fundamentos de Visión Artificial, Deep Learning (CNNs), Protocolos IoT (MQTT) y arquitecturas Fog Computing. |
| **6. Desarrollo del Tema** | Detalle técnico del pipeline: Captura (Edge) → Inferencia (YOLO Nano) → OCR (Fog) → Gestión (Cloud). |
| **7. Aplicación en la Industria** | Integración en estaciones de peaje, control de flujo vehicular y seguridad operacional. |
| **8. Casos de Estudio** | Validación mediante el flujo: Detección vehículo → Lectura Patente → Apertura de Barrera (Actuación). |
| **9. Conclusión** | Resultados de eficiencia en ancho de banda, resiliencia offline y escalabilidad multi-sitio. |
| **10. Referencias** | Bibliografía sobre Visión por Computador, AIoT y documentación técnica de herramientas (OpenCV, etc.). |
| **11. Anexos** | Documentos técnicos A (Escalabilidad), B (Resiliencia), C (Observabilidad) y D (Roadmap). |

---

## 3. Estrategia de Investigación por Capas

Para completar el informe de manera "cabal", la investigación se dividirá en tres ejes tecnológicos:

### Eje A: Percepción y Edge AI (Captura)
- **Investigación:** Eficiencia de modelos TinyML en hardware limitado (ESP32-CAM / RPi Zero).
- **Entregable:** Sección 6 del informe (Detección primaria y triggers MQTT).

### Eje B: Procesamiento y Visión Computacional (Procesamiento)
- **Investigación:** Comparativa de algoritmos de OCR (EasyOCR vs PyTesseract) y detección de objetos (YOLOv8) en el Fog.
- **Entregable:** Sección 5 y 6 del informe (Pipeline de visión y validación de patentes).

### Eje C: Sistemas de Control y Actuación (Plataforma y Actuadores)
- **Investigación:** Integración de la lógica de visión con sistemas de control físico (Arduino/ESP32 + Servomotores).
- **Entregable:** Sección 8 del informe (Estudio de caso del sistema de control completo).

---

## 4. Cronograma de Generación de Documentación
El fin de esta investigación es la consolidación de los archivos `00_portada.md` al `22_conclusiones.md` (ya existentes en la carpeta) para que formen un documento único coherente que satisfaga los requerimientos de extensión (10-20 páginas) y profundidad técnica solicitados.

## 5. Validación del Sistema de Control
Para cumplir con la nota específica del docente (**Captura → Procesamiento → Plataforma → Actuadores**), la investigación documentará cómo el sistema Percepta cierra el lazo de control:
1. **Captura:** Sensor visual (Cámara).
2. **Procesamiento:** Lógica de IA en Fog/PC.
3. **Plataforma:** Controlador que interpreta la decisión de la IA.
4. **Actuador:** Acción física sobre el entorno (Barrera).

---
**Nota:** Este plan asegura que no queden "cabos sueltos" respecto a la consigna del TP Final y que la investigación sirva como base sólida para la futura tesis de carrera de los 4 integrantes.
