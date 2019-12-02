Un pod qui tombe continuellement, ce n'est pas le must...

Supprimons le :

`kubectl delete deployment first-deployment`{{execute HOST1}}

Essayons une application qui expose un serveur que l'on va pouvoir joindre :

`kubectl create deployment hello-app --image=gcr.io/google-samples/hello-app:1.0`{{execute HOST1}}

Et maintenant, on va exposer un service pour pouvoir joindre ce port :

`kubectl expose deployment hello-app --port=8080 --type=NodePort`{{execute HOST1}}

On peut voir le servie généré et surtout le port qui est mis à notre disposition.

`kubectl get svc hello-app`{{execute HOST1}}

On récupère le port et on appelle notre service

`service=hello-app`{{execute HOST1}}

`export PORT=$(kubectl get svc ${service} -o go-template='{{range.spec.ports}}{{if .nodePort}}{{.nodePort}}{{"\n"}}{{end}}{{end}}')`{{execute HOST1}}

`echo $(minikube ip):$PORT`{{execute HOST1}}

`curl $(minikube ip):$PORT`{{execute HOST1}}
