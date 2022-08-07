---
title: "Kubernetes Development #1: Local Kubernetes Installations"
categories:
  - kubernetes
tags:
  - kubernetes
  - devops
  - containerization
  - kubernetes development
  - minikube
toc: true
toc_label: "Table of Contents"
toc_icon: "fas fa-bars"
---

Cloud-native computing, microservice architecture, containerization, and Kubernetes have now solidly entered mainstream DevOps conversations and have a powerful position in our industry.   

Developers must now adapt to this fundamental change, and this is a true challenge because while these approaches sound great in principle when it comes down to implement the changes they introduce are non-trivial and extensive especially when compared to what developers are accustomed when implementing a standard web application.  

This blog post will begin a series of documents to address questions about how to develop on Kubernetes. My intent is to give the tools and the directions to enable you, by the end of this series, to set up a development environment focused more on code and less on infrastructure.  

As a developer, you want to rapidly iterate on your application source code locally while still mirroring a remote production environment as closely as possible. And if you are accustomed to traditional methods, cloud-native development presents new obstacles to achieve this. Fortunately, today we have access to modern tools and patterns that can greatly reduce the time to get started with a working development workspace and delivery pipeline.  

In the present blog post, we will talk about some tools used to set up a local Kubernetes environment to create a safe and agile application-deployment process and explore the differences and strengths of each one. All the tools presented here are [CNCF](https://landscape.cncf.io/) certified conformant Kubernetes installers. 

![kubernetes](https://i0.wp.com/www.cienciaedados.com/wp-content/uploads/2018/04/Kubernetes-Pods-Nodes-Containers-e-Clusters.png?fit=1200%2C621&ssl=1)

# Minikube

Minikube is a Kubernetes SIGs project and has been started over four years ago. It has the capability to spawn a single-node Kubernetes cluster on Linux, macOS, and Windows (cross-platform). Minikube is a good cross-platform tool because it provides a unified way of working with local Kubernetes (Docker Machine) and supports a bunch of virtualizations for the deployment: VMs, containers and bare-metal.  

From a user perspective, Minikube is a very beginner-friendly tool. You start the cluster using *minikube start*, wait a bit and your *kubectl* is ready to go.  Minikube runs the latest stable version of Kubernetes, with support for standard Kubernetes features, but if you want to specify a Kubernetes version, you can do it with the flag “*kubernetes-version*”. 

![minikube-start](https://minikube.sigs.k8s.io/images/screenshot.png)

To help you manage your local cluster, Minikube has integrated support for the Kubernetes Dashboard UI. Running a simple command as *minikube dashboard* you can access it via browser to: 

- deploy containerized applications to a Kubernetes cluster;
- troubleshoot your containerized application;
- manage the cluster resources;
- get an overview of applications running on your cluster;
- creating or modifying individual Kubernetes resources (such as Deployments, Jobs, DaemonSets, etc).

![minikube-start](https://raw.githubusercontent.com/kubernetes/dashboard/master/docs/images/dashboard-ui.png)

If you are not yet convinced about minikube you can take a look [here](https://minikube.sigs.k8s.io/docs/) to learn more about all the features Minikube offers, such as addons, file system mounts and more. 

# Kind

Kind is another Kubernetes SIGS project like Minikube but can run local Kubernetes clusters only by deploying in Docker containers. This project was primarily designed for testing Kubernetes itself, but may be also used for local development or CI.  

Creating a cluster is very similar to Minikube’s approach. Executing kind create cluster, playing the waiting game, and afterwards you are good to go. By using different names (name) kind allows you to create multiple instances in parallel.

![kind-create-cluster](https://d33wubrfki0l68.cloudfront.net/e0f6f1da25268d7a0f4ca71368f5b8ab6ae68102/fcc29/images/kind-create-cluster.png)

Kind supports: 

- multi-node (including HA) clusters 
- building Kubernetes release builds from source (support for make / bash / docker or bazel, in addition to pre-published builds) 
- Linux, macOS and Windows 

# K3s

K3s is a lightweight Kubernetes version developed by Rancher Labs. By removing dispensable features (legacy, alpha, non-default, in-tree plugins) and using lightweight components (e.g., sqlite3 instead of etcd3) they achieved a significant downsizing. This results in a single binary with a size less of 100 MB.  

Because of its size, security, and highly availability, K3s is a strong tool for edge and IoT use cases. K3s also supports ARM64 and ARMv7 which means it works great from something small as a Raspberry Pi to an AWS a1.4xlarge 42GiB server. On top of this, K3s is also a great tool use in development and CI processes.  

The application is split into the K3s server and the agent. The former acts as a manager while the latter handles the actual workload. This can lead to some clutter in your local filesystem if you run it on your workstation. To avoid this, you can put K3s in a container (e.g., by using (rancher/k3s)[https://hub.docker.com/r/rancher/k3s]) which also allows you to easily run several independent instances. 

![k3s](https://k3s.io/images/how-it-works-k3s.svg)

One feature that stands out is called auto-deployment. It allows you to deploy your Kubernetes manifests and Helm charts by putting them in a specific directory. K3s watches for changes and takes care of applying them with no further interaction. This is especially useful for CI pipelines and IoT devices (both target use cases of K3s). Just create/update your configuration and K3s keeps your deployments up to date. 

# Summary

All these three tools are doing the same job while using different approaches and focusing on different use cases. I hope by now you have a better understanding about every one of them and which is the best candidate for solving your upcoming issues. **Personally, I like to stick with Minikube** because it supports Docker-based deployment and offers and larger set of functionalities when compared with Kind and also; I don’t need to use a light-weight solution as K3s is. 

In the next blog post of this series, we will explore some tools to **automate development workflows on Kubernetes** to significantly reduce the deployment and testing phases and provide a quick feedback loop which is always crucial for developer productivity. Stay tuned! 

# Resource links

- https://landscape.cncf.io/ 
- https://minikube.sigs.k8s.io/docs/ 
- https://github.com/kubernetes/minikube 
- https://github.com/kubernetes/dashboard 
- https://github.com/docker/machine 
- https://kind.sigs.k8s.io/ 
- https://github.com/kubernetes-sigs/kind 
- https://k3s.io/ 
- https://github.com/k3s-io/k3s 
 