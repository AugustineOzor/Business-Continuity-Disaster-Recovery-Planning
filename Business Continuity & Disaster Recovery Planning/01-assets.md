# 🗂️ Assets

> 6 systems in scope for the Business Impact Analysis, covering the supervisory control, recovery, and communications chain behind CriticalOps' water and power operations.

| # | Name | Type | Classification | Environment | Owner |
|---|---|---|---|---|---|
| 1 | SCADA Master Control Server | Server | ![Critical](https://img.shields.io/badge/class-Critical-b60205) | ![Production](https://img.shields.io/badge/env-Production-28a745) | OT Engineering Team |
| 2 | SCADA Master Control Server (DR Site) | Server | ![Critical](https://img.shields.io/badge/class-Critical-b60205) | ![DR](https://img.shields.io/badge/env-DR-6f42c1) | OT Engineering Team |
| 3 | Process Historian Database | Database | ![High](https://img.shields.io/badge/class-High-e36209) | ![Production](https://img.shields.io/badge/env-Production-28a745) | OT Engineering Team |
| 4 | Substation Communications Gateway | Network Device | ![Critical](https://img.shields.io/badge/class-Critical-b60205) | ![Production](https://img.shields.io/badge/env-Production-28a745) | Grid Operations |
| 5 | Treatment Plant HMI Workstations | Endpoint | ![High](https://img.shields.io/badge/class-High-e36209) | ![Production](https://img.shields.io/badge/env-Production-28a745) | Water Operations |
| 6 | Offsite SCADA Configuration Backup Store | Data Store | ![High](https://img.shields.io/badge/class-High-e36209) | ![DR](https://img.shields.io/badge/env-DR-6f42c1) | IT Infrastructure |

## 1. SCADA Master Control Server

**Type:** Server &nbsp;·&nbsp; **Classification:** ![Critical](https://img.shields.io/badge/class-Critical-b60205) &nbsp;·&nbsp; **Environment:** ![Production](https://img.shields.io/badge/env-Production-28a745)  
**Owner:** OT Engineering Team

**Description**  
Primary SCADA master station that polls field devices and issues supervisory commands across water treatment facilities and power grid substations serving 10M+ citizens. Loss of this server means loss of supervisory control, making it the anchor system for the Business Impact Analysis and the tightest RTO in scope.

---

## 2. SCADA Master Control Server (DR Site)

**Type:** Server &nbsp;·&nbsp; **Classification:** ![Critical](https://img.shields.io/badge/class-Critical-b60205) &nbsp;·&nbsp; **Environment:** ![DR](https://img.shields.io/badge/env-DR-6f42c1)  
**Owner:** OT Engineering Team

**Description**  
Standby SCADA master at the secondary control site, kept in sync with production and intended to take over supervisory control on failover. Its replication lag and failover time directly determine the achievable RTO and RPO for the whole SCADA platform.

---

## 3. Process Historian Database

**Type:** Database &nbsp;·&nbsp; **Classification:** ![High](https://img.shields.io/badge/class-High-e36209) &nbsp;·&nbsp; **Environment:** ![Production](https://img.shields.io/badge/env-Production-28a745)  
**Owner:** OT Engineering Team

**Description**  
Time-series database recording sensor readings, alarms, and operator actions from water and grid operations. Supports regulatory reporting, incident forensics, and trend analysis; data loss here sets the RPO conversation, though real-time control continues without it.

---

## 4. Substation Communications Gateway

**Type:** Network Device &nbsp;·&nbsp; **Classification:** ![Critical](https://img.shields.io/badge/class-Critical-b60205) &nbsp;·&nbsp; **Environment:** ![Production](https://img.shields.io/badge/env-Production-28a745)  
**Owner:** Grid Operations

**Description**  
Industrial gateway aggregating RTU and IED communications from power substations back to the control center over dedicated links. A failure severs visibility and remote control of the affected substations, so it carries one of the shortest tolerable outage windows.

---

## 5. Treatment Plant HMI Workstations

**Type:** Endpoint &nbsp;·&nbsp; **Classification:** ![High](https://img.shields.io/badge/class-High-e36209) &nbsp;·&nbsp; **Environment:** ![Production](https://img.shields.io/badge/env-Production-28a745)  
**Owner:** Water Operations

**Description**  
Operator human-machine interface workstations used to monitor and manually control treatment processes (chlorination, filtration, pumping). Operators can fall back to local manual control, but sustained loss degrades response speed and raises safety risk.

---

## 6. Offsite SCADA Configuration Backup Store

**Type:** Data Store &nbsp;·&nbsp; **Classification:** ![High](https://img.shields.io/badge/class-High-e36209) &nbsp;·&nbsp; **Environment:** ![DR](https://img.shields.io/badge/env-DR-6f42c1)  
**Owner:** IT Infrastructure

**Description**  
Offsite encrypted repository holding PLC logic, SCADA configuration exports, and system images needed to rebuild the control environment. Recovery from a major outage depends on these backups being current and restorable, which makes backup age and restore testing central to the RPO definition.

---


---

<div align="center">

[← Overview](README.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Risk Register →](02-risk-register.md)

</div>
