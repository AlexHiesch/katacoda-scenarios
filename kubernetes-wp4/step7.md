# What if we would need more instances?

Scale out to 10 instances
`kubectl scale deployment myapp --replicas=3`{{execute}}


`watch kubectl get po`{{execute}}

Stop it
`^C`{{execute ctrl-seq}}

How many pods do we have now?
`kubectl get po | tail +2 | wc -l`{{execute}}

Kill one pod and watch what happens
`kubectl delete pod $(kubectl get po | grep Running | head -n 1 | awk '{print $1;}') `{{execute}}

How many pods do we have now?
`kubectl get po | tail +2 | wc -l`{{execute}}


Since we have specified the desired amount of instances, it heals itself!
Isn't that nice?

