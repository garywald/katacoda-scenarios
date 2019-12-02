C'était pas très beau ce pod qui tombe continuellement.

Supprimons le :

`kubectl delete deployment first-deployment`{{execute}}

Essayons une application qui expose un serveur que l'on va pouvoir joindre :

`kubectl create deployment hello-app --image=gcr.io/google-samples/hello-app:1.0`{{execute}}

`kubectl get pods`{{execute}}

Et maintenant, on va exposer un service pour pouvoir joindre ce port :

`kubectl expose deployment hello-app --port=80 --type=LoadBalancer`
