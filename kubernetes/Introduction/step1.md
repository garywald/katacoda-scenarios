## Déploiement de l'environnement minikube

Par simplicité, nous allons exécuter notre cluster sur un environnement minikube. Testons l'installation de minikube.

`minikube version`{{execute T1}}

Nous pouvons voir que minikube est installé mais pas lancé.

`minikube status`{{execute T1}}

Nous pouvons lancer minikube.

`minikube start --wait=false`{{execute T1}}

`minikube status`{{execute T1}}

Une fois que votre environnement est monté, vous avez un cluster kubernetes qui comporte un node. Nous utiliserons le CLI pour interragir avec kubernetes. Le CLI s'utilise avec la commande `kubectl` qui vous permettra d'interragir avec le cluster pour déployer, regarder et manager vos ressources.

Exemple : Les détails concernant le cluster sont consultable en tapant la commande suivante :

`kubectl cluster-info`{{execute T1}}

Nous pouvons consulter les nodes du cluster via :

`kubectl get nodes`{{execute T1}}

Si le noeud est marqué en **NotReady**, c'est qu'il est en cours de démarrage.
Ici nous n'avons qu'un noeud car nous utilisons minikube. Dans un prochain tuto, nous verrons comment monter un cluster de plusieurs noeuds.

Mais pour l'instant commencons déjà par provisionner notre cluster.
