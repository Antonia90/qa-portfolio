# TC-US02 - Casos de prueba: Registro de usuario

Historia de usuario: [US-02](../user-stories/US-02-registro.md)
Jira ticket: QPLA-2

---

## TC-US02-001 - Registro exitoso con datos válidos
**Tipo:** Happy path
**Prioridad:** High

**Precondición:**
- El email `nuevo@test.com` no está registrado en el sistema

**Pasos:**
1. Navegar a la página de registro
2. Ingresar email `nuevo@test.com`
3. Ingresar contraseña: `Test1234!`
4. Confirmar contraseña: `Test1234!`
5. Hacer click en "Crear cuenta"

**Resultado esperado:**
- Se muestra mensaje de éxito: "Cuenta creada. Revisa tu email para confirmar"
- Se envía email de confirmación a `nuevo@test.com`
- El usuario no puede iniciar sesión hasta confirmar el email

---

## TC-US02-002 - Registro con email ya existente

**Tipo:** Negative path
**Prioridad:** High

**Precondición:**
- El email `usuario@test.com` ya está registrado en el sistema

**Pasos:**
1. Navegar a la página de registro
2. Ingresar email `usuario@test.com`
3. Ingresar contraseña válida
4. Hacer click en "Crear cuenta"

**Resultado esperado:**
- El registro no se completa
- Se muestra el mensaje: "Este email ya está registrado"
- Se ofrece enlace a la página de login

---

## TC-002-003 - Registro con email con formato inválido

**Tipo:** Negative path
**Prioridad:** High

**Precondición:**
- Ninguna

**Pasos:**
1. Navegar a la página de registro
2. Ingresar email sin formato válido `usuariosindominio`
3. Ingresar contraseña válida
4. Hacer click en "Crear cuenta"

**Resultado esperado:**
- El formulario no se envía
- Se muestra el mensaje: "Ingresa un email válido"
- El campo email se resalta como error

---

## TC-US02-004 — Registro con contraseña menor a 8 caracteres

**Tipo:** Negative path
**Prioridad:** High

**Precondición:**
- Ninguna

**Pasos:**
1. Navegar a la página de registro
2. Ingresar email válido: `nuevo@test.com`
3. Ingresar contraseña: `Test1!`  *(6 caracteres)*
4. Hacer clic en "Crear cuenta"

**Resultado esperado:**
- El formulario no se envía
- Se muestra el mensaje: "La contraseña debe tener al menos 8 caracteres"

---
## TC-US02-005 — Registro con contraseñas que no coinciden

**Tipo:** Negative path
**Prioridad:** Medium

**Precondición:**
- Ninguna

**Pasos:**
1. Navegar a la página de registro
2. Ingresar email: `nuevo@test.com`
3. Ingresar contraseña: `Test1234!`
4. Confirmar contraseña: `Test5678!`
5. Hacer clic en "Crear cuenta"

**Resultado esperado:**
- El formulario no se envía
- Se muestra el mensaje: "Las contraseñas no coinciden"
- El campo de confirmación se resalta como error



