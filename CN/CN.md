
# Throughput

Throughput is the actual rate at which data is successfully transmitted over a network or channel within a specific period.

# Repeater
 a **repeater** is a **network device used to regenerate and amplify signals** in order to extend the transmission distance of a network.


# Delay

time a packet takes to travel from source to destination

	1. Transmission delay: Amount of it takes for a router to push all the packets         into the link.
			Length/Transmission rate

	 2. Propagration delay: Amount of time it takes for a packet to travel from             point A to B through a Medium.
	         Distance/Propagation speed.

	 3. Processing delay: Amount of time it takes for a router to recieve the               packet from the input port do a processing like checking headers and                forward it
	 
	 4. Quiuing Delay: AMount of time spent by a packet in a queue. 



# Topologies

## Ring Topology
Devices are connected in a circular loop, forming a ring. Data travels in one direction around the ring, passing through every device until it reaches the destination

![[Pasted image 20251102202715.png]]

## Bus Topology

All devices are connected to a single central cable, called the bus. Data travels in both directions along the bus, and only the device addressed by the message responds.

![[Pasted image 20251102202810.png]]


## Star Topology

All devices are connected to a central hub or switch. Data passes through the hub before reaching its destination, allowing centralized management.

![[Pasted image 20251102202943.png]]


## Mesh Topology

Every device is directly connected to every other device. This provides many paths for data to travel, allowing for redundancy and fault tolerance.

![[Pasted image 20251102203031.png]]


## Tree Topology

A hierarchical topology that combines multiple star topologies onto a bus. Devices are organized in a parent-child relationship, much like branches of a tree.


![[Pasted image 20251102203054.png]]


## Hybrid Topology

A combination of two or more different topologies (such as star-bus or star-ring), used to leverage the strengths of each for specific requirements.

![[Pasted image 20251102203204.png]]



# DNS

Domain name system is a internet service that translates domain names into IP addresses.
If one DNS does not know the IP , it is forwarded to another DNS .. and so on

Distributed database design is used for faster DNS resolutions 

![[Pasted image 20251102203628.png]]

Two Types of Query resolution
1. Iterative
			Recursive resolution in DNS is a process where the DNS resolver (usually your local DNS server) takes full responsibility to get the final IP address for a domain name. When a client makes a recursive request, the resolver will query other DNS servers on the client's behalf, starting from the root servers, moving to the top-level domain (TLD) servers, and then to authoritative servers, until it gets a definitive answer or an error. The resolver then sends this final result back to the client, so the client makes only one request and the resolver handles the rest.


2. Recursive
			Iterative resolution, on the other hand, involves the client explicitly making queries step-by-step to different DNS servers. When the DNS resolver cannot answer from its cache, it responds to the client with the address of a DNS server closer to the answer (like a referral to the root server, then TLD server, and finally the authoritative server). The client then queries the next server itself. This process repeats until the client reaches the authoritative server with the final IP address or receives an error.



# circuit Switching 

Circuit Switching:  
Circuit switching is a connection-oriented communication method where a dedicated communication path (or circuit) is established between two devices before the data transfer begins. This circuit remains reserved exclusively for the entire duration of the communication session. It is commonly used in traditional telephone networks and real-time voice communication.

Key characteristics:

- The connection has three phases: establishment, data transfer, and release.
    
- The dedicated path guarantees bandwidth, leading to low latency and predictable performance.
    
- Data flows continuously along the same physical path.
    
- Circuit switching provides reliable communication but can be inefficient since the reserved bandwidth cannot be used by others even when no data is being sent.
    
- It requires call setup time before communication.
    
- The resource allocation is fixed and limited in scalability.
    
- Suitable for real-time applications like voice and video calls where low latency and steady connection are crucial.

Types:
		Space division switching
		 Time division switching


# Packet Switching
Packet switching is a connectionless communication method where data is divided into smaller units called packets, each independently routed through the network. Each packet contains source and destination addresses and may take different routes to reach the destination.

Key characteristics:

- No dedicated path; packets are forwarded based on routing decisions at each intermediate node.
    
- Bandwidth is shared dynamically among users, leading to efficient resource utilization.
    
- Packets may arrive out of order, experience varied delays, or get lost due to congestion.
    
- It uses store-and-forward switching, where intermediate nodes temporarily store packets before forwarding.
    
- It is scalable, cost-effective, and suitable for bursty or non-real-time data traffic such as internet browsing and email.
    
- Not ideal for real-time applications without additional quality of service mechanisms due to variable latency.

Types:
		Virtual Circuits
		 Datagram



# HTTP:
		HTTP (Hypertext Transfer Protocol) is an application-layer protocol used for transferring data over the web between clients (such as browsers) and servers. It follows a stateless, request-response model—each client request is matched with a server response, and the server does not retain information about the client’s previous requests. HTTP enables the loading of web pages and resources like images, videos, and scripts on the internet

| Feature                  | Persistent HTTP (Keep-Alive)                             | Non-Persistent HTTP                                |
| ------------------------ | -------------------------------------------------------- | -------------------------------------------------- |
| TCP Connection           | One TCP connection used for multiple requests/responses  | New TCP connection for each request/response       |
| Overhead                 | Lower overhead (connection reused)                       | Higher overhead (frequent setup/teardown)          |
| Default in Version       | HTTP/1.1 and later                                       | HTTP/1.0 (unless specified otherwise)              |
| Request-Response Pattern | Multiple objects fetched in sequence over one connection | Each object requires its own connection            |
| Efficiency               | More efficient, faster page load times                   | Less efficient, slower for pages with many objects |
| Connection Closure       | Remains open until client or server closes it            | Closed immediately after one response              |
| Example Scenario         | Downloading multiple images with a single connection     | Fetching several images opens many connections     |
- **Persistent HTTP:** The client opens a TCP connection to the server. Over this single connection, it can send multiple HTTP requests one after another, and receive multiple responses, without reopening a new connection each time. This dramatically reduces the delay caused by setting up and closing connections repeatedly and is especially efficient when a webpage requires multiple resources (images, stylesheets, scripts, etc.).[](https://vocal.media/education/difference-between-persistent-and-non-persistent-connection)​
    
- **Non-Persistent HTTP:** For each HTTP request (such as each image or script file), the client opens a new TCP connection, sends the request, receives the response, and then the connection is immediately closed. If a page requires multiple resources, each will incur the setup and teardown time for new connections, increasing total page load time


# SMTP

SMTP (Simple Mail Transfer Protocol) is a standard application-layer protocol used to transfer electronic mail (email) across networks, especially the Internet. It is responsible for sending, relaying, and forwarding email messages from senders to recipients.

SMTP operates using a client-server architecture and typically uses TCP port 25

- **Email Creation and Submission:** Users write emails using an email client (Mail User Agent, MUA) such as Outlook or Gmail. The email client connects to an SMTP server (Mail Submission Agent, MSA) and authenticates the user, usually via port 587.[](https://www.trout.software/resources/glossary/smtp-\(simple-mail-transfer-protocol\))​
    
- **Mail Transfer Process:** The SMTP server (Mail Transfer Agent, MTA) processes the outgoing message. If the recipient is in a different domain, the MTA consults the DNS MX records to find the destination mail server. Then, it transfers the message using SMTP via port 25.[](https://www.geeksforgeeks.org/computer-networks/simple-mail-transfer-protocol-smtp/)​
    
- **Relays and Gateways:** Emails may be relayed through one or more intermediate SMTP servers (relays) before reaching the final destination. If different email systems are involved, gateways translate between protocols.[](https://www.trout.software/resources/glossary/smtp-\(simple-mail-transfer-protocol\))​
    
- **Final Delivery and Access:** The destination SMTP server (Mail Delivery Agent, MDA) places the email in the recipient's mailbox. The recipient's email client later accesses the mailbox using retrieval protocols such as IMAP or POP3.



# OSI Model

![[Pasted image 20251106164620.png]]

The **OSI (Open Systems Interconnection) Model** is a conceptual framework that divides network communication into seven distinct "layers." Think of it as a 7-step assembly line for data

### Layer 7: The Application Layer

- **Main Function:** This is the "human" layer. It provides network services directly to the user's applications. It's the interface you see and interact with.
    
- **Key Concepts:** It's not the application itself (like your Chrome browser), but the protocols that the application uses to communicate. When you browse a website, your browser uses **HTTP**. When you send an email, your client uses **SMTP**.
    
- **PDU (Protocol Data Unit):** Data
    
- **Common Protocols:** **HTTP** (Web), **SMTP** (Email), **FTP** (File Transfer), **DNS** (Domain Name System).


### Layer 6: The Presentation Layer

- **Main Function:** This is the "translator" or "syntax" layer. It ensures that data from the sender's application can be understood by the receiver's application.
    
- **Key Concepts:** It handles three main tasks:
    
    1. **Translation:** Converts data between different formats (e.g., ASCII to EBCDIC).
        
    2. **Encryption/Decryption:** Manages encryption (like **SSL/TLS**) to secure the data.
        
    3. **Compression:** Compresses data to reduce its size for faster transmission (e.g., JPEG, MPEG).
        
- **PDU:** Data
    
- **Common Protocols:** **SSL/TLS** (Secure Sockets Layer), **JPEG**, **MPEG**, **ASCII**


### Layer 5: The Session Layer

- **Main Function:** This is the "dialog controller." It establishes, manages, and terminates the communication "sessions" between two devices.
    
- **Key Concepts:** It's responsible for opening a connection, keeping it alive while data is being transferred, and closing it when it's done. It also uses **checkpoints**; if a large file transfer is interrupted, the session layer can resume the transfer from the last checkpoint instead of starting over.
    
- **PDU:** Data
    
- **Common Protocols:** **NetBIOS** (Network Basic Input/Output System), **RPC** (Remote Procedure Call).


### Layer 4: The Transport Layer

- **Main Function:** This layer provides end-to-end data delivery and error recovery. It's the "post office" that ensures your data gets to the correct application on the destination computer.
    
- **Key Concepts:**
    
    - **Segmentation:** Breaks large data into smaller chunks called **segments**.
        
    - **Port Addressing:** Uses port numbers (e.g., Port 80 for HTTP, Port 443 for HTTPS) to deliver data to the correct _service_ on a computer.
        
    - **Reliability (TCP):** Uses **TCP (Transmission Control Protocol)** for reliable, connection-oriented delivery. It handles flow control, error control, and ensures segments arrive in the correct order.
        
    - **Speed (UDP):** Uses **UDP (User Datagram Protocol)** for fast, connectionless delivery. It's "best-effort" and doesn't guarantee delivery, making it good for video streaming or gaming where speed is more important than perfect accuracy.
        
- **PDU:** Segment (for TCP) / Datagram (for UDP)
    
- **Common Protocols:** **TCP**, **UDP**.



### Layer 3: The Network Layer

- **Main Function:** This is the "GPS" or "router" of the network. Its job is to move data **packets** across different networks to reach the final destination.
    
- **Key Concepts:**
    
    - **Logical Addressing:** Uses **IP addresses** (e.g., 192.168.1.1) to identify devices on a network.
        
    - **Routing:** Determines the best physical path for the data to travel from source to destination. This is what **routers** do.
        
    - **Packetizing:** Encapsulates segments from the transport layer into units called **packets**.
        
- **PDU:** Packet
    
- **Common Protocols:** **IP** (Internet Protocol), **ICMP** (Internet Control Message Protocol), **OSPF** (a routing protocol).


### Layer 2: The Data Link Layer

- **Main Function:** This layer handles node-to-node (or "hop-to-hop") data transfer over a _single, local_ network link. It ensures data is reliably transmitted over the physical medium.
    
- **Key Concepts:**
    
    - **Physical Addressing:** Uses **MAC addresses** (e.g., 00:1A:2B:3C:4D:5E), which are hard-coded into a device's network card.
        
    - **Framing:** Encapsulates packets from the network layer into units called **frames**. It adds a header and trailer to the packet.
        
    - **Error Control:** The trailer often contains a **CRC (Cyclic Redundancy Check)** to detect if the frame was corrupted during transmission.
        
- **PDU:** Frame
    
- **Common Protocols/Devices:** **Ethernet**, **Switches**, **Bridges**, **MAC address**.


### Layer 1: The Physical Layer

- **Main Function:** This is the "wires and waves" layer. It defines the physical and electrical specifications for the connection. It's responsible for transmitting the raw stream of bits (1s and 0s).
    
- **Key Concepts:** It defines everything about the physical hardware, such as cable types (e.g., Ethernet, Fiber Optic), voltage levels, and signal timing. If you can physically touch it, it's probably part of Layer 1.
    
- **PDU:** Bit
    
- **Common Protocols/Devices:** **Ethernet cables**, **Hubs**, **Repeaters**, **Wi-Fi** (radio waves).



#  Hub

- **What it is:** A multi-port repeater.
    
- **Function:** A hub is a central connection point for devices in a LAN (Local Area Network). When a data packet (frame) arrives at one port, the hub simply broadcasts that packet out to **all other ports** connected to it.
    
- **Operates at:** **Layer 1 (Physical Layer)**.
    
- **Key Downside:** This is very inefficient. If 10 computers are connected, a message for Computer 2 is also sent to 3, 4, 5, 6, 7, 8, 9, and 10. This creates a single **collision domain**, meaning if two devices try to send data at the same time, their data collides, and both must resend.


# Bridge

- **What it is:** A device with (usually) two ports used to connect two separate LAN segments.
    
- **Function:** A bridge "learns" the **MAC addresses** of the devices on each segment. When a frame arrives, the bridge reads the destination MAC address.
    
    - If the destination is on the _same segment_ as the source, the bridge blocks the frame from crossing over.
        
    - If the destination is on the _other segment_, the bridge forwards the frame.
        
- **Operates at:** **Layer 2 (Data Link Layer)**.
    
- **Key Advantage:** It **divides a collision domain**. This reduces unnecessary traffic and improves performance compared to a hub.



# Switch

- **What it is:** A modern, multi-port bridge. This is what you most likely use in a home or office LAN.
    
- **Function:** A switch is the intelligent successor to the hub. It maintains an internal **MAC address table** that maps each device's MAC address to its physical port on the switch. When a frame arrives, the switch reads the destination MAC address and forwards the frame **only to the specific port** connected to that destination device.
    
- **Operates at:** **Layer 2 (Data Link Layer)**.
    
- **Key Advantage:** Each port on a switch is its **own separate collision domain**. This means all devices can send and receive data simultaneously (in full-duplex mode) without collisions, drastically improving network speed and efficiency.


# Router

- **What it is:** A device that connects two or more different networks. (e.g., your home LAN and the internet).
    
- **Function:** While a switch uses MAC addresses (Layer 2) to move data within one network, a router uses **IP addresses** (Layer 3) to move data _between_ different networks. Its primary job is **routing**—determining the best logical path for a packet to take to reach its final destination across the internet.
    
- **Operates at:** **Layer 3 (Network Layer)**.
    
- Key Difference (Switch vs. Router):
    
    - A **Switch** connects devices on the **same network** (using MAC addresses).
        
    - A **Router** connects **different networks** (using IP addresses).
        
- A router also **divides broadcast domains**, meaning a broadcast message (like from DHCP) sent on one network will not be forwarded by the router to another, which prevents unnecessary traffic



# Gateway

- **What it is:** A more general-purpose device that acts as a "gate" between two dissimilar networks.
    
- **Function:** A gateway is a network node that can connect two networks that use completely **different protocols**. While a router connects two IP-based networks, a gateway can, for example, connect a TCP/IP network to a different type of network. It acts as a protocol translator.
    
- **Operates at:** Can operate at **all 7 layers** of the OSI model, though often at the Application Layer (e.g., an email gateway translating SMTP to another mail protocol)


![[Pasted image 20251106170145.png]]



# Layer 2 VS layer 3 switch 
![[Pasted image 20251211202431.png]]


### 📞 Connection-Oriented Service (e.g., TCP)

This service establishes a dedicated, reliable connection _before_ any data is sent. It's like making a phone call:

1. **Establish Connection:** You "dial" the number and the other person "picks up." This is a handshake.
    
2. **Transfer Data:** You have a conversation, and the words are heard in the exact order you speak them.
    
3. **Release Connection:** You both say "goodbye" and hang up, formally ending the session.
    

This method guarantees that all data arrives, arrives in the correct order, and is error-free.

#### Key Features:

- **Reliable:** It uses **acknowledgments (ACKs)** to confirm that data packets were received. If an ACK isn't received, the packet is sent again (retransmission).
    
- **Ordered:** Packets are numbered, so the receiver can reassemble them in the correct sequence, even if they arrive out of order.
    
- **Flow Control:** Manages the transmission speed so a fast sender doesn't overwhelm a slow receiver.
    
- **Overhead:** All this reliability (handshakes, acknowledgments, sequencing) adds significant overhead, making it a bit slower.
    

**Main Protocol:** **TCP (Transmission Control Protocol)**. **Use Cases:** Applications where accuracy is critical:

- Web browsing (HTTP/HTTPS)
    
- File transfers (FTP)
    
- Email (SMTP)



### ✉️ Connectionless Service (e.g., UDP)

This service does _not_ establish a connection. It simply sends the data. It's like mailing a stack of postcards.

- You write the destination address on each postcard and drop them in the mailbox one by one.
    
- You have **no idea** if they all arrived, if some got lost, or if they arrived in the right order.
    
- There is no "handshake" to start and no "goodbye" to end. You just send the data and hope for the best.
    

This method is "best-effort." It's fast, but it's not reliable.

#### Key Features:

- **Unreliable:** There are no acknowledgments, no retransmissions. If a packet is lost, it's gone for good.
    
- **Unordered:** Each packet (or "datagram") is sent independently. They might take different paths to the destination and arrive out of sequence.
    
- **No Flow Control:** It sends data as fast as possible, which can lead to congestion or packet loss.
    
- **Low Overhead:** Because it skips all the reliability steps, it's very fast and lightweight.
    

**Main Protocol:** **UDP (User Datagram Protocol)**. **Use Cases:** Applications where speed is more important than perfect accuracy:

- Video/Audio Streaming (VoIP)
    
- Online Gaming
    
- DNS (Domain Name System)



![[Pasted image 20251106170405.png]]


# Port numbers

A port number is a 16-bit number (from 0 to 65535) used by protocols like TCP and UDP to identify a specific application or service on a computer.

|**Protocol**|**Port Number**|**Description**|
|---|---|---|
|**FTP** (File Transfer Protocol)|**20** (Data) / **21** (Control)|Used for transferring files. It's unique in that it uses two ports: one to send commands (21) and one for the actual data (20).|
|**SSH** (Secure Shell)|**22**|Used for secure, encrypted remote login and command-line access to a server.|
|**Telnet**|**23**|An _unencrypted_ protocol for remote login. It's old and insecure; SSH has replaced it.|
|**SMTP** (Simple Mail Transfer)|**25**|Used for **sending** email from an email client to a mail server, and between mail servers.|
|**DNS** (Domain Name System)|**53**|Translates human-readable domain names (like `google.com`) into computer-readable IP addresses.|
|**HTTP** (Hypertext Transfer)|**80**|The foundational protocol for the World Wide Web. Used for loading standard, _unencrypted_ websites.|
|**POP3** (Post Office Protocol 3)|**110**|One of the main protocols used for **retrieving** email from a mail server to your email client.|
|**HTTPS** (HTTP Secure)|**443**|The secure, _encrypted_ version of HTTP. This is what you use for online banking, shopping, or logging into sites.|


# TCP and UDP

- 📞 **TCP (Transmission Control Protocol)** is like a **telephone call**. You must establish a connection first (the "handshake"), you're notified if the other person hears you (acknowledgments), and the conversation happens in a logical, ordered sequence.
    
- ✉️ **UDP (User Datagram Protocol)** is like sending **postcards**. You just write the address and send them. You don't know if they'll all arrive, if they'll arrive in the right order, or if they got lost.


| **Feature**      | **TCP (Transmission Control Protocol)**                                                                                                      | **UDP (User Datagram Protocol)**                                                                                            |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Connection**   | **Connection-Oriented**. It must establish a connection (via a "three-way handshake") before sending data.                                   | **Connectionless**. It just sends the data (datagrams) without any prior setup.                                             |
| **Reliability**  | **Reliable**. Guarantees that data will be delivered. It uses **acknowledgments (ACKs)** and **retransmissions** to resend any lost packets. | **Unreliable**. It's a "best-effort" protocol. There is no acknowledgment, no retransmission, and no guarantee of delivery. |
| **Ordering**     | **Ordered**. Packets (segments) are numbered and reassembled in the correct order at the destination.                                        | **Unordered**. Packets (datagrams) may arrive out of order, and the protocol doesn't fix this.                              |
| **Speed**        | **Slower**. The overhead of handshakes, acknowledgments, and ordering makes it slower.                                                       | **Faster**. Very low overhead because it doesn't do any of those reliability checks.                                        |
| **Overhead**     | **High**. The TCP header is larger (20 bytes) to manage sequence numbers, ACKs, etc..                                                        | **Low**. The UDP header is very small and simple (8 bytes).                                                                 |
| **Flow Control** | **Yes**. It has mechanisms (like a sliding window) to ensure a fast sender doesn't overwhelm a slow receiver.                                | **No**. It sends data as fast as possible, which can lead to packet loss if the receiver can't keep up.                     |
| **Use Cases**    | **Reliability is key:** Web browsing (HTTP/HTTPS), email (SMTP, POP3), file transfers (FTP).                                                 | **Speed is key:** Video/audio streaming (VoIP), online gaming, DNS.                                                         |



# Congestion control

**Congestion Control** is about a sender (or multiple senders) overwhelming the _network itself_ (i.e., the routers in the middle).

When a router's buffer (its waiting room for packets) is full, it has no choice but to **drop** packets. When packets are dropped, TCP has to retransmit them, which just adds _more_ load to an already overloaded network. This can lead to **congestion collapse**, where the network is busy but no useful data is getting through.

TCP's solution is an algorithm that tries to find out how much bandwidth is available and "backs off" when it detects packet loss.

To manage this, the TCP sender maintains a new variable called the **Congestion Window (cwnd)**. This is a limit on how much _unacknowledged_ data the sender can have in flight (in the network) at any one time.

The sender's effective window is the **minimum** of the receiver's window and the congestion window: `EffectiveWindow = min(rwnd, cwnd)`

The entire goal of TCP Congestion Control is to **dynamically adjust the size of `cwnd`** based on network conditions.


## TCP Slow start

This is the "starting" phase, used when a connection first begins or after a major packet loss (a timeout). The name is misleading; it's actually an **exponential growth** phase designed to quickly find the network's available capacity.

- **Initial State:** The sender starts with a small `cwnd`, typically 1 MSS (Maximum Segment Size).
    
- **The Rule:** For **every ACK** received, the sender **increases `cwnd` by 1 MSS**.
    
- **The Effect:** This effectively **doubles the `cwnd` every Round-Trip Time (RTT)**.
    
    - Send 1 packet -> get 1 ACK -> `cwnd` is now 2.
        
    - Send 2 packets -> get 2 ACKs -> `cwnd` is now 4.
        
    - Send 4 packets -> get 4 ACKs -> `cwnd` is now 8.
        

This exponential growth continues until `cwnd` reaches a threshold value called `ssthresh` (Slow Start Threshold).


# TCP segment structure

![[Pasted image 20251106173258.png]]

1. **Source Port (16 bits):**
    
    - Port number of the sending application.
        
2. **Destination Port (16 bits):**
    
    - Port number of the receiving application.
        
3. **Sequence Number (32 bits):**
    
    - Identifies the position of the first data byte in this segment in the overall byte stream.
        
4. **Acknowledgment Number (32 bits):**
    
    - Specifies the next expected byte by the sender (used for reliable delivery).
        
5. **Data Offset (Header Length, 4 bits):**
    
    - Indicates the size of the TCP header.
        
6. **Reserved (6 bits):**
    
    - Reserved for future use, set to zero.
        
7. **Flags (6 bits):**
- **URG:** Urgent pointer field is valid
    
- **ACK:** Acknowledgment number is valid
    
- **PSH:** Push data to application immediately
    
- **RST:** Reset the connection
    
- **SYN:** Initiate a connection
    
- **FIN:** Finish (close) the connection
        
8. **Window Size (16 bits):**
    
    - Advertises how much data the receiver can accept (used for flow control).
        
9. **Checksum (16 bits):**
    
    - Used for error detection of header and data.
        
10. **Urgent Pointer (16 bits):**
    
    - Indicates urgent data (used only if URG flag is set).
        
11. **Options (Variable length, up to 40 bytes):**
    
    - Used for special communication parameters, typically during connection setup.
        
12. **Padding (Variable):**
    
    - Ensures the header is a multiple of 32 bits.



### 🚰 TCP Flow Control

**Flow Control** is a mechanism that prevents a fast sender from overwhelming a slow receiver. It's a **receiver-side** solution.

Imagine the sender is a fast-flowing faucet and the receiver is a small glass. If you turn the faucet on full blast, the glass will overflow and most of the water (data) will be lost.

To solve this, TCP uses a **Sliding Window** protocol.

1. **The Receiver's Buffer:** The receiver has a buffer (a block of memory) to store incoming data before the application can read it.
    
2. **The Receiver Window (`rwnd`):** The receiver constantly calculates how much _free space_ is available in its buffer. This free space is called the **Receiver Window** (or `rwnd`).
    
3. **Advertising the Window:** The receiver includes this `rwnd` value in the **"Window Size"** field of every ACK packet it sends back to the sender. This is like the receiver holding up a sign that says, "I only have space for 4000 more bytes right now!"
    
4. **Sender Adjusts:** The sender receives this `rwnd` value and adjusts its sending rate. It will _not_ send more unacknowledged data than the `rwnd` value it last received.
    

**What happens if the buffer is full?** If the receiver's buffer becomes full, it advertises a **`rwnd` of 0**. This tells the sender, "STOP! I'm full." The sender must then stop sending data and wait until it receives a new ACK with a non-zero


### 🔧 TCP Error Control

**Error Control** is a set of mechanisms to detect and correct errors, ensuring data is delivered completely, in order, and without corruption.

TCP achieves error control using three main tools:

1. **Checksum (for Error Detection):**
    
    - Every TCP segment includes a **Checksum** field in its header.
        
    - The sender calculates a value based on the header and data, and the receiver performs the exact same calculation.
        
    - If the receiver's calculated checksum doesn't match the checksum in the header, the segment is known to be **corrupted**. The receiver silently **discards** it and does _not_ send an ACK. The sender will eventually retransmit it.
        
2. **Acknowledgments (ACKs) (for Error Confirmation):**
    
    - This is the core of TCP's reliability. When the receiver gets a data segment, it sends an **Acknowledgment (ACK)** packet back.
        
    - TCP uses **cumulative ACKs**. An ACK number of "501" means "I have successfully received every single byte from 1 up to 500, and I am now waiting for byte 501".
        
    - This cleverly acknowledges multiple packets at once and tells the sender exactly what to send next.
        
3. **Retransmission (for Error Correction):**
    
    - The sender starts a **Retransmission Time-Out (RTO)** timer every time it sends a segment.
        
    - If the data is lost or corrupted, the sender will not get an ACK. It corrects this in two ways:
        
        - **Timeout:** If the RTO timer expires before an ACK is received, the sender assumes the segment was lost and **retransmits** it.
            
        - **Fast Retransmit (3 Duplicate ACKs):** This is a much faster and more common method. Imagine the sender sends packets 1, 2, 3, 4, 5, but packet **2** is lost.
            
            - Receiver gets 1 -> sends ACK for 2.
                
            - Receiver gets 3 (out of order) -> sends **ACK for 2** (Duplicate 1).
                
            - Receiver gets 4 (out of order) -> sends **ACK for 2** (Duplicate 2).
                
            - Receiver gets 5 (out of order) -> sends **ACK for 2** (Duplicate 3).
                
        - When the sender receives **three duplicate ACKs** for the same data (ACK 2), it's a strong signal that packet 2 was lost. It immediately **retransmits** packet 2 without waiting for the timer to expire.

# Socket Programming
Think of it this way:

- An **IP Address** is your computer's "street address" on the network.
    
- A **Port Number** is the "apartment number" for a specific application (like your browser).
    
- A **Socket** is the actual **"door"** to that apartment.
    

A socket is an endpoint for communication. It's an object that your program can use to send and receive data. Socket programming is simply the art of using functions (system calls) to create and manage these sockets.

### ⚙️ How Socket Programming Works (The Server Side)

The most common example is a **TCP server** (a connection-oriented server). The server's job is to create a socket, wait for clients to connect, and then manage those connections. This process uses a few key system calls that appeared in your exam papers:

1. **`socket()`**
    
    - **What it does:** This is the first step. It creates the initial socket (the "door") but doesn't have an address yet.
        
    - **Analogy:** You are building a new door in a workshop. It exists, but it's not attached to any building or apartment.
        
2. **`bind()`**
    
    - **What it does:** This function assigns an address (an IP address and a port number) to the socket you just created.
        
    - **Analogy:** You take the door from the workshop and install it as the entrance to "Apartment 80" at "192.168.1.100." The socket is now bound to a specific location.
        
3. **`listen()`**
    
    - **What it does:** This call turns the socket from an "active" socket (one that could make connections) into a "passive" socket (one that waits for connections). It tells the operating system, "I am a server, please queue up any incoming connection requests for me."
        
    - **Analogy:** You put a "Welcome" mat outside the door and start listening for a knock.
        
4. **`accept()`**
    
    - **What it does:** This call blocks and _waits_. When a client tries to connect (knocks on the door), `accept()` "opens the door" and creates a _brand new_ socket that is dedicated to communicating with _that specific client_.
        
    - **Analogy:** Someone knocks. You open the door, and instead of talking to them in the hallway, you guide them to a private-line telephone (the new socket) where you can have a dedicated conversation. Your main "listening" door (the original socket) is now free to `accept()` calls from other clients.
        

This `accept()`-`new_socket` model is what allows a single server (like a web server) to handle thousands of clients at the same time.

### Client vs. Server

- **Server:** `socket()` $\rightarrow$ `bind()` $\rightarrow$ `listen()` $\rightarrow$ `accept()`
    
- **Client:** The client side is simpler. It just needs to `socket()` (create its own door) and then `connect()` (call the server's address and port).



# CLASSES of IP Addresses

### Class A

- **Purpose:** Designed for a small number of very large networks.
    
- **How to Identify:** The first bit is always **0**.
    
- **First Octet Range:** **1 – 126** (Note: 0 and 127 are reserved).
    
- **Network/Host Bits:** The first 8 bits (first octet) are the **Network ID**, and the remaining 24 bits are the **Host ID**.
    
    - `NNNNNNNN.HHHHHHHH.HHHHHHHH.HHHHHHHH`
        
- **Default Subnet Mask:** 255.0.0.0
    
- **Result:**
    
    - **Number of Networks:** $2^7 - 2$ (only 126 possible networks)
        
    - **Hosts per Network:** $2^{24} - 2$ (over 16 million hosts)
        

---

### Class B

- **Purpose:** Designed for medium-to-large networks.
    
- **How to Identify:** The first two bits are always **10**.
    
- **First Octet Range:** **128 – 191**
    
- **Network/Host Bits:** The first 16 bits (two octets) are the **Network ID**, and the remaining 16 bits are the **Host ID**.
    
    - `NNNNNNNN.NNNNNNNN.HHHHHHHH.HHHHHHHH`
        
- **Default Subnet Mask:** 255.255.0.0
    
- **Result:**
    
    - **Number of Networks:** $2^{14}$ (16,384 networks)
        
    - **Hosts per Network:** $2^{16} - 2$ (65,534 hosts)
        

---

### Class C

- **Purpose:** Designed for a large number of small networks (e.g., small businesses, home networks).
    
- **How to Identify:** The first three bits are always **110**.
    
- **First Octet Range:** **192 – 223**
    
- **Network/Host Bits:** The first 24 bits (three octets) are the **Network ID**, and the remaining 8 bits are the **Host ID**.
    
    - `NNNNNNNN.NNNNNNNN.NNNNNNNN.HHHHHHHH`
        
- **Default Subnet Mask:** 255.255.255.0
    
- **Result:**
    
    - **Number of Networks:** $2^{21}$ (over 2 million networks)
        
    - **Hosts per Network:** $2^8 - 2$ (254 hosts)
        

---

### Class D

- **Purpose:** Reserved for **multicasting**. There is no Network/Host division.
    
- **How to Identify:** The first four bits are always **1110**.
    
- **First Octet Range:** **224 – 239**
    
- **Use Case:** A single "multicast group" address that multiple interested hosts can listen to. Used for streaming video, online gaming, etc.
    

---

### Class E

- **Purpose:** Reserved for **experimental or future use**.
    
- **How to Identify:** The first four bits are always **1111**.
    
- **First Octet Range:** **240 – 255**
    
- **Use Case:** These addresses are not used on the public internet.


| **Class** | **First Octet Range** | **Leading Bits** | **Default Subnet Mask** | **Network ID / Host ID** |
| --------- | --------------------- | ---------------- | ----------------------- | ------------------------ |
| **A**     | 1 – 126               | `0...`           | 255.0.0.0               | N.H.H.H                  |
| **B**     | 128 – 191             | `10...`          | 255.255.0.0             | N.N.H.H                  |
| **C**     | 192 – 223             | `110...`         | 255.255.255.0           | N.N.N.H                  |
| **D**     | 224 – 239             | `1110...`        | N/A (Multicast)         | N/A                      |
| **E**     | 240 – 255             | `1111...`        | N/A (Experimental)      | N/A                      |


# Subnetting

### 🏢 What is Subnetting?

**Subnetting** is the process of taking one large network and dividing it into multiple smaller, logical networks called **subnets**.

Think of it this way:

- An **IP Network** (like a Class C) is a large office building.
    
- **Subnetting** is the act of putting up walls to divide that large open-plan office into smaller, private offices (the subnets).
    

### 🤔 Why Subnet?

The main reason is to solve the two biggest problems of a large network: performance and organization.

- **Reduces Broadcast Traffic:** The most important benefit. When a device sends a "broadcast" (a message for everyone), it now only travels to devices _within its own subnet_, not the entire network. This reduces noise and improves speed for everyone.
    
- **Improves Security:** By separating your network, you can control traffic _between_ subnets. You can put up a "firewall" (router) and say, "The Accounting subnet and the Guest Wi-Fi subnet are not allowed to talk to each other."
    
- **Simplifies Management:** It's easier to manage and troubleshoot 20 hosts in a subnet than 500 hosts in one giant network.
    
- **Efficient IP Use:** It allows you to divide a block of IP addresses and allocate them to different departments or locations as needed, without wasting them.
    

### 🔑 How Subnetting Works: The Subnet Mask

Subnetting works by "borrowing" bits from the **Host ID** part of an IP address and using them to create a new **Subnet ID** part.

The **Subnet Mask** is the key. It's a 32-bit number that tells a router which part of an IP address is the **Network** and which part is the **Host**.

- A `1` in the mask means "this bit is part of the Network/Subnet ID."
    
- A `0` in the mask means "this bit is part of the Host ID."
    

A standard Class C mask is 255.255.255.0, which in binary is:

11111111.11111111.11111111.00000000

(24 network bits, 8 host bits)

To create subnets, we _change_ this mask. We turn some of the `0`s (host bits) into `1`s (subnet bits).

---

### 🗺️ Step-by-Step Example

This is the part you'll be asked to do on the exam.

**Scenario:** You have a Class C network with the IP address `192.168.10.0`. You need to divide it into **4 subnets**.

#### Step 1: Find the bits to borrow

To get 4 subnets, we need to solve for $n$ in $2^n \ge 4$.

- $n=1$ gives $2^1 = 2$ subnets (not enough)
    
- $n=2$ gives $2^2 = 4$ subnets (perfect)
    
    So, we must borrow 2 bits from the host part.
    

#### Step 2: Calculate the new Subnet Mask

The original mask was 255.255.255.0, or /24.

The last octet was 00000000.

We borrow 2 bits, so we turn the first two 0s into 1s.

The last octet becomes 11000000.

- What is `11000000` in decimal?
    
    - $1 \times 128 + 1 \times 64 + 0 + 0 + 0 + 0 + 0 + 0 = 192$
        
- **New Subnet Mask:** `255.255.255.192`
    
- **New CIDR Notation:** The mask now has $24 + 2 = 26$ bits. So, it's a `/26` mask.
    

#### Step 3: Find the Subnet Addresses

The 2 bits we borrowed can have 4 values: `00`, `01`, `10`, `11`. These create our 4 subnets in the last octet:

- **Subnet 1 (00):** `192.168.10.00000000` $\rightarrow$ **`192.168.10.0`**
    
- **Subnet 2 (01):** `192.168.10.01000000` $\rightarrow$ **`192.168.10.64`**
    
- **Subnet 3 (10):** `192.168.10.10000000` $\rightarrow$ **`192.168.10.128`**
    
- **Subnet 4 (11):** `192.168.10.11000000` $\rightarrow$ **`192.168.10.192`**
    

_The "magic number" here is $256 - 192 = 64$. This tells you the subnets increment by 64 (0, 64, 128, 192)._

#### Step 4: Analyze the Hosts

Let's analyze **Subnet 2 (`192.168.10.64 /26`)**:

- **How many host bits are left?**
    
    - Original: 8 bits. We borrowed 2.
        
    - Host bits left: $8 - 2 = 6$ bits.
        
- **How many hosts per subnet?**
    
    - $2^6 = 64$ total addresses.
        
    - We must subtract 2: one for the Network ID and one for the Broadcast ID.
        
    - **Usable Hosts:** $64 - 2 = 62$ hosts.
        
- **Addresses for this subnet:**
    
    - **Network ID:** `192.168.10.64` (The "address" of the subnet itself. Cannot be used.)
        
    - **First Host IP:** `192.168.10.65` (The first usable address)
        
    - **Last Host IP:** `192.168.10.126` (The last usable address)
        
    - **Broadcast ID:** `192.168.10.127` (The message address for all 62 hosts. Cannot be used.




# Routing Algorithms

		Static algorithms
		 Dynamic algorithms
			 -Distance vector routing
			 -link state routing


# Distance Vector Routing
![[Pasted image 20251108170553.png]]

![[Pasted image 20251111115913.png]]a
# Count To infinity Problem 

![[Pasted image 20251108172136.png]]



# Link state routing 


![[Pasted image 20251108194853.png]]

![[Pasted image 20251111112938.png]]



# IPv4 vs IPv6

![[Pasted image 20251109113933.png]]

![[Pasted image 20251109113946.png]]





![[Pasted image 20251109161929.png]]![[Pasted image 20251109114146.png]]


# ARP

![[Pasted image 20251109120623.png]]



# NAT

![[Pasted image 20251109123958.png]]



# ERROR DETECTION AND CORRECTION

![[Pasted image 20251109163201.png]]


# CRC

![[Pasted image 20251109173750.png]]

**Cyclic Redundancy Check (CRC)** is an error-detecting code used to verify the integrity of data.

Think of it as a an "advanced checksum." When you send data from one place to another (over Wi-Fi, Ethernet, or even from your hard drive), you need a way to check if the data was accidentally corrupted during the trip (e.g., a `0` flipped to a `1`).

CRC is the method that calculates a small, unique "check value" based on the entire message and attaches it. The receiver performs the _exact same calculation_ and checks if its result matches the attached check value. If they don't match, the receiver knows the data is bad and can request a re-send.




# MUPLTIPLE ACCESS PROTOCOL

![[Pasted image 20251109180718.png]]

![[Pasted image 20251109180735.png]]


# ALOHA
![[Pasted image 20251109185211.png]]

![[Pasted image 20251109185230.png]]
![[Pasted image 20251109185334.png]]

![[Pasted image 20251109185417.png]]


# Slotted Aloha
![[Pasted image 20251110114726.png]]


Here are the technical rules for a computer network using Slotted ALOHA:

1. **Synchronized Time:** All devices (stations) on the network are synchronized to a master clock. They all know when a "time slot" begins and ends. A time slot is just long enough to send one packet of data.
    
2. **Transmission Rule:** When a station has data to send, it **must wait** for the _beginning_ of the very next time slot. It cannot transmit in the middle of a slot.
    
3. **Collision Handling:**
    
    - If two or more stations transmit in the same slot, their packets will collide, and the data will be lost.
        
    - The stations "listen" for an acknowledgment from the receiver. If they don't get one, they assume a collision occurred.
        
    - To fix this, both stations wait a **random** number of time slots before trying to send again. (Waiting a _random_ time is key—if they both waited 2 slots, they would just collide again).



	
![[Pasted image 20251110114804.png]]


# CSMA /CD

![[Pasted image 20251110134158.png]]



# CSMA/CA

![[Pasted image 20251110135318.png]]

|**Feature**|**CSMA/CD (Collision Detection)**|**CSMA/CA (Collision Avoidance)**|
|---|---|---|
|**Strategy**|**Reactive:** Fixes collisions _after_ they happen.|**Proactive:** Tries to prevent collisions _before_ they happen.|
|**Action**|Transmits, and stops if a collision is detected.|Sends a signal to reserve the channel _before_ transmitting.|
|**Used In**|**Wired Networks** (Old Ethernet)|**Wireless Networks** (Wi-Fi)|
|**When it sends**|As soon as the channel is idle.|After the channel is idle, plus a random wait time.|
|**Recovery**|Detects jam signal, waits a random time.|Relies on an **acknowledgment (ACK)**. If no ACK, it re-sends.|



# Sliding window Protocols

![[Pasted image 20251111131150.png]]
		-Goback n
		 - Selective repeat

# GO back n
![[Pasted image 20251111132218.png]]


## Selective Repeat ARQ



![[Pasted image 20251120144234.png]]



## Flow control ARQ


![[Pasted image 20251120144423.png]]


**ARQ (Automatic Repeat Request)** is an error-control strategy used in the Data Link Layer (Unit 5) and Transport Layer (Unit 3) to ensure that data is delivered reliably from sender to receiver111.

If data is lost, corrupted, or arrives out of order, ARQ protocols automatically request the retransmission of that data.

### **How ARQ Works (The Core Mechanism)**

ARQ relies on three main elements:

1. **Acknowledgments (ACK):** The receiver sends a message back to the sender saying, "I received this packet correctly."
    
2. **Timeouts:** The sender starts a timer when it sends a packet. If the timer runs out before an ACK arrives, the sender assumes the packet was lost.
    
3. **Retransmission:** Upon a timeout or a negative acknowledgment (NACK), the sender re-sends the packet.
    

---

### **The 3 Main Types of ARQ Protocols**

#### **1. Stop-and-Wait ARQ**

This is the simplest form of flow and error control.

- **Mechanism:** The sender sends **one** packet and stops. It waits for an ACK from the receiver before sending the next packet.
    
- **If Error Occurs:** If the sender waits too long (Timeout) without an ACK, it retransmits the packet.
    
- **Pros:** Very simple to implement.
    
- **Cons:** Extremely inefficient. The sender spends most of its time doing nothing (waiting), leading to very low throughput.
    

#### **2. Go-Back-N ARQ (Sliding Window)**

This improves efficiency by allowing the sender to send multiple packets (a "window" of packets) without waiting for an ACK.

- **Mechanism:** The sender sends packets $1, 2, 3, 4, 5...$ up to a limit (Window Size).
    
- **If Error Occurs (e.g., Packet 3 is lost):** The receiver discards Packet 3 _and_ all subsequent packets ($4, 5...$) because it expects them in order.
    
- **Retransmission:** The sender receives no ACK for Packet 3, times out, and must **"Go Back"** to 3 and retransmit $3, 4, 5$ again.
    
- **Key Feature:** Uses **Cumulative Acknowledgments** (e.g., ACK 4 means "I have received everything _up to_ 4").
    

#### **3. Selective Repeat ARQ**

This is the most efficient but most complex method.

- **Mechanism:** Like Go-Back-N, the sender sends multiple packets.
    
- **If Error Occurs (e.g., Packet 3 is lost):** The receiver accepts and buffers Packets 4 and 5 (even though they are out of order) but sends a warning (NACK) for Packet 3.
    
- **Retransmission:** The sender retransmits **only** Packet 3. Once Packet 3 arrives, the receiver reassembles the order ($3, 4, 5$) and delivers them.
    
- **Key Feature:** Retransmits only the specific damaged or lost packet.
    

---

### **Comparison Summary**

| **Feature**         | **Stop-and-Wait**          | **Go-Back-N**                       | **Selective Repeat**                     |
| ------------------- | -------------------------- | ----------------------------------- | ---------------------------------------- |
| **Efficiency**      | Low                        | Medium                              | High                                     |
| **Complexity**      | Low                        | Medium                              | High (Complex Logic)                     |
| **Retransmission**  | Resends the current packet | Resends lost packet + all following | Resends **only** the lost packet         |
| **Receiver Buffer** | Not required               | Not required                        | Required (to store out-of-order packets) |


## Stop and wait ARQ

![[Pasted image 20251120144922.png]]
## Go back n or sliding window ARQ



![[Pasted image 20251120144810.png]]


### **What is Framing?**

The Physical Layer transmits a raw stream of bits (0s and 1s) without understanding what they mean. The Data Link Layer picks up these raw bits and organizes them into manageable, distinct units called **Frames**.

Without framing, the receiver would not know where one packet ends and the next one begins.

---

### **Parts of a Frame**

A standard frame consists of three main sections:

1. **Header:**
    
    - Contains the **Source and Destination MAC addresses**.
        
    - Includes control information like the type of protocol being used (IPv4/IPv6).
        
2. **Payload (Data Field):**
    
    - This is the actual data packet received from the Network Layer (Layer 3).
        
3. **Trailer:**
    
    - Contains error detection bits, typically the **CRC (Cyclic Redundancy Check)** or FCS (Frame Check Sequence). This allows the receiver to check if the frame was corrupted during transmission.
        

---

### **Common Framing Methods**

How does the receiver know exactly where a frame starts and ends? It uses specific algorithms:

#### **1. Bit Stuffing (Most Important for Exams)**

- **Concept:** The sender uses a unique bit pattern (flag), usually `01111110`, to mark the start and end of a frame.
    
- **Problem:** What if the data inside the frame naturally contains `01111110`? The receiver might think the frame ended early.
    
- **Solution (Stuffing):** Whenever the sender sees five consecutive `1`s in the data (`11111`), it automatically "stuffs" (inserts) a `0` after them. The receiver reverses this process (removes the `0` after five `1`s) to get the original data.
    
![[Pasted image 20251120150642.png]]
#### **2. Byte Stuffing (Character Stuffing)**

- **Concept:** Similar to bit stuffing, but works with bytes (characters). It uses a special **"FLAG" byte** to start and end the frame.
    
- **Solution:** If the data contains the FLAG byte, the sender inserts an **"ESC" (Escape)** byte before it.
    
![[Pasted image 20251120150613.png]]
#### **3. Character Count**

- **Concept:** The header specifies the total number of characters in the frame.
    
- **Drawback:** If the "count" number gets corrupted during transmission (e.g., a `5` becomes a `9`), the receiver loses synchronization and cannot find the next frame. This method is rarely used today.
    

### **Why is Framing Necessary?**

1. **Synchronization:** Helps the receiver align with the sender's data stream.
    
2. **Error Control:** The trailer (CRC) allows the receiver to discard corrupted frames.
    
3. **Flow Control:** Allows the receiver to tell the sender to slow down if frames are arriving too fast.



![[Pasted image 20251120152132.png]]



Based on **Unit 5 (The Link layer and Local area networks)** of your syllabus1, **Multiple Access Protocols** are a set of rules that allow multiple nodes (computers) to share a single communication channel (like a cable or Wi-Fi frequency) efficiently.

Without these protocols, if two devices try to speak at the same time, their signals would crash into each other, causing a **Collision**, and the data would be destroyed.

These protocols are broadly categorized into three types:

---

### **1. Random Access Protocols (Contention-based)**

In these protocols, no station is superior to another. Any station can send data if the channel seems free. Collisions **can** occur, so the protocol must manage them.

#### **A. ALOHA**

This was the first random access protocol.

- **Pure ALOHA:**
    
    - **Rule:** Transmit whenever you have data.
        
    - **Mechanism:** After sending, listen for an Acknowledgment (ACK). If no ACK receives, assume collision and wait a random amount of time before resending.
        
    - **Efficiency:** Very low (~18%). High chance of collision.
        
- **Slotted ALOHA:**
    
    - **Rule:** Time is divided into fixed slots. You can only start transmitting at the _beginning_ of a slot.
        
    - **Efficiency:** Improved (~37%) because collisions can only happen if two nodes start at the exact same split-second.
        

#### **B. CSMA (Carrier Sense Multiple Access)**

"Listen before you speak."

- **Mechanism:** Before sending, the node "senses" (listens to) the channel.
    
    - If **Idle:** Send data.
        
    - If **Busy:** Wait.
        
- **Types:**
    
    - **1-Persistent:** If busy, keep listening continuously and transmit _immediately_ when it becomes free. (High collision risk if two people are waiting).
        
    - **Non-Persistent:** If busy, wait a random time and check again later. (Reduces collision, increases delay).
        
    - **P-Persistent:** If idle, transmit with probability _P_ (e.g., 0.1).
        

#### **C. CSMA/CD (Carrier Sense Multiple Access with Collision Detection)**

**Used in:** Wired Ethernet (LANs)2.

- **Concept:** "Listen while talking."
    
- **Mechanism:**
    
    1. **Sense:** Monitor the channel. If free, start sending.
        
    2. **Transmit & Monitor:** While sending bits, keep listening to the wire.
        
    3. **Detect Collision:** If signal energy spikes (interference), a collision occurred.
        
    4. **Stop:** Immediately stop sending and send a **Jam Signal** to warn others.
        
    5. **Backoff:** Wait a random time (using _Binary Exponential Backoff_) before trying again.
        
- **Note:** This does NOT work in wireless because you can't send and receive at the same time on a single antenna.
    

#### **D. CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)**

**Used in:** Wireless Networks (Wi-Fi).

- **Concept:** Prevent collisions before they happen.
    
- **Mechanism:**
    
    1. **Sense:** If channel is idle, wait for a brief period (IFS - Inter Frame Space).
        
    2. **RTS/CTS (Optional):** Send a **Request to Send (RTS)** packet. The receiver replies with **Clear to Send (CTS)**. This "reserves" the space so hidden nodes know to stay quiet.
        
    3. **Transmit:** Send data.
        
    4. **ACK:** Wait for acknowledgment.
        

---

### **2. Controlled Access Protocols (Collision-Free)**

Here, stations consult one another or a master node to decide who sends. Collisions are completely eliminated.

#### **A. Reservation**

- **Mechanism:** Time is divided into intervals. Before sending data, a station must reserve a slot in a short "reservation frame."
    
- **Analogy:** Making a dinner reservation. You don't just walk in; you book a table first.
    

#### **B. Polling**

- **Structure:** Requires a central "Primary" controller and secondary devices.
    
- **Mechanism:** The Primary device asks each Secondary device, "Do you have data to send?" one by one.
    
- **Pros:** No collisions.
    
- **Cons:** If the controller fails, the network dies. High overhead (lots of "polling" messages).
    

#### **C. Token Passing**

- **Used in:** Token Ring, Token Bus.
    
- **Mechanism:** A special small packet called a **Token** circulates around the ring.
    
- **Rule:** You can only speak if you hold the Token.
    
    1. Wait for the Token to arrive.
        
    2. Hold the Token, send your data.
        
    3. Release the Token to the next neighbor.
        
- **Pros:** Guaranteed fair access. No collisions.
    

---

### **3. Channelization Protocols**

(Often used in Cellular/Wireless, less emphasis in Link Layer theory but good to know).

- **FDMA (Frequency Division):** Bandwidth is split into different frequencies (Radio stations).
    
- **TDMA (Time Division):** Time is split into slots (You get 10ms, I get 10ms).
    
- **CDMA (Code Division):** Everyone speaks at once but in different "languages" (codes).
    

---

### **Summary for Exam**

|**Protocol**|**Type**|**Best Use Case**|**Key Concept**|
|---|---|---|---|
|**ALOHA**|Random|Satellite / Low Load|Send & Pray.|
|**CSMA/CD**|Random|**Wired Ethernet**|Listen while talking. Stop if crash.|
|**CSMA/CA**|Random|**Wi-Fi**|RTS/CTS to reserve space.|
|**Token Passing**|Controlled|Ring Networks|Only send if you hold the Token.|




## Ethernet Frame Format 

![[Pasted image 20251120164641.png]]

Ethernet is the most widely used wired LAN technology. It defines how data is formatted and transmitted over cables.

#### **Ethernet Frame Format**

You must memorize this structure for exams. The Ethernet frame encapsulates the data from the network layer.

1. **Preamble (7 Bytes):** A pattern of alternating 0s and 1s to wake up the receiver and synchronize clocks.
    
2. **SFD (Start Frame Delimiter - 1 Byte):** Marks the end of the preamble and the actual beginning of the frame (`10101011`).
    
3. **Destination MAC (6 Bytes):** The physical address of the receiver.
    
4. **Source MAC (6 Bytes):** The physical address of the sender.
    
5. **Length/Type (2 Bytes):** Indicates the type of protocol inside the payload (e.g., IPv4 or IPv6) or the length of the data.
    
6. **Data / Payload (46 - 1500 Bytes):** The actual IP packet. If the data is less than 46 bytes, padding (dummy 0s) is added.
    
7. **CRC (4 Bytes):** Cyclic Redundancy Check for error detection.



### **VLAN (Virtual Local Area Network)**

VLANs allow network administrators to segment a single physical LAN into multiple distinct "logical" networks.

- **The Problem:** In a standard switched LAN, broadcast traffic (like ARP requests) is sent to _everyone_. In a large organization, this creates noise and security risks.
    
- **The Solution (VLAN):** You can configure a switch so that ports 1-5 belong to the "Engineering VLAN" and ports 6-10 belong to the "Sales VLAN."
    
- **Key Characteristics:**
    
    - **Broadcast Control:** Broadcasts from Engineering stays in Engineering. They do not reach Sales.
        
    - **Security:** Devices in different VLANs cannot communicate directly; traffic must pass through a router (Layer 3) to cross over, allowing for firewall rules.
        
    - **802.1Q Tagging:** When a frame travels between switches (Trunk Link), a special **4-byte VLAN Tag** is inserted into the Ethernet header to identify which VLAN the frame belongs to.




### **Switches**

In Unit 5, you study switches not just as hardware, but as **Link Layer devices** that process frames.

- **Role:** A switch receives incoming frames and forwards them **only** to the port where the destination device is connected (Unicast), unlike a Hub which broadcasts to everyone.
    
- **Self-Learning Capability:** Switches are "plug-and-play." They build a **Switch Table (MAC Table)** automatically using this logic:
    
    1. **Learn:** When a frame arrives on Port 1 from Device A, the switch records `{Device A MAC : Port 1}` in its table.
        
    2. **Forward:** When a frame arrives destined for Device A, the switch checks its table.
        
        - If the destination is **Known**: Send specifically to that port (Filtering).
            
        - If the destination is **Unknown**: Flood the frame to all ports (except the sender).
            
- **Collision Domains:** Every port on a switch is a separate collision domain, allowing full-duplex communication (simultaneous send/receive).



Based on **Unit 4 (Network Layer)** of your syllabus, which covers "IP protocol and addressing in the Internet"1, **NAT (Network Address Translation)** is a critical concept used to manage IP addresses and connect local networks to the global internet.

### **What is NAT?**

NAT is a process usually performed by a **router** that modifies the IP address information in packet headers while they are in transit. Its primary job is to translate **Private IP addresses** (used within your home or office LAN) into a **Public IP address** (routable on the internet), and vice versa.

![Image of NAT network address translation diagram](https://encrypted-tbn3.gstatic.com/licensed-image?q=tbn:ANd9GcRkmQp5hG3PV3-TGS0NSZmv18-AAjoNOPHLqc-B5joQbIaMjqSDxMqbGzvHX9b1-psOSsmsEk3vtCPWOt7uLh-OicK5TMuBQo2AsiK3AjaUWY-0yWA)

Shutterstock

---

### **Why Do We Need NAT?**

1. **IPv4 Address Conservation:** There are not enough unique IPv4 addresses for every device on the planet. NAT allows an entire household (phones, laptops, TV) to share **one** single Public IP address provided by the ISP.
    
2. **Security:** It hides the internal IP addresses of your local devices from the outside world. External hackers only see the router's public IP, not your specific laptop's address.
    

---

### **How NAT Works (The Mechanism)**

Imagine you are sending a request from your laptop to Google.

1. **Outgoing (LAN to WAN):**
    
    - **Source:** Your Laptop (Private IP: `192.168.1.5`) sends a packet.
        
    - **Action:** The Router replaces the "Source IP" with its own **Public IP** (e.g., `203.0.113.10`) and assigns a unique **Port Number** to this session.
        
    - **NAT Table:** The router notes in its memory: _"Traffic on Port 5001 belongs to 192.168.1.5"_.
        
    - **Result:** The packet travels through the internet appearing to come from the router.
        
2. **Incoming (WAN to LAN):**
    
    - **Source:** Google replies to the Router's Public IP (`203.0.113.10`) on Port 5001.
        
    - **Action:** The router checks its NAT Table. It sees that Port 5001 corresponds to your laptop (`192.168.1.5`).
        
    - **Result:** It replaces the Destination IP with your private IP and forwards the packet to you.
        

---

### **Types of NAT**

|**Type**|**Description**|**Typical Use**|
|---|---|---|
|**Static NAT**|Maps **1 Private IP** to **1 Public IP** permanently.|Web Servers that need to be accessible from outside.|
|**Dynamic NAT**|Maps a Private IP to the _first available_ Public IP from a pool of addresses.|Large offices with a pool of public IPs.|
|**PAT (Port Address Translation)**|Maps **Multiple Private IPs** to **1 Single Public IP** by using different _Port Numbers_ to distinguish traffic.|**Home Wi-Fi Routers** (Most common).|

### **Analogy**

Think of a large corporate office:

- **Private IPs:** Employees have extension numbers (101, 102) that only work inside the building.
    
- **Public IP:** The company has one main phone number (555-1234).
    
- **NAT (The Receptionist):** When an employee calls a client, the client sees the main office number (555-1234). When the client calls back, they speak to the receptionist (Router), who checks who the call is for and transfers it to the correct extension (101).



**ARP (Address Resolution Protocol)** is a critical network protocol used to map a known **IP address** (Layer 3) to a physical **MAC address** (Layer 2).

In the context of your syllabus (**Unit 5: Link Layer**), "Addressing" refers to this interaction. Devices on a local network (LAN) communicate using MAC addresses (hardware addresses), not IP addresses. Therefore, even if you know the destination IP, your computer cannot send the data frame until it finds the corresponding MAC address.

### **Why Do We Need ARP?**

- **The Problem:** A sender (like your laptop) wants to send a packet to a destination IP (e.g., `192.168.1.5`). However, the Ethernet cable/switch only understands physical MAC addresses (e.g., `00:0a:95:9d:68:16`).
    
- **The Solution:** ARP asks the network, "Who owns this IP address?" and gets the physical MAC address in return.
    

---

### **How ARP Works (Step-by-Step)**

**1. Check Cache:** The sender first checks its internal **ARP Cache** (a small table in memory) to see if it already knows the MAC address for that IP. If yes, it uses it immediately.

**2. ARP Request (Broadcast):** If the MAC is not in the cache, the sender broadcasts a message to the entire LAN:

- **Message:** "Who has IP address `192.168.1.5`? Please tell `192.168.1.10`."
    
- **Destination MAC:** `FF:FF:FF:FF:FF:FF` (Broadcast address—everyone listens).
    

**3. ARP Reply (Unicast):** Every device receives the broadcast, but only the device with IP `192.168.1.5` responds.

- **Message:** "I am `192.168.1.5`, and my MAC address is `00:0a:95:9d:68:16`."
    
- **Destination MAC:** Sent directly (unicast) to the sender's MAC address.
    

**4. Update Cache:** The sender receives the reply and updates its ARP Cache so it doesn't have to ask again for a while (entries usually expire after a few minutes).

---

### **Key ARP Commands (For Practical Exams)**

Since your syllabus mentions "Network command and Network configuration commands" in the experiments list, you should know this command:

- **View ARP Table:**
    
    - **Windows/Linux:** `arp -a` _(This shows the list of IP-to-MAC mappings currently stored in your computer's memory.)_
        

### **Analogy**

Imagine you are in a classroom (LAN). You know a student's name (IP Address) is "Rahul," but you don't know where he is sitting (MAC Address).

1. **ARP Request:** You stand up and shout, "Is Rahul here?" (Broadcast).
    
2. **ARP Reply:** Rahul stands up and says, "I am Rahul, and I am sitting at Desk 4" (Unicast).
    
3. **Communication:** Now you can walk directly to Desk 4 to hand him a note.




# Principles of Reliable Data Transfer (RDT) 🛡️

Reliable data transfer protocols (rdt) ensure that data is delivered correctly and in order, despite the underlying **unreliable channel** (which may have bit errors or packet loss).

- **RDT 1.0:** Assumes a perfectly reliable channel (no errors, no loss).
    
- **RDT 2.0 (Stop-and-Wait):** Handles channels with **bit errors**.
    
    - It uses a **checksum** for error detection.
        
    - **Feedback** is used via **ACKs** (acknowledgements for OK packets) and **NAKs** (negative acknowledgements for erroneous packets).
        
    - The sender **retransmits** the packet upon receiving a NAK. The sender must wait for ACK/NAK before sending the next packet, making it a **stop-and-wait** protocol.
        
- **RDT 2.1:** Adds a **sequence number (0 or 1)** to the packet to prevent processing **duplicate** packets that might arise from corrupted ACKs/NAKs.
    
- **RDT 2.2:** Uses the same functionality as RDT 2.1 but replaces NAKs with **duplicate ACKs**. The receiver sends an ACK for the _last packet received OK_.
    
- **RDT 3.0 (Alternating-Bit Protocol):** Handles channels with **errors and loss** of both data packets and ACKs.
    
    - It adds a **countdown timer** to the sender.
        
    - If the sender does not receive an ACK within a **reasonable time**, it retransmits the packet. Sequence numbers (0 and 1) handle any duplicate packets caused by delayed ACKs or premature timeouts.


## Pipelined Protocols: Go-Back-N and Selective Repeat 🛣️

Pipelining is a technique that increases efficiency by allowing the sender to transmit **multiple packets** (requests) without waiting for the corresponding ACKs, filling the "pipe" of the network.

### Go-Back-N (GBN) Protocol

- **Sender Window:** The sender can have up to **N unacknowledged packets** in the pipeline.
    
- **ACKs:** The receiver sends **cumulative ACKs**, indicating the sequence number of the _next_ expected frame.
    
- **Handling Loss/Errors:**
    
    - The receiver **discards** any frames that are out of order (a gap) or duplicates. It re-sends an ACK for the last correct, in-order frame received.
        
    - The sender maintains a timer for the **oldest unacknowledged packet**. When the timer expires, the sender **retransmits all unacknowledged packets** (starting from the one that timed out).
        
- **Also known as:** Sliding Window Protocol.
    

### Selective Repeat (SR) Protocol

- **Sender Window:** The sender can also have up to N unacknowledged packets.
    
- **ACKs:** The receiver sends an **individual ACK for each correctly received packet**, even if they arrive out of order.
    
- **Handling Loss/Errors:**
    
    - The receiver can **buffer** out-of-order packets until the missing packet arrives, then deliver them in order to the upper layer.
        
    - The sender maintains a **timer for _each_ unacknowledged packet**.
        
    - When a timer expires, the sender **retransmits _only_ that specific unacknowledged packet**





## Flow Control and Congestion Control 🛑

### Flow Control

- **Definition:** The mechanism to manage data transmission rate between two nodes to **prevent a fast sender from overwhelming a slow receiver**.
    
- **Mechanism:** The receiver uses the **Receive Window (rwnd)** field to advertise the number of bytes it is willing to accept, based on its available buffer size. The sender adjusts its transmission volume according to this advertised window.
    

### Congestion Control

- **Definition:** Mechanisms to prevent **too many sources sending too much data too fast** for the network to handle, which leads to router buffer overflow and packet loss.
    
- **Approaches:**
    
    - **End-to-End Congestion Control (TCP's approach):** The network provides **no explicit feedback**. Congestion is **inferred** by the end system, usually from packet loss or increased delay (timeouts).
        
    - **Network-Assisted Congestion Control:** Routers provide **explicit feedback** to the end systems, either a single bit indicating congestion (like ECN) or an explicit transmission rate for the sender.



# IPv4


![[Pasted image 20251120234421.png]]

# IPv6

![[Pasted image 20251120234451.png]]



# TCP header

![[Pasted image 20251120234710.png]]


# UDP header

![[Pasted image 20251120234737.png]]



![[Pasted image 20251120235102.png]]


![[Pasted image 20251120235229.png]]



# Piggybacking
Piggybacking is an optimization technique used in bidirectional (two-way) communication protocols (like the Sliding Window Protocol).

The Concept: In a two-way communication, station A sends data to station B, and station B needs to send an Acknowledgment (ACK) back to confirm it received the data.

Without Piggybacking: Station B sends a separate, tiny control frame just for the ACK. This wastes bandwidth.

With Piggybacking: Station B waits a short time to see if it has its own data packet to send to A. If it does, it "attaches" (piggybacks) the ACK onto that data packet.

Analogy: Imagine you are on a phone call.

No Piggybacking:

Person A: "How are you?"

Person B: "I am fine." (ACK)

Person B: "By the way, are you coming to the party?" (Data)

Piggybacking:

Person A: "How are you?"

Person B: "I am fine, and are you coming to the party?" (ACK + Data combined)

Pros & Cons:

Advantage: It saves bandwidth by reducing the total number of frames sent.

Disadvantage: If Station B has no data to send, the ACK is delayed. If it waits too long, Station A might think the data was lost and retransmit it unnecessarily.