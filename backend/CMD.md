# CMD 1
docker build -f Dockerfile -t node-api:v2 .
docker run -it -d -p 49160:3001 --name node-api  node-api:v2
docker run -itd -e mongoUri=mongodb://admin:admin@mongo-container.demo-network:27017/admin -p 49160:3001 --name nodejs-demo-1  node-api:apline
mongo-container.demo-network => <container_name>.<network>
cd docker-compose
docker compose up -d
docker ps
docker network create --driver=bridge demo-network
docker network connect demo-network mongo-container
docker network connect demo-network nodejs-demo-1
docker  inspect demo-network
------
docker run -itd --network=demo-network -e mongoUri=mongodb://admin:admin@mongo-container.demo-network:27017/admin -p 49160:3000 --name nodejs-demo-1  node-api:apline