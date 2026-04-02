# QA Portfolio — Login & Authentication

Workspace de testing manual cubriendo el módulo de autenticación de usuarios.

## Estructura del proyecto

\```
qa-portfolio/
├── user-stories/          # Historias de usuario con criterios de aceptación
│   ├── US-01-login.md
│   ├── US-02-registro.md
│   └── US-03-recuperar-password.md
└── test-cases/            # Casos de prueba por historia
    ├── TC-US01-login.md
    ├── TC-US02-registro.md
    └── TC-US03-recuperar-password.md
\```

## Historias cubiertas

| ID | Historia | Casos de prueba | Tipos cubiertos |
|---|---|---|---|
| US-01 | Inicio de sesión | 6 casos | Happy path, Negative, Edge case |
| US-02 | Registro de usuario | 5 casos | Happy path, Negative |
| US-03 | Recuperación de contraseña | 5 casos | Happy path, Negative, Edge case |

## Metodología

- **Framework:** Scrum (gestionado en Jira)
- **Tipo de testing:** Manual funcional
- **Técnicas aplicadas:** Partición de equivalencia, valores límite, casos negativos
- **Buenas prácticas:** Un caso por escenario, precondiciones explícitas,
  resultados esperados específicos y verificables

## Herramientas

- Jira — gestión de historias de usuario y seguimiento
- GitHub — documentación y versionado de casos de prueba
- Markdown — formato estándar para documentación técnica
