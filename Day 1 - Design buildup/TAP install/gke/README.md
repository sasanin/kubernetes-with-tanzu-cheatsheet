## TAP version 1.5.1 on Google Kubernetes Engine (GKE)

## Introduction
This installation guide will let you install a full TAP profile on a GKE cluster using a Mac. Please take a note of the [TAP prerequisities for GKE](https://docs.vmware.com/en/VMware-Tanzu-Application-Platform/1.5/tap/prerequisites.html#:~:text=Google%20Kubernetes%20Engine).

Before installing TAP on GKE make sure that you have the following:
* Tanzu and Kubectl CLIs installed. If not, go to **XX**.
* A Tanzu Network account with noted username and password.
  - If not, please go to https://network.tanzu.vmware.com and create one. Save the username and password as we will **XX**
* Access to https://registry.tanzu.vmware.com using the same credentials as above.
* A Google Cloud Account that gives you access to the GKE console https://console.cloud.google.com/.

### Step 1 - Obtaining and refreshing CLIs
| What you are trying to achieve | On local Mac | In Google Cloud | Notes |
| --- | --- | --- | --- |
| Install Google Cloud CLI - **Download tar** | Confirm that you have a supported version (3.5 to 3.9) of Python 3 by running `python3 -V` or `python -V`.<br />If you do not have Python installed or the right version then fix it [here](https://www.python.org/downloads/).<br />Download the Google Cloud CLI for macOS 64-bit [x86_64](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-x86_64.tar.gz), [ARM64, Apple M1 silicon](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-arm.tar.gz), or [x86](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-x86.tar.gz). |  |  |
| Install Google Cloud CLI - **Unpack tar** | Extract the tar archive preferably to your `Home` directory. |  |  |
| Install Google Cloud CLI - **Install** | `cd` to the root of the folder you extracted in the last step and run script: `./google-cloud-sdk/install.sh.` |  |  |
| Install Google Cloud CLI - **Initialize** | Initialize the Google Cloud CLI by running this script: `./google-cloud-sdk/bin/gcloud init` |  | *If not succeeding (i.e. changes did not take place) try to open a new terminal and run the script from there.* |
| Update Tanzu CLI - **version**| `tanzu version` will show you the current Tanzu CLI version you are running.<br />If you would like to update it then run script: `tanzu update`|  | *Accept any new version by following the terminal instructions.* |
| Update Tanzu CLI - **plugins**| `tanzu plugin list` will show you the current installed plugins but also upgradeable ones.<br />If you would like to install any then run script: `tanzu plugin install <PLUGIN NAME>` or if you want to upgrade any then: `tanzu plugin upgrade <PLUGIN NAME>`.| | |
| Kubectl CLI - **health check and upgrade** | Use `kubectl version --output=yaml` to see your client and server versions in yaml format.<br />Make sure the CLI client can run on the latest supported Kubernetes version - check [here](https://kubernetes.io/releases/).<br />If you need to upgrade your Kubectl CLI then the simple thing is to use Homebrew: `brew upgrade kubectl`. || *You will also be able to see the output in json format if changing to `--output=json`.* |
  
### Step 2a - How to use a GKE Artifact Repository
| What you are trying to achieve | On local Mac | In Google Cloud | Notes |
| --- | --- | --- | --- |
| xx | `yy` |  | Pay attention to.. |
| xx | `yy` | | bla bla|

### Step 2b - How to use a Harbor Repository
| What you are trying to achieve | On local Mac | In Google Cloud | Notes |
| --- | --- | --- | --- |
| xx | `yy` |  | Pay attention to.. |
| xx | `yy` | | bla bla|

### Step 3 - 
| What you are trying to achieve | Kubernetes (+other tools) | Tanzu Kubernetes Grid | Notes |
| --- | --- | --- | --- |
| Install Docker | `kubectl get pods` | `tanzu list..`| Kind requires that you have Docker installed and configured |
| Install Kind | `kubectl apply -f xyz.yaml`. | Show file differences that **haven't been** staged |
