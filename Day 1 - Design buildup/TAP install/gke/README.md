## TAP version 1.5.1 on Google Kubernetes Engine (gke)

## Introduction
This installation guide will let you install a full TAP profile on a gce/gke (?) cluster using a Mac.

Before installing TAP on gke make sure that you have the following:
* Tanzu and Kubectl CLIs installed. If not, go to XX.
* A Tanzu Network account with noted username and password.
  - If not, please go to https://network.tanzu.vmware.com and create one. Save the username and password as we will 
* Access to https://registry.tanzu.vmware.com using the same credentials as above.
* A Google Cloud Account that gives you access to the gke console https://console.cloud.google.com/.

### Step 1 - 
| What you are trying to achieve | On local Mac | In Google Cloud | Notes |
| --- | --- | --- | --- |
| Install Google Cloud CLI | Confirm that you have a supported version (3.5 to 3.9) of Python 3 by running `python3 -V` or `python -V`. If you do not have Python installed or the right version then fix it [here](https://www.python.org/downloads/). Download the Google Cloud CLI for macOS 64-bit [x86_64](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-x86_64.tar.gz), [ARM64, Apple M1 silicon](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-arm.tar.gz), or [x86](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-x86.tar.gz) |  |  |
| Update Tanzu CLI | `kubectl version --client` |  | dd |
| Update Kubectl CLI |`kubectl cluster-info`||This should show XX|

### Step 2 - 
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Minikube | `brew install minikube` |  | Pay attention to.. |
| Verify Minikube install | `minikube version` | | The output should show something like this:<br />`minikube version: v1.29.0 commit: ddac20b4b34a9c8c857fc602203b6ba2679794d3`|

### Step 3 - 
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Docker | `kubectl get pods` | `tanzu list..`| Kind requires that you have Docker installed and configured |
| Install Kind | `kubectl apply -f xyz.yaml`. | Show file differences that **haven't been** staged |
