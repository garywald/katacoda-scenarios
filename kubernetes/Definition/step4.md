Nous allons terminer ce petit tutoriel en testant quelques autres fonctionnalités :

Aucun intérêt d'avoir un outil aussi puissant pour ne faire tourner qu'une seule instance de notre application :

`kubectl scale deployment hello-app --replicas=3`{{execute T1}}

Vous ai-je déjà dis que Kubernetes s'auto-répare?

`kubectl delete ${kubectl get pods -o jsonpath="{.items[0].metadata.name}"}`{{execute T1}}

Et sa mise à jour sans arrêt de process, en rolling-upgrade :

`kubectl set image deployment hello-app app=gcr.io/google-samples/hello-app:2.0`{{execute T1}}

Nous pouvons suivre sur le deuxième terminal comment la mise à jour s'effectue sans qu'il y ait la moindre interruption de service. D'ailleurs testons le service :

`curl $(minikube ip):$PORT`{{execute T1}}
