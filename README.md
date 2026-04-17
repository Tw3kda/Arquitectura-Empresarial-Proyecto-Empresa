# Arquitectura-Empresarial-Proyecto-Empresa

# Diagnóstico Técnico de Infraestructura  
## Sistema basado en acceso directo a archivos Excel


---

## 1. Descripción de la Infraestructura Actual

La infraestructura actual consiste en un único computador desde el cual un usuario accede directamente a múltiples archivos Excel. Estos archivos funcionan como principal fuente de almacenamiento, gestión y procesamiento de datos.

No existe una aplicación intermedia, base de datos centralizada ni servicios en la nube. La operación depende completamente del acceso manual a los archivos.

---

## 2. Identificación de Debilidades y Cuellos de Botella

### 2.1 Punto único de falla
El computador representa un único punto de falla. Si este equipo presenta problemas (fallo físico, malware, pérdida), todo el sistema queda inoperativo.

### 2.2 Falta de escalabilidad
El sistema no permite crecimiento eficiente:
- No soporta múltiples usuarios concurrentes
- El manejo de múltiples archivos se vuelve complejo
- El rendimiento disminuye a medida que crecen los datos

### 2.3 Acceso no controlado
No existen mecanismos robustos de control de acceso:
- Cualquier usuario con acceso al equipo puede modificar archivos
- No hay segmentación de permisos

### 2.4 Falta de concurrencia
No hay soporte para trabajo simultáneo:
- Riesgo de sobrescritura de archivos
- Conflictos entre versiones

### 2.5 Ausencia de trazabilidad
No se registran cambios:
- No es posible auditar modificaciones
- No hay historial confiable de versiones

### 2.6 Riesgos de integridad de datos
Alta probabilidad de errores manuales:
- Edición accidental
- Eliminación de información
- Inconsistencias entre archivos

### 2.7 Dependencia de procesos manuales
El sistema depende completamente del usuario:
- Procesos repetitivos
- Mayor probabilidad de errores humanos
- Baja eficiencia operativa

### 2.8 Almacenamiento no seguro
Los archivos pueden estar en:
- Disco local
- USB
- Correo electrónico

Esto genera riesgos de pérdida o filtración de información.

---

## 3. Diagnóstico Técnico

El sistema actual presenta una arquitectura altamente limitada, caracterizada por:

- Acoplamiento fuerte entre usuario, computador y datos
- Ausencia de capas de abstracción (no hay backend ni servicios)
- Falta de controles de seguridad y gobernanza de datos

Desde un punto de vista técnico, se trata de una arquitectura:

- No escalable
- No resiliente
- Difícil de mantener
- Altamente vulnerable

El principal problema radica en el uso de archivos Excel como sistema central, lo cual no está diseñado para soportar operaciones empresariales complejas ni multiusuario.

---

## 4. Impacto de las Limitaciones

Las debilidades identificadas pueden generar:

- Interrupciones operativas
- Pérdida de información crítica
- Decisiones basadas en datos incorrectos
- Riesgos de seguridad y cumplimiento
- Baja productividad

---

## 5. Buenas Prácticas de Arquitectura de Infraestructura

### 5.1 Arquitectura On-Premise

Características:
- Infraestructura local controlada por la organización
- Mayor control sobre los datos

Buenas prácticas:
- Redundancia de hardware
- Sistemas de backup automatizados
- Control de acceso basado en roles
- Segmentación de red

Limitaciones:
- Alto costo de mantenimiento
- Escalabilidad limitada

---

### 5.2 Arquitectura Cloud

Características:
- Infraestructura alojada en proveedores externos
- Acceso remoto y escalabilidad bajo demanda

Buenas prácticas:
- Uso de almacenamiento gestionado
- Control de acceso con identidad y roles (IAM)
- Backups automáticos y replicación
- Monitoreo continuo

Ventajas:
- Alta disponibilidad
- Escalabilidad
- Reducción de costos operativos

---

### 5.3 Arquitectura Híbrida

Características:
- Combinación de infraestructura local y en la nube

Buenas prácticas:
- Sincronización segura de datos
- Separación de cargas críticas
- Uso de VPN o conexiones seguras
- Estrategias de recuperación ante desastres

Ventajas:
- Flexibilidad
- Balance entre control y escalabilidad

---

## 6. Recomendaciones

Para mejorar la infraestructura actual se recomienda:

1. Migrar almacenamiento a la nube  
   Uso de plataformas seguras con control de acceso

2. Implementar control de versiones  
   Evitar pérdida de información y conflictos

3. Establecer permisos de acceso  
   Definir roles y restricciones por usuario

4. Automatizar copias de seguridad  
   Reducir riesgo de pérdida de datos

5. Evaluar migración a sistema estructurado  
   Sustituir Excel por base de datos o aplicación

---

## 7. Conclusión

La infraestructura actual, basada en un único computador y múltiples archivos Excel, no cumple con los estándares modernos de arquitectura. Presenta múltiples debilidades en términos de disponibilidad, seguridad y escalabilidad.

Se recomienda evolucionar hacia una arquitectura más robusta, preferiblemente basada en soluciones cloud o híbridas, que permitan garantizar la continuidad operativa y la protección de la información.



# Análisis de Seguridad usando STRIDE  
## Sistema de Procesamiento de Datos basado en Excel

---

## 1. Introducción

El sistema actual se basa en el uso de un computador que accede directamente a múltiples archivos Excel como fuente principal de almacenamiento y procesamiento de información. Este enfoque, aunque funcional, carece de controles de seguridad estructurados, lo que lo hace vulnerable a múltiples amenazas.

---

## 2. Metodología

Se utilizó el modelo de amenazas STRIDE, el cual clasifica los riesgos en las siguientes categorías:

- Spoofing (suplantación de identidad)  
- Tampering (alteración de datos)  
- Repudiation (repudio de acciones)  
- Information Disclosure (exposición de información)  
- Denial of Service (denegación de servicio)  
- Elevation of Privilege (elevación de privilegios)  

Este modelo permite identificar vulnerabilidades desde diferentes perspectivas de seguridad.

---

## 3. Tabla de Análisis de Amenazas

<img width="2487" height="221" alt="image" src="https://github.com/user-attachments/assets/320a9652-e9d2-4e7d-a66d-fe96470e0df1" />

## 4. Análisis de Riesgos

El análisis evidencia que la mayoría de las amenazas presentan una alta probabilidad de ocurrencia, principalmente debido a la ausencia de controles formales. Se identifican riesgos críticos en:

- Exposición de información sensible  
- Modificación no controlada de datos  
- Falta de trazabilidad  

El sistema presenta una alta dependencia de procesos manuales, lo que incrementa la vulnerabilidad.

---

## 5. Principales Vulnerabilidades

1. Ausencia de control de acceso  
   Cualquier usuario puede acceder o modificar los archivos.

2. Falta de trazabilidad  
   No es posible identificar quién realizó cambios.

3. Almacenamiento inseguro  
   Los archivos pueden ser copiados o compartidos sin restricciones.

4. Punto único de falla  
   Dependencia de un solo equipo para la operación.

---

## 6. Controles Recomendados

### Seguridad de acceso
- Implementar autenticación fuerte  
- Definir permisos por usuario  

### Protección de datos
- Encriptar archivos  
- Utilizar almacenamiento seguro en la nube  

### Auditoría
- Implementar versionado de archivos  
- Registrar cambios realizados  

### Disponibilidad
- Realizar copias de seguridad automáticas  
- Implementar redundancia de almacenamiento  

### Integridad
- Validar datos en Excel  
- Proteger celdas críticas  

---

## 7. Buenas Prácticas por Sector

### Educación
- Control de acceso a información académica  
- Protección de datos personales de estudiantes  
- Uso de plataformas centralizadas  

### Salud
- Encriptación de datos sensibles  
- Acceso basado en roles  
- Cumplimiento de normativas de privacidad  

### Logística
- Trazabilidad de operaciones  
- Integridad de datos  
- Centralización de la información  

---

## 8. Conclusión

El uso de archivos Excel como sistema principal sin controles de seguridad representa un riesgo significativo. Se recomienda evolucionar hacia una solución que incluya control de acceso, auditoría y centralización de la información, con el fin de garantizar la seguridad, integridad y disponibilidad de los datos.
