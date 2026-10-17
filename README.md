<div align="center">

<img width="3200" height="840" alt="banner" src="https://github.com/user-attachments/assets/a5bf694a-9af9-4451-9b66-854f0069eadf" />

# CriticalOps Inc — Business Continuity & Disaster Recovery Planning

![Progress](https://img.shields.io/badge/Progress-4%2F4%20Tasks-success) ![COBIT](https://img.shields.io/badge/-COBIT-informational) ![ISO 27001](https://img.shields.io/badge/-ISO%2027001-informational)

</div>

## Project Brief

> CriticalOps Inc operates SCADA systems for water treatment facilities and power grid substations serving 10M+ citizens. Classified as critical infrastructure under CISA guidelines, they must maintain operational resilience. As Business Continuity Manager, conduct Business Impact Analysis and define RTO/RPO requirements.

| | |
|---|---|
| **Client** | CriticalOps Inc |
| **Sector** | Critical infrastructure (water treatment and power grid) |
| **Scale** | 900 employees, serving 10M+ citizens |
| **Classification** | Critical infrastructure under CISA guidelines |
| **Role** | Business Continuity Manager |
| **Objective** | Conduct a Business Impact Analysis and define RTO/RPO requirements |
| **Frameworks** | COBIT, ISO 27001 |

## About this repository

This repo is a structured, portfolio-style write-up of a business continuity and disaster recovery program: a realistic (fictional) case study that follows the work from identifying which systems matter, through the risks to their availability, the controls that protect and recover them, and the audits that prove those controls work.

## What's inside

| Page | Contents |
|---|---|
| [🗂️ Assets](01-assets.md) | 6 systems in scope, from the SCADA master and its DR twin to the offsite backup store |
| [⚠️ Risk Register](02-risk-register.md) | 6 availability-focused risks, each written as Threat → Vulnerability → Impact → Asset |
| [🛡️ Controls](03-controls.md) | 8 controls mapped to ISO 27001 Annex A and NIST CSF |
| [🔍 Audits](04-audits.md) | 4 audits sequenced from target-setting to external assurance |

## How to read this

Each page links to the next through the navigation bar at the bottom: Assets → Risk Register → Controls → Audits. That is the order a continuity program is built in: know what must keep running, know what can stop it, put recovery controls in place, then prove they work.

## Methodology at a glance

- **Business impact first:** asset classification reflects how fast loss of each system hurts operations, which is what sets the recovery priority.
- **No invented targets:** RTO and RPO requirements are treated as outputs of the Business Impact Analysis. Controls that depend on them, such as replication lag alerting and historian backup intervals, reference the approved BIA targets rather than a made-up number.
- **Honest control ratings:** no control is rated Effective. Failover, restore, and manual-fallback capabilities are mostly unproven until exercised, and the ratings say so.
- **Standards referenced:** ISO 27001 Annex A (`A.5.30`, `A.6.3`, `A.7.5`, `A.8.14`, `A.8.22`) and NIST CSF (`DE.CM-01`, `PR.DS-11`)

---

<div align="center">

**[Start with Assets →](01-assets.md)**

</div>
