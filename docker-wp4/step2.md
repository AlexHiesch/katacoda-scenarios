# Start even more Containers!

To understand the lifecycle of containers, we can kick off another instance but this time we define the lifespan

`docker run -it alpine sleep 5`{{execute}}

So what is going on here? 
It seems like the container is getting killed if it's not active anymore?

Just one more time but now detached:
`docker run -d -it --name 20_sec_alive alpine sleep 20 && watch docker ps -a`{{execute}}

Check the stats
`docker top 20_sec_alive`{{execute interrupt}}

`docker stats`{{execute interrupt}}

Let's start a container that executes something and doesn't stop

`docker run alexhiesch/clock`{{execute}}

Whoops!
Now we are inside of the container and stuck with an endless loop.



