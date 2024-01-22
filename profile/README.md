# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps playground without any important services or data.

This will be a valuable resource for me as I study for some Platform Engineering/SRE-related certifications. I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves useful to other engineers.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B 8GB; I've rolled my own clusters in the past and found the physical details of cable management, power distribution, ventilation, etc aggravating, so I figured it would be worth some cash to have someone else figure out those details for me.

## General Plan and Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I'll use Ansible for configuration management on the nodes and setting up Kubernetes.
  - Basic OS configuration (users, groups, unattended upgrades, etc)
  - Kubernetes installation and cluster configuration
  - Kubernetes cluster resources (namespaces, etc)
- **[GitOps](https://github.com/goldentooth/gitops)**: App-of-Apps GitOps repository using ArgoCD. I would probably set it so that many or most of these apps are disabled at any given time, except when I'm doing targeted learning that involves them.
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
  - MetalLB
  - Cert-Manager
  - Open Policy Agent
  - Harbor (as a Proxy cache)
  - VictoriaMetrics
- **[Bash](https://github.com/goldentooth/bash)**: I'll write some helper scripts in Bash, installable with `bpkg`, to ease some of the common operations. Since I'm studying for certifications, I'm going to continue to type long commands out in full, but I'll add some scripts for selecting kubeconfigs and stuff.
  - Use the Kubeconfig
  - Execute some Ansible playbook
  - Edit the Ansible vault
- **[CloudOps](https://github.com/goldentooth/cloudops)**: AWS, LetsEncrypt, and other resources that are hosted in the greater cloud (as opposed to my fun-sized cloud):
  - AWS Route53 record(s) related to the cluster
  - AWS IAM resources
  - AWS SSM Parameter Store parameters
  - AWS CloudFront distribution?
  - ACME/LetsEncrypt certificates
