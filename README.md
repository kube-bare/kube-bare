# kube-bare
Deploy a Production Ready Kubernetes Cluster on Bere-Metal or On-Premise

# support os

+ centos 8
+ debian 10
+ ubuntu lts 18.04

# support kubernetes

+ kube-bare v1.15.x for  kubernetes v1.15
+ kube-bare v1.16.x for  kubernetes v1.16 

# support cni

+ cilium
+ calico
+ flannel
+ kube-router
+ kube-ovn

# support special networks

+ china 
+ offline

# install packages 

+ docker-ce
+ kubeadm
+ autoload kernel mod
+ sysctl conf
+ etcd HA cluster
+ haproxy for HA apiserver
+ keepalived for HA apiserver
+ kubernetes masters
+ kubernetes nodes

# support addons

+ cephfs-provisioner v2.1.0-k8s1.11
+ rbd-provisioner v2.1.1-k8s1.11
+ cert-manager v0.5.2
+ ingress-nginx v0.21.0
+ istio
+ sofa-mesh
+ prometheus
+ argo-cd

## quick start

```bash
git clone https://github.com/taomaree/kube-bare.git
cd kube-bare
sudo pip3 install -r requirements.txt

```

## OPTION: deploy kubernetes on local server as single node cluster for dev/testing 

```bash
ansible-playbook mini.yml

```

## OPTION: deploy kubernetes on remote server as single node cluster for dev/testing 

```bash
ansible-playbook mini.yml -e "hosts=1.2.3.4"
```

## OPTION: install a Production Ready HA cluster

```bash
cp inventory/inventory.example inventory/inventory.prod

## add hosts for etcd,lb,masters,nodes 
vi inventory.prod   

ansible-playbook -i inventory/inventory.prod ha.yml
```
