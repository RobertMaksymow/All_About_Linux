Networking_concepts

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

### 2. Protocols: TCP/IP
A protocol is a set of rules that defines how data is transmitted and received between advices in a network.<br>
It ensures standardized communication, allowing different systems to understand and intearct with each other. Examples include TCP/IP, HTTP, and SMTP (mail protocol) <br>
TCP/IP - Transmission Control Protocol / Internet Protocol <br>
TCP operates at the transport layer of the OSI model. It establishes a connection between two devices before data exchange, ensuring reliable and ordered delivery of information. <br>
It breakes data into packets, assigns sequence numbers, and uses acknowledgment messages to guarantee delivery. It's connection oriented, meaning it sets up, maintains and terminates a connection for data exchange.<br>
