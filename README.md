# 👋 Hey, I'm Asmit Gupta! (@pseudorex)
 
**Backend Developer** | Python • FastAPI • System Design  
Building high-performance APIs with intelligent caching, rate limiting, and real-world scalability 🚀
 
<p align="left">
  <a href="https://leetcode.com/u/Asmit_Gupta/" target="_blank">
    <img src="https://img.shields.io/badge/LeetCode-Asmit_Gupta-FFA116?style=flat&logo=leetcode&logoColor=black"/>
  </a>
  <a href="https://www.linkedin.com/in/asmitgpt" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-asmitgpt-0A66C2?style=flat&logo=linkedin&logoColor=white"/>
  </a>
  <a href="mailto:asmit.important@gmail.com">
    <img src="https://img.shields.io/badge/Email-asmit.important-EA4335?style=flat&logo=gmail&logoColor=white"/>
  </a>
</p>

---

## 👨‍💻 About Me

I'm an engineering student passionate about solving real-world performance problems with clean code and thoughtful system design. I specialize in building backend systems that handle traffic intelligently — not just more requests, but *smarter* request handling.

🔹 Strong foundation in algorithms, data structures, and distributed systems  
🔹 Focus on performance optimization, caching strategies, and DDoS mitigation  
🔹 Experience with high-concurrency systems, rate limiting, and real-time communication  
🔹 Love stress-testing with real metrics — if it's not measured, it's not optimized  

---

## 🛠️ Tech Stack

### 🐍 Backend & APIs
<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white"/>
  <img src="https://img.shields.io/badge/REST_API-4A90E2?style=flat"/>
  <img src="https://img.shields.io/badge/WebSockets-4353FF?style=flat"/>
  <img src="https://img.shields.io/badge/SQLAlchemy-000000?style=flat&logo=sqlalchemy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white"/>
</p>

### 🗄️ Databases & Caching
<p align="left">
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=flat&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white"/>
  <img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white"/>
</p>

### 📱 Frontend / Mobile
<p align="left">
  <img src="https://img.shields.io/badge/Flutter-02569B?style=flat&logo=flutter&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dart-0175C2?style=flat&logo=dart&logoColor=white"/>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white"/>
</p>

### ⚙️ DevOps & Testing
<p align="left">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white"/>
  <img src="https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=postman&logoColor=white"/>
  <img src="https://img.shields.io/badge/Locust-000000?style=flat"/>
  <img src="https://img.shields.io/badge/K6-7D64FF?style=flat&logo=k6&logoColor=white"/>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black"/>
</p>

---

## 📊 GitHub Statistics

<p align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=pseudorex&layout=compact&theme=radical&hide_border=true&bg_color=0D1117&title_color=FF6C37&text_color=FFFFFF&langs_count=8" alt="Top Languages" />
</p>

## 🔥 Featured Projects

### 🎼 Webhook Orchestra — Distributed Webhook Delivery Engine

A production-grade, distributed webhook delivery system built for scale, fault tolerance, and zero event loss — backed by FastAPI, Celery, RabbitMQ, and PostgreSQL.

**🎯 The Problem It Solves:**
- Guaranteed delivery even when subscriber endpoints are down, rate-limiting, or flaking
- Cascading failures silently taking down entire delivery pipelines
- No visibility into what failed, why, and what was retried
- Duplicate events and race conditions under high concurrency

**⚙️ Technical Highlights:**

✅ **Zero Event Loss** — All events persisted to PostgreSQL before any delivery attempt  
🔁 **6-Type Failure Classification** — PERMANENT, TRANSIENT, RATE_LIMITED, TIMEOUT, DNS_ERROR, CONNECTION_REFUSED — each with its own backoff strategy  
🔌 **Circuit Breaker** — 3-state machine (CLOSED → OPEN → HALF_OPEN) with 0–100 health scoring; auto-recovers without intervention  
📬 **Dead Letter Queue** — All exhausted retries captured with full failure context; manual replay via API  
🏢 **Multi-Tenant Isolation** — Every event and delivery is tenant-scoped with HMAC-SHA256 payload signing  
🚦 **Adaptive Queue Routing** — 3-tier queue system (high/default/low priority); auto-demotes traffic when backlog exceeds 2000 tasks  
🔒 **Race-Condition Safe** — `SELECT FOR UPDATE` on circuit breaker counters ensures exact threshold enforcement under 32-thread concurrency  
📊 **Full Observability** — Prometheus + Grafana dashboards + Jaeger distributed traces across every hop  

**📈 Load Test Results (Locust — 10+ minute sustained run):**

| Metric | Result |
|--------|--------|
| Total Requests | 19,940 |
| Failure Rate | **0.02%** |
| Sustained Throughput | 29.8 req/sec |
| Median Response Time | 1,300ms |
| p95 Response Time | 3,200ms |
| DLQ Backlog (post-test) | 39 — all failures captured, nothing lost |
| Healthy Endpoint Health Score | 88.5 / 100 |
| Failing Endpoint Health Score | 0 / 100 (circuit opened correctly) |

**Test suite:** 107 tests across circuit breaker, failure classifier, retry policy, signature service, and webhook engine — runs in ~1.3s with zero external dependencies.

**Tech Stack:** FastAPI • Celery • RabbitMQ • PostgreSQL • SQLAlchemy • Prometheus • Grafana • Jaeger • Docker

🔗 **[View Project →](https://github.com/pseudorex/webhook-orchestra)**

---

### 🛡️ QueryShield — Adaptive Rate Limiting & Intelligent Caching Middleware

A production-grade FastAPI middleware that protects backend databases from abuse while dramatically improving API performance through smart caching and endpoint-aware rate limiting.

**🎯 The Problem It Solves:**
- DDoS attacks overwhelming databases
- Expensive analytical queries running repeatedly
- Cache pollution from cold endpoints
- Inability to distinguish attack traffic from legitimate users

**⚙️ Technical Highlights:**

✅ **98.6% Cache Hit Ratio** — Only 361 DB hits out of 30,047 requests in multi-IP stress test  
⚡ **33× Average Speedup** — Redis responses 30–36× faster than PostgreSQL (10ms vs 372ms)  
🛡️ **86% Attack Traffic Blocked** — DDoS simulation with single-IP flood throttled at 86%, multi-IP legitimate traffic only 14%  
🧠 **Adaptive Threshold-Based Caching** — Only hot endpoints cached, preventing memory waste  
📊 **Sliding 1-Hour Window** — Real-time hot endpoint detection using Redis sorted sets  
⏱️ **Dynamic TTL Scaling** — TTL based on query execution cost × endpoint popularity  
🚫 **Zero 500 Errors** — Sustained 250 RPS burst load with complete stability  

**📈 Stress Test Results (Locust):**

| Test Scenario | Requests | Throttled | DB Hits | Cache Hit % | Median Latency |
|---------------|----------|-----------|---------|-------------|----------------|
| Single-IP DDoS | 45,050 | 86% | 175 (0.39%) | 97.1% | 11ms |
| Multi-IP (10 IPs) | 30,047 | 14% | 361 (1.2%) | 98.6% | 120ms |

**Why This Matters:** The system doesn't just block traffic — it's *intelligent*. It crushes malicious single-source floods (86% throttled) while serving legitimate distributed traffic smoothly (only 14% throttled, 98.6% cached). All results are fully reproducible with included Locust test scripts.

**Tech Stack:** FastAPI • PostgreSQL • Redis • Python • Locust

🔗 **[View Project →](https://github.com/pseudorex/QueryShield)**

---

### 🤝 Hackmates — Backend System for Team Formation

A production-style backend built with **FastAPI**, focused on scalability, caching, and real-time communication for hackathon team matching.

**Key Features:**
- Modular FastAPI architecture with clean service/route separation
- Redis for distributed caching & rate limiting
- PostgreSQL with proper indexing and query optimization
- WebSockets (Socket.IO) for real-time team updates
- Alembic for database migrations
- Token-based authentication with JWT

**Tech Stack:** FastAPI • Redis • PostgreSQL • WebSockets • Docker

🔗 **[View Project →](https://github.com/pseudorex/Hackmates)**

---

### 🎯 Math Premier League — Real-Time Quiz Competition Backend

A high-performance FastAPI backend for competitive quiz platforms with WebSocket communication, concurrent question assignment, and production-grade load testing. Built to handle extreme concurrent loads with zero failures.

**🎯 The Problem It Solves:**
- Race conditions in concurrent question assignment
- Real-time leaderboard synchronization across hundreds of teams
- Data integrity under extreme load
- Duplicate question allocation prevention

**⚙️ Technical Highlights:**

✅ **280+ Concurrent Team Registrations** — Handled 4,156 teams in 30 seconds with 100% success rate  
⚡ **Sub-500ms P95 Response Time** — 363ms average response under 100 concurrent users  
🔒 **Zero Duplicate Assignments** — Pessimistic locking + database constraints prevent race conditions  
📡 **WebSocket Real-Time Updates** — Live leaderboard broadcasting to all connected clients  
🧪 **K6 Load Tested** — 8,312 requests across 3 test scenarios with 0 HTTP failures  
🎯 **100% System Uptime** — Maintained stability under extreme 150 VU stress test  

**📊 Load Test Results (K6):**

| Test Scenario | VUs | Duration | Success Rate | Avg Response | P95 Response | Throughput |
|---------------|-----|----------|--------------|--------------|--------------|------------|
| Team Registration | 100 | 30.5s | 100% | 363ms | 499ms | 272 req/s |
| Admin Operations | 60 | 32.4s | 100% | 4.77s | 7.83s | 12 req/s |
| Full System Test | 150 | 46.8s | 100% | 6.47s | 33.73s | 5 req/s |

**Tech Stack:** FastAPI • PostgreSQL • WebSockets • SQLAlchemy • K6 • Uvicorn

🔗 **[View Project →](https://github.com/pseudorex/MPL_normal)**

---

## 🧠 Problem Solving & DSA

- **LeetCode Profile:** Active problem solver with focus on optimized solutions
- **Strong Understanding of:**
  - Arrays, Strings, HashMaps
  - Stacks, Queues, Linked Lists
  - Trees & Graphs (BFS, DFS, Dijkstra)
  - Dynamic Programming & Greedy Algorithms
- **Approach:** Write readable, maintainable code with clear time/space complexity analysis

🔗 **[LeetCode Profile](https://leetcode.com/u/Asmitrex/)**

---

## 📫 Let's Connect

<p align="left">
  <a href="mailto:asmit.important@gmail.com">
    <img src="https://img.shields.io/badge/Email-asmit.important-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
  <a href="https://www.linkedin.com/in/asmitgpt" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-asmitgpt-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://github.com/pseudorex" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-pseudorex-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
  <a href="https://leetcode.com/u/Asmitrex/" target="_blank">
    <img src="https://img.shields.io/badge/LeetCode-Asmitrex-FFA116?style=for-the-badge&logo=leetcode&logoColor=black"/>
  </a>
</p>

---

## 💡 What I'm Working On

- 🔬 Exploring distributed systems patterns (circuit breakers, bulkheads, retries)
- 🧪 Building more adaptive middleware for API protection
- 📚 Deepening knowledge in system design and scalability
- 🚀 Open to backend development opportunities and collaborations

---

## 🎯 Activity Graph

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=pseudorex&bg_color=0d1117&color=ff6c37&line=ff6c37&point=ffffff&area=true&hide_border=true" alt="Contribution Graph" />
</p>

---

<p align="center">
  <i>⭐ Let's build something that handles traffic intelligently, not just more traffic.</i>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=pseudorex&label=Profile%20Views&color=FF6C37&style=flat" alt="Profile Views" />
</p>
