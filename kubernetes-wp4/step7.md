# What if we would need more instances?

Scale out to 10 instances


`watch kubectl get po`{{execute}}

Stop it

Kill one host and watch what happens

`watch kubectl get po`{{execute}}

Since we have specified the desired amount of instances, it selfheals!
Isn't that nice?

