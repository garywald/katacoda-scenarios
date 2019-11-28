## Provisionning de notre Cluster

Nous pouvons lancer notre premier déploiement sur le cluster en utilisant la commande create

`kubectl create deployment first-deployment --image=garywald/docker-whale`{{execute}}

Pour voir ce qui se déroule dans un container et donc afficher sa sortie standard, nous utiliserons la commandes logs

`kubectl logs first-deployement`
