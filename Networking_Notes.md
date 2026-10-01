# Networking 

# Networking Fundamentals

These notes cover the basic concepts of computer networking that are important for understanding how devices communicate and form the foundation for cybersecurity.

---

## 1. Data Communication

Data communication is the exchange of data between two or more devices through a transmission medium such as a cable, optical fiber, or wireless network.

A data communication system mainly consists of five components:

1. **Sender** – The device that sends the data.
2. **Receiver** – The device that receives the data.
3. **Message** – The actual information being transmitted, such as text, images, audio, video, or files.
4. **Transmission Medium** – The path through which data travels, such as Ethernet cable, fiber optic cable, or wireless signals.
5. **Protocol** – A set of rules that defines how communication between devices takes place.

For example, when a laptop sends a file to another computer over Wi-Fi, the laptop acts as the sender, the other computer is the receiver, the file is the message, Wi-Fi is the transmission medium, and networking protocols control the communication.

---

## 2. Characteristics of Effective Data Communication

For communication to be effective, it should satisfy the following characteristics:

### Delivery

Data should reach the **correct destination**.

### Accuracy

Data should reach the receiver **without unwanted errors or modification**.

### Timeliness

Data should arrive within the required amount of time. This is especially important in real-time applications such as video calls, online gaming, and voice communication.

### Jitter

Jitter is the **variation in the delay of packet arrival**.

For example, if packets are expected every 20 ms but arrive after 20 ms, 35 ms, 15 ms, and 30 ms, the variation in their arrival time is called jitter.

High jitter can cause problems in applications such as VoIP and video conferencing.

---

## 3. Transmission Modes

Transmission mode defines the direction in which data can travel between communicating devices.

### Simplex

In simplex communication, data travels in **only one direction**.

Example:

`Sender → Receiver`

A keyboard sending information to a computer is a common example.

### Half Duplex

In half-duplex communication, both devices can send and receive data, but **not at the same time**.

Example:

`Device A ⇄ Device B`

Walkie-talkies are a common example.

### Full Duplex

In full-duplex communication, both devices can send and receive data **simultaneously**.

Example:

`Device A ⇆ Device B`

A phone call is a common example.

---

## 4. Network Criteria

A good network is generally evaluated on the basis of three major criteria:

### Performance

Network performance represents how efficiently a network transfers information.

It can be affected by:

- Throughput
- Latency
- Response time
- Number of users
- Available bandwidth
- Network hardware

**Throughput** represents the actual amount of data successfully transferred over a network within a particular amount of time.

### Reliability

Reliability represents how consistently a network operates without failure.

It depends on factors such as:

- Frequency of failures
- Recovery time after failure
- Availability of backup systems
- Fault tolerance

A reliable network should experience fewer failures and recover quickly when a failure occurs.

### Security

Network security protects systems and information from unauthorized access, modification, destruction, and disruption.

One of the fundamental concepts of cybersecurity is the **CIA Triad**:

- **Confidentiality** – Information should only be accessible to authorized users.
- **Integrity** – Information should not be changed or modified without authorization.
- **Availability** – Systems and information should remain accessible to authorized users when required.

The CIA Triad is one of the most important foundations of information security.

---

## 5. Types of Network Connections

Network connections can generally be classified as **Point-to-Point** and **Multipoint**.

### Point-to-Point Connection

A point-to-point connection provides a dedicated communication link between two devices.

Example:

`Device A -------- Device B`

Since the connection is dedicated to the two devices, the entire capacity of the link can be used by them.

### Multipoint Connection

In a multipoint connection, multiple devices share the same communication link.

Example:

          Device B
             |
Device A ----+---- Device C
             |
          Device D

The available capacity of the communication medium is shared between multiple connected devices.

---

# Network Topology

Network topology describes the **arrangement of devices and communication links in a network**.

It represents how computers, switches, routers, and other network devices are connected.

Network topology can be:

- **Physical topology** – The actual physical arrangement of devices and cables.
- **Logical topology** – How data logically travels through the network.

Common network topologies include Bus, Ring, Star, and Mesh.

---

## 6. Bus Topology

In a bus topology, all devices are connected to a single main communication cable called the **backbone**.

Example:

Device A
   |
================ Backbone ================
   |             |                |
Device B      Device C         Device D

Devices are connected to the backbone using connections traditionally referred to as **drop lines** and **taps**.

### Advantages

- Requires less cable than many other topologies.
- Simple for small networks.
- Relatively inexpensive.

### Disadvantages

- Failure of the main backbone can affect the entire network.
- Troubleshooting can be difficult.
- Network performance may decrease as more devices are added.

---

## 7. Ring Topology

In a ring topology, every device is connected to two neighboring devices, forming a circular structure.

Example:

        A
      /   \
     D     B
      \   /
        C

Data usually travels through the ring from one device to another until it reaches its destination.

In a basic single-ring network, failure of a device or communication link may interrupt communication. Some modern ring implementations use redundancy or dual rings to improve fault tolerance.

---

## 8. Star Topology

In a star topology, every device is connected to a central networking device such as a **switch or hub**.

Example:

           Device A
              |
Device B --- Switch --- Device C
              |
           Device D

Modern Ethernet networks commonly use switches rather than hubs.

### Advantages

- Easy to install and manage.
- Failure of one device's cable normally affects only that device.
- Easy to add or remove devices.
- Troubleshooting is relatively simple.

### Disadvantages

- Failure of the central switch can affect the entire network.
- Requires more cabling than a bus topology.

---

## 9. Mesh Topology

In a full mesh topology, every device has a direct connection with every other device in the network.

For `n` devices, the number of links required in a full mesh network is:

Links = n(n - 1) / 2

For example, if there are 4 devices:

Links = 4(4 - 1) / 2

Links = 4 × 3 / 2

Links = 6

Therefore, a full mesh network containing four devices requires six links.

### Advantages

- High reliability.
- Multiple communication paths are available.
- Failure of a single link usually does not stop the entire network.

### Disadvantages

- Requires a large amount of cabling.
- Expensive to install.
- Becomes complex as the number of devices increases.

---

# OSI Model and Peer-to-Peer Communication

The OSI model divides network communication into seven layers:

7. Application Layer  
6. Presentation Layer  
5. Session Layer  
4. Transport Layer  
3. Network Layer  
2. Data Link Layer  
1. Physical Layer  

When two computers communicate, corresponding layers logically communicate with each other using **peer-to-peer protocols**.

For example:

Application Layer  <-------->  Application Layer  
Transport Layer    <-------->  Transport Layer  
Network Layer      <-------->  Network Layer  

However, the data does not physically jump directly from one corresponding layer to another.

On the sender's device, data moves:

`Application → Presentation → Session → Transport → Network → Data Link → Physical`

It is then transmitted through the network.

At the destination, the process happens in reverse:

`Physical → Data Link → Network → Transport → Session → Presentation → Application`

This process is related to **encapsulation and decapsulation**, which are important concepts for understanding packet analysis and cybersecurity.

---
