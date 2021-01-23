# Let's start the cluster

Start the Cluster: 
`launch.sh`{{execute}}

Check what options we have with `kubectl`{{execute}}

There are a lot of Kubernetes resources.
Take a look at it:
`kubectl api-resources`{{execute}}

`kubectl api-resources | wc -l`{{execute}}

It's a lot, maybe we can focus on the ones we will use more frequently: 
`kubectl api-resources | grep true`{{execute}}
`kubectl api-resources | grep true | wc -l`{{execute}}

In case you forget the meaning of a resource:
`kubectl explain node`{{execute}}

Gives you the possible fields
`kubectl explain node.spec`{{execute}}

Expands it all
`kubectl explain node --recursive`{{execute}}






