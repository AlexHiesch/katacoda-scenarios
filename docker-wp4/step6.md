# Run multiple Containers at once with Docker Compose

You've reached the final exercise.

So far we have only tried out single containers. Real applications consists of ton of them that interact with each other. How do we do that with docker?

In this case we can explore a sample application that uses a flask container and a redis container managed by docker compose

Clone the application first
`git clone alexhiesch/trainingwheels`{{execute}}

`cd trainingwheels`{{execute}}

Understand the composition and the Dockerfile
`cat docker-compose.yml`{{execute}}

`cat www/Dockerfile`{{execute}}

`docker-compose up -d`{{execute}}

`docker-compose ps`{{execute}}

[Try it out here[(http://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com)

`docker-compose down`{{execute}}

`docker-compose down`{{execute}}

`docker system prune`{{execute}}

