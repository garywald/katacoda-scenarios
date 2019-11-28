## Déploiement de l'environnement minikube

Par simplicité, nous allons exécuter notre cluster sur un environnement minikube. Testons l'installation de minikube.

`minikube version`{{execute}}

Nous pouvons lancer minikube

`minikube start --wait=false`{{execute}}

Une fois que votre environnement est monté, vous avez un cluster kubernetes d'un noeud installé. Nous utiliserons le CLI pour interragir dessus ainsi qu'avec l'applicatif que l'on déploiera après. Le CLI s'utilise avec la commande `kubectl`

Exemple : Les détails concernant le cluster sont consultable en tapant la commande suivante :

`kubectl cluster-info`{{execute}}

Nous pouvons consulter les nodes utilisés par le cluster via :

`kubectl get nodes`{{execute}}

Si le noeud est marqué en **NotReady**, c'est qu'il est en cours de démarrage.
Ici nous n'avons qu'un noeud car nous utilisons minikube. Dans un prochain tuto, nous verrons comment monter un cluster de plusieurs noeuds.

Mais pour l'instant commencons déjà par provisionner notre cluster.
