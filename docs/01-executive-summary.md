[← Back to index](../README.md)

# 1. Executive Summary

We propose a secure, horizontally scalable hosting platform on Microsoft Azure across **two sites on two continents**, as requested in RFP §2.4.

Each application service runs on its own group of small virtual machines that scales out automatically under load. Data runs on Azure SQL Database (Microsoft SQL Server engine), with managed queueing and caching. The Disaster Recovery site runs at minimum capacity and scales up automatically when a failover happens, which keeps the cost low while meeting the RFP recovery requirements.

The platform covers all required environments (Development, QA, UAT, Staging, Production and DR), web application protection, DDoS and bot mitigation, backups, 24/7 monitoring and on-call support under a dedicated Hosting SLA. The full setup is delivered in **two sprints (4 weeks)**.
