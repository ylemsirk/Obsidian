## **DINA** (**D**ina **I**s **N**ot **A**ltice).
##### Empresa mediana de telecomunicaciones dominicana.

**Ofrece:**
- Servicios de telefonía móvil (voz, SMS y datos móviles en 4G/5G).
- Servicios de telefonía fija (voz tradicional e IP).
- Acceso a Internet fijo (FTTH e Internet inalámbrico).
- Almacenamiento en la nube (Se encuentra en fase piloto).

**Modelo de negocio:** 
- Orientación a B2C
- Dependencias y relaciones B2B 

**Modelo de seguridad:**
- DAC

**Genera ingresos mediante:**
- Tarifas y planes de suscripción
- Cobros por consumo

##### Componentes principales de la infraestructura de Red:

**Réd Móvil (4G/5G):** 
- RAN: Antenas, torres de transmisión y estaciones base.
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
- App Móvil (Mi Dina) y Portal Web (Página: www.dina.com.do).
- Pasarelas de pago. (servicios externos)
- Canales de Atención Omnicanal: Chatbots con IA (Peldet) y Zendesk.

##### Relaciones empresariales

**Tránsito IP:**
- Lumen

**Interconexión Local:**
- Acuerdos entre Claro, Altice y Viva.

**Licencias y concesiones de espectro radioeléctrico y numeración:**
- INDOTEL

##### Manejo de datos

**Datos que circulan entre los sistemas:**
- Tráfico de usuario
- Datos de señalización y control
- Datos transaccionales y de gestión
- Datos regulatorios e interconexión

**Quiénes los utilizan:**
- Núcleo de red
- Sistemas de facturación
- Sistemas de atención al cliente
- Usuarios a través de "Mi Dina" y el Portal Web

**Dónde se almacenan:**
- Data Centers
- Registros de Red
- Pasarelas de Pago

## Observaciones importantes
- Monitoreo de red pobre o nulo. Cantidad considerable de puntos ciegos.
- Los únicos logs generados se encuentran en el servidor del área de facturación y finanzas.
- Carencia de sistemas de seguridad integrada como SIEMs, SOARs, EDRs, etc.
- Documentación inexistente sobre el proceso de diseño de los servidores web.
- Falta de HSTS.
- Certificado web caducado hace 2 meses.
- El servidor web utiliza TLS 1.1.
- Base de datos y datos en reposo en texto plano en cada dispositivo de la empresa.
- Carencia de planes de respuesta y continuidad, RPO, RTO y sin pruebas de recuperación.
- Gestión de parches y actualizaciones deficiente.
- Falta de inventario de versiones y firmware
- Red plana (Un solo dominio de broadcast [Segmentación nula]), presenta congestión continua y cuellos de botella 0 segmentación. 
- Toda la red utiliza la VLAN 1.
- Redundancia nula, depende sustancialmente del switch central. Contiene un único router de borde.
- Stateless Firewall dentro del router borde y reglas permisivas que no contienen políticas restrictivas de conexiones de entrada o salida.
- Protocolos de acceso remoto abiertos en sus puertos por default.
- WPA-TKIP en todas las redes inalámbricas de la compañía.
- Servidor web alojado en la LAN interna.
- Ausencia de Port Security.
- DHCP Snooping deshabilitado
- Ausencia de Dynamic ARP Inspection.
- Cuarto de servidores con pobre sistema de ventilación y enfriamiento y puerta de madera con candado desgastado.
- El único guardia de seguridad se encuentra en la entrada del edificio.
- Ausencia de QoS para teléfonos IP que ocasiona jitters, altos niveles de latencia y bajo throughput.
- Puertos de switch sin usar habilitados
- Ausencia de 802.1X
- Telnet habilitado.
- 