
# Docker Swarm Monitoring

### Requirements:
### /etc/docker/daemon.json must contain the following:
{
  "metrics-addr" : "127.0.0.1:9323",
  "experimental" : true
}

### Deploy to single Docker node (use docker-compose.yml)
1. Run `docker-compose up -d`

### Or.....

### Deploy to a Docker Swarm (use docker-stack.yml)
1. Run `docker stack deploy prometheus --compose-file docker-stack.yml`

### Verify
Navigate to http://localhost:9090/targets and make sure everything is "UP"

### Configure
Navigate to http://localhost:3000 and login
Add a "Prometheus" data source
Import the dashboard from data/grafana/dashboards
Setup alerts as needed

### Teardown
1. Run `docker-compose down`

### or....

1. Run `docker stack rm prometheus`

Please contact Dwayne Lee (dwaynelee@quickenloans.com) with any issues, suggestions.  Enjoy!

