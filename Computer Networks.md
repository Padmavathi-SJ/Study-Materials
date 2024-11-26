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