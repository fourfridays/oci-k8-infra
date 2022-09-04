# oci-k8-infra
Terraform infrastructure as code deployment of Kubernetes platform.

## Infrastructure
Infrastructure code and readme taken and modified from [Free Oracle Cloud Kubernetes cluster with Terraform](https://arnoldgalovics.com/oracle-cloud-kubernetes-terraform/).

The repository contains a Terraform script for creating a fully functioning Kubernetes cluster on Oracle Cloud.

The repo was created for this article: [Free Oracle Cloud Kubernetes cluster with Terraform](https://arnoldgalovics.com/oracle-cloud-kubernetes-terraform/)

## Setup in a nutshell
1. Get the following data from your Oracle Cloud account
    * User OCID
    * Tenancy OCID
    * Compartment OCID
2. Open a terminal within the `oci-infra` folder
3. Execute a `terraform init`
4. Execute a `terraform apply`
5. Create your Kubernetes configuration file using 
    ```bash
    $ oci ce cluster create-kubeconfig --cluster-id <cluster OCID> --file ~/.kube/free-k8s-config --region <region> --token-version 2.0.0 --kube-endpoint PUBLIC_ENDPOINT
    ```
6. Apply your K8S config for kubectl
    ```bash
    $ export KUBECONFIG=~/.kube/free-k8s-config
    ```
7. To verify cluster access, do a `kubectl get nodes`
8. Enjoy

## Ingress

### Traefik
Code and instructions taken from [Ready/Set/Go Kubernetes+Traefik+LetsEncrypt on ARM at Oracle OCI](https://marcelo-ochoa.medium.com/ready-set-go-kubernetes-traefik-letsencrypt-on-arm-at-oracle-oci-eb4a672d3a3a)