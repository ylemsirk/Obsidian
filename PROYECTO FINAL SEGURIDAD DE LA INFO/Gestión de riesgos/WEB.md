Cada vulnerabilidad será evaluada de forma aislada tomando en cuenta su valor crudo.

| **Campo**    | **Contenido**                                                                                                                                                  |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-01                                                                                                                                                           |
| Descripción  | Cabecera `Strict-Transport-Secuirty` ausente en el servidor HTTPS. Evita al navegador recordar  la política HSTS.                                              |
| Activo       | Portal web y datos que viajen entre los clientes y el servidor.                                                                                                |
| Amenaza      | Atacante realizando un ataque MitM.                                                                                                                            |
| Impacto      | (3) Medio. No se fuerza al navegador a ingresar al sitio mediante HTTPS.                                                                                       |
| Probabilidad | (2) Medio-Baja.                                                                                                                                                |
| Riesgo       | (6) Medio.                                                                                                                                                     |
| Control      | Agregar `Strict-Transport-Security: max-age=63072000; includeSubDomains` a las cabeceras para forzar HTTPS a la página y todos sus subdominios durante 2 años. |

| **Campo**    | **Contenido**                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-02                                                                                                                                                 |
| Descripción  | Los directorios sensibles como `/cloud`, `/console` y `/admin`, son expuestos mediante un listado de directorios.                                    |
| Activo       | Información dentro de dichos directorios. Como: credenciales, exportaciones, información sensible de red, etc.                                       |
| Amenaza      |                                                                                                                                                      |
| Impacto      | Alto. Se exponen credenciales y exportaciones de clientes                                                                                            |
| Probabilidad | Alta                                                                                                                                                 |
| Riesgo       | Muy Alto                                                                                                                                             |
| Control      | Deshabilitar listado de directorios, exigir autenticación y únicamente proveer al usuario los archivos que pidió (dentro del marco de autorización). |

| **Campo**    | **Contenido**                                                                                                                                                                                     |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-03                                                                                                                                                                                              |
| Descripción  | Se muestran mensajes de error explícitos (como consultas SQL) dentro del modo debug de Flask cuando el campo recibe datos inesperados.                                                            |
| Activo       | Error Handling                                                                                                                                                                                    |
| Amenaza      |                                                                                                                                                                                                   |
| Impacto      | Alto                                                                                                                                                                                              |
| Probabilidad | Alta                                                                                                                                                                                              |
| Riesgo       | Alto-Crítico.                                                                                                                                                                                     |
| Control      | Convertir el parámetro `debug` de  `True` a `False` cuando se esté fuera del entorno de desarrollo local, y reservar detalles técnicos para logs internos en lugar de mostrarlos ante el usuario. |

| **Campo**    | **Contenido**                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------- |
| ID           | W-04                                                                                                            |
| Descripción  | La cuenta `admin` se mantuvo con una contraseña (admin123) por default desde su creación.                       |
| Activo       | Cuenta administrativa                                                                                           |
| Amenaza      |                                                                                                                 |
| Impacto      | Crítico. Permite acceder a usuarios no autorizados con permisos administrativos.                                |
| Probabilidad | Crítica. Estas cuentas suelen ser las más atacadas debido a sus privilegios.                                    |
| Riesgo       | Muy Crítico                                                                                                     |
| Control      | Reemplazar inmediatamente la contraseña a una más robusta, y evitar usar contraseñas débiles o predeterminadas. |

| **Campo**    | **Contenido**                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------- |
| ID           | W-05                                                                                                 |
| Descripción  | El formulario de login interpreta ciertos inputs como consultas SQL, y concatena username y password |
| Activo       | Formulario de login.                                                                                 |
| Amenaza      |                                                                                                      |
| Impacto      | Crítico. Permite acceder a usuarios no autorizados a cualquier cuenta solo con el nombre de usuario. |
| Probabilidad | Alta.                                                                                                |
| Riesgo       | Alto-Crítico                                                                                         |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                           |

| **Campo**    | **Contenido**                                                                                                       |
| ------------ | ------------------------------------------------------------------------------------------------------------------- |
| ID           | W-06                                                                                                                |
| Descripción  | El parametro `q` se concatena en una clausula `LIKE` dentro del formulario perteneciente a la Base de conocimiento. |
| Activo       | Búsqueda en la Base de conocimiento                                                                                 |
| Amenaza      |                                                                                                                     |
| Impacto      | Crítico. Permite extraer datos de la bases de datos mediante `UNION`                                                |
| Probabilidad | Media                                                                                                               |
| Riesgo       | Alto                                                                                                                |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                                          |

| **Campo**    | **Contenido**                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-07                                                                                                                                                 |
| Descripción  | Los datos de la base de datos de usuarios están almacenados en texto plano.                                                                          |
| Activo       | Base de datos de usuarios                                                                                                                            |
| Amenaza      |                                                                                                                                                      |
| Impacto      | Crítico                                                                                                                                              |
| Probabilidad | Crítica                                                                                                                                              |
| Riesgo       | Muy Crítico                                                                                                                                          |
| Control      | Utilizar algoritmos de hashing robustos como Argon2 o bcrypt que traen salting nativamente para codificar los datos sensibles en las bases de datos. |

| **Campo**    | **Contenido**                                                                                                                                                                                                              |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-08, W-09                                                                                                                                                                                                                 |
| Descripción  | Ejecución XSS reflejado dentro de la barra de búsqueda del apartado `Base de conocimiento` (W-08); y ejecución XSS almacenado dentro del formulario a la descripción de problemas del apartado `Soporte y tickets` (W-09). |
| Activo       | Barra de búsqueda y formulario                                                                                                                                                                                             |
| Amenaza      |                                                                                                                                                                                                                            |
| Impacto      |                                                                                                                                                                                                                            |
| Probabilidad |                                                                                                                                                                                                                            |
| Riesgo       |                                                                                                                                                                                                                            |
| Control      | Implementar conversión de caracteres especiales (`<, >, &, ", ')`) a entidades  seguras y validar entradas.                                                                                                                |

| **Campo**    | **Contenido**                                                                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-10                                                                                                                                                            |
| Descripción  | El formulario del apartado `Diagnóstico de conexión` recibe entradas del usuario, las concatena con un ping y las ejecuta en el contexto del sistema operativo. |
| Activo       | Herramienta de diagnóstico de red                                                                                                                               |
| Amenaza      |                                                                                                                                                                 |
| Impacto      |                                                                                                                                                                 |
| Probabilidad |                                                                                                                                                                 |
| Riesgo       |                                                                                                                                                                 |
| Control      |                                                                                                                                                                 |

| **Campo**    | **Contenido**                                                                                                  |
| ------------ | -------------------------------------------------------------------------------------------------------------- |
| ID           | W-11                                                                                                           |
| Descripción  | Versiones atrasadas de dependencias/herramientas como `Flask`, `Werkzeug`, `wheel`, `pip`, etc.                |
| Activo       | Herramientas utilizadas en el desarrollo de la página web.                                                     |
| Amenaza      |                                                                                                                |
| Impacto      |                                                                                                                |
| Probabilidad |                                                                                                                |
| Riesgo       |                                                                                                                |
| Control      | Actualizar `pip`, las dependencias y cualquier herramienta siendo utilizada en el desarrollo de la página web. |

| **Campo**    | **Contenido**                                                                                                                            |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-12                                                                                                                                     |
| Descripción  | Aún cuando el servidor recibe numerosos intentos de sesión, no bloquea o limita las peticiones.                                          |
| Activo       | Formulario de login.                                                                                                                     |
| Amenaza      |                                                                                                                                          |
| Impacto      |                                                                                                                                          |
| Probabilidad |                                                                                                                                          |
| Riesgo       |                                                                                                                                          |
| Control      | Aplicar rate limiting, bloquear la cuenta después de 3 intentos fallidos, implementar métodos de autenticación multifactor y un CAPTCHA. |

| **Campo**    | **Contenido**                                                                                                               |
| ------------ | --------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-13                                                                                                                        |
| Descripción  | La ruta `/admin` únicamente verifica si un usuario ha sido autenticado aún si la cuenta no pertenece a algún administrador. |
| Activo       |                                                                                                                             |
| Amenaza      |                                                                                                                             |
| Impacto      |                                                                                                                             |
| Probabilidad |                                                                                                                             |
| Riesgo       |                                                                                                                             |
| Control      | Aplicar políticas Zero Trust y cambiar a un modelo de control de acceso basado en roles (RBAC).                             |

| **Campo**    | **Contenido**                                                       |
| ------------ | ------------------------------------------------------------------- |
| ID           | W-14                                                                |
| Descripción  | Ausencia de autenticación multifactor para todas las cuentas.       |
| Activo       | Portal completo.                                                    |
| Amenaza      |                                                                     |
| Impacto      | Medio. Con una contraseña filtrada basta para ingresar a la cuenta. |
| Probabilidad | Media                                                               |
| Riesgo       | Medio                                                               |
| Control      | Considerar implementación de Active Directory                       |

| **Campo**    | **Contenido**                                                                                                                                                                             |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-15                                                                                                                                                                                      |
| Descripción  | Cualquier usuario puede acceder a recursos que no le corresponden con solo hacer cambios en la URL ya que no se verifica la identidad del usuario para acceder a recursos ajenos (IDOR).  |
| Activo       |                                                                                                                                                                                           |
| Amenaza      |                                                                                                                                                                                           |
| Impacto      |                                                                                                                                                                                           |
| Probabilidad |                                                                                                                                                                                           |
| Riesgo       |                                                                                                                                                                                           |
| Control      | Definir correctamente los permisos de los usuarios mediante un modelo de acceso como RBAC y aplicar mecanismos Zero Trust.                                                                |

| **Campo**    | **Contenido**                                                                                                     |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| ID           | W-16                                                                                                              |
| Descripción  | El `sid` puede ser declarado mediante la URL y acceder a una sesión existente desde otro navegador o dispositivo. |
| Activo       |                                                                                                                   |
| Amenaza      |                                                                                                                   |
| Impacto      |                                                                                                                   |
| Probabilidad |                                                                                                                   |
| Riesgo       |                                                                                                                   |
| Control      | Crear un `sid` distinto por cada inicio de sesión y bloquear el uso del mismo mediante modificación de la URL.    |

| **Campo**    | **Contenido**                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-17                                                                                                                                        |
| Descripción  | Las preferencias utilizan `pickle` para serializarse, posteriormente se almacenan en una cookie que el usuario puede editar de forma libre. |
| Activo       |                                                                                                                                             |
| Amenaza      |                                                                                                                                             |
| Impacto      |                                                                                                                                             |
| Probabilidad |                                                                                                                                             |
| Riesgo       |                                                                                                                                             |
| Control      | No usar pickle en casos donde los datos provengan del usuario. Validar entradas y utilizar JSON.                                            |

| **Campo**    | **Contenido**                                                                       |
| ------------ | ----------------------------------------------------------------------------------- |
| ID           | W-18                                                                                |
| Descripción  | El certificado digital venció el 31 de enero del 2024.                              |
| Activo       |                                                                                     |
| Amenaza      |                                                                                     |
| Impacto      |                                                                                     |
| Probabilidad |                                                                                     |
| Riesgo       |                                                                                     |
| Control      | Implementar mecanismos que alerten antes de su expiración y renovar el certificado. |

| **Campo**    | **Contenido**                                                          |
| ------------ | ---------------------------------------------------------------------- |
| ID           | W-19                                                                   |
| Descripción  | La página permite negociar TLS 1.1 con cifrado `ECDHE-RSA-AES256-SHA`. |
| Activo       |                                                                        |
| Amenaza      |                                                                        |
| Impacto      |                                                                        |
| Probabilidad |                                                                        |
| Riesgo       |                                                                        |
| Control      | Forzar TLS 1.2/1.3 únicamente.                                         |


| **Campo**    | **Contenido**                                                                                |
| ------------ | -------------------------------------------------------------------------------------------- |
| ID           | W-20                                                                                         |
| Descripción  | Hay una única fuente de logs, y esta solo presenta evidencia de visualizaciones en facturas. |
| Activo       |                                                                                              |
| Amenaza      |                                                                                              |
| Impacto      |                                                                                              |
| Probabilidad |                                                                                              |
| Riesgo       |                                                                                              |
| Control      |                                                                                              |