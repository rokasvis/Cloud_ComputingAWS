# Virtual Private Cloud (VPC)

## What is CIDR

Classless Inter-Domain Routing is a method for allocating IP addresses and for IP routing. The Internet Engineering Task Force introduced CIDR in 1993 to replace the previous classful network addressing architecture on the Internet. Its goal was to slow the growth of routing tables on routers across the Internet, and to help slow the rapid exhaustion of IPv4 addresses.

## What is an IPve4 and IPve6

The Internet Protocol version 4 (IPv4) is a protocol for use on packet-switched Link Layer networks (e.g. Ethernet).  IPv4 provides an addressing capability of approximately 4.3 billion addresses.

The Internet Protocol version 6 (IPv6) is more advanced and has better features compared to IPv4.  It has the capability to provide an infinite number of addresses.  It is replacing IPv4 to accommodate the growing number of networks worldwide and help solve the IP address exhaustion problem.

One of the differences between IPv4 and IPv6 is the appearance of the IP addresses.  IPv4 uses four 1 byte decimal numbers, separated by a dot (i.e. 192.168.1.1), while IPv6 uses hexadecimal numbers that are separated by colons (i.e. fe80::d4a8:6435:d2d8:d9f3b11). 

Advantages of IPv6 over IPv4:

- IPv6 simplified the router’s task compared to IPv4.
- IPv6 is more compatible to mobile networks than IPv4.
- IPv6 allows for bigger payloads than what is allowed in IPv4.
- IPv6 is used by less than 1% of the networks, while IPv4 is still in use by the remaining 99%.

## What is route table (RT)

A route table contains a set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed. To put it simply, a route table tells network packets which way they need to go to get to their destination.

## What is Internet Gateway (IG)

An internet gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between your VPC and the internet.

An internet gateway serves two purposes: to provide a target in your VPC route tables for internet-routable traffic, and to perform network address translation (NAT) for instances that have been assigned public IPv4 addresses. 

An internet gateway supports IPv4 and IPv6 traffic. It does not cause availability risks or bandwidth constraints on your network traffic. There's no additional charge for having an internet gateway in your account.

## VPC and Subnet Range

A subnet is a range of IP addresses in your VPC. You can launch AWS resources, such as EC2 instances, into a specific subnet. When you create a subnet, you specify the IPv4 CIDR block for the subnet, which is a subset of the VPC CIDR block. Each subnet must reside entirely within one Availability Zone and cannot span zones. By launching instances in separate Availability Zones, you can protect your applications from the failure of a single zone.

## What is NACLs

A network access control list (ACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets. You might set up network ACLs with rules similar to your security groups in order to add an additional layer of security to your VPC.

## What is the difference between stateless and stateful

The key difference between stateful and stateless applications is that stateless applications don’t “store” data whereas stateful applications require backing storage.

Stateful applications like the Cassandra, MongoDB and mySQL databases all require some type of persistent storage that will survive service restarts.

