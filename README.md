Bienvenue dans le dépôt `helm-charts`. Ce dépôt contient les Helm charts des applications utilisées pour l'apprentissage de Kubernetes. Vous trouverez ici toutes les ressources nécessaires pour déployer et gérer vos applications Kubernetes avec Helm.

## Description

Ce dépôt centralise les Helm charts qui faciliteront le déploiement, la configuration et la gestion des applications dans un cluster Kubernetes. Chaque chart est conçu pour être réutilisable et facile à personnaliser selon les besoins spécifiques des différents environnements de développement et de production.

## Dev

### Commandes de developpement

Ajoutons un fichier robots.txt à l'emplacement racine du référentiel , Cela évitera l'exploration de robots sur le référentiel Helm.
```sh
$ cd <"dir of the chart (for example: datascientest)">
$ echo -e “User-Agent: *\nDisallow: /” > robots.txt 
```

Nous devons créer un fichier .tgz de la chart Helm à l'emplacement racine qui nous permettra d'empaqueter les charts que nous avons créés pour pouvoir les distribuer. Il s'agit de la commande permettant de créer un fichier d'archive versionné du chart :
```sh
$ helm package <"dir of the chart (for example: datascientest)">  -d charts
```
ou si vous estes dans le meme repertoire:

```sh
$ helm package . -d charts
```

## Commandes d'utilisation

### Ajouter le dépôt Helm

Pour ajouter ce dépôt à votre configuration Helm, utilisez la commande suivante :
```sh
$ helm repo add <myrepos> https://f3lin.github.io/helm-charts/charts
```

### Rechercher dans le dépôt

Pour rechercher les charts disponibles dans ce dépôt, utilisez la commande suivante :
```sh
$  helm search repo <myrepos>
```

### Installer une application

Pour installer une application à partir de ce dépôt, utilisez la commande suivante :
```sh
$ helm install app <myrepos>/datascientest -n datascientest-chart --values=values.yaml --create-namespace
```

Cette commande installera l'application `datascientest` dans le namespace `datascientest-chart` en utilisant les valeurs définies dans le fichier `values.yaml ` et créera le namespace s'il n'existe pas déjà.

Nous espérons que ce dépôt vous sera utile pour vos projets Kubernetes. Pour toute question ou contribution, n'hésitez pas à ouvrir une issue ou une pull request.
