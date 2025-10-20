---
layout: post
title:  "Networking: Introduction"
date:   2025-10-12 20:43:12 +0300
categories: [networking]
---

## 0x0. Introduction
Before the world was connected... before a message could travel across continents in the blink of an eye… computers were silent, isolated giants. Massive machines, hidden in research labs and government facilities, stood alone—powerful, yet voiceless. Each one a locked island of information, unable to speak to another.

The world was changing. The Cold War loomed, and with it, a new kind of battlefield emerged—one not of bullets, but of data. The question was simple, yet revolutionary: What if machines could talk? In the late 1960s, the secretive U.S. government agency DARPA planted the seed of a digital revolution: [*ARPANET*](https://en.wikipedia.org/wiki/ARPANET). Four computers. Four connections. A single vision—to create a network that could survive even the unimaginable. This is how networking was born.

## 0x1. Networking
> A network is a set of hardware devices connected together, either physically or logically to allow them to exchange information.

As broad as this description of what networking is, in the end of the day, networking is just a way for devices to communicate with each other. When we have two or more devices connected together, we have a *network*. What is interesting is that we can have multiple independent networks communicating with each other in one larger network. In this larger network, each small block that creates it is called a *subnetwork*, and the large network consisting of two or more subnetworks we call an *internetwork*.

![Network, Subnetwork, Internetwork]({{site.baseurl}}/assets/images/network_subnetwork_internetwork.jpg)

### 0x1.1. Network types
The networks can be divided based on different criteria, but most often we classify them by:

#### 0x1.1.1. Relative distance between devices
  - ***Personal Area Networks (PANs)*** - A very short-range LAN with a range of only a few meters, intended mostly to connect together devices used by a single person. They often appear as wireless personal area networks (WPANs).

  - ***Local Area Networks (LANs)*** - Networks that connect relatively close devices — generally, within the same room or building.

  - ***Wireless Local Area Networks (Wireless LANs or WLANs)*** - LANs that connect the devices wirelessly.

  - ***Campus Area Networks (CANs)*** - Span multiple buildings in the same location. Often combining LAN and WAN.

  - ***Metropolitan Area Networks (MANs)*** - A network that spans a particular small region or a city, larger than LAN, but not large enough to be WAN.

  - ***Wide Area Networks (WANs)*** - Networks that connect together devices or other networks over a greater distance.

#### 0x1.1.2. By ownership:
  - ***Private*** - A network restricted to a specific organization or user group, offering controlled access and enhanced security.

  - ***Public*** - A network open to anyone (such as the internet), with minimal security and no access restrictions.

  - ***Hybrid*** - A network that combines both private and public elements, allowing secure communication and data sharing across both types.

#### 0x1.1.3. By the used topology:
  - ***Bus*** - A single central cable (the "bus") connects all devices in the network. Data can travel in both directions along the cable, and each device checks if the data is meant for it. If it's not — it passes it to the next. It's cheap and easy to implement, but if the main cable fails, the whole network goes down with it.

  ![Bus Topology]({{site.baseurl}}/assets/images/bus_topology.jpg)

  - ***Star*** - All devices are connected to a central hub or switch. Data flows through the hub, which manages traffic. It's easy to manage and implement. In case of a failing connection between a device and the central device, the whole network does not fail. But if the central device fails, the whole network fails with it.

  ![Star Topology]({{site.baseurl}}/assets/images/star_topology.jpg)

  - ***Extended Star*** - An extension of the star topology, where multiple star networks are connected to a central hub or switch. It scales easily but is still vulnerable if the central device fails.

  ![Extended Star Topology]({{site.baseurl}}/assets/images/extended_star_topology.jpg)

  - ***Tree*** - A hierarchical network topology that combines characteristics of star and bus topologies. The devices are connected in groups to a central node, forming a branching structure like a tree. It's scalable, but if the main trunk (node from which the tree structure starts branching) fails, large parts of the network may go down.

  ![Tree Topology]({{site.baseurl}}/assets/images/extended_star_topology.jpg)

  - ***Mesh*** - Every device is connected to every other device, either directly (full mesh) or partially (partial mesh). Offers multiple data paths. It's extremely fault-tolerant and reliable, but can be expensive to set up and maintain.

  ![Mesh Topology]({{site.baseurl}}/assets/images/mesh_topology.jpg)

## 0x2. Standardization
The computers communicate by following networking *protocols*, which are sets of rules, algorithms, messages and other mechanisms that enable networked devices to communicate effectively. The protocols are created with the help of international organizations that manage their standardization, such as:
  - International Organization for Standardization (*ISO*)
  - Institute of Electrical and Electronics Engineers (*IEEE*)
  - Information Technology Industry Council (*ITIC*)
  - International Telecommunication Union - Telecommunication Standardization Sector (*ITU-T*)
  - European Telecommunications Standards Institute (*ETSI*)

### 0x2.1. Standards
  - ***Proprietary*** - Standards owned by one particular organization.
  - ***Open*** - Are not owned by anyone. They are created by neutral organizations to ensure that compatible products can be designed and developed by many different companies. One of the critical factors in the success of the Internet has been its development using open standards!
  - ***De-Facto*** - A standard that is used as a universal standard just because over time it became widely used, not because it was developed and approved by a standards committee.

Standardization was achieved largely through building consensus through discussion about new technologies and protocols. If someone had a proposal for a new protocol or technology, or an idea for a change to an existing one, that person would create a memorandum describing it and circulate it to others. Since the goal was to solicit comments on the proposal, these memos were called **Requests for Comments (RFCs)**.

### 0x2.2. Network Layers, Models, and Architecture

#### 0x2.2.1. Layers
Networking technologies are most often divided by their functions into **layers**, where each layer is responsible for performing a particular type of task, as well as interacting with the layers above and below it. Layers are conceptually arranged into a vertical stack. Lower layers are charged with more hardware-level tasks, also providing **services** for the higher layers, that can be used to implement more abstract functions such as implementing user applications.

#### 0x2.2.2. Models
One other important benefit of layering is that it makes it possible for different technologies to interoperate. For this to be possible, it is necessary for everyone to agree on how layers will be defined and used. The most common tool for this purpose is a **networking model**. The model describes what the different layers are in the network, what each is responsible for doing, and how they interact. The most common general model in use today is the *Open Systems Interconnection (OSI)* Reference Model.

#### 0x2.2.3. Architecture
Closely related to the concept of a model is that of an **architecture**, which is essentially a set of rules that describes the function of some portion of the hardware and software that constitute a stack of layers. Such a rule-set usually takes the form of a specification or standard that describes how equipment and programs using the technology must behave.

## 0x3. Open System Interconnection (OSI) Model

The Open Systems Interconnection Reference Model (OSI Reference Model or OSI Model) provides a framework for breaking down complex internetworks into components that can more easily be understood and utilized. The model defines networking functions not as a large, complicated whole, but as a set of layered, modular components, each of which is responsible for a particular function. The suite became a very useful tool for both education and development. But while the model defines a framework for understanding networks, it never achieved widespread success because of its high abstraction, and the fact that not all networking components, protocols, and devices operate only at one specific layer.

### 0x3.1. The OSI Model Structure
The OSI model is comprised of seven conceptual layers (numbered from 1 to 7), where each layer is performing specific functions (higher the layer — higher the abstraction of the functions).

Each layer (except layer 7, because it's the highest layer in the model) provides **services** to the layer above it. A service is the set of operations or capabilities that a lower OSI layer offers to the layer above it. Each layer (other than layer 1) uses services provided from the layer below it.

Each layer is independent of the others, but provides an **interface**, by which it communicates with its adjacent layers — we call that communication *vertical communication*, because it's up or down the stack of layers. Also, each layer communicates with its corresponding layer on the other device via **protocols**, which are sets of rules or procedures that define the communication between devices at the same layer — we call that communication *horizontal communication*.

![The Open Systems Interconnection Reference Model's Layers]({{site.baseurl}}/assets/images/OSI_model_dark.png)

### 0x3.2. Data encapsulation - PDUs and SDUs
At every layer (except L1), the horizontal communications take the form of a message that is sent to at least one more device. Since these messages are the mechanism for communicating information between *protocols*, they are generally called **Protocol Data Units (PDUs)**. Each PDU has its specific format that implements the features and requirements of the protocol.

When a PDU gets passed to the layer below, the message gets called a **Service Data Unit (SDU)**, because it's a unit of data passed by a service. That way the message gets encapsulated in the PDU of each layer from its starting layer (Layer N) down to L1 — we call this process **encapsulation**. This process is done in reverse by the recipient of the message, who performs **decapsulation**.

### 0x3.3. OSI Layers
#### 0x3.3.1. Physical (Layer 1)
It's the lowest layer in the OSI Reference Model. The technologies at this layer deal with networking hardware specifications, data encoding, signaling, data transmission, and reception. It's closely related to L2.

#### 0x3.3.2. Data Link (Layer 2)
The Data Link layer defines most of the LAN and WLAN technologies. It's responsible for logical link control, media access control, hardware addressing, error detection and handling, and defining physical layer standards. It's often divided into:
  - ***Logical Link Control*** - Refers to the functions required for the establishment and control of logical links between two devices on a network.
  - ***Media Access Control*** - Refers to the procedures used by devices to control access to the network medium (the transmission medium) to avoid conflicts.

#### 0x3.3.3. Network (Layer 3)
If the Data Link layer is the one that basically defines the boundaries of what is considered a network, the Network layer is the one that defines how internetworks (interconnected networks) function. The Network layer is the lowest one in the OSI model that is concerned with actually getting data from one computer to another even if it is on a remote network.

#### 0x3.3.4. Transport (Layer 4)
The Transport layer is responsible for enabling end-to-end communication between application processes, which it accomplishes in part through the use of process-level addressing and multiplexing/demultiplexing. Transport layer protocols are responsible for dividing the application's data into blocks for transmission, and may be either **connection-oriented** (protocols that require a logical connection to be established between two devices before transferring data, such as TCP) or **connectionless** (protocols that do not establish a connection between devices; as soon as a device has data to send, it just sends it — such as UDP).

#### 0x3.3.5. Session (Layer 5)
The Session layer provides functions for establishing and managing sessions between software processes. The Session layer technologies are often implemented as sets of APIs (Application Programming Interfaces).

#### 0x3.3.6. Presentation (Layer 6)
Protocols at this layer take care of manipulation tasks that transform data from one representation to another, such as translation, compression, and encryption. In some cases, no such functions are required in a particular networking stack.

#### 0x3.3.7. Application (Layer 7)
Application protocols are defined at this layer, which implement specific user applications and other high-level functions.

![OSI Reference Model Layers]({{site.baseurl}}/assets/images/OSI_model.png)

## 0x4. The TCP/IP Protocol Suite
TCP/IP uses its own four-layer architecture that corresponds roughly to the OSI Reference Model, providing a framework for the various protocols that comprise the suite. The TCP/IP protocols were initially developed as part of the research network developed by the United States Defense Advanced Research Projects Agency (DARPA or ARPA), called ARPANET.

While TCP/IP is not the only internetworking protocol suite, it is definitely the most important one to date. Its unparalleled success is due to a wide variety of factors. These include its technical features, such as its routing-friendly design and scalability, its historical role as the protocol suite of the Internet, and its open standards and development process.

### 0x4.1. TCP/IP Services
Conceptually, the TCP/IP services can be split into two groups:
  - Services provided to other protocols - Consist of the core functions implemented by the main TCP/IP protocols designed to actually accomplish the internetworking functions of the protocol suite.
  - Services provided to end users directly - HTTP, FTP, ... and other services.

### 0x4.2. Client-Server operation
The TCP/IP protocol suite is strongly oriented around the notion of client-server network communication, where clients normally initiate communications by sending requests, and servers respond to such requests, providing the client with the desired data or an informative reply.

### 0x4.3. TCP/IP Architecture

![TCP/IP Protocol Suite Layers]({{site.baseurl}}/assets/images/TCP_model_layers.png)

#### 0x4.3.1. Network Access Layer
It's equivalent to the Physical and the Data Link layer in the OSI Reference Model. Protocols at this layer are PPP, Ethernet, Wi-Fi, ARP (though it's treated as OSI L2/L3 protocol in some sources, because we are requesting data about the Network layer).

#### 0x4.3.2. Internet Layer
Corresponds to the Network layer in the OSI Reference Model. The protocols at this layer are IP (IPv4 and IPv6), IP NAT, IPSec, ICMP/ICMPv4, ICMPv6, ND, and protocols used for message routing such as RIP, OSPF, GGP, HELLO, IGRP, EIGRP, BGP, EGP.

#### 0x4.3.3. Transport Layer
Corresponds to the Transport layer in the OSI Reference Model. Protocols at this layer are TCP and UDP.

#### 0x4.3.4. Application Layer
This is the highest layer in the TCP/IP protocol suite and is a rather broad layer, encompassing layers five through seven in the OSI Reference Model. Protocols at this layer are DNS, NFS, SNMP, FTP, SMTP, HTTP, and many more.

## 0x5. Conclusion

Networking is the foundation of modern communication and connectivity. From the early days of ARPANET to the globally interconnected Internet, the evolution of networking has been driven by standardization, layered architecture, and protocol design.

Though this post is on the dry side, I hope it helps you better understand the foundations of networking!
