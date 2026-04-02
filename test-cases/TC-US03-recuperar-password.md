# TC-US03 — Casos de prueba: Recuperación de contraseña

Historia de usuario: [US-03](../user-stories/US-03-recuperar-password.md)
Jira ticket: QP-3

---

## TC-US03-001 - Solicitud de recuperación con email válido

**Tipo:** Happy path
**Prioridad:** High

**Precondición:**
- El email `usuario@test.com` está registrado en el sistema

**Pasos:**
1. Navegar a la página de login
2. Hacer clic en "¿Olvidaste tu contraseña?"
3. Ingresar email: `usuario@test.com`
4. Hacer clic en "Enviar enlace de recuperación"

**Resultado esperado:**
- Se muestra el mensaje: "Si el email existe, recibirás un enlace en breve"
- Se envía un email con enlace de recuperación a `usuario@test.com`
- El enlace en el email es único y tiene vigencia de 24 horas

---

## TC-US03-002 — Solicitud con email no registrado

**Tipo:** Negative path
**Prioridad:** High

**Precondición:**
- El email `noexiste@test.com` NO está registrado

**Pasos:**
1. Navegar a "¿Olvidaste tu contraseña?"
2. Ingresar email: `noexiste@test.com`
3. Hacer clic en "Enviar enlace de recuperación"

**Resultado esperado:**
- Se muestra el mismo mensaje genérico: "Si el email existe, recibirás un enlace en breve"
- NO se revela si el email existe o no en el sistema
- No se envía ningún email

---

## TC-US03-003 — Enlace de recuperación expirado

**Tipo:** Edge case
**Prioridad:** High

**Precondición:**
- Se generó un enlace de recuperación hace más de 24 horas

**Pasos:**
1. Abrir el enlace de recuperación expirado desde el email
2. Intentar establecer una nueva contraseña

**Resultado esperado:**
- Se muestra el mensaje: "Este enlace ha expirado. Solicitá uno nuevo"
- Se ofrece un botón o enlace para solicitar un nuevo enlace
- No es posible cambiar la contraseña con ese enlace

---

## TC-US03-004 — Cambio exitoso de contraseña con enlace válido

**Tipo:** Happy path
**Prioridad:** High

**Precondición:**
- Se solicitó recuperación de contraseña y el enlace es válido (menos de 24 horas)

**Pasos:**
1. Abrir el enlace de recuperación desde el email
2. Ingresar nueva contraseña: `NuevoTest1234!`
3. Confirmar nueva contraseña: `NuevoTest1234!`
4. Hacer clic en "Guardar nueva contraseña"

**Resultado esperado:**
- Se muestra mensaje de éxito: "Contraseña actualizada correctamente"
- El usuario es redirigido al login
- El usuario puede iniciar sesión con la nueva contraseña
- El enlace de recuperación queda invalidado y no puede usarse de nuevo

---

## TC-US03-005 — Enlace de recuperación de un solo uso

**Tipo:** Edge case
**Prioridad:** Medium

**Precondición:**
- Se usó exitosamente un enlace de recuperación para cambiar la contraseña

**Pasos:**
1. Intentar abrir el mismo enlace de recuperación por segunda vez

**Resultado esperado:**
- Se muestra el mensaje: "Este enlace ya fue utilizado"
- No es posible cambiar la contraseña nuevamente con ese enlace

