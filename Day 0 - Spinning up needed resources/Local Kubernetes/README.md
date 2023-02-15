## Creating a local Kubernetes install with or without Tanzu

## Introduction
Throughout the cheatsheet here we will try to use Linux as much as possible. In this guide I use Ubuntu 22.04.1 LTS on a 64-bit Surface Pro 4 Windows machine. Here we will be installing Kubectl the XX and additional tools needed in order to be able to host and create clusters and containers.

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

