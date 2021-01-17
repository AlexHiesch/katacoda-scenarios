# Ephemeral - what does that mean?

Use Containers they say.
They are immutable. 
But what does this really mean?

`hostname`{{execute}}

`docker run -it --name my_server ubuntu sh`{{execute}}

`hostname`{{execute}}

It seems like we are now inside of the container

`-i` tells Docker to connect us to the container's stdin.

`-t` tells Docker that we want a pseudo-terminal.

Let's do some ASCII Arts with figlet:
`figlet`{{execute}}

hmm, guess we have to install it first:
`apt-get update && apt-get install figlet`{{execute}}

`figlet it just works`{{execute}}

`figlet -f script just one more time`{{execute}}

Stop it:
`exit`{{execute}}

Does this work again?

`docker run -it --name my_second_server ubuntu sh`{{execute}}

`figlet`{{execute}}

Nope. Bad luck.
Or maybe that's the actual container Workflow. 

Always start with a fresh image! 
(Even though you could start a stopped one and resume the activities)

Treat containers like cattle, not like pets.

`exit`{{execute}}
