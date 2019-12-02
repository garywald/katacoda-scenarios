Un pod qui tombe continuellement, ce n'est pas le must...

Supprimons le :

`kubectl delete deployment first-deployment`{{execute}}

Essayons une application qui expose un serveur que l'on va pouvoir joindre :

`kubectl create deployment hello-app --image=gcr.io/google-samples/hello-app:1.0`{{execute}}

Et maintenant, on va exposer un service pour pouvoir joindre ce port :

`kubectl expose deployment hello-app --port=8080 --type=NodePort`{{execute}}

On peut voir le servie généré et surtout le port qui est mis à notre disposition.

`kubectl get svc hello-app`{{execute}}

On récupère le port et on appelle notre service

`service=hello-app`{{execute}}

`export PORT=$(kubectl get svc ${service} -o go-template='{{range.spec.ports}}{{if .nodePort}}{{.nodePort}}{{"\n"}}{{end}}{{end}}')`{{execute}}

`echo $(minikube ip):$PORT`{{execute}}

`curl $(minikube ip):$PORT`{{execute}}
