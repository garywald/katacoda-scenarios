Nous allons terminer ce petit tutoriel en testant quelques autres fonctionnalités :

Aucun intérêt d'avoir un outil aussi puissant pour ne faire tourner qu'une seule instance de notre application :

`kubectl scale deployment hello-app --replicas=3`{{execute t1}}

Vous ai-je déjà dis que Kubernetes s'auto-répare?

`kubectl delete pod $(kubectl get pods -o jsonpath="{.items[0].metadata.name}")`{{execute t1}}

Et sa mise à jour sans arrêt de process, en rolling-upgrade :

`kubectl set image deployment hello-app hello-app=gcr.io/google-samples/hello-app:2.0`{{execute T1}}

Nous pouvons suivre sur le deuxième terminal comment la mise à jour s'effectue sans qu'il y ait la moindre interruption de service. D'ailleurs testons le service :

`watch -n 1 curl $(minikube ip):$PORT`{{execute T1}}
