
## IOT and its applications and characteristics

The Internet of Things (IoT) refers to the network of physical devices, vehicles, home appliances, and other items that are embedded with sensors, software, and network connectivity, allowing them to collect and exchange data.

## Applications 
-Smart homes
-Smart cities
-Industry automation
-Smart vehicles
-Healthcare
-Wearables
-Transport
-Education
-Defence


## Characteristics

-Connectivity
-Identity
-Intelligence
-Scalability
-Safety
-Security


## Components of IoT System

-Microcontroller
-Sensors/Actuators
-Communication module
-cloud
-Application/UI



# IoT Stack 

|Sr. No|Layer|What It Contains|What It Actually Does (Understand This Deeply)|
|---|---|---|---|
|1|**Physical / Sensor Layer**|Temperature, humidity, pressure, motion, gas sensors etc.|This layer interacts with the real world. Sensors convert physical signals (heat, light, movement) into electrical signals. It is the data collection layer. Without this, IoT cannot "feel" anything.|
|2|**Processing & Control Layer**|Microcontroller, processor, embedded OS|This is the brain layer. The microcontroller receives data from sensors, processes it using programmed logic, and decides actions. It may trigger actuators like motors or relays. Example: If temperature > 40°C → Turn ON fan.|
|3|**Hardware Interface Layer**|Serial communication components like RS232, SPI, I2C, CAN|This layer enables internal device communication. It allows sensors and controllers to talk to each other inside the hardware system. Think of it as wiring and communication pathways inside the device.|
|4|**RF / Communication Layer**|WiFi, Bluetooth, Zigbee, Cellular, LoRa|RF stands for Radio Frequency. This layer sends data wirelessly or via network to other devices or cloud. It handles short-range and long-range communication. This is how devices connect to the Internet.|
|5|**Session / Message Layer**|MQTT, HTTP, FTP, CoAP, SSH|This layer manages how data is packaged and sent. It defines messaging rules and protocols for communication between devices and servers. Example: MQTT is lightweight and widely used in IoT.|
|6|**User Experience Layer**|UI, dashboards, databases, SQL, web or mobile apps|This layer presents processed data to users. It includes applications, dashboards, alerts, and analytics. It allows users to monitor and control IoT devices.|
|7|**Application Layer**|Smart home, smart agriculture, smart healthcare, smart city systems|This is the final implementation layer where IoT solves real-world problems. It defines the actual use case of the system.|



# IoT challanges 

- Security – Protecting devices and data from cyber attacks.
    
- Privacy – Safeguarding sensitive user information.
    
- Scalability – Handling large numbers of devices and data efficiently.
    
- Interoperability – Ensuring communication between heterogeneous devices.
    
- Power Management – Optimizing energy consumption of devices.
    
- Data Management – Managing, storing, and processing large volumes of data.
    
- Connectivity – Maintaining reliable communication in diverse environments.
    
- System Complexity – Integrating hardware, software, and networking components effectively.



# Enabling Technologies

-Sensors 
-Cloud computing
-Big data analysis
-Embedded computing boards
-Communication protocols
-User interface 



# IoT Levels

IoT levels define the complexity and architecture of IoT systems based on how devices communicate, process data, and integrate with cloud services. They range from simple device-to-device communication to large-scale distributed intelligent systems involving gateways, cloud computing, and edge processing.


Level 1 :  this is the smallest and least complicated level . 
	     less devices are used 
	     no need for internet connection
	     data is collectd and processed locally 
	     one sensor is used 
	     monitoring and control is done through application
	     data generated is not so huge so stored locally
	     ex - temp sensor senses data and based on logic applied action can be triggered 

Level 2 : this level is little more complex than lvel 1 
         here data is sensed more frequently
         so data is generated more than level 1 
         analysis is done locally
         but stored on cloud 
         based on analysis the control action is triggered  through web or mobile application

Level 3 : Data sensing is so fast 
         volume of data is huge 
         so storage is done on cloud 
         and analysis is also done on cloud 
         based on applied analysis or logic the control action can be triggered  through the web or mobile application 

Level 4 :  here multiple sensors are used 
         All the sensors sense the data at the same ttime 
         and upload it on the cloud 
         analysis is done on the cloud 
         and storage is also done on the cloud 
         based on the analysis the control action can be triggered through the mobile or web application 

Level 5 :  here many sensors are used 
         data volume is so high that everything can not be stored and analysed 
         so a gateway node is used 
         all the sensors/nodes sends the data to gateway 
         gateway then filters the data and formats it and sends it to the cloud 
         then analysis is performed and control action can be triggered through any medium



# Cyber Physical System

A Cyber Physical System (CPS) is an integration of computation, networking, and physical processes where embedded computers and networks monitor and control physical processes through feedback mechanisms in real time.

Every CPS has:

1️⃣ Physical Components  
Machines, motors, sensors, actuators

2️⃣ Cyber Components  
Algorithms, software, embedded systems

3️⃣ Networking  
Communication between physical and cyber parts

4️⃣ Feedback Control  
Continuous monitoring and correction

|IoT|Cyber Physical System|
|---|---|
|Focuses on connectivity|Focuses on control|
|Sends data to cloud|Makes real-time decisions|
|Can work without tight feedback|Requires continuous feedback|
|Example: Smart fitness tracker|Example: Self-driving car|



# WSN

A Wireless Sensor Network (WSN) is a network of spatially distributed autonomous sensor nodes that monitor physical or environmental conditions and cooperatively pass data through wireless communication to a central base station.


- Nodes collect data
    
- Data is transmitted to neighboring nodes
    
- Data eventually reaches a Base Station (Sink Node)
    
- Base station processes or sends data to server/cloud

Application : 

- Forest fire detection
    
- Military surveillance
    
- Environmental monitoring
    
- Smart agriculture
    
- Industrial monitoring

|WSN|IoT|
|---|---|
|Focuses on sensing|Focuses on connecting things|
|Mostly sensor-based|Includes sensors + actuators + cloud|
|Usually local network|Global internet connectivity|
|Designed for monitoring|Designed for monitoring + control|



# M2M 
Machine to Machine (M2M) communication refers to the direct exchange of data between devices over wired or wireless networks without human intervention, primarily used for monitoring and control purposes.

- ATM machines communicating with bank servers
    
- Smart electricity meters
    
- Industrial machines reporting performance
    
- Vending machines sending stock status
    
- Vehicle tracking systems

| M2M                          | IoT                                |
| ---------------------------- | ---------------------------------- |
| Direct machine communication | Internet-based connected ecosystem |
| Often point-to-point         | Cloud-centric architecture         |
| Usually closed system        | Open, scalable system              |
| Limited scalability          | Massive scalability                |
| No strong focus on user apps | Includes user interfaces           |




# Microcontroller 

A microcontroller is a small and low-cost microcomputer, which is designed to perform the specific tasks of embedded systems like displaying microwave’s information, receiving remote signals, etc. 
The general microcontroller consists of the processor, the memory (RAM, ROM, EPROM), Serial ports, peripherals (timers, counters), etc.


# Specifications of a Sensor
|Specification|Meaning|
|---|---|
|Range|Minimum and maximum measurable value|
|Accuracy|Closeness to true value|
|Precision|Repeatability of measurements|
|Sensitivity|Output change per unit input change|
|Resolution|Smallest detectable change|
|Response Time|Time taken to react to input change|
|Linearity|Proportional relationship between input and output|
|Drift|Gradual deviation over time|
|Hysteresis|Output difference for increasing vs decreasing input|


# Microprocessor VS Microcontroller

|Microprocessor|Microcontroller|
|---|---|
|Microprocessors can be understood as the heart of a computer system.|Microcontrollers can be understood as the heart of an embedded system.|
|A microprocessor is a processor where memory and I/O components are connected externally.|A microcontroller is a controlling device where memory and I/O components are present internally on the same chip.|
|The circuit is complex due to external connections.|The circuit is less complex since components are integrated on a single chip.|
|Memory and I/O components must be connected externally.|Memory and I/O components are already available on-chip.|
|Cannot be used easily in compact systems.|Suitable for compact systems.|
|Generally consumes more power and is less efficient for small tasks.|Power efficient and optimized for specific control tasks.|
|Microprocessors typically have fewer built-in peripherals.|Microcontrollers have built-in peripherals like timers, ADC, serial communication modules etc.|
|Mainly used in personal computers and high-performance systems.|Used in washing machines, air conditioners, traffic lights, IoT devices, and embedded systems.|



# Arduino uno specs

Atmega328p microcontroller
5v operating voltage given by
		-usb
		 -external power socket
14 digital pins
6 analog pins
32kb flash memory
1kb sram
2kb eeprom

# Sensor
 is a device that measures/senses physical inputs from the environment and converts it into data which can be read by human or machines
		 -digital sensor
		 -analog sensor

--Gas sensor
--
![[Pasted image 20260305120015.png]]
--Obstacle sensor
--
![[Pasted image 20260305120038.png]]
--gyro sensor
--
--Heart beat Sensor
--
--Ultrasonic sensor
--
--LDR sensor
--
--PH sensor
--
--GPS sensor
--
--color sensor
--

# Category of sensors
![[Pasted image 20260307214925.png]]


# ARM
	Advance risc machine is a family of RISC-based processor architectures widely used in embedded systems, mobile devices, and IoT applications due to their low power consumption, high efficiency, and compact design.

it is a 32 bit procesessor
it has reverse compatibility (32 bit aloows 16 and 8 bit variants itself)
good speed /power consumption ratio
it has barrel shifter which enhances the hardware usage 
build on auto increment and decrement addresseing modes 
![[Pasted image 20260305130138.png]]
it has 13 general purpose registers  r0 - r12
all the registers are of 32 bits 

it has 3 special funtion registers 
r13  - stack pointer - holds adrees of tof of the stack
r14 - link register - holds next instruction adddress to return when branching to other instructions
r15 - program counter - address of next instruction to be executed 

one more register CPSR


CPSR stand for current program status register 
CPSR (Current Program Status Register) is a 32-bit register in ARM architecture that stores condition flags, processor mode information, interrupt control bits, and execution state, thereby controlling the operation and behavior of the processor.

![[Pasted image 20260305171652.png]]
![[Pasted image 20260305171705.png]]


![[Pasted image 20260308110255.png]]
![[Pasted image 20260308110734.png]]
![[Pasted image 20260308111005.png]]
# MQTT

MESSAGE QUEING  TELEMETRY TANSPORT
IT IS A LIGHTWEIGHT LOW BANDWIDTH PROTOCOL
DESIGNED FOR RESOURCE CONSTRAINED ENVIRONMENT
IT WORKS ON PUBLISH SUBSCIRBE MODEL
THE PUBLISHER SENDS THE MESSAGE TO MQTT BROKER 
AND THE BROKER THEN SENDS THAT MESSAGE TO THE SUBSCRIBER OF THAT TOPIC 
A PUBLISHER CAN BE ANY DEVICE IN A NETWORK WHICH PRODUCES AND TRANSMITS THE DATA LIKE A TEMPRATURE SENSOR 
SUBSCRIBERS ARE THE NODES INTERESTED IN/RECIEVING THE PERTICULAR DATA (TOPIC) 
ONLY SUBSCRIBER OF THAT TOPIC RECIEVES THE DATA HOWEVER THE DATA IS TRANSMITTED TO ALL THE DEVICES . 
THERE CAN BE MULTIPLE SUBCRIBERS OF A SINGLE TOPIC AND SINGLE NODE CAN SUBCRIBE TO MULTIPLE TOPICS 
ONE NODE CAN BE A SUBCRIBER AND PUBLISHER AT THE SAME TIME 
![[Pasted image 20260308113125.png]]
![[Pasted image 20260305180711.png]]
![[Pasted image 20260308105429.png]]



# COAP
![[Pasted image 20260308113419.png]]
![[Pasted image 20260308113632.png]]


# IPv4
![[Pasted image 20260308114613.png]]

![[Pasted image 20260308114921.png]]
## Traffic Class (8 bits)
This field controls **packet priority and traffic handling**.
It helps routers decide which packets should get faster service.

## Flow Label (20 bits)
This is used to identify **packets belonging to the same flow**.
A **flow** means a stream of packets from the same source to destination.

## Next Header (8 bits)
This field tells **what comes after the IPv6 header**.
It can indicate:
- a transport protocol
- another extension header

## Hop Limit (8 bits)
This prevents packets from circulating forever.
Each router **reduces the value by 1**.
If it reaches **0**, the packet is discarded.


## Features of Arduino

### 1. Open Source

Both hardware and software designs are open to everyone.

### 2. Easy Programming

Uses a simple **C/C++ based language** through the Arduino IDE.

### 3. Low Cost

Boards are inexpensive and widely available.

### 4. Digital and Analog Pins

Allows connection to many devices like sensors and motors.

### 5. USB Interface

Programs can be uploaded directly through a USB cable.

### 6. Cross Platform

Works on Windows, Linux, and Mac.

### 7. Large Community

Huge number of tutorials and libraries available.




![[Pasted image 20260308170133.png]]

![[Pasted image 20260308170141.png]]