## **DINA** (**D**ina **I**s **N**ot **A**ltice).
##### Empresa mediana de telecomunicaciones dominicana.

**Ofrece:**
- Servicios de telefonía móvil (voz, SMS y datos móviles en 4G/5G).
- Servicios de telefonía fija (voz tradicional e IP).
- Acceso a Internet fijo (FTTH e Internet inalámbrico).
- Almacenamiento en la nube (Aún en proceso).

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

**Red Fija (Fibra Óptica):**
- OLT
- ODN
- 5GC
- EPC
- BNG

**Infraestructura para Almacenamiento en la Nube:**
- Servidores de Almacenamiento.
- Data Centers.
- Aplicaciones web, iOS y Android.

**Aplicaciones B2C:**
- App Móvil (Mi Dina) y Portal Web (Página: www.dina.com.do).
- Pasarelas de pago.
- Canales de Atención Omnicanal: Chatbots con IA (Peldet) y Zendesk.

##### Proveedores Mayoristas y Regulatorios

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

## Topología Lógica

- 1 VLAN por piso, presenta congestión continua. 
- Stateless Firewalls con reglas flojas.
- Protocolos de acceso remoto abiertos en sus puertos por default.
- WPA-TKIP en todas las redes inalámbricas de la compañía



## Topología Física



## Observaciones importantes
- Monitoreo de red pobre o nulo
- Documentación inexistente sobre el proceso de diseño de los servidores web
- Falta de HSTS
- Certificado caducado hace 2 meses
- TLS 1.1
- Base de datos y datos en reposo en texto plano
- IRP, BCP, RPO, RTO y DRP inexistentes
- Gestión de parches y actualizaciones deficiente
- 