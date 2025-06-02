# Networking_concepts <br>
Random knowledge from the Internet on Networking <br>
https://youtu.be/M9Kex1ID7GY?si=s6Bw1IRAeFaTSAFi <br>
https://www.geeksforgeeks.org/open-systems-interconnection-model-osi <br>

1. OSI Model
2. Protocols: TCP/UDP/IP
3. Ports
4. Subnettingg
5. Routing
6. DNS
7. Firewalls and Security Groups
8. HTTP/HTTPS
9. CDN (Content Delivery Network)
10. VPN (Virtual Private Network)
11. Networking tools

### 1. OSI Model (Open Systems Interconnection Model)
Is a framework with seven layers that standardizes how different computer systems communicate. From the physical connection (layer 1) to end-user services (layer 7). Each layer has a specific role in managing aspects like hardware, addresssing, routing, and application-level interactions.
It simplifies understanding and trouble shooting network processes.



![image](https://github.com/user-attachments/assets/a2916fb0-a192-49d4-a37e-ffc3f4255644)
![image](https://github.com/user-attachments/assets/b4f150e8-eb91-474b-9b2b-93ae28790123)
Application / Presentation / Session layers from OSI are equvalent of Application layer in TCP/IP <br>
Data link / Physical layers are equivalent of Network Access in TCP/IP
![image](https://github.com/user-attachments/assets/7a1156c0-9398-4a3b-b90c-c6a7c29e6c22)

#### Layer 7: Application Layer
At the very top of the OSI Reference Model stack of layers, we find the Application layer which is implemented by the network applications. These applications produce the data to be transferred over the network. This layer also serves as a window for the application services to access the network and for displaying the received information to the user. Protocols used in the Application layer are SMTP, FTP, DNS, etc.

![image](https://github.com/user-attachments/assets/7a688030-2457-4b70-b6ce-2ea3689dd5ea)

Functions of the Application Layer
The main functions of the application layer are given below.

Network Virtual Terminal (NVT): It allows a user to log on to a remote host.
File Transfer Access and Management (FTAM): This application allows a user to access files in a remote host, retrieve files in a remote host, and manage or control files from a remote computer.
Mail Services: Provide email service.
Directory Services: This application provides distributed database sources and access for global information about various objects and services.
How Data Flows in the OSI Model?
When we transfer information from one device to another, it travels through 7 layers of OSI model. First data travels down through 7 layers from the sender's end and then climbs back 7 layers on the receiver's end.

Data flows through the OSI model in a step-by-step process:
![OSI-Model](https://github.com/user-attachments/assets/a2ef7c5f-5f8d-4094-b0e1-f42bce99078c)



Application Layer: Applications create the data.
Presentation Layer: Data is formatted and encrypted.
Session Layer: Connections are established and managed.
Transport Layer: Data is broken into segments for reliable delivery.
Network Layer: Segments are packaged into packets and routed.
Data Link Layer: Packets are framed and sent to the next device.
Physical Layer: Frames are converted into bits and transmitted physically.

#### Layer 6: Presentation Layer
The presentation layer is also called the Translation layer. The data from the application layer is extracted here and manipulated as per the required format to transmit over the network. Protocols used in the Presentation Layer are TLS/SSL (Transport Layer Security / Secure Sockets Layer).JPEG, MPEG, GIF, are standards or formats used for encoding data, which is part of the presentation layer’s role.

Functions of the Presentation Layer
Translation: For example, ASCII to EBCDIC.
Encryption/ Decryption: Data encryption translates the data into another form or code. The encrypted data is known as the ciphertext, and the decrypted data is known as plain text. A key value is used for encrypting as well as decrypting data.
Compression: Reduces the number of bits that need to be transmitted on the network.

#### Layer 5: Session Layer
Session Layer in the OSI Model is responsible for the establishment of connections, management of connections, terminations of sessions between two devices. It also provides authentication and security. Protocols used in the Session Layer are NetBIOS, PPTP.

Functions of the Session Layer
Session Establishment, Maintenance, and Termination: The layer allows the two processes to establish, use, and terminate a connection.
Synchronization: This layer allows a process to add checkpoints that are considered synchronization points in the data. These synchronization points help to identify the error so that the data is re-synchronized properly, and ends of the messages are not cut prematurely, and data loss is avoided.
Dialog Controller: The session layer allows two systems to start communication with each other in half-duplex or full duplex.
Example

Let us consider a scenario where a user wants to send a message through some Messenger application running in their browser. The “Messenger” here acts as the application layer which provides the user with an interface to create the data. This message or so-called Data is compressed, optionally encrypted (if the data is sensitive), and converted into bits (0’s and 1’s) so that it can be transmitted.
![image](https://github.com/user-attachments/assets/2113388f-f092-4146-b560-5ea3b8f39284)


#### Layer 4: Transport Layer
The transport layer provides services to the application layer and takes services from the network layer. The data in the transport layer is referred to as Segments. It is responsible for the end-to-end delivery of the complete message. The transport layer also provides the acknowledgment of the successful data transmission and re-transmits the data if an error is found. Protocols used in Transport Layer are TCP, UDP NetBIOS, PPTP.

At the sender's side, the transport layer receives the formatted data from the upper layers, performs Segmentation, and also implements Flow and error control to ensure proper data transmission. It also adds Source and Destination port number in its header and forwards the segmented data to the Network Layer.

Generally, this destination port number is configured, either by default or manually. For example, when a web application requests a web server, it typically uses port number 80, because this is the default port assigned to web applications. Many applications have default ports assigned.
At the Receiver’s side, Transport Layer reads the port number from its header and forwards the Data which it has received to the respective application. It also performs sequencing and reassembling of the segmented data.

Functions of the Transport Layer
Segmentation and Reassembly: This layer accepts the message from the (session) layer and breaks the message into smaller units. Each of the segments produced has a header associated with it. The transport layer at the destination station reassembles the message.
Service Point Addressing: To deliver the message to the correct process, the transport layer header includes a type of address called service point address or port address. Thus, by specifying this address, the transport layer makes sure that the message is delivered to the correct process.
Services Provided by Transport Layer
Connection-Oriented Service
Connectionless Service

#### Layer 3: Network Layer
The network layer works for the transmission of data from one host to the other located in different networks. It also takes care of packet routing i.e. selection of the shortest path to transmit the packet, from the number of routes available. The sender and receiver's IP address are placed in the header by the network layer. Segment in the Network layer is referred to as Packet. Network layer is implemented by networking devices such as routers and switches.

Functions of the Network Layer
Routing: The network layer protocols determine which route is suitable from source to destination. This function of the network layer is known as routing.
Logical Addressing: To identify each device inter-network uniquely, the network layer defines an addressing scheme. The sender and receiver’s IP addresses are placed in the header by the network layer. Such an address distinguishes each device uniquely and universally.

#### Layer 2: Data Link Layer (DLL)
The data link layer is responsible for the node-to-node delivery of the message. The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer. When a packet arrives in a network, it is the responsibility of the DLL to transmit it to the Host using its MAC address. Packet in the Data Link layer is referred to as Frame. Switches and Bridges are common Data Link Layer devices.

The Data Link Layer is divided into two sublayers:

Logical Link Control (LLC)
Media Access Control (MAC)
The packet received from the Network layer is further divided into frames depending on the frame size of the NIC (Network Interface Card). DLL also encapsulates Sender and Receiver’s MAC address in the header.

The Receiver’s MAC address is obtained by placing an ARP (Address Resolution Protocol) request onto the wire asking, "Who has that IP address?" and the destination host will reply with its MAC address.

Functions of the Data Link Layer
Framing: Framing is a function of the data link layer. It provides a way for a sender to transmit a set of bits that are meaningful to the receiver. This can be accomplished by attaching special bit patterns to the beginning and end of the frame.
Physical Addressing: After creating frames, the Data link layer adds physical addresses (MAC addresses) of the sender and/or receiver in the header of each frame.
Error Control: The data link layer provides the mechanism of error control in which it detects and retransmits damaged or lost frames.
Flow Control: The data rate must be constant on both sides else the data may get corrupted thus, flow control coordinates the amount of data that can be sent before receiving an acknowledgment.
Access Control: When a single communication channel is shared by multiple devices, the MAC sub-layer of the data link layer helps to determine which device has control over the channel at a given time.

#### Layer 1: Physical Layer
The lowest layer of the OSI reference model is the Physical Layer. It is responsible for the actual physical connection between the devices. The physical layer contains information in the form of bits. Physical Layer is responsible for transmitting individual bits from one node to the next. When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together. Common physical layer devices are Hub, Repeater, Modem, and Cables.
![image](https://github.com/user-attachments/assets/c834c53a-4a65-4601-af3d-b506656297d8)
Functions of the Physical Layer <br>
Bit Synchronization: The physical layer provides the synchronization of the bits by providing a clock. This clock controls both sender and receiver thus providing synchronization at the bit level.
Bit Rate Control: The Physical layer also defines the transmission rate i.e. the number of bits sent per second.
Physical Topologies: Physical layer specifies how the different, devices/nodes are arranged in a network i.e. bus topology, star topology, or mesh topology.
Transmission Mode: Physical layer also defines how the data flows between the two connected devices. The various transmission modes possible are Simplex, half-duplex and full duplex. <br>


### 2. Protocols: TCP/IP
A protocol is a set of rules that defines how data is transmitted and received between advices in a network.<br>
It ensures standardized communication, allowing different systems to understand and intearct with each other. Examples include TCP/IP, HTTP, and SMTP (mail protocol) <br>
TCP/IP - Transmission Control Protocol / Internet Protocol <br>
TCP operates at the transport layer of the OSI model. It establishes a connection between two devices before data exchange, ensuring reliable and ordered delivery of information. <br>
It breakes data into packets, assigns sequence numbers, and uses acknowledgment messages to guarantee delivery. It's connection oriented, meaning it sets up, maintains and terminates a connection for data exchange.<br>
