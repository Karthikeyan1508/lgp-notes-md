# Data Link Layer

The **Data Link Layer (DLL)** is the second layer from the bottom in the **OSI (Open System Interconnection)** network architecture model. It is responsible for the **node-to-node delivery** of data within the same local network. Its major role is to ensure **error-free transmission** of information. DLL is also responsible for **encoding, decoding**, and **organizing** the outgoing and incoming data.


![image](https://github.com/user-attachments/assets/9d09adf5-4975-470d-bb45-82a7656804b7)



---

## Primary Functions of the Data Link Layer

### 1. Framing

Divides the raw bit-stream received from the Physical layer into structured data units called **frames**.

### 2. Physical Addressing

Adds a header to each frame containing the **sender’s and receiver’s hardware (MAC) addresses** so that frames can be delivered to the correct device on the same network.

### 3. Flow Control

Regulates the rate of data transmission, ensuring that a **fast sender does not overwhelm a slower receiver**.

### 4. Error Control

Detects and recovers from frame errors (**loss, damage, or duplication**) by using techniques such as **checksums and retransmission requests**. Often implemented via a **trailer** appended to each frame.

### 5. Medium Access Control (MAC)

Determines **which device has permission to transmit** on the shared physical medium at any given time, preventing collisions and coordinating access.

---

## Link-Layer Addressing

* A **link-layer address** is also known as a **link address**, **physical address**, or **MAC address**.
* Since a link is controlled at the data-link layer, the addresses need to belong to this layer.
* When a datagram passes from the network layer to the data-link layer, it is encapsulated in a frame and **two data-link addresses are added** to the frame header.
* These addresses change **every time the frame moves** from one link to another.

### Types of Link-Layer Addresses:

* **Unicast**
* **Multicast**
* **Broadcast**

---

## Address Resolution Protocol (ARP)

**ARP** is a **network-layer protocol** used to **dynamically map a 32-bit IP address** (logical address) to a **48-bit MAC address** (physical address) on a local network.

### Key Points:

* Essential for enabling communication between devices on the same **LAN**.
* Bridges the gap between **IP-based addressing** and **MAC-based hardware addressing**.
* Operates using a simple **request–reply mechanism**.
* Although it supports Data Link Layer operations, ARP is classified under the **Network Layer** in the OSI model.
* Before sending a data packet, a device uses ARP to **find the recipient's MAC address** using its IP address.

### ARP Message Types:

* **ARP Request** – Broadcasted to ask:
  *“Who has IP X.X.X.X?”*
* **ARP Reply** – Unicast response:
  *“IP X.X.X.X is at MAC AA\:BB\:CC\:DD\:EE\:FF”*

![image](https://github.com/user-attachments/assets/cb187d0d-c3ca-42ab-94c4-90104b7c7d95)


---

## ARP Operation

* ARP maintains a **cache table** in which MAC addresses are mapped to IP addresses.
* If a host wants to send an IP datagram, it first **checks for a mapping** in the cache.
* If no mapping is found, it **broadcasts an ARP query** onto the network.
* The query contains the **target IP address**.
* Each host receives the query and **checks if it matches** its IP address.
* If it matches, the host sends a **response message** with its MAC address.
* The originator **adds the IP–MAC pair** to its ARP table.

### Example:

1. To determine system B’s MAC address, system A broadcasts an **ARP request** containing B’s IP.
2. All nodes except B **discard the packet** but may update their ARP tables.
3. System B sends back an **ARP response** (unicast) with its MAC address.
4. System A stores the IP–MAC pair in its **ARP table**.
5. If the target is on a different network, the **ARP request goes to the default router**.

---

## ARP Packet

The ARP packet format is used for ARP requests and replies and consists of multiple fields including hardware type, protocol type, hardware and protocol size, operation, sender and target hardware, and IP addresses. These fields work together to help devices on a network find and communicate with each other.

![image](https://github.com/user-attachments/assets/6d233f0d-fa43-44d7-940b-7a1468d1d1d1)


**Hardware type:** This is 16 bits field defining the type of the network on which ARP is running. Ethernet is given type 1. 

**Protocol type:** This is 16 bits field defining the protocol. The value of this field for the IPv4 protocol is 0800H.

**Hardware length:** This is an 8 bits field defining the length of the physical address in bytes. Ethernet is the value 6.

**Protocol length:** This is an 8 bits field defining the length of the logical address in bytes. For the IPv4 protocol, the value is 4.

**Operation (request or reply):** This is a 16 bits field defining the type of packet. Packet types are ARP request (1), and ARP reply (2).

**Sender hardware address:** This is a variable length field defining the physical address of the sender. For example, for Ethernet, this field is 6 bytes long.

**Sender protocol address:** This is also a variable length field defining the logical address of the sender For the IP protocol, this field is 4 bytes long.

**Target hardware address:** This is a variable length field defining the physical address of the target. For Ethernet, this field is 6 bytes long. For the ARP request messages, this field is all Os because the sender does not know the physical address of the target.

**Target protocol address:** This is also a variable length field defining the logical address of the target. For the IPv4 protocol, this field is 4 bytes long.

---

## RARP – Reverse ARP

**Reverse Address Resolution Protocol (RARP)** allows a host to **convert its MAC address** to the corresponding **IP address**.
Reverse ARP is a network protocol a client machine uses in a local area network to request its Internet Protocol address (IPv4) from the gateway router’s ARP table. The network administrator creates a table in the gateway router, which maps the MAC address to the corresponding IP address. When a new machine is set up or any machine which doesn’t have amemory to store the IP address, needs an IP address for its use. So the machine sends a RARP broadcast packet which contains its own MAC address in both the sender and receiver hardware address fields.

## CSMA (Carrier Sense Multiple Access)
---
Carrier Sense Multiple Access (CSMA) is a method used in computer networks to manage how devices share a communication channel to transfer the data between two devices. In this protocol, each device first sense the channel before sending the data. If the channel is busy, the device waits until it is free. This helps reduce collisions, where two devices send data at the same time, ensuring smoother communication across the network. CSMA is commonly used in technologies like Ethernet and Wi-Fi.

This method was developed to decrease the chances of collisions when two or more stations start sending their signals over the data link layer. Carrier Sense multiple access requires that each station first check the state of the medium before sending.

### What is Vulnerable Time in CSMA?
Vulnerable time is the short period when there’s a chance that two devices on a network might send data at the same time and cause a collision.

```  
Vulnerable time = Propagation time (Tp)
```
![image](https://github.com/user-attachments/assets/b5a0bacf-2dc3-4832-af5e-8b0cab7f5cd9)

The persistence methods can be applied to help the station take action when the channel is busy/idle. 

## Types of CSMA Protocol
There are two main types of Carrier Sense Multiple Access (CSMA) protocols, each designed to handle how devices manage potential data collisions on a shared communication channel. These types differ based on how they respond to the detection of a busy network:

1. Carrier Sense Multiple Access with Collision Detection (CSMA/CD)
2. CSMA/CA

## Carrier Sense Multiple Access with Collision Detection (CSMA/CD)

Carrier Sense Multiple Access with Collision Detection (CSMA/CD) is a network protocol for carrier transmission that operates in the Medium Access Control (MAC) layer. It senses or listens whether the shared channel for transmission is busy or not, and defers transmissions until the channel is free. The collision detection technology detects collisions by sensing transmissions from other stations. On detection of a collision, the station stops transmitting, sends a jam signal, and then waits for a random time interval before retransmission.

### Algorithms

- When a frame is ready, the transmitting station checks whether the channel is idle or busy.

- If the channel is busy, the station waits until the channel becomes idle.

- If the channel is idle, the station starts transmitting and continually monitors the channel to detect collision.

- If a collision is detected, the station starts the collision resolution algorithm.

- The station resets the retransmission counters and completes frame transmission.

- The algorithm of Collision Resolution is:

- The station continues transmission of the current frame for a specified time along with a jam signal, to ensure that all the other stations detect collision.

- The station increments the retransmission counter.

- If the maximum number of retransmission attempts is reached, then the station aborts transmission.

- Otherwise, the station waits for a backoff period which is generally a function of the number of collisions and restart main algorithm.

- Though this algorithm detects collisions, it does not reduce the number of collisions.

- It is not appropriate for large networks performance degrades exponentially when more stations are added.

![images (1)](https://github.com/user-attachments/assets/af29732e-36a1-4304-ad2e-e9cc78cd9066)

## CSMA with Collision Avoidance (CSMA/CA)

Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA) is a network protocol for carrier transmission that operates in the Medium Access Control (MAC) layer. In contrast to CSMA/CD (Carrier Sense Multiple Access/Collision Detection) that deals with collisions after their occurrence, CSMA/CA prevents collisions prior to their occurrence.

### Algorithm

The algorithm of CSMA/CA is:

- When a frame is ready, the transmitting station checks whether the channel is idle or busy.

- If the channel is busy, the station waits until the channel becomes idle.

- If the channel is idle, the station waits for an Inter-frame gap (IFG) amount of time and then sends the frame.

- After sending the frame, it sets a timer.

- The station then waits for acknowledgement from the receiver. If it receives the acknowledgement before expiry of timer, it marks a successful transmission.

- Otherwise, it waits for a back-off time period and restarts the algorithm.

![image](https://github.com/user-attachments/assets/0412d34d-959d-431e-8330-0adabe7f50ea)

## ALOHA Protocol
---

Aloha is a type of Random access protocol it was developed at the University of Hawaii in early 1970, it is a LAN-based protocol this type there are more chances of occurrence of collisions during the transmission of data from any source to the destination, Aloha has two types one Pure Aloha and another Slotted Aloha.

It is asynchronous because there is no coordination between devices. When multiple devices attempt to transmit data at the same time, it can result in a collision, where the data becomes garbled. In this case, each device will simply wait a random amount of time before attempting to transmit again. The basic concept of the ALOHA protocol can be applied to any system where uncoordinated users are competing for the use of a shared channel.

## Pure Aloha
- Pure ALOHA refers to the original ALOHA protocol. The idea is that each station sends a frame whenever one is available. Because there is only one channel to share, there is a chance that frames from different stations will collide.
- The pure ALOHA protocol utilizes acknowledgments from the receiver to ensure successful transmission. When a user sends a frame, it expects confirmation from the receiver. If no acknowledgment is received within a designated time period, the sender assumes that the frame was not received and retransmits the frame. 
- When two frames attempt to occupy the channel simultaneously, a collision occurs and both frames become garbled. If the first bit of a new frame overlaps with the last bit of a frame that is almost finished, both frames will be completely destroyed and will need to be retransmitted. If all users retransmit their frames at the same time after a time-out, the frames will collide again. 
- To prevent this, the pure ALOHA protocol dictates that each user waits a random amount of time, known as the back-off time, before retransmitting the frame. This randomness helps to avoid further collisions.

![image](https://github.com/user-attachments/assets/15a3ebd5-6041-4321-bf51-c243873327dc)

- The time-out period is equal to the maximum possible round-trip propagation delay, which is twice the amount of time required to send a frame between the two most widely separated stations   (2 x Tp).
- Let all the packets have the same length. And each requires a one-time unit for transmission (tp). Consider any user to send packet A at a time. If any other user B has generated a packet between time (to), and (to + tp), the end of packet B will collide with the beginning of packet A. Since in a pure ALOHA packet, a station does not listen to the channel before transmitting, it has no way of knowing that the above frame was already underway.

![image](https://github.com/user-attachments/assets/5c2d5441-9628-443a-92c1-d3f6ac652545)

Throughput of Pure ALOHA
The probability of successful transmission (S) can be derived from the probability that no other packets are sent during the vulnerable time period. This is given by:

```
S = G × e-2G
```
where:

S is the throughput (the average number of successful packet transmissions per packet time).
G is the average number of packets generated by the system in one packet time .
Maximum Throughput of Pure ALOHA
The maximum throughput occurs when G=0.5
```
Smax = 0.5 × e-1 ≈ 0.184
```
This means the maximum throughput of Pure ALOHA is approximately 18.4%. In other words, only about 18.4% of the time is used for successful transmissions, and the rest is lost due to collisions.

### Key Features of Pure ALOHA
- **Random Access:** Devices can send data whenever they have something to transmit, without needing to wait for a predetermined time slot.
- **Uncoordinated Transmission:** Devices do not coordinate with each other before transmitting. They simply attempt to send data whenever they have data to send.
- **Simple Implementation:** Pure ALOHA is straightforward to implement, making it suitable for early network experiments and scenarios with low traffic.
- **Persistent Approach:** Devices continue to attempt transmission even after a collision, using a form of exponential backoff. This means they introduce random delays before retrying, which helps reduce the chances of repeated collisions.
- **Contention-Based:** Since devices transmit without coordination, collisions may occur if two or more devices transmit simultaneously. Collisions are detected through feedback from the receiver or by the transmitting device itself.

 ---
## Slotted ALOHA

Slotted ALOHA is an improved version of the pure ALOHA protocol that aims to make communication networks more efficient. In this version, the channel is divided into small, fixed-length time slots and users are only allowed to transmit data at the beginning of each time slot. This synchronization of transmissions reduces the chances of collisions between devices, increasing the overall efficiency of the network.
### How Does Slotted ALOHA work?
The channel time is separated into time slots in slotted ALOHA, and stations are only authorized to transmit at particular times. These time slots correspond to the packet transmission time exactly. All users are then synchronized to these time slots so that whenever a user sends a packet, it must precisely match the next available channel slot. As a result, wasted time due to collisions can be reduced to one packet time or the susceptible period can be half.

When a user wants to transmit a frame, it waits until the next time slot and then sends the frame. If the frame is received successfully, the receiver sends an acknowledgment. If the acknowledgment is not received within a time-out period, the sender assumes that the frame was not received and retransmits the frame in the next time slot.

![image](https://github.com/user-attachments/assets/c47c29cd-e164-4346-9cf2-e45331617ff2)

### Throughput of Slotted ALOHA
The throughput of the Slotted ALOHA protocol is determined by the number of successful transmissions in each time slot. The maximum theoretical throughput of Slotted ALOHA is approximately 36.8%. This is due to the significant risk of collisions when multiple nodes attempt to transmit at the same time, causing lost packets and decreased overall throughput. The maximum throughput is achieved when around 37% of the network's nodes are actively transmitting data.

The maximum throughput of a slotted ALOHA channel is given by the formula:
```
Throughput (S) = G x e-G
The maximum Throughput occurs at G = 1,
i.e. S = 1/e = 0.368
```

Where:
G = the offered load (or the number of packets being transmitted per time slot). The offered load is a measure of the number of nodes attempting to transmit in a given time slot.

![image](https://github.com/user-attachments/assets/4e7c695e-bb27-4f37-b6f5-f288dc188d3a)

The throughput is a function of the offered load and it ranges from 0 to 1. As the offered load increases, the throughput decreases as more collisions occur, resulting in less successful transmissions. The maximum throughput is achieved when the offered load is equal to 0.37 and it is approximately 0.184.

It is important to note that the above equation assumes that all the packets are of the same length and that the channel is error-free. In practice, the throughput is usually much lower than this due to a number of factors such as packet errors, channel noise, and the overhead of retransmissions.

### Assumption of Slotted ALOHA
- All frames are of the same size.
- Time is divided into equal-sized slots, a slot equals the time to transmit one frame
- Nodes start to transmit frames only at beginning of slots.
- Nodes are synchronized.
- If two or more nodes transmit in a slot, all nodes detect collision before the slot ends.

### Advantages of Slotted ALOHA
**Simplicity:** The Slotted Aloha protocol is relatively simple to implement and understand, making it an easy option for low-complexity networks.
**Flexibility:** Slotted Aloha can be used in a wide range of network environments, including those with varying numbers of nodes and varying traffic loads
**Low Overhead:** Slotted Aloha does not require complex management or control mechanisms, which can help to reduce the overhead and complexity of the network.

### Disadvantages of Slotted ALOHA
**Low Throughput:** The maximum throughput of the Slotted Aloha protocol is relatively low at around 18.4%, which can be limiting for high-bandwidth applications.
**High Collision Rate:** The high collision rate in slotted ALOHA can result in a high packet loss rate, which can negatively impact the overall performance of the network.
**Inefficiency:** The protocol is inefficient at high loads, as the efficiency decreases as the number of nodes attempting to transmit increases.

## What Is Ethernet?
--- 
Ethernet technology provides rules that allow network-connected devices to talk to one another without talking over each other. In a verbal conversation, when two people speak at the same time, each may have difficulty understanding what the other is saying. This is amplified when, say, 10 people are talking at once. Imagine 100 or 1000 at once.

The same is true for a data network. If two or more connected devices on a shared network attempt to transmit data packets at the same time, a packet collision occurs. The pulses of electricity or photons that make up a packet overlap when sent at the same time over a shared copper or optical cable. This jumbles the sequence of "on" pulses and "off" voids that are sent to indicate the bits and bytes of 1s and 0s that make up a packet.

Ethernet was designed to solve the problem of packet collision. It provides network devices with a set of rules that essentially says: "Make sure no one else is talking before you talk. If you hear someone talking while you're talking, stop, listen, and wait for the talking to end before you talk again."

Ethernet is commonly associated with connected devices in a wired LAN or WAN. Using a wired Ethernet cable, devices are connected to an Ethernet switch. Ethernet has the ability to use both wired and fiber cables, delivering not only data but also power, now up to 90W with UPOE+.

More formally, Ethernet is a common name for the IEEE 802.3 standard based on the Carrier Sense Multiple Access/Collision Detection (CSMA/CD) protocol.

![image](https://github.com/user-attachments/assets/cffa26a5-355a-4ec0-993b-3fb7b5f6df5d)


### What are Ethernet frames?
In an Ethernet network, data is broken into packets, with each packet transmitted using the CSMA/CD algorithm until it arrives at its destination without colliding with any other packet. The first open slot after a transmission is reserved for an acknowledge packet. A device or node is either transmitting or receiving at any instant.

When sending data to another device on an Ethernet network, the MAC sublayer (data link sublayer):

- Encapsulates higher-level frames into frames appropriate for the transmission medium
- Adds a frame check sequence to identify transmission errors
- Forwards the data to the physical layer as soon as the CSMA/CD protocol permits, waiting as necessary to avoid collisions.
- Is responsible for compensating for collisions by starting retransmission when a collision (jam signal) is detected.
- When receiving data from the physical layer, the frame check sequence in the MAC block is used to ensure data integrity. It strips off the sender's Ethernet-packet preamble and padding before passing the data to the higher layers.

The Ethernet switch creates the frame by encapsulating the Ethernet packet with a preamble, which is used to synchronize the sender and receiver, followed by a 1-octet start-frame delimiter byte.

The Ethernet packet includes the data encapsulated by a header and a frame check value. The MAC header provides the source and destination MAC addresses as well as a 2-octet EtherType code indicating IPv4 or IPv6, MACsec encryption, etc. The frame ends with a frame check sequence (FCS), which is a 32-bit cyclic redundancy check used to detect any in-transit corruption of data.

There are different types of Ethernet networks that are used to connect devices and transfer data.

Let’s discuss them in simple terms:

**Fast Ethernet:** This type of Ethernet network uses cables called twisted pair or CAT5. It can transfer data at a speed of around 100 Mbps (megabits per second). Fast Ethernet uses both fiber optic and twisted pair cables to enable communication. There are three categories of Fast Ethernet: 100BASE-TX, 100BASE-FX, and 100BASE-T4.
**Gigabit Ethernet:** This is an upgrade from Fast Ethernet and is more common nowadays. It can transfer data at a speed of 1000 Mbps or 1 Gbps (gigabit per second). Gigabit Ethernet also uses fiber optic and twisted pair cables for communication. It often uses advanced cables like CAT5e, which can transfer data at a speed of 10 Gbps.
**10-Gigabit Ethernet:** This is an advanced and high-speed network that can transmit data at a speed of 10 gigabits per second. It uses special cables like CAT6a or CAT7 twisted-pair cables and fiber optic cables. With the help of fiber optic cables, this network can cover longer distances, up to around 10,000 meters.
**Switch Ethernet:** This type of network involves using switches or hubs to improve network performance. Each workstation in this network has its own dedicated connection, which improves the speed and efficiency of data transfer. Switch Ethernet supports a wide range of speeds, from 10 Mbps to 10 Gbps, depending on the version of Ethernet being used.

In summary, Fast Ethernet is the basic version with a speed of 100 Mbps, Gigabit Ethernet is faster with a speed of 1 Gbps, 10-Gigabit Ethernet is even faster with a speed of 10 Gbps, and Switch Ethernet uses switches or hubs to enhance network performance.The Manchester Encoding Technique is used in Ethernet. Using Manchester encoding, data can be transmitted over a physical medium in communication systems. It is a type of line coding where the signal transitions, as opposed to the absolute voltage levels, serve as the data representation.

### Key Features of Ethernet
**1. Speed:** Ethernet is capable of transmitting data at high speeds, with current Ethernet standards supporting speeds of up to 100 Gbps.
**2. Flexibility:** Ethernet is a flexible technology that can be used with a wide range of devices and operating systems. It can also be easily scaled to accommodate a growing number of users and devices.
**3. Reliability:** Ethernet is a reliable technology that uses error-correction techniques to ensure that data is transmitted accurately and efficiently.
**4. Cost-effectiveness:** Ethernet is a cost-effective technology that is widely available and easy to implement. It is also relatively low-maintenance, requiring minimal ongoing support.
**5. Interoperability:** Ethernet is an interoperable technology that allows devices from different manufacturers to communicate with each other seamlessly.
**6. Security:** Ethernet includes built-in security features, including encryption and authentication, to protect data from unauthorized access.
**7. Manageability:** Ethernet networks are easily managed, with various tools available to help

 network administrators monitor and control network traffic.
**8. Compatibility:** Ethernet is compatible with a wide range of other networking technologies, making it easy to integrate with other systems and devices.
**9. Availability:** Ethernet is a widely available technology that can be used in almost any setting, from homes and small offices to large data centers and enterprise-level networks.
**10. Simplicity:** Ethernet is a simple technology that is easy to understand and use. It does not require specialized knowledge or expertise to set up and configure, making it accessible to a wide range of users.
**11. Standardization:** Ethernet is a standardized technology, which means that all Ethernet devices and systems are designed to work together seamlessly. This makes it easier for network administrators to manage and troubleshoot Ethernet networks.
**12. Scalability:** Ethernet is highly scalable, which means it can easily accommodate the addition of new devices, users, and applications without sacrificing performance or reliability.
**13. Broad compatibility:** Ethernet is compatible with a wide range of protocols and technologies, including TCP/IP, HTTP, FTP, and others. This makes it a versatile technology that can be used in a variety of settings and applications.
**14. Ease of integration:** Ethernet can be easily integrated with other networking technologies, such as Wi-Fi and Bluetooth, to create a seamless and integrated network environment.

### How Ethernet Works?
In the Open Systems Interconnection (OSI) model, the Ethernet is located in the lower layers and facilitates the operation of the physical and data link layers. The OSI model consists of seven layers, which are as follows.

The topmost layer, known as the application layer, is what enables users to download and access data from email clients or web browsers. With the aid of the application, users enter their queries, and the request is then sent to the following layer, which is known as a “packet.” The packet contains data about the sender and the destination web address. The packet is transmitted from the application layer until it reaches the bottom layer, also known as the Ethernet frame.

## Error Detection in Computer Networks
Error is a condition when the receiver's information does not match the sender's. Digital signals suffer from noise during transmission that can introduce errors in the binary bits traveling from sender to receiver. That means a 0 bit may change to 1 or a 1 bit may change to 0. 

Data (Implemented either at the Data link layer or Transport Layer of the OSI Model) may get scrambled by noise or get corrupted whenever a message is transmitted. To prevent such errors, error-detection codes are added as extra data to digital messages. This helps in detecting any errors that may have occurred during message transmission.

## Types of Errors
### Single-Bit Error
A single-bit error refers to a type of data transmission error that occurs when one bit (i.e., a single binary digit) of a transmitted data unit is altered during transmission, resulting in an incorrect or corrupted data unit.

![image](https://github.com/user-attachments/assets/3d44ce0d-5768-41da-889d-8a7781945bed)


### Multiple-Bit Error
A multiple-bit error is an error type that arises when more than one bit in a data transmission is affected. Although multiple-bit errors are relatively rare when compared to single-bit errors, they can still occur, particularly in high-noise or high-interference digital environments.

![image](https://github.com/user-attachments/assets/ee3cc2ed-bd52-4176-8c1a-642bfffa20e9)


### Burst Error
When several consecutive bits are flipped mistakenly in digital transmission, it creates a burst error. This error causes a sequence of consecutive incorrect values.

![image](https://github.com/user-attachments/assets/c13fec51-24aa-49c8-8ce1-4786a6bfbd8a)

## Error Detection Methods
To detect errors, a common technique is to introduce redundancy bits that provide additional information. Various techniques for error detection include:

1. Simple Parity Check
2. Two-Dimensional Parity Check
3. Checksum
4. Cyclic Redundancy Check (CRC)

### Simple Parity Check
Simple-bit parity is a simple error detection method that involves adding an extra bit to a data transmission. It works as:

1 is added to the block if it contains an odd number of 1’s, and
0 is added if it contains an even number of 1’s
This scheme makes the total number of 1’s even, that is why it is called even parity checking.

![image](https://github.com/user-attachments/assets/a7d231d1-40e7-435a-b9a0-02d763486d3d)

### Advantages of Simple Parity Check
- Simple parity check can detect all single bit error.
- Simple parity check can detect an odd number of errors.
- **Implementation:** Simple Parity Check is easy to implement in both hardware and software.
- **Minimal Extra Data:** Only one additional bit (the parity bit) is added per data unit (e.g., per byte).
- **Fast Error Detection:** The process of calculating and checking the parity bit is quick, which allows for rapid error detection without significant delay in data processing or communication.
- Single-Bit Error Detection: It can effectively detect single-bit errors within a data unit, providing a basic level of error detection for relatively low-error environments.
  
### Disadvantages of Simple Parity Check
- Single Parity check is not able to detect even no. of bit error. 
For example, the Data to be transmitted is 101010. Codeword transmitted to the receiver is 1010101 (we have used even parity). 
Let's assume that during transmission, two of the bits of code word flipped to 1111101.
On receiving the code word, the receiver finds the no. of ones to be even and hence no error, which is a wrong assumption.

## **Two-Dimensional Parity Check**
**Two-dimensional Parity** check bits are calculated for each row, which is equivalent to a simple parity check bit. Parity check bits are also calculated for all columns, then both are sent along with the data. At the receiving end, these are compared with the parity bits calculated on the received data.

![image](https://github.com/user-attachments/assets/4a067342-b935-4515-bbbe-e2ff30d039cf)


### Advantages of Two-Dimensional Parity Check
- Two-Dimensional Parity Check can detect and correct all single bit error.
- Two-Dimensional Parity Check can detect two or three bit error that occur any where in the matrix.

### Disadvantages of Two-Dimensional Parity Check
- Two-Dimensional Parity Check can not correct two or three bit error. It can only detect two or three bit error.
- If we have a error in the parity bit then this scheme will not work.

## Checksum
**Checksum error detection** is a method used to identify errors in transmitted data. The process involves dividing the data into equally sized segments and using a 1's complement to calculate the sum of these segments. The calculated sum is then sent along with the data to the receiver. At the receiver's end, the same process is repeated and if all zeroes are obtained in the sum, it means that the data is correct.

### Checksum - Operation at Sender's Side
- Firstly, the data is divided into k segments each of m bits.
- On the sender’s end, the segments are added using 1’s complement arithmetic to get the sum. The sum is complemented to get the checksum.
The checksum segment is sent along with the data segments.
### Checksum - Operation at Receiver's Side
- At the receiver’s end, all received segments are added using 1’s complement arithmetic to get the sum. The sum is complemented.
- If the result is zero, the received data is accepted; otherwise discarded.

![image](https://github.com/user-attachments/assets/7fc58023-e953-4b3e-bc53-ac6684357bbc)


## Cyclic Redundancy Check (CRC)
- Unlike the checksum scheme, which is based on addition, CRC is based on binary division.
- In CRC, a sequence of redundant bits, called cyclic redundancy check bits, are appended to the end of the data unit so that the resulting data unit becomes exactly divisible by a second, predetermined binary number.
- At the destination, the incoming data unit is divided by the same number. If at this step there is no remainder, the data unit is assumed to be correct and is therefore accepted.
- A remainder indicates that the data unit has been damaged in transit and therefore must be rejected.

![image](https://github.com/user-attachments/assets/548b1325-7353-46e2-96fa-b6a1d89aae0f)

### CRC Working
We have given dataword of length n and divisor of length k.

Step 1: Append (k-1) zero's to the original message

Step 2: Perform modulo 2 division

Step 3: Remainder of division = CRC

Step 4: Code word = Data with append k-1 zero's + CRC

Note:
- CRC must be k-1 bits
- Length of Code word = n+k-1 bits

**Example:** Let's data to be send is 1010000 and divisor in the form of polynomial is x3+1. CRC method discussed below.

![image](https://github.com/user-attachments/assets/c8ad4fb9-73d6-4b8b-acc4-af9f833aace0)



## Advantages of Error Detection
- **Increased Data Reliability:** Error detection ensures that the data transmitted over the network is reliable, accurate, and free from errors. This ensures that the recipient receives the same data that was transmitted by the sender.
- **Improved Network Performance:** Error detection mechanisms can help to identify and isolate network issues that are causing errors. This can help to improve the overall performance of the network and reduce downtime.
- **Enhanced Data Security:** Error detection can also help to ensure that the data transmitted over the network is secure and has not been tampered with.

## Disadvantages of Error Detection
- **Overhead:** Error detection requires additional resources and processing power, which can lead to increased overhead on the network. This can result in slower network performance and increased latency.
- **False Positives:** Error detection mechanisms can sometimes generate false positives, which can result in unnecessary retransmission of data. This can further increase the overhead on the network.
- **Limited Error Correction:** Error detection can only identify errors but cannot correct them. This means that the recipient must rely on the sender to retransmit the data, which can lead to further delays and increased network overhead.

## Error Correction in Computer Networks

Computer Networks play a crucial role in the secured and encrypted transmission of data over the internet. However, the data transfer over a network includes many complex processes that cause some flaws in the data transmission. These flaws are called Errors which can be of different types. Therefore, it is important to correct them for efficient data transmission.

Once the errors are detected in the network, the deviated bits sequence needs to be replaced with the right bit sequence so that the receiver can accept the data and process it. This method is called Error Correction. We can correct the errors in the Network in two different ways which are listed below:

- **Forward Error Correction:** In this Error Correction Scenario, the receiving end is responsible for correcting the network error. There is no need for retransmission of the data from the sender’s side.
- **Backward Error Correction:** the sender is responsible for retransmitting the data if errors are detected by the receiver. The receiver signals the sender to resend the corrupted data or the entire message to ensure accurate delivery.

However, there is one of the most widely used Error Correction methods which is called ‘Hamming Code’ which was designed by R.W. Hamming. Let us have a quick look at it.

## Hamming Code

Hamming code is a block code that is capable of detecting up to two simultaneous bit errors and correcting single-bit errors. It was developed by R.W. Hamming for error correction.

In this coding method, the source encodes the message by inserting redundant bits within the message. These redundant bits are extra bits that are generated and inserted at specific positions in the message itself to enable error detection and correction. When the destination receives this message, it performs recalculations to detect errors and find the bit position that has error.
### Encoding a message by Hamming Code

The procedure used by the sender to encode the message encompasses the following steps ?

**Step 1: Calculation of the number of redundant bits.**
If the message contains m?number of data bits, r?number of redundant bits are added to it so that m? is able to indicate at least (m + r+ 1) different states. Here, (m + r) indicates location of an error in each of (? + ?) bit positions and one additional state indicates no error. Since, r? bits can indicate 2r? states, 2r? must be at least equal to (m + r + 1). Thus the following equation should hold  2r ? m+r+1

**Step 2: Positioning the redundant bits.**
The r redundant bits placed at bit positions of powers of 2, i.e. 1, 2, 4, 8, 16 etc. They are referred in the rest of this text as r1 (at position 1), r2 (at position 2), r3 (at position 4), r4 (at position 8) and so on.

**Step 3: Calculating the values of each redundant bit.**
The redundant bits are parity bits. A parity bit is an extra bit that makes the number of 1s either even or odd. The two types of parity are ?

- **Even Parity:** Here the total number of bits in the message is made even.

- **Odd Parity:** Here the total number of bits in the message is made odd.

Each redundant bit, ri, is calculated as the parity, generally even parity, based upon its bit position. It covers all bit positions whose binary representation includes a 1 in the ith position except the position of ri. Thus ?

- r1 is the parity bit for all data bits in positions whose binary representation includes a 1 in the least significant position excluding 1 (3, 5, 7, 9, 11 and so on)

- r2 is the parity bit for all data bits in positions whose binary representation includes a 1 in the position 2 from right except 2 (3, 6, 7, 10, 11 and so on)

- r3 is the parity bit for all data bits in positions whose binary representation includes a 1 in the position 3 from right except 4 (5-7, 12-15, 20-23 and so on)

## Decoding a message in Hamming Code
Once the receiver gets an incoming message, it performs recalculations to detect errors and correct them. The steps for recalculation are ?

**Step 1: Calculation of the number of redundant bits**
Using the same formula as in encoding, the number of redundant bits are ascertained.

2r ? m + r + 1 where m is the number of data bits and r is the number of redundant bits.

**Step 2: Positioning the redundant bits**
The r redundant bits placed at bit positions of powers of 2, i.e. 1, 2, 4, 8, 16 etc.

**Step 3: Parity checking**
Parity bits are calculated based upon the data bits and the redundant bits using the same rule as during generation of c1,c2 ,c3 ,c4 etc. Thus

c1 = parity(1, 3, 5, 7, 9, 11 and so on)

c2 = parity(2, 3, 6, 7, 10, 11 and so on)

c3 = parity(4-7, 12-15, 20-23 and so on)

**Step 4: Error detection and correction**
The decimal equivalent of the parity bits binary values is calculated. If it is 0, there is no error. Otherwise, the decimal value gives the bit position which has error. For example, if c1c2c3c4 = 1001, it implies that the data bit at position 9, decimal equivalent of 1001, has error. The bit is flipped to get the correct message.
