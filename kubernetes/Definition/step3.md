C'était pas très beau ce pod qui tombe continuellement.

Supprimons le :

`kubectl delete deployment first-deployment`{{execute}}

Essayons une application qui expose un serveur que l'on va pouvoir joindre :

`kubectl create deployment hello-app --image=gcr.io/google-samples/hello-app:1.0`{{execute}}

`kubectl get pods`{{execute}}

Et maintenant, on va exposer un service pour pouvoir joindre ce port :

`kubectl expose deployment hello-app --port=8080 --type=LoadBalancer`{{execute}}

`kubectl get svc hello-app`{{execute}}

On récupère le port que kubernetes a mis à notre disposition et on appelle notre service
`service=first-deployment`{{execute}}
`export PORT=$(kubectl get svc ${service} -o go-template='{{range.spec.ports}}{{if .nodePort}}{{.nodePort}}{{"\n"}}{{end}}{{end}}')`{{execute}}
`curl $(minikube ip):$PORT`{{execute}}
