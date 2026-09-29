[← Back to index](../Readme.md)

# 5. Environments

| Environment | Purpose | RFP ref | Setup |
|---|---|---|---|
| **Development** | Developer integration and daily builds | §2.2.8 | Dev/QA environment: 2 small VMs + own database; shut down after hours |
| **QA / Test** | Functional and integration testing | §2.2.8, §2.4 | Same Dev/QA servers, separate database |
| **UAT** | Client acceptance testing | §2.2.8 | UAT/Staging environment: 2 small VMs + own database |
| **Staging** | Production-like pre-release validation | §2.4 | Same UAT/Staging servers, separate database, same configuration as Production |
| **Production** | Live service, Site A | §2.4 | Scale sets per service, 2 → 3 nodes |
| **DR** | Standby, Site B | §2.4 | Minimum capacity, scales up on failover |

Every environment has its own database, its own configuration and its own deployment pipeline stage: **Dev → QA → UAT → Staging → Production**.
