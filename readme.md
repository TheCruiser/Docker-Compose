## A Simple MERN Stack Application

<<<<<<< Updated upstream
### Create a network for the docker containers
=======
Note - To run this project using ```docker compose```, follow the below steps.

Switch to the ```compose``` branch to learn the

1. Implementation of ```Dockerfile``` for ```client``` and ```server```.
2. Run the containers using ```Docker Compose```.

Run it local without Docker
Prerequisite

Install ```npm```

Start Server:
>>>>>>> Stashed changes
```
docker network create demo
```

### Build the client
```
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client
```
docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend
```

### Verify the client is running

Open your browser and type http://localhost:5173

### Run the mongodb container
```
docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest
```

### Build the server
```
cd mern/backend
docker build -t mern-backend .
```

### Run the server
```
docker run --name=backend --network=demo -d -p 5050:5050 mern-backend
```
### Using Docker Compose
```
docker compose up -d
```