# Where should I enable Virtual Network (VNet) Flow Logs?
Discussion of the decision where to apply Virtual Network Flow Logs, impact of Hub-enablement only contrasted with Spoke enablement.

# Introduction
This document assumes the reader is familiar with VNet Flow logs as a technology. If not the links below will help:

- https://blog.cloudtrooper.net/2024/05/08/vnet-flow-logs-recipes/
- https://learn.microsoft.com/en-us/azure/network-watcher/traffic-analytics-schema?WT.mc_id=Portal-fx&tabs=vnet#fields-used-in-traffic-analytics-schema
- https://techcommunity.microsoft.com/t5/azure-networking-blog/network-traffic-observability-with-virtual-network-flow-logs/ba-p/4112907
- https://youtu.be/lvQM2K_77TI

# Enablement
One of the primary benefits of VNet Flow Logs (vs NSG Flow Logs) is the ability to enable on mass, at the VNet level, irrespective of if you are using NSG or not. You can also enable VNet Flow Logs at the subnet or NIC level, but this is a less popular config.

Customers in Azure often run Hub/Spoke topologies like the one shown below, wherein many _Spoke_ Virtual Neworks connect to a single centralised _Hub_ Virual Network. With the latter containing shared services including network components like Firewalls and Gateways.

![](images/2024-05-22-15-26-19.png)
![](images/2024-05-22-15-26-34.png)

