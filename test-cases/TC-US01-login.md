# TC -US01 - Casos de prueba: Inicio de sesión

Historia de usuario: [US-01](../user-stories/US-01-login.md)
Jira ticket: QPLA-1

---

## TC-US01-001 - Login exitoso con credenciales válidas

**Tipo:** Happy path
**Prioridad:** High

**Precondición:**
- El usuario existe en el sistema con email `usuario@test.com` y contraseña `Test1234!`
- El usuario no está bloqueado

**Pasos:**
1. Navegar a la página de login
2. Ingresar email: `usuario@test.com`
3. Ingresar contraseña: `Test1234!`
4. Hacer click en "Iniciar sesión"

**Resultado esperado:**
- El usuario es redirigido a su página de inicio
- Se muestra su nombre o avatar en la interfaz
- No se muestra ningún mensaje de error

---

## TC-US01-002 - Login fallido con contraseña incorrecta

**Tipo:** Negative path
**Prioridad:** High

**Precondición:**
- El usuario existe en el sistema con el mail `usuario@test.com`

**Pasos:**
1. Navegar a la página de login
2. Ingresar email: `usuario@test.com`
3. Ingresar contraseña: `wrongpassword`
4. Hacer click en "Iniciar sesión"

**Resultado esperado:**
- El usuario permanece en la página de login
- Se muestra un mensaje: "Email o contraseña incorrectos"
- La contraseña no se muestra en texto plano
- El campo de contraseña se limpia automáticamente

---

## TC-US01-003 - Login fallido con email no registrado

**Tipo:** Negative path
**Prioridad:** High

**Precondición:**
- Ninguna cuenta registrada con el email `noexiste@test.com`

**Pasos:**
1. Navegar a la página de login
2. Ingresar email: `noexiste@test.com`
3. Ingresar cualquier contraseña
4. Hacer click en "Iniciar sesión"

**Resultado esperado:**
- El usuario permanece en la página login
- Se muestra el mensaje: "Email o contraseña incorrectos"
- El mensaje no especifica si el error es el email o la contraseña

---

## TC-US01-004 - Login con campos vacíos

**Tipo:** Negative path
**Prioridad:** Medium

**Precondición:**
- Ninguna

**Pasos:**
1. Navegar a la página de login
2. Dejar ambos campos vacíos
3. Hacer click en "Iniciar sesión"

**Resultado esperado:**
- El usuario permanece en la página de login
- Se resaltan los campos vacíos con indicación visual de error
- Se muestra el mensaje: "Este campo es obligatorio" en cada campo vacío

---

## TC-US01-005 - Bloqueo tras 3 intentos fallidos

**Tipo:** Edge case
**Prioridad:** High

**Precondición:**
- El usuario existe en el sistema con el mail `usuario@test.com`

**Pasos:**
1. Navegar a la página de login
2. Ingresar el email correcto: `usuario@test.com`
3. Ingresar contraseña incorrecta: `wrongpassword`
4. Hacer click en "Iniciar sesión"
5. Repetir los pasos 2, 3 y 4 dos veces más
6. Ingresar mail correcto y contraseña **correcta**
7. Hacer click en "Iniciar sesión"


**Resultado esperado:**
- En el tercer intento fallido: se muestra mensaje de bloqueo temporal
- En el 7mo paso: el acceso es denegado aunque la contraseña sea correcta
- Se indica al usuario cuánto tiempo debe esperar antes de intentar de nuevo

---

## TC-US001-006 - Login con email en mayúsculas

**Tipo:** Edge case
**Prioridad:** Low

**Precondición:**
- El usuario existe con email `usuario@test.com` (minúsculas)

**Pasos:**
1. Navegar a la página de login
2. Ingresar el email: `USUARIO@TEST.COM`
3. Ingresar contraseña correcta: `Test1234!`
4. Hacer click en "Iniciar sesión"

**Resultado esperado:**
- El login es exitoso
- El usuario es dirigido a la página de inicio
- El sistema trata el email como case-insensitive (no distingue mayúsculas)

