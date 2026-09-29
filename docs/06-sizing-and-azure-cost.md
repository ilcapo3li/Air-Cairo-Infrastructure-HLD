[← Back to index](../README.md)

# 6. Sizing and Estimated Azure Cost (monthly)

> **Billed by Microsoft and Cloudflare directly to the client (Bill B). Not part of our fees.**
> Approximate list prices, PAYG, Linux. Small VM: D2as v5 (2 vCPU, 8 GB) ≈ $63. UAE North is approximately 10–15% higher. Final figures will be confirmed with the Azure Pricing Calculator.

### 6.1 Site A — Production
| Item | Detail | $/month |
|---|---|---|
| Service VMs | 4 service groups × 2 nodes (up to 3) | 504 – 756 |
| Azure SQL Database | Primary, General Purpose (~2 vCores) | ~350 |
| Cosmos DB (cache) | Autoscale throughput (free tier applies) | 0 – 50 |
| Service Bus | Standard tier | ~15 |
| Blob storage | Documents and media, geo-redundant | ~30 |
| Load balancer, public IP | | ~25 |
| Monitoring and logs | Azure Monitor / Log Analytics | ~50 |
| Jump host | Small VM | ~15 |
| OS disks | | ~50 |
| **Subtotal** | **8–12 VMs** | **~1,040 – 1,340** |

### 6.2 Site B — DR (minimum capacity)
| Item | Detail | $/month |
|---|---|---|
| Service VMs | 2 small VMs running all services | ~140 |
| Azure SQL geo-replica | Smaller compute size | ~120 – 180 |
| Cosmos DB replica | | 0 – 50 |
| Load balancer, disks | | ~40 |
| **Subtotal** | **2 VMs** | **~300 – 410** |

**During a real failover:** Site B scales up to production size. Extra cost while DR is active ≈ **$800–1,000/month**, charged pro-rata only for the days in failover.

### 6.3 Dev/QA environment
| Item | Detail | $/month |
|---|---|---|
| Service VMs | 2 small VMs, shut down after hours | ~80 – 126 |
| Azure SQL | 2 small databases (Dev, QA) | ~30 |
| **Subtotal** | **2 VMs** | **~110 – 160** |

### 6.4 UAT/Staging environment
| Item | Detail | $/month |
|---|---|---|
| Service VMs | 2 small VMs, shut down after hours when not in use | ~80 – 126 |
| Azure SQL | 2 small databases (UAT, Staging) | ~60 |
| **Subtotal** | **2 VMs** | **~140 – 190** |

Non-production cache and queue use free or basic tiers (~$10/month total).

### 6.5 Shared services
| Item | $/month |
|---|---|
| Cloudflare (Pro to Business plan) | 25 – 250 |
| Outbound traffic (egress) | 20 – 260 |
| Hosted build agents (Azure DevOps) | ~40 |
| SQL long-term backup retention | ~20 |
| Optional: Azure Firewall Basic, per site | ~290 |

### 6.6 Total
| Scenario | Monthly | Yearly |
|---|---|---|
| Normal operation, PAYG | **~$1,700 – $2,700** | ~$20k – $32k |
| With 1-year reserved instances on production VMs | ~$1,550 – $2,500 | ~$19k – $30k |

Total: approximately 14–18 small VMs across all environments.

> The 3TB per site is a minimum bandwidth capacity. Actual traffic for a B2B cargo portal is expected to be considerably lower.
