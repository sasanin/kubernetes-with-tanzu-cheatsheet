## TAP version 1.5.1 on Google Kubernetes Engine (GKE)

## Introduction
This installation guide will let you install a full TAP profile on a GKE cluster using a Mac. Please take a note of the [TAP prerequisities for GKE](https://docs.vmware.com/en/VMware-Tanzu-Application-Platform/1.5/tap/prerequisites.html#:~:text=Google%20Kubernetes%20Engine).

Before installing TAP on GKE make sure that you have the following:
* Tanzu and Kubectl CLIs installed. If not, go to **XX**.
* Docker installed on your Mac. If not, [install client binaries on macOS](https://docs.docker.com/engine/install/binaries/#:~:text=Install%20client%20binaries%20on%20macOS%F0%9F%94%97).
* A Tanzu Network account with noted username and password.
  - If not, please go to https://network.tanzu.vmware.com and create one. Save the username and password as we will **XX**
* Access to https://registry.tanzu.vmware.com using the same credentials as above.
* A Google Cloud Account that gives you access to the GKE console https://console.cloud.google.com/.

### Step 1 - Obtaining and refreshing CLIs
| What you are trying to achieve | On local Mac | In Google Cloud | Notes |
| --- | --- | --- | --- |
| Install Google Cloud CLI - **Download tar** | Confirm that you have a supported version (3.5 to 3.9) of Python 3 by running `python3 -V` or `python -V`.<br />If you do not have Python installed or the right version then fix it [here](https://www.python.org/downloads/).<br />Download the gcloud CLI for macOS 64-bit [x86_64](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-x86_64.tar.gz), [ARM64, Apple M1 silicon](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-arm.tar.gz), or [x86](https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-435.0.1-darwin-x86.tar.gz). |  |  |
| Install Google Cloud CLI - **Unpack tar** | Extract the tar archive preferably to your `Home` directory. |  |  |
| Install Google Cloud CLI - **Install** | `cd` to the root of the folder you extracted in the last step and run script: `./google-cloud-sdk/install.sh.` |  |  |
| Install Google Cloud CLI - **Initialize** | Initialize the gcloud CLI by running this script: `./google-cloud-sdk/bin/gcloud init`.<br />Accept the option to log in using your Google user account and select your project (if only one, Google will automatically select if for you). |  | *If not succeeding (i.e. changes did not take place) try to open a new terminal and run the script from there.* |
| Install Google Cloud CLI - **Update** | Update the gcloud CLI: `gcloud components update` | | |
| Install Google Cloud CLI - **(Optional) Login** | Login to your Google Account using: `gcloud login auth` | | *This script will take you to a page where you will authenticate with the gcloud CLI!<br />This step is only needed if you have not logged in yet!* |
| Install Google Cloud CLI - **(Optional) Set project** | See available projects by: `gcloud projects list`.<br />Set the project that you want to use: `gcloud config set project <PROJECT_ID>` | | |
| Install Google Cloud CLI - **Enable services** | Enable the Artifact Registry and Resource Manager APIs for the gcloud CLI: `gcloud services enable artifactregistry.googleapis.com cloudbuild.googleapis.com` | | *Make sure Operation "VALUE" finishes successfully.* |
| Update Tanzu CLI - **Version**| `tanzu version` will show you the current Tanzu CLI version you are running.<br />If you would like to update it then run script: `tanzu update`|  | *Accept any new version by following the terminal instructions.* |
| Update Tanzu CLI - **Plugins**| `tanzu plugin list` will show you the current installed plugins but also upgradeable ones.<br />If you would like to install any then run script: `tanzu plugin install <PLUGIN NAME>` or if you want to upgrade any then: `tanzu plugin upgrade <PLUGIN NAME>`.| | |
| Kubectl CLI - **Health check and upgrade** | Use `kubectl version --output=yaml` to see your client and server versions in yaml format.<br />Make sure the CLI client can run on the latest supported Kubernetes version - check [here](https://kubernetes.io/releases/).<br />If you need to upgrade your Kubectl CLI then the simple thing is to use Homebrew: `brew upgrade kubectl`. || *You will also be able to see the output in json format if changing to `--output=json`.* |
  
### Step 2a - How to use a GKE Artifact Repository
| What you are trying to achieve | On local Mac | In Google Cloud | Notes |
| --- | --- | --- | --- |
| Go to Artifact Registry in Google Cloud | | Go to your [Google Cloud Console](https://console.cloud.google.com/) and search for "Artifact Registry". This reqistry will hold all your repositories. | *Before you start make sure you are in the right project. Check this by the project drop down list in upper left corner.* |
| Create new Registry | | Click on `CREATE REPOSITORY` and fill in the following:<br />*Name*: tap-registry<br />*Format*: Docker<br />*Mode*: Standard<br />*Location type*: Region >> your region (I am using `europe-north1 (Finland)`<br />*Encryption*: Google-managed encryption key<br />Click on `CREATE`.| *You must create an Artifact Registry Docker repository before you push an image (e.g. TAP) to it.<br /><br />You can confirm the creation in terminal by: `gcloud artifacts repositories list`.*|
| Configure Docker for the repository | **(2)** Copy the command and run it in terminal to configure gcloud as the credential helper for the Artifact Registry domain associated with the location of tap-registry. | **(1)** Check mark the tap-registry repository and click on `SETUP INSTRUCTIONS`. ||
| Assign value to `GOOGLE_REGISTRY_PROJECT`| Open `tap-registry` and copy the path to it. Save it as europe-north1-docker.pkg.dev/<YOUR_PROJECT>/tap-registry for variable GOOGLE_REGISTRY_PROJECT`. |  | |

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
