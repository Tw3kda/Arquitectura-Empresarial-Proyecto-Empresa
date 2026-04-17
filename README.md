# Arquitectura-Empresarial-Proyecto-Empresa
# Diagnóstico Técnico de Infraestructura  
## Sistema basado en Google Drive

<img width="710" height="562" alt="diagram-export-4-16-2026-9_28_27-PM" src="https://github.com/user-attachments/assets/1f0a5c50-baea-4280-bfff-5e0cbbaba820" />

---

## 1. Descripción

El sistema utiliza almacenamiento en la nube mediante Google Drive, accedido desde un computador. Los archivos Excel funcionan como repositorio principal de información.

---

## 2. Debilidades y Cuellos de Botella

### 2.1 Dependencia de conexión a internet
Sin conexión no hay acceso al sistema.

### 2.2 Gestión de permisos compleja
Errores en configuración pueden generar accesos indebidos.

### 2.3 Falta de estructura de datos
Excel no escala bien para grandes volúmenes o lógica compleja.

### 2.4 Dependencia del usuario
Procesos siguen siendo manuales.

### 2.5 Seguridad del endpoint
El computador sigue siendo un punto vulnerable.

---

## 3. Diagnóstico

La arquitectura actual puede clasificarse como:

- Cloud básica
- No estructurada
- Semi-colaborativa

Aunque mejora disponibilidad, sigue siendo limitada en:

- Escalabilidad
- Gobernanza de datos
- Automatización

---

## 4. Buenas Prácticas

### Cloud
- Uso de IAM (gestión de identidades)
- Control de accesos
- Auditoría de actividad
- Backups

### Híbrida
- Copias locales controladas
- Redundancia

---

## 5. Recomendaciones

- Implementar políticas de acceso estrictas
- Migrar a base de datos si el sistema crece
- Automatizar procesos
- Mejorar seguridad del endpoint

---

## 6. Conclusión

El uso de Google Drive representa una mejora significativa en disponibilidad y colaboración, pero no resuelve problemas estructurales del uso de Excel como sistema principal. Se recomienda evolucionar hacia una arquitectura más robusta y controlada.

---

# Análisis de Seguridad con STRIDE  
## Sistema basado en Google Drive

<img width="2487" height="221" alt="image" src="https://github.com/user-attachments/assets/fe10c952-f894-4200-ba9e-d022c07f1ef9" />

---

## 1. Introducción

El sistema actual utiliza Google Drive como plataforma de almacenamiento centralizado para archivos Excel, accesibles desde un computador por parte de los usuarios. Este enfoque mejora la disponibilidad y colaboración respecto a un sistema local, pero introduce nuevos riesgos relacionados con accesos, compartición y gestión de identidades.

---

## 2. Cambios Clave respecto al sistema anterior

- Eliminación del punto único de falla local
- Introducción de acceso remoto
- Soporte para colaboración
- Dependencia de credenciales y configuración de permisos

---

## 3. Principales Riesgos

### Acceso no autorizado
El robo de credenciales permite acceso completo al sistema.

### Exposición de información
El uso de enlaces públicos puede generar filtraciones críticas.

### Permisos mal configurados
Usuarios con más privilegios de los necesarios pueden modificar información sensible.

### Dependencia del endpoint
Aunque los datos están en la nube, el acceso depende de la seguridad del computador.

---

## 4. Fortalezas del sistema

- Alta disponibilidad
- Versionado automático
- Acceso remoto
- Reducción de pérdida física de datos

---

## 5. Controles Recomendados

- Implementar autenticación multifactor (MFA)
- Aplicar principio de mínimo privilegio
- Restringir compartición por enlaces públicos
- Auditar accesos y actividades
- Capacitar a usuarios en uso seguro

---

## 6. Conclusión

El uso de Google Drive mejora significativamente la arquitectura respecto a un sistema local, pero introduce riesgos asociados a la gestión de accesos y compartición. La seguridad depende principalmente de la configuración adecuada de permisos y del control de identidad.
---

# Informe de Cumplimiento Normativo  
## Sistema basado en Google Drive y archivos Excel


<img width="2127" height="421" alt="image" src="https://github.com/user-attachments/assets/b8541d43-cb32-46b9-995c-96081e2b69f2" />


---

## 1. Introducción

Este informe evalúa el cumplimiento normativo del sistema actual basado en archivos Excel almacenados en Google Drive. Se consideran normativas colombianas e internacionales relacionadas con protección de datos personales y seguridad de la información.

---

## 2. Normativas analizadas

- Ley 1581 de 2012 (Habeas Data - Colombia)  
- ISO/IEC 27001 (Gestión de seguridad de la información)  
- Principios de protección de datos personales  
- Buenas prácticas de gobernanza de datos  

---

## 3. Hallazgos generales

El sistema presenta un cumplimiento parcial de las normativas debido al uso de Google Drive, que provee ciertos controles básicos como cifrado, control de acceso y versionado.

Sin embargo, estos controles no son suficientes para cumplir completamente con los requisitos formales de seguridad y gobernanza.

---

## 4. Principales brechas identificadas

### 4.1 Falta de formalización en protección de datos
No existen políticas documentadas sobre tratamiento de datos personales ni mecanismos claros de consentimiento informado.

### 4.2 Gestión de accesos insuficiente
El control de accesos depende de configuraciones básicas de Google Drive, sin un modelo formal de roles y permisos.

### 4.3 Ausencia de gestión de riesgos
No se ha realizado un análisis estructurado de riesgos de seguridad de la información.

### 4.4 Falta de continuidad del negocio
No existe un plan formal de respaldo y recuperación ante desastres.

### 4.5 Deficiencia en auditoría y trazabilidad
La trazabilidad se limita al historial de versiones de Google Drive, sin un sistema de auditoría centralizado.

---

## 5. Recomendaciones

### 5.1 Protección de datos
- Implementar políticas de tratamiento de datos personales  
- Establecer mecanismos de consentimiento informado  

### 5.2 Seguridad de la información
- Implementar un modelo de control de acceso basado en roles (RBAC)  
- Aplicar políticas de cifrado adicional para datos sensibles  

### 5.3 Gestión de riesgos
- Adoptar una metodología formal de gestión de riesgos  
- Identificar y clasificar activos de información  

### 5.4 Continuidad del negocio
- Implementar estrategias de respaldo automático  
- Definir planes de recuperación ante incidentes  

### 5.5 Gobernanza
- Definir responsables de datos (data owner y data steward)  
- Establecer políticas internas de uso de la información  
- Implementar programas de capacitación en seguridad  

---

## 6. Conclusión

El sistema actual basado en Google Drive y archivos Excel presenta un nivel de cumplimiento parcial frente a las normativas analizadas. Aunque la plataforma ofrece controles básicos de seguridad, es necesario implementar políticas formales de seguridad, gobernanza y gestión de datos para lograr cumplimiento completo con estándares como ISO/IEC 27001 y la Ley 1581 de 2012.

