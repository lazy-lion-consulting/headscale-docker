# Linux - Using Tailscale app with Headscale

## Requirments

1. Tailscale is already installed
2. Tailscale app is currently running

## Step 1 - Generate an Auth key (headscale docker host)
Run the following command for each mac to connect to your namespace
```bash
docker exec headscale headscale --namespace <TAILSCALE_NAMESPACE> preauthkeys create --reusable --expiration 24h
```

## Step 2 - Log linux client into Headscale server (terminal)

Run the following command in a terminal session
```bash
tailscale up --login-server http://docker.za.cloudlet.cloud:8080 --authkey fe568698cbbe9dce27e8f31252314ada93e8f60221c02d3e --force-reauth
# example
tailscale up --login-server http://docker.za.cloudlet.cloud:8080 --authkey fe568698cbbe9dce27e8f31252314ada93e8f60221c02d3e --force-reauth
```
