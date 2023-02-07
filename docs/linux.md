# Linux - Using Tailscale app with Headscale

## Requirments

1. Tailscale is already installed
2. Tailscale app is currently running

---

## Installation

Attaching the Tailscale client to a Headscale server

### Step 1 - Generate an Auth key (headscale docker host)

Run the following command for each mac to connect to your namespace

```bash
# Older version
docker exec headscale headscale --namespace <TAILSCALE_NAMESPACE> preauthkeys create --reusable --expiration 24h
# Newer version
docker exec headscale headscale --user <TAILSCALE_NAMESPACE> preauthkeys create --reusable --expiration 24h
```

### Step 2 - Log linux client into Headscale server (terminal)

Run the following command in a terminal session

```bash
tailscale up --login-server <URL_OF_HEADSCALE:PORT> --authkey  <AUTHKEY_GENERATED_ON_HEADCSCALE_SERVER> --force-reauth
# example
tailscale up --login-server http://docker.za.cloudlet.cloud:8080 --authkey 23a6cd86968c00a79a220e48100efa144f7e7868c729dba7 --force-reauth
```

## Removal

Removing the custom Headscale server from the Tailscale client

### Step 1 - Log out

```bash
tailscale logout
```

### Step 2 - Reset & Log In

```bash
tailscale up --reset
```
