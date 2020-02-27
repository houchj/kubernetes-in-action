## memo in this Chapter

### 1. change label of a existing pod to let it selected by service
$ kubectl label pod xxxxx app=kubia --overwrite <br>

### 2. query if there is any pods in the svc's selector
$ kubectl get po -l app=kubia <br>

### 3. NodePort service in minikube does not have an external IP, instead please use following command: <br>
$ minikube service kubia-nodeport <br>
it will open a browser window to access the service automatically, http://192.168.99.100:30123/  <br>

the IP 192.168.99.100 is also the node's Internal IP

So this make it loos like that the minukube with one default node setup has one IP address both for internal and external IP.



