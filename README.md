# Go Microservices

Mini project microservices with Golang

## π° Technologies π°

- Go
- Docker
- Kubernestes
- PostgreSQL
- Mongo
- RPC
- gRPC
- Rabbitmq
- Mailhog

## π° Architecture π°
 
 TBD

## π° How to build and run π°

### π³ Docker π³

#### Using Docker Compose

Deploy project with [Docker Compose](https://docs.docker.com/compose/)
#### Using automation script

**Using with Bash verion >= 4** *(To check Bash version, use: bash --version)*

1. Go to source code folder.
2. **βοΈIMPORTANT:** Update submodule ```git submodule update --init --recursive```
3. Grant permission ```chmod +x helper```
4. Run helper's help menu ```./helper help```
5. Happy deploying

![Clean, build images, and run containers (command ./helper clean build run mongo-ui)](./images/console-01.png)

![Front end](./images/front-end-01.png)

### π’ Kubernetes π’

TBD