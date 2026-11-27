
| Campo        | Contenido                                                                                             |
| ------------ | ----------------------------------------------------------------------------------------------------- |
| ID           | N-01                                                                                                  |
| Descripción  | No se exige inicio de sesión en el puerto consola del `SW-IDF01`.                                     |
| Activo       | Switch `SW-IDF01` y su configuración                                                                  |
| Amenaza      | Visitante o empleado con acceso a físico al switch.                                                   |
| Impacto      | (5) Crítico                                                                                           |
| Probabilidad | (4) Alta                                                                                              |
| Riesgo       | (20) Crítico                                                                                          |
| Control      | Configurar la interfaz de consola para que exija una contraseña robusta al momento de iniciar sesión. |

| Campo        | Contenido                                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-02                                                                                                                                                    |
| Descripción  | Todos los puertos de `SW-IDF0` se encuentran en la VLAN1. Hay una segmentación nula. Toda la red está bajo el mismo dominio de broadcast (máscara /16). |
| Activo       | Infraestructura completa de red.                                                                                                                        |
| Amenaza      | Cualquier máquina atacante o malware que esté dentro de la red.                                                                                         |
| Impacto      | (5) Crítico                                                                                                                                             |
| Probabilidad | (4) Alta                                                                                                                                                |
| Riesgo       | (20) Crítico                                                                                                                                            |
| Control      | Aplicar VLANs según su uso o departamento.                                                                                                              |

| Campo        | Contenido                                                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-03                                                                                                                                               |
| Descripción  | Ausencia total de `port-security` en todos los puertos de `SW-IDF01`.                                                                              |
| Activo       | Puertos en `SW-IDF01`.                                                                                                                             |
| Amenaza      | Atacante queriendo ocasionar una denegación de servicio mediante MAC Flooding.                                                                     |
| Impacto      | (3) Medio                                                                                                                                          |
| Probabilidad | (4) Alta                                                                                                                                           |
| Riesgo       | (12) Alto                                                                                                                                          |
| Control      | Aplicar `port-security` con `violation restrict`, `mac-address sticky` y `maximum 1` en todos sus puertos y apagar los que no se están utilizando. |

| Campo        | Contenido                                                                                                         |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| ID           | N-04                                                                                                              |
| Descripción  | Toda la red se queda inoperable cuando se apaga el `SW-CORE`. Hay un único punto de fallo y una nula redundancia. |
| Activo       | Operabilidad de la empresa.                                                                                       |
| Amenaza      | Personal de limpieza o empleado desconectando el switch de su fuente de poder.                                    |
| Impacto      | (5) Crítico                                                                                                       |
| Probabilidad | (4) Alta                                                                                                          |
| Riesgo       | (20) Crítico                                                                                                      |
| Control      | Añadir un stack de switches.                                                                                      |

| Campo        | Contenido                                                                                                              |
| ------------ | ---------------------------------------------------------------------------------------------------------------------- |
| ID           | N-05                                                                                                                   |
| Descripción  | Todo contacto con el internet se corta si se apaga el `RTR-BORDE`. Hay un único punto de fallo y una nula redundancia. |
| Activo       | Disponibilidad de los servicios que ofrece la empresa.                                                                 |
| Amenaza      | ISP con fallas de conectividad.                                                                                        |
| Impacto      | (5) Crítico                                                                                                            |
| Probabilidad | (5) Crítico                                                                                                            |
| Riesgo       | (25) Crítico                                                                                                           |
| Control      | Añadir un segundo router borde utilizando otro proveedor.                                                              |

| Campo        | Contenido                                                                                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-06                                                                                                                                                                        |
| Descripción  | El SSH dentro del `SW-CORE` es bastante vulnerable a ataques de diccionario debido a su contraseña débil `admin123`. También, no bloquea los intentos repetidos de ingreso. |
| Activo       | `SW-CORE` y su configuración.                                                                                                                                               |
| Amenaza      | Atacante realizando ataques de fuerza bruta o de diccionario para obtener acceso remoto al switch.                                                                          |
| Impacto      | (5) Crítico                                                                                                                                                                 |
| Probabilidad | (4) Alta                                                                                                                                                                    |
| Riesgo       | (20) Crítico                                                                                                                                                                |
| Control      | Utilizar contraseñas robustas a la hora de configurar SSH. Limitar la cantidad de intentos fallidos y solo admitir el acceso a las VLANs designadas.                        |

| Campo        | Contenido                                                                                                                                                           |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-07                                                                                                                                                                |
| Descripción  | El AP `AP-P1-CORP`, encargado de proveer la red `DINA-CORP` cuenta con una contraseña sumamente débil (`password`) y un estándar de seguridad obsoleto (`WPA-TKIP`) |
| Activo       | Red inalámbrica `DINA-CORP`.                                                                                                                                        |
| Amenaza      | Atacante realizando ataques de fuerza bruta o de diccionario para ingresar a la red corporativa.                                                                    |
| Impacto      | (5) Crítico                                                                                                                                                         |
| Probabilidad | (5) Crítica                                                                                                                                                         |
| Riesgo       | (25) Crítico                                                                                                                                                        |
| Control      | Migrar a WPA2-Enterprise como mínimo o WPA3-Enterprise. Y aplicar una buena configuración en el servidor RADIUS.                                                    |

| Campo        | Contenido                                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-08                                                                                                                                                             |
| Descripción  | Un servidor Rogue DHCP puede conectarse al `SW-IDF01` y crear pools sin restricciones.                                                                           |
| Activo       | Configuración IP de la red y sus equipos.                                                                                                                        |
| Amenaza      | Atacante conectando un servidor DHCP malicioso para realizar ataques como DNS spoofing o MitM.                                                                   |
| Impacto      | (4) Alto                                                                                                                                                         |
| Probabilidad | (3) Media                                                                                                                                                        |
| Riesgo       | (12) Alto                                                                                                                                                        |
| Control      | Aplicar `DHCP Snooping` en el switch `SW-IDF01` y solo utilizar `trust` en el puerto correspondiente donde se tiene la conexión hacia el servidor DHCP legítimo. |

| Campo        | Contenido                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------ |
| ID           | N-09                                                                                       |
| Descripción  | El servidor web se encuentra dentro de la red interna, exponiendo toda la red al internet. |
| Activo       | Servidor Web, portal web,                                                                  |
| Amenaza      | Atacante que aprovechó vulnerabilidades en la página web y obtuvo acceso al servidor.      |
| Impacto      | (5) Crítico                                                                                |
| Probabilidad | (3) Media                                                                                  |
| Riesgo       | (15) Alto                                                                                  |
| Control      | Implementar una DMZ, el uso de NGFW y WAFs con configuraciones estrictas.                  |

| Campo        | Contenido                                                                                                                    |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| ID           | N-10                                                                                                                         |
| Descripción  | Un AP malicio (Evil Twin) puede conectarse al `SW-IDF01` y crear una red inalámbrica con el mismo SSID que una red legítima. |
| Activo       | Información que pasa por el AP.                                                                                              |
| Amenaza      | Atacante que realiza un ataque MitM en busca de obtener información sensible.                                                |
| Impacto      | (5) Crítico                                                                                                                  |
| Probabilidad | (3) Media                                                                                                                    |
| Riesgo       | (15) Alto                                                                                                                    |
| Control      | Establecer autenticación 802.1X, IDS/IPS Inalámbricos y activar PMF para evitar ataques de desautenticación.                 |