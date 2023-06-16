## TAP version 1.5.1 on Google Kubernetes Engine (gke)

## Introduction
Before installing TAP on gke make sure that you have the following:
* A Tanzu Network account with noted username and password.
  - If not, please go to https://network.tanzu.vmware.com and create one. Save the username and password as we will 
* Access to https://registry.tanzu.vmware.com using the same credentials as above.
* A Google Cloud Account that gives you access to the gke console https://console.cloud.google.com/.

### Step 1 - 
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Kubectl | `brew install kubectl` |  |  |
| Verify Kubectl install | `kubectl version --client` |  | The output should show something like this:<br />`Client Version: version.Info{Major:"1", Minor:"26", GitVersion:"v1.26.1", GitCommit:"8f94681cd294aa8cfd3407b8191f6c70214973a4", GitTreeState:"clean", BuildDate:"2023-01-18T15:51:24Z", GoVersion:"go1.19.5", Compiler:"gc", Platform:"linux/amd64"}Kustomize Version: v4.5.7`|
|Verify Kubectl config|`kubectl cluster-info`||This should show XX|

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
