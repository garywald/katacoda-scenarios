## Provisionning de notre Cluster

Pour la suite du tutoriel, nous allons regarder ce qu'il se passe au niveau de mes pods en continue sur un deuxième terminal

`watch -n 1 kubectl get pods`{{execute T2}}

Nous pouvons lancer notre premier déploiement sur le cluster en utilisant la commande create ou run. Retournez sur le premier terminal ou lancer la commande suivante :

`kubectl create deployment first-deployment --image=garywald/docker-whale`{{execute T1}}

En vous rendant sur le deuxième terminal, vous pouvez suivre le déploiement du pod.

Il s'agit ici d'un container qui n'execute qu'une commande echo. Il ne restera donc pas up, on peut se baser pour son status ou sur le nombre de restarts pour suivre l'execution.

Pour voir ce qui se déroule dans un container et donc afficher sa sortie standard, nous utiliserons la commande `logs`

`kubectl logs -l app=first-deployment --tail 100`{{execute T1}}
