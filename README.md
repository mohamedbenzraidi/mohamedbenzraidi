<div align="center">

# Mohamed Benzraidi

### Software Engineer | Cloud & DevOps | AI/ML

**Building reliable software, automating infrastructure, and exploring intelligent systems.**

<p>
  <a href="https://mohamed-benzraidi.vercel.app/">
    <img src="https://img.shields.io/badge/Portfolio-Visit-2563EB?style=for-the-badge&logo=vercel&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:mohamed.benzraidi.cs@gmail.com">
    <img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,100:1E40AF&height=3" width="100%" />

</div>

## 👨‍💻 About Me

I'm a final-year Software Engineering student at **ENSA Al Hoceima, Morocco**, with a strong interest in software architecture, cloud infrastructure, DevOps, and artificial intelligence.

I enjoy designing and building scalable applications, automating infrastructure, and exploring how software engineering and machine learning can solve real-world problems.

- 🎓 Engineering student in Software Engineering — ENSAH
- ☁️ Interested in Cloud Computing, DevOps & Infrastructure Automation
- 💻 Experienced with Java, Spring Boot, Python and modern software architectures
- 🤖 Exploring Machine Learning and Deep Learning
- 🏢 Former Cloud & DevOps Intern at STMicroelectronics
- 🏢 Former Software Engineering Intern at DGM
- 🎯 Looking for a **PFE Internship — 2027**

---

## ⚡ At a Glance

| 🧩 Projects | 🧱 Microservices | 🐳 Containers | ☸️ K8s deployments | 🧠 ML models | 🔁 CI/CD pipelines |
|:-:|:-:|:-:|:-:|:-:|:-:|
| **4+** | **8+** | **15+** | **Helm + GitOps** | **BiLSTM / LLM** | **Automated** |

| 📝 Lines of code | 🧪 Test coverage | 📦 Commits | ☁️ Cloud | 🔐 Security |
|:-:|:-:|:-:|:-:|:-:|
| **40K+** | **70%+** (core services) | **1,000+** | **AWS** | **JWT · CIS hardening** |

> 💡 Numbers are indicative of my main repositories and grow with every project.

---

## 🛠️ Technical Skills

### Programming Languages
<p>
  <img src="https://skillicons.dev/icons?i=java,python,c,cpp,js,ts,kotlin" />
</p>

### Backend & Software Engineering
<p>
  <img src="https://skillicons.dev/icons?i=spring,nodejs,flask,laravel,hibernate,postgres,mongodb,redis" />
</p>

### Frontend Development
<p>
  <img src="https://skillicons.dev/icons?i=react,nextjs,html,css,tailwind" />
</p>

### Cloud, DevOps & Infrastructure
<p>
  <img src="https://skillicons.dev/icons?i=aws,docker,kubernetes,terraform,ansible,jenkins,githubactions,linux,bash" />
</p>

### AI & Machine Learning
<p>
  <img src="https://skillicons.dev/icons?i=pytorch,tensorflow,opencv" />
</p>

### Tools & Technologies
<p>
  <img src="https://skillicons.dev/icons?i=git,github,idea,vscode,postman,prometheus,grafana" />
</p>

---

## 🚀 Featured Projects

### ☁️ MediCloud — Distributed Healthcare Platform

> A cloud-native healthcare platform where every business capability (patients, appointments, records, notifications) is an independent, observable and deployable microservice.

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=flat-square&logo=argo&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)

| 📝 Lines of code | 🧱 Services | 🔌 REST endpoints | 🐳 Docker images | 📊 Dashboards |
|:-:|:-:|:-:|:-:|:-:|
| **~20K** | **8+** | **60+** | **10+** | **5+** |

```mermaid
flowchart LR
    C[Client] --> G[API Gateway<br/>JWT Auth]
    G --> P[Patient Service]
    G --> A[Appointment Service]
    G --> R[Records Service]
    A -- events --> K[(Kafka)]
    K --> N[Notification Service]
    P --> DB1[(PostgreSQL)]
    R --> DB2[(MongoDB)]
    G --> RD[(Redis cache)]
```

**What makes it solid**
- 🧭 **API Gateway & service discovery** with Spring Cloud for a single, secured entry point
- 🔐 **Stateless JWT authentication** and role-based access control
- 📨 **Event-driven communication** with Kafka for loose coupling and resilience
- ⚡ **Redis caching** to cut latency on hot read paths
- ☸️ **Kubernetes + Helm** packaging, **ArgoCD** GitOps continuous delivery
- 📈 **Prometheus & Grafana** for metrics, dashboards and alerting

#### 🛡️ Zero Trust Security Design

Healthcare data is sensitive, so MediCloud follows one rule: **never trust, always verify**. No request is trusted because of where it comes from. Every hop is authenticated, authorized and logged.

| Zero Trust pillar | Mechanism | Status |
|---|---|:-:|
| Identity | JWT authentication, role-based access | ✅ In place |
| Edge | API Gateway as single secured entry point | ✅ In place |
| Delivery | GitOps with ArgoCD, Helm | ✅ In place |
| Observability | Prometheus and Grafana | ✅ In place |
| Short-lived tokens, MFA | OIDC identity provider | 🛠️ Roadmap |
| Service-to-service trust | mTLS through a service mesh | 🛠️ Roadmap |
| Network isolation | Default-deny Kubernetes NetworkPolicies | 🛠️ Roadmap |
| Secrets | Vault with dynamic DB credentials | 🛠️ Roadmap |
| Policy as code | OPA / Kyverno admission and authorization | 🛠️ Roadmap |
| Supply chain | Trivy scan, SBOM, Cosign image signing | 🛠️ Roadmap |

**1. Zero Trust architecture: every layer verifies**

```mermaid
flowchart TB
    U["👤 User / Client"] -->|HTTPS · TLS 1.3| EDGE
    subgraph EDGE["🌐 Edge · the perimeter is never trusted"]
        WAF["WAF + rate limiting"] --> GW["API Gateway<br/>JWT validation"]
    end
    IDP["🔑 Identity Provider<br/>OIDC · MFA"] -.->|short-lived tokens| GW
    subgraph MESH["☸️ Kubernetes · mTLS between services · default-deny NetworkPolicies"]
        P["Patient Service"]
        A["Appointment Service"]
        R["Records Service"]
        K[("Kafka")]
        N["Notification Service"]
        A -->|mTLS| K
        K -->|mTLS| N
    end
    GW --> P
    GW --> A
    GW --> R
    subgraph DATA["🗄️ Data zone · encrypted at rest"]
        PG[("PostgreSQL")]
        MG[("MongoDB")]
        RD[("Redis")]
    end
    P --> PG
    R --> MG
    GW --> RD
    V["🔐 Vault<br/>secrets and dynamic DB credentials"] -.-> P
    V -.-> R
    POL["📜 Policy engine<br/>OPA / Kyverno"] -.-> MESH
    OBS["📈 Prometheus · Grafana · audit logs"] -.-> MESH
```

**2. Request lifecycle: authenticate and authorize at every hop**

```mermaid
sequenceDiagram
    autonumber
    actor U as Doctor
    participant IDP as Identity Provider
    participant GW as API Gateway
    participant OPA as Policy Engine
    participant S as Records Service
    participant V as Vault
    participant DB as MongoDB
    U->>IDP: Login + MFA
    IDP-->>U: Short-lived JWT
    U->>GW: Request + JWT
    GW->>GW: Verify signature, expiry, audience
    GW->>OPA: Can this role access this resource?
    OPA-->>GW: Allow or Deny
    GW->>S: Forward request over mTLS
    S->>S: Re-validate token and scopes
    S->>V: Ask for DB credentials
    V-->>S: Dynamic credentials with short TTL
    S->>DB: Query over TLS
    DB-->>S: Data
    S-->>GW: Response
    GW-->>U: Response
    Note over GW,DB: Every hop is authenticated, authorized and logged
```

**3. Zero Trust delivery: only verified code reaches the cluster**

```mermaid
flowchart LR
    DEV["👨‍💻 Developer<br/>signed commit"] --> T
    subgraph CI["⚙️ CI pipeline"]
        direction LR
        T["Unit tests"] --> SAST["SAST + dependency scan"] --> B["Build image"] --> TR["Trivy scan"] --> SB["SBOM"] --> SG["Sign with Cosign"]
    end
    SG --> REG[("🐳 Private registry")]
    REG --> GIT["📦 Helm values in Git"]
    GIT --> ARGO["🔄 ArgoCD<br/>GitOps sync"]
    ARGO --> ADM{"🛡️ Admission control<br/>Kyverno / OPA"}
    ADM -->|signature valid, non-root, limits set| OK["✅ Pod deployed"]
    ADM -->|policy violation| KO["❌ Rejected"]
```

🔗 [View Repository](https://github.com/mohamedbenzraidi/medicloud)

---

### 🧠 EarlyAlert ICU — AI-Based Patient Deterioration Prediction

> A deep learning system that analyses sequences of vital signs and lab values to flag ICU patients at risk **before** their condition deteriorates.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

| 📝 Lines of code | 🧬 Architecture | 📈 Input | 🎯 Output | 🖥️ Interface |
|:-:|:-:|:-:|:-:|:-:|
| **~5K** | **BiLSTM + Attention** | **Time-series** | **Risk score** | **Streamlit** |

**Highlights**
- 🔁 **Bidirectional LSTM** to capture temporal dependencies in both directions
- 🎯 **Attention mechanism** to highlight which time steps drive each prediction (explainability)
- 🧹 Full pipeline: preprocessing, imputation, windowing, training, evaluation
- 📊 Metrics tracked: **AUROC, precision/recall, F1** with class-imbalance handling
- 🖥️ **Interactive dashboard** to monitor patients and visualise risk over time

---

### 🏗️ Infrastructure Automation & Provisioning

> Everything as code: from a bare server to a hardened, reproducible environment, with no manual clicks.

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Packer](https://img.shields.io/badge/Packer-02A8EF?style=flat-square&logo=packer&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

| 📝 IaC lines | 🧩 Terraform modules | 📜 Ansible roles | 🖼️ Golden images | ⏱️ Provisioning |
|:-:|:-:|:-:|:-:|:-:|
| **~6K** | **10+** | **10+** | **CIS-hardened Ubuntu** | **Minutes, not hours** |

**Highlights**
- 🏗️ **Terraform** modules for reproducible AWS environments
- 🖼️ **Packer** golden images hardened with **CIS benchmarks**
- 🔧 **Ansible** roles for configuration management and idempotent setup
- 🖧 **Redfish** API for automated bare-metal server provisioning
- ♻️ Same code, same result: dev, test and prod stay consistent

---

### 🤖 Medical AI & RAG

> A medical knowledge assistant that answers questions grounded in trusted documents instead of guessing.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![HuggingFace](https://img.shields.io/badge/BioMistral-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

| 📝 Lines of code | 🧠 Model | ⚙️ Fine-tuning | 🔎 Retrieval |
|:-:|:-:|:-:|:-:|
| **~3K** | **BioMistral** | **QLoRA (4-bit)** | **Vector search** |

**Highlights**
- 🧬 Domain-specific LLM fine-tuned efficiently with **QLoRA** on limited GPU memory
- 📚 **Retrieval-Augmented Generation** to ground answers in source documents and reduce hallucinations
- 🔎 Embeddings + vector database for fast semantic search

---

## 🧭 What I Bring

- ✅ **Architecture mindset**: I design systems that scale and stay maintainable
- ✅ **End-to-end ownership**: from code to container to cluster to monitoring
- ✅ **Automation first**: if I do it twice, I script it
- ✅ **Security aware**: JWT, hardened images, CIS recommendations
- ✅ **Data & AI curiosity**: deep learning and LLMs applied to healthcare

---

## 🎓 Education & Certifications

### Education
**École Nationale des Sciences Appliquées d'Al Hoceima (ENSAH)**

Engineering Degree — Software Engineering  
2022 – 2027 (Expected)


---

## 📊 GitHub Statistics

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=mohamedbenzraidi&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />

<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=mohamedbenzraidi&layout=compact&theme=tokyonight&hide_border=true" />

<img width="95%" src="https://github-readme-streak-stats.herokuapp.com/?user=mohamedbenzraidi&theme=tokyonight&hide_border=true" />

</div>

---

## 🌐 Let's Connect

I'm always interested in discussing software engineering, cloud technologies, DevOps, AI, and innovative projects.

<div align="center">

<a href="https://mohamed-benzraidi.vercel.app/">
  <img src="https://img.shields.io/badge/Personal%20Portfolio-Visit%20Website-2563EB?style=for-the-badge&logo=vercel&logoColor=white" />
</a>

<a href="mailto:mohamed.benzraidi.cs@gmail.com">
  <img src="https://img.shields.io/badge/Email-Get%20in%20Touch-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
</a>

<br/><br/>

**Building today. Engineering tomorrow.**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E40AF,100:0F172A&height=100&section=footer" />

</div>
