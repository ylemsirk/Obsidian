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
| Descripción  | El directorio `/cloud` y sus subdirectorios son expuestos mediante un listado de directorios.                                                        |
| Activo       | Directorio `/cloud` Información dentro de dichos directorios. Como: credenciales, exportaciones, información sensible de red, etc.                   |
| Amenaza      | Atacante no autorizado realizando pruebas de reconocimiento activo.                                                                                  |
| Impacto      | (5) Crítico. Se exponen credenciales y exportaciones de clientes                                                                                     |
| Probabilidad | (5) Crítica                                                                                                                                          |
| Riesgo       | (25) Crítico                                                                                                                                         |
| Control      | Deshabilitar listado de directorios, exigir autenticación y únicamente proveer al usuario los archivos que pidió (dentro del marco de autorización). |

| **Campo**    | **Contenido**                                                                                                                                                                                     |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-03                                                                                                                                                                                              |
| Descripción  | Se muestran mensajes de error explícitos (como consultas SQL) dentro del modo debug de Flask cuando el campo recibe datos inesperados.                                                            |
| Activo       | Herramienta de manejo de errores de Flask.                                                                                                                                                        |
| Amenaza      | Atacante probando distintas entradas o caracteres en busca de obtener información sobre vulnerabilidades.                                                                                         |
| Impacto      | (3) Medio. Los mensajes de error pueden dar información extra que puede ser utilizada para ataques futuros.                                                                                       |
| Probabilidad | (4) Alta.                                                                                                                                                                                         |
| Riesgo       | (12) Alto.                                                                                                                                                                                        |
| Control      | Convertir el parámetro `debug` de  `True` a `False` cuando se esté fuera del entorno de desarrollo local, y reservar detalles técnicos para logs internos en lugar de mostrarlos ante el usuario. |

| **Campo**    | **Contenido**                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------- |
| ID           | W-04                                                                                                            |
| Descripción  | La cuenta `admin` se mantuvo con una contraseña (admin123) por default desde su creación.                       |
| Activo       | Cuenta administrativa.                                                                                          |
| Amenaza      | Atacante haciendo uso de ataques de diccionario.                                                                |
| Impacto      | (5) Crítico. Permite acceder a usuarios no autorizados con permisos administrativos.                            |
| Probabilidad | (5) Crítica. Estas cuentas suelen ser las más atacadas debido a sus privilegios.                                |
| Riesgo       | (25) Muy Crítico                                                                                                |
| Control      | Reemplazar inmediatamente la contraseña a una más robusta, y evitar usar contraseñas débiles o predeterminadas. |

| **Campo**    | **Contenido**                                                                                            |
| ------------ | -------------------------------------------------------------------------------------------------------- |
| ID           | W-05                                                                                                     |
| Descripción  | El formulario de login interpreta ciertos inputs como consultas SQL, y concatena username y password     |
| Activo       | Base de datos de usuarios y formulario de login.                                                         |
| Amenaza      | Atacante buscando saltarse el proceso de autenticación para obtener acceso a las cuentas.                |
| Impacto      | (5) Crítico. Permite acceder a usuarios no autorizados a cualquier cuenta solo con el nombre de usuario. |
| Probabilidad | (5) Crítica.                                                                                             |
| Riesgo       | (25) Crítico                                                                                             |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                               |

| **Campo**    | **Contenido**                                                                                                       |
| ------------ | ------------------------------------------------------------------------------------------------------------------- |
| ID           | W-06                                                                                                                |
| Descripción  | El parametro `q` se concatena en una clausula `LIKE` dentro del formulario perteneciente a la Base de conocimiento. |
| Activo       | Búsqueda en la Base de conocimiento.                                                                                |
| Amenaza      | Atacante buscando extraer información de la base de datos.                                                          |
| Impacto      | (5) Crítico. Permite extraer datos de la bases de datos mediante `UNION`.                                           |
| Probabilidad | (4) Alta.                                                                                                           |
| Riesgo       | (20) Crítico                                                                                                        |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                                          |

| **Campo**    | **Contenido**                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-07                                                                                                                                                 |
| Descripción  | Los datos de la base de datos de usuarios están almacenados en texto plano.                                                                          |
| Activo       | Base de datos de usuarios                                                                                                                            |
| Amenaza      | Atacante con acceso a la información de la base de datos que puede realizar exfiltración de datos.                                                   |
| Impacto      | (5) Crítico                                                                                                                                          |
| Probabilidad | (4) Alta                                                                                                                                             |
| Riesgo       | (20) Crítico                                                                                                                                         |
| Control      | Utilizar algoritmos de hashing robustos como Argon2 o bcrypt que traen salting nativamente para codificar los datos sensibles en las bases de datos. |

| **Campo**    | **Contenido**                                                                                               |
| ------------ | ----------------------------------------------------------------------------------------------------------- |
| ID           | W-08                                                                                                        |
| Descripción  | Ejecución XSS reflejado dentro de la barra de búsqueda del apartado `Base de conocimiento`.                 |
| Activo       | Barra de búsqueda y formulario.                                                                             |
| Amenaza      |                                                                                                             |
| Impacto      | (4) Alto                                                                                                    |
| Probabilidad | (3) Media                                                                                                   |
| Riesgo       | (12) Alta                                                                                                   |
| Control      | Implementar conversión de caracteres especiales (`<, >, &, ", ')`) a entidades  seguras y validar entradas. |

| **Campo**    | **Contenido**                                                                                                  |
| ------------ | -------------------------------------------------------------------------------------------------------------- |
| ID           | W-09                                                                                                           |
| Descripción  | Ejecución XSS almacenado dentro del formulario a la descripción de problemas del apartado `Soporte y tickets`. |
| Activo       | Formulario de `Soporte y tickets`.                                                                             |
| Amenaza      |                                                                                                                |
| Impacto      | (4) Alto                                                                                                       |
| Probabilidad | (4) Alta                                                                                                       |
| Riesgo       | (16) Alto                                                                                                      |
| Control      | Implementar conversión de caracteres especiales (`<, >, &, ", ')`) a entidades  seguras y validar entradas.    |

| **Campo**    | **Contenido**                                                                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-10                                                                                                                                                                                        |
| Descripción  | El formulario del apartado `Diagnóstico de conexión` recibe entradas del usuario, las concatena con un ping y las ejecuta en el contexto del sistema operativo.                             |
| Activo       | Herramienta de diagnóstico de red                                                                                                                                                           |
| Amenaza      | Atacante utilizando la herramienta de diagnóstico para ejecutar comandos shell.                                                                                                             |
| Impacto      | (5) Crítica                                                                                                                                                                                 |
| Probabilidad | (4) Alta                                                                                                                                                                                    |
| Riesgo       | (20) Crítico                                                                                                                                                                                |
| Control      | Evitar la ejecución de comandos del sistema operativo y usar APIs en su lugar. Verificar la identidad y permisos del usuario antes de ingresar al apartado o al momento de enviar comandos. |

| **Campo**    | **Contenido**                                                                                                                           |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-11                                                                                                                                    |
| Descripción  | Versiones atrasadas de dependencias/herramientas como `Flask`, `Werkzeug`, `wheel`, `pip`, etc.                                         |
| Activo       | Herramientas utilizadas en el desarrollo de la página web.                                                                              |
| Amenaza      | Atacante investigando y aprovechando vulnerabilidades conocidas sobre las versiones desactualizadas de las dependencias y herramientas. |
| Impacto      | (4) Alto                                                                                                                                |
| Probabilidad | (4) Alta                                                                                                                                |
| Riesgo       | (16) Alto                                                                                                                               |
| Control      | Actualizar `pip`, las dependencias y cualquier herramienta siendo utilizada en el desarrollo de la página web.                          |

| **Campo**    | **Contenido**                                                                                                                            |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-12                                                                                                                                     |
| Descripción  | Aún cuando el servidor recibe numerosos intentos de sesión, no bloquea o limita las peticiones.                                          |
| Activo       | Formulario de login.                                                                                                                     |
| Amenaza      | Atacante realizando ataques de autenticación como: ataques de fuerza bruta, ataques de diccionario, password spraying, etc.              |
| Impacto      | (4) Alto                                                                                                                                 |
| Probabilidad | (5) Crítica                                                                                                                              |
| Riesgo       | (20) Crítico                                                                                                                             |
| Control      | Aplicar rate limiting, bloquear la cuenta después de 3 intentos fallidos, implementar métodos de autenticación multifactor y un CAPTCHA. |

| **Campo**    | **Contenido**                                                                                                               |
| ------------ | --------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-13                                                                                                                        |
| Descripción  | La ruta `/admin` únicamente verifica si un usuario ha sido autenticado aún si la cuenta no pertenece a algún administrador. |
| Activo       | Panel administrativo y ruta `/admin`.                                                                                       |
| Amenaza      | Empleado o cliente malicioso con cuenta comprometida.                                                                       |
| Impacto      | (5) Crítico                                                                                                                 |
| Probabilidad | (5) Crítico                                                                                                                 |
| Riesgo       | (25) Crítico                                                                                                                |
| Control      | Aplicar políticas Zero Trust y cambiar a un modelo de control de acceso basado en roles (RBAC).                             |

| **Campo**    | **Contenido**                                                                                                                            |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-14                                                                                                                                     |
| Descripción  | Ausencia de autenticación multifactor para todas las cuentas.                                                                            |
| Activo       | Portal completo.                                                                                                                         |
| Amenaza      | Atacante que haya obtenido las credenciales de algún usuario mediante filtraciones de datos, escaneo de tráfico, uso de keyloggers, etc. |
| Impacto      | (4) Alto. Con una contraseña filtrada basta para ingresar a la cuenta.                                                                   |
| Probabilidad | (4) Alta                                                                                                                                 |
| Riesgo       | (4) Alto                                                                                                                                 |
| Control      | Considerar implementación de Active Directory                                                                                            |

| **Campo**    | **Contenido**                                                                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-15                                                                                                                                                                                        |
| Descripción  | Cualquier usuario puede acceder a una factura que no le corresponden con solo hacer cambios en la URL ya que no se verifica la identidad del usuario para acceder a recursos ajenos (IDOR). |
| Activo       | Facturas y datos sensibles de usuarios.                                                                                                                                                     |
| Amenaza      | Cliente o empleado malicioso.                                                                                                                                                               |
| Impacto      | (4) Alto                                                                                                                                                                                    |
| Probabilidad | (4) Alta                                                                                                                                                                                    |
| Riesgo       | (16) Alto                                                                                                                                                                                   |
| Control      | Definir correctamente los permisos de los usuarios mediante un modelo de acceso como RBAC y aplicar mecanismos Zero Trust.                                                                  |

| **Campo**    | **Contenido**                                                                                                     |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| ID           | W-16                                                                                                              |
| Descripción  | El `sid` puede ser declarado mediante la URL y acceder a una sesión existente desde otro navegador o dispositivo. |
| Activo       | Gestión de sesiones y cuentas autenticadas.                                                                       |
| Amenaza      | Un atacante que conozca alguna sid para ser reutilizada con fines maliciosos.                                     |
| Impacto      | (5) Crítico                                                                                                       |
| Probabilidad | (4) Alta                                                                                                          |
| Riesgo       | (20) Crítico                                                                                                      |
| Control      | Crear un `sid` distinto por cada inicio de sesión y bloquear el uso del mismo mediante modificación de la URL.    |

| **Campo**    | **Contenido**                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-17                                                                                                                                        |
| Descripción  | Las preferencias utilizan `pickle` para serializarse, posteriormente se almacenan en una cookie que el usuario puede editar de forma libre. |
| Activo       | Configuración de `Flask` y las cookies de preferencias.                                                                                     |
| Amenaza      | Atacante que busque ejecutar comandos al deserializar los datos dentro del servidor.                                                        |
| Impacto      | (5) Crítico.                                                                                                                                |
| Probabilidad | (3) Media                                                                                                                                   |
| Riesgo       | (15) Alto                                                                                                                                   |
| Control      | No usar pickle en casos donde los datos provengan del usuario. Validar entradas y utilizar JSON.                                            |

| **Campo**    | **Contenido**                                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-18                                                                                                                          |
| Descripción  | El certificado digital venció el 31 de enero del 2024.                                                                        |
| Activo       | Certificado TLS y confianza de usuarios.                                                                                      |
| Amenaza      | Atacante                                                                                                                      |
| Impacto      | (4) Alta. Los navegadores pueden bloquear la conexión o mostrar una advertencia, afectando negativamente a la disponibilidad. |
| Probabilidad | (5) Crítica                                                                                                                   |
| Riesgo       | (20) Crítico                                                                                                                  |
| Control      | Implementar mecanismos que alerten antes de su expiración y renovar el certificado.                                           |

| **Campo**    | **Contenido**                                                             |
| ------------ | ------------------------------------------------------------------------- |
| ID           | W-19                                                                      |
| Descripción  | La página permite negociar TLS 1.1 con cifrado `ECDHE-RSA-AES256-SHA`.    |
| Activo       | Comunicaciones entre clientes y servidor. Configuración TLS del servidor. |
| Amenaza      | Atacante                                                                  |
| Impacto      | (3) Medio                                                                 |
| Probabilidad | (3) Media                                                                 |
| Riesgo       | (9) Medio                                                                 |
| Control      | Forzar TLS 1.2/1.3 únicamente.                                            |


| **Campo**    | **Contenido**                                                                                                                |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-20                                                                                                                         |
| Descripción  | Hay una única fuente de logs, y esta solo presenta evidencia de visualizaciones en facturas.                                 |
| Activo       | Logs de los eventos ocurridos en la página.                                                                                  |
| Amenaza      | Atacante que realice acciones maliciosas hacia la página las cuales no serán registradas.                                    |
| Impacto      | (4) Alto                                                                                                                     |
| Probabilidad | (4) Alta                                                                                                                     |
| Riesgo       | (16) Alta                                                                                                                    |
| Control      | Implementar sistemas de seguridad integrada como SIEMs, EDRs, etc. Centralizar los logs en un servidor dedicado y protegido. |

8, 9, 10