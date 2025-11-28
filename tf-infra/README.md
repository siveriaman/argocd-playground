Usage:
---
Perform the following steps to use the provider:

Go to the provider example folder:
```
cd tf-infra
```
Edit the main.tf file and change the config as needed.

Initialize Terraform:
```
terraform init
```
Plan the provisioning:
```
terraform plan
```
Deploy the cluster:
```
terraform apply
```
More details about implementation: https://registry.terraform.io/providers/tehcyx/kind/latest/docs/resources/cluster

In case of local deployment:
----
* Forward Argocd connection to localhost:
```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
* Retrieve initial admin user password within the next commands:
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath='{.data.password}' | base64 -d
```
