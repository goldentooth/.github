# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the `.github` repository for the Goldentooth organization, which contains profile information and documentation for a 12-node Raspberry Pi cluster. The repository primarily contains:

- Profile README.md with comprehensive cluster documentation
- Cluster architecture diagrams and images
- License information (Unlicense)

## Architecture & Purpose

Goldentooth is a physical infrastructure playground - a 12-node Raspberry Pi 4B cluster (48 cores, 96GB RAM total) designed for experimenting with distributed systems, orchestration layers, and failure modes. The cluster serves as a "Chaos Zoo" for learning system behavior under stress.

### Node Layout
- **Edge Node**: `Allyrion` - Load balancer, NFS, HAProxy, Envoy, Consul client
- **Leader Nodes**: `Bettley`, `Cargyll`, `Dalt` - Kubernetes control plane, Vault, Nomad/Slurm servers, Consul servers  
- **Worker Nodes**: `Erenford`, `Fenn`, `Gardener`, `Harlton`, `Inchfield`, `Jast`, `Karstark`, `Lipps` - Kubernetes workers, Nomad/Slurm clients, Consul clients

### Core Services Stack
- **Orchestration**: Kubernetes, Nomad
- **Scheduling**: Slurm, Nomad
- **GitOps**: Argo CD
- **Secrets**: Vault, SealedSecrets, ExternalSecrets
- **Observability**: Prometheus, Node Exporter, Grafana
- **Service Discovery**: Consul, mDNS
- **Load Balancing**: MetalLB (L2), HAProxy, Envoy
- **Storage**: NFS
- **DNS**: ExternalDNS
- **Logging**: Vector, Loki

## Related Repositories

The Goldentooth ecosystem consists of multiple specialized repositories:
- Infrastructure-as-Code: `terraform`, `ansible`
- Documentation: `clog` (changelog)
- Monitoring: `prometheus-node-exporter`, `grafana-dashboards`
- Security: `external-secrets`, `sealed-secrets`
- Networking: `external-dns`, `metallb`
- Applications: `httpbin`, `flood`, `flags`, `pulse`
- Development: `agent`, `bash`, `gitops-template`

## Development Notes

This is primarily a documentation repository with no build processes, tests, or complex development workflows. Changes typically involve updating the profile README.md with cluster status, architecture changes, or new service additions.

## Organizational Context

The Goldentooth organization is part of the broader "Nug Doug Cinematic Universe" - a collection of GitHub organizations and repositories under `@ndouglas` that follow similar organizational patterns. Related organizations include `bitterbridge` and `hellholt`, which may share architectural concepts, naming conventions, or infrastructure approaches.

The repository follows the Unlicense terms - all content is in the public domain.