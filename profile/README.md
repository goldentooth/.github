# GoldenTooth

GoldenTooth is my Pi Bramble (Cluster), which I'm building in order to have a fun-sized DevOps/MLOps playground without any important services or data.

I'm building this cluster not to host anything in particular, but to act as something as a Chaos Zoo, where I just deploy things and then try to destroy them to learn about their behavior. No service has, or will have, any purpose other than as a way of learning about itself or the other services.

## About the Cluster

My cluster is built around a PicoCluster 10H with ten Raspberry Pi 4B (8GB RAM, 128GB SD).

Currently, it has the following general structure:
- 1 load balancer/proxy node: Allyrion
  - HAProxy for high availability of the Kubernetes control plane nodes
  - Nginx as a general-purpose HTTP/S proxy
  - NFS server for shared data
  - Consul client (in progress)
- 3 "leader" nodes: Bettley, Cargyll, and Dalt
  - Kubernetes control plane
  - Slurm controller (Bettley) and fallback (Cargyll, Dayne)
  - Consul server (Bettley) and fallback (Cargyll, Dayne) (in progress)
- 6 "follower" nodes: Erenford, Fenn, Gardener, Harlton, Inchfield, and Jast
  - Kubernetes worker node
  - Slurm compute node
  - Consul client (in progress)

## Recent Things

- I set up a CloudFront distribution and an ACM certificate for goldentooth.net...
- I set up Nginx as a reverse proxy, forwarding incoming requests for `<service>.home-proxy.goldentooth.net` to `<service>.goldentooth.net`, and thence to either a cluster node Nginx instance serving a static status page or a Kubernetes service exposed via MetalLB and added to Route53 by ExternalDNS.

## The (Rough) Roadmap

- Set up Consul (in progress). Consul will be useful in a few different ways, but I also think that service discovery will provide interesting information for visualization (more later).
- Set up existing services to speak to Consul for service discovery. So we'll be able to e.g. see services announce themselves, see health checks, etc.
- Set up Envoy as a global ingress, using Consul for route discovery. The hope here is an extremely dynamic mapping from domain names to services within the intranet. Then I think I can do something like visualize requests and show how they're routed to different nodes at different times. Visualize e.g. different load balancer algorithms, visualize failover, etc.
- Set up Authelia as a more secure front door. I would like to set up an account system eventually and grant privileges. Like, I don't _want_ people to destroy my cluster, not substantial privileges, but to be able to poke around a bit. Presumably read-only. See graphs, visualizations, etc.
- Tear down existing Nginx proxy. Nginx served its purpose but I'm fairly comfortable with it and I can use it in more interesting ways within the cluster. A couple of server blocks isn't that interesting. I wanna get weird with Nginx.
- Work on per-node pages, e.g. `https://node-name.goldentooth.net` that will show individual node status, logs, etc. Not sure what to do here yet -- currently they're static HTML. Might dynamically update them on a cron job. I could write a script that just gathers a bunch of figures, dumps them into JSON, and the HTML loads the JSON via JS and uses that to populate the page. Simple, clean, very flexible.

## Repository Structure

- **[Cluster](https://github.com/goldentooth/cluster)**: I use Ansible for configuration management on the nodes (and some Terraform for AWS resources), including:
  - [Raspberry Pi OS](https://www.raspberrypi.com/software/)
  - [HAProxy](https://www.haproxy.org)
  - [Kubernetes](https://kubernetes.io)
  - [Argo CD](https://argoproj.github.io/cd/)
  - [Slurm](http://slurm.schedmd.com)
- **[Blog](https://github.com/goldentooth/blog)**: Blog, formerly named **Kubernetes, the _Excruciating_ Way** (Mdbook, Terraform, GitHub Actions). Read it at https://blog.goldentooth.net/ ! 
- **[Bash](https://github.com/goldentooth/bash)**: Helper scripts, written in Bash.
- A number of GitOps repositories for deploying specific applications/ecosystems within Kubernetes via Argo CD:
  - **[httpbin](https://github.com/goldentooth/httpbin)**: A Go port of `httpbin`, a cool little server for testing and debugging.
  - **[MetalLB](https://github.com/goldentooth/metallb)**: To achieve parity with cloud services for painless load balancer deployment.
  - **[Prometheus Node Exporter](https://github.com/goldentooth/prometheus-node-exporter)**: For gathering information about cluster nodes.
  - **[ExternalDNS](https://github.com/goldentooth/external-dns)**: To create DNS records for load balancer services.

## Permissions
I'm releasing everything I create here under an [Unlicense](https://choosealicense.com/licenses/unlicense/) in the hopes that it proves interesting or useful to other engineers.
