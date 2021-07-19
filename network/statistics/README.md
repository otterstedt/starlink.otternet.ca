# Monitoring & Statistics
I have started to monitor the Starlink WAN to see how it works over time.

## Monitoring

### Dishy API

#### starlink-gprc-tools

Python scripts to provide time series data to InfluxDB

I have it setup as a SystemD service to periodically collect metrics from the API.

- [Docker Image](https://hub.docker.com/r/neurocis/starlink-grpc-tools/)
- [Github repo](https://github.com/sparky8512/starlink-grpc-tools)

Service file
```
[Unit]
Description=Starlinkstats Docker
Requires=docker.service
After=docker.service influxd.service

[Service]
ExecStart=/usr/bin/docker run --rm --name='starlink-grpc-tools' -e INFLUXDB_HOST=localhost     -e INFLUXDB_PORT=8086     -e INFLUXDB_DB=starlinkstats     --net=host neurocis/starlink-grpc-tools dish_grpc_influx.py -v status alert_detail
User=otterstedt
Group=docker
Environment=PATH=/bin:/usr/bin:/usr/local/bin:$PATH
WorkingDirectory=/home/otterstedt
TimeoutSec=60
RestartSec=1
Restart=always

[Install]
WantedBy=multi-user.target
```
The docker command starts the container which executes one round of data collection from the API then the container exits. By using 
```
Restart=always
RestartSec=1
```
I am able to collect data continuously without the need for scheduled cronjobs etc.

## Visualization

### Grafana

Grafana dashboards are used to visualize the metrics from the InfluxDB.

I used the [Starlink dashboard](https://github.com/sparky8512/starlink-grpc-tools/blob/main/GrafanaDashboard%20-%20Starlink%20Statistics.json) provided by [sparky8512](https://github.com/sparky8512) as a starting point.

#### My Dashboards 
- [Public Starlink Statistics Dashboard](https://grafana.otternet.ca/d/ymkHwLaMz/)

```
Note: The server hosting the dashboard might occasionally be unavailable 
```