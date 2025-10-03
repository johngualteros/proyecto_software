# Historias de usuario
 
## HU-01 – Registro de usuarios
**Dado** un usuario no registrado  
**Cuando** ingresa email válido y contraseña con requisitos mínimos y envía el formulario  
**Entonces** se crea la cuenta y se redirige a Login.
 
**Criterios de aceptación**
- Validar formato de email.
- Contraseña con longitud mínima ≥ 8.
- Email único en el sistema.
- Contraseñas almacenadas hasheadas.
- Si el email ya existe, mostrar “email ya registrado” y no crear la cuenta.
 
---
 
## HU-02 – Inicio de sesión
**Dado** un usuario registrado  
**Cuando** ingresa credenciales válidas y envía el formulario  
**Entonces** accede a su cuenta y es redirigido a `/reminders`.
 
**Criterios de aceptación**
- Validar presencia de email y contraseña.
- En error, mostrar “credenciales inválidas” sin revelar si el email existe.
- Generar token de sesión con expiración; proteger rutas para requerir sesión activa.
 
---
 
## HU-03 – Cierre de sesión
**Dado** un usuario autenticado  
**Cuando** selecciona “Cerrar sesión”  
**Entonces** se invalida la sesión y se redirige a Login.
 
**Criterios de aceptación**
- Invalidar token/estado de sesión.
- Bloquear acceso a rutas protegidas hasta nuevo inicio de sesión.
- Feedback visual de cierre de sesión.
 
---
 
## HU-04 – Crear recordatorio
**Dado** un usuario autenticado  
**Cuando** completa título y fecha/hora futura y guarda  
**Entonces** el recordatorio queda registrado como activo.
 
**Criterios de aceptación**
- Campos obligatorios: título y fecha/hora.
- Validar fecha/hora > ahora considerando zona horaria del usuario.
- Si fecha/hora es pasada, mostrar error y no guardar.
- Mostrar confirmación visual al guardar.
 
---
 
## HU-05 – Editar recordatorio
**Dado** un recordatorio existente del usuario  
**Cuando** actualiza título y/o fecha/hora a un valor válido futuro  
**Entonces** se guardan los cambios correctamente.
 
**Criterios de aceptación**
- Aplicar las mismas validaciones que en creación.
- No permitir actualizar a fecha/hora pasada.
- Mostrar confirmación visual al actualizar.
- Conservar estado activo si corresponde.
 
---
 
## HU-06 – Eliminar recordatorio
**Dado** un recordatorio existente del usuario  
**Cuando** confirma la eliminación  
**Entonces** el recordatorio se elimina y no se programan envíos futuros.
 
**Criterios de aceptación**
- Solicitar confirmación previa.
- Remover de la lista inmediatamente.
- Impedir nuevos envíos del recordatorio eliminado.
- Mostrar confirmación visual.
 
---
 
## HU-07 – Envío automático de recordatorios (email)
**Dado** un recordatorio activo con `scheduleAt = T`  
**Cuando** llega la hora **T** (1 min antes)  
**Entonces** el sistema envía un correo electrónico al usuario y registra el envío en el historial.
 
**Criterios de aceptación**
- Canal único: email.
- Registrar en historial: `scheduledAt`, `sentAt`, `status (SENT/FAILED)` y `errorMsg`.
- Un reintento breve automático.
- No duplicar envíos para el mismo **T**.
 
---
 
## HU-08 – Visualizar historial de recordatorios
**Dado** un usuario autenticado con envíos previos  
**Cuando** accede a la pantalla de Historial  
**Entonces** visualiza la lista de envíos con fecha/hora, estado y detalle básico.
 
**Criterios de aceptación**
- Solo lectura (sin editar/eliminar).
- Orden por defecto descendente (más recientes primero).
- Mostrar claramente estado `SENT/FAILED`.
- Paginación.
 
---
 
## HU-09 – Filtrar historial por fechas
**Dado** un usuario autenticado con envíos registrados  
**Cuando** aplica un filtro desde/hasta  
**Entonces** se muestran solo los envíos dentro del rango seleccionado.
 
**Criterios de aceptación**
- Validar que `desde ≤ hasta`.
- Mantener orden/paginación al filtrar.
- Conservar otros filtros/estado de la vista.