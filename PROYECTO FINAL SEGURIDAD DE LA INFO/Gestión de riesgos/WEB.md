
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
| Descripción  |                                                                                                      |
| Activo       | Formulario de login.                                                                                 |
| Amenaza      |                                                                                                      |
| Impacto      | Crítico. Permite acceder a usuarios no autorizados a cualquier cuenta solo con el nombre de usuario. |
| Probabilidad | Alta.                                                                                                |
| Riesgo       | Alto-Crítico                                                                                         |
| Control      | Implementar consultas parametrizadas dentro del código y validar entradas.                           |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-07          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-08          |
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
