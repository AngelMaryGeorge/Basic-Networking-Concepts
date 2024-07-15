# OSI Model
The Open Systems Interconnection (OSI) model is a set of standards that defines how computers communicate over a network. 
In the OSI model, data flow gets broken down into seven layers that build upon each other. 
Each layer uses data from the layer before it and serves a specific purpose in the broader network communication.

The OSI model works from the bottom up, beginning from layer 1 (Physical) and ending with the top layer 7 (Application). 
The top layer is the most direct point of user interaction with the OSI model—if you’re reading this article on a device, you’re working on the 7th layer at this very moment.


![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/dcb80c1b-37e1-4aa4-898e-53108298a453)


## Layer 1: Physical
The Physical layer handles raw data within physical media. 
That raw data is made up of bit of information and the Physical layer converts those into electrical signals that define certain aspects of a piece of physical media. 
For example, Physical layer specifications may define aspects like voltage levels, transmission distances, and cable standards. 
You find Physical-layer specifications in technologies like Bluetooth and Ethernet.

## Layer 2: Data Link
The Data Link layer takes data in the form of electrical signals (frames) and delivers them across members (nodes) of a single network. 
Data Link frames only operate on a local network and do not cross the boundaries into other networks.
The Data Link layer can also detect and recover transmission errors by attaching extra information containing an error detection code to a given frame.
When that frame is sent across the network, its receiver checks the received frame by matching the extracted data with the code.

## Layer 3: Network
A Network describes the entire ecosystem of subnetworks and other networks that are all connected to each other via special hosts called gateways or routers. 
The Network layer works with routes (paths from one network to another). The Layer determines the most effective route to convey information. 
Sometimes, the message you’re trying to send is particularly large. 
In this case, the network may split it into several fragments at one node, send them separately, and reassemble them at the destination node.

## Layer 4: Transport
The Transport layer protocols provide host-to-host communication services for applications. 
It is responsible for connection-oriented communication, reliability, and flow control. 
Connection-oriented communication uses a pre-established connection between hosts as a pathway for communicating between applications. 
Some protocols of the Transport layer are connection-oriented, but some protocols of this layer are not connection-oriented and instead transfer data end-to-end without the need for connection.

## Layer 5: Session
The Session layer controls connections, whether that’s keeping an eye on possible connection losses or temporarily closing or re-opening connections depending on their frequency of use. 
The protocols of the Session layer try to recover any connection losses when they happen. 
It also optimizes connections: if a connection is not used for a long period, Session-layer protocols may close it and re-open it later. 
These protocols also provide synchronization points in the stream of exchanged messages, or in other words, spots for large messages to momentarily regather and make sure they’re all on the same page.

## Layer 6: Presentation
The Presentation layer also called a Syntax layer, ensures that the recipient of the information can read and understand what it receives from another system; the information is presented in a legible way. 
Processes such as data encoding, compression, and encryption happen on this layer.

## Layer 7: Application
The OSI model’s top and final layer is the Application layer. 
The Application layer displays the data in the correct format to the end-user—you! 
This includes technologies such as HTTP, DNS, FTP, SSH, and much more. 
