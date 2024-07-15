# netstat
netstat is a command that shows you specific information about the communications between your local machine and other machines/devices on the network. 
Netstat shows active TCP connections as well as ports on which the server is listening. 
It is useful when you need to see which network services are running on a local machine.

In the example below, we can discover that there is an apache web server listening on the default HTTP port.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/433fbd0d-ff18-4634-b99e-135170ca55dd)

In the above example, the command netstat -lp shows only listening servers (-l flag)and their program name (-p flag). Other netstat flag commands include:

-a: all active ports
-n: only numerical IP addresses and ports
-f: whenever possible, provide all names of foreign connections
-o: show process ID
-r: routing table
