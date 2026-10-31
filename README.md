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

| 🔐 Cloud IAM Zero Trust | 🏥 MediCloud |
|:--|:--|
| **3** AWS accounts federated through one IdP | **7** Spring Boot modules (4 business services) |
| **6** Terraform modules + bootstrap | **1** event-driven flow with Kafka |
| **4** organization-level guardrails (SCP) | **Redis** rate limiting + circuit breaker |
| **11** documented test scenarios | **React** frontend served through the gateway |

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

### 🔐 Cloud IAM Zero Trust — Multi-Account AWS SSO Federation

> One identity provider, three AWS accounts: SAML single sign-on, mandatory MFA, least privilege, organization-wide guardrails, sensitive-event detection, and everything deployed as code.

![Terraform](https://img.shields.io/badge/IaC-Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/Cloud-AWS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![Keycloak](https://img.shields.io/badge/IdP-Keycloak-4D4D4D?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/CI-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Status](https://img.shields.io/badge/status-in%20progress-yellow?style=flat-square)

| 🏢 AWS accounts | 🧩 Terraform modules | 🚫 SCP guardrails | 🧪 Test scenarios | 🗝️ Human access keys |
|:-:|:-:|:-:|:-:|:-:|
| **3** (security, dev, prod) | **6** + bootstrap | **4** | **11** | **0** |

**Architecture**

```mermaid
flowchart TB
    U["👤 Users<br/>password + OTP"] --> KC["🔑 Keycloak IdP<br/>cloud-admins · developers · auditors"]
    KC -->|SAML 2.0 signed assertion| IC["🪪 AWS IAM Identity Center<br/>permission sets"]
    subgraph ORG["🏢 AWS Organizations · SCP guardrails"]
        SEC["🛡️ security account<br/>org CloudTrail · Access Analyzer"]
        DEV["🧪 dev account<br/>limited PowerUser"]
        PROD["🚀 prod account<br/>ReadOnly · Admin 1 h"]
    end
    IC --> SEC
    IC --> DEV
    IC --> PROD
    SEC --> EB["🔔 EventBridge + SNS<br/>sensitive-event alerts"]
    GH["⚙️ GitHub Actions<br/>OIDC, no stored keys"] --> TF["📦 Terraform plan<br/>Checkov · gitleaks"]
    TF -.-> ORG
```

**Authentication flow**

```mermaid
sequenceDiagram
    autonumber
    actor U as User
    participant IC as IAM Identity Center
    participant KC as Keycloak
    participant AWS as AWS account
    participant CT as CloudTrail + EventBridge
    U->>IC: Open the SSO portal
    IC->>KC: Redirect for authentication
    KC->>U: Ask password + OTP
    U->>KC: Credentials + second factor
    KC-->>IC: Signed SAML assertion
    IC-->>U: Choose account and role
    U->>AWS: Temporary session on the allowed role
    AWS->>CT: Every action is logged
    CT-->>U: Alert on root login, IAM user creation, policy change, break-glass use
```

**What makes it solid**
- 🔑 **Single identity per person**, no local IAM users and no long-lived keys for humans (one documented break-glass exception)
- 🛂 **Role-based access**: groups → permission sets → accounts, with a 1 h session for admins
- 🎯 **Least privilege driven by real activity**: a broad starting policy replaced by one generated from IAM Access Analyzer
- 🚧 **Organization guardrails (SCP)**: protect CloudTrail, forbid root usage, IAM users and access keys, restrict allowed regions
- 🚨 **Detection**: EventBridge → SNS alerts on sensitive events
- 🤖 **100% Infrastructure as Code**: Terraform with encrypted S3 state and native locking, CI with `fmt`, `validate`, Checkov, gitleaks and `plan`
- 📊 **Measurable outcome**: Prowler (CIS AWS) score before and after

---

### 🏥 MediCloud — Cloud-Native Medical Platform

> A microservices platform for patient and appointment management, built with Spring Boot 3 and Spring Cloud, where booking an appointment triggers an asynchronous notification through Kafka.

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)

| 🧱 Spring modules | 💼 Business services | 📨 Kafka flow | 🛡️ Resilience | 📘 API docs |
|:-:|:-:|:-:|:-:|:-:|
| **7** | **4** (auth, patient, appointment, notification) | **1** appointment → notification | **Rate limiting + circuit breaker** | **Swagger** |

**Architecture**

```mermaid
flowchart TB
    FE["🖥️ React + Vite frontend"] --> GW["🚪 API Gateway :8080<br/>routing · rate limiting · circuit breaker"]
    GW --> AU["🔐 Auth :8081<br/>register · login · refresh · JWT"]
    GW --> PA["🧑‍⚕️ Patient :8082<br/>CRUD · Swagger"]
    GW --> AP["📅 Appointment :8083<br/>CRUD · OpenFeign"]
    AP -->|appointment-scheduled-topic| K[("Kafka")]
    K --> NO["📧 Notification :8084<br/>email simulation"]
    GW --> RD[("Redis")]
    AU --> PG[("PostgreSQL")]
    PA --> PG
    AP --> PG
    NO --> PG
    EU["🧭 Eureka :8761<br/>service discovery"] -.-> GW
    CS["⚙️ Config Server :8888"] -.-> GW
```

**Event-driven flow**

```mermaid
sequenceDiagram
    autonumber
    actor U as User
    participant GW as API Gateway
    participant AP as Appointment Service
    participant K as Kafka
    participant NO as Notification Service
    U->>GW: POST appointment
    GW->>AP: Route request
    AP->>AP: Save appointment
    AP-)K: Publish appointment-scheduled event
    AP-->>U: 201 Created
    K-)NO: Consume event
    NO->>NO: Build and send email
    Note over AP,NO: The user never waits for the notification
```

**Engineering status**

| Area | Status |
|---|:-:|
| Service discovery (Eureka), Auth with JWT, Appointment + Kafka producer | ✅ Done |
| API Gateway with Redis rate limiting and circuit breaker | ✅ Done |
| React frontend, Docker Compose, Kubernetes manifests (Deployments, Ingress, HPA) | ✅ Done |
| Gateway routing alignment and JWT enforcement on Patient service | 🚧 In progress |
| Helm charts, ArgoCD, Prometheus and Grafana | 🛠️ Roadmap |
| Testcontainers and higher test coverage, real email/SMS provider | 🛠️ Roadmap |

🔗 [View Repository](https://github.com/mohamedbenzraidi/medicloud)

---

## 🧭 What I Bring

- ✅ **Architecture mindset**: I design systems that scale and stay maintainable
- ✅ **End-to-end ownership**: from code to container to cloud account
- ✅ **Automation first**: if I do it twice, I script it
- ✅ **Security by design**: SAML SSO, MFA, least privilege, organization guardrails, JWT
- ✅ **Honest engineering**: I document limits, trade-offs and what is still on the roadmap

---

## 🎓 Education

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
