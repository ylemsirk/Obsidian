| Campo        | Contenido                                                         |
| ------------ | ----------------------------------------------------------------- |
| ID           | N-01                                                              |
| Descripción  | No se exige inicio de sesión en el puerto consola del `SW-IDF01`. |
| Activo       |                                                                   |
| Amenaza      |                                                                   |
| Impacto      | (5) Crítico                                                       |
| Probabilidad | (4) Alta                                                          |
| Riesgo       | (20) Crítico                                                      |
| Control      |                                                                   |

| Campo        | Contenido                                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-02                                                                                                                                                    |
| Descripción  | Todos los puertos de `SW-IDF0` se encuentran en la VLAN1. Hay una segmentación nula. Toda la red está bajo el mismo dominio de broadcast (máscara /16). |
| Activo       |                                                                                                                                                         |
| Amenaza      |                                                                                                                                                         |
| Impacto      | (4) Alto                                                                                                                                                |
| Probabilidad | (4) Alta                                                                                                                                                |
| Riesgo       | (16) Alto                                                                                                                                               |
| Control      |                                                                                                                                                         |

| Campo        | Contenido                                                            |
| ------------ | -------------------------------------------------------------------- |
| ID           | N-03                                                                 |
| Descripción  | Ausencia total de `port-security` en todos los puertos de `SW-IDF01` |
| Activo       |                                                                      |
| Amenaza      |                                                                      |
| Impacto      | (3) Medio                                                            |
| Probabilidad | (4) Alta                                                             |
| Riesgo       | (12) Alto                                                            |
| Control      |                                                                      |

| Campo        | Contenido                                                                                                         |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| ID           | N-04                                                                                                              |
| Descripción  | Toda la red se queda inoperable cuando se apaga el `SW-CORE`. Hay un único punto de fallo y una nula redundancia. |
| Activo       |                                                                                                                   |
| Amenaza      |                                                                                                                   |
| Impacto      | (5) Crítico                                                                                                       |
| Probabilidad | (4) Alta                                                                                                          |
| Riesgo       | (20) Crítico                                                                                                      |
| Control      |                                                                                                                   |

| Campo        | Contenido    |
| ------------ | ------------ |
| ID           | N-05         |
| Descripción  |              |
| Activo       |              |
| Amenaza      |              |
| Impacto      | (5) Crítico  |
| Probabilidad | (5) Alta     |
| Riesgo       | (25) Crítico |
| Control      |              |

| Campo        | Contenido                                                                                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-06                                                                                                                                                                        |
| Descripción  | El SSH dentro del `SW-CORE` es bastante vulnerable a ataques de diccionario debido a su contraseña débil `admin123`. También, no bloquea los intentos repetidos de ingreso. |
| Activo       |                                                                                                                                                                             |
| Amenaza      |                                                                                                                                                                             |
| Impacto      | (5) Crítico                                                                                                                                                                 |
| Probabilidad | (4) Alta                                                                                                                                                                    |
| Riesgo       | (20) Crítico                                                                                                                                                                |
| Control      |                                                                                                                                                                             |

| Campo        | Contenido                    |
| ------------ | ---------------------------- |
| ID           | N-07                         |
| Descripción  | El AP `AP-P1-CORP` cuenta co |
| Activo       |                              |
| Amenaza      |                              |
| Impacto      | (5) Crítico                  |
| Probabilidad | (5) Crítica                  |
| Riesgo       | (25) Crítico                 |
| Control      |                              |

| Campo        | Contenido                                                                              |
| ------------ | -------------------------------------------------------------------------------------- |
| ID           | N-08                                                                                   |
| Descripción  | Un servidor Rogue DHCP puede conectarse al `SW-IDF01` y crear pools sin restricciones. |
| Activo       |                                                                                        |
| Amenaza      |                                                                                        |
| Impacto      | (4) Alto                                                                               |
| Probabilidad | (3) Media                                                                              |
| Riesgo       | (12) Alto                                                                              |
| Control      |                                                                                        |