# Let's explore the cluster a bit

Verify that our nodes are running `kubectl get nodes`{{execute}}

More details `kubectl get nodes -o wide`{{execute}}

I said MOOOOOOOOOOOORE details `kubectl get nodes node01 -o json`{{execute}}

A bit less verbose `kubectl get nodes node01 -o yaml`{{execute}}

What OS are they running on?

`kubectl get nodes -o json | jq .items[].status.nodeInfo.osImage | sort | uniq -c`{{execute}}

Show the capacity of all our nodes as a stream of JSON objects
`kubectl get nodes -o json | jq ".items[] | {name:.metadata.name} + .status.capacity"`{{execute}}

In order to get details of a particular note, use `kubectl describe node node01`{{execute}}