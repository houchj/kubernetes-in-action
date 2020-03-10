##  Memos in this Chapter

### 1. the kubectl-proxy is a little old, change it to newer versions, see the folder kubectl-proxy
       the kubectl version is changed to 1.15.9 reflecting the latest version in monsoon <br>
       $ docker build -t houchj/kubectl-proxy:1.15.10 .  (version bumped because of a permission bug in the orignal code) <br>
       $ docker push houchj/kubectl-proxy:1.15.10         <br>
       $ kubectl apply -f website-controller.yaml         <br>
  Until now, we should see one Deployment called "website-controller" and one ReplicaSet one Pod started successfully. <br>
  Looks like the RBAC is not enabled on monsoon, the above steps were successful without following command in the book: <br>
       $ kubectl create clusterrolebinding website-controller --clusterrole=cluster-admin --serviceaccount=default:website-controller

### 2. the new image is under houchj/kubectl-proxy:1.15.10


### 3. about how to use the new WebSite





