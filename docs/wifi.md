# WiFi

| Setting          |       Main        | IoT |  Guest  |
| ---------------- | :---------------: | :-: | :-----: |
| Name             | Ministry of Magic |     | Muggles |
| Network          |        LAN        | IoT |  guest  |
| Broadcasting APs |        All        |     |   All   |

## Manual

| Setting                 | Notes                                                                        | Main | IoT | Guest |
| :---------------------- | ---------------------------------------------------------------------------- | :--: | --- | :---: |
| Private Pre-Shared Keys | PPSK requires the use of WPA2 security and only supports 2.4/5 Ghz networks. |  🔴  |     |  🔴   |
| Hotspot Portal          |                                                                              |  🔴  |     |  🟢   |

### Guest Hotspot

| Setting             | Notes                                             | Main | IoT | Guest |
| ------------------- | ------------------------------------------------- | :--: | --- | :---: |
| Guest Portal        | Requires guests to interactwith the guest portal. |  🔴  |     |  🟢   |
| Authentication Type |                                                   | n/a  |     | None  |

#### Network Isolation

|             Setting             | Notes                                                                                     | Main | IoT |                                                                     Guest                                                                      |
| :-----------------------------: | ----------------------------------------------------------------------------------------- | ---- | --- | :--------------------------------------------------------------------------------------------------------------------------------------------: |
|  Allowed Authorisation Access   | Allow guests to access specific hostnames or subnets whether or not they have authorized. |      |     |                                                                       -                                                                        |
| Restricted Authorisation Access | Restric guests from accessing specific hostnames or subnets after they have authorized.   |      |     | 10.0.0.0/8 (10.0.0.0 to 10.255.255.255)<br />172.16.0.0/12 (172.16.0.0 to 172.31.255.255)<br />192.168.0.0/16 (192.168.0.0 to 192.168.255.255) |

| Setting                         | Notes                                                                                                                                                                                         |                         Main                          | IoT |             Guest             |
| :------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------: | --- | :---------------------------: |
| Private Pre-Shared Keys         | PPSK requires the use of WPA2 security and only supports 2.4/5 Ghz networks.                                                                                                                  |                          🔴                           |     |              🔴               |
| Hotspot Portal                  |                                                                                                                                                                                               |                          🔴                           |     |              🟢               |
| WiFi Band                       | The 5 GHz band transmits data at faster speeds than the 2.4 GHz band, but may provide a smaller coverage area.                                                                                |                      2.4 + 5 GHz                      |     |             5 GHz             |
| Band Steering                   | Forces compatible clients to move to the 5GHz WiFi band to improve network perofmance.                                                                                                        |                          🔴                           |     |              n/a              |
| Hide WiFi Name                  |                                                                                                                                                                                               |                          🔴                           |     |              🔴               |
| Client Device Isolation         | Prevents wireless clients on the same AP from communicating with each other. This may inhibit the functionality of AirPlay, Chromecast, Sonos devices, screen mirroing and wireless printers. |                          🔴                           |     |              🟢               |
| Proxy ARP                       | Reduces airtime usage by allowing APs to "proxy" common broadcast frames as unicast. This can improve latency, but may cause connectivity issues in some networks.                            |                          🔴                           |     |              🔴               |
| BSS Transition                  | Improves client transitions between APs when they have a week signal. Clients that do not support this eature may experience connectivity issues.                                             |                          🟢                           |     |              🟢               |
| UAPSD                           | Ensures more efficient power consumption fo WiFi. VoIP and similar devices.                                                                                                                   |                          🟢                           |     |              🟢               |
| Fast Roaming                    | You will experience connectivity issues with devices that do not support the 802.11r WiFi standard.                                                                                           |                          🟢                           |     |              🟢               |
| WiFi Speed Limit                | Sets upload and download bandwidth limita for clients on this network.  If diasbled, default WiFi Speed Limit profile will be used.                                                           |                       Disabled                        |     |           Disabled            |
| Multicast Enhancment            | Converts multicast WiFi traffic to unicast, when possible.                                                                                                                                    |                          🔴                           |     |                               |
| Multicast and Broadcast Control | Only allow specific devices to send broadcast trafficon a WiFi network. Things likeproters, AirPlay, and Chromecast devices should be added to the exceptions.                                |                       Disabled                        |     |           Disabled            |
| 802.11 DTIM Period              | Delivery Traffic Indication Message. Misconfuring this setting may result in client disconnections. We receommend seeting this to "Auto".                                                     | Custom: 2.4GHz (2) 5 GHz (3)<br />[Default (1) + (3)] |     | Auto<br />[Default (1) + (3)] |
| Minimum Data Rate Control       | Clients incapable of meeting the minimum rates will experience connectivity issues.                                                                                                           |                         Auto                          |     |             Auto              |
| MAC Address Filter              | Allow and prohibitclients from joining a WiFi network based on their MAC address.                                                                                                             |                       Disabled                        |     |           Disabled            |
| RADIUS MAC Authentication       | Uses the MAC ID as credentials to pass traffic.                                                                                                                                               |                       Disabled                        |     |           Disabled            |

### Security

| Settings             | Notes                                                                                                                                  |     Main     |   IoT    |    Guest     |
| :------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | :----------: | :------: | :----------: |
| Security Protocol    | This is the authentication protocol used when clients connect to your WiFi SSID. We recommend WPA2 for the home or small office users. |     WPA2     |          |  WPA2/WPA3   |
| SAE Anti-clogging    |                                                                                                                                        |              |          |      5       |
| SAE Sync time        |                                                                                                                                        |              |          |      5       |
| PMF                  | Protected Management Frames enhance safety for WiFi connection.                                                                        |   Disabled   | Disabled |   Optional   |
| Group Rekey Interval | Sets how often connected device groups are assigned a new key.                                                                         |      🟢      |          |      🟢      |
| GTK Rekeying every   |                                                                                                                                        | 7200 seconds |          | 3600 seconds |

| Settings       | col2                                                           |   Main    |    IoT    |   Guest   |
| -------------- | -------------------------------------------------------------- | :-------: | :-------: | :-------: |
| WiFi Scheduler | Schedules times afor  WiFi network to be turned "on" or "off". | No Scedue | No Scedue | No Scedue |

# To Do

- [ ] Make Security Protocol be WPA2/WPA3 on Main network.
- [ ] Create a new WiFi network (say Hufflepuff) and move the few non-IoT devices off of Ministry of Magic to it. (This will be the new'Main' network)
  - [ ] Check the Firewall rules before activating
  - [ ] Acticate Band Steering
- [ ] Move Ministry of Magic Wifi to point to the the IoT network (from the current LAN network)
  - [ ] Check the Firewall rules before activating
  - [ ] Set to 2.4 GHz only
  - [ ] Turn off Band Steering
- [ ] Turn PMF on the (new) main network (Hufflepuff)
- [ ] Look to create a Management Network and move the network components on to it.
- [ ] Update this document!
