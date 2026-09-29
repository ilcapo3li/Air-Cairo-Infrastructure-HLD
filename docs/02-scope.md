[← Back to index](../Readme.md)

# 2. Scope

### 2.1 In scope
- Hosting design and build on Microsoft Azure (Site A primary, Site B DR).
- Environments: Dev/QA, UAT/Staging, Production, DR.
- Network security, WAF, DDoS and bot mitigation.
- Web server management: configuration, tuning, patching (RFP §2.2.6).
- Azure SQL Database setup, geo-replication, backup retention and performance monitoring.
- Managed queue (Azure Service Bus) and cache (Azure Cosmos DB).
- Backup and restore, DR plan and DR runbook, one DR failover test.
- CI/CD pipelines, source code repository and versioning platform.
- 24/7 automated uptime and performance monitoring, alerting and self-healing.
- Secure remote access for support.
- On-call operational support under a separate Hosting SLA (RFP §2.2.8).
- Required documents: Hosting HLD, Backup Policy, DR Plan, Data Breach Policy, SLA monitoring method, Escalation Matrix.

### 2.2 Out of scope
- Application design and development (website, agent portal, admin/CMS, mobile app).
- Integrations with Cargo Flash, SAP, payment gateway, SMS, maps and chatbot.
- Enterprise DXP licensing and implementation.
- Application bug fixing and content management support.
- Load test execution, go-live support and hypercare: billed at on-call hourly rates when requested.

### 2.3 Shared responsibilities (to be agreed with the application vendor)
| Item | Our part | Application vendor's part | RFP |
|---|---|---|---|
| Horizontal scaling | Scale sets, load balancing, autoscale rules | **Stateless services** (no local session or files) | §2.4 |
| Self-healing | Health probes, automatic restart and node replacement | Health-check endpoint in each service | §2.2.1 |
| Caching | Cosmos DB cache store, CDN | Cache logic and TTLs in the code | §2.2.9 |
| Messaging | Service Bus namespace, queues, access | Producers and consumers in the code | §2.3.19 |
| Source code repository | Platform, access control, backups | Code, branching, reviews | §2.2.8 |
| Load testing | Test tooling and infrastructure scaling | Test scenarios and results analysis | §2.2.5 |
| Security testing | Infrastructure hardening and scans | Application security fixes | §2.2.5 |
| Minification, image optimization | Build pipeline steps | Build configuration | §2.2.9 |
| Encryption at rest | Disk encryption, SQL TDE (default) | Field-level encryption if needed | §2.3.18 |
| Audit logging, anomaly detection | Log platform and alerts | Application audit events | §2.2.4, §2.3.18 |
| Mobile app release | Build and release pipeline | App code; store accounts owned by the client | §2.2.3 |
