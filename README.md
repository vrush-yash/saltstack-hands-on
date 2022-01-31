# saltstack-hands-on

This is an example to deploy one saltstack master and two saltstack minions on docker.

Details:

vrushyash/saltmaster:v2 - docker image for saltmaster
vrushyash/saltminion:v2 - docker image for saltminion
docker-compose.yaml - Execute this file to build images and deploy three docker containers, one master and two minion. This is a basic example, will keep on updating this example.
  a. Inputs from user: 
	i. salt_repo_url - Provide URL to salt repo for respective version, example: "https://archive.repo.saltproject.io/yum/redhat/7/x86_64/archive/3000.3.repo", which is for salt version 3000.3. You can find such URL for saltstack website: https://repo.saltproject.io/ for newer versions of salt or https://archive.repo.saltproject.io for older versions of salt
  b. network name
  c. alias to containers
 
Commands:
In case, you download image from docker hub:

A]
1. Download images or build directly using docker-compose:
  i. Download image from docker repo:
    a. docker pull vrushyash/saltmaster:v2
    b. docker pull vrushyash/saltminion:v2
  ii. Build image locally using compose:
    a. Go to directory where you have compose file, then execute: docker-compose build
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
