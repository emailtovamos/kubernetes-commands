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
