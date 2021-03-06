# Kubernetes scripts deployment

## Prerequisites
In order to deploy the k8s scripts, you will need the following:

- A cloud infrastructure like Azure or AWS
- A k8s cluster where you are able to deploy containers

## Important information
If you are using AWS, you maybe need to change some things in order to get the deployment scripts working, e.g. the storage-class files.

## How to deploy the k8s scripts
Firstly, you need to connect your local machine to your cloud infrastructure via ssh like this:

`ssh -i '<path to ssh rsa file>' -L localhost:3500:<cloud infrastructure k8s cluster ip address>:<cloud infrastructure k8s cluster port> <cloud infrastructure user>@<cloud infrastructure ip address>`

Then, you may use the ps1 scripts located in `idsa/src/k8s`. In this case you need to execute them in the following order:

1. `create_namespace.ps1`
2. `apply_azure_storage-classes.ps1`
3. `apply_broker.ps1`, `apply_daps.ps1`

## How to delete the deployed containers
In order to delete the broker and daps k8s deployments, simply run the `delete_namespace.ps1` script. It will take a while until everything is deleted, though.

## Tips
We recommend to use a k8s-based IDE like Lens. Managing and debugging k8s units is a lot easier using one.