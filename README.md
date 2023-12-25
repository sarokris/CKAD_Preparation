# CKAD_Preparation
Certified Kubernetes application developer certification preparation guide and learnings 

Root level attributes of every kubernetes definition files are below

* `apiVersion`
* `kind`
* `metadata`
* `spec`

## Useful Kubectl Commands 
### Pod
*   `kubectl get pods` 
    -  This can be used to get the currently running pods
*  `kubectl run <pod-name> --image=<image-name>`
    -  Easiest way to create the pod using kubectl run command
*  `kubectl describe pod <pod-name>` 
    -  Use this to get the insights about the pod like name, Node, Image and other metadata
*  `kubectl delete pod <pod-name> [--force]` 
    - This is to delete the pod --force is an optional param here 

*  `kubectl get pod <pod-name> -o yaml > pod-definition.yaml`
    - You may extract the pod definition to a file using this command

*  `kubectl edit pod <pod-name>`
    - You can utilize this command to modify the properties of the pod

*  `kubectl run <pod-name> --image=<image-name> --dry-run=client -o yaml > file_name.yaml`
    - Easiest way to create the pod definition file using exam environment once the file is ready you can use the next command to create the pod
*  `kubectl create|apply  -f pod_definition_file.yaml`
    - This is to create pod using pod-definition-file

### ReplicaSet
#### Replication controller is replaced by ReplicaSet
* Helps in ensuring the specified number of pods is running, by having said that the **High availability** is achieved.

* Another usecase is creating multiple container to share the load accross the pods (**Load balancing & Scaling**)  

* When the demand increases and out of resources in the existing worker node it can create the additional pods to balance the node in another worker node

#### Root level attributes for every ReplicaSet 
![Solution](./images/replicaset_rootlevel_attr.png)
#### A sample ReplicaSet
![Solution](./images/replicaset.png)

> Replicaset can also manage the pod that has not been created as part of the replicaset creation using the **selector**

#### Scaling replicas
- There are different ways to scale the number of replicas, lets take a look at the possible ways
* You can update the **replicas** in your replicaSet definition file and run the below command to scale in
    - `kubectl replace -f replicaset-definition.yaml`
* You can also use the **scale** command like below, this will also update replicas as 6 in your replicaset-definition file.
    - `kubectl scale --replicas=6 -f replicaset-definition.yaml`

#### Other useful commands 
* `kubectl create -f replicaset-definition.yaml`
   - Used to create the replicaset
* `kubectl get replicaset`
   - Used to get the replicasets
* `kubectl delete replicaset my-app`
   - Used to delete the replicaset and also undelying pods
> scaling and replcing you can refer the previous section 
