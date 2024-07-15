# IP Subnetting, CIDR
The most critical component of networking is the IP address. 
Every time you surf the internet, your browser is connected to its remote server using an IP address. 
You cannot use the internet or network without one.

An IP address is a 32-bit number divided into four 8-bit sections called octets. 
It can be represented in both decimal and binary formats. 
An IP address may contain a subnetwork that’s different from the host. 
The address comes with a subnet mask that distinguishes the part of the IP address that is the network and the part that is the host address.

For example, given an IP address of 192.168.12.20 with the subnet mask of 255.255.255.0, 192.168.12 represents a network address and .20 represents a host address. 
The concept of a netmask leads us to the idea of classful addressing, which divides the 32-bit IP address into 5 sub-classes.

In classful addressing, all IP addresses have an 8-bit, 16-bit. or 24-bit network prefix. 
Class A has an 8-bit long network ID and a 24-bit host ID. There are over 16 million class A addresses. 
Class B has network and host IDs of 16 bits each—there are 65,535 class B addresses. 
Class C holds the smallest networks—254 addresses. Each Class C network ID is 24 bits long with an 8-bit long host.

When ordering IP addresses, you want to keep in mind the size of your network and order a class that fits your needs. 
It’s conceptually easy to do this when you have very large or small networks. 
But problems arise in the middle when you’re in between Class B and C: you need more than 254 addresses but less than 65,535.

Let’s use an example. Let’s assume that you need 1000 addresses in your network. 
It’s more than 254, so you have to go with the next largest class—Class B. 
But now you’re only occupying 1,000 addresses and left with 65,000 unused ones. 
It doesn’t make sense. One solution to this could be to use multiple class C ranges. 
But having a huge number of small networks makes routing overly complicated! 
In our search for a new solution to this IP trolley problem, we’ve started to break networks using Classless Inter-Domain Routing.

Instead of having network classes with fixed sizes, network administrators are allowed to move the subnet boundary to anywhere inside the parent network. 
In other words, we are no longer limited by 8-bit, 16-bit, or 24-bit netmasks.

Let’s go back to our example. Imagine that we have an address that gives us 254 hosts..but we want 300 hosts. Using the old solution, you could get two Class C ranges (making your life more complicated). 
Now with Classless Interdomain Routing, instead of getting an additional Class C network, we can simply decrease our netmask bits by one and get a network that has 510 hosts. That’s much more reasonable!

The table below outlines the most common combination of addresses and netmasks and important details about them.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/f2fbc9e9-6642-476b-84cf-14765f511b5b)

## Routing

Think about a route as a path. 
Different routes lead to different destinations and are used when trying to reach certain targets. 
It’s like driving. If your destination is a residence in a quiet neighborhood, you’ll take a local road. 
If you want to go the mall a few towns over, you may take a state highway. But if you want to road trip across the country, you’ll hop onto the interstate.

We use tables to help us determine the routes we want to take. This screenshot demonstrates a typical route table in AWS:

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/a9efd2bb-4caa-43cb-9eb2-92430568c89d)


When making a routing decision, more narrow rules are evaluated first:

- If a packet destination is in a range of 10.21.0.0/16 – it will remain in a local network (your neighborhood).
- If a packet destination is in a range of 10.0.0.0/8 – it will be sent to the transit gateway (TGW) interface (your state highways).
- If a packet destination does not fall in any of these ranges, the widest one is evaluated which is 0.0.0.0/0 which means it is internet traffic. 
  And the packet will be redirected to the Network Address Translation (NAT) interface (hello, I-95!).
