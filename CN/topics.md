These foundational topics appear very regularly, often in Q1.

- **OSI Reference Model:** Be prepared to draw the 7-layer model and explain the functions or services of each layer1111. Sometimes questions target specific layers, like what OSI layer handles segmentation or routing222.
    
- **Networking Devices:** You must know the function of devices like **Router**, **Switch**, **Bridge**, **Gateway**, **Repeater**, and **Hub**3333.
    
- **Switching Methods:** Differentiate between **Circuit Switching and Packet Switching**44444.
    
- **Network Topologies:** Be able to list different topologies and explain at least one (like Star Topology) with its advantages and disadvantages5555.
    
- **Service Types:** A very common comparison is **Connection-Oriented vs. Connection-Less services**6666666666.
    
- **Transmission Delays:** Understand the different types of delays in packet transmission (like processing, queuing, transmission, and propagation delay)777777.
    

---

### 🖥️ Application Layer (L5/L7)

This is a highly reliable section for questions.

- **DNS (Domain Name System):** Explain how DNS works 88, including the hierarchical system 999999and resolution techniques1010.
    
- **HTTP:** Explain the HTTP protocol1111. A very common question is to compare **Persistent and Non-Persistent HTTP**12121212. You may also be asked to justify why HTTP is a "stateless" protocol131313.
    
- **Port Numbers:** Be prepared to list the well-known port numbers for protocols like **HTTP, SMTP, DNS, FTP, Telnet, and POP3**141414141414141414.
    

---

### 📦 Transport Layer (L4)

This layer is critical. Expect detailed questions on TCP.

- **TCP vs. UDP:** This is one of the most frequent comparison questions. You must be able to compare TCP and UDP in detail15151515151515.
    
- **TCP Congestion Control:** This is a major 7-mark question. Be ready to explain the TCP congestion control mechanism 1616161616, often including components like **Slow Start**1717.
    
- **TCP Segment & Flags:** Know the TCP segment structure 181818181818and be able to explain the significance of flags like **SYN, FIN, ACK, PSH, URG, and RST**19191919191919.
    
- **TCP Flow and Error Control:** Explain the mechanisms TCP uses for flow and error control202020202020.
    
- **Socket Programming Calls:** Know the purpose of system calls like **socket()** and **bind()**212121212121.
    

---

### 🗺️ Network Layer (L3)

This layer is heavily focused on routing and IP addressing.

- **IP Addressing & Subnetting:** This topic is **guaranteed** to be on the exam.
    
    - Explain the different **classes of IP addresses** (A, B, C)22222222.
        
    - Explain **subnetting** with an example23232323232323.
        
    - You may be given a numerical problem to find the number of hosts, subnet mask, or a specific customer's IP from a block24242424.
        
- **Routing Algorithms:**
    
    - **Distance Vector Routing:** Explain the algorithm25252525.
        
    - **Link State Routing:** Explain the algorithm2626262626.
        
    - **Count-to-Infinity Problem:** This specific problem with Distance Vector routing is asked very frequently as a separate question272727272727272727.
        
- **IPv4 vs. IPv6:** Be prepared to compare the two protocols28282828.
    
- **Virtual Circuit vs. Datagram Networks:** This is another common comparison question29292929.
    
- **ARP and NAT:** Know the purpose of Address Resolution Protocol (ARP) and Network Address Translation (NAT)303030303030.
    

---

### 🔗 Data Link Layer (L2)

Expect numerical problems and questions on access protocols.

- **Error Detection (CRC):** This is a very common **numerical problem**. You will likely be given a message and a generator polynomial (e.g., $x^4+x^2+1$) and asked to **generate the CRC code** or check for an error
    
- **MAC Protocols (Random Access):**
    
    - Explain different types of **CSMA** (e.g., CSMA/CD, p-persistent)
    - Explain **Slotted ALOHA**34343434343434.
        
- **Sliding Window Protocols:** Be able to describe and compare **Go-Back-N and Selective Repeat** protocols35353535.
    
- **Ethernet:** Know the 802.3 Ethernet standard or be able to explain the Ethernet frame structure36363636



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