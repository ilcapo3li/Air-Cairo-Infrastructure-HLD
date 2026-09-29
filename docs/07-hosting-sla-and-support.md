[← Back to index](../Readme.md)

# 7. Hosting SLA and Support Model

### 7.1 Severity levels (from RFP §2.2.8)
| Severity | Definition | Response | Resolve | Coverage |
|---|---|---|---|---|
| Critical | Main website or service down; impact on revenue or financial transactions | 1 hour | 4 hours | 24×7 incl. holidays |
| Medium | Decreased performance; low financial, regulatory or customer impact | 2 hours | 1 business day | 5×8 |
| Minor | Minor degradation, no financial or customer impact | 4 hours | 2 business days | 5×8 |
| Change request | As agreed per request | Per estimate | Per estimate | 5×8 |

Business hours: Sunday to Thursday, Egypt time.

### 7.2 Support model: on-call, ticket-based
- **24/7 automated monitoring** detects issues and alerts the on-call engineer.
- **On-call engineers** cover Critical incidents 24×7 within the 1-hour response time.
- **All other requests** are handled through tickets during business hours.
- **Routine operations** (patching, backup checks, monthly report) run on a fixed monthly schedule.
- **Channels:** ticket portal, email, phone, chat (RFP §2.2.7).

### 7.3 Hosting SLA terms (proposed)
- Availability: 99.9% monthly for production.
- Planned maintenance: notified at least 5 business days in advance, off-peak hours.
- Service credits apply to hosting availability only. Excluded: application code, Cargo Flash, SAP, payment gateway, Azure platform outages, third-party services, client-side changes.
- Monthly SLA report: availability, incidents, response and resolve times, recurring errors.
- Quarterly SLA review with the client.

### 7.4 Escalation matrix (template)
| Level | Role | When |
|---|---|---|
| L1 | On-call engineer | All incidents |
| L2 | Senior infrastructure engineer | Not resolved within 1 hour (Critical) |
| L3 | Lead architect | Not resolved within 2 hours (Critical) |
| L4 | Account director | SLA breach risk |

### 7.5 Routine operations calendar
| Activity | Frequency |
|---|---|
| OS and web server patching | Monthly |
| Backup verification and restore test | Monthly |
| Performance, scaling and cost review | Monthly |
| Availability and SLA report | Monthly |
| Security review and vulnerability scan | Quarterly |
| DR failover test | Twice a year |
| SLA review | Quarterly |
