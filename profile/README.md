# 🦷 Goldentooth 🦷
( <span style="display:inline-block; min-width: 2em;">🌀</span>[ndouglas](https://github.com/ndouglas/) | <span style="display:inline-block; min-width: 2em;">🌉</span>[bitterbridge](https://github.com/bitterbridge/) | <span style="display:inline-block; min-width: 2em;">️‍🔥</span>[hellholt](https://github.com/hellholt/) | <span style="display:inline-block; min-width: 2em;">🦷</span>[goldentooth](https://github.com/goldentooth/) )

---

## 🧩 What Is Goldentooth?

Goldentooth is [my](https://github.com/ndouglas/) personal Pi Bramble — a 12-node Raspberry Pi 4B (8GB RAM, 128-256GB SD, 120GB-1TB SSD) cluster housed in a 12U 10" rack.

That's about as puny as anything with 48 cores and 96GB RAM could possibly be.

It's a sandbox for experimenting with distributed systems, orchestration layers, and failure modes. Services have no purpose but to teach me how they behave under stress, failure, and reconfiguration.

Think of it as a **Chaos Zoo**, a system design playground, or a physical dev environment for recursive infrastructure.

---

![My Cluster](./cluster.png)

## 🗺️ Node Layout

| Role         | Nodes                                      | Responsibilities |
|--------------|--------------------------------------------|------------------|
| 🧭 **Edge**   | `Allyrion`                                 | Load balancer, NFS, HAProxy, Envoy, Consul client |
| 🧠 **Leaders**| `Bettley`, `Cargyll`, `Dalt`               | Kubernetes control plane, Vault, Nomad/Slurm servers, Consul servers |
| 🧑‍🌾 **Workers**| `Erenford`, `Fenn`, `Gardener`, `Harlton`, `Inchfield`, `Jast`, `Karstark`, `Lipps` | Kubernetes workers, Nomad/Slurm clients, Consul clients |

---

## 🔧 Service Table

| **Service**                       | **Tool(s)**                                 | **Type**             | **Interface(s)**            | **Exposed?**     |
|-----------------------------------|---------------------------------------------|----------------------|-----------------------------|------------------|
| Cluster Orchestration             | Kubernetes, Nomad                           | Control Plane        | `kubectl`, REST API         | Internal         |
| Scheduling                        | Slurm, Nomad                                | Batch/Job Scheduler  | CLI, REST                   | Internal         |
| Deployment Automation             | Argo CD                                     | GitOps Controller    | Web UI, CLI                 | Internal         |
| Secrets Management                | Vault, SealedSecrets, ExternalSecrets       | Secret Store         | CLI, API, CRDs              | Internal         |
| Observability                     | Prometheus, Node Exporter, Grafana          | Metrics              | PromQL, HTTP                | Internal         |
| Service Discovery                 | Consul, mDNS                                | Internal DNS         | DNS, HTTP API               | Internal         |
| Baremetal K8s Load Balancing      | MetalLB                                     | L2 (formerly BGP)    | K8s, ARP                    | Internal         |
| Networking / Routing              | HAProxy, Envoy                              | L4/L7 Proxying       | TCP, HTTP                   | Some Public      |
| Data Storage                      | NFS                                         | Shared Filesystem    | NFS Protocol                | Internal         |
| DNS Management                    | ExternalDNS                                 | Cloud DNS Updates    | CRDs                        | Internal         |
| Log Collection/Shipping           | Vector                                      | Log Shipper          | Various                     | Internal         |
| Log Aggregation                   | Loki                                        | Log Aggregator       | HTTP                        | Internal         |

---

## 📦 Repositories

- ❓ [seaweedfs-cluster](https://github.com/goldentooth/seaweedfs-cluster): SeaweedFS distributed storage cluster deployment for Goldentooth infrastructure
- ❓ [p5js-sketches](https://github.com/goldentooth/p5js-sketches): P5.js Sketch Server - Static file server for hosting p5.js sketches on Ceph storage
- ❓ [seaweedfs-operator](https://github.com/goldentooth/seaweedfs-operator): SeaweedFS Kubernetes Operator deployment for Goldentooth cluster
- 🐚 [bash](https://github.com/goldentooth/bash): Bash scripts for interacting with GoldenTooth, my Pi Bramble/Cluster
- ❓ [cert-manager](https://github.com/goldentooth/cert-manager): cert-manager with step-ca ACME integration for Goldentooth Kubernetes cluster
- 🧰 [ansible](https://github.com/goldentooth/ansible): Basic setup for my Pi bramble/cluster.
- ❓ [seaweedfs](https://github.com/goldentooth/seaweedfs): SeaweedFS distributed storage cluster for Goldentooth Pi infrastructure - ReadWriteMany storage optimized for ARM64 hardware
- 🚜 [terraform](https://github.com/goldentooth/terraform): General Terraform Infrastructure-as-Code for Goldentooth
- ❓ [longhorn](https://github.com/goldentooth/longhorn): Longhorn distributed block storage for Goldentooth Pi infrastructure - High-performance ReadWriteOnce storage optimized for SSD and ARM64 hardware
- 👋 [.github](https://github.com/goldentooth/.github): My ✨special ✨ repository
- ❓ [p5js-template](https://github.com/goldentooth/p5js-template): Template for P5.js sketches
- 🧲 [metallb](https://github.com/goldentooth/metallb): MetalLB ArgoCD application
- 🧱 [clog](https://github.com/goldentooth/clog): The changelog formerly known as "Kubernetes, the _Excruciating_ Way".
- 📈 [kube-state-metrics](https://github.com/goldentooth/kube-state-metrics): Kubernetes object metrics collection for the goldentooth cluster
- 🧰 [cross-compile-toolkit](https://github.com/goldentooth/cross-compile-toolkit): Containerized cross-compilation toolkit for ARM64 binaries targeting Raspberry Pi cluster
- 🔐 [sealed-secrets](https://github.com/goldentooth/sealed-secrets): SealedSecrets GitOps repository.
- 🗝️ [external-secrets](https://github.com/goldentooth/external-secrets): GitOps repository for ExternalSecrets
- 📡 [httpbin](https://github.com/goldentooth/httpbin): `httpbingo` Argo CD application
- 🌐 [external-dns](https://github.com/goldentooth/external-dns): ExternalDNS GitOps repository.
- 📊 [grafana-dashboards](https://github.com/goldentooth/grafana-dashboards): Grafana Dashboards
- 🛰️ [mcp-server](https://github.com/goldentooth/mcp-server): MCP server for Goldentooth cluster management
- 🧞 [agent](https://github.com/goldentooth/agent): An experimental intelligent agent for my Pi Bramble
- 🫀 [pulse](https://github.com/goldentooth/pulse): Node network effects visualized as a heartbeat.
- 🛣️ [roadmap](https://github.com/goldentooth/roadmap): Planning and researching the future of Goldentooth.
- 🧬 [gitops-template](https://github.com/goldentooth/gitops-template): A template for my GitOps repositories.
- 🛡️ [asoiaf-noble-house-images](https://github.com/goldentooth/asoiaf-noble-house-images): Images derived from arms from noble houses of ASoIaF.


---

## Permissions
Everything's under an [Unlicense](https://choosealicense.com/licenses/unlicense/).

!["Nothing is true." "Everything is permitted."](./niteip.jpg)

---

< [@ndouglas](https://github.com/ndouglas/)
