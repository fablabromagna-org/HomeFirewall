# Home Firewall
An old unused RouteBoard with ether1 port out of order, the needing for a firewall with VPN facility, no money in my pocket, two studying days and some cut and paste from the Internet are the ingredients of this recipe.

I'm not a RouterOS guru, so there could be better solutions, but this one works for me: suggestions for configuration and English improvement are welcome!

# Some info about my home network

Telco ADSL router

WAN side: DHCP public address

LAN side: 
IP address - 192.168.1.1/24
DHCP server with address pool 192.168.1.0/24
Static Lease for 192.168.1.35 (RouterBoard address)
Port forwarding from WAN interface to RouterBoard address for UDP ports: 500 (IKE), 1701 (L2TP), 4500 (IPsec)

RouterBoard addresses:
ether2: (LAN interface with DHCP server active)
192.168.100.1/24

ether5: (WAN interface)
DHCP client on (the address 192.168.1.35 is reserved on Telco Router)

VPN network:
192.168.102.0/24

# Dynamic DNS
In my network I've a device that handles DynamicDNS. This is a required function if you want to reach your network from the outside and you don't have a static public IP.
If you actually don't have any Dynamic DNS client active on your network you can rely on RouterOS functions.
You have to choose a Dynamic DNS free provider, create an account and follow the instruction available here for RouterBoard configuration:
https://wiki.mikrotik.com/wiki/Scripts#General

If you search the web for "mikrotik dynamic dns" you'll find lots of solutions and ready-made scripts.

# References & Greetings
RouterOS by Example - Stephen R.W. Discher 1st ed.

Johann Fenech blog - https://blog.johannfenech.com/?p=1385

Mikrotik Wiki - https://wiki.mikrotik.com

Thanks to Edoardo Savini for support!
