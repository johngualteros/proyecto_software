# Alcance del Proyecto: MedTime - Aplicación de Adherencia a la Medicación

**MedTime** es una **aplicación web** diseñada para ayudar a los usuarios a mejorar su **adherencia a la medicación** a través de **recordatorios automáticos** y un **sistema de historial de envíos**.

El sistema se compone de una **interfaz accesible** para el usuario final y una **API RESTful** para el manejo de usuarios, recordatorios y seguimiento. El desarrollo será realizado por un **equipo de dos personas** como proyecto académico.

---

## Objetivos del Proyecto

* Desarrollar una **aplicación web** que permita el **registro** e **inicio de sesión** de usuarios.
* Implementar un sistema para la **creación** y **gestión de recordatorios** de medicación.
* Desarrollar un módulo para el **seguimiento y visualización** del **historial de envíos** de recordatorios.
* Diseñar e implementar una **API RESTful** conectada a una base de datos **NoSQL (MongoDB)**.
* Entregar **documentación técnica y de usuario** que respalde el funcionamiento del sistema.

---

## Entregables

1.  **Aplicación web funcional** accesible desde navegador.
2.  **Backend** desarrollado en **Node.js con Express**, conectado a **MongoDB**.
3.  **Interfaz de usuario** desarrollada en **ReactJS**.
4.  **Documentación técnica** del sistema (arquitectura, estructura de datos, instalación).
5.  **Manual de usuario** básico (uso del sistema, funcionalidades principales).

---

## Requerimientos

### Requerimientos Funcionales (RF)

| Módulo | RF |
| :--- | :--- |
| **Autenticación** | Registro de usuarios |
| | Inicio de sesión |
| | Cierre de sesión |
| **Recordatorios** | Crear recordatorios con fecha y hora |
| | Editar o eliminar recordatorios |
| | **Envío automático de recordatorios por correo electrónico** |
| **Historial** | Visualizar historial de recordatorios enviados |
| | Filtrar historial por fechas |

### Requerimientos No Funcionales (RNF)

* La interfaz será **responsiva** y de **fácil navegación**.
* Las contraseñas estarán **encriptadas** en la base de datos.
* El backend deberá seguir principios de **seguridad básica en APIs REST**.
* **Tiempo de carga aceptable** en conexiones promedio.

---

## Lo que **Incluye** el Proyecto

* Diseño y desarrollo de la **interfaz de usuario con ReactJS**.
* **Backend completo** con **Node.js** y **Express**.
* Integración con base de datos **MongoDB** para persistencia.
* Módulos de **registro/login**.
* **Gestión de recordatorios** (crear, editar, eliminar, **envío automático por correo electrónico únicamente**).
* **Historial de recordatorios** ya enviados (solo serán visibles, no se pueden editar ni eliminar ya que son generados por el sistema).
* Entrega de la **aplicación funcional** y **documentación técnica**.

## Lo que **NO Incluye** el Proyecto

* Aplicaciones móviles nativas (**Android/iOS**).
* Recordatorios vía **SMS** o **WhatsApp**.
* Integraciones con sistemas médicos externos o **historiales clínicos**.
* Validaciones médicas o **recetas electrónicas**.
* Implementación de **roles de usuario** o **dashboards administrativos complejos**.

---

## Restricciones

* **Tiempo limitado**: El desarrollo se realizará dentro del calendario académico.
* **Equipo reducido**: Implementado por **dos integrantes**, lo que limita la complejidad.
* **Recursos disponibles**:
    * **Software**: Node.js, Express, ReactJS, MongoDB, Git, Figma, Postman, VS Code.
    * **Hardware**: Computadoras personales con conexión a internet.

---

## Planificación (Evolución por Fases)

### Corto Plazo (Fase Inicial)

* Configuración del **entorno de desarrollo** (Node.js, Express, ReactJS, MongoDB, Git).
* Implementación del **módulo de autenticación** (registro, inicio y cierre de sesión).
* **Encriptación de contraseñas** en la base de datos.
* Desarrollo de un **prototipo funcional** de la interfaz web con las pantallas básicas (registro, login, panel inicial).

### Mediano Plazo (Funcionalidad Principal)

* Implementación del **módulo de recordatorios** (crear, editar, eliminar con fecha/hora).
* Configuración del **envío automático de notificaciones por correo electrónico**.
* Desarrollo del **módulo de historial** (consulta y filtrado por fecha de recordatorios enviados).
* Refuerzo de la **seguridad** (**JWT** en autenticación, **validación de datos** en la API).
* Realización de **pruebas unitarias y de integración**.
* Elaboración del **manual de usuario**.

### Largo Plazo (Evolución y Escalabilidad - *Fuera de Alcance Académico Actual*)

* Mejora de la **escalabilidad y robustez** del sistema.
* **Despliegue** de la aplicación **en la nube**.
* Nuevas funcionalidades: **notificaciones push** en navegador, **aplicación móvil híbrida** con React Native, **dashboards de estadísticas**.
* Mejoras en **interfaz gráfica, accesibilidad y experiencia de usuario**.
* Implementación de **roles y permisos avanzados**.
* Pruebas de **carga y seguridad** más estrictas para entorno de producción.