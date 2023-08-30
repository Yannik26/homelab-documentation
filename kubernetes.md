---
title: Kubernetes
nav_order: 1
layout: page
---
# Kubernetes Setup
For Kubernetes [K3S](https://k3s.io) will be used.
## Install OS
Debian is used, use the debian clout template via clout-init
## Install K3S
	curl -sfL https://get.k3s.io | sh - 

## Install Flux
Create new personal access token with all permissions unter repo set.
	export GITHUB_TOKEN=<your-token>
Bootstrap flux
	flux bootstrap github   --owner=Yannik26   --repository=k3s-flux   --path=clusters/production   --personal --read-write-key --components-extra=image-reflector-controller,image-automation-controller

## Mozilla SOPS
