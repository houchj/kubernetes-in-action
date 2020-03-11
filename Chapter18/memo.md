##  Memos in this Chapter

### 1. the kubectl-proxy is a little old, change it to newer versions, see the folder kubectl-proxy
       the kubectl version is changed to 1.15.9 reflecting the latest version in monsoon <br>
       $ docker build -t houchj/kubectl-proxy:1.15.10 .  (version bumped because of a permission bug in the orignal code) <br>
       $ docker push houchj/kubectl-proxy:1.15.10         <br>
       $ kubectl apply -f website-controller.yaml         <br>
  Until now, we should see one Deployment called "website-controller" and one ReplicaSet one Pod started successfully. <br>
  RBAC is enabled on monsoon, the above steps were successful on local with kubectl proxy(cluster admin role), but failed in the pod(service account role) without following command in the book: <br>
       $ kubectl create clusterrolebinding website-controller --clusterrole=cluster-admin --serviceaccount=default:website-controller  <br>

### 2. the new image is under houchj/kubectl-proxy:1.15.10
### 3. the new controller image is under houchj/website-controller:1.0.5

### 4. the controller code is under https://github.com/houchj/k8s-website-controller.git
  Note: fully works on monsoon
### 5. about how to use the new WebSite
  Use command kubectl create -f website-controller.yaml to create the controller. make sure the controller pods is started and no error in the controller pod. <br>
  Use command $ kubectl create -f kubia-website.yaml to create the new Website resource under the new controller, then use following steps to access it(cluster node). <br>
  1. start kubectl proxy on localhost <br>
  2. http://127.0.0.1:8001/api/v1/namespaces/ec01/services/kubia-website:80/proxy/ <br>




