# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps playground without any important services or data.

This will be a valuable resource for me as I study for some Platform Engineering/SRE-related certifications. I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves useful to other engineers.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B 8GB; I've rolled my own clusters in the past and found the physical details of cable management, power distribution, ventilation, etc aggravating, so I figured it would be worth some cash to have someone else figure out those details for me.

## Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I use Ansible for configuration management on the nodes, including:
  - [Raspberry Pi OS](https://www.raspberrypi.com/software/)
  - [HAProxy](https://www.haproxy.org)
  - [Kubernetes](https://kubernetes.io)
  - [Argo CD](https://argoproj.github.io/cd/)
- **[Incubator](https://github.com/goldentooth/incubator)**: App-of-Apps GitOps repository for applications under development.
  <!--
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
  -->
- **[Kubernetes, the _Excruciating_ Way](https://github.com/goldentooth/kubernetes-the-excruciating-way)**: Basically a development journal for my work on this cluster.
- **[Bash](https://github.com/goldentooth/bash)**: Helper scripts, written in Bash.
- A number of GitOps repositories for deploying specific applications/ecosystems within Kubernetes:
  - **[MetalLB](https://github.com/goldentooth/metallb)**: To achieve parity with cloud services for painless load balancer deployment
