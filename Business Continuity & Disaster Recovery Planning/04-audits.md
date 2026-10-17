# 🔍 Audits

> 4 audits sequenced from target-setting through recoverability testing, failover proof, and external assurance.

| # | Audit | Type | Status | Lead | Findings | Dates |
|---|---|---|---|---|---|---|
| 1 | BIA and RTO/RPO Validation Self-Assessment | ![Self-Assessment](https://img.shields.io/badge/type-Self--Assessment-6a737d) | ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09) | Augustine Ozor | 0 | 2026-10-01 → 2026-11-15 |
| 2 | SCADA Backup and Restore Readiness Review | ![Internal](https://img.shields.io/badge/type-Internal-0366d6) | ![Completed](https://img.shields.io/badge/status-Completed-28a745) | Internal Audit Team | 3 | 2026-08-17 → 2026-09-11 |
| 3 | Annual DR Failover Exercise Audit | ![Internal](https://img.shields.io/badge/type-Internal-0366d6) | ![Planned](https://img.shields.io/badge/status-Planned-6a737d) | Internal Audit Team | 0 | 2027-02-01 → 2027-02-26 |
| 4 | ISO 27001 Surveillance Audit: Business Continuity Controls | ![External](https://img.shields.io/badge/type-External-6f42c1) | ![Planning](https://img.shields.io/badge/status-Planning-0366d6) | Certification body lead auditor (to be assigned) | 0 | 2027-03-08 → 2027-03-12 |

## 1. BIA and RTO/RPO Validation Self-Assessment

**Type:** ![Self-Assessment](https://img.shields.io/badge/type-Self--Assessment-6a737d) &nbsp;·&nbsp; **Status:** ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09) &nbsp;·&nbsp; **Findings:** 0  
**Lead:** Augustine Ozor &nbsp;·&nbsp; **Dates:** 2026-10-01 → 2026-11-15

**Scope**  
Review the Business Impact Analysis for the SCADA master servers, process historian, substation communications gateways, HMI workstations, and offsite backup store; confirm RTO and RPO targets are defined, approved by operations leadership, and traceable to the replication and backup controls that must meet them.

---

## 2. SCADA Backup and Restore Readiness Review

**Type:** ![Internal](https://img.shields.io/badge/type-Internal-0366d6) &nbsp;·&nbsp; **Status:** ![Completed](https://img.shields.io/badge/status-Completed-28a745) &nbsp;·&nbsp; **Findings:** 3  
**Lead:** Internal Audit Team &nbsp;·&nbsp; **Dates:** 2026-08-17 → 2026-09-11

**Scope**  
Test whether PLC logic exports, SCADA system images, and historian backups in the offsite store are current, complete, and restorable. Covered backup age records, restore procedures, and evidence of past restore tests for the production and DR environments.

---

## 3. Annual DR Failover Exercise Audit

**Type:** ![Internal](https://img.shields.io/badge/type-Internal-0366d6) &nbsp;·&nbsp; **Status:** ![Planned](https://img.shields.io/badge/status-Planned-6a737d) &nbsp;·&nbsp; **Findings:** 0  
**Lead:** Internal Audit Team &nbsp;·&nbsp; **Dates:** 2027-02-01 → 2027-02-26

**Scope**  
Observe and evidence an end-to-end failover of supervisory control from the production SCADA master to the DR site, measure actual takeover time against the approved RTO, and verify replication state against the approved RPO at the moment of failover.

---

## 4. ISO 27001 Surveillance Audit: Business Continuity Controls

**Type:** ![External](https://img.shields.io/badge/type-External-6f42c1) &nbsp;·&nbsp; **Status:** ![Planning](https://img.shields.io/badge/status-Planning-0366d6) &nbsp;·&nbsp; **Findings:** 0  
**Lead:** Certification body lead auditor (to be assigned) &nbsp;·&nbsp; **Dates:** 2027-03-08 → 2027-03-12

**Scope**  
External surveillance review of ICT readiness for business continuity, redundancy of processing facilities, network segregation, and backup controls (Annex A 5.30, 8.13, 8.14, 8.22) across the SCADA environment and DR site.

---


---

<div align="center">

[← Controls](03-controls.md) &nbsp;|&nbsp; [🏠 Home](README.md)

</div>
