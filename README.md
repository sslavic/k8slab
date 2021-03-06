# Kubernetes (k8s) Laboratory
In this project I prepared one automated version for the Kubernetes "getting started" suggested by the official documentation [here](https://kubernetes.io/docs/getting-started-guides/centos/centos_manual_config/)

There is a training called **Scalable Microservices with Kubernetes** provided by Udacity [here](https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615), this training is hosted by [Carter Morgan](https://github.com/askcarter) and [Kelsey Hightower](https://github.com/kelseyhightower), they give a very good and detailed explanation about microservices and the technologies used to prepare your applications to the new era. You can get from zero to hero with this course.

I just prepared this project because in the training from Udacity they show the examples using [Google Cloud](https://cloud.google.com/), which is a very good solution but for some companies that are still using on premise environments, like companies from the finance market for example, would be good to have the same agility from startups inside financial companies, that's why I did this lab.

## Prerequisites

### Installed on your desktop
* Fedora 24 (My host Operating System)
* Vagrant 1.9.4
* Virtualbox 5.1.20

### Will be installed by the automation
* CentOS 7
* Chef
* mDNS
* Docker
* Kubernetes
* Etcd
* Flannel

## Features

* Create and boot VirtualBox instances
* Provision the hosts with all necessary tools
* Spin up 5 hosts (1 master, 4 minions)
* You can SSH into the instances using ```vagrant ssh <host>```
* Automatic SSH key generation to access your hosts through vagrant

## Usage

After install vagrant and virtualbox on your desktop, you can clone this repo and open the Vagrantfile to replace the parameter "bridge" on line ```config.vm.network 'public_network', bridge: 'wlp8s0'```. Instead of "wlp8s0" you can put whatever name you have for your NIC connected to your network. After that, follow the commands bellow:

```console
$ vagrant up
$ vagrant ssh kube1
[vagrant@kube1 ~]$ sudo kubectl get nodes
NAME          STATUS    AGE
kube2.local   Ready     1h
kube3.local   Ready     56m
kube4.local   Ready     53m
kube5.local   Ready     50m
```
From here you are good to go and follow the training from Udacity, keep in mind that this is not for production, this project can be used for lab and training purpose only.
