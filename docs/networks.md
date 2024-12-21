# Networks

| Setting |      LAN       |      IoT       |     Guest      |
| ------- | :------------: | :------------: | :------------: |
| Router  | Office UDM Pro | Office UDM Pro | Office UDM Pro |

## IP6

| Setting             | Notes | LAN  | IoT  | Guest |
| ------------------- | ----- | ---- | ---- | ----- |
| IPv6 Interface Type |       | None | None | None  |

## IP4

### Gateway IP/Subnet

| Setting            | Notes                                                                        |      LAN       |      IoT       |     Guest      |
| :----------------- | ---------------------------------------------------------------------------- | :------------: | :------------: | :------------: |
| Auto-Scale Network | PPSK requires the use of WPA2 security and only supports 2.4/5 Ghz networks. |       🔴       |       🔴       |       🔴       |
| Host Address       |                                                                              |  192.168.1.1   | 192.168.107.1  | 192.168.199.1  |
| Netmask            |                                                                              | 24 (249 hosts) | 24 (249 hosts) | 24 (249 hosts) |

### Advanced

#### Manual

| Setting               | NotesNotes                                                                                                                                                                                                                                                                                                       | LAN | IoT | Guest |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | :-: | :---: |
| VLAN ID               | An ID used to differentiate new virtual Networks from your default network (VLAN 1)                                                                                                                                                                                                                              | (1) | 107 |  199  |
| Guest Network         | Isolates the network from other Virtal Networks not defined as Guest Networks using firewall rules on the UniFi Gateway. Guests on this network are able to communicate with each and access the internet. If the landing page is enabled in the Hotspot Manager. Guests are also redirected for authentication. | 🔴  | 🔴  |  🟢   |
| Isolate Network       | Isolates this network from all other Virtual Networks using firewall rules on the UniFi Gateway. Devices on this network are able to communicate with each other.                                                                                                                                                | 🔴  | 🔴  |   -   |
| Allow Internet Access | Allows devices on this network to access the internet.                                                                                                                                                                                                                                                           | 🟢  | 🟢  |  🟢   |
| ICMP Snooping         | Improves network bandwidth by only sending multicast traffic such as Airplay to the intended network devices. This may however increase multicast latency and drop any non-registered multicast traffic (such as PTPv2).                                                                                         | 🟢  | 🟢  |  🔴   |
| Multicast DNS         | Allows multicast traffic to transmit across multiple networks. We recommend this featurewhen using AirPlay or Chromecast.                                                                                                                                                                                        | 🟢  | 🟢  |  🔴   |

### DHCP

| Setting   | Notes | LAN         |     IoT     |    Guest    |
| :-------- | ----- | ----------- | :---------: | :---------: |
| DHCP Mode |       | DHCP Server | DHCP Server | DHCP Server |

#### DHCP Range

| Setting | Notes | LAN           |       IoT       | Guest           |
| ------- | ----- | ------------- | :-------------: | --------------- |
| Start   |       | 192.168.1.6   |  192.168.107.6  | 192.168.199.6   |
| Stop    |       | 192.168.1.254 | 192.168.107.254 | 192.168.199.254 |

#### DHCP Name Server

| Setting     | Notes | LAN    |  IoT   | Guest |
| :---------- | ----- | ------ | :----: | :---: |
| Auto/Manual |       | Manual | Manual | Auto  |

| Setting      | Notes |      LAN      |      IoT      | Guest |
| :----------- | ----- | :-----------: | :-----------: | :---: |
| DNS Server 1 |       | 192.168.1.235 | 192.168.1.235 |   -   |
| DNS Server 2 |       |  192.168.1.1  |  192.168.1.1  |   -   |
| DNS Server 3 |       |       -       |       -       |   -   |
| DNS Server 4 |       |       -       |       -       |   -   |

|     Setting     | Notes | LAN                   | IoT                     |         Guest         |
| :-------------: | ----- | --------------------- | ----------------------- | :-------------------: |
| DHCP Lease Time |       | 86400 Seconds (1 day) | 10800 Seconds (3 hours) | 86400 Seconds (1 day) |

| Setting         | Notes | LAN  | IoT  | Guest |
| :-------------- | ----- | ---- | :--: | :---: |
| DHCP Gateway IP |       | Auto | Auto | Auto  |

| Setting            | Notes | LAN | IoT | Guest |
| :----------------- | ----- | :-: | :-: | :---: |
| DHCP UniFi Console |       |  -  |  -  |   -   |

| Setting       | Notes                                                                | Main | IoT | Guest |
| :------------ | -------------------------------------------------------------------- | :--: | :-: | :---: |
| DHCP Guarding | Protects against rogue DHCP servers by only permitting trusted ones. |  🟢  | 🟢  |  🟢   |

| Setting              | Notes |     LAN     |      IoT      |     Guest     |
| :------------------- | ----- | :---------: | :-----------: | :-----------: |
| DNS Trusted Server 1 |       | 192.168.1.1 | 192.168.107.1 | 192.168.199.1 |
| DNS Trusted Server 2 |       |      -      |       -       |       -       |
| DNS Trusted Server 3 |       |      -      |       -       |       -       |

| Setting           | Notes                                                                                                                         | LAN | IoT | Guest |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------- | :-: | :-: | :---: |
| DHCP NTP Server   | The DHCP Network Time Orotocol (NTP) server must have a vaid IP address. This cannot be a fully qulaified domain name (FQDN). | 🔴  | 🔴  |  🔴   |
| DHCP Network Boot | Boot a device over the network by specifying the server IP address and filename (PXE).                                        | 🔴  | 🔴  |  🔴   |
| DHCP Time Offset  | The time offseet in seconds, of clients on this network from Coordinated Universal Time (UTC).                                | 🔴  | 🔴  |  🔴   |
| DHCP WPAD URL     |                                                                                                                               |  -  |  -  |   -   |
| DHCP TFTP Server  |                                                                                                                               |  -  |  -  |   -   |
