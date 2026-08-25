# Oracle at VLDB 2026

Explore Oracle’s latest research and technical papers presented at VLDB.

## Sponsor Talk: Trusted Agentic AI with Oracle AI Database
__Tuesday 13:45 – 15:15 Otis__
Tirthankar Lahiri
Senior Vice President, Mission-Critical Data and AI Engines

## Papers

### [Real-time SQL Plan Management in Oracle](PASTE_PAPER_URL_HERE)
__Tuesday 10:45 – 12:15 Marina Ballroom I__

_Sunil Chakkappen (Oracle) · Mohamed Ziauddin (Oracle) · Hong Su (Oracle) · Shreya Kunjibettu (Oracle) · Nigel Bayliss (Oracle)_

Consistent query performance is essential for mission critical database applications, yet SQL execution plans can change due to factors such as database upgrades, DML changes, new indexes, etc. While plan stability mechanisms such as stored outlines prevent regressions by freezing execution plans, they also inhibit performance improvements by disallowing plan evolution. We introduced SQL Plan Management (SPM) in Oracle 11g to address this trade-off by maintaining a set of accepted execution plans and allowing plan evolution only when new plans demonstrably outperform existing baselines. However, prior implementations of SPM primarily rely on background performance verification processes, delaying regression detection and recovery. This issue is amplified in autonomous cloud database systems, where several automatic actions that could cause plan change driven regressions are performed with limited customer control. Timely detection and remediation is paramount, but the constrained background resources on cloud may not keep pace. To overcome these limitations, we introduce Real-Time SPM in Oracle 26ai, a novel extension of SPM that performs foreground verification of new execution plans during user query execution. Real-Time SPM leverages runtime session context to immediately validate plan changes, enabling rapid adoption of superior plans while promptly detecting and preventing regressions. This paper presents the architecture and design of Real-Time SPM - including technical challenges like reliably comparing performance of previous plans - and contrasts it with traditional background plan evolution. Our experiments highlight tangible benefits of Real-Time SPM - delivering immediate performance boost while preserving plan stability in both cloud-native and on-premise environments. Real-Time SPM is successfully deployed in Oracle production, laying the groundwork for more adaptive and user-responsive SQL plan management in enterprise RDBMS platforms.

### [IORM: Hierarchical I/O Governance for Thousands of Consolidated Databases on Oracle Exadata](https://arxiv.org/abs/2605.29006)
__Wednesday 13:45 – 15:15 Marina Ballroom I__

_Rajarshi Chowdhury (Oracle America Inc) · Akshay Shah (Oracle America Inc) · Zakaria Alrmaih (Oracle America Inc) · Chenhao Guo (Oracle America Inc) · Anubhav Singh (Oracle America Inc) · Sue Lee (Oracle America Inc)_

Oracle Exadata consolidates thousands of tenant databases onto shared storage infrastructure deployed at hundreds of customer sites worldwide. Oracle Multitenant architecture enables this extreme density, with thousands of tenant databases sharing a single Exadata storage system—but this creates a multi-level resource hierarchy (container databases, tenant databases, and workloads within tenants) that commodity block-layer schedulers cannot govern, as they lack visibility into database semantics and tenant boundaries.This paper presents the I/O Resource Manager (IORM), a storage-side scheduler built on three mechanisms: I/O Tagging, which propagates semantic context from the database kernel to the storage scheduler; Hierarchical Resource Profiles, which express compositional allocation policies across consolidation tiers using shares and limits; and Unified Storage Governance, which applies these policies consistently across all tiers of the storage hierarchy—persistent memory, flash, and hard disk—including cache placement decisions. IORM enables successful cloud deployments where thousands of tenants coexist on shared storage: production OLTP workloads run alongside concurrent analytical workloads from the same or different databases without noisy-neighbor interference. Evaluation on production Exadata systems demonstrates that IORM dramatically improves latency consistency, virtually eliminating tail latency outliers and delivering order-of-magnitude improvements in average read latency under mixed workloads. Hierarchical limits compose correctly across all three levels, and proportional share allocation tracks configured ratios closely even under highly skewed demand.

### [Why We Created Yet Another Memory Framework: Understanding MGA’s Role in Next-Gen Database Systems](PASTE_PAPER_URL_HERE) 
__Thursday 10:45 – 12:15 Marina Ballroom I__

_Vikramraj Sitpal (Oracle) · Pei Li (Oracle) · Shubham Kumar (Oracle) · Somansh Reddy Satish (Oracle) · Ravi Thammaiah (Oracle) · Nagarajan Muthukrishnan (Oracle)_

Despite the presence of multiple memory regions in modern database systems, supporting an efficient form of memory remains a challenge under production constraints. In enterprise-grade data systems, existing abstractions impose a trade-off between coarse-grained global sharing and strict process isolation, resulting in data copying, memory fragmentation, and limited support for controlled sharing. These challenges become more pronounced as workloads grow more diverse, and systems must tolerate process failures while maintaining predictable performance. This paper introduces the Managed Global Area (MGA), a scoped shared-memory abstraction in Oracle AI Database that addresses these limitations. MGA allows components to explicitly define allocation source, membership, and coordination semantics across selected processes while integrating with a production database engine. Unlike fully shared memory regions in Oracle, such as the System Global Area (SGA), MGA supports dynamic process membership and modular memory usage without imposing system-wide visibility. We evaluate MGA on analytical and AI workloads that stress shared-memory execution, including TPC-H hash joins and ONNX Runtime inference. Under concurrent execution, MGA reduces latency for join-intensive TPC-H queries by up to 35%. For ONNX-based inference, MGA-enabled model sharing reduces memory footprint by up to 90% and lowers large-model inference latency by up to 37%. These results demonstrate that dynamically scoped shared memory can improve both efficiency and predictability in production database systems.

---

For more information, visit [Oracle Database](https://www.oracle.com/database/).
