# Let's start and explore the cluster a bit

Start the Cluster: 
`launch.sh`{{execute}}

Check what options we have with `kubectl`{{execute}}

Verify that our nodes are running `kubectl get nodes`{{execute}}
More details `kubectl get nodes -o wide`{{execute}}
I said MOOOOOOOOOOOORE details `kubectl get nodes node01 -o json`{{execute}}
A bit less verbose `kubectl get nodes node01 -o yaml`{{execute}}
What OS are they running on?
`kubectl get nodes -o json | jq .items[].status.nodeInfo.osImage | sort | uniq -c`{{execute}}
Show the capacity of all our nodes as a stream of JSON objects
`kubectl get nodes -o json | jq ".items[] | {name:.metadata.name} + .status.capacity"`{{execute}}

In order to get details of a particular note, use `kubectl describe node node01`{{execute}}



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






