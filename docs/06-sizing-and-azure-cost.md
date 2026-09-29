[← Back to index](../README.md)

# 6. Sizing and Estimated Azure Cost (monthly)

> **Billed by Microsoft and Cloudflare directly to the client (Bill B). Not part of our fees.**
> Approximate list prices, PAYG, Linux. Small VM: D2as v5 (2 vCPU, 8 GB) ≈ $63, based on European (Italy North) pricing. Final figures will be confirmed with the Azure Pricing Calculator.

> **Regional price note:** UAE North is approximately 10–15% more expensive than Italy North. The tables below use Italy North prices, so the region chosen for each site changes the total:
>
> | Layout | Site A (production) | Site B (DR) | Effect on monthly cost |
> |---|---|---|---|
> | **Proposed:** Site A UAE North, Site B Italy North | ~1,150 – 1,540 (+~100–200) | ~300 – 410 (no change) | **+~100 – 200** |
> | Alternative: Site A Italy North, Site B UAE North | ~1,040 – 1,340 (no change) | ~330 – 470 (+~30–60) | +~30 – 60 |
>
> Hosting the primary site in the UAE costs roughly **$70 – 140 more per month** than hosting it in Italy, because the larger production footprint sits in the more expensive region. The same ratio applies to the extra cost during a DR failover.
>
> **These figures are rough estimates, not accurate quotations.** Actual costs depend on the final regions, usage, traffic and Microsoft pricing at the time of purchase, and will be confirmed with the Azure Pricing Calculator.
>
> **This sizing is an initial baseline.** Features, components and sizes may be added or adjusted during hosting, based on actual usage, performance and monitoring results. Any change that affects cost will be discussed and agreed with the client beforehand.

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
