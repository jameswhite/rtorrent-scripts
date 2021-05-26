#### Usage
```
docker-compose up --build --force-recreate --remove-orphans

```

#### Follow along with:
```
while [ 1 ]; do clear;mosquitto_sub -h 127.0.0.1 -p 1883 -t '#'; sleep 1; done

```
