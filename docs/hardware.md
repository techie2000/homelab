# Hardware

- The kit will be hosted in the home office which is a shared space and so in terms of noise and heat, has to pass the GF test (and to some extent, aesthetics) 😜
- If CEPH is to be used for HA in the cluster, a separate 10gig network is preferred. Potentially use the 40gig offered by Thunderbolt 4 to service that requirement, and use a dedicated 10gig NIC for everything else.
  - Note, I don't have enough 10gig ports on the switch to use it on day 1.... network upgrade to follow 😃

## NAS / Fileserver

| Component   | Options                 | Unit Price | Units | Cost  | Source | Notes                                                                                                   |
| ----------- | ----------------------- | ---------- | ----- | ----- | ------ | ------------------------------------------------------------------------------------------------------- |
| Case        | XPC-4400 4u 400mm E-ATX | 119        | 1     | 119   | [xcase.co.uk](https://www.xcase.co.uk/products/xpc-4400-4u-400mm-e-atx)  |   |
| Case        | XPC-340 3u 400mm ATX    |  95        | 1     |  95   | [xcase.co.uk](https://www.xcase.co.uk/products/xpc-340-3u-400mm-atx-rackmount-chassis) |   |
| Case        | 2U IPC 2U-2404L         | 120        | 1     | 120   | [scan.co.uk](https://www.scan.co.uk/products/2u-ipc-2u-2404s-40cm-storage-server-case-micro-atx-supports-4x-35-25-hdd-3x-40mm-fans-2x-usb30-w-o-p) | Mini ITX or µATX, 8xhot swappable bays (SFF-8087), 3x 40mm fan, max motherboard size: 244mm x 244mm, max height CPU cooler: 32/65mm |
| Case        | Codegen 4U600V2         | 120        | 1     | 120   | [scan.co.uk](https://www.scan.co.uk/products/codegen-4u600v2-4u-rackmount-v2-600mm-deep-butterfly-lock-includes-2-x-80mm-and-2-x-120mm-fans-atx-m) | ATX, 8 x 3.5" Internal + 3 x 5.25" External, 2 x 120mm + 2 x 80mm fans, max height CPU cooler: 139 mm |
| Case        | 4U IPC 4U-44            | 155        | 1     | 155   | [scan.co.uk](https://www.scan.co.uk/products/4u-ipc-4u-4408-storage-server-case-w-o-psu-supports-8x-35-25-hdd-2x-80mm-fans-2x-usb-30) | eATX, 8xhot swappable bays (2xSFF-8087), 2x 80mm rear fans, max motherboard size: 305mm x 345mm, max height CPU cooler: 80mm/155mm |
| Motherboard |                         |            |       |       |        |                                                                                                         |
| CPU         |                         |            |       |       |        | Does not need to be that powerful. This build will be IO-bound rather than CPU-bound. No onboard GPU required. |
| CPU Cooler  |                         |            |       |       |        | Will need to be low height if a 2U chassis is used                                                      |
| Memory      |                         |            |       |       |        | Does not need masses of memory, nor especially fast memory                                              |
| SSD         |                         |            |       |       |        | Something small as an OS/boot disk                                                                      |
| NVME        |                         |            |       |       |        | May not need any at all. At most, something small as an OS/boot disk                                    |
| HHD         |                         |            |       |       |        | Will primarily be re-using existing disks from various small servers I have built. Prices quoted are what it would be if building new. |
| NIC         |                         |            |       |       |        | Motherboard will likely come with a single 1/2.5gig NIC. Look to use that as a management interface only. Look for 2x10gig NIC that the file transfers will use. |
| GPU         |                         |            |       |       |        | Not required. Will be headerless.                                                                       |
| PSU         |                         |            |       |       |        | Doesn't have to be that powerful given the components. More power if running disks in the case rather than external DAS/JBOD |
| Total       |                         |            |       |       |        |                                                                                                         |

Case considerations: Consider 2-4U depending on whether hosting HBA only, or hot-swappable storage built-in.
## Hypervisor

| Component   | Options | Unit Price | Units | Cost  | Source | Notes                                                                                                   |
| ----------- | ------- | ---------- | ----- | ----- | ------ | ------------------------------------------------------------------------------------------------------- |
| Case        |         |            |       |       |        | Rack-mountable. Consider 2-4U. The primary consideration is cooling and noise.                          |
| Motherboard |         |            |       |       |        | Looking to host AMD4, 4 memory slots, 2 thunderbolt ports, and an additional 10gig NIC.                 |
| CPU         |         |            |       |       |        | 8 cores minimum, target 16. Preference to low TDP (65W target, 105W max). Consider onboard GPU.         |
| CPU Cooler  |         |            |       |       |        | Will need to be low height if a 2U chassis is used                                                      |
| Memory      |         |            |       |       |        | Will start with 64gig (2x32) and increase to 128gig as required. 3200 speed in mind                     |
| SSD         |         |            |       |       |        | Something small as an OS/boot disk                                                                      |
| NVME        |         |            |       |       |        | Will host VM's. 1TB minimum, probably 2TB (more ideal but too expensive).                               |
| HHD         |         |            |       |       |        | May not need any at all. At most, something to store local backups. Look at 5-10 times NVME sizing.     |
| NIC         |         |            |       |       |        | Motherboard will likely come with a single 1/2.5gig NIC. Look for 10gig NIC that the file transfers will use. |
| GPU         |         |            |       |       |        | Not necessarily required. CPU may have usable GPU. My 1660 Supra has been serving me well for years.    |
| PSU         |         |            |       |       |        | Preference for Corsair 'i' models to allow energy consumption and fan speed/temps monitoring.            |
| Total       |         |            |       |       |        |                                                                                                         |

## Clustering

Will likely be 2 identical copies of hypervisor 1.
