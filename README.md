# poc-stromae-mongo

**Ce dépôt contient :**
- l'ensemble des helm charts utilisés (répertoire ./apps) pour construire l'environnement de test de performance sur dev.insee.io à savoir :
  - une base [MongoDB](https://github.com/bitnami/charts/tree/master/bitnami/mongodb)

* Mongodb (accessible au sein du cluster uniquement)

| parameter  | value  |
|---|---|
| uri  |  ```echo mongodb://demo:$(kubectl get secret -n $ns mongodb-secret -o jsonpath="{.data.mongodb-password}" \| base64 --decode ; echo)@my-mongodb-0.my-mongodb-headless:27017,my-mongodb-1.my-mongodb-headless:27017,my-mongodb-2.my-mongodb-headless:27017``` |
| database  | poc |
