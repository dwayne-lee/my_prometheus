
# Docker Swarm Monitoring

### Requirements:
### /etc/docker/daemon.json may need to contain the following:
```
{
  "metrics-addr" : "0.0.0.0:9323",
  "experimental" : true
}
```

### Create a secret to store the Grafana login password (change it after initial login)
docker secret create grafana_admin_pass grafana_admin_pass.txt

### Create a config for the prometheus.yml file
docker config create prometheus.yml prometheus.yml

### Deploy to Docker Swarm (use docker-compose.yml)
Run `docker-compose up -d`

### Fix perms on the Prometheus volume
chown nobody:nobody -R /var/lib/docker/volumes/prometheus_prometheus-data

### Verify
Navigate to http://<manager-ip>:9090/targets and make sure everything is "UP"

### Configure
1. Navigate to http://<manager-ip>:3000 and login
2. Add a "Prometheus" data source
3. Import the dashboard from docker_and_system.json file
4. Setup alerts as needed

### Teardown
Run `docker-compose down`


Please contact Dwayne Lee (dwaynelee@quickenloans.com) with any issues, suggestions.  Enjoy!

