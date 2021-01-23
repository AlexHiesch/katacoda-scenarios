# It's about time to run our first container

 `kubectl run firsttry --image=alpine ping google.com -t 1000`{{execute}}

What happened?

`kubectl get po`{{execute}}

`kubectl get all`{{execute}}

It seems like we are not running containers, but instead a deployment, a pod and a replicaset

What is the pod doing?
Let's stream the logs:
`kubectl logs deploy/firsttry --follow --tail 1`{{execute}}

1 pod doesn't sound much, I think we can do better than that:
`kubectl scale deployment firsttry 10`{{execute}}

Take a look at the logs again:

`kubectl logs deploy/firsttry --follow --tail 1`{{execute}}

Seems like we have more pods now of different age:
`kubectl get po`{{execute}}

Maybe 10 are actually a bit too much.

