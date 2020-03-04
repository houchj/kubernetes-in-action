## Memos of helm 

### 1. the connection of helm repo and hub need proxy, but monsoon kubernetes doesn't need proxy in corp network so need to use following command:
 set HTTP_PROXY=http://proxy.pvgl.sap.corp:8080
 set HTTPS_PROXY=http://proxy.pvgl.sap.corp:8080
 set NO_PROXY=localhost, *.cloud.sap






