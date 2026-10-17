# ⚠️ Risk Register

> 6 risks, each written as [Threat] exploits [Vulnerability] causing [Impact] to [Asset], scored by likelihood × impact.

| # | Title | Category | Status | Risk Score |
|---|---|---|---|---|
| 1 | Ransomware operator exploits flat IT/OT network segmentation causing loss of supervisory control to SCADA Master Control Server | Availability | ![Open](https://img.shields.io/badge/status-Open-d73a49) | 15 (3 × 5) — Critical |
| 2 | Replication lag exploits untested failover procedure causing failed or delayed takeover by the SCADA Master Control Server (DR Site) | Availability | ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09) | 20 (4 × 5) — Critical |
| 3 | Storage failure exploits infrequent historian backups causing loss of recent sensor and alarm data in the Process Historian Database | Data Protection | ![Open](https://img.shields.io/badge/status-Open-d73a49) | 9 (3 × 3) — Medium |
| 4 | Severe weather exploits single communications path causing loss of remote control of substations via the Substation Communications Gateway | Physical Security | ![Open](https://img.shields.io/badge/status-Open-d73a49) | 12 (3 × 4) — High |
| 5 | Untrained operator exploits outdated manual-fallback procedures causing delayed manual control during an outage of the Treatment Plant HMI Workstations | Human Error | ![Open](https://img.shields.io/badge/status-Open-d73a49) | 8 (2 × 4) — Medium |
| 6 | Stale backups exploit untested restore procedures causing failed rebuild of the control environment from the Offsite SCADA Configuration Backup Store | Availability | ![Open](https://img.shields.io/badge/status-Open-d73a49) | 16 (4 × 4) — Critical |

## 1. Ransomware operator exploits flat IT/OT network segmentation causing loss of supervisory control to SCADA Master Control Server

**Category:** Availability &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Likelihood:** 3/5 &nbsp;·&nbsp; **Impact:** 5/5 &nbsp;·&nbsp; **Risk Score:** 15 (3 × 5) — Critical  
**Owner:** OT Engineering Team

**Description**  
A ransomware operator who gains a foothold on the corporate IT network moves laterally across weak IT/OT segmentation and encrypts or disables the SCADA Master Control Server, removing supervisory control over water treatment and power substations serving 10M+ citizens.

**Decision Rationale**  
Likelihood rated Possible (3) because critical infrastructure operators are actively targeted, but segmentation controls and monitoring reduce the odds of a successful pivot into the OT zone. Impact rated Severe (5) because loss of the master station removes supervisory control of services that millions of people depend on, and it sets the tightest RTO in the analysis.

---

## 2. Replication lag exploits untested failover procedure causing failed or delayed takeover by the SCADA Master Control Server (DR Site)

**Category:** Availability &nbsp;·&nbsp; **Status:** ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09)  
**Likelihood:** 4/5 &nbsp;·&nbsp; **Impact:** 5/5 &nbsp;·&nbsp; **Risk Score:** 20 (4 × 5) — Critical  
**Owner:** OT Engineering Team

**Description**  
Data replication between the production and DR SCADA masters lags under load, and the failover procedure has not been exercised end to end, so a real outage could leave the DR site with stale state or unable to assume control within the target recovery time.

**Decision Rationale**  
Likelihood rated Likely (4) because failover procedures that have never been rehearsed commonly fail or run long on first real use. Impact rated Severe (5) because the DR master is the recovery path for the most critical system, so a failed takeover turns a contained outage into a prolonged loss of control. Marked In Progress because defining RTO and RPO for this pair is the active BIA work.

---

## 3. Storage failure exploits infrequent historian backups causing loss of recent sensor and alarm data in the Process Historian Database

**Category:** Data Protection &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Likelihood:** 3/5 &nbsp;·&nbsp; **Impact:** 3/5 &nbsp;·&nbsp; **Risk Score:** 9 (3 × 3) — Medium  
**Owner:** OT Engineering Team

**Description**  
A disk or database failure on the Process Historian occurs between infrequent backup cycles, losing recent time-series readings, alarms, and operator action records needed for regulatory reporting and incident forensics.

**Decision Rationale**  
Likelihood rated Possible (3) because storage failures are a normal lifecycle event and the backup interval has not been set against a defined RPO. Impact rated Moderate (3) because real-time control continues without the historian, so the harm is lost records and reporting gaps rather than loss of operations.

---

## 4. Severe weather exploits single communications path causing loss of remote control of substations via the Substation Communications Gateway

**Category:** Physical Security &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Likelihood:** 3/5 &nbsp;·&nbsp; **Impact:** 4/5 &nbsp;·&nbsp; **Risk Score:** 12 (3 × 4) — High  
**Owner:** Grid Operations

**Description**  
Storm, flooding, or line damage takes out the single dedicated communications link behind the Substation Communications Gateway, cutting the control center's visibility and remote control of the affected substations until the path is restored.

**Decision Rationale**  
Likelihood rated Possible (3) because severe weather affecting a regional link is a recurring event, though not certain in any given year. Impact rated Major (4) because affected substations can still run locally and the wider grid has redundancy, but remote switching and monitoring are lost and restoration depends on field crews.

---

## 5. Untrained operator exploits outdated manual-fallback procedures causing delayed manual control during an outage of the Treatment Plant HMI Workstations

**Category:** Human Error &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Likelihood:** 2/5 &nbsp;·&nbsp; **Impact:** 4/5 &nbsp;·&nbsp; **Risk Score:** 8 (2 × 4) — Medium  
**Owner:** Water Operations

**Description**  
When the HMI workstations fail, operators must switch to local manual control of chlorination, filtration, and pumping. Procedures that are out of date or rarely practiced slow that switch and increase the chance of a process mistake.

**Decision Rationale**  
Likelihood rated Unlikely (2) because trained operators run manual control as part of normal practice and a fallback path already exists. Impact rated Major (4) because errors in treatment processes carry public health and safety consequences, even if they are short-lived.

---

## 6. Stale backups exploit untested restore procedures causing failed rebuild of the control environment from the Offsite SCADA Configuration Backup Store

**Category:** Availability &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Likelihood:** 4/5 &nbsp;·&nbsp; **Impact:** 4/5 &nbsp;·&nbsp; **Risk Score:** 16 (4 × 4) — Critical  
**Owner:** IT Infrastructure

**Description**  
After a major outage or destructive attack, the team relies on PLC logic, SCADA configuration exports, and system images in the offsite store, but backups are not restore-tested and may be out of date, so the control environment cannot be rebuilt to its last known good state.

**Decision Rationale**  
Likelihood rated Likely (4) because untested restores and aging configuration backups are one of the most common reasons recovery plans fail in practice. Impact rated Major (4) because a failed rebuild extends the outage well beyond the target RTO, though the DR site gives a partial alternative path.

---


---

<div align="center">

[← Assets](01-assets.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Controls →](03-controls.md)

</div>
