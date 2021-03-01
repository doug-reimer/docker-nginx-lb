
## Individual Containers

The following steps show how to build and deploy the containers "manually".


### Build the containers
```bash
docker build -t web-01 ./web-01
docker build -t web-01 ./web-01
docker build -t lb-01 ./load_balancer
```

### Start first web server
```bash
# docker run -itd --network MyNetwork -p 8001:80 --name web-01 web-01
docker run -itd --network MyNetwork --name web-01 web-01
```

### Start second web server
```bash
# docker run -itd --network MyNetwork -p 8002:80 --name web-02 web-02
docker run -itd --network MyNetwork --name web-02 web-02
```

### Start the load balancer/proxy
```bash
docker run -itd --network MyNetwork -p 8000:80 --name lb-01 lb-01
```

## Use Docker Compose

Instead of using the above steps, we can use docker-compose to orchestrate the containers via the `docker-compose.yml`:

```bash
docker-compose up -d
```

```bash
docker-compose down
```
