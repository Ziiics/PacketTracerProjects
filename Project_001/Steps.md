# Project 1 - Single LAN Office Setup

This project is done in Packet Tracer. This will be the most basic project in this journey. The idea is to get myself familiar with the different network devices available and the troubleshooting steps by relying on the simulation of packet's movement among the network traffic.

Steps

1. Add all the devices and the required physical cabling
2. Turn on router and run no shutdown on necessary ports
3. Decided IP addresses range,

- Internal : 192.168.1.0/24
- ISP : 200.1.2.0/24
- WAN : 200.1.1.0/24

4. Internal IP segregation

| IP Range                     | Description                |
| ---------------------------- | -------------------------- |
| 192.168.1.2 to 192.168.1.9   | Infrastructure             |
| 192.168.1.10 to 192.168.1.19 | Printer and static devices |
| 192.168.1.30 to 192.168.1.79 | End Host and Users         |
| 192.168.1.80 +               | For expansion              |
