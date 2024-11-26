* COMPUTER: commonly operating machine, particularly used for technlogical and educational research

* US govt --> ARPA --> Advance Research Progress Agency
* "arpa net"
* TCP - Transmission Control Protocol
  
### PROTOCOL:
* The set of rules designed by internet society
* The set of rules regulation to follow to do an operation over the internet
* like, how our application should communicate with other applications

### TCP - Transmission control Protocol:
* TCP will ensure the data successfully reaches its desination with its complete data without any lost
* example: security email(passcodes..)

### UDP - User Datagram protocol:
* If we do not want to send a complete msg , but just wants to send, at the time we can use UDP protocols
* so some data can be lost when via UDP
* example: Video conference

### HTTP -Hyper Text Transfer Protocol:
* used by world wide web(www)

### DATA:
* we are getting the data from server as "packets"

### IP Address:
* An IP address is the "identity" of each host.
* IP address will determine where our computer located
* PORT NO will determine which application we are using
* IP addresses are 32 bits(os and 1s)
* Repreented as four Octets --> x.x.x.x
* x ---> 0 to 255

### PORT:
* IP address will determine where our computer located
* PORT NO will determine which application we are using
* PORT NO --> 16 bit (2^16 ~ 65000)
* HTTP --> 80 --> default port no
* Mongodb --> 27107 --> default port no
* SQL --> 1433 --> default port no

### HOST:
* HOSTS are any device which send or receive traffic
* clients and servers

* 1 mbps --> mega bits per second
* 1 gbps --> giga bits per second
* 1 kbps --> kilo bits per second

### PACKETS:

### Network Types:
* LAN --> Local Area Network --> within a building
* MAN --> MetroPolitan Area Networkc--> across a city
* WAN --> Wide Area Network -> across countries
* LAN -> MAN -> WAN
* Optical Fiber Cables
* Frame relay

### ISP - Internet Service Provider:
* In india -> TATA (a large cable from chennai to singapore)

### Moderm
* Moderm will convert tha data to "electrical signal" to send to another moderm(reciever) or some device

### TOPOLOGIES:
* **Bus Topology** --> if one area got damaged, the entire connection will be spoiled.
  
* **Ring Topology** --> computers connected in the ring (round) format, every one can communicate with one another as one by one, like msg from 1 to 5 , it should travel from 1->2->3->4->5 like this only will communicate.
* Here also, if one cable breaks, the entire communication will be spoiled
  
* **Star Topoogy** --> one central device with several devices, all devices can communicate via that central device only.
* if central device breaks, the entire communication will go down

* **Tree Topology** --> combination of bus topology and star topology

* **Mesh topology** --> every single computer is connected with every single computer.
* limitations --> expensive, because more cables needed to connect every one with every one.
* scalability issues also.

## Structure of Network:

### OSI model --> OPEN SYSTEM INTERCONNECTION MODEL
* How two or more computer communicate with each other.
* OSI has 7 layers
  1. Application layer
  2. Presentation Layer
  3. session layer
  4. transport layer
  5. network layer
  6. data link layer
  7. physical layer

### 1. Application Layer
* It is implemented in software
* like, to manage the application users, contains applications
* it will send to presentation layer(down one)

### 2. Presentation Layer
* it will convert tha data(chars, numbers, words) to binary machine language( os and 1s)
* it will send the comverted data to session layer(down one)

### 3. Session layer:
* setting up and managing the connections
* authentication perfomed.
* it will send the established session with next layer -> transport layer (down one)
  
### Transport Layer:
* ensure the data to send to the nest layer --> network layer
* here, TCP and UDP performs
* it will send to network layer (down one)

### Network Layer:
* will communicate from one computer to another computer in different network locations.
* logical addressing --> IP Address.
* network layer will asign the IP Address to the sender and reciever
* It will generate the IP Packets
* also it performs routing
* moving the data packets from source to destination
* all routing protocols, the transportation of packets are all done by network layer.
* it will the data packets to data link layer.

### Data Link Layer
* it will recieve the data packets from network layer
* the data packets contains the source and destination IP address.
* Media access control

### Physical Layer:
* hardware layer
* works done by cables
* it will convert the electrical signal to the corresponding receiver data type.

### TCP/IP model:
* The **internet protocol shoot**
* it is similar to OSI model
* it has 5 layers
    1. Application layer --> users interacts with this ex: whatsapp, browser, etc .. where--> in our devices
    2. Trasnport layer
    3. network layer
    4. data link layer
    5. physical layer

### Protocols:

### 1. client - server Architecture:
*

### 2. P2P --?> PEER TO PEER:
* every single computer can turn as client and server

### HTTP Protocol:
* HTTP protocol is application layer's protocol
* it is a stateless protocol.
* HTTP request

### www:
* www --> world wide web --> A collection of web pages

### HTTP methods:
* GET
* POST
* PUT
* DELETE

### Status codes:
* 1xx --> Infromation status codes
* 2xx --> success codes
* 3xx --> redirecting codes
* 4xx --> client request error
* 5xx --> internel server error

### Cookies:
* cookie is an unique string
* stored in our browser.
* ex: when we are visiting a website for a 1st time, the cookie will be created, from the next time itself the cookie will serach in tha database, like who am I, like

### SMTP --> Simple Mail Transfer Protocol:
* how the email is working?
* SMTP is in the application layer protocol.
* when we are sending an email from **yahoo.com to gmail.com** sender --> sender's SMTP server --> reciever's SMTP server --> Reciever
* internaly it uses TCP
* if we are sending an email from **gmail.com to gmail.com**, the SMTP sever won't use

### TCP Error Handling

### POP - Post Office Protocol:
* default port no --> 110

### IMAP - Internet Message Access Protocol:
* allows to view the emails in multiple devices


## DNS - DOMAIN NAME SYSTEM
* DNS will map two IP Addresses.
* it will find the IP address in the server
* it will find the IP address in the internet and serve that application
* mail.google.com
* main --> sub domain
* google --> second level domain
* .com --> to level domain --> Root DNS server
* Root DNS servers:
    1. .io
    2. .org
    3. .com


* Transport layer protocol --> TCP & UDP
* Application layer protocol --> HTTP
* Network layer protocol --> IP

### Data Packet:
* every __data packet__ will have the **source port no** and also the **destination port no**, length of data gram, checksum, and also our data.
* total size of data packet = 2^16 - 8 (~65000)


### UDP - User Datagram Protocol
* here, our data may or may not be delivered
* data may change or lost on the way
* data may not be in order , how sender sends
* it is a connectionless protocol
* without making a connection between two computers, it will still transfers the data
* UDP uses checksums(the data is in the order how the sender sends the data).
* UDP is always faster , because it on't ensure like the comfirmation of data sends or not like.
* Use Cases: 1. Video conferencing apps
             2. Gaming


### TCP - Transmission Control Protocol
* It is a transport layer protocol
* Application layer sends lots of raw data, and TCP segments this data, and divide into chunks, checksums.
* It may also collect the data from network layer and divide into chunks
* It takes care of **when data does not arrive**, **maintains the order of data using __sequence number__(seq nums are generated random nums, so hackers cannot take advantage) & __acknowledgement number__.
* __Features__:
   1. TCP is onnection oriented
   2. 1st the connection have to established, then we can transfer the data
   3. Error control
   4. conjestion control
   5. it is bidirectional (full duplex --> can communicate each other simultaneously)

 
* in Transport layer, the data is in the form of  __segments__
* in network layer, the data is in the form of __packets__
* in data link layer , the data is in the form of __frames__


### Router:
* router hepls to direct the network traffics
* every single router connected between several computers, is having its own __network address__
* network address:
* __Routing Table__: it will dircte the data packest to reach the destination from the source.
* __Forwading Table__: it is a part of routing table, this also tells like instruction step by step to the data packets to reach the destination
* routing table and forwading table are living inside ROUTER.
* every router is a __node__
* the link between router and devices are __edges__
* Static Routing --> manually
* Dynamic Routing --> automatically it will evolve

### IP - Intenet Protocol
* it is a network layer's protocol

### IPV4 - IP Address Version 4
* it will define uniqly a device/server/client or etc...
* 32 -bit with 4 words
* ex: 192.168.2.30: each has 8 bits(octet),8*4=32 bits
    1. 192.168.2 --> subnet id provided by ISP
    2. 30 --> host Id (our device Id)
   

### IPV6 - IP Address Version 6
* 128-bits
* 

### Class of IP Addresses:
* Class A --> 0.0.0.0 --> 127.255.255.251
* Class B --> 128.0.0.0 --> 191.255.255.255
* Class C --> 192.0.0.0 --> 223.255.255.251
* Class D --> 224.0.0.0 --> 239.255.255.255
* Class E --> 240.0.0.0 --> 255.255.255.255

### Subnet mask:
* 
