# 2.1 Principles of Network Applications

At the core of network application development is writing programs that run on different end systems and communicate with each other over the network. 

For example, in the Web application there are two distinct programs that communicate with each other: the browser program running in the user’s host  and the Web server program running in the Web server's host.

## 2.1.1 Network Application Architectures

- Before coding, you should have a broad architectural plan for your application
- network architecture (5 layer) is different from **application architecture**
- two predominant architectural paradigms used in modern network applications:
	- [[client server architecture]]
	- peer-to-peer ([[P2P ]]) architecture

## 2.1.2 Processes Communicating

Before building your network application, you also need a basic understanding of how the programs (**processes** in OS terminology), running in multiple end systems, communicate with each other.

Processes on two different end systems communicate with each other by exchanging **messages** across the computer network. 

### Client and Server Processes

A network application consists of pairs of processes that send messages to each other over a network.

>In the context of a communication session between a pair of processes, the process that initiates the communication (that is, initially contacts the other process at the beginning of the session) is labeled as the **client**. The process that waits to be contacted to begin the session is the **server**.

 In P2P file sharing, when Peer A asks Peer B to send a specific file, Peer A is the client and Peer B is the server in the context of this specific communication session.

### The Interface Between the Process and the Computer Network

Any message sent from one process to another must go through the underlying network. A process sends messages into, and receives messages from, the network through a software interface called a **socket**. A **socket** is also referred to as the **Application Programming Interface (API)** between the application and the network.

**Analogy**: Process => house; socket => door
![[socket-communication.png]]

### Addressing Processes

In order for a process running on one host to send packets to a process running on another host, the receiving process needs to have an address.

To identify the receiving process, two pieces of information need to be specified:
- the address of the host (**IP address**)
- an identifier that specifies the receiving process (more precisely, receiving socket) in the destination host (**port number**)

 Popular applications have been assigned specific port numbers. For example, a Web server is identified by port number 80. 

## 2.1.3 Transport Services Available to Applications

Many networks, including the Internet, provide more than one transport-layer protocol. When you develop an application, you must choose one of the available transport-layer protocols.

The possible services that a transport-layer protocol can offer to applications can be classified along four dimensions:
- reliable data transfer
- throughput
- timing
- security

### Reliable Data Transfer

If a protocol provides a guaranteed data delivery service, it is said to provide **reliable data transfer**. 

When a transport-layer protocol doesn’t provide reliable data transfer, some of the data sent by the sending process may never arrive at the receiving process. This may be acceptable for **loss-tolerant applications,** most notably multimedia applications such as conversational audio/video that can tolerate some amount of data loss. In these multimedia applications, lost data might result in a small glitch in the audio/video—not a crucial impairment.

### Throughput

Because other sessions (network apps) will be sharing the bandwidth along the network path, and because these other sessions will be coming and going, the available throughput can fluctuate with time.

A transport-layer protocol could provide  guaranteed available throughput at
some specified rate. (r bits/sec)

Such a guaranteed throughput service would appeal to many applications. For example internet telephony application that encodes voice at 32 kbps. 

Applications that have throughput requirements are said to be **bandwidth-sensitive applications** 
**Elastic applications** can make use of as much, or as little, throughput as happens to
be available. Electronic mail, file transfer, and Web transfers are all elastic applications.

### Timing

A transport-layer protocol can also provide timing guarantees.  An example guarantee might be that every bit that the sender pumps into the socket arrives at the receiver’s socket no more than 100 msec later.

Such a service would be appealing to interactive real-time applications, such as Internet telephony, virtual environments, teleconferencing, and multiplayer games.

### Security

Finally, a transport protocol can provide an application with one or more security services. (encryption / decryption)

## 2.1.4 Transport Services Provided by the Internet

Let’s now get more specific and examine the type of transport services provided by the Internet. The Internet makes two transport protocols available to applications, UDP and TCP.

![[requirements-of-selected-network-apps.png]]

### TCP Services

- **connection-oriented service** : after handshaking, establish a **TCP connection** between client and server. The connection is a full-duplex connection. Close the connection when you are done.
- **reliable data transfer service** : guaranteed delivery with no missing or duplicate bytes

TCP also includes a congestion-control mechanism, a service for the ­ general welfare of the Internet rather than for the direct benefit of the communicating processes.

The TCP congestion-control mechanism throttles a sending process (client or server) when the network is congested between sender and receiver.

#### TLS (Transport Layer Security)

TCP can be easily enhanced at the application layer with TLS to provide security services. TLS is not a third internet transport layer protocol and also it isn't on the same level as TCP and UDP. It is an enhancement of TCP, with the enhancements being implemented in the application layer.

if an application wants to use the services of TLS, it needs to include TLS code (existing, highly optimized libraries and classes) in both the client and server sides of the application.

### UDP Services

- connectionless 
- unreliable data transfer service
- Furthermore, messages that do arrive at the receiving process may arrive out of order.
- no congestion-control mechanism

### Services Not Provided by Internet Transport Protocols

- throughput and timing guarantees
- time-sensitive applications often work fairly well because they have been designed to cope, to the greatest extent possible, with this lack of guarantee
- In summary, today’s Internet can often provide satisfactory service to time-sensitive applications, but it cannot provide any timing or throughput guarantees

![[popular-apps-their-app-and-transport-layer-protocols.png]]

## 2.1.5 Application-Layer Protocols

An **application-layer protocol** defines:
- The types of messages exchanged, for example, request messages and response messages
- The syntax of the various message types, such as the fields in the message and how the fields are delineated
- The semantics of the fields, that is, the meaning of the information in the fields
- Rules for determining when and how a process sends messages and responds to messages

The Web’s application-layer protocol, HTTP, defines the format and sequence of messages exchanged between browser and Web server.

## 2.1.6 Network Applications Covered in This Book

- web
- electronic mail
- directory service
- video streaming
- p2p applications


# 2.2 The Web and HTTP

the Web and its protocols serve as a platform for YouTube, Web-based e-mail (such as Gmail), and most mobile Internet applications, including Instagram and Google Maps.

## 2.2.1 Overview of HTTP

>**HyperText Transfer Protocol (HTTP)**

HTTP defines how Web clients request Web pages from Web servers and how servers transfer Web pages to clients.

A **Web page** (also called a document) consists of objects. An object is simply a file—such as an HTML file, a JPEG image, a Javascrpt file, a CCS style sheet file, or a video clip—that is addressable by a single URL.

 For example, if a Web page contains HTML text and five JPEG images, then the Web page has six objects.

