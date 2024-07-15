# Domain Name System (DNS)

## DNS Overview

As discussed previously, computers tell each other apart using IP addresses. 
Humans, on the other hand, identify things with names. 
Humans and computers have to interact, but it would be really hard for humans to interpret IP addresses and impossible for computers to communicate with names. 
This is where the Domain Name System (DNS) comes it. The DNS merges the needs of both parties, converting human-readable domain names into computer-friendly IP addresses and vice versa.

To better understand how this system works, let’s walk through the process of retrieving an IP address from a web browser request using the DNS lookup process.

1. Client initiates a query to a Recursive Resolver.
2. The Recursive Resolver connects to a Root Server.
3. The Root Nameserver then responds to the resolver with the address of a Top Level Domain (TLD) Server (such as .com or .net)
4. The Root Resolver makes a request to the TLD Server.
5. The TLD Server returns the IP address of the Domain Nameserver, which stores the information about the requested domain.
6. The Recursive Resolver sends a query to the Domain Nameserver.
7. The IP address for the requested domain is returned to the Recursive Resolver from the Domain Nameserver.
8. The Recursive Resolver provides the client with the IP address of the requested domain.

The visual below also explains how this works. 
It’s a lot like a game of telephone that translates information back and forth from computer to human language until it reaches its final desired form.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/00d9c4fe-1003-4151-86d9-2a6f2a4585c8)

## Domains, Zones, and Delegation

A domain is a self-contained network on the internet. 
There are many domains and each can have subdomains and more below them.
The easiest way to visualize domains is as a tree with nodes. 
The top-level namespace (the DNS root zone) is the highest hierarchical level of the DNS and is divided into top-level domains such as .com .gov and .io. Each TLD of that tree represents a domain and all subdomains below it. 
For example, example.com is a subdomain of the .com domain. You can keep breaking these domains and subdomains down, like folders and subfolders within a file system.

Different organizations on different domains. For example, the root domain is owned by the organization called ICANN, while Verisign controls the .com domain. But ownership is not a simple split. 
The root domain includes all domains on the internet, including the .com domain. 
It’s like ICANN owns the entire tree while Verisign owns one branch of it…but the branch is still part of the larger tree.

So how can Verisign own that branch? The answer is delegation. 
The delegation process allows an organization that owns a domain to give control over a subdomain to another organization.

Delegation is done via Nameserver (NS) records. 
When a domain owner delegates a subdomain to another organization, they create an NS record. 
The NS record indicates the new owner of the subdomain and directs all communications related to that domain to the servers of that organization. 
The organization controlling these servers is technically a domain owner. It continues as more nameservers are built and subdomains delegated.

To make things clearer, let’s consider a simplified example.

1. ICANN manages a root nameserver (in fact there are multiple root nameservers across the globe).
2. Verisign builds their own nameserver and asks ICANN to delegate control over the .com zone to them.
3. ICANN creates an NS record that points to the nameserver owned by Verisign. Now, any time a client contacts them for the .com domain, they are redirected to Verisign’s server.
4. You start a company called “Example Ltd” and you want to register your own domain, example.com, in a .com zone.
5. You build your own nameserver and ask Verisign to delegate control over example.com to you.
6. Verisign creates similar NS records on their nameserver which delegates control over the example.com domain to “Example Ltd.” Now, you control that domain.


## DNS record types
DNS records, also known as zone files, provide information about a domain. This includes the IP address that is associated with this domain and how to handle queries for it. Each DNS record has a time-to-live setting (TTL) which indicates how often a DNS server will refresh it. 

Below are the most commonly used types of DNS records and their meaning.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/0a4a3f81-9985-40fe-b16e-2ea32b767094)



