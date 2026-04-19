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
