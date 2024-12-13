<div align="center">

<img src="https://raw.githubusercontent.com/onedr0p/home-ops/main/docs/src/assets/logo.png" align="center" width="144px" height="144px"/>

### My Home Operations Repository :octocat:

_... managed with Flux, Renovate, and GitHub Actions_ 🤖

</div>

<div align="center">

[![Discord](https://img.shields.io/discord/673534664354430999?style=for-the-badge&label&logo=discord&logoColor=white&color=blue)](https://discord.gg/home-operations)&nbsp;&nbsp;
[![Talos](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Ftalos_version&style=for-the-badge&logo=talos&logoColor=white&color=blue&label=%20)](https://talos.dev)&nbsp;&nbsp;
[![Kubernetes](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fkubernetes_version&style=for-the-badge&logo=kubernetes&logoColor=white&color=blue&label=%20)](https://kubernetes.io)&nbsp;&nbsp;
[![Renovate](https://img.shields.io/github/actions/workflow/status/onedr0p/home-ops/renovate.yaml?branch=main&label=&logo=renovatebot&style=for-the-badge&color=blue)](https://github.com/onedr0p/home-ops/actions/workflows/renovate.yaml)

</div>

<div align="center">

[![Home-Internet](https://img.shields.io/uptimerobot/status/m793494864-dfc695db066960233ac70f45?color=brightgreeen&label=Home%20Internet&style=for-the-badge&logo=ubiquiti&logoColor=white)](https://status.wabbit.life)&nbsp;&nbsp;
[![Status-Page](https://img.shields.io/uptimerobot/status/m793599155-ba1b18e51c9f8653acd0f5c1?color=brightgreeen&label=Status%20Page&style=for-the-badge&logo=statuspage&logoColor=white)](https://status.wabbit.life)&nbsp;&nbsp;
[![Alertmanager](https://img.shields.io/uptimerobot/status/m793494864-dfc695db066960233ac70f45?color=brightgreeen&label=Alertmanager&style=for-the-badge&logo=prometheus&logoColor=white)](https://status.wabbit.life)

</div>

<div align="center">

[![Age-Days](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_age_days&style=flat-square&label=Age)](https://github.com/kashalls/kromgo)&nbsp;&nbsp;
[![Uptime-Days](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_uptime_days&style=flat-square&label=Uptime)](https://github.com/kashalls/kromgo)&nbsp;&nbsp;
[![Node-Count](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_node_count&style=flat-square&label=Nodes)](https://github.com/kashalls/kromgo)&nbsp;&nbsp;
[![Pod-Count](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_pod_count&style=flat-square&label=Pods)](https://github.com/kashalls/kromgo)&nbsp;&nbsp;
[![CPU-Usage](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_cpu_usage&style=flat-square&label=CPU)](https://github.com/kashalls/kromgo)&nbsp;&nbsp;
[![Memory-Usage](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_memory_usage&style=flat-square&label=Memory)](https://github.com/kashalls/kromgo)&nbsp;&nbsp;
[![Power-Usage](https://img.shields.io/endpoint?url=https%3A%2F%2Fkromgo.wabbit.life%2Fcluster_power_usage&style=flat-square&label=Power)](https://github.com/kashalls/kromgo)

</div>

### :wrench:&nbsp; Tools

| Tool                                                               | Purpose                                                             |
|--------------------------------------------------------------------|---------------------------------------------------------------------|
| [ansible](https://www.ansible.com)                                 | Preparing Talos Linux and bootstrapping the install                 |
| [flux](https://toolkit.fluxcd.io/)                                 | Operator that manages your k8s cluster based on your Git repository |
| [go-task](https://github.com/go-task/task)                         | A task runner / simpler Make alternative written in Go              |
| [sops](https://github.com/mozilla/sops)                            | Encrypts k8s secrets with GnuPG                                     |


## 💻 Nodes
| Node                          | Hostname        | RAM  | Storage               | Networking                  | Function         | Operating System |
|-------------------------------|-----------------|------|-----------------------|-----------------------------|------------------|------------------|
| Lenovo ThinkCentre M720Q      | Logos           | 64GB | 512GB SSD             | 10GbE X710-DA2              | Control Plane    | Talos Linux      |
| Lenovo ThinkCentre M720Q      | Pneuma          | 64GB | 512GB SSD             | 10GbE x710-DA2              | Control Plane    | Talos Linux      |
| Beelink EQ12                  | Ontos           | 16GB | 512GB SSD             | 2x 2.5Gb 802.3ad Bond       | Control Plane    | Talos Linux      |


## Storage
| Node                          | Hostname        | RAM  | Storage                                                 | Networking       |Function         | Operating System |
|-------------------------------|-----------------|------|---------------------------------------------------------|------------------|-----------------|------------------|
| DIY                           | Aionios         | 32GB | 3 x 20TB CRM HDD ZFS Array, RAIDZ1, 2TB SSD, 512GB NVME |10GbE X710-DA2    |Storage NAS      | Ubuntu Server    |
|                               |                 |      |                                                         |                  |                 |                  |


## Network

| Vendor   | Model                        | Function                                                          |
|----------|------------------------------|-------------------------------------------------------------------|
| Mikrotik | RB5009                       | Edge Router connected to 1Gb Uplink                               |
| Mikrotik | CRS309-1G-8S+IN              | Edge Switch, 10Gb SFP+ Ports                                      |
| Ubiquiti | Unifi U7 Pro                 | Main access point for the house                                   |
| Raspberry| Pi4                          | PiHole & Unbound dedicated device / VPN into network              |

Kubernetes nodes are on their own VLAN which has access to the NAS.

## ☁️ Cloud Dependencies

While most of my infrastructure and workloads are self-hosted I do rely upon the cloud for certain key parts of my setup. This saves me from having to worry about two things. (1) Dealing with chicken/egg scenarios and (2) services I critically need whether my cluster is online or not.

| Service                                                               | Use                                                                | Cost           |
|-----------------------------------------------------------------------|--------------------------------------------------------------------|----------------|
| [Cloudflare](https://www.cloudflare.com/)                             | Domain(s)                                                          | Free           |
| [GitHub](https://github.com/)                                         | Hosting this repository and continuous integration/deployments     | Free           |
| [Oracle Vault](https://www.oracle.com/uk/cloud/)                      | External Secrets                                                   | Free           |
|                                                                       |                                                                    | Total: ~0£/mo  |

## Stargazers

[![Star History Chart](https://api.star-history.com/svg?repos=tajinder400/home-operations&type=Date)](https://star-history.com/#tajinder400/home-operations&Date)
