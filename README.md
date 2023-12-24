# CKAD_Preparation
Certified Kubernetes application developer certification preparation guide and learnings 

Root level attributes of every kubernetes definition files are below

* `apiVersion`
* `kind`
* `metadata`
* `spec`

## Useful Kubectl Commands 
### Pod
*  > `kubectl get pods` 
    -  This can be used to get the currently running pods
* > `kubectl run <pod-name> --image=<image-name>`
    -  Easiest way to create the pod using kubectl run command
* > `kubectl describe pod <pod-name>` 
    -  Use this to get the insights about the pod like name, Node, Image and other metadata
* > `kubectl delete pod <pod-name> [--force]` 
    - This is to delete the pod --force is an optional param here 

* > `kubectl get pod <pod-name> -o yaml > pod-definition.yaml`
    - You may extract the pod definition to a file using this command

* > `kubectl edit pod <pod-name>`
    - You can utilize this command to modify the properties of the pod

* > `kubectl run <pod-name> --image=<image-name> --dry-run=client -o yaml > file_name.yaml`
    - Easiest way to create the pod definition file using exam environment once the file is ready you can use the next command to create the pod
* > `kubectl create|apply  -f pod_definition_file.yaml`
    - This is to create pod using pod-definition-file
