# Práctica 1 – Diseño e Implementación de Red LAN  
## Redes de Computadoras 1  
### Universidad San Carlos de Guatemala  
### Facultad de Ingeniería  
### Ingeniería en Ciencias y Sistemas  

---

## 📌 Información del Estudiante

- **Nombre:** Estuardo Vaquiax  
- **Carnet:** 202201336  
- **Semestre:** 1S-2026  
- **Curso:** Redes de Computadoras 1  

---

## 🏢 Descripción del Proyecto

En esta práctica se diseñó e implementó una red LAN para la empresa **Constructiva S.A.**, simulando un edificio corporativo de tres niveles.

La red fue desarrollada en **Cisco Packet Tracer**, aplicando:

- Direccionamiento IPv4 estático
- Configuración de switches mediante CLI
- Cableado estructurado bajo el estándar TIA/EIA-568B
- Organización visual por departamentos
- Verificación de conectividad total mediante pruebas de ping
- Análisis de paquetes ARP e ICMP en modo simulación

---

## 🧱 Estructura de la Red

El edificio está dividido en:

### Piso 1 – Recepción y Administración
- Recepción
- Contabilidad
- Legal
- Sala de Reuniones

### Piso 2 – Diseño Arquitectónico y Urbanismo
- Arquitectura
- Urbanismo
- Sala de revisión de planos

### Piso 3 – Ingeniería y Dirección
- Dirección General
- Ingeniería Civil
- Departamento de Servidores Principales

Cada piso cuenta con un switch principal que interconecta los switches departamentales.

---

## 🌐 Configuración de Red

- **Red Base:** 192.178.36.0/24  
- **Máscara:** 255.255.255.0  
- **Direccionamiento:** Estático  
- **Modelo de Switch:** Cisco 2960  

Todos los switches fueron configurados mediante CLI con:

- Hostname personalizado
- Contraseña de acceso (carnet)
- Guardado de configuración

---

## 📁 Contenido del Repositorio

Practica1/
│
├── Topologia_Practica1.pkt
├── Manual Tecnico.md
└── imagenes/