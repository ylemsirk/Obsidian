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
- 5GC: Núcleo responsable de la tecnología 45.
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
- Portal Web (Página: www.dina.com.do).
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
- Pasarelas de Pago

<hr>

### Infraestructura de red

#### Topología Lógica
(PROX. detalles de conexiones, dispositivos y simulación en Packet Tracer)

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
- Stateless Firewall dentro del router borde y reglas permisivas que no contienen políticas restrictivas de conexiones de entrada o salida.
- Toda la red utiliza la VLAN 1.
- Redundancia nula, depende sustancialmente del switch central. Contiene un único router de borde.
- Protocolos de acceso remoto abiertos en sus puertos por default.
- WPA-TKIP en todas las redes inalámbricas de la compañía.
- Servidor web alojado en la LAN interna.
- Ausencia de Port Security.
- DHCP Snooping deshabilitado.
- Ausencia de Dynamic ARP Inspection.
- Ausencia de QoS para teléfonos IP que ocasiona jitters, altos niveles de latencia y bajo throughput.
- Puertos de switch sin usar habilitados.
- Ausencia de 802.1X.
- Telnet habilitado.

#### Técnicas
- Base de datos y datos en reposo en texto plano en cada dispositivo de la empresa.
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
Tras distintas pruebas de penetración, se llegó a la conclusión de que dentro de la página web se encontraban cada una de las 10 vulnerabilidades más comunes en páginas web según la lista OWASP Top 10:2025.

**[A01:2025] Broken Access Control:** 
- Permite a usuarios no autorizados modificar parámetros en peticiones HTTP, URLs y cookies para obtener acceso a información confidencial.
- No bloquea curls de dichas páginas confidenciales.

**[A02:2025] Security Misconfiguration:** 
- Se omite la cabecera HSTS, el listado de directorios se mantiene activo. 
- Las cuentas administradoras poseen los nombres y contraseñas por defecto.

**[A03:2025] Software Supply Chain Failures:** 
- Peldet.

**[A04:2025] Cryptographic Failures:** 
- Certificado web caducado hace 2 meses. 
- El servidor web utiliza TLS 1.1. 
- Las contraseñas se guardan en texto plano.

**[A05:2025] Injection:** 
- La base de datos interpreta algunos inputs como consultas SQL. 
- Permite XSS mediante la barra de búsqueda.
- OS Command Injection.

**[A06:2025] Insecure Design:** 
- Documentación inexistente sobre el proceso de diseño de los servidores web. 
- No se contemplaron los límites de peticiones.
- Posee ausencia de alta disponibilidad y distribución de tráfico.

**[A07:2025] Authentication Failures:** 
- Permite intentos ilimitados de contraseña.
- Ausencia de MFA.
- Mantiene el mismo ID de sesión activo después de un inicio de sesión.

**[A08:2025] Software or Data Integrity Failures:** 
- Permite deserealización insegura

**[A09:2025] Security Logging and Alerting Failures:**
- Logs de cualquier índole sin guardar.
- Inexistencia de alertas.

**[A10:2025] Mishandling of Exceptional Conditions:**
- CWE-209: Mensajes de error demasiado detallados.


**1. Adquisición de clientes**
1. El cliente solicita un servicio.
2. Atención al cliente registra sus datos y contrato.
3. CRM genera el perfil del cliente.
4. BSS registra el plan contratado.


**2. Provisión de telefonía móvil**
1. El cliente adquiere una SIM.
2. DINA registra la suscripción en sus sistemas.
3. Se asocian los identificadores del abonado y el perfil de servicio.
4. La infraestructura del MNO proporciona conectividad radioeléctrica.
5. DINA administra las funciones de su red móvil conforme a su arquitectura Full MVNO.

**3. Provisión de Internet FTTH**
1. El cliente solicita Internet.
2. Se verifica la disponibilidad de cobertura.
3. Se genera una orden de instalación.
4. Un técnico instala y registra la ONT.
5. Se configura el servicio mediante los sistemas de aprovisionamiento.

**4. Consumo y facturación**
1. Los sistemas generan registros de consumo y eventos de servicio.
2. Charging calcula el consumo correspondiente.
3. Billing genera la factura.
4. El cliente recibe la notificación de pago.
5. La transacción se procesa mediante una pasarela externa.

**5. Atención al cliente**
1. El cliente presenta una consulta o reclamación.
2. Zendesk registra el caso.
3. Peldet puede intervenir como chatbot.
4. El empleado consulta los sistemas autorizados.
5. Se documenta y cierra el incidente.

**6. Almacenamiento cloud**

1. El cliente solicita espacio.
    
2. Se crea una cuenta o espacio de almacenamiento.
    
3. Se asigna una cuota.
    
4. Se configuran permisos de acceso.
    
5. Se registran operaciones y eventos de almacenamiento.
    

Activos: plataforma cloud, identidades, almacenamiento y registros.