
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

| **Campo**    | **Contenido**                                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | W-04                                                                                                                                   |
| Descripción  | Se muestran mensajes de error explícitos (como consultas SQL) dentro del modo debug de Flask cuando el campo recibe datos inesperados. |
| Activo       |                                                                                                                                        |
| Amenaza      |                                                                                                                                        |
| Impacto      | Alto                                                                                                                                   |
| Probabilidad | Alta                                                                                                                                   |
| Riesgo       | Muy Alto.                                                                                                                              |
| Control      |                                                                                                                                        |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-05          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

| **Campo**    | **Contenido** |
| ------------ | ------------- |
| ID           | W-06          |
| Descripción  |               |
| Activo       |               |
| Amenaza      |               |
| Impacto      |               |
| Probabilidad |               |
| Riesgo       |               |
| Control      |               |

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
