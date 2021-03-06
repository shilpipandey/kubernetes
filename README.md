# Kubernetes basic commands

1. To install kubectl:
  > brew install kubernetes-cli

2. To ensure the version you installed is sufficiently up-to-date:
  > kubectl version

3. List the available nodes with the command:
  > kubectl get nodes

4. List the current namespaces in a cluster: 
  > kubectl get namespaces

5. List all pods in current namespace in ps output format:
> kubectl get pods

6. Switch to the production namespace:
> kubectl config use-context prod

7. Get pods in a particular namespace:
> kubectl -n “namespace name” get pods

8. Get pods in a particular namespace with more details:
> kubectl -n “namespace name” get pods -w

9. List all pods in all namespaces:
> kubectl get pods --all-namespaces  

10. List all pods in the namespace, with more details:
> kubectl get pods -o wide         

11. List all pods in the namespace, including uninitialized ones:
> kubectl get pods --include-uninitialized      

12. List all services in the namespace:
> kubectl get services

13. List a particular replication controller
> kubectl get rc "rc-name"

14. List a particular RC:
> kubectl get replicationcontroller "rc-name"

15. You can also get a detailed output of your pod by using the command:
> kubectl describe pods

16. View the deployment with the command:
> kubectl get deployments

17. List Services Sorted by Name:
> kubectl get services --sort-by=.metadata.name

## Deleting Resources ##
1. Delete a pod using the type and name specified in pod.json:
> kubectl delete -f ./pod.json 

2. Delete pods and services with same names "baz" and "foo"
> kubectl delete pod,service baz foo 

3. Delete pods and services with label name=myLabel
> kubectl delete pods,services -l name=myLabel  

4. Delete pods and services, including uninitialized ones, with label name=myLabel
> kubectl delete pods,services -l name=myLabel --include-uninitialized

5. Delete all pods and services, including uninitialized ones, in namespace my-ns
> kubectl -n my-ns delete po,svc --all
