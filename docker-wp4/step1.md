# The starting: Hello World!

Let's see if docker is installed at all
`docker`{{execute}}

And what kind of version we use here:

`docker version`{{execute}}

Does it also work properly?
Let's check it out start our first container:

`docker run hello-world`{{execute}}

Let's check if it's still running:

`docker ps`{{execute}}

Empty??? Why's that?

Should we maybe check all runs independently of their status?

`docker ps -s -a`{{execute}}

