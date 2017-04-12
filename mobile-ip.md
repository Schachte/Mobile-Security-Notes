# Mobile IP

## Why do we need mobile ip?

- Need a protocol to allow connectivity even when you're moving across the grid
- IP address 1 wants to send a message to IP address 2
- DNS servers have a fixed IP address 
- When you move you connect to a new cell tower. When you connect to new cell tower (handoff) you need to do a DNS update. (TOOO MANY UPDATES) Lots of DNS overload. 
- IPv4 doesn't work for these reasons

## What exactly is IP (Internet Protocol)

- Network layer, "best effort" packet delivery
- Consists of network ID + host ID
- IP addresses are tied to the "Home Network Address"
    . Hosts are assumed to be wired
    . Intermediate routers look only at the network address
    . Mobility without a change in IP will result in unroutable packets

## How does Mobile IP Work?

- Think, if we had to do a DNS update every time we moved, we would have 100 trillion updates.
- This is not scalable AT ALL. It's not even physically possible. 
- "Mobile IP" allows people to move without having to change the permanent IP address.
- Every phone as a PERMANENT IP address
- Every phone has a home agent (similar to home location registrar) on its home network (Considered permanent IP address)
- When you go from one registration area to another, you can register with other location registrars and they act at home agents for mobile IP
- When a mobile host moves, it establishes a care-of-address. Similar to forwarding pointer concept

## Recap on some definitions

- Mobile host - The phone
- Permanent IP address - The IP that is associated with a mobile host at the home network (Where you typically connect to)
- Foreign Hosts/Agents - Places that you register to when you're on the move. They assign you a temporary IP address to route packets to you
- Care of Address - The temporary IP address that is assigned to you when connected to a foreign host. The mobile host will notify the home agent about the temporary IP address.
- Correspondent Host - Someone who is trying to send you a message sends it to the permanent address of the mobile host (Doesn't care about the care of address at all)
    . Packets will get rerouted from home network to the foreign host

## IP-in-IP Tunneling

- Packet to be forwarded is encapsulated in new IP packet.
- Needed when home agent sends data to care-of-address
- The home agent doesn't tamper the original packet AT ALL.
    . All it does it repackage it into a new packet and make that packet the payload
    . The source address is the home agent and destination is the care-of-address IP

## Care of Address

- Mobile Host connects to a new network, you can do one of the following:
    1. Care of can be the address of the foreign agent which forwards packets to mobile host
    2. Care of can be temporary, foreign IP (direct link to mobile host)
        . Packets tunnels directly to mobile host
- Regardless, the care of address must be registered with the home agent

## Routing Inefficiency 

- What if the correspondent host and home agent have the same IP (on the same network?)
- IP-in-IP tunneling inefficient at this point
    . Solution: Do the inefficient routing once, then you share the IPs (he mumbled the solution in the video)


