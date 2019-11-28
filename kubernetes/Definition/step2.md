## Provisionning de notre Cluster

Nous pouvons lancer notre premier déploiement sur le cluster en utilisant la commande create

`kubectl create deployment first-deployment --image=garywald/docker-whale`{{execute}}

Regardons notre déploiement généré :

`kubectl get pods`{{execute}}

Il s'agit ici d'un container qui n'execute qu'une commande echo. Il ne restera donc pas up, on peut se baser pour son execution au nombre de restarts.
Pour voir ce qui se déroule dans un container et donc afficher sa sortie standard, nous utiliserons la commande `logs`

`kubectl logs -l app=first-deployment --tail 100`{{execute}}
