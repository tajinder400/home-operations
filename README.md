<div align="center">

<img src="https://raw.githubusercontent.com/onedr0p/home-ops/main/docs/src/assets/logo.png" align="center" width="144px" height="144px"/>

### My Home Operations Repository :octocat:

_... managed with Flux, Renovate, and GitHub Actions_ 🤖

</div>

<div align="center">

[![Kubernetes](https://img.shields.io/badge/dynamic/yaml?url=https%3A%2F%2Fraw.githubusercontent.com%2Fsamip5%2Fk8s-cluster%2Fmain%2Fk8s%2Fbase%2Fsystem-upgrade%2Fsystem-upgrade-controller%2Fplans%2Fserver-plan.yaml&query=spec.version&style=for-the-badge&logo=kubernetes&logoColor=white&label=%20)](https://kubernetes.io/)&nbsp;&nbsp;
[![Renovate](https://img.shields.io/github/actions/workflow/status/samip5/k8s-cluster/schedule-renovate.yaml?branch=main&label=&logo=renovatebot&style=for-the-badge&color=blue)](https://github.com/samip5/k8s-cluster/actions/workflows/schedule-renovate.yaml)

</div>


### :wrench:&nbsp; Tools

| Tool                                                               | Purpose                                                             |
|--------------------------------------------------------------------|---------------------------------------------------------------------|
| [ansible](https://www.ansible.com)                                 | Preparing Talos Linux and bootstrapping the install                 |
| [flux](https://toolkit.fluxcd.io/)                                 | Operator that manages your k8s cluster based on your Git repository |
| [go-task](https://github.com/go-task/task)                         | A task runner / simpler Make alternative written in Go              |
| [sops](https://github.com/mozilla/sops)                            | Encrypts k8s secrets with GnuPG                                     |


## 💻 Nodes
| Node                          | Hostname        | RAM  | Storage                                            | Function         | Operating System |
|-------------------------------|-----------------|------|----------------------------------------------------|------------------|------------------|
| KVM                           | Pneuma          | 16GB | 512GB SSD                                          | Control Plane    | Talos Linux      |
| Beelink EQ12                  | Ontos           | 16GB | 512GB SSD                                          | Control Plane    | Talos Linux      |
| Lenovo ThinkCentre M9720Q     | Logos           | 16GB | 512GB SSD                                          | Control Plane    | Talos Linux      |


## Storage
| Node         | Hostname | RAM  | Storage                                                                | Function             | Operating System   |
|--------------|----------|------|------------------------------------------------------------------------|------------|---------|--------------------|
| DIY          | NAS      | 16GB | ZFS Array: 3 x 20TB CMR HDD's. RAIDZ1, 2TB SSD, 512GB NVME             | NFS Server, KVM Host | Ubuntu Server 24,04|

## Network

| Vendor   | Model                        | Function                                                          |
|----------|------------------------------|-------------------------------------------------------------------|
| Mikrotik | RB5009                       | Edge Router connected to 1Gb Uplink                               |
| Mikrotik | CRS309-1G-8S+IN              | Edge Switch, 10Gb SFP+ Ports                                      |
| Ubiquiti | Unifi U7 Pro                 | Bedroom switching (gaming iTX system, Apple TV 4K and Steam Deck) |
| Raspberry| Pi4                          | PiHole & Unbound dedicated device. Will probably decomission      |

All nodes are connected to a dual-stack network, with private IPv4 and public IPv6.
Kubernetes nodes are on their own VLAN which has access to the NAS.

## ☁️ Cloud Dependencies

While most of my infrastructure and workloads are self-hosted I do rely upon the cloud for certain key parts of my setup. This saves me from having to worry about two things. (1) Dealing with chicken/egg scenarios and (2) services I critically need whether my cluster is online or not.

| Service                                                               | Use                                                                | Cost           |
|-----------------------------------------------------------------------|--------------------------------------------------------------------|----------------|
| [Cloudflare](https://www.cloudflare.com/)                             | Domain(s) and S3                                                   | Free           |
| [GitHub](https://github.com/)                                         | Hosting this repository and continuous integration/deployments     | Free           |
|                                                                       |                                                                    | Total: ~0£/mo  |

## Stargazers

[![Star History Chart](https://api.star-history.com/svg?repos=tajinder400/home-operations&type=Date)](https://star-history.com/#tajinder400/home-operations&Date)
