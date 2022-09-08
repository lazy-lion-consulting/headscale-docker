# MacOS - Using Tailscale app with Headscale

## Requirments

1. Tailscale is already installed
2. Tailscale app is currently closed

---

## Installation

### Step 1 - Download profile (web browser)

Download a custom profile from the headscale server

1. Go to *URL_OF_HEADSCALE:PORT*/apple
    e.g. [http://docker.za.cloudlet.cloud:8080/apple](http://docker.za.cloudlet.cloud:8080/apple)
2. Click the profile download hyperlink and save to a known location

### Step 2 - Install profile (macos)

Install the custom profile for the headscale server

1. Open the file from finder (a notification should appear about the next step)
2. Go to `System Preferences`->`Profiles` and you should see it there
3. Click the `Install` button

### Step 3 - Start Tailscale (macos)

Start the official Tailscale app
`CMD+Spacebar` and type `Tailscale`, then hit enter

### Step 4 - Generate an Auth key (headscale docker host)

Run the following command for each mac to connect to your namespace

```bash
docker exec headscale headscale --namespace <TAILSCALE_NAMESPACE> preauthkeys create --reusable --expiration 24h
```

### Step 5 - Log Mac into Headscale server (terminal)

Run the following command in a terminal session

```bash
/Applications/Tailscale.app/Contents/MacOS/Tailscale up -login-server <URL_OF_HEADSCALE:PORT> --accept-routes --authkey <AUTHKEY_GENERATED_ON_HEADCSCALE_SERVER>
# example
/Applications/Tailscale.app/Contents/MacOS/Tailscale up -login-server http://docker.za.cloudlet.cloud:8080 --accept-routes --authkey 23a6cd86968c00a79a220e48100efa144f7e7868c729dba7
```

## Removal

### Step 1 - ToDo
