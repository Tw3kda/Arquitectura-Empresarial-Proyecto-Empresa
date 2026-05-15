# Análisis de Riesgos de Arquitectura Empresarial: Gestión Financiera y Cartera
**Proyecto:** ACR VITAL LABORAL SAS  
**Caso de Estudio:** Problema #3 - Consolidación Financiera y Gestión de Cartera  

---

## 1. Descripción de la Situación Actual (Arquitectura AS-IS)

La arquitectura actual de **ACR VITAL LABORAL SAS** se clasifica como una **Cloud Básica No Estructurada**, caracterizada por una alta dependencia de procesos manuales y herramientas ofimáticas aisladas.

* **Infraestructura y Almacenamiento:** El núcleo financiero reside en archivos de Excel dispersos almacenados en **Google Drive**. El acceso depende de la seguridad de dispositivos locales y la estabilidad de la conexión a internet.
* **Gestión de Datos:** Existe una desconexión total entre las dos líneas de negocio (Salud Ocupacional y CRC). La información de ingresos se transcribe manualmente desde los sistemas operativos (**BIOFILE** y recibos de **SISEC**) hacia un Excel consolidado mensual.
* **Procesos de Cartera:** El seguimiento de los créditos corporativos (plazos de hasta 3 meses) es puramente visual y reactivo. No existen alertas automáticas, lo que delega la detección de morosidad a la revisión periódica manual.
* **Gobierno TI:** El conocimiento del proceso está centralizado en dos personas, lo que genera una alta dependencia del factor humano y una gobernanza de datos limitada a permisos básicos de edición.

---

## 2. Análisis de Riesgos por Dominios

Siguiendo la **Guía Metodológica**, se identifican los siguientes riesgos estructurales:

### A. Riesgos de Negocio
* **Riesgo de Liquidez:** La ausencia de alertas de vencimiento incrementa la probabilidad de morosidad, afectando el capital de trabajo.
* **Dependencia de Personas:** La operatividad del cierre contable depende de personal específico, creando un riesgo de continuidad si estos actores no están disponibles.

### B. Riesgos de Procesos
* **Errores de Transcripción:** La digitación manual entre sistemas aumenta el riesgo de inconsistencias en los montos facturados y recaudados.
* **Falta de Trazabilidad:** El uso de archivos planos impide auditar quién realizó cambios en los saldos o aplicó pagos parciales negociados.

### C. Riesgos de Datos
* **Silos de Información:** La falta de integración impide una visión 360° del rendimiento financiero de la IPS.
* **Baja Integridad:** Excel no garantiza la persistencia de datos a largo plazo frente a errores de fórmulas o corrupción de archivos.

### D. Riesgos de Seguridad e Infraestructura
* **Punto Único de Falla (SPOF):** La pérdida de acceso a la cuenta de Drive o el fallo del computador principal paraliza la gestión financiera.
* **Incumplimiento Normativo:** Dificultad para cumplir rigurosamente con la Ley 1581 (Habeas Data) debido a la falta de logs de acceso y cifrado de datos contables sensibles.

---

## 3. Propuesta de Arquitectura Objetivo (TO-BE)

La solución propuesta evoluciona hacia una **Arquitectura Centralizada y Escalable**, diseñada para mitigar los riesgos identificados.

* **Capa de Integración (Backend):** Implementación de un servicio de API para la **carga masiva** de reportes. Esto elimina la transcripción manual y estandariza la ingesta de datos desde BIOFILE y SISEC.
* **Capa de Datos (Datalayer):** Base de datos relacional (Financial_DB) que mantiene libros contables separados por área, pero permite una consolidación automática en tiempo real.
* **Motor de Reglas de Cartera:** Sistema automatizado que:
    1. Registra la fecha de la primera cuenta de cobro.
    2. Calcula saldos totales considerando pagos parciales.
    3. Dispara **alertas internas** periódicas antes de cumplirse el plazo de 3 meses.
* **Capa de Presentación:** Dashboards interactivos con indicadores históricos y gráficos de rendimiento para el apoyo a la toma de decisiones gerenciales.

---

## 4. Matriz de Mitigación

| Riesgo Identificado | Mitigación Arquitectónica (TO-BE) | Mejora Obtenida |
| :--- | :--- | :--- |
| **Errores de digitación manual** | Carga masiva de datos estructurados | **Integridad:** Eliminación del error humano en la captura. |
| **Morosidad no detectada** | Módulo de alertas internas automáticas | **Eficiencia:** Mejora inmediata en el recaudo de cartera. |
| **Acceso inseguro / Falta de logs** | Gestión de Identidades (IAM) y Audit Logs | **Seguridad:** Trazabilidad total de cada ajuste financiero. |
| **Decisiones sin datos** | Dashboard de Inteligencia de Negocio | **Estratégica:** Visibilidad histórica y proyecciones reales. |

---

> **Conclusión:** La transición al modelo TO-BE permite a **ACR VITAL LABORAL SAS** transformar su gestión financiera de un proceso manual propenso al riesgo en una operación estratégica, segura y alineada con los objetivos de crecimiento de la IPS.
