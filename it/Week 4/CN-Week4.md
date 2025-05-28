# Session Layer in OSI model

The Session Layer is the 5th layer in the Open System Interconnection (OSI) model which plays an important role in controlling the dialogues (connections) between computers. This layer is responsible for setting up, coordinating, and terminating conversations, exchanges, and dialogues between the applications at each end. It establishes, manages, and terminates the connections between the local and remote applications.

- Dialogue Control is also implemented in the Session Layer of the OSI model but in TCP/IP the dialogue control is implemented in the Application Layer.
- Session-layer services are commonly used in application environments that use remote procedure calls (RPCs).
- Zone Information Protocol in AppleTalk is an example of Session Layer Implementation.
- Session Layer has synchronization and resynchronization techniques that ensure reliable and orderly communication over networks, which is particularly important in applications requiring high levels of data integrity and continuity.
- Synchronization points are markers or tokens inserted into the data stream that allow communication sessions to have checkpoints and on the other hand Resynchronization involves restoring a session to a known state after a disruption, such as a network failure or session timeout.

![image](https://github.com/user-attachments/assets/7c5fe50c-bf7e-4155-ba04-ac5889648bef)

In Session Layer, data streams are received and further marked, which is then resynchronized properly, so that the ends of the messages are not cut initially and further data loss is avoided. This layer establishes a connection between the session entities. This layer handles and manipulates data that it receives from the Session Layer as well as from the Presentation Layer.

## Functions of Session Layer
The session layer performs several different as well as important functions that are needed for establishing as well as maintaining a safe and secure connection:

**1. Session Establishment:** It establishes and manages sessions between communicating parties that cab be connection-oriented or connectionless. It also maps sessions to transport connections.

![image](https://github.com/user-attachments/assets/370f275e-8b3c-477a-a801-cd4a251cc317)

**2. Communication Synchronization:** It ensures reliable connectivity and recovery by using synchronization bits and checkpoints in data stream.

![image](https://github.com/user-attachments/assets/e8fbaabd-043c-4429-b982-68824ed85499)

**3. Activity Management:** It allow the user to divide data into logical units called activities. An activity can be processed on its own and each activity is independent of activities that come before and after it.

![image](https://github.com/user-attachments/assets/ace6d9fe-a56d-4726-b8ff-2b7b77d8e0e2)

**4. Dialog Management :** It refers to deciding whose turn it is to talk. Some applications uses a token mechanism for half-duplex mode, where only one party holds the token to transmit data while other supports full-duplex mode for simultaneous data transmission.

![image](https://github.com/user-attachments/assets/4eed912b-2e97-4e72-9565-c05d9b2299d4)

**5. Data Transfer:** It manages data exchange between systems.

![image](https://github.com/user-attachments/assets/675bab03-f680-4f45-a05d-50350cb14341)

**6. Resynchronization:** In this,  all the tokens are restored to the positions that were set during synchronization. The various options for resynchronization includes set, abandon and restart.

![image](https://github.com/user-attachments/assets/33dcb798-dc68-4c96-8a6b-721dde41f692)

## Working of Session Layer

The Session Layer manages communication sessions between applications over a network.

- It establishes connections, negotiating session parameters like authentication and communication direction (full-duplex or half-duplex).
- It oversees data exchange by using tokens to manage transmission rights and prevent collisions.
- Synchronization techniques are implemented, inserting checkpoints for recovery in case of disruptions.
- It ensures orderly communication, reducing message loss, duplication, or errors caused by overlapping communication.
- The Session Layer gracefully terminates the session, ensuring all data is exchanged and both sides agree to close

## Session Layer Protocols
Session Layer uses some protocols which are required for safe, secure and accurate communication which exists between two-ender user applications. Following are some of the protocols provided or used by the Session Layer:

- **AppleTalk Data Stream Protocol (ADSP):** ADSP is that type of protocol which was developed by Apple Inc. and it includes a number of features that allow local area networks to be connected with no prior setup. This protocol was released in 1985. This protocol rigorously followed the OSI model of protocol layering. ADSP itself has two protocols named: AppleTalk Address Resolution Protocol (AARP) and Name Binding Protocol (NBP), both aimed at making system self-configuring.

- **Real-time Transport Control Protocol (RTCP):** RTCP is a protocol which provides out-of-band statistics and control information for an RTP (Real-time Transport Protocol) session. RTCP's primary function is to provide feedback on the quality of service (QoS) in media distribution by periodically sending statistical information such as transmitted octet and packet counts or packet loss to the participants in the streaming multimedia session.

- **Point-to-Point Tunneling Protocol (PPTP):** PPTP is a protocol which provides a method for implementing virtual private networks. PPTP uses a TCP control channel and a Generic Routing Encapsulation tunnel to encapsulate PPP (Point-to-Point Protocol) packets This protocol provides security levels and remote access levels comparable with typical VPN (Virtual Private Network) products.

- **Password Authentication Protocol (PAP):** It is a password-based authentication protocol used by Point to Point Protocol (PPP) to validate users. Almost all network operating systems, remote servers support PAP. PAP authentication is done at the time of the initial link establishment and verifies the identity of the client using a two-way handshake (Client-sends data and server in return sends Authentication-ACK (Acknowledgement) after the data sent by client is verified completely).

- **Remote Procedure Call Protocol (RPCP):** It is a protocol that is used when a computer program causes a procedure (or a sub-routine) to execute in a different address space without the programmer explicitly coding the details for the remote interaction. This is basically the form of client-server interaction, typically implemented via a request-response message-passing system.

- **Sockets Direct Protocol (SDP):** It is a protocol that supports streams of sockets over Remote Direct Memory Access (RDMA) network fabrics. The purpose of SDP is to provide an RDMA-accelerated alternative to the TCP protocol. The primary goal is to perform one particular thing in such a manner which is transparent to the application.

## Presentation Layer

The Presentation Layer, also known as Layer 6 in the OSI (Open Systems Interconnection) model, is responsible for translating data between the application layer and the lower layers of the network. It serves as the intermediary that formats and encrypts data to ensure compatibility between different systems and applications.

![image](https://github.com/user-attachments/assets/10ea98a5-835c-4b1f-a9b0-01cfa2497905)

## Data Encoding and Decoding

Encoding involves converting data from one format to another, making it suitable for transmission over a network. This process may involve converting character data to binary formats or using specific encoding schemes like ASCII, EBCDIC, or UTF-8. Decoding, on the other hand, reverses this process, converting the received data back into a format understandable by the application layer.

For instance, when transmitting text, the Presentation Layer encodes the text into a binary format that can be efficiently sent across the network. Upon receipt, the Presentation Layer decodes the binary data back into text, ensuring that the receiving application interprets the information correctly. This encoding/decoding process is essential for maintaining data integrity and ensuring accurate communication between different systems.

### Data Compression and Encryption

Data Compression reduces the size of the data being transmitted, minimising bandwidth usage and accelerating transfer speeds. Compression algorithms, such as ZIP or GZIP, can significantly decrease the amount of data sent over the network, improving performance. However, while compressing data, it's crucial to balance the level of compression with the potential loss of data quality, especially for multimedia content.

![image](https://github.com/user-attachments/assets/a5a7f4f5-dec6-4303-b36f-1b2a66801fbd)

Data Encryption converts data into a secure format that can only be accessed by authorised users. The Presentation Layer employs encryption algorithms (e.g., AES, RSA) to safeguard sensitive information during transmission. By encrypting data, organisations can protect against unauthorised access and data breaches, ensuring confidentiality and integrity during communication.

## Data Formatting in Communication

Data formatting is crucial in ensuring effective communication between different systems. The Presentation Layer defines how data is structured and formatted, enabling applications to correctly interpret and display the information being transmitted. Proper data formatting guarantees that all parties involved in the communication process understand the information in the same way.

For example, when transmitting financial data, the Presentation Layer might specify the number format, decimal places, or currency symbols to ensure that the receiving system interprets the data correctly. Inconsistent formatting can lead to miscommunication, data corruption, or processing errors, emphasising the need for standardised data formats. By enforcing data formatting, the Presentation Layer enhances interoperability among various applications and systems.

## Protocols and Standards at the Presentation Layer
Several protocols and standards operate at the Presentation Layer, facilitating secure and efficient data communication. Notable examples include:

**SSL/TLS (Secure Sockets Layer/Transport Layer Security):** These protocols ensure secure communication over the internet by encrypting data between web browsers and servers. SSL/TLS operates at the Presentation Layer, providing authentication, confidentiality, and data integrity. This is particularly important for protecting sensitive information transmitted during online transactions, such as credit card details and personal data.

**MIME (Multipurpose Internet Mail Extensions):** MIME is a standard that allows the exchange of different types of data, such as text, images, and audio, over email and other internet protocols. It enables email clients to correctly interpret and display various content types by specifying the format and encoding used.

![image](https://github.com/user-attachments/assets/33d98947-4966-4d66-ab24-03fc6aaba01c)

## Presentation Layer in Cross-Platform Communication

The Presentation Layer plays a pivotal role in enabling cross-platform communication by ensuring that data can be exchanged and understood between different operating systems, hardware architectures, and application environments. In a world where diverse systems operate together, the Presentation Layer standardised data formats and encoding schemes, facilitating seamless integration.

For instance, when an application on a Windows machine communicates with a Linux server, the Presentation Layer ensures that the data is correctly formatted and encoded so both systems can interpret it accurately. This compatibility is crucial for cloud computing, web services, and API communications, where various platforms must interact efficiently.
