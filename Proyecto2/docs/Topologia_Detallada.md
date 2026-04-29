# Topología Detallada – Proyecto 2: BanTech GT

## 1. Introducción
Este documento describe **paso a paso** la topología física y lógica de la red multisede para BanTech GT, siguiendo los requerimientos del enunciado y usando tu carnet 202201336 (XX=36, Y=6). Cada dispositivo, conexión, tipo de cable y puerto está especificado para facilitar la implementación y documentación posterior.

---

## 2. Nomenclatura General
- **Routers:** R-[Sede] (ej. R-Occidente)
- **Switches Multicapa:** MS[No]-[Sede] (ej. MS1-Oriente)
- **Switches de Acceso:** SW[No]-[Sede] (ej. SW1-Norte)
- **Servidores:** SRV-[Función]-[Sede] (ej. SRV-BD-Central)
- **PCs:** PC[No]-[Área]-[Sede] (ej. PC1-Cajas-Occidente)

---

## 3. Backbone Core (Núcleo Nacional)
### Dispositivos
- 3 Routers Cisco 2911: R-Core1, R-Core2, R-Core3
- 1 Switch Multicapa Cisco 3560: MS-Backbone

### Conexiones
- **R-Core1 <-> R-Core2:**
  - Tipo de cable: Fibra óptica (Cable de fibra óptica)
  - Puertos: G0/1 <-> G0/1
- **R-Core2 <-> R-Core3:**
  - Tipo de cable: Ethernet (Cable cruzado)
  - Puertos: G0/2 <-> G0/2
- **R-Core3 <-> R-Core1:**
  - Tipo de cable: Serial (Cable serial DCE)
  - Puertos: S0/0/0 <-> S0/0/0
- **Todos los routers al MS-Backbone:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/0 de cada router <-> G1/0/1, G1/0/2, G1/0/3 del switch

### Justificación
- El anillo garantiza redundancia total y tolerancia a fallos.
- Diferentes medios físicos simulan escenarios reales de conectividad WAN y LAN.

---

## 4. Sede Occidente (Agencia Regional Comercial)
### Dispositivos
- 1 Router Cisco 2911: R-Occidente
- 2 Switches de Acceso Cisco 2960: SW1-Occidente, SW2-Occidente
- 4 PCs: PC1-Cajas, PC2-Asesores, PC3-Gerencia, PC4-Seguridad

### Conexiones
- **R-Occidente <-> SW1-Occidente:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/1 <-> F0/1
- **SW1-Occidente <-> SW2-Occidente:**
  - Tipo de cable: Ethernet (Cable troncal cruzado)
  - Puertos: F0/24 <-> F0/24
- **PCs a SW2-Occidente:**
  - PC1-Cajas: F0/2
  - PC2-Asesores: F0/3
  - PC3-Gerencia: F0/4
  - PC4-Seguridad: F0/5
  - Tipo de cable: Ethernet (Cable directo)

### Justificación
- Dos switches permiten segmentar áreas críticas y facilitan la administración con VTP.
- El trunk entre switches soporta VLANs y redundancia local.

---

## 5. Sede Norte (Centro de Autorización de Créditos)
### Dispositivos
- 1 Router Cisco 2911: R-Norte
- 3 Switches de Acceso Cisco 2960: SW1-Norte, SW2-Norte, SW3-Norte
- 3 PCs: PC1-Analisis, PC2-Auditoria, PC3-Legal

### Conexiones
- **R-Norte <-> SW1-Norte:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/1 <-> F0/1
- **SW1-Norte <-> SW2-Norte:**
  - Tipo de cable: Ethernet (Cable cruzado)
  - Puertos: F0/24 <-> F0/24
- **SW2-Norte <-> SW3-Norte:**
  - Tipo de cable: Ethernet (Cable cruzado)
  - Puertos: F0/23 <-> F0/23
- **SW3-Norte <-> SW1-Norte:**
  - Tipo de cable: Ethernet (Cable cruzado)
  - Puertos: F0/22 <-> F0/22
- **PCs a SW2-Norte:**
  - PC1-Analisis: F0/2
  - PC2-Auditoria: F0/3
  - PC3-Legal: F0/4
  - Tipo de cable: Ethernet (Cable directo)

### Justificación
- Topología en anillo para redundancia de capa 2.
- Rapid PVST+ y root bridge forzado en SW1-Norte.

---

## 6. Sede Oriente (Centro Financiero Legado)
### Dispositivos
- 2 Switches Multicapa Cisco 3560: MS1-Oriente, MS2-Oriente
- 2 Switches de Acceso Cisco 2960: SW1-Oriente, SW2-Oriente
- 2 PCs: PC1-Boveda, PC2-Plataforma

### Conexiones
- **MS1-Oriente <-> MS2-Oriente:**
  - Tipo de cable: Ethernet (Cable cruzado)
  - Puertos: G0/2 <-> G0/2
- **MS1-Oriente <-> SW1-Oriente:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/1 <-> F0/1
- **MS2-Oriente <-> SW2-Oriente:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/1 <-> F0/1
- **SW1-Oriente <-> SW2-Oriente:**
  - Tipo de cable: Ethernet (Cable cruzado)
  - Puertos: F0/24 <-> F0/24
- **PCs a SW1-Oriente:**
  - PC1-Boveda: F0/2
  - PC2-Plataforma: F0/3
  - Tipo de cable: Ethernet (Cable directo)

### Justificación
- Dos switches multicapa permiten HSRP/VRRP para alta disponibilidad de gateway.
- Conexión redundante entre switches de acceso y multicapa.

---

## 7. Data Center y Sede Central (Alta Seguridad)
### Dispositivos
- 2 Routers Cisco 2911: R-Central1, R-Central2
- 2 Switches de Distribución Cisco 3560: DSW1-Central, DSW2-Central
- 2 Switches de Acceso Cisco 2960: SW1-Central, SW2-Central
- 3 Servidores: SRV-BD, SRV-Web, SRV-NOC

### Conexiones
- **R-Central1 <-> DSW1-Central:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/1 <-> G0/1
- **R-Central2 <-> DSW2-Central:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/1 <-> G0/1
- **DSW1-Central <-> SW1-Central:**
  - Tipo de cable: EtherChannel (2 cables Ethernet directos)
  - Puertos: F0/21, F0/22 <-> F0/21, F0/22
- **DSW2-Central <-> SW2-Central:**
  - Tipo de cable: EtherChannel (2 cables Ethernet directos)
  - Puertos: F0/23, F0/24 <-> F0/23, F0/24
- **Servidores a SW1-Central:**
  - SRV-BD: F0/2
  - SRV-Web: F0/3
  - SRV-NOC: F0/4
  - Tipo de cable: Ethernet (Cable directo)

### Justificación
- EtherChannel previene cuellos de botella y asegura redundancia física.
- Segmento aislado para seguridad y control de tráfico.

---

## 8. Conexión de Sedes al Backbone
- **Cada router de sede (R-Occidente, R-Norte, R-Central2) se conecta al backbone:**
  - Tipo de cable: Ethernet (Cable directo)
  - Puertos: G0/0 de cada router de sede <-> G1/0/4, G1/0/5, G1/0/6 del MS-Backbone

---

## 9. Notas Finales
- Todos los cables deben ser **nombrados** en Packet Tracer según origen-destino (ej. R-Occidente_G0/1_to_SW1-Occidente_F0/1).
- Todos los dispositivos deben tener **hostname** configurado según la nomenclatura.
- Documenta cualquier cambio físico en este archivo para mantener trazabilidad.

---

**¡Sigue este archivo al pie de la letra para construir la topología completa y facilitar la documentación y configuración posterior!**
