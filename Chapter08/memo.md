###   Issues in this Chapter

## 1. the busybox image can not be started up, because the request memory and cpu are too small,
<p>change to following: <br>
    resources:
      requests:
        cpu: 150m
        memory: 1000Ki
      limits:
        cpu: 1000m
        memory: 40Mi
</p>

### 2. curl -H "Authorization: Bearer $TOKEN" https://kubernetes
 Page 241, the above command will report error as the kubernetes version upgraded: <br>
forbidden: User \"system:serviceaccount:default:default\" cannot get path \ <br>
Change to this command will resolve the issue: <br>
curl -H "Authorization: Bearer $TOKEN" https://kubernetes/api/v1

### 3. Without disabling the RBAC the list pod api will pop error.
curl -H "Authorization: Bearer $TOKEN" https://kubernetes/api/v1/namespaces/$NS/pods <br>
pods is forbidden: User \"system:serviceaccount:default:default\" cannot list resource \"pods\" in API group \"\" in the namespace \"default\ <br>

So do this: <br>
kubectl create clusterrolebinding permissive-binding \
--clusterrole=cluster-admin \
--group=system:serviceaccounts


### 4. All the commands modified in the Chapter
export CURL_CA_BUNDLE=/var/run/secrets/kubernetes.io/serviceaccount/ca.crt <br>
TOKEN=$(cat /var/run/secrets/kubernetes.io/serviceaccount/token)  <br>

curl -H "Authorization: Bearer $TOKEN" https://kubernetes  <br>

NS=$(cat /var/run/secrets/kubernetes.io/serviceaccount/namespace) <br>

curl -H "Authorization: Bearer $TOKEN" https://kubernetes/api/v1/namespaces/$NS/pods <br>

kubectl create clusterrolebinding permissive-binding \  <br>
--clusterrole=cluster-admin \   <br>
--group=system:serviceaccounts  <br>


minikube start --extra-config=apiserver.Features.Enable-SwaggerUI=true <br>


