# Corporate Campus LAN Infrastructure Design — Constructiva S.A.

Academic project developed for the **Computer Networks 1** course at the Universidad de San Carlos de Guatemala (First Semester 2026).

This repository contains the design, structured cabling plan, IPv4 addressing scheme, and Cisco switch configurations for an enterprise 3-story corporate building network modeled in **Cisco Packet Tracer**.

---

## Overview

The network serves multiple corporate departments organized across three distinct floors. The topology incorporates strict TIA/EIA-568B cabling standards, static IPv4 subnet allocation, hierarchical switch interconnection using Cisco Catalyst 2960 switches, and connectivity verification through packet-level ARP and ICMP tracing.

---

## Topology Structure

- **Floor 1 (Reception and Administration):** Reception, Accounting, Legal Department, and Main Conference Hall.
- **Floor 2 (Architectural Design and Urbanism):** Architecture Lab, Urban Planning Department, Blueprint Review Room.
- **Floor 3 (Engineering and Executive Management):** Executive Directorate, Civil Engineering Department, and Primary Data Center / Server Room.

Each level features a designated distribution switch routing departmental access switches back to the primary building backbone.

---

## Key Features

- Structured IPv4 base subnetting (`192.178.36.0/24`) with static gateway and endpoint mappings
- Command-line switch provisioning with encrypted access passwords and customized hostnames
- Packet-level validation covering full ARP resolution cycles and ICMP round-trip latency checks
- Technical manual with complete switch CLI configurations and verification screenshots

---

## Technologies

- Cisco Packet Tracer
- Hardware Emulated: Cisco Catalyst 2960 Switches
- Standards: TIA/EIA-568B Structured Cabling, IPv4, ARP, ICMP

---

## Repository Structure

```
Redes1_1S_2026_202201336/
├── Practica1/
│   ├── Topologia_Practica1.pkt    # Cisco Packet Tracer simulation
│   ├── Manual_Tecnico.md          # Technical documentation
│   └── imagenes/                  # Verification evidence and topology diagrams
├── Practica2/                     # Practice 2 lab files
├── Proyecto1/                     # Course Project 1 files
├── Proyecto2/                     # Course Project 2 files
└── README.md
```

---

## Academic Context

| Field       | Detail                                         |
|-------------|------------------------------------------------|
| Course      | Computer Networks 1 (REDES1)                   |
| Institution | Universidad de San Carlos de Guatemala         |
| Semester    | First Semester 2026                            |
| Author      | Estuardo Josue Vaquiax Reyes (202201336)       |
