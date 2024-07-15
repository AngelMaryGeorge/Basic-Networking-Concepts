# dig

The next tool to learn is “dig”, not “how to dig”, but just “dig” – which stands for Domain Information Groper.
It is used for troubleshooting Domain Name System (DNS) problems and verifying DNS records. 
dig performs DNS Lookups and then shows you the answers returned from the name server(s).

The basic syntax of dig for a DNS record lookup is [dig] [domain name]. 
This will make an NS query and return the “A record”—Address record—for a given domain name.

Let’s break down this example by looking up the DNS record for the domain google.com. At the top, you can see the request: dig google.com. 
In the ANSWER section of the response, you get a number of pieces of information:

The queried server (google.com)
TTL ( in this case 93)
Query class (IN= internet)
Query type (A= address)
The IP address for the queried domain (172.217.0.46)
So there you have it—the google.com DNS record is associated with the IP address 172.217.0.46.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/f98eda6b-b3fd-416b-94aa-fb1beb5fe9f5)

Like with curl, the dig has a default method. 
By default, dig will attempt to query each server specified using the /etc/resolv.conf file, the automatic file type for configuring DNS name servers. 
But in some cases, you may want to send queries to a specific DNS server. You can do this with the @ flag.

This example checks the DNS record for google.com on specifically the 8.8.8.8 server. 
As you can see, it returns a different ANSWER from the /etc/resolv.conf file used in the default above.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/a6ec48cf-91aa-4f1c-8712-91edd43de6fe)

By default, dig also returns an ANSWER of a A record (address). 
But you can also check different types of DNS records using the -t option. The syntax for this would look like:

``` dig -t [record type] [domain name] ```
The example below specifics the TXT record for the google domain.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/18b072b7-e3c0-4af8-a23a-85bde7547f0c)


Other dig record types you may want to specifically query:

MX record- mail exchanger, tells you what mail server accepts email messages for a given domain name
NS record- all authoritative servers for a domain name
ALL- all DNS records for a domain name
Dig is a great tool for DevOps engineers to have in their toolbox because it helps you troubleshoot for your name servers, double-check records, and trace IP addresses and their domain names, among other things.
