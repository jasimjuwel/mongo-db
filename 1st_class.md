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


### Docker compose command

- docker-compose up -d
- docker ps
- docker volume ls

### Docker bash terminal

- sudo docker exec -it mongodb_mongodb_container_1 bash
- mongo admin -u root -p rootpassword

### Docker database command

- show databases
- use food
#### insert data :

    db.fruits.insertMany([ {name: "apple", origin: "usa", price: 5}, {name: "orange", origin: "italy", price: 3}, {name: "mango", origin: "malaysia", price: 3} ])


- show collections
- db.fruits.find().pretty()
