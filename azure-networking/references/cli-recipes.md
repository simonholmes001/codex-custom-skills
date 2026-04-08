# Azure CLI Recipes for Networking

Run `az login` and set context first:

```bash
az account set --subscription "<subscription-id-or-name>"
```

## Show effective routes on a NIC

```bash
az network nic show-effective-route-table \
  --resource-group <rg> \
  --name <nic-name> \
  -o table
```

## Show effective NSG rules on a NIC

```bash
az network nic list-effective-nsg \
  --resource-group <rg> \
  --name <nic-name> \
  -o json
```

## List NSG rules ordered by priority

```bash
az network nsg rule list \
  --resource-group <rg> \
  --nsg-name <nsg-name> \
  --query "sort_by(@,&priority)[].{name:name,priority:priority,access:access,direction:direction,src:sourceAddressPrefix,dst:destinationAddressPrefix,port:destinationPortRange}" \
  -o table
```

## Check VNet peering states

```bash
az network vnet peering list \
  --resource-group <rg> \
  --vnet-name <vnet-name> \
  --query "[].{name:name,state:peeringState,allowForwardedTraffic:allowForwardedTraffic,allowGatewayTransit:allowGatewayTransit,useRemoteGateways:useRemoteGateways}" \
  -o table
```

## Check private endpoint and DNS zone links

```bash
az network private-endpoint list -g <rg> -o table
az network private-dns link vnet list \
  --resource-group <dns-rg> \
  --zone-name <private-zone-name> \
  -o table
```

## Check VPN gateway connections and BGP peers

```bash
az network vpn-connection list -g <rg> -o table
az network vnet-gateway list-bgp-peer-status \
  --resource-group <rg> \
  --name <vnet-gateway-name> \
  -o table
```

## Run Connection Troubleshoot (Network Watcher)

```bash
az network watcher test-connectivity \
  --resource-group <network-watcher-rg> \
  --source-resource <source-resource-id> \
  --dest-address <fqdn-or-ip> \
  --dest-port <port> \
  -o json
```
