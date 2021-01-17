# Analyze Images

How do those images look like?

Why is docker so fast all the time with spin up time?


`docker run --rm -it -v /var/run/docker.sock:/var/run/docker.sock wagoodman/dive:latest python`{{execute}}

Compare the different layers, their size and which files are modified in each layer