[← Back to index](../Readme.md)

# 3. Requirements Traceability (Infrastructure)

| ID | RFP requirement | RFP ref | Our response |
|---|---|---|---|
| H-01 | Scalable and efficient hosting with HLD | §2.4 | One scale set per service, horizontal autoscale 2 → 3 nodes; [Section 4](04-high-level-design.md) |
| H-02 | High availability (redundancy) | §2.4 | Minimum 2 nodes per service across availability zones; managed SQL with built-in HA |
| H-03 | Network firewall | §2.4 | Stateful Network Security Groups + host firewalls; optional Azure Firewall Basic |
| H-04 | Web application firewall | §2.4 | Edge WAF with managed rule sets (Cloudflare) |
| H-05 | DDoS prevention and bot mitigation | §2.4 | Edge DDoS and bot protection (Cloudflare) + Azure basic DDoS protection |
| H-06 | Two sites, two geo locations, preferably two continents, HA and DR | §2.4 | Site A: Europe (Italy North); Site B: Asia (UAE North) |
| H-07 | Minimum bandwidth 3TB per site | §2.4 | Capacity provided at both sites |
| H-08 | Staging environment | §2.4 | Dedicated UAT/Staging environment |
| H-09 | Test environment by vendor | §2.4 | Dedicated Dev/QA environment |
| H-10 | 24×365 availability, planned outages notified in advance | §2.4 | Proposed 99.9% monthly availability; maintenance windows notified in advance |
| H-11 | Reliable backups at a safe location | §2.4 | Automated SQL backups, geo-redundant storage, long-term retention |
| H-12 | DR implemented + backup policy | §2.4 | Scale-up DR site in Site B; Backup Policy document |
| O-01 | Web server configuration, tuning, patching, uptime monitoring | §2.2.6 | Nginx managed by us |
| O-02 | Secure remote support; email, phone, chat; proactive monitoring | §2.2.7 | Jump host with VPN; support channels; automated alerting |
| O-03 | Deployments, backup/restore, health monitoring, pipelines, upgrades, DB patching | §2.3.20 | Operations runbooks; database patching handled by the managed service |
| O-04 | Self-healing (automatic restart of failed services) | §2.2.1 | Health probes, auto-restart, auto-replace of failed nodes |
| S-01 | HTTPS/TLS for all data exchange | §2.2.4 | TLS 1.2+ end to end |
| S-02 | Encryption at rest for customer data | §2.3.18 | Disk encryption + SQL TDE |
| S-03 | Real-time anomaly monitoring | §2.3.18 | Central logs, security alerts |
| S-04 | Data breach policy | §2.3.18 | Delivered as document |
| A-01 | Three-tier architecture | §2.3.19 | Presentation, service and data tiers on separate subnets |
| A-02 | Microsoft SQL Server | §2.3.19 | Azure SQL Database (Microsoft SQL Server engine) |
| A-03 | Azure compatible, scalable, secure | §2.3.19 | Hosted on Azure |
| A-04 | Inter-service messaging (e.g. message queues) | §2.3.19 | Azure Service Bus |
| L-01 | Separate Hosting SLA | §2.2.8 | [Section 7](07-hosting-sla-and-support.md) |
| L-02 | Dev, QA, UAT servers | §2.2.8 | [Section 5](05-environments.md) |
| L-03 | 24/7 uptime monitoring | §2.2.8 | [Section 4.8](04-high-level-design.md) |
| L-04 | Escalation matrix, man-day rate | §2.2.8 | Sections [7](07-hosting-sla-and-support.md) and [9](09-commercial-summary.md) |
