# Metrics Server for Eth-Runner

## Prerequisites
* Docker

## Start metrics server
The `start_metrics_server.sh` will start the InfluxDB + Grafana + Telegraf(StatsD) docker container called `eth-metrics-influx`.

## Setup Grafana
Go to `http://<miner-ip-address>:3003` (substitute `<miner-ip-address>` with the IP of your Miner machine, since the Docker container is running in there. Otherwise, change it to where Grafana is being hosted by `start_metrics_server.sh`)and use the following login for Grafana:
```
username: root
password: root
```
The InfluxDB datasource is not initially setup within Grafana. So, navigate to create a new datasource, select InfluxDB as the type and then use the database name `ethmetrics`, no login required.

### Creating dashboards
The dashboard is initially not setup as well, so that's a manual effort of creating one's own custom dashboards, or.... use the `sample_grafana_metrics_dashboard.json` provided and import into Grafana to use it as a starting point for your own dashboard.

Enjoy!
