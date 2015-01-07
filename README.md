# dockerPlay

# build the image
docker build -t pkelly/angular-webapp .

# create a container
docker run -d -p 80 --name angular-app pkelly/angular-webapp nginx

# see if it's working
docker ps -a

# remove all containers
docker rm `docker ps -a -q`

# See the webapp running
curl $(boot2docker ip):49154
