<div align="center">

# Nelson Ramos

Computer Engineering student at Universidade de Aveiro (LECI, 2024–2027).  
Focused on DevOps/SRE, infrastructure and low-level software development.

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nelsonrocharamos/)
[![University](https://img.shields.io/badge/UAveiro-LECI-003DA5?style=flat&logo=academia&logoColor=white)](https://www.ua.pt/)
[![English C1](https://img.shields.io/badge/English-C1_Advanced-8B0000?style=flat&logo=britishcouncil&logoColor=white)](https://credentials.britishcouncil.org/8859dfbd-536b-4795-a296-d4aa7d458980)

<br>

🇵🇹 Portugal
</div>

---

## About

Computer Engineering student at **Universidade de Aveiro** (LECI, 2024–2027), with a strong focus on **DevOps / SRE / Infrastructure** and **low-level software development**.

I've built a solid foundation in C - data structures, manual memory management and performance-oriented design - and I'm actively deepening my knowledge of CI/CD pipelines, containerisation, cloud infrastructure, infrastructure-as-code, and observability. \
I enjoy working at the boundary between systems programming and automation: writing code that runs fast and pipelines that ship reliably.

I'm curious, problem-driven, and looking to grow inside teams where I can both contribute and learn from experienced engineers.

---

## Tech Stack & Expertise

| Domain | Tools & Technologies |
| :--- | :--- |
| **Languages** | `C` - `Go`, `Python` - `Bash` - `C++` |
| **Systems** | `Linux` - `cgroups v2` - `namespaces` - `systemd` - `sockets` |
| **Infrastructure** | `Terraform` - `Ansible` - `AWS (EC2, VPC, Route53, NAT)` - `OCI` |
| **Observability** | `Prometheus` - `Grafana` - `Alertmanager` |
| **DevOps** | `GitHub Actions` - `Kubernetes` - `Docker` - `CI/CD Pipelines` |
| **Build & Tooling** | `Make` - `CMake` - `GCC/Clang` - `Valgrind` - `GDB` |
| **Quality & Sec** | `cppcheck` - `gosec` - `Trivy` - `CodeQL` - `race detector` |

---

## Featured Projects

### [Forge](https://github.com/nelsonramosua/Forge) - Self-Hosted PaaS
 
A deployment platform built from scratch. Push to GitHub -> app live at its own HTTPS subdomain. No Docker, no Kubernetes, no third-party platform.
 
**Infrastructure & operations:**
- Terraform stacks for AWS and OCI: VPC/VCN, public/private subnets, NAT gateway, EC2, Route53, scoped security groups. Workers in private subnets with no public IP.
- Ansible bootstraps both hosts: compiles from source, renders ansible-vault-encrypted env files, manages systemd units for all services.
- Caddy as a dynamic reverse proxy — routes and TLS certificates provisioned automatically per subdomain on every deploy via its JSON Admin API.
- Prometheus + Grafana + Alertmanager for observability, with a custom Go metrics exporter per worker node.
- Automatic rollback on health check failure. Graceful process lifecycle (SIGTERM -> grace -> SIGKILL). cgroup v2 + Linux namespace isolation.

**System design:**
- Control plane in Go: HMAC-SHA256 webhook validation, task scheduler, SQLite WAL state, AES-256-GCM secrets vault, SSE log streaming.
- Worker agent in C11: poll-driven task execution, hand-rolled HTTP client, custom recursive-descent JSON parser, Linux user/PID/mount namespaces, no container runtime.
- CI: Go vet/lint/race detector, strict C compilation, gosec, Trivy, CodeQL, Terraform validate, Ansible lint, E2E tests.
Live at [nforge.space](https://nforge.space) - Admin console at [admin.nforge.space](https://admin.nforge.space).
 
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)

### [miniAI](https://github.com/nelsonramosua/miniAI) — Neural Network from Scratch in C

A complete feed-forward neural network built in pure C, zero ML library dependencies.

- Backpropagation, ReLU/Softmax activations, L2 regularisation, gradient clipping.
- Custom **arena allocator** for high-performance memory management.
- PNG image pipeline with automatic character segmentation.
- **98%+ accuracy** on digit/alphanumeric recognition (62 classes).
- Full hyperparameter grid search with automatic config persistence.
- CI/CD on Linux + macOS, Docker Hub releases, GitHub Pages docs.

![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-2088FF?style=flat-square&logo=githubactions&logoColor=white)

---

### [TSP Solver](https://github.com/nelsonramosua/TSP) — Algorithms for the Travelling Salesman Problem

Side-by-side comparison of exact, heuristic, and meta-heuristic TSP algorithms in pure C.

| Category | Algorithms |
|:---|:---|
| Exact | Exhaustive Search (±pruning), Held-Karp |
| Heuristic | Nearest Neighbour, Greedy, Nearest Insertion, Christofides |
| Meta-heuristic | 2-Opt, Simulated Annealing, Ant Colony, Genetic Algorithm |
| Lower Bounds | MST, Held-Karp Lagrangian Relaxation |

CI/CD on Linux + macOS, Docker Hub releases, GitHub Pages docs.

Benchmarked on TSPLIB instances (Eil51, Oliver30, Swiss42). \
**< 3% error** vs optimal on real European city graphs with the best meta-heuristics.

![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-2088FF?style=flat-square&logo=githubactions&logoColor=white)

---

## Education

- **Licenciatura em Engenharia de Computadores e Informática (LECI)**. \
Universidade de Aveiro: Sep 2024 - Jun 2027 (Expected): Current GPA: 16/20.
- **Ensino Secundário em Ciências e Tecnologias**. \
Escola Secundária Dr. Mário Sacramento: Sep 2021 - Jun 2024: GPA: 18/20.

---

## Languages

- Portuguese - Native. 
- English - C1/C2 (Aptis ESOL Advanced, British Council, issue Apr 2024).

---

<div align="center">
<sub>Please, feel free to explore the repos, open issues, open pull requests, contribute or reach out on LinkedIn.</sub>
</div>
