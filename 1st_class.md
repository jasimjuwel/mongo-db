

## 1st Class Assignment

   
### docker-compose.yml

#

version: '3'
services:
  mongodb_container:
    image: mongo:latest
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: rootpassword
    ports:
      - 27017:27017
    volumes:
      - mongodb_data_container:/data/db

volumes:
  mongodb_data_container:


### Steps

- docker-compose up -d
- docker ps
- docker volume ls

- sudo docker exec -it mongodb_mongodb_container_1 bash
- mongo admin -u root -p rootpassword

- show databases
- use food
- show collections
- db.fruits.find().pretty()
