# Manual Técnico

## Práctica 1 -- Diseño e Implementación de Red LAN

### Redes de Computadoras 1

### Universidad San Carlos de Guatemala

### Facultad de Ingeniería

### Ingeniería en Ciencias y Sistemas

------------------------------------------------------------------------

# 1. Información General

**Estudiante:** Estuardo Josué Vaquiax Reyes\
**Carnet:** 202201336\
**Red Base:** 192.178.36.0/24\
**Máscara de Subred:** 255.255.255.0\
**Simulador Utilizado:** Cisco Packet Tracer\
**Modelo de Switch:** Cisco 2960

------------------------------------------------------------------------

# 2. Descripción General del Proyecto

Se diseñó e implementó una red LAN para la empresa Constructiva S.A.,
distribuida en un edificio corporativo de tres niveles.

La topología fue desarrollada en Cisco Packet Tracer, aplicando:

-   Principios de cableado estructurado TIA/EIA-568B
-   Direccionamiento IPv4 estático
-   Configuración básica de switches mediante CLI
-   Organización visual por departamentos
-   Verificación de conectividad total mediante pruebas de ping
-   Análisis de paquetes ARP e ICMP en modo simulación

------------------------------------------------------------------------

# 3. Diseño de la Topología

## 3.1 Distribución por Pisos

### Piso 1 -- Recepción y Administración (30 equipos)

-   Recepción
-   Contabilidad
-   Legal
-   Sala de Reuniones

### Piso 2 -- Diseño Arquitectónico y Urbanismo (17 equipos)

-   Arquitectura
-   Urbanismo
-   Sala de revisión de planos

### Piso 3 -- Ingeniería y Dirección de Proyectos (13 equipos)

-   Dirección General
-   Ingeniería Civil
-   Departamento de Servidores Principales

Cada piso cuenta con un switch principal que distribuye la conexión
hacia los switches de cada departamento.

------------------------------------------------------------------------

## 3.2 Imagen General de la Topología

![Topologia](./images/topologia3.png)
*Figura 1. Topología piso 1.*
![Topologia](./images/topologia2.png)
*Figura 2. Topología piso 1.*
![Topologia](./images/topologia3.png)
*Figura 3. Topología piso 2.*
![Topologia](./images/topologia4.png)
*Figura 4. Topología piso 3.*


------------------------------------------------------------------------

# 4. Cableado Estructurado

Se aplicó el estándar TIA/EIA-568B de la siguiente manera:

-   Cable Straight-Through:
    -   PC → Switch
    -   Laptop → Switch
    -   Servidor → Switch
-   Cable Crossover:
    -   Switch principal ↔ Switch de departamento
    -   Switch principal ↔ Switch principal

------------------------------------------------------------------------

# 5. Configuración de Switches

## 5.1 Comandos Utilizados

    enable
    configure terminal
    hostname NOMBRE_DEL_SWITCH
    enable secret 202201336
    line console 0
    password 202201336
    login
    exit
    exit
    write memory

## 5.2 Evidencia de Configuración

![Topologia](./images/cli.png)
*Figura 5. Configuración del switch 1 SW_L1.*

------------------------------------------------------------------------

# 6. Asignación de Direcciones IP

Red utilizada:

192.178.36.0/24

No se configuró gateway debido a que la red funciona dentro de una sola
subred sin router.

## 6.1 Tabla de Direccionamiento IP
### Ejemplos

  Dispositivo   Departamento             IP
  ------------- ------------------------ --------------
  PC1           Recepción                192.178.36.6
  Server1       Recepción                192.178.36.17
  PC            Contabilidad             192.178.36.23
  PC            Legal                    192.178.36.22
  PC            Arquitectura             192.178.36.13
  Server        Urbanismo                192.178.36.44
  PC            Dirección                192.178.36.45
  Server        Ingeniería               192.178.36.56
  Server        Servidores Principales   192.178.36.35



------------------------------------------------------------------------

# 7. Evidencia de Configuración en Equipos Finales

![Topologia](./images/ip1.png)
![Topologia](./images/ip2.png)
![Topologia](./images/ip3.png)
![Topologia](./images/ip4.png)
![Topologia](./images/ip5.png)
![Topologia](./images/ip6.png)
![Topologia](./images/ip7.png)
![Topologia](./images/ip8.png)
![Topologia](./images/ip9.png)
![Topologia](./images/ip10.png)
------------------------------------------------------------------------

# 8. Pruebas de Conectividad

![Topologia](./images/c1.png)
![Topologia](./images/c2.png)
![Topologia](./images/c3.png)
![Topologia](./images/c4.png)
![Topologia](./images/c5.png)
![Topologia](./images/c6.png)
![Topologia](./images/c7.png)
![Topologia](./images/c8.png)
![Topologia](./images/c9.png)
![Topologia](./images/c10.png)

------------------------------------------------------------------------

# 9. Análisis en Modo Simulación

## 9.1 Evidencia ARP

![Topologia](./images/arp.png)

## 9.2 Evidencia ICMP

![Topologia](./images/icmp.png)

------------------------------------------------------------------------

# 10. Cumplimiento de Requisitos

-   Diseño completo y organizado 
-   Configuración CLI en switches 
-   Asignación correcta de IPs 
-   Conectividad total verificada 
-   Aplicación correcta del estándar TIA/EIA-568B 
-   Documentación técnica en formato Markdown 

------------------------------------------------------------------------

# 11. Conclusiones

La red LAN fue implementada exitosamente cumpliendo con todos los
requerimientos establecidos en el enunciado.\
Se logró conectividad total entre dispositivos y una correcta
documentación técnica del proyecto.

------------------------------------------------------------------------
