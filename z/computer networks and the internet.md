
# 1.1 What is the Internet

Internet can be described as : 
- the basic hardware and software components that make up the internet
- a networking infrastructure that provides service to distributed applications

## 1.1.1 A Nuts-and-Bolts Description

- all devices connected to the internet are called **hosts** or **end systems**
- End systems are connected together by a network of **communication links** (copper cables, fiber optics, etc) and **packet switches**. (routers and switches) 
- Different links have different **transmission rate** (bits/sec)
- A **packet switch** receives incoming packet and forwards it
- End systems access the Internet through **Internet Service Providers** (**ISPs**)
- Each ISP is in itself a network of packet switches and communication links
- The Internet principal protocols are collectively known as **TCP/IP**

## 1.1.2 A Services Description

- **distributed applications** example : Electronic mail, Web surfing, instant messaging, Video streaming, etc.
- These are called **distributed applications** because they involve multiple end systems that exchange data with each other
- Because applications run on end systems, you are going to need to write programs that run on the end systems. You might, for example, write your programs in Java, C, or Python.
- End systems attached to the Internet provide a **socket interface** that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system. 
- This Internet socket interface is a set of rules that the sending program must follow so that the Internet can deliver the data to the destination program.

## 1.1.3 What is a protocol

All activity in the internet that involves two or more communicating remote entities is governed by a protocol.

>A **protocol** defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

# 1.2 The Network Edge

The computers and other devices connected to the internet are often referred to as **end systems** or **hosts**.

**End systems** are called **hosts** because they host (that is, run) application programs such as Web browser program, a Web server program, an e-mail reader program or an e-mail server program.

**Hosts** are further divided into **clients** and **servers**.

## 1.2.1 Client and Server Programs

A **client program** is a program running on one end system that requests and receives a service from a **server program** running on another end system. Since, a client program typically runs on one computer and the server program runs on another computer, client-server Internet applications are, by definition **distributed applications**.

## 1.2.2 Access Networks

>The network that physically connects an end system to the first router.

### DSL

- A residence typically obtains **DSL** (digital subscriber line) Internet access from the same local telephone company (telco) that provides its wired local phone access.
- Thus, when DSL is used, a customer’s telco is also its ISP.
- asymmetric access
- makes use of the telco's existing telephone infrastructure
![[dsl-internet-access.png]]

This approach makes the single DSL link appear as if there were three separate links (by frequency division multiplexing) , so that a telephone call and an Internet connection can share the DSL link at the same time.

>[!info] Asymmetric access
>When upstream and downstream transmission rates are different.

### Cable

- cable modems divide the HFC network into two channels, a downstream and an upstream channel
- asymmetric access
- makes use of the cable television company’s existing cable television infrastructure
- it is a shared broadcast medium. In particular, every packet sent by the head end travels downstream on every link to every home and every packet sent by a home travels on the upstream channel to the head end.
![[hybrid-fiber-coaxial.png]]

**Fiber node**: neighborhood-level junctions (supports 500 - 5000 homes)
**CMTS**: Cable Modem Termination System (similar function as DSLAM)

### Fiber-To-The-Home (FTTH)

- There are two competing optical-distribution network architectures that perform this splitting: active optical networks (AONs) and passive optical networks (PONs)
![[ftth-internet-access.png]]

**ONT** : Optical Network Terminator
**OLT** : Optical Line Terminator (conversion between optical and electrical signals)

At home user connects a home router to the ONT and access the internet via this home router.
In PON architecture, all packets sent from OLT to the splitter are replicated at the splitter (similar to a cable head end).

### Ethernet

Ethernet is by far the most prevaent access technology in corporate, university, and home networks. Ethernet users use twisted-pair copper wire to connect to an Ethernet switch.
![[ethernet-internet-access.png]]

### WiFi

- In a **wireless LAN**, wireless users transmit/receive packets to/from an **access point** that in turn is connected to the wired internet.
- A wireless LAN user must typically be within a few tens of meters of the access point.

### Wide-Area Wireless Access: 3G and LTE 4G and 5G

- Mobile devices such as iPhones and Android devices are being used to message, share photos in social networks, make mobile payments, watch movies, stream music, and much more while on the run.
- These devices employ the same wireless infrastructure used for cellular telephony to send/receive packets through a base station that is operated by the cellular network provider.
- Unlike WiFi, a user need only be within a few tens of kilometers (as opposed to a few tens of meters) of the base station.

## 1.2.2 Physical Media

Our bit, when travelling from source to destination, passes through a series of transmitter-receiver pairs. For each transmitter-receiver pair, the bit is sent by propagating electromagnetic waves or optical pulses across a **physical medium**.

Two types of physical medium: 
- **guided** : waves are guided along a solid medium, such as fiber-optic cable, twisted-pair copper wire, or a coaxial cable.
- **unguided** : waves propagate in the atmosphere and in outer space, such as in a wireless LAN or a digital satellite channel.

### Twisted-Pair Copper Wire

- least expensive and most commonly used
- two insulated copper wires, each about 1 mm thick, spiral pattern
- wires are twisted to reduce electrical interference from similar pairs close by
- **Unshielded Twisted Pair (UTP)** is commonly used for LANs
- data rates range from 10Mbps to 10Gbps

### Coaxial Cable

- consists of two concentric copper conductors
- can be used as a guided **shared medium**. A number of end systems can be connected directly to the cable, with each of the end system receiving whatever is sent by the other end systems
- data rates of hundreds of Mpbps

### Fiber Optics

- thin flexible medium that conducts pulses of light, with each pulse representing a bit
- immune to electromagnetic interference
- very low signal attenuation up to 100 kilometers
- many long distance telephone networks now use fiber optics
- data rates up to 10s or even 100s of Gbps

### Terrestrial Radio Channels

- Radio channels carry signals in the electromagnetic spectrum
- no physical wire, can penetrate walls, can potentially carry a signal for long distances
- broadly classified into two types:
	- operate in local areas (ten to few hundred meters). Ex: wireless LAN technologies described in 1.2.2
	- operate in wide area (tens of kilometers). Ex: cellular access technologies

### Satellite Radio Channels

- A communication satellite links two or more Earth-based microwave transmitter/receivers, known as ground stations
- The satellite receives transmissions on one frequency band, regenerates the signal using a repeater (discussed below), and transmits the signal on another frequency.
- two types
	- geostationary satellites
	- low-earth orbiting (LEO) satellites

# 1.3 The Network Core

## 1.3.1 Packet Switching

- In a network application, end systems exchange **messages** with each other
- To send a message from a source end system to a destination end system, the source breaks long messages into smaller chunks of data known as **packets**
- Packet = L bits, Transmission rate of link = R bits/sec, Time = Packet size / Transmission rate i.e. L/R seconds

### Store-and-Forward Transmission

- Most packet switches use **store-and-forward transmission** at the inputs to the links 
- Store-and-forward transmission means that the packet switch must receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link
![[store-and-forward-packet-switching.png]]

Each packet size = L bits
Each Link Transmission rate = R bps

General case of sending one packet from source to destination over a path consisting of *N* links each of rate R (thus there are N-1 routers between source and destination) =
d (end-to-end) = N L / R

For above diagram, N = 2 so 2L / R is the time taken to transmit 1 packet.

### Queuing Delays and Packet Loss

- Each packet switch has multiple links attached to it
- For each attached link, the packet switch has an **output buffer**, which stores packets that the router is about to send into that link
- if link is busy then packet will have to wait in output buffer, this is called **queuing delays**
- **packet loss** : if output queue is full then either the next incoming packet or a packet from the queue will be dropped
![[packet-switching.png]]

### Forwarding Tables and Routing Protocols

>[!question] How does the router determine which link it should forward the packet onto?
>Router uses a packet's destination address to index a forwarding table and determine the appropriate outbound link.

- In the Internet, every end system has an address called an IP address (has a hierarchical structure like postal address)
- When a source end system wants to send a packet to a destination end system, the source includes the destination’s IP address in the packet’s header
- each router has a **forwarding table** that maps destination addresses (or portions of the destination addresses) to that router’s outbound links

## 1.3.2 Circuit Switching

- There are two fundamental approaches to moving data through a network of links and switches: **circuit switching** and **packet switching**
- In circuit-switched networks, the resources needed along a path (buffers, link transmission rate) to provide for communication between the end systems are *reserved* for the duration of the communication session between the end systems
- In packet-switched networks, these resources are not reserved; a session’s messages use the resources on demand and, as a consequence, may have to wait (that is, queue) for access to a communication link
- Traditional telephone networks are examples of circuit-switched networks
![[simple-circuit-switched-network.png]]
Each circuit gets 1/4th transmission rate of the original link. If each link between switches has a transmission rate of 1 Mbps, then each end-to-end circuit gets 250 kbps of dedicated transmission rate.

### Multiplexing in Circuit-Switched Networks

> A circuit in a link is implemented with either **frequency-division multiplexing (FDM)** or **time-division multiplexing (TDM)**

**Frequency Division Multiplexing**
- With FDM, the frequency spectrum of a link is divided up among the connections established across the link
- Specifically, the link dedicates a frequency band to each connection for the d­uration of the connection. In telephone networks, this frequency band typically has a width of 4 kHz (that is, 4,000 hertz or 4,000 cycles per second). The width of the band is called, not surprisingly, the **bandwidth**.
![[fdm.png]]


**Time Division Multiplexing**
- For a TDM link, time is divided into frames of fixed duration, and each frame is divided into a fixed number of time slots
- When the network establishes a connection across a link, the network dedicates one time slot in every frame to this connection. These slots are dedicated for the sole use of that connection, with one time slot available for use (in every frame) to transmit the connection’s data
- Transmission rate = Frame rate x no. of bits in a slot. Example : 8000 frames per second and each slot consists of 8 bits, then the transmission rate of each circuit = 8000 * 8 = 64 kbps.
![[tdm.png]]

### Packet Switching Versus Circuit Switching

- Critics of packet switching have often argued that packet switching is not suitable for real-time services (for example, telephone calls and video conference calls)
- because of its variable and unpredictable end-to-end delays (due primarily to variable and unpredictable queuing delays)
- Proponents of packet switching argue that
	- (1) it offers better sharing of transmission capacity (1 Mbps link) (35 users) than circuit switching (10 users) and 
	- (2) it is simpler, more efficient, and less costly to implement than circuit switching

## 1.3.3 A Network of Networks

- end systems connect to the internet via ISP
- an ISP can be a cable or telco but also a university or company

>ISPs must be interconnected so that all end systems can send packets to each other

One naive approach would be to have each access ISP directly connect with every other access ISP all over the world. (costly for access ISPs)

**Network Structure I**
Interconnect all of the access ISPs with a *single global transit* ISP (imaginary), which has at least one router near each of the hundreds of thousands of access ISPs. Global transit ISP (**provider**) will charge access ISP (**customer**) based on amount of traffic it exchanges with itself.

**Network Structure 2**
*multiple* global transit ISPs and they must interconnect. Although some ISPs do have impressive global coverage and do directly connect with many access ISPs, no ISP has presence in each and every city in the world.

**Network Structure 3**
To further complicate matters, in some regions there may be a **larger regional ISP** (possibly spanning an entire country) to which the smaller **regional ISPs** in that region connect. This larger regional ISP then connects to a **tier-1 ISP**.

**Network Structure 4**
To build a network that more closely resembles today’s Internet, we must add points of presence (PoPs), multi-homing, peering, and Internet exchange points (IXPs) to the hierarchical Network Structure 3.

A **PoP** is simply a group of one or more routers (at the same location) in the provider’s network where customer ISPs can connect into the provider ISP. For a customer network to connect to a provider’s PoP, it can lease a high-speed link from a third-party telecommunications provider to directly connect one of its routers to a router at the PoP.

Any ISP (except for iter-1 ISPs) may choose to **multi-home**, that is, to connect to two or more provider ISPs. When an ISP multi-homes, it can continue to send and receive packets into the Internet even if one of its providers has a failure.

The amount that a customer ISP pays a provider ISP reflects the amount of traffic it exchanges with the provider. To reduce these costs, a pair of nearby ISPs at the same level of the hierarchy can **peer**, that is, they can directly connect their networks together so that all the traffic between them passes over the direct connection rather than through upstream intermediaries. When two ISPs peer, it is typically settlement-free, that is, neither ISP pays the other.

Along these same lines, a third-party company can create an **Internet Exchange Point (IXP)**,
which is a meeting point where multiple ISPs can peer together. An IXP is typically in a stand-alone building with its own switches.

**Network Structure 5**
add **content-provider networks** to Network Structure 4. Content provider network example: Google.

Google private network attempts to “bypass” the upper tiers of the Internet by peering (settlement free) with lower-tier ISPs, either by directly connecting with them or by connecting
with them at IXPs.

However, because many access ISPs can still only be reached by transiting through tier-1 networks, the Google network also connects to tier-1 ISPs, and pays those ISPs for the traffic it exchanges with them. By creating its own network, a content provider not only reduces its payments to upper-tier ISPs, but also has greater control of how its services are ultimately delivered to end users.

![[interconnection-of-isps.png]]

# 1.4 Delay, Loss, and Throughput in Packet-Switched Networks

Ideally, we would like Internet services to be able to move as much data as we want between any two end systems, instantaneously, without any loss of data.

## 1.4.1 Overview of Delay in Packet-Switched Networks

When a packet travels from one node (host or router) to the subsequent node (host or router) along this path, the packet suffers from several types of delays at *each* node along the path. Together all the delays accumulate to give a **total nodal delay**.

### Types of Delay

![[nodal-delay.png]]

### Processing Delay

The time required to examine the packet’s header and determine where to direct the packet is part of the **processing delay**

### Queuing Delay

At the queue, the packet experiences a **queuing delay** as it waits to be transmitted onto the link.

### Transmission Delay

Packet size = L bits, R = transmission rate bits/second
The **transmission delay** is L/R. This is the amount of time required to push (that is, transmit) all of the packet’s bits into the link.

### Propagation Delay

Once a bit is pushed into the link, it needs to propagate to router B. The time required to propagate from the beginning of the link to router B is the **propagation delay.**

Propagation speed (**s**) ranges in - 2 x 10^8 m/s to 3 x 10^8 m/s
Distance (**d**) - between router A and B
**Propagation delay** = d/s

### Comparing Transmission and Propagation Delay

**Analogy**: Segments between tollbooth = links
Tollbooths = routers
Car = bit
Caravan of 10 cars = packet
Speed of car = 100 km/hr
Distance between tollbooths = 100 km
Tollbooth transmission rate = 1 car/12 sec

>entire caravan must be stored at the tollbooth before it can begin to be forwarded.

Time required by tollbooth to push the entire caravan onto the highway = (10 cars) / (5 cars/minute)= 2 minutes (this time is analogous to transmission delay in a router)

Time required for a car to travel from the exit of one tollbooth to the next tollbooth = 100 km/(100 km/hr) = 1 hour (this time is analogous to propagation delay)

==Nodal delay = processing + queuing + transmission + propagation==
(nodal delay is the delay at **one router only**)

![[caravan-analogy.png]]

## 1.4.2 Queuing Delay and Packet Loss

- The most complicated and interesting component of nodal delay is the queuing delay
- Unlike the other three delays, the queuing delay can vary from packet to packet
- Factors affecting queuing delay:
	- rate at which traffic arrives at the queue
	- transmission rate of the link
	- nature of arriving traffic (periodically or arrives in bursts)

**Assumptions**
Average rate at which packets arrive at the queue = a (is in units of packets/sec)
Transmission rate = R (bits/sec)
Each packet size = L bits
queue is very bit (can hold essentially an infinite number of bits)

**Average rate at which bits arrive in the queue = La bits/sec**

==Traffic intensity = La / R ==, If :
- La / R > 1 then queue will increase without bound and the queuing delay will approach infinity
- La / R <= 1 then nature of traffic (bursts or periodic) impacts the queuing delay
![[attachments/average-queuing-delay-vs-traffic-intensity.png]]

### Packet Loss

The fraction of lost packets increases as the traffic intensity (*La/R*) increases. Therefore, performance at a node is often measured not only in terms of delay, but also in terms of the probability of packet loss.

## 1.4.3 End-to-End Delay

**Network setup assumptions**:
- There are **N − 1 routers** between source and destination  
	-So total **nodes = N** (source + routers)
- Network is **uncongested**  
	- **Queuing delay ≈ 0**
- Each node has the **same delays**
- Packet size = **L bits**
- Transmission rate = **R bits/sec**

The packet goes through N nodes, and each node adds the same delay so,
total delay = (sum of delays at one node) x (number of nodes)

end-to-end-delay = N (processing delay + transmission delay + propagation delay)


## 1.4.4 Throughput in Computer Networks

- In addition to delay and packet loss, another critical performance measure in computer networks is end-to-end throughput
- **instantaneous throughput** - (bits/sec) you can see this when you download a file from the internet (4.6 Mb/s)
- **average throughput** = F/T bits/sec; where F is the size of file in bits; T is time it took for host to receive all F bits in seconds
- Throughput is the **minimum** of transmission rates because the slowest link acts as a bottleneck, limiting the rate at which data can be delivered to the destination. Faster links cannot increase end-to-end throughput.


![[throughput.png]]

In (a) suppose that all the links in the core of the communication network have very high transmission rates, much higher than Rs and Rc then throughput = min {Rs, Rc}

In (b), if R = 200 Mpbs, Rs = 5 Mbps, Rc = 2 Mbps then each pair will get 20 Mbps transmission rate. In this case throughput will again be min {Rs, Rc}.
(Case where R is 100s of times larger than Rs and Rc)

However, If R = 5 Mbps , Rs = 2 Mbps, Rc = 1 Mbps then each pair will get 500 Kbps transmission rate. In this case the highest transmission link (R) became the bottleneck link and hence the throughput is now 500 Kbps.

So throughput depends on :
- transmission rates of the links over which data flows (a)
- intervening traffic (b)

>Therefore, the constraining factor for throughput in today’s Internet is typically the access network.


# 1.5 Protocol Layers and Their Service Models

## 1.5.1 Layered Architecture

As long as the layer provides the same service to the layer above it, and uses the same services from the layer below it, the remainder of the system remains unchanged when a layer’s implementation is changed.

### Protocol Layering

| Application |
| ----------- |
| Transport   |
| Network     |
| Link        |
| Physical    |
**Five-layer internet protocol stack**

### Application Layer

- network applications
- HTTP (Web document request and transfer)
- SMTP (transfer of e-mail messages)
- FTP (transfer of files between end systems)
- packet of information at this layer is called **messsage**

### Transport Layer

- transports application-layer messages between application endpoints
- [[TCP]] & [[UDP]]
- transport-layer packet is called **segment**

### Network Layer

- moves network layer packets from one host to another
- network layer packets are called **datagrams**
- IP protocol, routing protocols

### Link Layer

- move a packet from one node (host or router) to the next node in **route**
- Protocols example: Wifi, Ethernet, PPP, etc.
- link-layer packets as **frames**

## 1.5.2 Encapsulation

>[!note] Hosts implement all five layers; this is consistent with the view that the internet architecture puts much of its complexity at the edges of the network.


![[layers-in-nw-devices.png]]

Each layer adds its own header information, so on the receiver side the information can be delivered correctly.

At each layer, a packet has two types of fields:
- header fields
- **payload field**

# 1.6 Networks Under Attack

## The Bad Guys Can Put Malware into Your Host Via the Internet

Much of the malware out there today is **self-replicating**:  once it infects one host, from that host it seeks entry into other hosts over the Internet.

Once malware infects our device it can do all kinds of devious things, including deleting our files and installing spyware that collects our private information. Our compromised host may also be enrolled in a network of thousands of similarly compromised devices, collectively known as a **botnet**, which the bad guys control and leverage for spam
e-mail distribution or distributed denial-of-service attacks against targeted hosts.

## The Bad Guys Can Attack Servers and Network Infrastructure

**Denial of Service (DoS) attacks**
A DoS attack renders a network, host, or other piece of infrastructure unusable by legitimate users. Most DoS attacks fall into one of three categories:
- **Vulnerability attack** - If the right sequence of packets is sent to a vulnerable application or operating system, the service can stop or, worse, the host can crash.
- **Bandwidth flooding** - The attacker sends a deluge of packets to the targeted host—so many packets that the target’s access link becomes clogged, preventing legitimate packets from reaching the server.
- **Connection flooding** - The attacker establishes a large number of half-open or fully open TCP connections at the target host. The host can become so bogged down with these bogus connections that it stops accepting legitimate connections.

## The Bad Guys Can Sniff Packets

>Always accept the possibility that someone may be recording copies of your packets. Best defense against packet sniffing is **cryptography**.

WiFi or wireless internet provides convenient but is vulnerable. Someone might place a passive receiver in the vicinity of the wireless transmitter, that receiver can obtain a copy of every packet that is transmitted!. 

A passive receiver that records a copy of every packet that flies by is called a **packet sniffer**.

## The Bad Guys Can Masquerade as Someone You Trust

The ability to inject packets into the Internet with a false source address is known as **IP spoofing**, and is but one of many ways in which one user can masquerade as another user.

To solve this problem, we will need *end-point authentication*, that is, a mechanism that will allow us to determine with certainty if a message originates from where we think it does.

---

