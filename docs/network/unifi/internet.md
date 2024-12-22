# Internet setup

## Package

EE Full Fibre Max

### Capabilities

- Download: 900 Mbps
- Upload: 110 Mbps

### Unifi Setup

#### EE/BT ISP (WAN1)

| Setting     |                      |
| :---------- | -------------------- |
| Name        | EE/BT ISP (WAN1)     |
| Host Device | Office UDM Pro       |
| Interface   | Port 9 (GE "Port 9") |

##### Expected ISP Speeds

| Setting  |         |
| -------- | ------- |
| Download | 900Mbps |
| Upload   | 110Mbps |

##### Advanced

###### Manual

| Setting           | Notes                                                                                                                                       |     |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | :-: |
| Use VLAN          | Most ISPs do not use VLAN tagging for incoming internet. If you are unsure, we recommend verifying with your service provider.              | 🔴  |
| MAC Address Clone | Copies the MAC address of an ISP-locked device to your UniFi Gateway to enable inernet connectivity.                                        | 🔴  |
| Smart Queues      | Prioritizes traffic and reduces delays when the router's bandwidth becomesoverloaded. Not recommended for connections faster than 300 Mbps. | 🔴  |
| IPTV Streaming    | Forwards IPTV streams received from the service provider to a set-top box or smart TV connected to the local network.                       | 🟢  |

###### IPTV Streaming

| Setting         | IoT | LAN | guest |
| :-------------- | :-: | :-: | :---: |
| Viewing Network | 🟢  | 🔴  |  🔴   |

| Setting |     |
| ------- | --- |
|         |     |
|         |     |

#### Secondary (WAN2)
