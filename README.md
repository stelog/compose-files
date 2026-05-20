# Container

Docker Compose configurations for a self-hosted home server stack. Each service lives in its own subdirectory with an independent `docker-compose.yml` and a local `.env` file that holds secrets and machine-specific values.

## Services

| Service | Description |
|---|---|
| autoheal | Restarts containers that fail their health check |
| ddclient | Dynamic DNS client — keeps DDNS records in sync with the current public IP |
| deconz | Zigbee coordinator gateway (ConBee III) with REST/WebSocket API |
| diun | Docker Image Update Notifier — watches running containers for new upstream images |
| heimdall | Dashboard for self-hosted services |
| homeassist | Home Assistant home automation platform, bundled with Matter Server |
| homebridge | Apple HomeKit bridge for devices without native HomeKit support |
| jellyfin | Media server for movies, series, documentaries and anime |
| pi-hole6 | Network-wide DNS ad blocker (Pi-hole v6) |
| portainer | Web UI for managing Docker containers, stacks and volumes |
| scrutiny | S.M.A.R.T. hard drive health monitoring with InfluxDB backend |
| smokeping | Network latency and packet loss monitoring |
| speedtest-tracker | Scheduled internet speed tests with history |

## Secrets and configuration

All sensitive values (passwords, API keys, tokens) are stored in a per-service `.env` file that is excluded from version control via the root `.gitignore`. Only `docker-compose.yml` files and safe example/template files are committed.

When setting up on a new host, create a `.env` file in each service directory before starting the stack. Refer to the comments inside each `docker-compose.yml` for the required variables.

## Usage

```sh
cd <service>
docker compose up -d
```
