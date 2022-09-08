# Headscale

An open Source Tailscale server alternative

This project space to host `headscale`. An open source alternative to tailscale.

# Source project

[Master Headscale Project](https://github.com/juanfont/headscale)

[Official How To - Docker Guide](https://github.com/juanfont/headscale/blob/main/docs/running-headscale-container.md)

# How to use this project

## Pull latest version

```bash
git pull ssh://git@devops.iohub.cloud:10022/richard/oxide-tailscale-server.git
```

## Configure Optional settings

### DB username & password

Edit these settings in the following two file (to be the same)

```bash
./config/config.yaml
./docker-compose.yml
```

## Update file permissions

```bash
sudo chown [docker-user]:[docker-group] postgres-data
sudo rm -rf postgres-data/.gitignore
```

## Start up services

```bash
docker-compose up -d
```

## Check that services are online

```bash
curl http://localhost:9090/metrics
```

# Tailscale Client Usage

1. [Linux Guide](https://devops.iohub.cloud/richard/oxide-tailscale-server/-/blob/main/docs/linux.md)
2. [MacOS Guide](https://devops.iohub.cloud/richard/oxide-tailscale-server/-/blob/main/docs/macos.md)
3. *ToDo*
4. Follow the official guide for registration & usage

[Official Headscale Guide](https://github.com/juanfont/headscale/blob/main/docs/running-headscale-container.md#register-a-machine-normal-login)
