# kube-bare
Deploy a Production Ready Kubernetes Cluster on Bere-Metal or On-Premise

## ROADMAP
### support os

+ centos 8  (TBD)
+ debian 10
+ ubuntu lts 18.04

### support kubernetes

+ kube-bare v1.15.x for  kubernetes v1.15
+ kube-bare v1.16.x for  kubernetes v1.16 

### support cni

+ cilium
+ calico
+ flannel
+ kube-router
+ kube-ovn

### support special networks

+ china 
+ offline (TBD)

### install packages 

+ docker-ce
+ kubeadm
+ autoload kernel mod
+ sysctl conf
+ etcd HA cluster
+ haproxy for HA apiserver
+ keepalived for HA apiserver
+ kubernetes masters
+ kubernetes nodes



## quick start

```bash
git clone https://github.com/taomaree/kube-bare.git
cd kube-bare
sudo pip3 install -r requirements.txt

```

## OPTION: deploy kubernetes on local server as single node

```bash
ansible-playbook deploy-single-node.yml

```

## OPTION: deploy kubernetes on remote server as single node

```bash
ansible-playbook deploy-single-node.yml -e "hosts=1.2.3.4"
```

## OPTION: depoly kubernetes for a Production Ready HA cluster

```bash
cp inventory/inventory.example inventory/inventory.prod

## add hosts for etcd,lb,masters,nodes 
vi inventory.prod   

ansible-playbook -i inventory/inventory.prod deploy-ha-cluster.yml

```
