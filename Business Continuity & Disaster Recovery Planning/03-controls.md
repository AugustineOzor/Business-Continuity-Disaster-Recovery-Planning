# 🛡️ Controls

> 8 controls mapped to ISO 27001 Annex A and NIST CSF, each tied to a specific continuity risk.

| # | Control | Framework | Reference | Effectiveness | Frequency |
|---|---|---|---|---|---|
| 1 | IT/OT Network Segmentation with DMZ and Firewall Allow-Listing | ISO 27001 | `A.8.22` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Continuous |
| 2 | OT Network Monitoring with Anomaly Alerting | NIST CSF | `DE.CM-01` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Continuous |
| 3 | Automated DR Replication with Lag Alerting | ISO 27001 | `A.8.14` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Continuous |
| 4 | Annual Full DR Failover Exercise | ISO 27001 | `A.5.30` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Annual |
| 5 | Historian Log-Shipping Backup Aligned to RPO | NIST CSF | `PR.DS-11` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Continuous |
| 6 | Secondary Radio Link for Substation Communications Gateways | ISO 27001 | `A.7.5` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Quarterly |
| 7 | Operator Manual-Fallback Drills and Procedure Review | ISO 27001 | `A.6.3` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Annual |
| 8 | Quarterly Restore Test of SCADA Configuration Backups | NIST CSF | `PR.DS-11` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Quarterly |

## 1. IT/OT Network Segmentation with DMZ and Firewall Allow-Listing

**Framework:** ISO 27001 `A.8.22` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** OT Engineering Team

**Description**  
Separate the SCADA network from corporate IT with a firewall pair and DMZ, permit only allow-listed hosts and industrial protocols across the boundary, and require remote engineering access to go through a jump host with MFA.

**Decision Rationale**  
Rated Partially Effective because the segmentation architecture is in place and enforced, but the allow-list has not yet been fully reviewed against current traffic, so some legacy rules may still be broader than needed. Until that review is complete, the lateral-movement path described in the related risk is reduced but not closed.

---

## 2. OT Network Monitoring with Anomaly Alerting

**Framework:** NIST CSF `DE.CM-01` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** OT Engineering Team

**Description**  
Passively monitor SCADA network traffic for unauthorized devices, unexpected protocol commands, and new connections across the IT/OT boundary, with alerts routed to the on-call OT security contact.

**Decision Rationale**  
Rated Not Tested because the monitoring is newly deployed and has not yet been validated with a simulated unauthorized connection or out-of-profile command, so detection reliability is unconfirmed.

---

## 3. Automated DR Replication with Lag Alerting

**Framework:** ISO 27001 `A.8.14` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** OT Engineering Team

**Description**  
Replicate SCADA master state and configuration from production to the DR site continuously, and alert the OT engineering team whenever replication lag exceeds the RPO target set in the Business Impact Analysis.

**Decision Rationale**  
Rated Partially Effective because replication runs and lag is visible, but the alert threshold cannot be finalized until the BIA sets the RPO. Until then the control monitors lag without a confirmed pass/fail line.

---

## 4. Annual Full DR Failover Exercise

**Framework:** ISO 27001 `A.5.30` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** OT Engineering Team

**Description**  
Run a documented end-to-end failover of supervisory control from the production SCADA master to the DR site once a year, measure the time to assume control against the RTO target, and record gaps for correction.

**Decision Rationale**  
Rated Not Tested because no full failover has been exercised yet, so the achievable recovery time is unmeasured. The RTO target from the BIA will become the pass criterion once it is approved.

---

## 5. Historian Log-Shipping Backup Aligned to RPO

**Framework:** NIST CSF `PR.DS-11` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** OT Engineering Team

**Description**  
Ship Process Historian transaction logs to a separate storage target continuously and take full backups on a fixed schedule, with the log-shipping interval set from the RPO approved in the Business Impact Analysis.

**Decision Rationale**  
Rated Partially Effective because backups and log shipping run today, but the interval was set before an RPO existed, so it has not been confirmed to meet the tolerable data-loss window.

---

## 6. Secondary Radio Link for Substation Communications Gateways

**Framework:** ISO 27001 `A.7.5` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** Grid Operations

**Description**  
Provide each substation communications gateway with a secondary radio or cellular path that takes over automatically when the primary dedicated link fails, with a quarterly failover test per substation.

**Decision Rationale**  
Rated Not Tested because secondary paths are provisioned but no automatic failover test has been run to confirm the gateway switches paths and control traffic resumes.

---

## 7. Operator Manual-Fallback Drills and Procedure Review

**Framework:** ISO 27001 `A.6.3` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** Water Operations

**Description**  
Run a drill once a year for every operating shift crew in which HMI workstations are taken offline and operators switch to local manual control of chlorination, filtration, and pumping, followed by a review and update of the written fallback procedures.

**Decision Rationale**  
Rated Partially Effective because drills have been run for some shift crews but not yet all of them, so procedure readiness is uneven across the workforce.

---

## 8. Quarterly Restore Test of SCADA Configuration Backups

**Framework:** NIST CSF `PR.DS-11` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** IT Infrastructure

**Description**  
Each quarter, restore a randomly selected PLC logic export and SCADA system image from the offsite backup store into an isolated environment, confirm it boots and matches the current baseline, and log the age of the backup used.

**Decision Rationale**  
Rated Not Tested because the schedule is defined but the first restore test has not been performed, so it is unconfirmed that the backups can rebuild the control environment.

---


---

<div align="center">

[← Risk Register](02-risk-register.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Audits →](04-audits.md)

</div>
