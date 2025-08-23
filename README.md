This repo is for task one of secure dev ops, it's mean to create containers using docker for the mern-app Project 2.

Instructions
1. Create an EC2 Instance the same as Task A
2. Add Inbound security groups, for port 80 (http), 443 (https), and 8081 TCP custom
3. Install docker in the new instance same as Task C
4. git clone this repo then make the Docker-Task-One the cd
5. Add certs using this command in command line: mkdir -p nginx/certs
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout nginx/certs/self.key -out nginx/certs/self.crt \
  -subj "/C=US/ST=State/L=City/O=Org/OU=Dev/CN=localhost"
6. build docker by doing, "docker compose build" then "docker compose up -d"
