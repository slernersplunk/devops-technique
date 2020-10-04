https://opensource.com/article/20/5/kubectl-cheat-sheet


Install k3s https://k3s.io/  
`curl -sfL https://get.k3s.io | sh -`  

`kubectl get pods --all-namespaces`

Docker Desktop for Mac  
`kubectl config use-context docker-desktop`

Shell into pod  
`kubectl exec --stdin --tty PODNAME -- /bin/bash`

Blank ubuntu pod
```
apiVersion: v1
kind: Pod
metadata:
  name: ubuntu
  labels:
    app: ubuntu
spec:
  containers:
  - image: ubuntu
    command:
      - "sleep"
      - "604800"
    imagePullPolicy: IfNotPresent
    name: ubuntu
  restartPolicy: Always
  ```
