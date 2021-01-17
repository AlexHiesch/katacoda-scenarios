# Start even more Containers!

To understand the lifecycle of containers, we can kick off another instance but this time we define the lifespan

`docker run -it hello-world sleep 5`{{execute}}

So what is going on here? 
It seems like the container is getting killed if it's not active anymore?

Just one more time but now detached:
`docker run -it hello-world sleep 120 && docker ps`{{execute}}


Let's start a container that executes something and doesn't stop

`docker run alexhiesch/clock`{{execute}}

Whoops!
Now we are inside of the container and stuck with an endless loop.



