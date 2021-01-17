# Analyze Images

How do those images look like?

Why is docker so fast all the time with spin up time?

`docker run --rm -it -v /var/run/docker.sock:/var/run/docker.sock wagoodman/dive:latest figlet`{{execute}}

Stop it:
`^C`{{execute ctrl-seq}}


Compare the different layers, their size and which files are modified in each layer

BONUS: 
Check the bloated image of python. Isn't it amazing how much stuff is included beyond python?

`docker run --rm -it -v /var/run/docker.sock:/var/run/docker.sock wagoodman/dive:latest python`{{execute}}

Stop it:
`^C`{{execute ctrl-seq}}