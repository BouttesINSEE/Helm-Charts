# helm-charts

**Ce dépôt contient :**
- l'ensemble des helm charts utilisés (répertoire ./apps) pour construire l'environnement de test de performance sur dev.insee.io à savoir :
  - une base [MongoDB](https://github.com/bitnami/charts/tree/master/bitnami/mongodb)

* Mongodb (accessible au sein du cluster uniquement)

| parameter  | value  |
|---|---|
| uri  |  ```echo mongodb://demo:$(kubectl get secret -n $ns mongodb-secret -o jsonpath="{.data.mongodb-password}" \| base64 --decode ; echo)@my-mongodb-0.my-mongodb-headless:27017,my-mongodb-1.my-mongodb-headless:27017,my-mongodb-2.my-mongodb-headless:27017``` |
| database  | poc |


## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:
```
  helm repo add BouttesINSEE https://BouttesINSEE.github.io/helm-charts
```
If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
BouttesINSEE` to see the charts.

To install the <chart-name> chart:

    helm install my-<chart-name> <alias>/<chart-name>

To uninstall the chart:

    helm delete my-<chart-name>
