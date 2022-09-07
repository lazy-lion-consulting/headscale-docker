# Headscale

An open Source Tailscale server alternative

This project space to host `headscale`. An open source alternative to tailscale.

# Source project

[headscale_readme](https://github.com/juanfont/headscale/blob/main/docs/running-headscale-container.md)

# Usage

## Get the latest build

```bash
git pull ssh://git@devops.iohub.cloud:10022/richard/oxide-tailscale-server.git
```

## Options

### DB username & password

Edit these settings in the following two file (to be the same)

```bash
./config/config.yaml
./docker-compose.yml
```

## Update permissions

```bash
sudo chown [docker-user]:[docker-group] postgres-data
sudo rm -rf postgres-data/.gitignore
```

## Deploy

```bash
docker-compose up -d
```
