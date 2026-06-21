
## Pila y ejecución

- Backend: Node 22 + TypeScript, Express, JWT, bcrypt, CORS. Entrada en `server.ts`.

- Frontend: Next.js 16 (App Router) con React 19 y Tailwind base en `frontend/`.

- Scripts backend: `npm run dev`, `npm run test`, `npm run test:unit`, `npm run test:cucumber`, `npm run build`.

- Scripts frontend: `pnpm install` o `npm install` en `frontend/`, luego `npm run dev`.

  

## Arquitectura backend (capas)

- Presentación (`src/app/presentation`): routers Express y controladores (`urgencias`, `auth`, `reclamo`, `atencion`) que validan request mínimos y delegan a servicios.

- Servicios (`src/app/service`): reglas de negocio aisladas de infraestructura. Inyectan contratos de repositorios/infra (interfaces en `src/app/interface`).

- Infraestructura (`src/app/infrastructure`): implementaciones concretas (repos in-memory, JWT, bcrypt, middleware auth).

- Dominio (`src/models`): entidades y value objects con validaciones en constructores; comparadores y getters tipados.

- Tests y mocks (`src/test/mocks`, `test/`): repos y datos en memoria para BDD y unit tests.

  

## Dominio principal

- Personas: `Persona` base; `Paciente` (afiliado opcional, `Domicilio`), `Doctor` y `Enfermera` con matrícula.

- Seguridad: `Usuario` con `Rol` (`medico`, `enfermero`, `administrativo`) y `Email` VO.

- Cobertura social: `ObraSocial`, `Afiliado` (obra + número).

- Ingresos: `Ingreso` agrupa paciente, enfermera, constantes vitales, nivel, estado y doctor asignado; ordena por `NivelEmergencia` y timestamp.

- Atenciones: `Atencion` vincula ingreso + informe + doctor y marca fin del ingreso.

- Estados: `EstadoIngreso` (`Pendiente`, `En proceso`, `Finalizado`).

- Niveles: `NivelEmergencia` (estático, códigos 1–5) con comparación por prioridad.

  

## Value Objects y validaciones

- Identidad/contacto: `Cuil` (10/11 dígitos, formato, `formatearConGuiones`), `Email` (regex), `NumeroAfiliado` (no vacío).

- Signos vitales: `Temperatura` (30–45 °C), `FrecuenciaCardiaca` (40–200), `FrecuenciaRespiratoria` (8–60), `FrecuenciaSistolica` (60–180), `FrecuenciaDiastolica` (40–120), `TensionArterial` combina sistólica/diastólica y traduce errores de rango.

- Base abstracta `Frecuencia` valida no negativo y rango cuando aplica.

- Errores específicos: `InvalidValueError`, `PacienteError`, `AuthError`.

  

## Servicios clave

- `UrgenciaService`: valida signos con VOs, busca paciente en repo, crea `Ingreso`, mantiene `listaEspera` ordenada por prioridad/tiempo, permite reclamar paciente, asignar doctor y registrar `Atencion` marcando ingreso `FINALIZADO`. Previene doble asignación o atención fuera de estado.

- `PacienteService`: registra paciente con validación de campos obligatorios; opcionalmente valida obra social existente y afiliación vía repos `RepoObrasSociales` y `RepoAfiliaciones`; construye VOs y `Afiliado` cuando corresponde.

- `AuthService`: registra usuario con password >= 8, evita email duplicado, guarda hash bcrypt y emite JWT (payload con `sub`, `email`, `rol`); login compara hash y retorna token.

- Infra services: `BcryptPasswordHasher` y `JwtService` (implementa `JwtProvider` con expiración default 60m).

  

## Infraestructura

- Repos in-memory: `InMemoryRepoUsuarios` (en infraestructura) para producción demo y `DBPruebaEnMemoria`/`InMemoryUsuariosRepo`/`InMemoryObrasSocialesRepo`/`InMemoryAfiliacionesRepo` para tests.

- Seguridad: `JwtTokenProvider` y `authMiddleware` (valida Bearer, adjunta `user`), `adminMiddleware` (rol administrativo).

- Semillas en `server.ts`: crea usuarios demo (`admin`, `medico`, `enfermera`) y llena pacientes + ingresos de ejemplo al arrancar.

  

## API HTTP (Express)

- `/api/auth/register` (POST, protegido admin): alta de usuario.

- `/api/auth/login` (POST): devuelve JWT.

- `/api/urgencias/crear-paciente` (POST): alta rápida de paciente en memoria.

- `/api/urgencias/registrar` (POST): crea ingreso/triage.

- `/api/urgencias/lista-espera` (GET): lista ingresos pendientes ordenados.

- `/api/urgencias/pacientes` (GET): lista pacientes registrados.

- `/api/reclamo/reclamar` (POST, auth): médico reclama paciente (por CUIL opcional o próximo).

- `/api/reclamo/mis-ingresos` (GET, auth): ingresos asignados al médico.

- `/api/atencion/registrar` (POST, auth): médico registra atención y finaliza ingreso.

  

## Frontend (Next.js)

- `app/page.tsx`: login/registro simple, guarda JWT en `localStorage` y redirige a `/urgencias`.

- `app/urgencias/page.tsx`: renderiza `Dashboard`.

- `Dashboard`: tabs condicionados por rol decodificado del JWT (`registro`, `urgencia`, `lista`, `usuarios`); permite logout.

- `PacienteForm`: POST `/api/urgencias/crear-paciente`, propaga CUIL al siguiente paso.

- `UrgenciaForm`: POST `/api/urgencias/registrar`, usa datos de enfermera prellenados.

- `ListaEspera`: GET lista espera; médicos pueden reclamar (`/api/reclamo/reclamar`) y registrar atención (`/api/atencion/registrar`); muestra asignados y en proceso.

- `UsuarioForm`: creación de usuarios (solo tab visible para rol administrativo).

- Estilos en `globals.css` con tema oscuro, tarjetas y botones gradientes.

  

## BDD y pruebas

- Features en `test/features`: urgencias (prioridades, validaciones de signos), reclamo (estado EN_PROCESO y cola), atención (finaliza ingreso), autenticación, registro de pacientes.

- Step definitions usan `DBPruebaEnMemoria` y servicios reales para validar reglas de negocio end-to-end.

- Unit tests en `test/unit` cubren value objects, modelos y servicios (nombres por carpeta). Ejecutar con `npm run test:unit`.

  

## Flujo de datos típico

1) Administrativo crea usuario o enfermera registra paciente.

2) Enfermera registra urgencia → `UrgenciaService` valida VOs y encola `Ingreso`.

3) Médico reclama paciente → estado pasa a `EN_PROCESO`.

4) Médico registra atención → se crea `Atencion` y el ingreso queda `FINALIZADO`.

5) JWT protege rutas de reclamo/atención y alta de usuarios.

  

## Consideraciones y mejoras rápidas

- Persistencia real faltante: repos in-memory; reemplazar por base de datos implementando contratos `Repo*`.

- Validaciones en controladores son mínimas; mover a value objects o middlewares de esquema.

- Frontend consume rutas relativas; al desplegar configurar proxy/baseURL y almacenamiento seguro del token.

- Roles en JWT usan minúsculas para médicos/enfermeras y se normalizan en frontend; alinear nomenclatura si se agrega RBAC estricto.