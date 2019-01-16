# kubernetes-commands
Commands for kubectl, the command line interface of kubernetes

- Get information about current running deployment: 

  ```kubectl get deployment <deploymentName> -o yaml```
  
- Save information about current deployment in a local yaml file: 

  ```kubectl get deployment <deploymentName> -o yaml > currentDeployment.yaml```
  
- Check revisions of a deployment. You can only see the number of histories based on the number set by `revisionHistoryLimit` in the deployment yaml file. 

  ```kubectl rollout history deployment <deploymentName>```
  
- Roll back to a specific version (let's say 2): 

  ```kubectl rollout undo deployment <deploymentName> --to-revision=2```
  
- Get detailed information about a particular resource e.g. pod named podName: 

  ```kubectl describe pod podName```
  
- Delete everything running. Assuming everything you ran lies in the current folder (e.g. deployment.yaml, replicaset.yaml): 

  ```kubectl delete -f .```
  
- See all available contexts: 

  ```kubectl config get-contexts```
  
- See the current context:

  ```kubectl config current-context```
  
- Make docker-for-desktop(e.g.) as the current context:

  ```kubectl config use-context docker-for-desktop```
