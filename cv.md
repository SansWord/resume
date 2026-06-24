# CV -- Wen-Kai "SansWord" Huang

**Location:** San Jose, CA
**Email:** sansword@gmail.com
**Phone:** (669) 220-0281
**LinkedIn:** linkedin.com/in/sansword
**GitHub:** github.com/SansWord
**Portfolio:** sansword.github.io/resume

*"A data-platform builder applying senior engineering discipline — measurement, cost, judgment — to AI-assisted software."*

## Professional Summary

Senior Software Engineer with 9+ years designing and operating large-scale distributed systems and global data infrastructure on AWS and GCP, serving ~900M monthly active users across US, APAC, and Europe. Specialized in high-throughput, fault-tolerant pipelines (>20K msgs/sec), scalable data platforms, and cloud-native migrations. Proven technical leader and mentor recognized for cross-functional collaboration and driving large-scale impact across globally distributed teams. Now building and measuring agentic development and harness engineering through hands-on projects and public writing — applying measurement discipline (cost, model comparison, workflow design) to AI-assisted software engineering.

## Work Experience

### Yahoo! -- Sunnyvale, CA
**Sr. Software Dev Engineer**
Feb 2019 – Jun 2025

- Led end-to-end delivery of Yahoo's data infrastructure evolution to GCP over years, leading a dedicated 5+ engineer team to build a new GCP-native ingestion platform while designing a globally distributed multi-tenant pipeline using Cloud Composer, Airflow, and Dataproc — improving data freshness from 3+ hours to under 60 minutes across US, APAC, and Europe
- Contributed to Yahoo's hybrid cloud data infrastructure, supporting a zero-downtime AWS migration with Kubernetes-based auto-scaling and maintaining the multi-region lambda architecture serving recommendation, ads, and multiple downstream systems across News, Sports, and Finance
- Identified and resolved large-scale query inefficiencies, building aggregation and caching layers that reduced data scanned from 725 GB to 121 KB and cut query costs by 70% on Yahoo's BigQuery infrastructure
- Drove an on-call reliability initiative over several months, resolving root causes and improving monitoring to reduce open incident tickets from 1,000+ to zero; established practices subsequently adopted by the broader on-call team
- Led cross-functional collaboration between ML research and engineering teams to productionize ranking models, co-inventing a patented salient entity algorithm (US11803605B2), and integrating ranking models into production

### Yahoo! E-Commerce Platform -- Taipei, Taiwan
**Sr. Engineer**
Jun 2016 – Feb 2019

- Drove early AWS adoption across Yahoo engineering, building blue/green deployment and auto-scaling patterns via ECS that were later adopted by global teams
- Contributed to migrating 80 TB from house object storage to S3 with zero downtime, implementing dual-write/dual-read patterns to ensure data consistency and safe cutover; completed migration to drive system EOL
- Scaled Pigeon, a high-availability Apache Pulsar-based message bus sustaining 20K msgs/sec with data consistency guarantees, providing HTTP endpoints that abstracted client-side complexity across Yahoo's e-commerce teams; drove migration from Apache ActiveMQ and improved MTBF from 3.5 days to 90 days (~26×)
- Core developer of Cupid, a fault-tolerant multi-tenant discount service replacing a 10-year-old system; invented a flexible JSON-based rule engine and designed its rule semantics, empowering teams to independently configure promotions and marketing strategies — driving 10K/day coupon redemption growth and boosting annual sales events

## AI Engineering in Public — Shipped Projects & Measured Writing

*The through-line here is **measurement and judgment** — applying senior engineering discipline (cost analysis, model comparison, security review, design tradeoffs) to AI-assisted work, and documenting the work openly so it stands as evidence. Backed by a public blog on the skeptic-to-shipping journey (https://sansword.github.io/sans_blog/), a learning-in-public notes repo with measured cost/model studies (https://github.com/SansWord/sans_learning), and the shipped projects below.*

### AI Coding Practice — applied exploration of agentic development
2026 – Present

- **The Document Tree — keeping AI-built projects on track** — Context-engineering essay: a lazy-loaded document tree (small auto-loaded index → topic docs), a two-tier maintained/historical doc split, one-fact-one-place, and using a fresh-context agent to catch where docs silently drift from the code. Grounded in the real CLAUDE.md / docs/ trees of guasi and sans_cube, and productized as a reusable GitHub template — sans_doc_tree (https://github.com/SansWord/sans_doc_tree). https://sansword.github.io/sans_blog/doc-tree/
- **sans_blog (Writing Hub)** — My writing home: essays and study guides on building software, and on building it with AI. Highlights: "My Tiny AI Bootcamp" (the skeptic-to-shipping story, https://sansword.github.io/sans_blog/tiny-ai-bootcamp/), a worked Leaderboard System Design study guide (https://sansword.github.io/sans_blog/sd_mock/), and agentic-coding pieces like The Document Tree. https://sansword.github.io/sans_blog/
- **guasi (我是) — cross-platform social identity verification** — Shipped a live full-stack product end-to-end: Next.js 16 / React 19, Postgres (Neon) + Prisma, NextAuth, with per-PR preview deploys on isolated DB branches, post-deploy smoke tests, and agentic Claude Code workflows backed by a maintained cost ledger and devlog. The product is a platform-independent identity-verification service: people prove which social accounts are the same person (anti-impersonation) and keep that proof publicly verifiable even if an account is suspended — no platform API access; verification relies on publicly auditable posted content. https://guasi.tw/about
- **sans_ai_mock — an AI mock-interview kit** — Multi-mode Claude Code agent — a root CLAUDE.md mode-routes between interviewer and developer modes on a single repo. Measured per-mock API cost (~$19–$26) across Pro / Max / raw-API tiers; includes feedback rubric, real-run example, and a security-aware CLAUDE.md audit recipe for safe repo onboarding. https://github.com/SansWord/sans_ai_mock
- **sans_cube — Bluetooth Rubik's-cube solve analyzer** — A real-time smart-cube solve analyzer with BLE ingestion, live 3D rendering, phase detection (CFOP/Roux), and opt-in Firestore cloud sync. Deliberately picked an unfamiliar stack to stress-test AI-assisted workflows on greenfield code. https://sansword.github.io/sans_cube/
- **More work** — sans_learning (measured Claude Code cost notes — 7.8× model delta, https://github.com/SansWord/sans_learning) · cut_sh (ffmpeg scripting, https://sansword.github.io/cut_sh/) · sans_yt_summary (Claude skill, prompt-injection hardening, https://github.com/SansWord/sans_yt_summary/)

## Patent

- **Determining Salient Entities and Generating Salient Entity Tags Based Upon Articles** -- US11803605B2. Co-invented methods to identify salient entities in articles at scale and apply them in production recommendation systems at Yahoo. https://patents.google.com/patent/US11803605B2

## Education

- MS Computer Science, National Chengchi University, Taipei, Taiwan -- Major: Programming Languages and Software Methodology
- BS Mathematics, National Chengchi University, Taipei, Taiwan

## Skills

- **Languages:** Python, Java, SQL, Shell, Groovy
- **Cloud — GCP:** Dataproc, Cloud Composer, Dataflow, Airflow, BigQuery
- **Cloud — AWS:** S3, ECS, ELB, ElastiCache
- **Infrastructure:** Terraform, Kubernetes, Docker, Redis
- **Stream Processing:** Apache Storm, Apache Pulsar, Kafka
- **AI Coding Practice:** Agentic Programming, Harness Engineering
