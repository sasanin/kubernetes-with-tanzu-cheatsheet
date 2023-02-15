## Creating a local Kubernetes install with or without Tanzu

## Introduction
Throughout the cheatsheet here we will try to use Linux as much as possible. In this guide I use Ubuntu 22.04.1 LTS on a 64-bit Surface Pro 4 Windows machine. For many of things I use Homebrew just for the case of simplying things. If needed the guide will describe other approaches for installing things.

> Make sure to [download Homebrew](https://brew.sh/) using this command in terminal: $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Here we will be installing Kubectl the XX and additional tools needed in order to be able to host and create clusters and containers.

### Installing Kubectl
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Homebrew | `kubectl get pods` | `tanzu list..`| Pay attention to.. |
| Install Kubectl | `kubectl apply -f xyz.yaml`. | Show file differences that **haven't been** staged |

### Y
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Do something X | `kubectl get pods` | `tanzu list..`| Pay attention to.. |
| Do something Y | `kubectl apply -f xyz.yaml`. | Show file differences that **haven't been** staged |

