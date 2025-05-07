# 🦷 GoldenTooth 🦷
( <span style="display:inline-block; min-width: 2em;">🌀</span>[ndouglas](https://github.com/ndouglas/) | <span style="display:inline-block; min-width: 2em;">🌉</span>[bitterbridge](https://github.com/bitterbridge/) | <span style="display:inline-block; min-width: 2em;">️‍🔥</span>[hellholt](https://github.com/hellholt/) | <span style="display:inline-block; min-width: 2em;">🦷</span>[goldentooth](https://github.com/goldentooth/) )

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps/MLOps playground without any important services or data.

I'm building this cluster not to host anything in particular, but to act as something as a Chaos Zoo, where I just deploy things and then try to destroy them to learn about their behavior. No service has, or will have, any purpose other than as a way of learning about itself or the other services.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B (8GB RAM, 128GB SD).

Currently, it has the following general structure:
- 1 load balancer/proxy node: Allyrion
  - HAProxy for high availability of the Kubernetes control plane nodes
  - Nginx as a general-purpose HTTP/S proxy
  - NFS server for shared data
  - Consul client
  - Envoy for edge-routing services
- 3 "leader" nodes: Bettley, Cargyll, and Dalt
  - Kubernetes control plane
  - Slurm controllers
  - Consul servers
  - Vault servers
  - Nomad servers
- 6 "follower" nodes: Erenford, Fenn, Gardener, Harlton, Inchfield, and Jast
  - Kubernetes worker nodes
  - Slurm compute nodes
  - Consul clients
  - Nomad clients

## Repositories
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


## Software/Services

Here's a list of some of the major services/tools/applications I have installed and running on GoldenTooth. This list will expand greatly.

- [Raspberry Pi OS](https://www.raspberrypi.com/software/)
- [HAProxy](https://www.haproxy.org)
- [Kubernetes](https://kubernetes.io)
- [Argo CD](https://argoproj.github.io/cd/)
- [Slurm](http://slurm.schedmd.com)
- [Consul](https://www.consul.io)
- [Vault](https://vaultproject.io/)
- [Envoy](https://www.envoyproxy.io/)
- [Nomad](https://www.nomadproject.io)

## Permissions
I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves interesting or useful to other engineers.

---

< [@ndouglas](https://github.com/ndouglas/)