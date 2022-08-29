# Use the official helm chat

Link: https://github.com/jenkinsci/helm-charts/tree/main/charts/jenkins

## Download Repository

```shell

  helm repo add jenkins https://charts.jenkins.io
  helm repo update

```

## Create values.yaml

```shell

  helm show values jenkins/jenkins > ./helm/values.yaml

```

## Install helm chart

```shell

  helm upgrade --install jenkins jenkins/jenkins -n jenkins -f ./helm/values.yaml

```

## Remove helm chart

```shell

  helm uninstall jenkins -n jenkins

```

## Get Password after installing chart

```shell

  kubectl exec --namespace jenkins -it svc/jenkins -c jenkins -- /bin/cat /run/secrets/additional/chart-admin-password && echo
  # use this password to login with the account "admin"

```
