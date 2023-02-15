## Creating a local Kubernetes install with or without Tanzu

## Introduction
Throughout the cheatsheet here we will try to use Linux as much as possible. In this guide I use Ubuntu 22.04.1 LTS on a 64-bit Surface Pro 4 Windows machine. For many of things I use Homebrew just for the case of simplying things. If needed the guide will describe other approaches for installing things.

> Make sure to [download Homebrew](https://brew.sh/) using this command in terminal:  
> ```$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"```

Here we will be installing Kubectl that will enable us to run commands against Kubernetes clusters and additional tools needed in order to run clusters locally.

### Install Kubectl
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Kubectl | `brew install kubectl` |  |  |
| Verify Kubectl install | `kubectl version --client` |  | The output should show something like this:<br />`Client Version: version.Info{Major:"1", Minor:"26", GitVersion:"v1.26.1", GitCommit:"8f94681cd294aa8cfd3407b8191f6c70214973a4", GitTreeState:"clean", BuildDate:"2023-01-18T15:51:24Z", GoVersion:"go1.19.5", Compiler:"gc", Platform:"linux/amd64"}Kustomize Version: v4.5.7`|
|Verify Kubectl config|`kubectl cluster-info`||This should show XX|

### Install Minikube
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Minikube | `brew install minikube` |  | Pay attention to.. |
| Verify Minikube install | `minikube version` | | The output should show something like this:<br />`minikube version: v1.29.0 commit: ddac20b4b34a9c8c857fc602203b6ba2679794d3`|

### Install Kind (alternative)
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Docker | `kubectl get pods` | `tanzu list..`| Kind requires that you have Docker installed and configured |
| Install Kind | `kubectl apply -f xyz.yaml`. | Show file differences that **haven't been** staged |
