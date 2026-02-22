
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

