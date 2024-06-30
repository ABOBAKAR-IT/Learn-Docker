# Docker Compose
Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application's services. Then, with a single command, you create and start all the services from your configuration.
Compose work in all environments:production, staging, development, testing, as well as CI workflows.
Docker Desktop includes Docker Compose along with Docker Engine and Docker CLI which are Compose prerequisites.\n
Following are use Cases of Docker Compose:-
- Development environments
- Automated testing environments
- Single host deployments


## Docker Compose file 1
```yml
version: '3.8'
services:
  mongodb:
    image: mongo
    ports:
      - "8000:27017"
    volumes:
      - mongodbdata:/data/db
    networks:
        - my-network
    environment:
      DB_ENV: development
    container_name:mongodb
  server:
    build: 
        context: ./Backend-API
        dockerfile: Dockerfile
    volumes:
        - ./Backend-API:/app
    ports:
        - "3000:3000"
    depends_on:
        - mongodb
    networks:
        - my-network
    container_name: server
  react:
    stdin_open: true
    tty: true
    build: 
        context: ./Frontend-UI
        dockerfile: Dockerfile
    volumes:
        - ./Frontend-UI:/app
    ports:
        - "3001:3001"
    depends_on:
        - mongodb
        - server
    networks:
        - my-network
    container_name: react

volumes:
    mongodbdata:
networks:
    my-network:
    
```

