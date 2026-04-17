# Arquitectura-Empresarial-Proyecto-Empresa




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
