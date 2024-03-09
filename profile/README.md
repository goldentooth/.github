# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps playground without any important services or data.

This will be a valuable resource for me as I study for some Platform Engineering/SRE-related certifications. I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves useful to other engineers.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B 8GB; I've rolled my own clusters in the past and found the physical details of cable management, power distribution, ventilation, etc aggravating, so I figured it would be worth some cash to have someone else figure out those details for me.

## General Plan and Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I use Ansible for configuration management on the nodes, including:
  - [Raspberry Pi OS](https://www.raspberrypi.com/software/)
  - [HAProxy](https://www.haproxy.org)
  - [Kubernetes](https://kubernetes.io)
  - [Argo CD](https://argoproj.github.io/cd/)
- **[Incubator](https://github.com/goldentooth/incubator)**: App-of-Apps GitOps repository for Argo CD holding applications that I'm not yet ready to spin off into individualized GitOps repositories. Things that may appear here at one time or another:
  - Prometheus
  - Grafana
  - Alertmanager
  - Elasticsearch
  - Logstash
  - Loki
  - Kibana
  - Istio
  - MySQL
  - PostgreSQL
  - Redis
  - Httpbin
  - Nginx
  - RabbitMQ
  - Kafka
  - External-DNS
  - Cert-Manager
  - Open Policy Agent
  - Harbor (as a Proxy cache)
  - VictoriaMetrics
- **[Kubernetes, the _Excruciating_ Way](https://github.com/goldentooth/kubernetes-the-excruciating-way)**: A low-level, step-by-step, thoroughly-documented descent into Hell.
- **[Kubespray](https://github.com/goldentooth/kubespray)**: I initially deployed Kubernetes via Kubespray, and still crib notes from it from time to time :eyes:
- **[Bash](https://github.com/goldentooth/bash)**: I'll write some helper scripts in Bash, installable with `bpkg`, to ease some of the common operations. Since I'm studying for certifications, I'm going to continue to type long commands out in full, but I'll add some scripts for selecting kubeconfigs and stuff.
  - Edit the Ansible vault
  - Prepare the cluster (e.g. `raspi-config`, hostnames, disabling swap, etc)
  - Set up the cluster (and reset it)
  - Retrieve and install the Kubeconfig
  - Etc.
- A number of GitOps repositories for deploying specific applications/ecosystems within Kubernetes:
  - **[MetalLB](https://github.com/goldentooth/metallb)**: To achieve parity with cloud services for painless load balancer deployment
