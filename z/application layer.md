# 2.1 Principles of Network Applications

At the core of network application development is writing programs that run on different end systems and communicate with each other over the network. 

For example, in the Web application there are two distinct programs that communicate with each other: the browser program running in the user’s host  and the Web server program running in the Web server's host.

You can't write application software for network-core devices, such as routers or link-layer switches because these devices they don't function at the network layer.

## 2.1.1 Network Application Architectures

- Before coding, you should have a broad architectural plan for your application
- network architecture (5 layer) is different from **application architecture**
- two predominant architectural paradigms used in modern network applications:
	- [[client server architecture]]
	- peer-to-peer ([[z/P2P]]) architecture

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

A **Web page** (also called a document) consists of objects. An **object** is simply a file—such as an HTML file, a JPEG image, a Javascrpt file, a CCS style sheet file, or a video clip—that is addressable by a single URL.

 For example, if a Web page contains HTML text and five JPEG images, then the Web page has six objects.
![[http-request-response-behavior.png]]

When a user requests a Web page (for example, clicks on a hyperlink), the browser sends HTTP request messages for the objects in the page to the server. The server receives the requests and responds with HTTP response messages that contain the objects.

>HTTP uses TCP as its underlying transport protocol.

**Socket-interface** is the door between the client/server process and the TCP connection.

It is important to note that the server sends requested files to clients without storing any state information about the client.  Because an HTTP server maintains no information about the clients, HTTP is said to be a **stateless protocol**.

## 2.2.2 Non-Persistent and Persistent Connections

When this client-server interaction is taking place over TCP, the application developer needs to make an important decision—should each request/response pair be sent over a *separate* TCP connection, or should all of the requests and their corresponding responses be sent over the *same* TCP connection? In the former approach, the application is said to use **non-persistent connections**; and in the latter approach, **persistent connections**. 

>HTTP uses **persistent connections** in its default mode

### HTTP with Non-Persistent Connections

Each TCP connection is closed after the server sends the object - the connection does not persists for other objects.

>[!note] Each non-persistent TCP connection transports exactly one request message and one response message.

**Three way handshake** : the client sends a small TCP segment to the server, the server acknowledges and responds with a small TCP segment, and, finally, the client acknowledges back to the server.

### HTTP with Persistent Connections

With HTTP/1.1 persistent connections, the server leaves the TCP connection open after sending a response. Subsequent requests and responses between the same client and server can be sent over the same connection.

These requests for objects can be back-to-back, without waiting for replies to pending requests (**pipelining**). When the server receives the back-to-back requests, it sends the objects back-to-back.

>[!note] The default mode of HTTP uses persistent connections with pipelining. 

>HTTP is an **application layer protocol.**

## 2.2.3 HTTP Message Format

### HTTP Request Message

![[attachments/general-format-of-http-req-message.png]]

![[attachments/an-http-request-message.png]]

The first line is called **request line** and the subsequent lines are called **header lines**.

If you use **POST** method, then the data will be sent via **entity body**.

>[!question] Why do we need the host line? There's already a TCP connection in place to the host. Find the answer in section 2.2.5 (that line is required by the Web Proxy Caches)

The HEAD method is similar to the GET method. When a server receives a request with the HEAD method, it responds with an HTTP message but it leaves out the requested object. Application developers often use the HEAD method for debugging.

### HTTP Response Message

![[attachments/general-http-reponse-format.png]]

![[attachments/sample-http-response-method.png]]

**Entity body** contains the requested object itself.
**Conent-Length** : indicates the number of bytes in the object being sent

**Little experiment**
```
telnet gaia.cs.umass.edu 80
GET /kurose_ross/interactive/index.php HTTP/1.1
Host: gaia.cs.umass.edu
```

## 2.2.4 User-Server Interaction: Cookies

HTTP is a stateless protocol but often times you would like to identify users on your website, either because you want to restrict user access or because you want to serve content as a function of user identity. (amazon or flipkart account).

For these purposes HTTP uses cookies.  A cookie technology has four components:

 1. a cookie header line in the HTTP response message
 2. a cookie header line in the HTTP request message
 3. a cookie file kept on the user’s end system and managed by the user’s browser
 4. a back-end database at the Web site. 

![[attachments/http-cookies.png]]

## 2.2.5 Web Caching

A **Web cache**—also called a **proxy server**—is a network entity that satisfies HTTP requests on the behalf of an origin Web server. The Web cache has its own disk storage and keeps copies of recently requested objects in this storage.

A browser can be configured so each request first goes to the Web cache. If web cache doesn't have that resource then it opens a TCP connection to the original server and request for the resource. It then stores a copy of this resource on itself and send it to the client on the existing TCP connection between itself and client.

![[attachments/proxy-server.png]]

Advantages of **web caches**:
1. can substantially reduce the response time for a client request
2. can substantially reduce traffic on an institution's access link to the internet. By reducing traffic, the institution does not have to upgrade bandwidth as quickly, thereby reducing costs.

### The Conditional GET

Although caching can reduce user-perceived response times, it introduces a new problem the object housed in the Web server may have been modified since the copy was cached at the client.

Solution: **conditional GET**

 An HTTP request message is a so-called conditional GET message if
1. the request message uses the GET method and 
2. the request message includes an `If-Modified-Since`: header line.

## 2.2.6 HTTP/2

>[!question] Why HTTP/2? What's the problem with HTTP/1.1?

Recall that HTTP/1.1 uses persistent TCP connections, 

## 2.3 Electronic Mail in the Internet

Internet Mail system has three major components:
- user agents (example Microsoft Outlook, Gmail, Apple Mail)
- mail servers
- Simple Mail Transfer Protocol (SMTP)

Mail servers form the core of the email infrastructure. Each recipient has a **mailbox** located in one of the mail servers. SMTP uses TCP. SMTP is the principal application layer protocol for Internet electronic mail.

![[internet-mail-system.png]]

### 2.3.1 SMTP

