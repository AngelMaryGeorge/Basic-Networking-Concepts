# TCP/IP

## What is TCP/IP, and how is it different from OSI?
The OSI model explained above is great for developing a theoretical understanding of a networking stack, but it’s a challenging model to use in practice. 
Instead, nowadays we use the Transmission Control Protocol/Internet Protocol (TCP/IP) Model. 
This model has a similar layered structure, but it’s less complicated.

TCP/IP combines the three top levels of OSI (Application, Presentation, and Session) into a single Application layer in TCP. 
The two bottommost layers of OSI (Data Link and Physical) become the Network Interface layer in TCP.

The final result of these mergers is a 4-layer TCP/IP model. From the bottom up, those are Network Interface, Network, Transport, and Application.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/b92eb4b6-156e-4a83-b4fd-33d6586e615b)


One of the most important layers to understand in the TCP/IP model is the Application layer. 
This layer is responsible for process-to-process communication over an IP network. 
Each application in this layer is defined using a numerical specification called a Request for Comment (RFC). 
For example, HTTP, which is a protocol on the Application layer, is defined by RFC number 7231.

The other layer of the TCP/IP model that requires particular special attention is the Transport layer because it introduces several important networking concepts.

## TCP vs UDP
The Transport layer of the TCP/IP model uses two major protocols: TCP and UDP.

TCP is a connection-oriented protocol. 
This means that it first establishes a link between the source and destination before it sends data. 
Once the connection has been made, then TCP breaks down large data sets into smaller packets, sends them along the connection, and ensures data integrity throughout the entire process. 
TCP is a preferred protocol when data integrity is critical, such as in any transactional system.


UDP in turn is not connection-oriented. 
UDP starts transmitting data immediately, without waiting for connection confirmation from the receiving side. 
Even though some data loss can happen, UDP is most often used in cases where speed is more important than perfect transmission, such as in voice or video streaming.

## Ports and Protocols
The Transport layer of TCP/IP also introduces the concept of ports. 
TCP ports are labeled with specific port numbers, digital identifiers match the information received from the network with the proper process needed to process that data.

Here are some examples of the most used ports:

Port Number	          Process	                    What it’s used for
22	                   SSH	                      Secure shell, remote access, and file transfer
53	                   DNS	                      Resolving domain names into IP addresses
80	                   HTTP	                      Serving web pages
443	                   HHTPs	                    Serving web pages in a secure manner
3306	                 MySQL	                    Database connections

While many ports are non-privileged,—anyone can use them without special permission—some require root permissions. 
Ports 1-1023 are called “well-known ports” and require root permissions before a server can listen to them. 
It’s a good practice to avoid running web servers as root, assign minimal permissions to services, and use nonprivileged ports when possible. 
That’s why sometimes we can see ports 8080 for HTTP and ports 6433 for HTTPS—they’re non-privileged.
