# Levantamiento de Información (Workshop)

## Objetivo
Definir los requerimientos funcionales mínimos y validar las necesidades reales de los usuarios para un MVP de recordatorios de medicación que ahora incluye **persistencia**, **autenticación básica** e **historial de envíos por email**, priorizando simplicidad, utilidad y viabilidad técnica para un equipo de dos personas.

## Metodología
- **Formato:** Sesión remota (audio)
- **Enfoque:** Design Thinking – fase de ideación con facilitación guiada (preguntas estructuradas)
- **Técnicas:** Brainstorming, priorización rápida (matriz impacto/esfuerzo), definición de métricas

## Participantes
- **Facilitación:** John Alejandro Gualteros García y Ángela Michel Pinzón Oliveros (moderación, agenda, notas)
- **Equipo técnico:** John Alejandro Gualteros García y Ángela Michel Pinzón Oliveros
- **Usuarios/Stakeholders:** Pacientes/usuarios finales representativos (perfiles básicos de adherencia)

## Herramientas
- Llamada de audio y tablero colaborativo (notas/priorización)
- Repositorio con issues/Kanban

## Duración y dinámica (20 min)
1. Apertura y objetivo (2’)
2. Contexto (3’)
3. Ideación guiada / lluvia de ideas (8’)
4. Priorización rápida (4’)
5. Cierre con acuerdos, métricas y próximos pasos (3’)

## Hallazgos clave
- El olvido es el principal motivo de incumplimiento, especialmente en tratamientos prolongados.
- Se valora un historial/estado básico de envíos como confirmación; no requiere edición posterior.
- La interfaz debe priorizar claridad, rapidez y baja fricción (responsiva, sin sobrecarga visual).

---

# Decisiones de Alcance (MVP Actualizado)

## Se incluye (MVP)
- **Autenticación básica:** registro, login y logout (contraseñas hasheadas).
- **CRUD de recordatorios:** crear, editar y eliminar con fecha y hora.
- **Validaciones mínimas:** no permitir fechas/horas pasadas y campos esenciales obligatorios.
- **Envío automático por correo electrónico** en la hora programada.
- **Historial de envíos (solo lectura)** con filtros por fecha.
- **Interfaz web responsiva**, navegación simple y lenguaje accesible.
- **API RESTful conectada a MongoDB** (persistencia).

## Se excluye (futuras fases)
- Recordatorios por SMS/WhatsApp.
- Integraciones con calendarios o sistemas médicos.
- Módulos de familiares/cuidadores y roles avanzados.
- Dashboards administrativos complejos.
- Apps móviles nativas.
- Validaciones médicas/recetas electrónicas.

## Métricas de éxito
- **Onboarding ≤ 3 min** hasta crear el primer recordatorio.
- **≥ 90%** de recordatorios disparan email en la hora programada (ventana de ±1 min).
- **Deliverability ≥ 95%** de emails sin rebote.
- **Tiempo de carga inicial ≤ 2 s** en conexión estándar.
- **Errores 5xx < 1%** en endpoints principales.

---

# Lluvia de ideas
- Registro de usuarios con correo y contraseña  
- Recordatorios automáticos por correo electrónico  
- Confirmación de que el recordatorio fue enviado  
- Historial de recordatorios enviados  
- No permitir recordatorios con fecha pasada  
- Notificaciones simples, sin distracciones  
- Frontend con diseño limpio, sin elementos innecesarios  
- Interfaz responsiva para celular y computador  
- Lenguaje claro, sin tecnicismos  
- Módulo para crear, editar y eliminar recordatorios fácilmente  
- Correo como único canal de notificación (por ahora)  
- Sistema ligero, que cargue rápido en conexiones normales  
- Evitar dashboards complicados o funcionalidades que confundan  
- Solo mostrar historial, sin opción de editar ni borrar envíos pasados  
- Base de datos NoSQL (MongoDB) para mayor flexibilidad  
- Validaciones básicas en formularios: email, contraseña, fechas  
- Uso de **JWT** para autenticación segura  
- Implementar **nodemailer** o servicio SMTP para envíos de correo  
- Posibilidad de recordatorios recurrentes (opcional en futuro)  
- Separación clara entre frontend y backend  
- Desplegar en **Vercel** y **Render** para evitar costos  
- No incluir roles o perfiles diferenciados por ahora  
- No usar SMS ni WhatsApp por limitaciones técnicas y de costo  
- Aplicación pensada como **MVP**: pocas funciones, pero bien hechas  
- Manejo de errores centralizado en el backend  
- Autenticación obligatoria para ver y modificar recordatorios  
- Diseño adaptado a personas mayores o no expertas en tecnología  
- No integrar con calendarios externos en esta etapa  
- Evitar dependencias innecesarias que ralenticen el sistema  

---

# Decisiones tomadas a partir de la lluvia de ideas

A partir del análisis de las ideas generadas durante la sesión de brainstorming, se concluyó que el proyecto se enfocará en una **solución mínima viable (MVP)** que priorice la simplicidad, la utilidad real para el usuario y la viabilidad técnica dentro del tiempo y los recursos disponibles.

## Funcionalidades principales
- **Registro e inicio de sesión** de usuarios, con autenticación mediante **JWT** y almacenamiento de contraseñas en **MongoDB** (encriptadas).
- **Creación, edición y eliminación de recordatorios** personalizados, con fecha y hora programada para su **envío automático por correo electrónico**.
- **Visualización de un historial** básico de recordatorios enviados, **sin edición ni eliminación**, como confirmación del sistema.
- **Interfaz web responsiva** en **ReactJS**, con navegación clara y lenguaje accesible.
- **Backend en Node.js (Express)**, estructurado como **API RESTful** conectada a **MongoDB**.
- **Envío automatizado de correos** utilizando **nodemailer** o una solución SMTP similar, gestionado desde el backend.
- **Documentación técnica y manual de usuario** para facilitar el entendimiento y la entrega académica.

## Fuera de alcance actual
- Envío de recordatorios por **SMS** o **WhatsApp**.
- Integración con **calendarios externos** o **sistemas médicos**.
- **Módulos para familiares/cuidadores**.
- **Roles de usuario** o **paneles administrativos avanzados**.
