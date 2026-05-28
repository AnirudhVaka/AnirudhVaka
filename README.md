<!--
  GitHub Profile README for AnirudhVaka
  HOW TO USE:
  1. Create a new PUBLIC repo named exactly: AnirudhVaka
  2. Add this file as README.md
  3. Commit. It will render automatically at the top of your profile.
  4. Settings > Profile > enable "Include private contributions on my profile"
     so your activity graph looks active even though work is in private repos.
-->

<h1 align="center">Hi, I'm Anirudh Vaka 👋</h1>

<p align="center">
  <b>Senior DevOps Engineer & DevOps Lead</b><br/>
  I build and operate production cloud infrastructure — and ship AI/LLM systems on top of it.
</p>

<p align="center">
  <a href="https://anirudhvaka.dev"><img src="https://img.shields.io/badge/Portfolio-anirudhvaka.dev-0A66C2?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio"/></a>
  <a href="https://linkedin.com/in/anirudhvaka"><img src="https://img.shields.io/badge/LinkedIn-anirudhvaka-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://prepatlas.in/engineering"><img src="https://img.shields.io/badge/Writeups-prepatlas.in/engineering-FF6B35?style=for-the-badge&logo=readme&logoColor=white" alt="Engineering Writeups"/></a>
  <a href="mailto:anirudhvaka@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

---

### 🚀 About Me

I lead DevOps for a **B2B SaaS platform serving 1000+ customers globally**, running production **AWS** and **Kubernetes** at **99.9% uptime**. I'm equally at home architecting multi-region cloud infrastructure, building secure CI/CD pipelines, and self-hosting LLMs on bare metal. On the side, I build and operate **two live AI SaaS products** with paying users.

- 🏗️ **I design for scale & reliability** — multi-region AWS, active-active failover, 200+ CI/CD pipelines
- 🤖 **I ship AI infrastructure** — self-hosted LLMs (DeepSeek, Qwen), RAG with pgvector, Claude integration
- 🔐 **I own security end-to-end** — SOC 2 (Type 1 & 2), SonarQube, OPA/Gatekeeper, container hardening
- 👥 **I lead a team of 5** — setting standards, owning architecture, mentoring on cloud-native practices

---

### 🏛️ How I Architect Systems

A reference architecture in the style of what I build and operate in production:

```mermaid
flowchart TB
    subgraph Users["🌐 Global Users"]
        U[Users / Clients]
    end

    subgraph Edge["☁️ Edge & DNS"]
        R53[Route 53<br/>Active-Active Failover]
        CF[CloudFront CDN]
    end

    subgraph CICD["🔄 CI/CD & GitOps"]
        GH[GitHub Actions]
        ARGO[ArgoCD]
        TF[Terraform IaC]
    end

    subgraph Region1["🟢 AWS Region (Primary)"]
        ALB1[Load Balancer]
        subgraph EKS1["EKS Cluster"]
            SVC1[Microservices<br/>100+ containers]
        end
        RDS1[(RDS / PostgreSQL)]
        REDIS1[(Redis)]
    end

    subgraph AI["🤖 AI / LLM Layer"]
        OLLAMA[Self-Hosted LLMs<br/>DeepSeek · Qwen via Ollama]
        RAG[RAG + pgvector]
        CLAUDE[Anthropic Claude API]
    end

    subgraph Obs["📊 Observability"]
        PROM[Prometheus]
        GRAF[Grafana]
        LOKI[Loki]
    end

    subgraph Sec["🔐 Security & DevSecOps"]
        IAM[IAM · KMS · Secrets Mgr]
        SCAN[Trivy · SonarQube · OPA]
    end

    U --> R53 --> CF --> ALB1 --> EKS1
    GH --> ARGO --> EKS1
    TF -.provisions.-> Region1
    EKS1 --> RDS1
    EKS1 --> REDIS1
    EKS1 --> RAG --> OLLAMA
    RAG --> CLAUDE
    EKS1 -.metrics/logs.-> Obs
    Sec -.guards.-> EKS1
    Sec -.guards.-> CICD
```

---

### 🛠️ Tech Stack

**☁️ Cloud & Infrastructure**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)

**🔄 CI/CD & GitOps**

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)
![ArgoCD](https://img.shields.io/badge/Argo_CD-EF7B4D?style=flat-square&logo=argo&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab_CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white)

**📊 Observability**

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Loki](https://img.shields.io/badge/Loki-F5A800?style=flat-square&logo=grafana&logoColor=white)
![Sentry](https://img.shields.io/badge/Sentry-362D59?style=flat-square&logo=sentry&logoColor=white)

**🤖 AI / LLM Infrastructure**

![Ollama](https://img.shields.io/badge/Ollama_(Self--Hosted_LLMs)-000000?style=flat-square&logo=ollama&logoColor=white)
![Claude](https://img.shields.io/badge/Anthropic_Claude-D97757?style=flat-square&logo=anthropic&logoColor=white)
![pgvector](https://img.shields.io/badge/pgvector_RAG-4169E1?style=flat-square&logo=postgresql&logoColor=white)

**🔐 Security & DevSecOps**

![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square&logo=sonarqube&logoColor=white)
![OPA](https://img.shields.io/badge/OPA_/_Gatekeeper-7D9199?style=flat-square&logo=openpolicyagent&logoColor=white)
![Trivy](https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aquasecurity&logoColor=white)

**💻 Languages & Data**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)

---

### 🚢 Things I've Built

| Project | What it is | Stack |
|---------|-----------|-------|
| **[PrepAtlas](https://prepatlas.in)** | AI exam-prep SaaS with grounded RAG — live, paying users. [Engineering writeups →](https://prepatlas.in/engineering) | Next.js · pgvector · Claude · AWS |
| **[HumanifyCV](https://humanifycv.com)** | AI text-humanization SaaS with a custom Claude AI router — live, paying customers | TypeScript · AWS ECS · PostgreSQL |
| **Self-Hosted LLM Platform** | DeepSeek & Qwen on-prem via Ollama — internal chatbot + dev coding assistant | Ollama · On-prem · API layer |

---

### 📈 Highlights

```text
⚡ 99.9% uptime         across hybrid Kubernetes (EKS + on-prem)
🚀 ~60% faster releases via zero-downtime deployments
🛡️ ~70% fewer errors    through automated CI/CD security gates
💰 ~25% cost reduction  via Python automation & right-sizing
📦 200+ pipelines       built across multiple services & environments
🔐 SOC 2 Type 1 & 2     full ownership of controls, evidence, audits
```

---

### 📊 GitHub Activity

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=AnirudhVaka&show_icons=true&count_private=true&hide_border=true&theme=tokyonight" alt="GitHub Stats" height="160"/>
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=AnirudhVaka&hide_border=true&theme=tokyonight" alt="GitHub Streak" height="160"/>
</p>

---

### 📌 A Note on My Repositories

Most of my work lives in **private company and product repositories** — client infrastructure, SaaS products, and internal tooling — so my public GitHub shows only a fraction of what I build. My **[portfolio](https://anirudhvaka.dev)** and **[engineering writeups](https://prepatlas.in/engineering)** are the best window into how I architect and operate real systems.

<p align="center"><i>Always happy to talk infrastructure, reliability, and AI systems → anirudhvaka@gmail.com</i></p>
