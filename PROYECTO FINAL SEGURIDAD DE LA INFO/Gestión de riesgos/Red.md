
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



| VLAN | Nombre      | Red                 | Gateway      | Función                                                         |
| ---- | ----------- | ------------------- | ------------ | --------------------------------------------------------------- |
| 10   | SERVERS     | 10.10.10.0/24       | 10.10.10.1   | `SRV-DHCP`, `SRV-DNS`, `SRV-DB`, `SRV-RADIUS`                   |
| 20   | CS          | 10.10.20.0/24       | 10.10.20.1   | PCs de Atención al Cliente (Piso 1)                             |
| 21   | FINANZAS    | 10.10.21.0/24       | 10.10.21.1   | PCs de Finanzas + `SRV-LOGS` (Piso 1)                           |
| 30   | VOZ         | 10.10.30.0/24       | 10.10.30.1   | Teléfonos IP de Piso 1 y Piso 3 (VLAN auxiliar de voz)          |
| 40   | IT\_ADMIN   | 10.10.40.0/24       | 10.10.40.1   | PCs de IT y Administración (Piso 3)                             |
| 50   | WIFI\_CORP  | 10.10.50.0/24       | 10.10.50.1   | Clientes Wi-Fi corporativos (`DINA-CORP`)                       |
| 60   | WIFI\_GUEST | 10.10.60.0/24       | 10.10.60.1   | Clientes Wi-Fi de invitados (`DINA-GUEST`), aislada del resto   |
| 99   | MGMT        | 10.10.99.0/29       | 10.10.99.1   | Gestión de switches y APs                                       |
| 100  | DMZ         | 172.16.100.0/24     | 172.16.100.1 | `SRV-WEB`, colgado del NGFW, fuera de la LAN interna            |
| 999  | PARKING     | (sin red)           | —            | Puertos sin usar, en `shutdown`                                 |
| 1    | nativa      | (sin uso operativo) | —            | No se asigna a ningún dispositivo real; queda vacía a propósito |

| Fase                  | Modelo           | Nombre exacto                       | VLAN                     | IP / máscara / gateway                                           |
| --------------------- | ---------------- | ----------------------------------- | ------------------------ | ---------------------------------------------------------------- |
| 1 Internet            | Router 1941      | `ISP-LUMEN`                         | —                        | Gi0/0 203.0.113.1/30, Gi0/1 198.51.100.1/24                      |
| 1                     | Router 1941      | `ISP-ALTERNO` (nuevo)               | —                        | Gi0/0 203.0.113.5/30, Gi0/1 198.51.100.1/24                      |
| 1                     | Switch 2960-24TT | `SW-INTERNET`                       | —                        | sin IP                                                           |
| 1                     | Server-PT        | `SRV-PELDET`                        | —                        | 198.51.100.10/24, gw .1                                          |
| 1                     | Server-PT        | `SRV-ZENDESK`                       | —                        | 198.51.100.11/24, gw .1                                          |
| 1                     | Server-PT        | `SRV-PAGOS`                         | —                        | 198.51.100.12/24, gw .1                                          |
| 2 Perímetro (Piso 2)  | ASA5505          | `NGFW-BORDE-01` (nuevo)             | —                        | Outside 203.0.113.2/30, DMZ 172.16.100.1/24, Inside 10.10.5.1/30 |
| 2                     | ASA5505          | `NGFW-BORDE-02` (nuevo)             | —                        | Outside 203.0.113.6/30, Inside 10.10.5.5/30                      |
| 2                     | Switch 2960-24TT | `SW-DMZ` (nuevo)                    | 100                      | 172.16.100.2/24                                                  |
| 2                     | Server-PT        | `SRV-WEB` (reubicado)               | 100                      | 172.16.100.10/24, gw 172.16.100.1                                |
| 3 Core (Piso 2)       | 3650-24PS        | `SW-CORE-01` (antes `SW-CORE`)      | 99                       | 10.10.99.2/29 — hace inter-VLAN routing                          |
| 3                     | 3650-24PS        | `SW-CORE-02` (nuevo)                | 99                       | miembro del mismo stack que `SW-CORE-01`                         |
| 4 Servidores (Piso 2) | Server-PT        | `SRV-DHCP`                          | 10                       | 10.10.10.10/24, gw 10.10.10.1                                    |
| 4                     | Server-PT        | `SRV-DNS`                           | 10                       | 10.10.10.11/24, gw 10.10.10.1                                    |
| 4                     | Server-PT        | `SRV-DB`                            | 10                       | 10.10.10.13/24, gw 10.10.10.1                                    |
| 4                     | Server-PT        | `SRV-RADIUS` (nuevo)                | 10                       | 10.10.10.14/24, gw 10.10.10.1                                    |
| 5 Piso 1              | Switch 2960-24TT | `SW-IDF01`                          | 99 (troncal 20,21,30,99) | 10.10.99.3/29                                                    |
| 5                     | PC-PT            | `PC-CS-01`, `PC-CS-02`              | 20                       | DHCP                                                             |
| 5                     | PC-PT            | `PC-FIN-01`, `PC-FIN-02`            | 21                       | DHCP                                                             |
| 5                     | IP Phone 7960    | `TEL-CS-01`                         | 30                       | DHCP                                                             |
| 5                     | IP Phone 7960    | `TEL-FIN-01`                        | 30                       | DHCP                                                             |
| 5                     | Server-PT        | `SRV-LOGS`                          | 21                       | 10.10.21.14/24, gw 10.10.21.1                                    |
| 6 Piso 3              | Switch 2960-24TT | `SW-IDF03`                          | 99 (troncal 40,30,99)    | 10.10.99.4/29                                                    |
| 6                     | PC-PT            | `PC-IT-01`, `PC-IT-02`, `PC-ADM-01` | 40                       | DHCP                                                             |
| 6                     | IP Phone 7960    | `TEL-ADM-01`                        | 30                       | DHCP                                                             |
| 7 Wi-Fi (Piso 1)      | Access Point-PT  | `AP-P1-CORP` (SSID `DINA-CORP`)     | 50                       | sin IP — WPA2/3-Enterprise contra `SRV-RADIUS`                   |
| 7                     | Access Point-PT  | `AP-P1-GUEST` (SSID `DINA-GUEST`)   | 60                       | sin IP                                                           |
| 7                     | Laptop-PT        | `LAP-CORP-01`                       | 50                       | DHCP                                                             |
| 7                     | Smartphone-PT    | `CEL-GUEST-01`                      | 60                       | DHCP                                                             |
