# Monitoring

Grafana + InfluxDB + Telegraf packed in docker compose.

## Run with

```
docker-compose start
```

## Setup

In `/etc/hosts`

```
<docker-machine ip> docker.local
```

## URLs and Ports

- InfluxDB admin interface: `http://docker.local:8083`
- Grafana interface: `http://docker.local:3000/` (user: admin, password: admin)
- StatsD: running on default port `8125`

# Test metric

```sh
echo "test,region=us-west,env=dev:10|c" | nc -C -w 1 -u docker.local 8125
```
