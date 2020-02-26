## Issues in this Chapter

### 1. ssd-monitor-daemonset.yaml
apiVersion is not apps/v1beta2, now latest kubernetes it is in apps/v1

### 2. nodeSelector in ssd-monitor-daemonset.yaml "disk: ssd" does not have any matched node, execute following in minikube: <br>
kubectl label node minikube disk=ssd <br>
kubectl describe node minikube <br>
After the label is added, a new DeamonSet pod will be added automatically. <br>

### 3. 


