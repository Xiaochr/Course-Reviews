# 计算机网络

## 1. Introduction

- Networks: exchange something from one site to the others

- Why computer networks? 【s1 p20】
    - Communication, resource sharing, collaboration. 

### Connectivity

- What do we need to connect two computers? 【s1 p27】
    - computers
    - links

- Building blocks 【s1 p28】
    - Nodes
        - Hosts: work for the users
        - Switches: work for the network
    - Direct links
        - point to point
        - **multiple access** (常用)

- Device at the center
    - Hub（集线器）, a box
    - Switch（交换机）, a computer
    - Router（路由器）

- Switched networks 【s1 p30】
    - suitable for scaling up
    - circuit switched (tel.), packet switched (computer)
    - can be defined recursively

- Network scales 【s1 p32】
    - SAN, LAN, WAN, MAN, Internet

### Networking resource sharing

- Fundamental resource sharing concept: **multiplexing** （复用）

- Solutions 【s1 p35】
    - Synchronous Time-Division Multiplexing (STDM)
        - 分时间段使用，这段时间归谁，那段时间归谁，不能乱用。
    - Frequency-Division Multiplexing (FDM)
        - 分出多个lane，每个lane分配一台电脑，同样是专属。这样效率还是不高，可能一条道没用，另一条道却堵。
    - Packet switching (Statistical Multiplexing, On-demand Time-division)
        - 将各个电脑的数据包分成小块，小块混杂着传输。
        - 各个小块过程中可能线路不同，但最终到达的目的地相同。

- Circuit vs Packet switching 【s1 p37】

### Architecture

- Support for common services 【s1 p42】
    - request/reply channel
    - message stream channel: videos, sending message continuously

- Layering 【s1 p43】
    - Application programs, Process-to-process channels, Host-to-host connectivity, Hardware

- **Layers of network applications** 【s1 p44】
    - Users
    - Applications
    - Network services
    - Network hardware

- Simplified file transfer architecture


## 2. Network architecture

### Layering and protocols

- **Protocols** 【s2 p7】
    - Standards at a layer
    - a library function, or a running process
    - protocol stack: set of consecutive layers

- **Interfaces** 【s2 p8】
    - service interface
    - peer-to-peer interface

- Protocol graph
    - most peer-to-peer communication is indirect, direct only at hardware level. 
    - RRP: request/reply protocols
    - MSP: message stream
    - HHP: host-to-host

- Encapsulation （封装）
    - Data $\rightarrow$ (RRP, Data) $\rightarrow$ (HHP, RRP, Data) $\rightarrow$ (RRP, Data) $\rightarrow$ Data

### Architecture

#### ISO/OSI Model

- 7 layers
    - 7: Application
    - Presentation
    - Session
    - Transport
    - Network
    - Data link
    - 1: Physical

- 太麻烦了，仅供参考，实际并未使用。

- Nodes 至少要有3个layer: physical, data link, network

- Brief introduction of the 7 layers 【s2 p14~p16】

#### TCP/IP architecture

- 漏斗形 hourglass shape 【s2 p17】

- Does not imply strict layering

- 4 layers 【s2 p19】
    - 4: Application
    - Transport
    - Network
    - 1: Physical


### Application programming interface (API)

- How can we build network applications? 【s2 p24】
    - applications: inter-process communication
    - common services
    - A **network architecture** is a layered arrangement of common services, which support inter-process communication. 

- The most widely used network API: **socket interface**
    - A socket is defined as an endpoint for communication
    - Host num: Port num, 161.25.19.8: 1625

- The client/server paradigm 【s2 p28】
    - steps

- Further notes about socket API 【s2 p37】


## 3. Direct connection

### Network performance

- Performance metrics 【s3 p4】
    - Bandwidth
        - data transmitted per time unit
        - Mbps = $10^6$ bits per second
    - Latency
        - time to send message from point A to point B
        - RTT: round-trip time. RTT == Propagation delay $\times$ 2
        - **Latency = Propagation + Transmit + Queue**
    - Throughput = $\frac{\text{TransferSize}}{\text{TransferTime}}$

- Latency 和 Bandwidth 可以看作 fix cost 和 unit cost。
    - For high speed networks, latency dominates. 

- Delay $\times$ Bandwidth product
    - amount of data "in the pipe"
    - **the amount of data the sender can send before the receiver receives**. 

- 当算大小时，用2的次方换算，如 $1KB = 1024 Bytes$；当算速度时，用10的次方换算，如 $1Kbps = 1000 bits/s$

### Direct link

- One can send message to the other without the third computer. 

- Direct link networks 【s3 p14】
    - connecting
    - encoding
    - framing
    - error detection
    - reliable delivery
    - media access control

#### Connecting hardware

- Node architecture, network adapter, links 【s3 p18~p20】

- Typical cables 【s3 p22】
    - twisted pairs
    - coaxial cables
    - fiber optic cables

- Wireless links 【s3 p26】
    - Mobile phone system
    - Wireless LAN/WAN
    - Short range device connection (infrared, bluetooth)

#### Encoding, framing, and error detection (NOT required)

#### Reliable transmission

- Transmitted frames may be delayed or lost. 

- Solution: Automatic Repeat reQuest (ARQ)
    - Correctness: each packet is released to the network layer once and only once, without error
    - Efficiency

- Stop and wait 【s3 p51】
    - Acknowledgement and timeouts
    - It does not keep the pipe full

- Improvements 【s3 p54】
    - Concurrent logical channels

- **Sliding window** 【s3 p55】
    - allow multiple outstanding un-ACKed frames
    - upper bound: window. 【s3 p57】
        - Sender window size (SWS): Delay $\times$ Bandwidth product. 
        - Receiver window size (RWS): = 1 or = SWS


## Direct link networks

- Ethernet, Token rings, Wireless 【s4 p4】

- IEEE 802.x specifications 【s4 p6】

### Ethernet

- Physical connection 【s4 p9】

- Physical topologies 【s4 p10】
    - Linear bus topology
        - not so reliable, many single failure points
        - difficult to identify the problem if the entire network shuts down
    - Star topology
        - require more cable length, but more reliable

- Ethernet transmission 【s4 p14】
    - Broadcast
        - all stations receive all transmissions
    - CSMA/CD medium access control (MAC) scheme 【s4 p15】
        - all hosts compete for the same link. possibility of collisions
    - Transmission algorithms
        - 1-persistent protocol
        - p-persistent protocol

- Ethernet addresses 【s4 p18】
    - addresses are assigned to network adapters
    - 48-bits
    - address recognition 【s4 p19】
    - Possible destinations 【s4 p20】
        - unicast, broadcast, multicast
    - MAC address is used to distinguish between the destinations
    - Promiscuous mode

### Token rings

- Ring topology 【s4 p26】
    - prevent collisions before occurring

- Token ring transmission 【s4 p27】

- Token passing paradigm
    - travel in a unidirectional fashion

- When the node fails, the relay closes bypassing the node. 
    - 在物理角度与 Ethernet 并没有本质区别，同样可以用 Hub

- Token ring maintenance 【s4 p30】
    - Ring can elect a new monitor. Highest MAC address wins.

- FDDI (Fiber Distributed Data Interface) dual ring operation
    - no single failure point
    - 但 token ring 太复杂了，现在更多用 Ethernet 的结构。

### Wireless

- Wireless links 【s4 p33】
    - similar to Ethernet structure, sometimes called "wireless ethernet". 

- Access point (AP)

- Ad hoc (mesh structure) 【s4 p35】

- Most radios in wireless networking can’t transmit and receive at the same time, so we can’t detect collisions. Instead, we’ll do CSMA/CA (collision avoidance). 

- Problems
    - The hidden node problem 【s4 p37】
    - The exposed node problem
    - Solution: Multiple Access with Collision Avoidance (MACA) 【s4 p39】









## Questions

### s1

- What is packet switching? What are the advantages of packet switching?

- Why is layering useful?

### s3

- If you want to connect your home to the Internet, what are the common access technologies available for you to choose from?

- Why is the sliding window transmission “reliable”?

- Why should the sender window size (SWS) be set to bandwidth*delay product estimate?

### s4

- Why is Ethernet more popular than Token Ring in LANs?

- Why might a mesh (ad-hoc) topology be superior to a base station topology for communication in a natural disaster?

- How can an ethernet communicate with an FDDI network?

