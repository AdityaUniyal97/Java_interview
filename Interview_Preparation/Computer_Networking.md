# Why do we need layers ?
Layers are used to organise the protocols(are the set of rules , Every protocols have some header which define what is the message its details etc all of these are specified by the protocols) like HTPP , TCP, UDP , IP.

# What is OSI MODEL ?
<u><b>OSI(Open System Interconnect Mode)</b></u>  is more like a theorotical model becuse it is never used in the actual implementation of netwroking
- The model which is used in the actual implementation or over the internet is the <u><b>TCP(Transmission Control Protocols)</b></u>
- OSI says that we can divide our computer ntetwork into 7 layers .
  - *Aplication Layer
  -  Presentation Layer
  - Session Layer
  - Transportation Layer
  - Network Layer
  - Data Link Layer
  - Phycial Layer*
  
**1) Physical Layer** is repsonsible for transmitting the raw binary data(0 and 1s) between the device over the physical medium . It ensures the physical connections between the devices through wired or wire-less communciation

**2) Data Link Layer** uses the physical medium for communciation . it ensures 1 to 1 communication . Data Link layer is responisble for communciation between the local area network through devices like switches or either net.

**3) Network Layer** Data Link Layer provide 1 to 1 communication maybe using some switches or the shared media but if we want to connect to a device which is not directly connected to you maybe server in some other country than we use the services of the network layer.
- Network layer routes your message from local netwrok to some distant network . It helps to find the routes to that distant network.
- It include multiple routers(routers are network layer devices which routes your message from one end to another end)
- So there are multiple rotuers for sending or reciving messages from the distant and all these routing is happened using the Network Lyaer Devices.

<u><b>Transportation Layer</b></u> It is responisble for end to end delivery of the packets
- It break down the big data into smaller packets than reassembling htese smaller packets at the reciever side.
- Transport Layer usse to main protocols:
   - <u><b>TCP</b></u> Ensures a relibale communication llike a phone call where you make sure that the other pserson hears you clearly
   - <u><b>UDP</b></u> faster but less reilaible

<u><b>Session Layer</b></u> manages the coomunication session between the devices
 It is responsible for :
  - <u><b>Session Management</b></u> Establishing ,  mantaining , and terminating the session
  - <u><b>Auuthentication and Security</b></u> verifies the user device idenetity and ensures a secure communication
  - <u><b>Sets the CheckPoint</b></u> Sets the checkpoint so that if the communication break it can start agin from the last checkpoint

<u><b>Pesentation Layer</b></u> prepares the data for the application layer and make sure that the data is in readable format
- <u><b>Encryption and Decryption</b></u> To make communication safe it encrypt the data at the sender side using the secret key and than again decrypt it at the reciver side.

<u><b>Application Layer</b></u> This is the top most layer where user interact with the app 
- Application layer is responsible for implimenting protocols like HTTP for web-browser , SMTP for email , FTP for file transfer

<u><b>TCP/IP Model(Tranmission Control protocol)</b></u> divide the computer network into 4 layers

<u><b>Network Access Layer</b></u> Combines the physical and the data link layer of the OSI model

<u><b>Internet Layer</b></u> It is similar to the Network Layer in the OSI model
- Repsonsible for routing the data assigning the logical address. 
- It include protocol like TCP , ASAP etc

<u><b>Transport Layer</b></u> Manages the end to end communication between the devices
- Same as the Transport Layer in the OSI Model
- It uses the two main Protocols : TCP , UDP

<u><b>Application Layer</b></u> Handles the user interactions and implimetns the protocols like HTTP , FTP , SMTP

<u><b>Data Link Layer</b></u> The main task of the Data Link Layer is to take the data packet form the Network Layer add Header and Footer into it together  called as the FRAME , Than this Frame is sent over hte physical media which can be of wired or wireless network which only understand the binary(0s and 1s) than at the receiver end this package is recieved and than the data packet is send to the Netwokr layer.
# 1 How would you connect two remote offices ?
The two technologies which are used are
 **VPN(Virtual Private Network)=** It creates a secure encrypted connection over the internet , making it appears as if the device are on the same private network.
 **Cloud Computing=** Connects the offices through cloud based infrasturcures , enabling access to shared resources and services.

# 2 What is Internetworking? 
Internetworking means connecting multiple smaller netwroks to form one large network using devices  like the **router** or **gateways** . It allows multiple netwroks like the public , private or commerical to communicate as one . For example the internet is the largest internetwork connecting millions of smaller networks.

# 3 What are the user-support layers in the OSI Model?
The OSI model user support layers are :-> 
<u><b>Application Layer</b></u>  Provides services like the email , file transfer , and web browsing.
<u><b>Presentation Layer</b></u> Ensures the data is in readable format by translating it from formats like Encryption.
<u><b>Session Layer</b></u> Manges the sessions between applications , including opening , maintaing and closing connections

# 4 What are the networks-support in the OSI model ?
These layers manages data movement across networks : 
<u><b>Netwrok Layer</b></u> handles routing and addressing 
<u><b>Data Link Layer</b></u> Ensures reliable data transfer between adjacent nodes
<u><b>Physical Layer</b></u> Transmites the raw data trough wired cables or the wireless signals.

# 5 What is HTTPS ?
**HTTPS(Hyper Text Transfer Protocols Service)** is a secure version of HTTP . It uses SSL / TLS protocols to encrypt the communication , ensuing the data communication and privacy . It operats on the port 443 by default protecting sensitive information like the passowrds or credit cards number. 

# 6 What service does the aplication layer provide ?
Application layers in the internet model offer these serivces :
**Mail services** For sending or receiving the emails.
**Directory Services** To locate and manage the resources over the networks.
**File Transfer** For uploding and downloading files.
**Network Virtual Terminal** Simulate a terminal to interact with a remote host.

# 7 Where are headers and trailers added in the OSI  model ?
<u><b>Headers</b></u> are added at each layer(from layer 3 to layer 7) to provide control and address information.
<u><b>Trailer</b></u> are added at the data link layers to detect and correct the errors in the transmission.

# 8 What happens to data packets when moving betweeen the OSI layers ?
<u><b>Lower to Upper Layers</b></u> Headers are removed as the packets is proccessed by each layers
<u><b>Upper to Lower Layer</b></u> Headers are added to provide the neccessary information like the routing or the security details.

# 9 What is Zone-Based Firewall ?
Zone Based Firewall is a smart and secure way to control netwrok traffic . It divides network into different "zones"(like the internal or external) and applies specific rules for how traffic can flow between these zones. 
          **How it Wokrs**
<u><b>Traffic Monitoring :</b></u> The firewall tracks all the details of the traffic such as,
Who is sending the data(source IP).
Where it's going(destination IP address).
Which ports are used(soruce/destination ports).
<u><b>Allowing Replies</b></u> If someone inside your network start communication(e.g, an employee visiting a wbesite) , the firewall allows the reply from the website.
<u><b>Blocking Unwanted Traffic</b></u> If an outsides tries to send the data to your network without being requested , than firewall will automatically blocks it.

# 10 What is Server Farm ?
A server farm is a collections of servers working together in the same location to perfrom high - volume task . They are used for applications like :
Hosting website
handling large - sclae  computations
Supporting cloud services.
Benefits include improved performance  , scalability  and redundency.

# 11 What are the three main methods of users authentications ?
<u><b>Passwords</b></u> A secret word or the phrase which is only known to the users.
<u><b>BioMetrics</b></u> Physical traits like a finger print or the iris scan
<u><b>Two-Factors Authentication</b></u> used for higher security

# 12 What is a CIA traid in a network security ?
CIA stands for Confidentiality , Integretiy , and Availability.
<u><b>Confidentially</b></u> Ensuers that the information is only accessible to the authorized individuals. Encrpting data to prevent from unauthorized access
<u><b>Integrity</b></u> Ensure the data is accurate and hasnt been tempered . Example using digital signature to vairfy documents
<u><b>Availabilty</b></u> Ensure that data is accessible when needed . 

# 13 What is VPN ?
<u><b>VPN(Virutal Private Network)</b></u> provides a secure communication between a device and a private network over a public netwrok(like a internet)
It encrypt the data for security .
It allows remote users to access interal resources , as they are physically present in the network.

# 14 What is the difference between the Symmetric and Asymmetric Encryption
<u><b>Symmetric Encryption</b></u> Uses the same key for encryption and decryption . it is fast but less secure since the key must be shared
<u><b>Assymetric Encryption</b></u> Uses a public key for encryption and private key for decryption . It is more secure but slower due to complex key generation
# 15 At what layer does IPsec Work?
<u><b>Ipsec</b></u> work on the Network Layer(Layer 3) , securing data transfer between devices by encrypting and authenticating each IP packet.

# 16 What are Digital Signature ?
<u><b>Digital Signature</b></u> ensure the authenticity of a message or a document by verifying the identity of the sender and ensuing that the data has not been tempered 

# 17 What is the defference between a Firewall and IPS(Intrusion Prevention System)
<u><b>Firewall</b></u> blocks unauthorized traffic based upon the predefined rules . Example Blocking traffic from the suspiscius IP address.
<u><b>IPS</b></u> Actively montior the traffic and takes neccessary action 

