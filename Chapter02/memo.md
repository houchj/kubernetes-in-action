## Issues in the book:

### 1. 
houchj@ubuntu:~$ kubectl run kubia --image=houchj/kubia --port=8080 --generator=run/v1 <br>
kubectl run --generator=run/v1 is DEPRECATED and will be removed in a future version. Use kubectl run --generator=run-pod/v1 or kubectl create instead.
replicationcontroller/kubia created

### 2.
When installing minikube, use VirtualBox drive is much more better, even though linux can use --vm-driver=none option it needs sudo permission and makes the installation much more complex.<br>
Follow this to install it on ubuntu: https://vitux.com/how-to-install-virtualbox-on-ubuntu/

### 3.
After a successful installation, if kubectl can not connect the the cluster, please check the ~/.kube/config for the cluster ip address and add it to NO_PROXY env variable.


### 4.
After successful installation, if minikube dashboard can not open, minikube stop and minikube start again to resolve it.


 