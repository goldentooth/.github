# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps/MLOps playground without any important services or data.

I'm building this cluster not to host anything in particular, but to act as something as a Chaos Zoo, where I just deploy things and then try to destroy them to learn about their behavior. No service has, or will have, any purpose other than as a way of learning about the other services.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B (8GB RAM, 128GB SD).

Currently, it has the following general structure:
- 1 load balancer/proxy node: Allyrion
  - HAProxy for high availability of the Kubernetes control plane nodes
  - Nginx as a general-purpose HTTP/S proxy
  - NFS server for shared data
- 3 "leader" nodes: Bettley, Cargyll, and Dalt
  - Kubernetes control plane
  - Slurm controller (Bettley) and fallback (Cargyll, Dayne)
  - Consul leader (Bettley) and fallback (Cargyll, Dayne)
- 6 "follower" nodes: Erenford, Fenn, Gardener, Harlton, Inchfield, and Jast
  - Kubernetes worker node
  - Slurm compute node

## Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I use Ansible for configuration management on the nodes (and some Terraform for AWS resources), including:
  - [Raspberry Pi OS](https://www.raspberrypi.com/software/)
  - [HAProxy](https://www.haproxy.org)
  - [Kubernetes](https://kubernetes.io)
  - [Argo CD](https://argoproj.github.io/cd/)
  - [Slurm](http://slurm.schedmd.com)
- **[Blog](https://github.com/goldentooth/blog)**: Blog, formerly named **Kubernetes, the _Excruciating_ Way** (Mdbook, Terraform, GitHub Actions). Read it at https://goldentooth.net/ !
- **[Bash](https://github.com/goldentooth/bash)**: Helper scripts, written in Bash.
- A number of GitOps repositories for deploying specific applications/ecosystems within Kubernetes via Argo CD:
  - **[httpbin](https://github.com/goldentooth/httpbin)**: A Go port of `httpbin`, a cool little server for testing and debugging.
  - **[MetalLB](https://github.com/goldentooth/metallb)**: To achieve parity with cloud services for painless load balancer deployment.
  - **[Prometheus Node Exporter](https://github.com/goldentooth/prometheus-node-exporter)**: For gathering information about cluster nodes.
  - **[ExternalDNS](https://github.com/goldentooth/external-dns)**: To create DNS records for load balancer services.

## Permissions
I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves interesting or useful to other engineers.
