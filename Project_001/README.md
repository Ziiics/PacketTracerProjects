# Project 1 - Single LAN Office Setup

This will be the most basic project in this journey. The idea is to get myself familiar with the different network devices available and the troubleshooting steps by relying on the simulation of packet's movement among the network traffic.

The file: [Project_001 Packet Tracer file.](Project001.pkt)

### Topology

![project001_topology](./Project_001.png)
There are a total of 15 workstations, one switch on each side (internal and ISP) which are connected by router from each side on WAN connection.

#### IP Address

| Description      | IP              |
| ---------------- | --------------- |
| Internal Range   | 192.168.10.0/24 |
| Internal Gateway | 192.168.10.1    |
| WAN Range        | 200.1.1.0/28    |
| ISP's Range      | 200.1.2.10      |
| ISP's server     | 200.1.2.30      |
| ISP's switch     | 200.1.2.10      |

### Key Concepts Implemented

- Flat network subnetting
- (not sure what else)

### Steps

1. Insert necessary nodes/devices (2 routers, 2 switches, 2 printers, and 15 end users)
2. Add physical connection between devices
3. Choose the IP Range (as listed above)

| Description | IP/Prefix       | Gateway      |
| ----------- | --------------- | ------------ |
| Internal    | 192.168.10.0/24 | 192.168.10.1 |
| ISP         | 200.1.2.0/24    | 200.1.2.1    |
| WAN         | 200.1.1.0/24    | 200.1.1.1    |

4. Configure switch's hostname and the designated IP addresses and default gateway.
   - Switched uses VLAN 1 SVI for management IP.
   - Switching still uses MAC, not IP.
5. Configure router's hostname and IP address. Add local address to LAN facing and external address to WAN facing port.
   - Router connects two different network, enabling inter-network communication.
6. Rename end hosts and manually add its IP, DNS, and default gateway. Uwsually subnet mask is auto added, but can also adjust.
   - DNS for this projects is not required for IP-based testing, only for name resolution.
7. Check local traffic between internal devices
8. Apply PAT overload to the router on LAN router side, letting packet going out to share the same public IP.
9. Add ISP connection
   - Added second reouter to simulate ISP for full control of routing and return traffic
   - Ads switch and server (for internet connection check)
   - Assign WAN IP to the Router port that face the WAN. Assign internal ISP's IP to the switch.
   - For the werver, update its IP address and ensure **http/https** service is on
10. Try reaching ISP server through LAN workstations or end devices by doing **< server-ip >/index.html** or even just the server-ip through browser on ens devices

### Validation and Testing

- [x] Check workstations connection to the ISP server
- [x] Check if the traffic coming out from LAN shows the wanted IP
- [x] If the data sent to the ISP are able to return accordingly

### Key learnings

- I know about NAT, but PAT is new. It is a Port Address Translation that makes every traffic coming out from the router to a shared configured IP address.
- I thought that reaching to the server don't need IP as how we user internet. But I forgot that DNS didn't exist here.
