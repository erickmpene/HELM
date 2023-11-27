## DEPLOY HELM

#### This command will allow you to install HELM on your server

```sh 
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh

```

### Install kube-prometheus-stack
```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install [RELEASE_NAME] prometheus-community/kube-prometheus-stack
```
### Uninstall Helm Chart
```sh
helm uninstall [RELEASE_NAME]
```
### Grafana (Default password) 
Find default password for user "admin"  
```sh 
kubectl get secret <grafana's pod> -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```