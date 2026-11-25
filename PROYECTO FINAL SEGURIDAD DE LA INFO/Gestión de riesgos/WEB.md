Cada vulnerabilidad será evaluada de forma aislada tomando en cuenta su valor crudo.

| **Campo**    | **Contenido**                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-01, W-03                                                                                                                                           |
| Descripción  | Los directorios sensibles como `/cloud`, `/console` y `/admin`, son expuestos mediante un listado de directorios.                                    |
| Activo       | Información dentro de dichos directorios. Como: credenciales, exportaciones, información sensible de red, etc.                                       |
| Amenaza      |                                                                                                                                                      |
| Impacto      | Alto. Se exponen credenciales y exportaciones de clientes                                                                                            |
| Probabilidad | Alta                                                                                                                                                 |
| Riesgo       | Muy Alto                                                                                                                                             |
| Control      | Deshabilitar listado de directorios, exigir autenticación y únicamente proveer al usuario los archivos que pidió (dentro del marco de autorización). |

| **Campo**    | **Contenido**                                                                                                                                                  |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-02                                                                                                                                                           |
| Descripción  | Cabeceras HSTS ausentes.                                                                                                                                       |
| Activo       | Portal web.                                                                                                                                                    |
| Amenaza      |                                                                                                                                                                |
| Impacto      | Medio. No se fuerza al navegador a ingresar al sitio mediante HTTPS.                                                                                           |
| Probabilidad | Alta                                                                                                                                                           |
| Riesgo       | Medio-Alto                                                                                                                                                     |
| Control      | Agregar `Strict-Transport-Security: max-age=63072000; includeSubDomains` a las cabeceras para forzar HTTPS a la página y todos sus subdominios durante 2 años. |

| **Campo**    | **Contenido**                                                                                                                                                                                     |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-04                                                                                                                                                                                              |
| Descripción  | Se muestran mensajes de error explícitos (como consultas SQL) dentro del modo debug de Flask cuando el campo recibe datos inesperados.                                                            |
| Activo       | Error Handling                                                                                                                                                                                    |
| Amenaza      |                                                                                                                                                                                                   |
| Impacto      | Alto                                                                                                                                                                                              |
| Probabilidad | Alta                                                                                                                                                                                              |
| Riesgo       | Alto-Crítico.                                                                                                                                                                                     |
| Control      | Convertir el parámetro `debug` de  `True` a `False` cuando se esté fuera del entorno de desarrollo local, y reservar detalles técnicos para logs internos en lugar de mostrarlos ante el usuario. |

| **Campo**    | **Contenido**                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------- |
| ID           | W-05                                                                                                            |
| Descripción  | La cuenta `admin` se creó con una contraseña (admin123) por default o súper común.                              |
| Activo       | Cuenta administrativa                                                                                           |
| Amenaza      |                                                                                                                 |
| Impacto      | Crítico. Permite acceder a usuarios no autorizados con permisos administrativos.                                |
| Probabilidad | Crítica. Estas cuentas suelen ser las más atacadas debido a sus privilegios.                                    |
| Riesgo       | Muy Crítico                                                                                                     |
| Control      | Reemplazar inmediatamente la contraseña a una más robusta, y evitar usar contraseñas débiles o predeterminadas. |

| **Campo**    | **Contenido**                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------- |
| ID           | W-06                                                                                                 |
| Descripción  | El formulario de login interpreta ciertos inputs como consultas SQL, y concatena username y password |
| Activo       | Formulario de login.                                                                                 |
| Amenaza      |                                                                                                      |
| Impacto      | Crítico. Permite acceder a usuarios no autorizados a cualquier cuenta solo con el nombre de usuario. |
| Probabilidad | Alta.                                                                                                |
| Riesgo       | Alto-Crítico                                                                                         |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                           |

| **Campo**    | **Contenido**                                                       |
| ------------ | ------------------------------------------------------------------- |
| ID           | W-07                                                                |
| Descripción  | Ausencia de autenticación multifactor para todas las cuentas.       |
| Activo       | Portal completo.                                                    |
| Amenaza      |                                                                     |
| Impacto      | Medio. Con una contraseña filtrada basta para ingresar a la cuenta. |
| Probabilidad | Media                                                               |
| Riesgo       | Medio                                                               |
| Control      | Considerar implementación de Active Directory                       |

| **Campo**    | **Contenido**                                                                                                       |
| ------------ | ------------------------------------------------------------------------------------------------------------------- |
| ID           | W-08                                                                                                                |
| Descripción  | El parametro `q` se concatena en una clausula `LIKE` dentro del formulario perteneciente a la Base de conocimiento. |
| Activo       | Búsqueda en la Base de conocimiento                                                                                 |
| Amenaza      |                                                                                                                     |
| Impacto      | Crítico. Permite extraer datos de la bases de datos mediante `UNION`                                                |
| Probabilidad | Media                                                                                                               |
| Riesgo       | Alto                                                                                                                |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                                          |

| **Campo**    | **Contenido**                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-09                                                                                                                                                 |
| Descripción  | Los datos de la base de datos de usuarios están almacenados en texto plano.                                                                          |
| Activo       | Base de datos de usuarios                                                                                                                            |
| Amenaza      |                                                                                                                                                      |
| Impacto      | Crítico                                                                                                                                              |
| Probabilidad | Crítica                                                                                                                                              |
| Riesgo       | Muy Crítico                                                                                                                                          |
| Control      | Utilizar algoritmos de hashing robustos como Argon2 o bcrypt que traen salting nativamente para codificar los datos sensibles en las bases de datos. |

| **Campo**    | **Contenido**                                                                                                                                                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ID           | W-10, W-11                                                                                                                                                                                                   |
| Descripción  | Ejecución XSS reflejado dentro de la barra de búsqueda del apartado `Base de conocimiento`; y ejecución XSS almacenado dentro del formulario a la descripción de problemas del apartado `Soporte y tickets`. |
| Activo       | Barra de búsqueda y formulario                                                                                                                                                                               |
| Amenaza      |                                                                                                                                                                                                              |
| Impacto      |                                                                                                                                                                                                              |
| Probabilidad |                                                                                                                                                                                                              |
| Riesgo       |                                                                                                                                                                                                              |
| Control      | Implementar conversión de caracteres especiales (`<, >, &, ", ')`) a entidades  seguras y validar entradas.                                                                                                  |

| **Campo**    | **Contenido**                                                                                                              |
| ------------ | -------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-12                                                                                                                       |
| Descripción  | El formulario del apartado `Diagnóstico de conexión` recibe entradas del usuario, las concatena con un ping y las ejecuta. |
| Activo       | Herramienta de diagnóstico de red                                                                                          |
| Amenaza      |                                                                                                                            |
| Impacto      |                                                                                                                            |
| Probabilidad |                                                                                                                            |
| Riesgo       |                                                                                                                            |
| Control      |                                                                                                                            |

| **Campo**    | **Contenido**                                                                                                  |
| ------------ | -------------------------------------------------------------------------------------------------------------- |
| ID           | W-13                                                                                                           |
| Descripción  | Versiones atrasadas de dependencias/herramientas como `Flask`, `Werkzeug`, `wheel`, `pip`, etc.                |
| Activo       | Herramientas utilizadas en el desarrollo de la página web.                                                     |
| Amenaza      |                                                                                                                |
| Impacto      |                                                                                                                |
| Probabilidad |                                                                                                                |
| Riesgo       |                                                                                                                |
| Control      | Actualizar `pip`, las dependencias y cualquier herramienta siendo utilizada en el desarrollo de la página web. |

| **Campo**    | **Contenido**                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-14                                                                                                                                        |
| Descripción  | Documentación muy insuficiente (prácticamente inexistente) sobre el diseño y arquitectura de la página.                                     |
| Activo       | Documentación de arquitectura de la página.                                                                                                 |
| Amenaza      |                                                                                                                                             |
| Impacto      |                                                                                                                                             |
| Probabilidad |                                                                                                                                             |
| Riesgo       |                                                                                                                                             |
| Control      | Crear y mantener documentación clara y concisa sobre el diseño, herramientas, procesos, componentes, controles y arquitectura de la página. |

| **Campo**    | **Contenido**                                                                                                                            |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-15                                                                                                                                     |
| Descripción  | Aún cuando el servidor recibe numerosos intentos de sesión, no bloquea o limita las peticiones.                                          |
| Activo       |                                                                                                                                          |
| Amenaza      |                                                                                                                                          |
| Impacto      |                                                                                                                                          |
| Probabilidad |                                                                                                                                          |
| Riesgo       |                                                                                                                                          |
| Control      | Aplicar rate limiting, bloquear la cuenta después de 3 intentos fallidos, implementar métodos de autenticación multifactor y un CAPTCHA. |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-01          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |