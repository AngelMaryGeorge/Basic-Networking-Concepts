# Firewalls and Security Groups

## Objectives
- Understand the basics of firewalls
- Learn about Security Groups in AWS
- Explore Network ACLs (Access Control Lists)

## Concepts

### Basics of Firewalls
A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between a trusted internal network and untrusted external networks, such as the internet.

**Types of Firewalls:**
Network Layer (Packet Filtering) Firewalls:

- Examines packets at the network level (IP addresses, ports).
- Operates at both the OSI model's Network and Transport layers (e.g., iptables, Cisco ASA).

**Application Layer (Proxy) Firewalls:**
- Inspects traffic at the application layer (HTTP, FTP).
- Can perform deep packet inspection and filtering (e.g., Squid proxy).

**Stateful Inspection Firewalls:**
- Tracks the state of active connections and allows only legitimate packets.
- Provides enhanced security by analyzing the context of traffic (e.g., Palo Alto Networks).

### Security Groups in AWS
Security Groups act as virtual firewalls for EC2 instances to control inbound and outbound traffic. They are stateful, meaning if you allow outbound traffic, the return traffic is automatically allowed.

**Key Features:**
- Inbound Rules: Specify the protocols, ports, and IP ranges allowed to reach the instance.
- Outbound Rules: Define the destinations, protocols, and ports allowed from the instance.
- Implicit Deny: All inbound and outbound traffic is denied by default unless explicitly allowed.

### Network ACLs (Access Control Lists)
Network ACLs are an optional layer of security for controlling traffic in and out of a subnet in AWS. Unlike Security Groups, they are stateless and evaluate rules in numerical order.

**Key Differences from Security Groups:**
- Stateless: Each rule applies to incoming or outgoing traffic independently.
- Ordered Rules: Processed based on rule number priority.
- Subnet-level: Applied at the subnet level, affecting all instances within the subnet.

Example Network ACL Rules:
- Allow HTTP inbound from any source: Rule #100: Allow, HTTP (80), 0.0.0.0/0, Inbound
- Deny all inbound traffic: Rule #200: Deny, All Traffic, 0.0.0.0/0, Inbound

## Summary
In this lesson, you learned about firewalls, including their types and functions. You also explored Security Groups in AWS, which provide instance-level security, and Network ACLs, which offer subnet-level control over traffic flow.
