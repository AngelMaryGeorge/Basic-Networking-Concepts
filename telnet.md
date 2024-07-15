# telnet
One important caveat to tools like ping and traceroute? A server responding to traceroute or ping does not necessarily mean that it is operational.

Imagine that we have a virtual machine with an Apache HTTP server on it. 
This means that in order to load web pages, the machine needs to have the Apache daemon up and running. 
If it’s not running, although the virtual machine may be responsive to ping requests, we will not be able to load anything.

On the flip side, if a server does not respond to ping, – it’s not necessarily down. 
Some system administrators configure their firewalls to drop all ping requests, so you’d get no response from the server. 
But the server behind this firewall can still be reachable via other protocols.

Because of these limitations to traceroute and ping, you want to be able to test whether or not the protocol you’re using will allow you to establish a network connection. 
Telnet is a command that can help with this.

Historically, telnet was used as a command-line interface for accessing remote servers. 
However, because telnet does not encrypt the data, it is not secure to use it for remote access and has since been replaced by SSH.

But telnet is still helpful. Nowadays, we can use telnet to test if one host can establish a network connection using a certain protocol. 

A telnet command testing the connection to google.com at port 443, for example, looks like this:

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/d08c8e52-fa4d-4be5-9eaf-66945a53401d)

As you can see above, the command succeeded, which means that a connection is allowed between our local machine and a remote system on a given port.
