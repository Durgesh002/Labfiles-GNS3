# OSPF Lab Topology - Cisco Routers

## Overview

This project explores the configuration of **OSPF (Open Shortest Path First)** on Cisco routers. The primary goal was to understand how OSPF operates in a multi-area environment using Cisco's IOS.

In addition to OSPF, the lab experiment also incorporated **VLANs** and **Inter-VLAN routing**, adding depth and real-world complexity to the topology. 

--

## Key Takeaways

The lab simulation helped me understand how to configure OSPF protocol on Cisco routers. Encountered a few problems-namely, unable to ping devices while testing the routing and reachability between devices. The devices were not able to ping when in the same VLAN. But, in the end I was able to figure it out. The ABRs (ARea border routers play a significant role in sharing routes beween different areas. This lab was able to give my a basic idea of OSPF configurations is done.

Commands used:

`R1(config)#router ospf process ID` (this could be same on router) 

`R1(config)#network 192.168.6.0 0.0.0.255 area 22` (22 is the area ID. It cannot be same as it changes depending on which area the router belongs to)

`R1(config)#do sh ip ospf neighbor` (This shows list of other neighboring OSPF routers

`R1(config)#do sh ip protocols` --> (Output helps to understand the currently running dynamic routing protocol).

--

## Outputs

Routing table

The table has many routes learned via OSPF. Please note that the routes learned via OSPF is indicated by letter 'O'. The routes inducating '0 IA' are the inter area routes shared by the ABR.

<img>![ip-route-ospf](https://github.com/user-attachments/assets/810581ae-9b67-4384-83ac-21c7119a3f85)</img>

Ping test

Tested the connectivity and reachability between devices by pinging. Additionally, you can use traceroute command on the Cisco router and it shows the path the packet traces to reach the destination.

<img>![ping](https://github.com/user-attachments/assets/5288ec26-83f2-46ab-83f3-99ecbffd75ca)</img>

