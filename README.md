
# Docker Swarm Monitoring

### Requirements:
### /etc/docker/daemon.json must contain the following:
```
{
  "metrics-addr" : "0.0.0.0:9323",
  "experimental" : true
}
```

### Deploy to single Docker node (use docker-compose.yml)
Run `docker-compose up -d`

### Or.....

### Deploy to a Docker Swarm (use docker-stack.yml)
Run `docker stack deploy prometheus --compose-file docker-stack.yml`

### Verify
Navigate to http://localhost:9090/targets and make sure everything is "UP"

### Configure
1. Navigate to http://localhost:3000 and login
2. Add a "Prometheus" data source
3. Import the dashboard from data/grafana/dashboards
4. Setup alerts as needed

### Teardown
Run `docker-compose down`

### or....

Run `docker stack rm prometheus`


Please contact Dwayne Lee (dwaynelee@quickenloans.com) with any issues, suggestions.  Enjoy!

