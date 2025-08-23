This repo is for task one of secure dev ops, it's mean to create containers using docker for the mern-app Project 2. Kubernetes has not been added yet

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


Using the app
1. Frontend: open https://PUBLIC_IP/ in a new browser, ignore the security warning, then play around (add data into database)
2. Api: in the command line in the instance put: curl -k -X POST https://PUBLIC_IP/api/record/add -H "Content-Type: application/json" -d '{"name":"ApiUser","position":"Engineer","level":"Senior"}'
3. Mongo express: visit: http://PUBLIC_IP:8081/ the login is admin and pass. Then play around, add records
4. Whilst doing all the above switch between the frontend and mongo express and check that they're updating correspondingly when new data is added/deleted/updated
