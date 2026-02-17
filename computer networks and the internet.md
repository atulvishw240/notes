
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

- asymmetric access
- makes use of the cable television company’s existing cable television infrastructure
![[hybrid-fiber-coaxial.png]]

**Fiber node**: neighborhood-level junctions (supports 500 - 5000 homes)
**CMTS**: Cable Modem Termination System