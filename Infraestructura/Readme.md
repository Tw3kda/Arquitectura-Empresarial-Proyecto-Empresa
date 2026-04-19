# Diagnóstico Técnico de Infraestructura  
## Sistema basado en Google Drive

<img width="710" height="562" alt="diagram-export-4-16-2026-9_28_27-PM" src="https://github.com/user-attachments/assets/1f0a5c50-baea-4280-bfff-5e0cbbaba820" />

---

## 1. Descripción

El sistema utiliza almacenamiento en la nube mediante Google Drive, accedido desde un computador. Los archivos Excel funcionan como repositorio principal de información financiera y contable.

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

## 7. Modelo To-Be
<img width="1244" height="937" alt="diagram-export-4-17-2026-9_30_46-AM" src="https://github.com/user-attachments/assets/7a0dce4d-b775-4cbb-9ead-d6b72dcadf9a" />

# Análisis de la Arquitectura TO-BE

## Problemas que soluciona
- Eliminación de múltiples archivos Excel dispersos en Google Drive  
- Reducción de errores manuales en procesos financieros  
- Falta de control y trazabilidad de cambios  
- Dificultad para generar reportes e indicadores  
- Baja visibilidad sobre cartera y pagos pendientes  

---

## Beneficios principales

### Seguridad y cumplimiento
- Control de accesos y autenticación centralizada  
- Trazabilidad mediante logs  
- Alineación con:
  - ISO/IEC 27001  
  - Ley 1581 de 2012 (Habeas Data)  

---

### Infraestructura (Cloud)
- Preparado para despliegue en la nube  
- Alta disponibilidad  
- Escalabilidad según demanda  
- Backups automáticos  

---

### Operativos
- Automatización de procesos  
- Reducción de tiempos de atención  
- Disminución de errores humanos  
- Integración de áreas (ocupacional y CRC)  

---

### Beneficios económicos
- Mayor control financiero  
- Identificación de empresas con pagos pendientes  
- Mejor gestión de cartera  
- Optimización del flujo de caja  
- Mejores decisiones administrativas  

---

## Conclusión
La arquitectura TO-BE permite pasar de un sistema manual y limitado a una solución centralizada, segura y escalable, mejorando el control financiero y la toma de decisiones.
