# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps/MLOps playground without any important services or data.

This will be a valuable resource for me as I study for some Platform Engineering/SRE-related certifications, MLOps/HPC, etc. I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves useful to other engineers.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B (8GB RAM, 128GB SD).
  - **Allyrion**: HAProxy, NFS server.
  - **Bettley**: Kubernetes control plane, Slurm controller.
  - **Cargyll**: Kubernetes control plane, Slurm backup controller.
  - **Dalt**: Kubernetes control plane, Slurm backup controller.
  - **Erenford**: Kubernetes worker, Slurm compute.
  - **Fenn**: Kubernetes worker, Slurm compute.
  - **Gardener**: Kubernetes worker, Slurm compute.
  - **Harlton**: Kubernetes worker, Slurm compute.
  - **Inchfield**: Kubernetes worker, Slurm compute.
  - **Jast**: Kubernetes worker, Slurm compute.

## Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I use Ansible for configuration management on the nodes (and some Terraform for AWS resources), including:
  - [Raspberry Pi OS](https://www.raspberrypi.com/software/)
  - [HAProxy](https://www.haproxy.org)
  - [Kubernetes](https://kubernetes.io)
  - [Argo CD](https://argoproj.github.io/cd/)
  - [Slurm](http://slurm.schedmd.com)
- **[Kubernetes, the _Excruciating_ Way](https://github.com/goldentooth/kubernetes-the-excruciating-way)**: Basically a development journal for my work on this cluster.
- **[Bash](https://github.com/goldentooth/bash)**: Helper scripts, written in Bash.
- A number of GitOps repositories for deploying specific applications/ecosystems within Kubernetes via Argo CD:
  - **[httpbin](https://github.com/goldentooth/httpbin)**: A Go port of `httpbin`, a cool little server for testing and debugging.
  - **[MetalLB](https://github.com/goldentooth/metallb)**: To achieve parity with cloud services for painless load balancer deployment.
  - **[Prometheus Node Exporter](https://github.com/goldentooth/prometheus-node-exporter)**: For gathering information about cluster nodes.
  - **[ExternalDNS](https://github.com/goldentooth/external-dns)**: To create DNS records for load balancer services.
