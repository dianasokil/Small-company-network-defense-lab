# Small Company Network Defense Lab

Lab simulation built in Cisco Packet Tracer. This is not a real company network.

## What I built
- Router: Cisco 2911, named HQ-Router, 192.168.10.1
- Switch: Cisco 2960
- Employee-PC-1: 192.168.10.10
- Employee-PC-2: 192.168.10.11
- Admin-PC: 192.168.10.20
- Web-Server: Server-PT, 192.168.10.30

All devices use static IP addressing, with 192.168.10.1 as the gateway and 255.255.255.0 as the subnet mask.

## What I tested
- Ping from PCs to the router, to each other, and to the web server: successful
- Web access from Employee-PC-1 to http://192.168.10.30: successful
- Fixed a router to switch link issue by reconnecting with the automatic connection type in Packet Tracer

## Security: switch port security
Configured on FastEthernet0/1 to 0/4:
- switchport mode access
- switchport port-security
- switchport port-security maximum 1
- switchport port-security mac-address sticky
- switchport port-security violation shutdown

This means only one approved device, learned by its MAC address, can use each port. A different device on the same port causes the port to shut down. Port security controls which device can connect to a port, it does not track websites or browsing history.

## How to open it
Open Network-Defense-Lab.pkt in Cisco Packet Tracer. Screenshots in this repo show the topology, the web page test, and the port security output.

## Next steps I plan
- VLAN segmentation for office and servers
- An access rule so only web traffic reaches the server

