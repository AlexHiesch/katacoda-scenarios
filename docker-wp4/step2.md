# Start even more Containers!

To understand the lifecycle of containers, we can kick off another instance but this time we define the lifespan

`docker run -it alpine sleep 5`{{execute}}

So what is going on here? 
It seems like the container is getting killed if it's not active anymore?

`docker ps -n 1`{{execute}}

Just one more time but now detached:
`docker run -rm -d -it --name 20_sec_alive alpine sleep 20 && watch docker ps -a`{{execute}}

Check the stats:

`docker top 20_sec_alive`{{execute interrupt}}

`docker stats`{{execute interrupt}}

Let's start a container that executes something and doesn't stop

`docker run alexhiesch/clock`{{execute interrupt}}

Whoops!
Now we are inside of the container and stuck with an endless loop.

Stop it:
`^C`{{execute ctrl-seq}}

Run it again, but this time in the background:
`docker run -rm --name clock -d alexhiesch/clock`{{execute interrupt}}

Read the logs: 
`docker logs clock `{{execute interrupt}}

Stream the logs of the recent entry:
`docker logs -t --tail 1 -f clock`{{execute interrupt}}

Stop it:
`^C`{{execute ctrl-seq}}

What if we run multiple instances at once? How much disk space will it use?

`docker run -rm --name clock2 -d alexhiesch/clock && docker run -rm --name clock3 -d alexhiesch/clock && docker run -rm --name clock4 -d alexhiesch/clock && docker run -rm --name clock5 -d alexhiesch/clock && docker system df -v && docker ps -s`{{execute interrupt}}

