# Headscale Configuration & Options

> IPv4 addresses are (by default) going to be provided in the 100.64.0.0/24 range.
> Inter-node IPv6 addresses will work (regardless of the IPv6 support outside of the tunnel)

## Namespace Management
Managing namespaces (logical groupings of devices that are able to communicate)
```bash
# Create a namespace
docker exec headscale headscale namespaces create [NAMESPACE]

# List all namespaces
docker exec headscale headscale namespaces list

# Rename a namespace
docker exec headscale headscale namespaces rename [OLD_NAME] [NEW_NAME]

# Delete a namespace
docker exec headscale headscale namespaces create [NAMESPACE]
```

## Node management
Managing nodes (devices that are connected to the namespace)
```bash
# Register node to namespace
docker exec headscale headscale --namespace [NAMESPACE] preauthkeys create --reusable --expiration 24h
>> Returns a key to be supplied to Tailscale app *See linux tailascale client guide

# List all nodes
docker exec headscale headscale nodes list

# Rename a node
docker-compose exec headscale headscale nodes rename [NEW_NAME] -i [NODE_ID]

# Delete a node
docker-compose exec headscale headscale nodes delete -i [NODE_ID]
```

*This is not an exhaustive list. Please see the help for further options*

## Help

```bash
# More info can be found with
docker-compose exec headscale headscale --help
```
