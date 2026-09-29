[← Back to index](../README.md)

# 8. Delivery Plan — 2 Sprints (4 Weeks, 160 Hours)

### Sprint 1 — Foundation & Non-Production (Weeks 1–2, 80 hours)
| Deliverable | Detail |
|---|---|
| Discovery & design | Requirements confirmation, Hosting HLD and LLD |
| Azure foundation | Subscriptions, networking in both sites, NSGs, jump host with VPN |
| Edge security | Cloudflare WAF, DDoS, bot protection, TLS, DNS |
| CI/CD & repository | Source repository, pipelines with stages Dev → QA → UAT → Staging → Production |
| **Dev/QA environment** | Servers, databases, cache, queue, deployment |
| **UAT/Staging environment** | Servers, databases, cache, queue, deployment |
| Infrastructure as code | All of the above in Terraform + Ansible |

**Acceptance:** Dev/QA and UAT/Staging environments running; HLD approved.

### Sprint 2 — Production, DR & Operations Readiness (Weeks 3–4, 80 hours)
| Deliverable | Detail |
|---|---|
| Production (Site A) | Scale sets per service, autoscale 2 → 3, Azure SQL, Cosmos DB, Service Bus, Blob |
| DR (Site B) | Minimum-capacity services, SQL geo-replica, scale-up automation |
| Monitoring & self-healing | Uptime checks, metrics, alerts, on-call routing, auto-restart and node replacement |
| Security hardening | Encryption, access control, patch baseline, security logging |
| Backup & DR | Backup Policy, DR Plan, DR runbook, one failover test |
| Documents | Data Breach Policy, SLA monitoring method, Escalation Matrix |
| Handover | Runbooks and knowledge transfer to client staff |

**Acceptance:** Production and DR ready; DR failover test passed; documents delivered.

### Payment
| Milestone | Payment |
|---|---|
| Sprint 1 accepted | 50% |
| Sprint 2 accepted | 50% |

Go-live date depends on the application vendor's schedule. Go-live support, load test execution and hypercare are billed at on-call hourly rates.
