# Hardware

- The kit will be hosted in the home office which is a shared space and so in terms of noise and heat, has to pass the GF test (and to some extent, aesthetics) 😜
- If CEPH is to be used for HA in the cluster, a separate 10gig network is preferred. Potentially use the 40gig offered by Thunderbolt 4 to service that requirement, and use a dedicated 10gig NIC for everything else.
  - Note, I on't have enough 10gig ports on the switch to use it on day 1.... network upgrade to follow 😃

## NAS / Fileserver

| Component   | Options | Unit Price | Units | Cost  | Source | Notes                                                                                                   |
| ----------- | ------- | ---------- | ----- | ----- | ------ | ------------------------------------------------------------------------------------------------------- |
| Case        |         |            |       |       |        | Rack mountable. Consider 2-4U depending on whether hosting HBA only, or hot-swappable storage built-in. |
| Motherboard |         |            |       |       |        |                                                                                                         |
| CPU         |         |            |       |       |        | Does not need to be that powerful. This build will be IO-bound rather than CPU-bound. No onboard GPU required. |
| CPU Cooler  |         |            |       |       |        | Will need to be low height if a 2U chassis is used                                                      |
| Memory      |         |            |       |       |        | Does not need masses of memory, nor especially fast memory                                              |
| SSD         |         |            |       |       |        | Something small as an OS/boot disk                                                                      |
| NVME        |         |            |       |       |        | May not need any at all. At most, something small as an OS/boot disk                                    |
| HHD         |         |            |       |       |        | Will primarily be re-using existing disks from various small servers I have built. Prices quoted are what it would be if building new. |
| NIC         |         |            |       |       |        | Motherboard will likely come with a single 1/2.5gig NIC. Look to use that as a management interface only. Look for 2x10gig NIC that the file transfers will use. |
| GPU         |         |            |       |       |        | Not required. Will be headerless.                                                                       |
| PSU         |         |            |       |       |        | Doesn't have to be that powerful given the components. More power if running disks in the case rather than external DAS/JBOD |
| Total       |         |            |       |       |        |                                                                                                         |

## Hypervisor

| Component   | Options | Unit Price | Units | Cost  | Source | Notes                                                                                                   |
| ----------- | ------- | ---------- | ----- | ----- | ------ | ------------------------------------------------------------------------------------------------------- |
| Case        |         |            |       |       |        | Rack mountable. Consider 2-4U. The primary consideration is cooling and noise.                          |
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
