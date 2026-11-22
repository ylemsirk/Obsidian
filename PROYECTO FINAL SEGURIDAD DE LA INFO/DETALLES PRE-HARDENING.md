# **DINA** (**D**ina **I**s **N**ot **A**ltice).
### Empresa mediana de telecomunicaciones Full MVNO dominicana.

<hr>

**Ofrece:**
- Servicios de telefonía móvil (voz, SMS y datos móviles en 4G/5G).
- Servicios de telefonía fija (voz tradicional e IP).
- Acceso a Internet fijo (FTTH).
- Almacenamiento en la nube (Se encuentra en fase piloto).

**Modelo de negocio:** 
- Orientación a B2C
- Dependencias y relaciones B2B 

**Modelo de control de acceso:**
- DAC

**Genera ingresos mediante:**
- Tarifas y planes de suscripción
- Cobros por consumo

#### Componentes principales de la infraestructura de Red:

**Réd Móvil (4G/5G):** 
- EPC (4G LTE): Núcleo responsable de la tecnología 4G.
- 5GC: Núcleo responsable de la tecnología 5G.
- IMS

**Red Fija (Fibra Óptica):**
- ONT/ONU
- ODN
- OLT
- BNG

**Infraestructura para Almacenamiento en la Nube:**
- Servidores de Almacenamiento.
- Data Centers.
- Aplicaciones web, iOS y Android.

**Aplicaciones B2C:**
- Portal Web (Página: www.dina.test).
- Pasarelas de pago. (servicios externos)
- Canales de Atención Omnicanal: Chatbots con IA (Peldet) y Zendesk.

#### Relaciones empresariales

**Tránsito IP:**
- Lumen

**Interconexión Local:**
- MNO Anfitrión.

**Licencias y concesiones de espectro radioeléctrico y numeración:**
- INDOTEL

#### Manejo de datos

**Datos que circulan entre los sistemas:**
- Tráfico de usuario
- Datos de señalización y control
- Datos transaccionales y de gestión
- Datos regulatorios e interconexión

**Quiénes los utilizan:**
- Núcleo de red
- Sistemas de facturación
- Sistemas de atención al cliente
- Usuarios a través del Portal Web

**Dónde se almacenan:**
- Data Centers
- Registros de Red
- Sistemas de logs.
- Proveedores externos.

<hr>

### Infraestructura de red

#### Topología Lógica

| Fase | Modelo en PT | Nombre exacto | IP / máscara / gateway |
|---|---|---|---|
| 1 Internet | Router 1941 | `ISP-LUMEN` | Gi0/0 203.0.113.1/30, Gi0/1 198.51.100.1/24 |
| 1 | Switch 2960-24TT | `SW-INTERNET` | sin IP |
| 1 | Server-PT | `SRV-PELDET` | 198.51.100.10/24, gw .1 |
| 1 | Server-PT | `SRV-ZENDESK` | 198.51.100.11/24, gw .1 |
| 1 | Server-PT | `SRV-PAGOS` | 198.51.100.12/24, gw .1 |
| 1 | PC-PT | `PC-ATACANTE` | 198.51.100.50/24, gw .1 |
| 2 Borde y core (Piso 2) | WRT300N | `RTR-BORDE` | LAN 192.168.0.1/16, WAN 203.0.113.2/30, gw 203.0.113.1 |
| 2 | Switch 2960-24TT | `SW-CORE` | VLAN1: 192.168.0.2/16 |
| 3 Servidores (Piso 2) | Server-PT | `SRV-DHCP` | 192.168.0.10/16, gw 192.168.0.1 |
| 3 | Server-PT | `SRV-DNS` | 192.168.0.11/16 |
| 3 | Server-PT | `SRV-WEB` | 192.168.0.12/16 |
| 3 | Server-PT | `SRV-DB` | 192.168.0.13/16 |
| 4 Piso 1 | Switch 2960-24TT | `SW-IDF01` | VLAN1: 192.168.0.3/16 |
| 4 | PC-PT | `PC-CS-01`, `PC-CS-02` | DHCP |
| 4 | PC-PT | `PC-FIN-01`, `PC-FIN-02` | DHCP |
| 4 | IP Phone 7960 | `TEL-CS-01`, `TEL-FIN-01` | DHCP |
| 4 | Server-PT | `SRV-LOGS` | 192.168.0.14/16 |
| 5 Piso 3 | Switch 2960-24TT | `SW-IDF03` | VLAN1: 192.168.0.4/16 |
| 5 | PC-PT | `PC-IT-01`, `PC-IT-02`, `PC-ADM-01` | DHCP |
| 5 | IP Phone 7960 | `TEL-ADM-01` | DHCP |
| 6 Wi-Fi (Piso 1) | Access Point-PT | `AP-P1-CORP` (SSID `DINA-CORP`) | sin IP |
| 6 | Access Point-PT | `AP-P1-GUEST` (SSID `DINA-GUEST`) | sin IP |
| 6 | Laptop-PT | `LAP-CORP-01` | DHCP |
| 6 | Smartphone-PT | `CEL-GUEST-01` | DHCP |


![[PROYECTO FINAL SEGURIDAD DE LA INFO/Pasted image 20261119221334.png]]
#### Topología Física

**Piso 1: Atención al Cliente y Finanzas:**
- Estaciones de trabajo
- Teléfonos IP
- Impresoras
- Access Points
- Armario de telecomunicaciones IDF-01
- Switch de acceso

**Piso 2: Data Center:**
- Racks de servidores.
- Core Switch.
- Router de borde.
- Paneles de parcheo.
- UPS.
- Sistema de vigilancia.

**Piso 3: IT y Administración:**
- Puestos de trabajo.
- Impresoras.
- Teléfonos IP.
- Armario de telecomunicaciones IDF-03.
- Switch de acceso.

**Conexiones verticales**
- Fibra óptica entre el Data Center y los IDF.
- Cableado estructurado hacia cada puesto de trabajo.
- Una sola ruta de cableado entre pisos en el escenario inicial.
- Ausencia de una ruta alternativa de conectividad.

<hr>

### Vulnerabilidades encontradas

#### Red
- Monitoreo de red pobre o nulo. Cantidad considerable de puntos ciegos.
- Red plana 192.168.0.0/16 (Un solo dominio de broadcast.[Segmentación nula]), presenta congestión continua y cuellos de botella 0 segmentación. 
- Toda la red utiliza la VLAN 1.
- Redundancia nula, depende sustancialmente del switch central. Contiene un único router de borde.
- Protocolos (SSH, Telnet y RDP) de acceso remoto abiertos en sus puertos por default.
- WPA-TKIP en todas las redes inalámbricas de la compañía.
- Servidor web alojado en la LAN interna.
- Ausencia de Port Security.
- DHCP Snooping deshabilitado.
- Ausencia de Dynamic ARP Inspection.
- Ausencia de QoS para teléfonos IP.
- Puertos de switch sin usar habilitados.
- Ausencia de 802.1X.
- Telnet habilitado.

#### Técnicas
- La base de datos guarda todos los datos en texto plano
- Datos en reposo en texto plano en cada dispositivo de la empresa.
- Carencia de planes de respuesta y continuidad, RPO, RTO y sin pruebas de recuperación.
- Gestión de parches y actualizaciones deficiente.
- El último backup de las configuraciones de red y la base de datos se realizó hace 4 meses.
- Los únicos logs generados se encuentran en el servidor del área de facturación y finanzas.
- Carencia de sistemas de seguridad integrada como SIEMs, SOARs, EDRs, etc.

#### Físicas
- Cuarto de servidores con pobre sistema de ventilación y enfriamiento y puerta de madera con candado desgastado.
- El único guardia de seguridad se encuentra en la entrada del edificio.
- Cámaras con puntos ciegos.
- Racks sin cerraduras.
- Ausencia de sensores de temperatura en el Data Center y cuartos de telecomunicaciones por piso.
- UPS insuficiente, la energía proveída solo dura 30 minutos. 
- Personal de limpieza y visitantes con acceso libre.
- Cableados sin protección.

#### Operacionales
- Contraseñas débiles o predeterminadas en los dispositivos de la infraestructura.
- No existe algún inventario actualizado de activos tecnológicos.
- No hay políticas de gestión de configuraciones.
- Los backups se almacenan en la misma infraestructura productiva.
- No existe una matriz formal de responsabilidades de seguridad.
- Ausencia de Active Directory.

#### Página web
Tras distintas pruebas de penetración, se llegó a la conclusión de que dentro de la página web se encontraban cada una de las 10 categorías más comunes de vulnerabilidades en páginas web según la lista OWASP Top 10:2025.

**[A01:2025] Broken Access Control:** 
- CWE-639: Permite a usuarios no autorizados modificar parámetros en peticiones HTTP, URLs y cookies para obtener acceso a información confidencial.

**[A02:2025] Security Misconfiguration:** 
- Se omite la cabecera HSTS.
- CWE-548: El listado de directorios se mantiene activo. 
- CWE-1392: Las cuentas administradoras poseen los nombres y contraseñas por defecto.

**[A03:2025] Software Supply Chain Failures:** 
- CWE-1395: Dependencia de terceros vulnerables.

**[A04:2025] Cryptographic Failures:** 
- CWE-327: El servidor web utiliza TLS 1.1. 
- CWE-256: Las contraseñas se guardan en texto plano.

**[A05:2025] Injection:** 
- CWE-89: La base de datos interpreta algunos inputs como consultas SQL. 
- CWE-79: Permite XSS mediante la barra de búsqueda.
- CWE-78: OS Command Injection.

**[A06:2025] Insecure Design:** 
- CWE-1053: Documentación inexistente sobre el proceso de diseño de los servidores web. 
- CWE-770: No se contemplaron los límites de peticiones.

**[A07:2025] Authentication Failures:** 
- CWE-307: Permite intentos ilimitados de contraseña.
- CWE-308: Ausencia de MFA.
- CWE-384: Mantiene el mismo ID de sesión activo después de un inicio de sesión.

**[A08:2025] Software or Data Integrity Failures:** 
- CWE-502: Permite deserealización insegura

**[A09:2025] Security Logging and Alerting Failures:**
- CWE-778: Logs de cualquier índole sin guardar.

**[A10:2025] Mishandling of Exceptional Conditions:**
- CWE-209: Mensajes de error demasiado detallados.


