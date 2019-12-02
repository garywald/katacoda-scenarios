## Provisionning de notre Cluster

Pour la suite du tutoriel, nous allons regarder ce qu'il se passe au niveau de mes pods en continue sur le deuxième terminal

`watch -n 1 kubectl get pods`{{execute HOST2}}

Nous pouvons lancer notre premier déploiement sur le cluster en utilisant la commande create

`kubectl create deployment first-deployment --image=garywald/docker-whale`{{execute HOST1}}

Il s'agit ici d'un container qui n'execute qu'une commande echo. Il ne restera donc pas up, on peut se baser pour son status ou sur le nombre de restarts pour suivre l'execution.

Pour voir ce qui se déroule dans un container et donc afficher sa sortie standard, nous utiliserons la commande `logs`

`kubectl logs -l app=first-deployment --tail 100`{{execute HOST1}}
