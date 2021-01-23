# It's about time to run our first container

 `kubectl run firsttry --image=alpine ping google.com`{{execute}}

What happened?

`kubectl get po`{{execute}}

`kubectl get all`{{execute}}

It seems like we are not running containers, but instead a deployment, a pod and a replicaset

What is the pod doing?
Let's stream the logs:
`kubectl logs firsttry --follow --tail 1`{{execute}}

