# 🦷 GoldenTooth 🦷
( <span style="display:inline-block; min-width: 2em;">🌀</span>[ndouglas](https://github.com/ndouglas/) | <span style="display:inline-block; min-width: 2em;">🌉</span>[bitterbridge](https://github.com/bitterbridge/) | <span style="display:inline-block; min-width: 2em;">️‍🔥</span>[hellholt](https://github.com/hellholt/) | <span style="display:inline-block; min-width: 2em;">🦷</span>[goldentooth](https://github.com/goldentooth/) )

---

## 🧩 What Is GoldenTooth?

GoldenTooth is [my](https://github.com/ndouglas/) personal Pi Bramble — a ten-node Raspberry Pi 4B (8GB RAM, 128GB SD) cluster housed in a PicoCluster 10H.

It's a sandbox for experimenting with distributed systems, orchestration layers, and failure modes. Services have no purpose but to teach me how they behave under stress, failure, and reconfiguration.

Think of it as a **Chaos Zoo**, a system design playground, or a physical dev environment for recursive infrastructure.

---

## 🗺️ Node Layout

| Role         | Nodes                                      | Responsibilities |
|--------------|--------------------------------------------|------------------|
| 🧭 **Edge**   | `Allyrion`                                 | Load balancer, NFS, HAProxy, Envoy, Consul client |
| 🧠 **Leaders**| `Bettley`, `Cargyll`, `Dalt`               | Kubernetes control plane, Vault, Nomad/Slurm servers, Consul servers |
| 🧑‍🌾 **Workers**| `Erenford`, `Fenn`, `Gardener`, `Harlton`, `Inchfield`, `Jast` | Kubernetes workers, Nomad/Slurm clients, Consul clients |

---

## 🔧 Affordance Table

| **Affordance**             | **Tool(s)**                          | **Type**             | **Interface(s)**            | **Exposed?**     |
|---------------------------|--------------------------------------|----------------------|-----------------------------|------------------|
| Cluster Orchestration     | Kubernetes, Nomad                    | Control Plane        | `kubectl`, REST API         | Internal only    |
| Scheduling                | Slurm, Nomad                         | Batch/Job Scheduler  | CLI, REST                   | Internal         |
| Deployment Automation     | Argo CD                              | GitOps Controller    | Web UI, CLI                 | Optional         |
| Secrets Management        | Vault, SealedSecrets, ExternalSecrets| Secret Store         | CLI, API, CRDs              | Internal         |
| Observability             | Prometheus, Node Exporter            | Metrics              | PromQL, HTTP                | Partially Public |
| Service Discovery         | Consul, mDNS                         | Internal DNS         | DNS, HTTP API               | Internal         |
| Networking / Routing      | HAProxy, Envoy, MetalLB              | L4/L7 Proxying       | TCP, HTTP                   | Some Public      |
| Data Storage              | NFS                                  | Shared Filesystem    | NFS Protocol                | Internal         |
| DNS Management            | ExternalDNS                          | Cloud DNS Updates    | CRDs                        | Yes              |

---

## 📦 Repositories

- 👋 [.github](https://github.com/goldentooth/.github): My ✨special ✨ repository
- 🚜 [terraform](https://github.com/goldentooth/terraform): General Terraform Infrastructure-as-Code for Goldentooth
- 🛣️ [roadmap](https://github.com/goldentooth/roadmap): Planning and researching the future of Goldentooth.
- 🫀 [pulse](https://github.com/goldentooth/pulse): Node network effects visualized as a heartbeat.
- 🧱 [clog](https://github.com/goldentooth/clog): Dev blog, formerly known as **Kubernetes, the _Excruciating_ Way**
- 🗝️ [external-secrets](https://github.com/goldentooth/external-secrets): GitOps repository for ExternalSecrets
- 🔐 [sealed-secrets](https://github.com/goldentooth/sealed-secrets): SealedSecrets GitOps repository.
- 🌐 [external-dns](https://github.com/goldentooth/external-dns): ExternalDNS GitOps repository.
- 🧬 [gitops-template](https://github.com/goldentooth/gitops-template): A template for my GitOps repositories.
- 📈 [prometheus-node-exporter](https://github.com/goldentooth/prometheus-node-exporter): Argo CD application
- 📡 [httpbin](https://github.com/goldentooth/httpbin): `httpbingo` Argo CD application
- 🧲 [metallb](https://github.com/goldentooth/metallb): MetalLB ArgoCD application
- 🛡️ [asoiaf-noble-house-images](https://github.com/goldentooth/asoiaf-noble-house-images): Images derived from arms from noble houses of ASoIaF.
- 🐚 [bash](https://github.com/goldentooth/bash): Bash scripts for interacting with GoldenTooth, my Pi Bramble/Cluster
- 🧰 [ansible](https://github.com/goldentooth/ansible): Basic setup for my Pi bramble/cluster.


---

## Permissions
Everything's under an [Unlicense](https://choosealicense.com/licenses/unlicense/).

!["Nothing is true." "Everything is permitted."](./niteip.jpg)

---

< [@ndouglas](https://github.com/ndouglas/)