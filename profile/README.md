# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps playground without any important services or data.

This will be a valuable resource for me as I study for some Platform Engineering/SRE-related certifications. I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves useful to other engineers.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B (8GB RAM, 128GB SD). The first node runs HAProxy, and the other nine form a Kubernetes cluster with three control plane nodes and six worker nodes.

## Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I use Ansible for configuration management on the nodes, including:
  - [Raspberry Pi OS](https://www.raspberrypi.com/software/)
  - [HAProxy](https://www.haproxy.org)
  - [Kubernetes](https://kubernetes.io)
  - [Argo CD](https://argoproj.github.io/cd/)
- **[Incubator](https://github.com/goldentooth/incubator)**: App-of-Apps GitOps repository for applications under development.
- **[Kubernetes, the _Excruciating_ Way](https://github.com/goldentooth/kubernetes-the-excruciating-way)**: Basically a development journal for my work on this cluster.
- **[Bash](https://github.com/goldentooth/bash)**: Helper scripts, written in Bash.
- A number of GitOps repositories for deploying specific applications/ecosystems within Kubernetes via Argo CD:
  - **[httpbin](https://github.com/goldentooth/httpbin)**: A Go port of `httpbin`, a cool little server for testing and debugging.
  - **[MetalLB](https://github.com/goldentooth/metallb)**: To achieve parity with cloud services for painless load balancer deployment.
  - **[Prometheus Node Exporter](https://github.com/goldentooth/prometheus-node-exporter)**: For gathering information about cluster nodes.
  - **[ExternalDNS](https://github.com/goldentooth/external-dns)**: To create DNS records for load balancer services.
- **[Gitops Template](https://github.com/goldentooth/gitops-template)**: A template repository for the ApplicationSet.
