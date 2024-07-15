# traceroute
Sometimes a network is particularly slow, and you want to track the routes of your packets or identify which gateway is causing delays. 
It can be challenging to do this manually, which is where the traceroute command comes in handy.

“traceroute” is a diagnostic command (also sometimes written as “tracert”) that can show you possible routes across an IP network and calculate any transit delays in that route. 
Whereas the ping command only shows a final round trip time for packets to go from host to destination and back, traceroute calculates the total time spent establishing a connection by adding up the mean respective round trip times for each subsequent node along a given route.

The overarching goal of traceroute for troubleshooting is to launch User Datagram Protocol (UDP) probes of increasing time to live (TTL) until the Internet Control Message Protocol (ICMP) sends a “time exceeded” message back. 
The “time exceeded” message is an indicator that the packet has reached a router along the root. The process increases TTL by one each time until the “port unavailable” message bounces back—indicating either the end of the destination or that the maximum TTL is reached.

The probes always start by sending a packet with TTL=1. Every time a packet hits a router, it lowers the TTL by 1, so we know that when we get a time exceeded message it is because TTL is at 0; we have reached another stop along the route. 
Thus, the probe increases TTL by one setting every time, slowly adding hops along the route until the destination is found or the maximum number of hops is hit. At the end of it all, you receive information about the specific path a packet follows and each route along the way.

The report you receive shares the following information:

The Time to Live
The IP addresses of each stop in the route—each gateway that has responded to the probe
The round trip time for each router along the route
This is valuable information for knowing an exact route and troubleshooting any speed and network issues. 
But one of the most valuable tools in traceroute is that the report specifically marks with an asterisk (*) for any router on the route that does not send a response within the time limit. 
Now, you know exactly where to look to troubleshoot.

Here’s an example of a report output from a traceroute command. Take a close look at it.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/20f87ab9-c308-4333-977b-3178bb62b27e)

You may notice that lines 2 and 3 are identical. 
This is an example of a buggy kernel in the second hop that forwards packets with zero TTL – lbl.csam.arpa .

As you can see, traceroute can give you a lot of really helpful diagnostic information quickly and simply. 
However, it does have limitations. Some networks don’t provide address-to-name translations. 
When those appear on your report, you have to guess the path that packets take cross-country. This happens in the report sample above at hop number 6 with IP address 128.32.197.4, a router along the NSFNet, which doesn’t give you the named translation.

Overall, though, traceroute is a commonly used diagnostic tool and one that you will use often in your DevOps career.
