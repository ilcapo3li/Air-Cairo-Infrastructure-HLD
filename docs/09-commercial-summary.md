[← Back to index](../README.md)

# 9. Commercial Summary

The commercial offer is split into **two separate bills**, so the client always sees our fees apart from the cloud cost.

| Bill | Issued by | Covers |
|---|---|---|
| **A — Our services** | Us | Infrastructure setup + on-call support |
| **B — Cloud consumption** | Microsoft and Cloudflare, **directly to the client** | Azure resources, Cloudflare plan |

We do not resell or mark up cloud consumption. The Azure subscription and Cloudflare account are owned by the client; we operate them with delegated access.

### 9.1 Bill A — Our services

**Setup (one time)**
| Item | Basis | Price |
|---|---|---|
| Infrastructure setup | 2 sprints, 160 hours at $50/hour | **$8,000 fixed** |

**On-call support (monthly)**
| Item | Rate |
|---|---|
| Business hours (Sunday–Thursday, Egypt time) | **$50 / hour** |
| After hours, weekends and holidays (24/7) | **$75 / hour** |
| Critical call-out | Minimum 2 hours per call-out |
| Man-day (business hours) | $400 / day |
| **Monthly minimum** | **$500** (covers 10 business hours: 24/7 monitoring, on-call availability, monthly patching, backup checks, monthly report) |

**Year one — our fees**
| Item | Estimate |
|---|---|
| Setup | $8,000 |
| Support, 12 months (minimum $500/month + extra tickets) | $6,000 – $15,000 |
| **Total Bill A** | **$14,000 – $23,000** |

### 9.2 Bill B — Cloud consumption (paid by the client directly)

| Part | Monthly | What drives it |
|---|---|---|
| **Fixed baseline** | **~$1,700** | All environments running at minimum size: 2 nodes per service, SQL primary + DR replica, Dev/QA, UAT/Staging, cache, queue, monitoring, Cloudflare Pro |
| Variable | $0 – ~$1,000 | Autoscale to 3 nodes, traffic (egress), cache throughput, non-production left running, Cloudflare Business if needed |
| During a DR failover only | +$800 – $1,000 pro-rata | Site B scaled up to production size for the failover days |

| Scenario | Monthly | Yearly |
|---|---|---|
| Normal operation, PAYG | ~$1,700 – $2,700 | ~$20,000 – $32,000 |
| With 1-year reserved instances on production VMs | ~$1,550 – $2,500 | ~$19,000 – $30,000 |

Detailed breakdown: [Section 6](06-sizing-and-azure-cost.md). Final figures to be confirmed with the Azure Pricing Calculator for the selected regions.

### 9.3 Year one at a glance

| | Bill A — Us | Bill B — Cloud (direct) | Total |
|---|---|---|---|
| One time | $8,000 | — | $8,000 |
| Monthly (minimum) | $500 | ~$1,700 | ~$2,200 |
| Year one | $14,000 – $23,000 | ~$20,000 – $32,000 | ~$34,000 – $55,000 |
