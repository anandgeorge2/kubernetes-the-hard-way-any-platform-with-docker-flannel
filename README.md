# Kubernetes The Hard Way on any cloud with docker and flannel as CNI

This tutorial removes the dependancy of google cloud and related commands from the original hardway setup from Kelsey.
So steps in this repo will work on AWS, Azure, GCP, bare metal, ESX, VirtualBox, Workstation and more. This assumes both the
control plane and worker nodes are just Linux machines which are route-able to each other and connected to the internet. 

This tutorial walks you through setting up Kubernetes the hard way. This guide is not for people looking for a fully automated command to bring up a Kubernetes cluster. If that's you then check out [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine), or the [Getting Started Guides](https://kubernetes.io/docs/setup).

Kubernetes The Hard Way is optimized for learning, which means taking the long route to ensure you understand each task required to bootstrap a Kubernetes cluster.

> The results of this tutorial should not be viewed as production ready, and may receive limited support from the community, but don't let that stop you from learning!

## Copyright

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.


## Target Audience

The target audience for this tutorial is someone planning to support a production Kubernetes cluster and wants to understand how everything fits together.

## Cluster Details

Kubernetes The Hard Way guides you through bootstrapping a highly available Kubernetes cluster with end-to-end encryption between components and RBAC authentication.

* [kubernetes](https://github.com/kubernetes/kubernetes) 1.15.3
* [docker](https://github.com/docker/docker-ce) 19.03.4
* [flannel](https://github.com/coreos/flannel)v0.11.0
* [coredns](https://github.com/coredns/coredns) v1.6.3
* [cni](https://github.com/containernetworking/cni) v0.7.1
* [etcd](https://github.com/coreos/etcd) v3.4.0

## Labs

This tutorial assumes you have access to 6 computers which can run Ubuntu ( 18.04.3 is used for this particular setup - version should not matter much). The computers can be VMs/bare-metal/or even mixed, can be on-prem or cloud. Either way, these machines should be routable without any NAT-ing requirements. Best way to check is to ping the IPs from both directions provided ICMP is not disabled. Or better use something like Netcat. Also, it is assumed that there is no firewall between these machines. Steps in this repo are tested for both Ubuntu and RHEL/CentOS, on ESX, Baremetal, Vmware workstation and VirtualBox. Also, the steps are expected to work on any cloud platform without any modification.

* [Prerequisites](docs/01-prerequisites.md)
* [Installing the Client Tools](docs/02-client-tools.md)
* [Provisioning Compute Resources](docs/03-compute-resources.md)
* [Provisioning the CA and Generating TLS Certificates](docs/04-certificate-authority.md)
* [Generating Kubernetes Configuration Files for Authentication](docs/05-kubernetes-configuration-files.md)
* [Generating the Data Encryption Config and Key](docs/06-data-encryption-keys.md)
* [Bootstrapping the etcd Cluster](docs/07-bootstrapping-etcd.md)
* [Bootstrapping the Kubernetes Control Plane](docs/08-bootstrapping-kubernetes-controllers.md)
* [Bootstrapping the Kubernetes Worker Nodes](docs/09-bootstrapping-kubernetes-workers.md)
* [Configuring kubectl for Remote Access](docs/10-configuring-kubectl.md)
* [Provisioning Pod Network Routes](docs/11-pod-network-routes.md)
* [Deploying the DNS Cluster Add-on](docs/12-dns-addon.md)
* [Smoke Test](docs/13-smoke-test.md)
* [Cleaning Up](docs/14-cleanup.md)
