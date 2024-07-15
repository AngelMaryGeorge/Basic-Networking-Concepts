# nmap
The next tool to become familiar with as a DevOps engineer is nmap. nmap, or “network mapper”, is also a free, open-source tool like netstat. A use case for nmap is almost identical to that for netstat, with one minor difference. When you’re using netstat, you have to log into a server. But nmap scans all servers in a network.

nmap sends raw IP packets to determine the hosts available on a given network, what services are offered by these hosts, and what operating systems they are running. System administrators use nmap for tasks such as network inventory and security audits—sometimes known as “white hat” hacking because it identifies vulnerabilities in order to secure and resolve them. However, this tool is also widely used by “black hat” hackers, who use the information provided to exploit vulnerabilities in the network. Because of this potential, some cloud providers do not allow nmap to run on their networks.

In many ways, DevOps engineers are white hat hackers—troubleshooters, security protectors, and network experts. To demonstrate how nmap can be useful for us, let’s go through a simple scenario.

Assume we gained SSH (Secure Shell Protocol) access to an unknown server. Our goal is to find out what else is running on the network.

First, let’s find out the IP of our server and the IP range of our network using our address.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/fef691f3-d57f-4801-86c1-1a1cc1e3fc97)

Our IP address is 172.31.44.35 and 255.255.240.0 netmask corresponds to /20
Now that we know this information, we can initiate a nmap ping scan using the following command:

``` nmap -sn 172.31.44.35/20 ```
![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/e8115ade-e124-4640-8c25-60d59cbdc3c5)

We can see now that there are 15 hosts in the specified subnet.

Let’s test one of these hosts and find out which ports it is listening to. You can do this using the command below:

``` nmap -A 172.31.36.237 ```
![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/c77f4319-f93c-4a46-8a67-cc82323f41c9)

The nmap command helps us see that the there is an SSH and HTTP processes listening to ports on this server.

Since we know that a curl is a great tool for HTTP, we can then try obtaining the webpage using curl.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/1d5379db-cf4c-4161-b839-257c351d83b6)


Or we can establish an ssh connection, another portocol which is used multiple times throught a typical day in life of a DevOps engineer.
