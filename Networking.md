A computer network is a system where multiple computers are connected with each other  to share resources , data to each other . These connections can be established using the wired and wireless network.
### Goal of Networking
**Resource Sharing** Resources can be easily shared like printers, internet connections
**Data Accessiblity** Real time access to file and data bases locally and remotely
**Comunication** provide seamless comunication for data exchange
**Scalaility** provide flexibilty to grow by adding new devices

### Transmission Mode
Transmission Mode refer to the direction in which the data is flowing between two devices . 
**Simple Mode** = Here the data only flow in one direction like one device sending the data the other device can only recive it.
**Half-Duplex** = Here the data travels in both the direction but not in the same times 
**Full-Duplex** = Here the data travels in both the direction in same time like in Phone call. 

### Types of Networks
**LAN(Local Area Network)** = LAN is small area network that allow the devices to communicate with each other in confied area. 
LAN speed is fast
Ex = Office Network , School Network
**MAN(Metropoliton Area Network)** = MAN allow the devices to comunicate with each other in  region roughly like a metropoliton city
Ex: Switches , hub
**WAN(WIde Area Network)** = WAN allow the devices to communicate with each other in large geographical areas . WAN work by connecting several LAN and MAN for large coverage
WAN speed is slow as compare to LAN and MAN
**PAN(Personal Area Network)** = PAN allow the devices to communicate with each other in very limited area , typically in few meters 
Ex = Personal Hotspot

### Interconnected Network
Formed by connecting multiple networks like LAN,WAN,MAN,PAN 
**Merits**
**Scalable** = Easy to expand
**Improve Communication** = Inhances the communication between the deivces
**Dimerits
Latency** = Data trasfer becomes slow
**Security Risk** = interconnected Network are not secure cause their are multiple netowrk together

### Network Topology
Network topology refer to the arrangemement of the devices and the connections in a netwrok . It determine how the data will flow among all the devices in a network
#### Types of Topology
**Pysical Topology** represent the arrangement of cables, computers and other devices
**Logical Topology** logically represent how the data will flow in the network
#### <u>Physical Topologies</u>
**Star Topology** here all the devices are connected to a central hub.
Advantages 
- Easy to add and remove the devices
- Fault taolrence is simple
Disadvantage
- If hub fails entire network get disables
- High cost for maintaing the hub
Ex: Shoping mall security system where all the camera are connected to a central control room

**Ring Topoly** here all the devices are arranged in a circular manner. Data travels in one direction
Advantage:
- Equal opportunity for data transmission
- No collision since data is travelling only in one direction
Disadvantage:
- A single failure will disrupt the network
ex: Circular metro system

**Bus Topolgy** here all the devices are connected to a single communication line 
Advantage:
- Cost effective
Disadvantage:
- Limited number of devices can connect
- If the Backbone cables fails entire network will fail

**Mesh Topology** Each device is connected to every other device.
Advantage:
- Highly reliable as each device is conencted to one another so thier is no case of single point of failure
Disadvantage:
- Mainting the Mesh topology can be expnesive
ex = Spider web
#### Comparison of Topologies

| Feature         | Star Topology          | Ring Topology              | Mesh Topology          | Bus Topology              |
| --------------- | ---------------------- | -------------------------- | ---------------------- | ------------------------- |
| Structure       | Central hub            | Circular loop              | Fully interconnected   | Single communication line |
| Fault Tolerance | Moderate (hub failure) | Low (one failure disrupts) | High                   | Low                       |
| Cost            | Moderate               | Low                        | High                   | Low                       |
| Scalability     | Easy to expand         | Difficult to expand        | Difficult but reliable | Limited                   |
## Logical topology 
 logically represent how the data will flow in the network
 **Logical Bus Topolgy** 
 - All the deivces are connected to a common medium
 - Data is sent to all the connected devices but ony allowed reciver can process it
 **Logical Ring Topology**
 - Data is flow in a circular direction

### Token passing
- Is a protocol where a special data packet(token) travel within the network. 
- All the device in a network must have this token to communicate in order way
Advantage:
- Prevents collision since data is travelling in a order
- Token passing uses the Ring Topologiy

### Fiber Distributed Data Interface(FDDI)
- FDDI is a high speed networking which uses the optical fiber or copper cables I
- t uses the Ring Toplogy for fault tolerence
Advatnage:
- Support data rate upto 100mbps

### Virtual LANs(VLAN)
- VLAN is a logical grouping of devices  unrelated to thier physical location
Advantage:
- VLAN divide the network for improved perfromance
- Reduce traffic


## OSI Models and Layer
Open Source Interconnection is a more like a theoritical model becuse it is never used in a actual implimentation
OSI says that we can divide our computer ntetwork into 7 layers .
  -  *Aplication Layer- 
  -  Presentation Layer
  - Session Layer
  - Transportation Layer
  - Network Layer
  - Data Link Layer
  - Phycial Layer*
  **Pysical Layer** is responsible for transmitting the raw binary data between the devices over the physical medium
  **Data Link layer** Uses the physical medium for communication and provide 1 to 1 coummunication
 **Network Layer** is responsible for routing the data packet between the devices and between different network
 - Uses the IP address for identifying the reciver
 - Routing  = Provide the best path fof the data
 - Packet Forwarding = Transfer the data from source to destination 
 **Transport Layer** is responsible for end to end deliver of the packet , it does breaking down the big data into smaller packets and than reassembling these packets on the reciver side
 - Transport Layer uses two important protocols 
 - *TCP* , UDP
 **Session Layer** Manages the communication session between the devices, It is responsible for
 - Session Mangement = Establishing , maintaining and terminating the sesion
 - Authentication Management = Verifies the user device and establish secure communication
**Presentation Layer** here the data is prepared for the user
- Encrpt = to make communication safe data is encrypted on the sender side and decrypt on the reciver side
**Application Layer**  This is the top most layer where the user interact with the app
- Application layer is responsible for implimenting the HTTP for web-browser,smtp for email , FTP for file transfer

## TCP/IP
TCP/IP Model is a practical framework that tells how the devices will communicate over the internet. Unless OSI model it has only four layers for communication
#### Layers of TCP/IP MODEL
**Networking Interface Model** Manage the hardware and physical data transmission
**Internet Layer** Handles data packet routing and addresing using IP
**Transport Layer** Ensure realible delivery of the data
**Appliacation Layer** Provide user service like email , web briowsing

## Netowork Cabeling
Network cabeling is the physical infrastructure that connects devices to a network , allowing them to share data and communicate. 

**Twisted Pair Cable** 
Is a type of cable used for network and telephone communication that consist of two or moe pairs of insulated copper wire twisted together **Types**
- **Unshielded Twisted Pair(UTP)** Most common and used in LAN(Local Area Network)
- **Shieleded Twisted Pair(STP)** Equiped with protective shild to minimize the external interference  

**Fiber Optics cables**
It is a cables that transmit the data as light pulses through glass or plastic fibre . They are used in many communication inluding telephonic , networking and lighting 
**Types**
- **Single-Mode Fiber** Transmit a signle light wave, good for long dsitance communication
- **Multi-Mode Fiber** Transmit multiple waves & offer cost effective

## Network Devices
**Router** is a networking device that connects multiple networks together and routes the data packets between them using IP address
- Router finds the best path for data transmission
- Connects the local netwrok to internet

**Switch** is used to connect multiple devices within the same network and transfer the data to the reciver using his MAC address

**Hub** is a basic networkign device that broadcast the data to all the connected devices.

**Repeater** applies and regenerate the data signa; to extend its range
