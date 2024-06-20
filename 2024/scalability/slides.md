---
theme: default
class: 'text-center'
highlighter: shiki
transition: slide-left
title: Database Scalability
mdc: true
colorSchema: light
---

# Database Scalability
# All you need to know

Exploring the Cornerstone of Successful SaaS Platforms  
  

**Ed Huang, Cofounder & CTO, PingCAP**

---

# Is your system really scalable?

What we're talking about when we talk about database scalability?

- A few TBs?

![image](https://dongxu-pics.s3.amazonaws.com/pub/2024/06/19/b7367c08.jpg){width=400px lazy}

**Scalability != Amount of Data**

---
layout: center
class: text-center
---


![image](https://dongxu-pics.s3.amazonaws.com/pub/2024/06/19/f880a105.jpg){width=350px lazy}

👆Scale on disk but not on the compute

![image](https://dongxu-pics.s3.amazonaws.com/pub/2024/06/19/f25454c7.jpg){width=350px lazy}

👆Scale on different components but not the pipeline

---

# The First Principle of Scalability

- Fundamental principle:  **Expand from zero to many without design changes**
  - Little to no changes in code
  - No need to re-architect the system

![](https://dongxu-pics.s3.amazonaws.com/pub/2024/06/19/f3bad972.jpg){width=300px lazy}

---

# Scalability Categories

- **Data and Throughput**
- **Metadata**
- **Connection and Resource Control**
- **Operational at scale**
- **Advanced Features at scale**

---

# Scalability: Data and Throughput

- **Data Scalability:** 
  - Adding more nodes to handle increasing data volumes (e.g., TiDB can handle up to 1 PB)
- **Throughput Scalability:**
  - Increasing QPS and TPS to handle more queries and transactions (e.g., e-commerce platform during sales events)

---

# When you gonna need it?

## *"I got both big tenants and small tenants"*
<br>

- For big tenants
  - Scale-out without pain
  - High isolation requirement
- For small tenants
  - Consolidate for saving cost
  - Rapid Growth

---

# How TiDB tackle this

- Scale-out
- Isolation
- Consolidation

---

# Metadata Scalability

- **Schema and Table Count Scalability:**
  - Supporting up to 1 million schemas/tables without performance loss
- **DDL Operations on massive database objects:**
  - Handling multiple concurrent DDL operations for evolving database structures

## Why? That's the most intutive way to build a multi-tenant system

---

# When you gonna need it?

## *"Every tenant should have their own tables!"*

<br>
Let's do a simple math: A SaaS company has 10000 users(tenants), for each user, system will create 100 table for them, the total table number would be:

10000 * 100 = 1 Million Tables!

And for each table, its metadata in database system is 10KB:

10 KB per table * 1,000,000 = 10G

**Note that this is only the meta data**

Image if there's even 10Mb in each table, that would be huge.

10M * 1,000,000 = 10 TB

---

# How TiDB solve this problem

- 

---

# Connection and Resource Scalability

- **Connection Count Scalability:**
  - Managing millions of concurrent user connections
  - **Technical Implementation:** Connection Pooling, Asynchronous IO
- **Resource Utilization Scalability:**
  - Dynamic allocation and prioritization of resources (e.g., resource control for multi-tenant platforms)
  - **Technical Implementation:** Resource Groups, Quotas and Priorities, Dynamic Resource Allocation

---

# Scenario: Not all tenants (or application) are equal



---

# How TiBB solve this problem

---

# Operational Scalability
  - **Batch Processing Scalability (Bulk Loading / Parallel Processing / Big Transaction):**
    - Efficient handling of large data operations
    - **Technical Implementation:** Bulk Loading, Parallel Processing, Batched Writes
  - **Backup and Restore Scalability:**
    - Rapid backup and restore processes for data continuity
    - **Technical Implementation:** Incremental Backups, Parallel Restore, Backup Compression
---

# Advanced Features (at scale!)
- **Content:** 
  - **Query Plan Control Scalability:**
    - Efficient query plan management with global bind features
    - **Technical Implementation:** Global Bindings, Adaptive Query Optimization
  - **HTAP Scalability:**
    - Combining transactional and analytical processing within a single database
    - **Technical Implementation:** Unified Storage Engine, Real-time Data Replication
  - **AI Readiness and Vector Search Scalability:**
    - Supporting AI applications with scalable vector search capabilities
    - **Technical Implementation:** Vector Indexing, Approximate Nearest Neighbor Search (ANNS)
---

# Slide 9: Conclusion
- **Title:** Conclusion
- **Content:** 
  - Summary of scalability categories
  - TiDB’s exemplary scalability features
  - Final thoughts on the importance of scalable database solutions
---

# Q&A

Thank you!

Ed Huang (h@pingcap.com)

