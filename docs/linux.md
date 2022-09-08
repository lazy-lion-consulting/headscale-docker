# Linux - Using Tailscale app with Headscale

## Requirments

1. Tailscale is already installed
2. Tailscale app is currently running

---

## Installation

### Step 1 - Generate an Auth key (headscale docker host)

Run the following command for each mac to connect to your namespace

```bash
docker exec headscale headscale --namespace <TAILSCALE_NAMESPACE> preauthkeys create --reusable --expiration 24h
```

### Step 2 - Log linux client into Headscale server (terminal)

Run the following command in a terminal session

```bash
tailscale up --login-server <URL_OF_HEADSCALE:PORT> --authkey  <AUTHKEY_GENERATED_ON_HEADCSCALE_SERVER> --force-reauth
# example
tailscale up --login-server http://docker.za.cloudlet.cloud:8080 --authkey 23a6cd86968c00a79a220e48100efa144f7e7868c729dba7 --force-reauth
```

## Removal

## Step 1
