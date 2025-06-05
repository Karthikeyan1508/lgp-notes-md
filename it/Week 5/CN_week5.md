# Client-Server Model

The Client-Server Model is a distributed application architecture that divides tasks or workloads between servers (providers of resources or services) and clients (requesters of those services). In this model, a client sends a request to a server for data, which is typically processed on the server side. The server then returns the requested data to the client.

Clients generally do not share resources with each other, but instead rely on the server to provide the resources or services requested. Common examples of the client-server model include email systems and the World Wide Web (WWW), where email clients interact with mail servers, and web browsers request resources from web servers.

## How Does the Client-Server Model Work?
In this article, we are going to take a dive into the Client-Server model and have a look at how the Internet works via, web browsers. This article will help us have a solid WEB foundation and help us easily work with WEB technologies.

## Client
When we talk about a "Client," it refers to a device (usually a computer, smartphone, or application) that requests and receives services from a server. The client is the entity that initiates communication, asking for data or resources from the server. For instance, web browsers like Google Chrome, Mozilla Firefox, or Safari are common client applications that request data from a server to render web pages.

## Server
A Server, on the other hand, is a remote computer or system that provides data, resources, or services to clients. It listens to incoming client requests, processes them, and sends the required information back. A server can handle multiple client requests simultaneously.

For example, Web servers host websites, and database servers store and serve databases for applications. In simple terms, the client sends a request to the server, and the server serves the request as long as the data or service is available in its system.

![image](https://github.com/user-attachments/assets/f626583d-90b4-4a8a-b7ac-4e8913fb88bf)

## How the Browser Interacts With the Servers?
The process of interacting with servers through a browser involves several steps. Here's a breakdown of the steps taken when you enter a URL in a browser and receive the website data:

1. **User Enters the URL (Uniform Resource Locator):** The user types a website address (e.g., www.example.com) into the browser's address bar.

2. **DNS (Domain Name System) Lookup:** The browser sends a request to the DNS server to resolve the human-readable URL into an IP address (since computers use IP addresses to identify and connect to each other).

3. **DNS Server Resolves the Address:** The DNS server looks up the domain name and returns the IP address of the web server hosting the requested website.

4. **Browser Sends HTTP/HTTPS Request:** The browser sends an HTTP/HTTPS request to the IP address of the web server to fetch the website’s data. HTTP (HyperText Transfer Protocol) or HTTPS (the secure version) is the protocol used for communication between the browser (client) and the web server (server).

5. **Server Sends Website Files:** The server processes the request and sends the necessary website files (HTML, CSS, JavaScript, images, etc.) back to the browser.

6. **Rendering the Website:** The browser renders the files and displays the website to the user. This rendering process involves several components:Together, these components, known as Just-In-Time (JIT) Compilers, allow the browser to convert raw data into a visual webpage.

**DOM (Document Object Model) Interpreter:** Processes the HTML structure.
**CSS Interpreter:** Applies styles to the HTML elements.
**JS Engine:** Executes JavaScript code for interactivity.

Together, these components, known as Just-In-Time (JIT) Compilers, allow the browser to convert raw data into a visual webpage.

![image](https://github.com/user-attachments/assets/a7926ac7-4dad-4e23-b7cc-05cf2840c3f3)

## Advantages of the Client-Server Model

The Client-Server model offers several advantages that make it popular in networked and distributed systems:

- **Centralized Data Management:** All data is stored in a centralized server, which makes it easier to manage, update, and back up.

- **Cost Efficiency:** Since the server handles most of the processing, clients require fewer resources and can be simpler devices, reducing costs.

- **Scalability:** Both clients and servers can be scaled separately. Servers can be upgraded to handle more clients, and new clients can be added without significant changes to the server infrastructure.

- **Data Recovery:** Centralized data storage on the server allows for better data recovery and easier backup strategies.

- **Security:** Security measures such as firewalls, encryption, and authentication can be centralized on the server, ensuring that sensitive data is protected.

## Disadvantages of Client-Server Model

- **Clients Are Vulnerable:** Clients are prone to viruses, Trojans, and worms if present in the Server or uploaded into the Server.
**- Servers Are Targets:** Servers are prone to Denial of Service (DOS) attacks, where the server is overwhelmed with traffic and made unavailable to legitimate clients.
**- Data Spoofing and Modification:** Data packets may be spoofed or modified during transmission if the proper security measures (e.g., encryption) are not implemented.
**- Man-in-the-Middle (MITM) Attacks:** Phishing or capturing login credentials or other useful information of the user are common and MITM(Man in the Middle) attacks are common.

## Real-World Examples of the Client-Server Model

**1. Email Systems**

Client: The user’s email client (e.g., Microsoft Outlook, Gmail App).
Server: The email server (e.g., Gmail Server, Yahoo Mail Server).
How It Works: The email client requests emails from the server, and the server delivers them. Similarly, when the user sends an email, the client communicates with the server to send the message.

**2. The World Wide Web**
Client: A web browser (e.g., Google Chrome, Mozilla Firefox).
Server: A web server (e.g., Apache Server, Nginx Server).
How It Works: The browser requests the web pages from the server, and the server sends the HTML files back to the client, which are then rendered and displayed.

**3. Cloud Storage Services**
Client: The user’s device (e.g., smartphone, PC).
Server: A cloud server (e.g., Google Drive, Dropbox).
How It Works: The client uploads files to the server and can download them when needed. The server stores all the user’s files centrally, ensuring remote access to data.

## Conclusion
The Client-Server Architecture is fundamental to modern networking and distributed systems. It efficiently handles resource sharing, data management, and scalability. While there are some security risks, such as Denial of Service (DoS) attacks and Man-in-the-Middle (MITM) attacks, these can be mitigated with encryption, firewalls, and authentication mechanisms.

The Client-Server Model has become more powerful with cloud computing, where servers provide scalable and secure services to clients globally. Understanding how the Client-Server model works lays a solid foundation for anyone working with web technologies, networking, or cloud services.

# What Is A Firewall?

**A firewall is either a hardware device or a software application that helps protect your network from attackers. The firewall shields your network by acting as a 24/7 filter,** scanning the data that attempts to enter your network and preventing anything that looks suspicious from getting through.

A simple way to explain how a firewall works is to think of it as a security guard with intimate knowledge of millions of potential criminals. If the guard sees one, he or she keeps the criminal out of the building. Similarly, a firewall’s protection comes from monitoring and regulating traffic that goes in and out of your network. This is accomplished using a few different methods, including packet filtering, a proxy service, and stateful inspection. 

Firewalls can be either hardware or software, and they form a wall between your network and the internet or between segments of your network and the rest of your system. Not only do firewalls keep malicious code out of your network, but some, because they can examine data both as it comes in and goes out, can also prevent an attacker from using your system to spread harmful code.

## How does a Firewall Work?
Firewalls are essential security tools that monitor and control network traffic, acting like gatekeepers for your system. They inspect data packets, comparing them to predefined rules to determine whether to allow or block them. 

These rules can be based on various factors, such as source and destination IP addresses, ports, and protocols. Firewalls use techniques like packet filtering, proxy services, and stateful inspection to enforce these rules.

By carefully scrutinizing network traffic and enforcing security rules, firewalls prevent unauthorized access, block malicious activities, and protect your system from a wide range of cyber threats. They act as a vital line of defense, safeguarding your sensitive data and ensuring a secure online environment.

## How Firewalls Filter Traffic to Prevent Unauthorized Access
Firewalls meticulously inspect network traffic to ensure only legitimate data passes through while blocking unauthorized access. This process involves several key steps, working together to safeguard your network from potential threats.

**Process in 5 Steps:**

- **Traffic Monitoring:** Constantly monitors all incoming and outgoing network traffic, acting as a vigilant gatekeeper for your system.

- **Rule Application:** Compares each data packet against predefined security rules to determine if it should be allowed or blocked.
- **Packet Inspection:** Examines packet headers and contents, including source/destination IP addresses and ports, for suspicious activity.
- **Decision Making:**  Based on inspection and rules, decides to allow legitimate traffic and block potential threats.
- **Logging and Alerts:**  Maintains detailed logs of actions and generates alerts for suspicious activity or unauthorized access attempts.

This multi-layered filtering process ensures that your network remains protected from unauthorized access and potential threats

## Firewall Types

### Hardware firewalls
A hardware firewall is a system that works independently from the computer it is protecting as it filters information coming from the internet into the system. If you have a broadband internet router, it likely has its own firewall.

To protect your system, a hardware firewall checks the data coming in from the various parts of the internet and verifies that it is safe. Hardware firewalls that use packet filtering examine each data packet and check to see where it is coming from and its location. The data the firewall collects about each packet is then compared to a permissions list to see if it fits the profile of data that should be discarded. A hardware firewall can protect all the computers attached to it, making it an easily scalable solution.

![image](https://github.com/user-attachments/assets/3ec6eeb3-28e4-482a-a945-63c42bf68e57)

### Software firewalls
A software firewall is a program used by a computer to inspect data that goes in and out of the device. It can be customized by the user to meet their needs. Like hardware firewalls, software firewalls filter data by checking to see if it—or its behavior—fits the profile of malicious code.

Software firewalls can monitor traffic trying to leave your computer as well, preventing it from being used to attack other networks or devices. A software firewall has to be installed on each computer in the network. Therefore, a software firewall can only protect one computer at a time.

Firewalls use different methods to protect your network or computer. They include the following:

### Packet filtering
Data is organized in packets. When a firewall executes packet filtering, it examines the packets of data, comparing it against filters, which consist of information used to identify malicious data. If a data packet meets the parameters of a threat as defined by a filter, then it is discarded and your network is protected. Data packets that are deemed safe are allowed to pass through.

### Proxy service
With a proxy service, the firewall acts as a go-between positioned between your computer and anything that tries to connect to it. A proxy firewall is like a mirror of your computer and detects malicious actors attempting to get through to your device. 

Proxy firewalls are a secure solution because of the separation they provide between your computer and the internet. Attackers often need to connect directly to your computer to attack it. Because a proxy is between your computer and the internet, hackers cannot form a direct connection to it, rendering their attack useless. 

However, there are applications that proxies are not capable of supporting, and if one of these is important to your business, this could pose an issue. For example, Spotify, Google Play, and QWebView have all been known to have issues when interfacing with a proxy. Proxies also tend to work slower than other types of firewalls, which could reduce throughput and impact important business processes.

### Stateful inspection
A stateful inspection firewall inspects every data packet and compares it against a threat database. During the inspection process, the firewall checks where the data is coming from, the ports it uses, and the applications it is associated with. If the data packet checks out, it is allowed to pass. Otherwise, it is discarded. 

Stateful inspection can also collect information about the data packets that go through it and use that to gain more insights into data that may pose potential threats in the future.

Because a proxy server has its own IP address, it acts as a go-between for a computer and the internet. Your computer knows this address, and when you send a request on the internet, it is routed to the proxy, which then gets the response from the web server and forwards the data from the page to your computer’s browser, like Chrome, Safari, Firefox, or Microsoft Edge.


## How Does A Firewall Protect Data?
Firewall filters keep harmful data outside your computer. Some of the top risks from which firewalls protect your computer include backdoors, denial-of-service (DoS) attacks, macros, remote logins, spam, and viruses.

Backdoors are “doorways” to applications with vulnerabilities that attackers exploit to get inside. This includes operating systems that may have bugs that hackers can use to gain access to your computer.

DoS attacks are executed when a hacker requests permission to connect to a server, and when the server responds, it cannot find the system that made the request. When this is done again and again, the server gets flooded and has to expend so much power to deal with the mass of requests, rendering it unable to meet the needs of legitimate visitors. In some cases, the server has to come offline completely. There are some firewalls that can check whether the connection requests are legitimate, and thus, protect your network from DoS attacks.

Macros refer to scripts run by applications to automate processes. A macro can contain a series of dependent steps that are all launched by one command. Hackers design or purchase macros intended to work within certain applications. A macro can be hidden inside seemingly innocent data, and once it enters your computer, it wreaks havoc on your system. A firewall can detect malicious macros as it examines the packets of data that attempt to pass through.

Remote logins are often used to help someone with a computer issue. However, in the hands of the wrong person, they can be abused, particularly because remote logins provide nearly complete access to your system.

Spam can sometimes include links to malicious websites. These types of sites activate malicious code that forces cookies onto a computer. The cookies create backdoors for hackers to gain access to the computer. Preventing a spam attack is often as simple as not clicking on anything suspicious in an email, regardless of who the sender appears to be. A firewall can inspect your emails and prevent your computer from getting infected.

Viruses, once on a computer, copy themselves and spread to another device on the network. Viruses can be used to do a variety of things, ranging from relatively harmless activity to erasing data on your computer. Firewalls can inspect data packets for viruses, but it is better to use antivirus software in conjunction with a firewall to maximize your security.

# What is SSL?

SSL, or Secure Sockets Layer, is an encryption-based Internet security protocol. It was first developed by Netscape in 1995 for the purpose of ensuring privacy, authentication, and data integrity in Internet communications. SSL is the predecessor to the modern TLS encryption used today.

A website that implements SSL/TLS has "HTTPS" in its URL instead of "HTTP."

## How does SSL/TLS work?
In order to provide a high degree of privacy, SSL encrypts data that is transmitted across the web. This means that anyone who tries to intercept this data will only see a garbled mix of characters that is nearly impossible to decrypt.

SSL initiates an authentication process called a handshake between two communicating devices to ensure that both devices are really who they claim to be.

SSL also digitally signs data in order to provide data integrity, verifying that the data is not tampered with before reaching its intended recipient.
There have been several iterations of SSL, each more secure than the last. In 1999 SSL was updated to become TLS.

## Why is SSL/TLS important?
Originally, data on the Web was transmitted in plaintext that anyone could read if they intercepted the message. For example, if a consumer visited a shopping website, placed an order, and entered their credit card number on the website, that credit card number would travel across the Internet unconcealed.

SSL was created to correct this problem and protect user privacy. By encrypting any data that goes between a user and a web server, SSL ensures that anyone who intercepts the data can only see a scrambled mess of characters. The consumer's credit card number is now safe, only visible to the shopping website where they entered it.

SSL also stops certain kinds of cyber attacks: It authenticates web servers, which is important because attackers will often try to set up fake websites to trick users and steal data. It also prevents attackers from tampering with data in transit, like a tamper-proof seal on a medicine container.

Are SSL and TLS the same thing?
SSL is the direct predecessor of another protocol called TLS (Transport Layer Security). In 1999 the Internet Engineering Task Force (IETF) proposed an update to SSL. Since this update was being developed by the IETF and Netscape was no longer involved, the name was changed to TLS. The differences between the final version of SSL (3.0) and the first version of TLS are not drastic; the name change was applied to signify the change in ownership.

Since they are so closely related, the two terms are often used interchangeably and confused. Some people still use SSL to refer to TLS, others use the term "SSL/TLS encryption" because SSL still has so much name recognition.

Is SSL still up to date?
SSL has not been updated since SSL 3.0 in 1996 and is now considered to be deprecated. There are several known vulnerabilities in the SSL protocol, and security experts recommend discontinuing its use. In fact, most modern web browsers no longer support SSL at all.

TLS is the up-to-date encryption protocol that is still being implemented online, even though many people still refer to it as "SSL encryption." This can be a source of confusion for someone shopping for security solutions. The truth is that any vendor offering "SSL" these days is almost certainly providing TLS protection, which has been an industry standard for over 20 years. But since many folks are still searching for "SSL protection," the term is still featured prominently on many product pages.

What is an SSL certificate?
SSL can only be implemented by websites that have an SSL certificate (technically a "TLS certificate"). An SSL certificate is like an ID card or a badge that proves someone is who they say they are. SSL certificates are stored and displayed on the Web by a website's or application's server.

One of the most important pieces of information in an SSL certificate is the website's public key. The public key makes encryption and authentication possible. A user's device views the public key and uses it to establish secure encryption keys with the web server. Meanwhile the web server also has a private key that is kept secret; the private key decrypts data encrypted with the public key.

Certificate authorities (CA) are responsible for issuing SSL certificates.

## What are the types of SSL certificates?
There are several different types of SSL certificates. One certificate can apply to a single website or several websites, depending on the type:

- **Single-domain:** A single-domain SSL certificate applies to only one domain (a "domain" is the name of a website, like www.cloudflare.com).
**- Wildcard:** Like a single-domain certificate, a wildcard SSL certificate applies to only one domain. However, it also includes that domain's subdomains. For example, a wildcard certificate could cover www.cloudflare.com, blog.cloudflare.com, and developers.cloudflare.com, while a single-domain certificate could only cover the first.
- **Multi-domain:** As the name indicates, multi-domain SSL certificates can apply to multiple unrelated domains.

SSL certificates also come with different validation levels. A validation level is like a background check, and the level changes depending on the thoroughness of the check.

- **Domain Validation:** This is the least-stringent level of validation, and the cheapest. All a business has to do is prove they control the domain.
- **Organization Validation:** This is a more hands-on process: The CA directly contacts the person or business requesting the certificate. These certificates are more trustworthy for users.
- **Extended Validation:** This requires a full background check of an organization before the SSL certificate can be issued.

# World Wide Web (WWW)

The World Wide Web (WWW), often called the Web, is a system of interconnected webpages and information that you can access using the Internet. It was created to help people share and find information easily, using links that connect different pages together. The Web allows us to browse websites, watch videos, shop online, and connect with others around the world through our computers and phones.

All public websites or web pages that people may access on their local computers and other devices through the internet are collectively known as the World Wide Web or W3. Users can get further information by navigating to links interconnecting these pages and documents. This data may be presented in text, picture, audio, or video formats on the internet.

![image](https://github.com/user-attachments/assets/3896ffad-7d13-4fe6-94fa-4571afe0469f)

**Fact:** Today, it connects over 63% of the world’s population, making it one of the most powerful tools for communication and information sharing.

## Key Parts of the Web

The Web has three main building blocks that make it work:

- **URL (Uniform Resource Locator):** This is the address of a webpage, like https://www.example.com. It tells your browser exactly where to find the page.
- **HTTP (Hypertext Transfer Protocol):** This is the set of rules that lets your browser and the server talk to each other to send and receive webpages.
- **HTML (Hypertext Markup Language):** This is the code that tells browsers how to display a webpage, including where to put text, pictures, and links.

## Working of World Wide Web(WWW)

A Web browser is used to access web pages. Web browsers can be defined as programs which display text, data, pictures, animation and video on the Internet. Hyperlinked resources on the World Wide Web can be accessed using software interfaces provided by Web browsers. Initially, Web browsers were used only for surfing the Web but now they have become more universal.

The below diagram indicates how the Web operates just like client-server architecture of the internet. When users request web pages or other information, then the web browser of your system request to the server for the information and then the web server  provide requested services to web browser back and finally the requested service is utilized by the user who made the request.

![image](https://github.com/user-attachments/assets/e43b74e7-e2c2-48dc-99d7-3b5cadcd9e44)

## World Wide Web (WWW) Vs Internet
It’s easy to mix up the Web and the Internet, but they’re different:

![image](https://github.com/user-attachments/assets/ce4ea5d9-7b7c-4dc6-b5c5-b1a6ede1695e)

# What is IP Security (IPSec)

**IP Security (IPSec)** refers to a collection of communication rules or protocols used to establish secure network connections. Internet Protocol (IP) is the common standard that controls how data is transmitted across the internet. IPSec enhances the protocol security by introducing encryption and authentication. IPSec encrypts data at the source and then decrypts it at the destination. It also verifies the source of the data.

## Importance of IPSec
IPSec (Internet Protocol Security) is important because it helps keep your data safe and secure when you send it over the Internet or any network. Here are some of the important aspects why IPSec is Important:

- IPSec protects the data through Data Encryption.
- IPSec provides Data Integrity.
- IPSec is often used in Virtual Private Networks (VPNs) to create secure, private connections.
- IPSec protects from Cyber Attacks.

### Features of IPSec
1. **Authentication:** IPSec provides authentication of IP packets using digital signatures or shared secrets. This helps ensure that the packets are not tampered with or forged.
2. **Confidentiality:** IPSec provides confidentiality by encrypting IP packets, preventing eavesdropping on the network traffic.
3. **Integrity:** IPSec provides integrity by ensuring that IP packets have not been modified or corrupted during transmission.
4. **Key management:** IPSec provides key management services, including key exchange and key revocation, to ensure that cryptographic keys are securely managed.
5. **Tunneling:** IPSec supports tunneling, allowing IP packets to be encapsulated within another protocol, such as GRE (Generic Routing Encapsulation) or L2TP (Layer 2 Tunneling Protocol).
6. **Flexibility:** IPSec can be configured to provide security for a wide range of network topologies, including point-to-point, site-to-site, and remote access connections.
7. **Interoperability:** IPSec is an open standard protocol, which means that it is supported by a wide range of vendors and can be used in heterogeneous environments.

## How Does IPSec Work
IPSec (Internet Protocol Security) is used to secure data when it travels over the Internet. IPSec works by creating secure connections between devices, making sure that the information exchanged is kept safe from unauthorized access. IPSec majorly operates in two ways i.e. Transport Mode and Tunnel Mode.

To provide security, IPSec uses two main protocols: AH (Authentication Header) and ESP (Encapsulating Security Payload). Both protocols are very useful as Authentication Header verifies the data that whether it comes from a trusted source and hasn’t been changed, and ESP has the work of performing authentication and also encrypts the data so that it becomes difficult to read.

For Encryption, IPSec uses cryptographic keys. It can be created and shared using a process called IKE (Internet Key Exchange), that ensures that both devices have the correct keys to establish a secure connection.

When two devices communicate using IPSec, the devices first initiate the connection by sending a request to each other. After that, they mutually decide on protection of data using passwords or digital certificates. Now, they establish the secure tunnel for communication. Once the tunnel is set up, data can be transmitted safely, as IPSec is encrypting the data and also checking the integrity of the data to ensure that data has not been altered. After the communication is finished, the devices can close the secure connection. In this way, the IPSec works.

![image](https://github.com/user-attachments/assets/0a234974-35c3-4593-9ef2-6aad29bdfe9f)

## IPSec Connection Establishment Process
IPSec is a protocol suite used in securing communication using the Internet Protocol such that each packet communicated in the course of a particular session is authenticated and encrypted. The process of establishing an IPSec connection involves two main phases:

### Phase 1 Establishing the IKE (Internet Key Exchange) Tunnel
In phase 1, the main aim is to establish the secure channel the IKE tunnel, which is used to further negotiations. Phase 1 can operate in one of two modes:

**Main Mode:** Main Mode is a six-message exchange procedure that is more secure than Basic Mode, although at the cost of a longer session, since identity information is transmitted during negotiations.
**Aggressive Mode:** Aggressive Mode takes lesser time with the exchange of three messages and is less secure since more information like identity is disclosed during the course of negotiation.

### Phase 2: Establishing the IPSec Tunnel
Phase 2 is called Quick Mode and its aim is to negotiate the IPSec Security Associations after the construction of a secure IKE tunnel has been made. There are two modes in Phase 2.

**Tunnel Mode:** This mode encapsulates the whole of the original IP packet including the header and data. It is mostly deployed in the site to site VPNs.
**Transport Mode:** By this mode, only the actual data to be transmitted is encrypted and the header part of the IP packets remain unaltered. It is mainly employed in end to end communication between hosts.

## Difference Between IPSec Tunnel Mode and IPSec Transport Mode
The IPSec tunnel mode is appropriate for sending data over public networks because it improves data security against unauthorised parties. The computer encrypts all data, including the payload and header, and adds a new header to it.
IPSec transport mode encrypts only the data packet's payload while leaving the IP header unchanged. The unencrypted packet header enables routers to determine the destination address of each data packet. As a result, IPSec transport is utilized in a closed and trusted network, such as to secure a direct link between two computers.

## Protocols Used in IPSec
It has the following components:

1. Encapsulating Security Payload (ESP)
2. Authentication Header (AH)
3. Internet Key Exchange (IKE)

**1. Encapsulating Security Payload (ESP):** It provides data integrity, encryption, authentication, and anti-replay. It also provides authentication for payload.

**2. Authentication Header (AH):** It also provides data integrity, authentication, and anti-replay and it does not provide encryption. The anti-replay protection protects against the unauthorized transmission of packets. It does not protect data confidentiality.

![image](https://github.com/user-attachments/assets/bc1bfc19-65c6-43df-9467-4089a6aab7d9)

**3. Internet Key Exchange (IKE):** It is a network security protocol designed to dynamically exchange encryption keys and find a way over Security Association (SA) between 2 devices. The Security Association (SA) establishes shared security attributes between 2 network entities to support secure communication. The Key Management Protocol (ISAKMP) and Internet Security Association provides a framework for authentication and key exchange. ISAKMP tells how the setup of the Security Associations (SAs) and how direct connections between two hosts are using IPsec. Internet Key Exchange (IKE) provides message content protection and also an open frame for implementing standard algorithms such as SHA and MD5. The algorithm's IP sec users produce a unique identifier for each packet. This identifier then allows a device to determine whether a packet has been correct or not. Packets that are not authorized are discarded and not given to the receiver. 

![image](https://github.com/user-attachments/assets/51514dce-bd55-4756-967a-564b771048b1)

### IP Security Architecture
IPSec (IP Security) architecture uses two protocols to secure the traffic or data flow. These protocols are

- ESP (Encapsulation Security Payload)
- AH (Authentication Header)

IPSec Architecture includes protocols, algorithms, DOI, and Key Management. All these components are very important in order to provide the three main services such as Confidentiality, Authenticity and Integrity.

![image](https://github.com/user-attachments/assets/ce850517-7170-4e27-a8c6-dbd03583f79b)

### IPSec Encryption
IPSec encryption is a software function that encrypts data to protect it from unauthorized access. An encryption key encrypts data, which must be decrypted. IPSec supports a variety of encryption algorithms, including AES, Triple DES etc. IPSec combines asymmetric and symmetric encryption to provide both speed and security during data transmission. In asymmetric encryption, the encryption key is made public, while the decryption key remains private. Symmetric encryption employs the same public key to encrypt and decrypts data. IPSec builds a secure connection using asymmetric encryption and then switches to symmetric encryption to speed up data transmission.

### IPSec VPN
VPN(Virtual Private Network) is a networking software that enables users to browse the internet anonymously and securely. An IPSec VPN is a type of VPN software that uses the IPSec protocol to establish encrypted tunnels over the internet. It offers end-to-end encryption, which means that data is broken down at the computer and then collected at the receiving server.

### Uses of IP Security
IPsec can be used to do the following things:

- To encrypt application layer data.
- To provide security for routers sending routing data across the public internet.
- To provide authentication without encryption, like to authenticate that the data originates from a known sender.
- To protect network data by setting up circuits using IPsec tunneling in which all data being sent between the two endpoints is encrypted, as with a Virtual Private Network(VPN) connection.

### Advantages of IPSec
- **Strong security:** IPSec provides strong cryptographic security services that help protect sensitive data and ensure network privacy and integrity.
- **Wide compatibility:** IPSec is an open standard protocol that is widely supported by vendors and can be used in heterogeneous environments.
- **Flexibility:** IPSec can be configured to provide security for a wide range of network topologies, including point-to-point, site-to-site, and remote access connections.
- **Scalability:** IPSec can be used to secure large-scale networks and can be scaled up or down as needed.
- **Improved network performance:** IPSec can help improve network performance by reducing network congestion and improving network efficiency.

### Disadvantages of IPSec
- **Configuration Complexity:** IPSec can be complex to configure and requires specialized knowledge and skills.
- **Compatibility Issues:** IPSec can have compatibility issues with some network devices and applications, which can lead to interoperability problems.
- **Performance Impact:** IPSec can impact network performance due to the overhead of encryption and decryption of IP packets.
- **Key Management:** IPSec requires effective key management to ensure the security of the cryptographic keys used for encryption and authentication.
- **Limited Protection:** IPSec only provides protection for IP traffic, and other protocols such as ICMP, DNS, and routing protocols may still be vulnerable to attacks.
