# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps playground without any important services or data.

This will be a valuable resource for me as I study for some Platform Engineering/SRE-related certifications. I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves useful to other engineers.

## About the Cluster

My cluster is five Raspberry Pi 4B 8GBs housed in a Pico 5H. I've rolled my own clusters in the past and found the physical details of cable management, power distribution, ventilation, etc aggravating, so I figured it would be worth some cash to have someone else figure out those details for me.

## General Plan and Repository Structure

- **[Ansible](https://github.com/goldentooth/ansible)**: I'll use Ansible for configuration management on the nodes and setting up Kubernetes.
  - Basic OS configuration (users, groups, unattended upgrades, etc)
  - Kubernetes installation and cluster configuration
  - Kubernetes cluster resources (namespaces, etc)
- **[ArgoCD](https://github.com/goldentooth/argocd)**: App-of-Apps GitOps repository. I would probably set it so that many or most of these apps are disabled at any given time, except when I'm doing targeted learning that involves them.
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
  - Cert-Manager
  - Open Policy Agent
  - Harbor (as a Proxy cache)
- **[Bash](https://github.com/goldentooth/bash)**: I'll write some helper scripts in Bash, installable with `bpkg`, to ease some of the common operations. Since I'm studying for certifications, I'm going to continue to type long commands out in full, but I'll add some scripts for selecting kubeconfigs and stuff.
  - Use the Kubeconfig
  - Execute some Ansible playbook
  - Edit the Ansible vault

