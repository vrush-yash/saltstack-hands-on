# saltstack-hands-on

This is an example to deploy one saltstack master and two saltstack minions on docker.

Details:

vrushyash/saltmaster:v1 - docker image for saltmaster
vrushyash/saltminion:v1 - docker image for saltminion
docker-compose.yaml - Execute this file to deploy three docker containers, one master and two minion. This is a basic example, will keep on updating this example.

Commands:
In case, you download image from docker hub:

A]
1. Download images:
  a. docker pull vrushyash/saltmaster:v1
  b. docker pull vrushyash/saltminion:v1
2. Execute docker compose file:
  a. docker-compose up -d (execute this commands on same directory where you keep docker-compose.yaml file

B]
1. Create image on your workstation locally
  a. Clone this repository
  b. Goto path: ./saltmaster, and execute command: docker build -t <image name with tag> . (Example: docker build -t Roku/saltserver .)
  c. Goto path: ./saltminion, and execute command: docker build -t <image name with tag> . (Example: docker build -t Roku/saltminion .)
2. Execute docker compose: 
  a. docker-compose up -d (execute this commands on same directory where you keep docker-compose.yaml file

C]
1. Access containers:
  a. docker-compose ps - list containers deployed using compose file
  b. docker-compose exec saltmaster bash - to login on saltmaster
  c. docker-compose exec saltminion1 bash - to login on one of the minion
2. You can directly access containers with basic docker commands as well
  a. docker ps | grep salt
  b. docker exec -it <container name> /bin/bash
