# How to customize Containers to your needs with Dockerfile

So how can I now use now figlet from now on with any new container?


a) Use one where it is already preinstalled. 
This could be a bloated distrubution with a lot of tools preinstalled. 
Or search the docker hub for an image that mentions the desired package

[Docker Hub](https://hub.docker.com/)

`docker search figlet`{{execute}}

Please be very careful in doing so.
The Docker Hub Ecosystem is larger than the Android marketplace and according to recent studies, more than half of the images there are malicious or potentially harmful.

b) Rather create your own dedicated container definition with Dockerfile

Create a new empty file
`touch Dockerfile`{{execute}}

`Dockerfile`{{open}}

Insert the following definition into the Dockerfile

`FROM ubuntu
# shell syntax with string
RUN apt-get update
# exec syntax with json list
RUN ["apt-get", "install", "-y","figlet"]
CMD exec figlet -f script Welcome to the figlet image based on ubuntu`{{copy}}


Build an image according to the Dockerfile in the current working dir
`docker build -t figlet .`{{execute}}

Start the image
`docker run -ti figlet`{{execute}}

Try out figlet
`figlet it works`{{execute}}
