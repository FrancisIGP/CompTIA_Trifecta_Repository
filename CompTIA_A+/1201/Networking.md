# CompTIA A+ Core 1 (220-1201)

The content for this material is based from the [Official CompTIA A+ 220-1201 Exam Objectives](https://partners.comptia.org/docs/default-source/resources/comptia-a-220-1201-exam-objectives-(2-0)). These objectives serve as a comprehensive guide to the topics covered in the certification exam, including hardware, networking, mobile devices, virtualization, cloud computing, and troubleshooting.

## 2.0 Networking

### 2.1 Compare and contrast Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) ports, protocols, and their purposes

### Introduction to IP

- The network is designed to transfer data from one device to another and can be imagined as a highway where packages (data) are encapsulated with information and shipped via delivery trucks (IP packets) that travel over the network to be unpacked at the destination
.
    - These data packages contain TCP or UDP information, which is essential for managing how data is transferred across the network.

- These networks can be referred to as:

    - Ethernet networks
    - Wireless networks
    - DSL networks
    - Cable Systems
    - etc.

- Internet Protocol (IP)

    - 2 types: IP version 4 (IPv4) and IP version 6 (IPv6)

    - As mentioned earlier, IP packets are encapsulated with specific information that enables the reliable transfer of data across a network. These packets are structured into three main parts:

        - Header - This section contains control and routing information necessary for routing and delivery.

            - Source IP address (where the packet came from)

            - Destination IP address (where the packet is going)

        - Payload - Contains the transport layer segment, such as TCP or UDP.

            - TCP or UDP segment - Transport layer protocols that define how data is broken into segments (TCP for reliable connection, UDP for faster, connectionless transmission).

                - Source Port - This is the port number of the sending application (typically the client). It is often a dynamic or ephemeral port, which is a temporary port randomly chosen by the client from a predefined range (usually 1024 to 65535). It allows multiple connections to the same destination without conflict.

                - Destination Port - This is the port number of the receiving application, typically the server (Ports through 0 to 1023). It is usually a non-ephemeral or well-known port—a specific number assigned to a standard service (service port) . For example:

                    - Port 80 for HTTP (web)

                    - Port 443 for HTTPS (secure web)

                    - Port 25 for SMTP (email)

                    - Port 53 for DNS (domain name system)

                - These ports ensure that data is delivered to the correct application on a device.   

                - Other transport layer info like sequence number, checksum, etc.

            - Payload - The actual content or message from the user (e.g., web page, email content, file data, etc.).

        - Trailer - It is a section added at the end of a data frame, mainly used at the Data Link Layer for error checking (e.g., CRC). IP packets at the Network Layer do not have trailers; error checking is done in the header or by other layers like TCP or Ethernet.

- TCP vs UDP

    - TCP and UDP are transport layer protocols that enable multiple applications to communicate over a network. They add capabilities that IP alone can’t provide, such as multiplexing—allowing many applications on one system to communicate simultaneously with a remote server.

    - Transmission Control Protocol (TCP)

        - TCP is a connection-based protocol that establishes a reliable connection between sender and receiver before data transfer, making it ideal for important transactions but slower.

            - This formal connection process is called the TCP 3-way handshake:

                - Step 1 – SYN (Client → Server): Client sends a synchronize packet to request connection, including an initial sequence number.

                - Step 2 – SYN-ACK (Server → Client): Server acknowledges (ACK) the request and sends its own SYN with a sequence number.

                - Step 3 – ACK (Client → Server): Client acknowledges the server’s SYN. The connection is now established, ready for data transfer.

        - TCP ensures all packets arrive correctly and in order, retransmitting lost packets, which adds overhead and slows communication.

        - Supports flow control, allowing the receiver to manage how much data is sent over the network to prevent overload.

        - TCP is commonly used in applications where data accuracy is critical, such as web browsing (HTTP/HTTPS), email (SMTP), and file transfers (FTP).

    - User Datagram Protocol (UDP)

        - UDP is connectionless and faster, sending data without establishing a formal connection or waiting for acknowledgments.

        - It does not guarantee delivery or order, so packets may be lost or arrive out of sequence, making it less reliable.

        - Some applications add their own error handling to compensate for UDP’s lack of retransmission.

        - UDP is used in applications where speed is more important than accuracy, such as online gaming, video streaming, and voice calls (VoIP).

### Common Protocols/Ports

- Network protocols are a set of rules that computers follow to communicate and share data properly over a network. It’s like a common language with specific instructions so devices can understand each other.

- TCP and UDP protocols uses port numbers to communicate with import services in the network and familiarizing yourself with the common port numbers will help you troubleshoot better. This can also be useful if you are implementing port-based security in your firewall to manage inbound/outbound traffic.

### Comprehensive Table of Ports and Protocols

| **Port Number(s)**       | **Protocol Name**                                             | **TCP/UDP** | **Purpose / Explanation**                                                                                                                                               |
| ------------------------ | ------------------------------------------------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 20, 21                   | FTP (File Transfer Protocol)                                  | TCP         | **Port 21** is used to establish control (commands), and **Port 20** is used to send data. FTP transfers files between computers but is **not secure** (no encryption). |
| 22                       | SSH (Secure Shell)                                            | TCP         | Used for **secure remote login** to another computer. SSH encrypts traffic (unlike Telnet) and is commonly used for managing servers.                                   |
| 23                       | Telnet                                                        | TCP         | Allows a user to **remotely access another device** but sends everything in **plain text** (insecure). Mostly obsolete, replaced by SSH.                                |
| 25                       | SMTP (Simple Mail Transfer Protocol)                          | TCP         | Used to **send emails** from a client to a mail server or between mail servers. Doesn't handle incoming mail.                                                           |
| 53                       | DNS (Domain Name System)                                      | TCP/UDP     | Translates **domain names into IP addresses**. Uses **UDP** for normal queries and **TCP** for zone transfers or large queries.                                         |
| 67 (server), 68 (client) | DHCP (Dynamic Host Configuration Protocol)                    | UDP         | Automatically **assigns IP addresses** and other network config to clients. Port 67 is used by the server; 68 is used by the client.                                    |
| 80                       | HTTP (Hypertext Transfer Protocol)                            | TCP         | The standard protocol for **browsing websites** (not secure). Uses plain text; data can be intercepted.                                                                 |
| 110                      | POP3 (Post Office Protocol v3)                                | TCP         | Used to **receive emails** by downloading them to a local device and usually deleting them from the server. Ideal for single-device use.                                |
| 143                      | IMAP (Internet Message Access Protocol)                       | TCP         | Allows **multiple-device email access**, where emails remain on the server. Common with web-based email services.                                                       |
| 137-139                  | NetBIOS/NetBT (Network Basic Input/Output System over TCP/IP) | TCP/UDP     | Used by older Windows systems for **file and printer sharing**, and name resolution before DNS and SMB took over.                                                       |
| 389                      | LDAP (Lightweight Directory Access Protocol)                  | TCP/UDP     | Used to **access and manage directory services**, such as user credentials and organizational data in Active Directory.                                                 |
| 443                      | HTTPS (HTTP Secure)                                           | TCP         | A secure version of HTTP. Encrypts data between your browser and websites using SSL/TLS. Standard for **secure web browsing**.                                          |
| 445                      | SMB/CIFS (Server Message Block/Common Internet File System)   | TCP         | Used for **file, printer, and resource sharing** across Windows networks. Modern replacement for NetBIOS.                                                               |
| 3389                     | RDP (Remote Desktop Protocol)                                 | TCP         | Enables **graphical remote access** to a Windows computer, letting you control it as if you’re physically there.                                                        |

### NetBIOS vs SMB (Key Difference)

| **NetBIOS / NetBT**                                                                            | **SMB / CIFS**                                                                           |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Specialized in **locating devices (name service)** and **establishing sessions** between them. | Specialized in **transferring data** — like files, printers, and inter-process messages. |
| Think of it as the **directory and handshake system**.                                         | Think of it as the **delivery system**.                                                  |
| Doesn’t transfer files itself — it just helps devices find each other and talk.                | Actually moves the files, shares folders, or lets you use a network printer.             |
| Often used **together with SMB in older systems**.                                             | Still widely used today **without needing NetBIOS**.                                     |

> Think: NetBIOS says **“Hi, I found you!”**, SMB says **“Cool, now send me the file.”**

### 2.2 Explain wireless networking technologies

### Wireless Technologies

- The standards for wireless networks come from an Industrial Electrical Electronics Engineers (IEEE) LAN/MAN Standards Comittee called the **IEEE 802** committee and the wireless networking part of this committee is the **802.11** standard.

- many updates over time, check with IEEE for the latest.

- instead of referring to them as 802.11 wireless networks, you can call it a **Wi-Fi** network.

	- This is a trademark from the Wi-Fi Alliance who is responsible for testing the interoperability of all of these different wireless devices

    - These WiFi networks can also be referenced as generations:

        - 802.11ac is WiFi 5
        - 802.11ax is WiFi 6 and WiFi 6E (Extended)
        - 802.11be is WiFi 7
        - Future versions will increment accordingly.

- Frequencies

    - Wireless networks operate on different frequency bands, primarily **2.4 GHz**, **5 GHz**, and more recently **6 GHz** (used in Wi-Fi 6E).

    - These frequency bands define **how far and how fast** data can travel:

        - **2.4 GHz**: Has **longer range** but **lower speeds** and is more prone to interference (used by many devices like microwaves, Bluetooth, etc.).
        - **5 GHz**: Offers **faster speeds** and **less interference**, but with **shorter range**.
        - **6 GHz**: Provides **even more channels**, **higher speeds**, and **lower latency**, but requires **Wi-Fi 6E compatible devices**.

    - Some routers use **dual-band or tri-band** technology to operate on **multiple frequencies** simultaneously, improving speed and reducing congestion.

- Channels

    - Each frequency band is divided into **smaller segments called channels**. These are used to carry the wireless signal.

    - For example, the **2.4 GHz** band has **14 channels** (in some regions), but only **3 non-overlapping channels** (1, 6, and 11) to prevent interference.

    - The **5 GHz** and **6 GHz** bands have many more channels, and most of them are **non-overlapping**, reducing interference and increasing performance.

    - Channels are assigned and regulated by **IEEE standards** and **regional regulations**, meaning not all channels are available in every country.

- Bandwidth

    - **Bandwidth** in wireless networking has **two related meanings**, often confused:

        - **Channel Width** (in MHz):

            - This is the **amount of frequency space** used for a single wireless channel.
            - Common widths are **20, 40, 80, and 160 MHz**.
            - Wider channels allow more data to be transmitted at once, increasing potential speed.
            - However, wider channels can cause more **interference** and are more likely to **overlap** with other channels, especially in congested areas.
            - Example: A channel on the 5 GHz band using 80 MHz can carry more data, but may interfere with nearby channels if not planned properly.

        - **Data Bandwidth** (in Mbps or Gbps):

            - This is the **amount of data** that can be transferred **per second** across a network.
            - Affected by:
                - Channel width
                - Frequency band
                - Signal strength and quality
                - Distance from the access point
                - Network congestion and interference

    - More bandwidth **(in MHz)** generally allows for **higher throughput**, but actual performance depends on multiple environmental and technical factors.

- Bluetooth

    - Bluetooth is a **short-range wireless technology** used for connecting devices over distances up to **10 meters**.

    - Common Bluetooth devices include:

        - Headsets
        - Speakers
        - Keyboards and mice
        - Fitness trackers and smartwatches

    - Bluetooth operates in the **2.4 GHz** ISM (Industrial, Scientific, Medical) band, which is **unlicensed**—meaning no special permission is required to use it.

- Radio-frequency Identification (RFID)

    - RFID is a wireless communication method that uses **radio waves** to **identify and track objects**.

    - RFID tags come in two types:

        - **Passive RFID**:

            - No battery; powered by the radio waves from the reader.
            - Typically used for **short-range scanning** (like in access cards or inventory tags).

        - **Active RFID**:

            - Battery-powered; doesn't rely on external radio waves.
            - Capable of **longer-range communication**.

    - Supports **bidirectional communication**, allowing the tag and reader to exchange data.

- Near Field Communication (NFC)

    - NFC is based on RFID technology but is designed for **two-way communication** over **very short distances** (usually less than 4 cm).

    - Common uses include:
        - Contactless payments (e.g., Apple Pay, Google Pay)
        - Identity verification
        - Authentication and access control

    - NFC is often used to **initiate** connections with other wireless technologies (like Wi-Fi or Bluetooth), supplying configuration data needed for the connection.

### 2.3 Summarize services provided by networked hosts

### Network Services

- Most services we use on the internet such as web and DNS servers are ran by physical servers, often located on data centers or in a secure isolated area. These servers are built with multiple technologies that run different services.

- Domain Name System (DNS)

  - Converts names to IP addresses and vice versa.

  - The load on these servers is evenly distributed across many different servers worldwide 
  based on the domain name they support.
  
  - DNS servers retrieve the website itself or a cached version of it when accessed.
  
  - DNS servers are usually managed by your Internet Service Provider (ISP) or enterprise IT department.

- Dynamic Host Configuration Protocol (DHCP)
  
  - A widely used service primarily assigned for automatic IP address and configuration assignment to devices within a local area network (LAN).
  
  - Enterprise networks usually have multiple DHCP servers to provide redundancy in case one becomes unavailable.

- File Share
  
  - A centralized file-sharing system where files are stored and can be easily accessed by other people within the organization.
  
  - Runs a standard type of file service depending on its environment: Server Message Block (SMB), Apple Filing Protocol (AFP), etc.
  
  - Some file-sharing services may hide the specific protocol being used to manage these files.

- Print Server
  
  - A printing service that allows you to remotely assign print jobs, queue them, and ensure they are printed successfully.
  
  - This service can be integrated into an independent system linked to the printer or built into the printer itself via a network card.
  
  - Uses standard printing protocols:
  
    - Server Message Block (SMB)
    - Internet Printing Protocol (IPP)
    - Line Printer Daemon (LPD)

- Mail Server
  
  - Responsible for handling and managing incoming and outgoing email messages for your system.
  
  - Also managed by ISPs or enterprise IT departments.
  
  - One of the few services with very high uptime expectations (24/7 support), as it often needs to be available at any given moment, requiring proper installation and maintenance.

- System Log (Syslog)
  
  - A very useful debugging service that allows you to consolidate all accumulated system log files from different sources into a centralized database.
  
  - These log files are usually stored on a central logging receiver called a Security Information and Event Manager (SIEM), which allows you to access log files from one consolidated point.
  
  - Due to its high resource demands, it requires substantial disk space to store numerous existing and incoming log files from various systems.

- Web Server
  
  - Responsible for responding to browser requests using browsing protocols such as HTTP/HTTPS to access websites.
  
  - These websites are built with HTML/HTML5, containing the content of the website, which is then interpreted and displayed graphically by the browser.

- Authentication Server
  
  - An authentication service that verifies your login credentials (username/password) and grants access to the respective service.
  
    - Sometimes referred to as Authentication, Authorization, and Accounting (AAA) server.
  
  - Has a centralized database where all user credentials are stored and managed.
  
  - Often implemented in enterprise networks to provide high security and ensure continuous access to credentials through redundant authentication servers.

- Database Server
  
  - Stores information in tables or spreadsheet-like formats, allowing you to create relations called "relational databases" that link data together.
  
  - Uses a standard language called Structured Query Language (SQL) to store, manage, and access these databases.
  
    - Examples include Microsoft SQL Server, MySQL, etc.

- Network Time Protocol (NTP)
  
  - Synchronizes the time on devices, ensuring all system clocks are up-to-date.
  
  - Beneficial for processes such as comparing log files and using encryption technologies that require accurate system date and time.
  
  - NTP servers are often redundant and reference a central clock to maintain consistent configurations across servers.
  
  - Your local computer, whether it runs Windows, Linux, or another operating system (OS), will have an NTP client configured to periodically check and update the system’s date and time via an NTP server.

### Internet Appliances

- Spam Gateways
  
  - A filtering service that evaluates incoming emails to identify and separate legitimate emails from spam, phishing, or malicious emails.
  
    - Often deployed as a separate cloud service or independent system that scans email content, sender reputation, attachments, and embedded links.
  
    - Not always 100% accurate — sometimes legitimate emails can mistakenly end up in spam folders (false positives).
  
  - Helps reduce unwanted or potentially harmful emails, allowing users to focus on important and relevant communications.

- All-in-one Security Appliance
  
  - A comprehensive security device, often referred to as Unified Threat Management (UTM) or Web Security Gateway, placed at the network perimeter to protect internal networks from external threats.
  
  - Combines multiple security and network management functions into a single appliance, simplifying deployment and administration while providing broad protection.
  
  - Typical functions include:
  
    - URL filtering / content inspection – Blocks access to dangerous or inappropriate websites.
  
    - Malware inspection – Scans incoming and outgoing traffic for viruses, worms, and other malware.
  
    - Spam filtering – Blocks unsolicited or malicious emails.
    
    - CSU/DSU – Connects digital WAN lines (less common today but still used in some environments).
    
    - Router / switch – Provides basic routing and switching capabilities.
    
    - Firewall – Controls incoming and outgoing network traffic based on security rules.
    
    -  Intrusion Prevention/Detection System (IPS/IDS) – Detects and blocks network attacks and suspicious behavior.
    
    - Bandwidth shaping – Manages and prioritizes network traffic to optimize performance.
    
    - VPN endpoint – Allows secure remote access through Virtual Private Network connections.
    
    - Others – May also include SSL inspection, DLP (Data Loss Prevention), and more depending on the model.

- Load Balancer
 
  - A network device or software that distributes incoming traffic across multiple servers or resources to ensure no single server becomes overloaded.
 
  - Helps improve performance, prevent downtime, and optimize resource usage by sharing the workload evenly.
  
  - Commonly used for:

    - Web servers
    - Database servers
    - Application servers
  
  - Can perform health checks to detect if a server is down, and automatically reroute traffic to healthy servers (failover).
  
  - Types of load balancing methods include:
  
    - Round Robin – rotates requests evenly across servers.
  
    - Least Connections – directs traffic to the server with the fewest active connections.
  
    - IP Hash – routes based on the client’s IP address.

- Proxy Server
  
  - An intermediary server that sits between a client (such as a user's computer) and the internet, forwarding requests and responses.
  
  - Common functions include:
  
    - **Content filtering** – blocks access to certain websites or types of content based on organizational policies.
  
    - **Caching** – stores copies of frequently accessed web pages to speed up response times and reduce internet bandwidth usage.
  
    - **Anonymity** – hides the client’s real IP address, helping to protect privacy and security.
  
    - **Security** – can block malicious sites or monitor traffic for suspicious activity.
  
    - etc.
    
  - Types of proxies:
  
    - **Forward Proxy** – used by clients inside a network to access external resources.
  
    - **Reverse Proxy** – sits in front of web servers to handle incoming requests, often used for load balancing, caching, or security.
  
  - Often used in corporate environments, schools, and data centers.

- SCADA / ICS

  - SCADA stands for Supervisory Control and Data Acquisition. 

  - Large scale, multi-site Industrial Control System (ICS).

  - Both are used to monitor, manage, control, and automate operations remotely across the network. 
  
  - Often used in industrial operations such as:
  
    - Manufacturing
    - Power plants
    - Water treatment
    - Oil and gas pipelines
    - Transportation systems

  - SCADA / ICS systems collect real-time data from sensors, machines, and equipment, then display this data to operators who can monitor or control the system remotely.

    - Security is critical since these systems control critical infrastructure and can be targeted by cyberattacks. This is achieved by placing them on secured and segmented networks that can only be accessed physically or through highly controlled systems.

  - SCADA / ICS systems prioritize:
  
    - High availability
    - Real-time response
    - Safety and reliability

- Legacy and Embedded Systems

  - Legacy systems are older hardware or software still in use because they are stable, costly to replace, or critical for specific operations.

  - These systems may not support modern security features or updates, making them vulnerable to threats if not properly isolated or maintained.

  - Embedded systems are purpose-built computing systems designed to perform dedicated tasks within larger devices.

  - They often operate with limited computing resources, run specialized software, and are designed for long-term, stable operation.

  - Embedded systems are found in:
    - Industrial automation (PLCs, controllers)
    - Consumer electronics (smart TVs, appliances, cameras)
    - Automotive systems (engine control units, airbags, infotainment)
    - Healthcare equipment (monitors, pacemakers)

  - Both legacy and embedded systems can pose security risks if not properly isolated, maintained, or secured, since many were not designed with modern cybersecurity threats in mind.

- Internet of Things (IoT)

  - IoT refers to a network of physical devices connected to the internet that collect, exchange, and process data.

  - IoT devices include:

    - Smart home devices (e.g. thermostats, lights, locks)
    - Wearables (e.g. fitness trackers, smartwatches)
    - Industrial sensors
    - Smart city infrastructure

  - IoT devices often communicate remotely through cloud platforms, mobile apps, or management systems.

  - Security is a major concern due to the large number of devices, varying security standards, and the sensitive data being collected.

  - Proper network segmentation, firmware updates, and strong authentication can help secure IoT environments.

### 2.4 Explain common network configuration concepts

### DNS Configuration

- Recall: Domain Name System (DNS) is a well-known service that translates human-readable names in to computer-readable IP addresses, vice versa.

- DNS server's are distributed databases scattered all over the internet that stores all registered domain names on the world wide web.

  - Has 13 root server clusters (Over 1,000 actual servers)

  - These root clusters allows us to communicate with:
  
    - Hundreds of generic top-level domains (gTLDs) - .com, .org, .net., etc. and over 275 country 

    - Over 275 country code top-level domains (ccTLDs) - .us, .ca, .ph, .uk, etc.

- The DNS hierarchy

  - Allows us to have a systematic hierarchy to organize DNS infrastructures to make it sensible and accessible to worldwide.

  - Root Domain (.): The conceptual top of the DNS tree.

  - Top-Level Domains (TLDs): Directly below the root, these include familiar extensions like .com, .net, .edu, and .org.

  - Second-Level Domains (e.g., .professormesser): Registered names directly under a TLD.

  - Subdomains (e.g., www, live, mail, east, west): Further divisions under a second-level domain. These can be used to organize content or services (e.g., mail.professormesser.com).

  - Hosts/Entities (e.g., trey, katie, ethan, judy): The lowest level shown, representing specific devices or users within a subdomain.

```
. (Root Domain)
└─── .com
     ├─── .professormesser
     │    ├─── www
     │    ├─── live
     │    ├─── mail
     │    │    ├─── trey
     │    │    └─── katie
     │    ├─── east
     │    └─── west
     │         ├─── ethan
     │         └─── judy
     ├─── .net
     ├─── .edu
     └─── .org
```

- DNS lookup

  - Tools might be necessary to help you gather insights on how a specific DNS server is configured.

  - Dig command

    - A common tool for Linux and MacOS, some Windows versions might have an installable version of dig, that allows you perform a query against a DNS server.

    - dig (Domain Information Groper)

    - A command-line tool used to query DNS servers directly.
    
    - Mainly used by network admins and IT professionals to troubleshoot DNS issues, check DNS records, and verify domain configurations.

    - dig gives detailed output including:

      - DNS response codes
      - Query times
      - Individual record details (A, AAAA, MX, NS, TXT, etc.)
      - Full DNS server responses

    - Syntax example:  

      - dig google.com
      - dig google.com MX

    - Often preferred over nslookup because it provides more detailed and modern output.

```
dig professormesser.com

; <<>> DiG 9.18.30-0ubuntu0.24.04.2-Ubuntu <<>> professormesser.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 27716
;; flags: qr rd ra; QUERY: 1, ANSWER: 3, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;professormesser.com.           IN      A

;; ANSWER SECTION:
professormesser.com.    300     IN      A       172.67.41.114
professormesser.com.    300     IN      A       104.22.73.108
professormesser.com.    300     IN      A       104.22.72.108

;; Query time: 56 msec
;; SERVER: 10.255.255.254#53(10.255.255.254) (UDP)
;; WHEN: Thu Jun 12 23:14:12 CST 2025
;; MSG SIZE  rcvd: 96
```

  - nslookup (Name Server Lookup)

    - Another command-line tool used to query DNS servers.

    - Commonly used for quick DNS lookups and basic troubleshooting.

    - Can retrieve:
      - IP addresses for domain names
      - DNS record information (A, MX, NS, etc.)

    - Syntax example:
      - nslookup google.com

    - Simpler and more widely available across different systems, but not as detailed as dig.

```
nslookup professormesser.com

Server:         10.255.255.254
Address:        10.255.255.254#53

Non-authoritative answer:
Name:   professormesser.com
Address: 172.67.41.114
Name:   professormesser.com
Address: 104.22.73.108
Name:   professormesser.com
Address: 104.22.72.108
```

- DNS Records

  - Queries that are performed against DNS servers returns information which are obtained from DNS records called resource records (RR).

  - Resource records contains over 30 record types:

    - IP addresses
    - Certifications
    - Host alias names
    - etc.

   - These DNS configurations are critical making one mistake cause these devices to be suddenly unavailable to the internet.

   - Make sure to make backups to prevent problems.

- DNS Configuration

  - DNS server configurations can be modified via the raw configuration file or via a web-based interface that can be easily viewed, modified, and managed by an administrator.

  - Address records (A)(AAAA)

    - Defines the IP address for a specific host name.

    - A Record (Address Record) - records for IPv4 addresses

      - Maps a domain name to an IPv4 address.
      - Example: google.com → 142.250.190.14

    - AAAA Record (IPv6 Address Record) - records for IPv6 addresses

      - Can also be called Quad A record
      - Maps a domain name to an IPv6 address.
      - Example: google.com → 2607:f8b0:4009:80b::200e

  - Time to Live (TTL) - Extra Info

    - TTL is a value in DNS records that tells how long the information should be cached by DNS servers and clients before they check for updated data. It’s measured in seconds.

    - Example: TTL = 3600 → cache the record for 1 hour.

    - Why TTL matters:

      - **Lower TTL** means faster updates (good for frequently changing records), but causes more DNS lookups, which can slightly increase traffic.
      
      - **Higher TTL** means fewer lookups and better performance, but changes take longer to propagate if you update the DNS record.

    - TTL is set when you configure your DNS records in your DNS management system.

  - Canonical name records (CNAME)

    - A DNS record used to assign alias for addressing different names. Useful for multi-functional servers with different services under a single name.

    - Example:

      - www.example.com has a CNAME pointing to example.com.

      - Then example.com resolves to an A record with IP 93.184.216.34.

      - 3600 is the TTL (time to live) in seconds.

```
dig www.example.com CNAME

; <<>> DiG 9.16.1-Ubuntu <<>> www.example.com CNAME
;; ANSWER SECTION:
www.example.com.   3600   IN   CNAME   example.com.
example.com.       3600   IN   A       93.184.216.34
```

  - MX (Mail Exchanger Record)

    - MX records define which mail servers are responsible for receiving email for a domain.

    - Each MX record has:

      - **Priority value** (lower value = higher priority)
      - **Mail server hostname** (FQDN) - example: mail1
      
      > A Fully Qualified Domain Name (FQDN) is the complete, specific address of a host on the internet

    - When someone sends an email to your domain, their mail server looks up your MX records to know where to deliver the message.

    - MX records do not contain IP addresses directly; they point to hostnames, which are resolved via A or AAAA records.

    - MX records are configured through your DNS management panel.

    - Example MX records for example.com:
    
      - Priority: 10, Mail server: mail1.example.com
      - Priority: 20, Mail server: mail2.example.com

      - mail1.example.com is the primary server.
      - If mail1 is unavailable, mail2 will handle the email.

  - TXT (Text Record)

    - TXT records allow domain owners to store any text information in DNS.

    - Originally made for human-readable notes but now heavily used for email security and domain verification.

    - Common uses:

      - **SPF (Sender Policy Framework)**

        - Helps prevent spammers and spoofing emails from pretending to be from your domain.
        
        - Lists authorized servers allowed to send email on behalf of your domain.
        
        - Email servers check this record to verify if the sending server is legitimate.
        
        - Example:
          - "v=spf1 include:_spf.google.com ~all"

      - **DKIM (DomainKeys Identified Mail)**

        - Adds a digital signature to outgoing emails.
        
        - The public key for verifying these signatures is stored in a TXT record.
        
        - Receiving servers verify that the message hasn’t been altered and that it truly came from your domain.
        
        - Example:
          - "v=DKIM1; k=rsa; p=MIGfMA0GCSq..."

      - **DMARC (Domain-based Message Authentication, Reporting, and Conformance)**
        
        - Works together with SPF and DKIM.
        
        - Tells receiving servers what to do if an email fails authentication (e.g. reject, quarantine, or allow).
        
        - Can also send reports to the domain owner about email authentication activity.
        
        - Example:
          - "v=DMARC1; p=reject; rua=mailto:dmarc-reports@example.com"

      - **Domain Verification**
        
        - Used by cloud services (Google, Microsoft 365, etc.) to verify domain ownership.
        
        - Usually done by placing a special code in a TXT record.
        
        - Example:
          - "google-site-verification=abc123"

      - **Other Custom Configurations**
        
        - Some services store custom configuration settings, API keys, or other metadata in TXT records.
        
        - Depends on the service's specific needs.

    - Syntax:
      
      - TXT records are entered as plain text strings inside your DNS management system.
      
      - Multiple TXT records can exist for a single domain.

    - Sample commands usage:

      - dig professormesser.com txt
      - nslookup -type=txt professormesser.com

- DHCP Configuration

  - Recall: DHCP automatically assigns IP addresses and network settings to devices on a network.

  - Common settings given: IP address, subnet mask, gateway, DNS servers.

  - DORA Process (DHCP 4-step process)

    1. **Discover** — Client broadcasts looking for DHCP servers. Usually broadcasted (255.255.255.255:udp/67) under the address (0.0.0.0:udp/68)
    2. **Offer** — Server responds with an available IP address.
    3. **Request** — Client requests to accept the offered IP.
    4. **Acknowledge** — Server confirms and assigns the IP to the client.
  
  - Leases

    - Devices leases an IP addresses which are assigned temporarily by the DHCP server.
    
    - The lease has an expiration time in which clients has renew leases before they expire to keep the IP.

  - Reservations

    - There are instances where an admin needs to assign a fixed IP to a device based on its MAC address, often for mission-critical devices that require a stable IP address.
    
    - The device will always receive the same IP when requesting DHCP from the network.

    - Other names:

      - Static DHCP assignment
      - Static DHCP
      - IP reservation

  - Exclusions

    - Unlike reservations (where IPs are still managed by DHCP), exclusions completely block certain IP addresses from being assigned to any device.

    - Used to prevent DHCP from handing out specific IPs, usually because those IPs are manually assigned elsewhere to static devices like servers or printers, to avoid conflicts.

    - Example: Exclude 192.168.1.100 if it’s manually assigned to a static server.

  - DHCP Scope 

    - It refers to the pre-configured pool of IP addresses (and related network settings) that DHCP can hand out to devices including excluded and reserved IP addresses.

      - These pool of addresses that are configured to be automaticall assigned are also known as DHCP pool.

    - Scope defines *what* the DHCP server can assign for a specific network.
    
    - Example: 192.168.1.100 to 192.168.1.200.

    - Other network settings included:

      - Subnet mask
      - Lease duration
      - DNS server
      - Default gateway
      - etc.

- LAN (Local Area Network)

  - A network of devices within a limited area (office, building, home, etc.).

  - By default, all devices in the same LAN are part of the **same broadcast domain**.

  - A broadcast domain means:

    - Broadcast messages (like ARP requests) are received by all devices within that LAN.

- VLAN (Virtual LAN)

  - An efficient way to break up a single LAN into multiple virtual networks (VLAN).

  - Even though devices are physically connected to the same switch, VLANs separate them logically, making it efficient and cost-effective without having to buy another switch!

  - Each VLAN is its own **separate broadcast domain**. Devices in one VLAN do not see broadcasts from other VLANs.

- VPN (Virtual Private Network)

  - A network device that adds a layer of security by encrypting (private) data traversing a public network.

    - VPN Encryption Process

      - Encryption ensures data cannot be read by anyone except the intended parties.

      - Secures data from unwanted parties like hackers.

      - VPN uses protocols like IPsec, SSL/TLS to create a secure tunnel.

  - Can be built-in to the system or can be a third party software.
  
  - VPN Concentrator

    - A specialized device (or software) that manages many VPN connections at once.
    
    - Handles encryption, authentication, and traffic for multiple users or sites.
    
    - Often integrated into a VPN firewall or other purpose-built devices.
    
    - Acts as a central hub for VPN traffic.

  - VPN Types:

    - Client-to-Site VPN (Remote Access VPN)

      - A single user connects securely to a company network over the internet, often used by remote workers.
      
      - Requires VPN client software on the user's device to initiate the connection.

      - The encrypted data from the client is sent over the internet and decrypted by the VPN concentrator (or VPN gateway) at the company network.

      - Can be configured as always-on, automatically connecting when the device powers up or connects to any network.

      - Example: A worker accessing company resources (files, applications, intranet) remotely.

    - Site-to-Site VPN

      - Connects two entire networks together over the internet; commonly used to link multiple office locations.

      - Usually set up on routers, firewalls, or dedicated VPN appliances. Some Unified Threat Management (UTM) devices can also handle site-to-site VPNs.

      - The VPN concentrator function is usually integrated into the network devices at both sites, so no separate client software is needed on individual devices.

      - Example: The head office network connected securely to a branch office network.

### 2.5 Compare and contrast common networking hardware devices

- Normally, on network enterprise you would encounter many network racks containing several devices, each having its own networking functionality or role.

- These networking functions can be standalone or have several functionalities built-in to a single device. Some of these functionalities include:

  - Routing
  - Switching
  - Firewall
  - etc.

- Router

  - A layer 3 device that connects different networks together and makes forwarding decisions based on the IP destination of an IP packet.

    - Keeps a routing table that helps it decide the best path for data to travel.

  - Routers would also sometimes have switching capabilities. This multi-functional device is called a layer switch.

  - Can also have other functionalities like:

    - NAT (Network Address Translation)
    - Firewall features
    - DHCP server
    - VPN support

  - Routers connects diverse network types including:

    - LAN
    - WAN
    - Copper
    - Fiber
    - etc. 

- Switches

  - An intelligent networking device mainly used in wired networks. It acts as a central connection point, allowing devices to communicate with each other.

  - Primarily makes forwarding decisions based on **MAC addresses**, unlike routers which use **IP addresses** for routing decisions.

  - Contains an **application-specific integrated circuit (ASIC)** that enables high-speed and efficient forwarding of network traffic.

  - May have several to hundreds of port interfaces for devices to connect to, depending on the switch type.

    - Some switches provide **Power over Ethernet (PoE)** functionality, allowing the same cable to deliver both power and network connectivity to devices.

  - Some switches may also support additional networking functions such as routing, making them **Layer 3 switches** or **multilayer switches**.

  - 2 Types of Switches

    - Managed Switches

      - Allow full configuration and control over network traffic using a simple network management protocol (SNMP) which enables performance monitoring, fault detection, and remote management.
      
      - Support features like VLANs, QoS, port security, SNMP monitoring, and remote management.
      
      - Used in enterprise or larger networks where advanced control is needed.

    - Unmanaged Switches

      - Basic plug-and-play devices with no configuration options.
      
      - Simply forward traffic between connected devices.
      
      - Used in small networks or home setups where advanced features aren’t necessary.

      - Significantly cheaper compared to managed switches

- Access Point (AP) or Wireless Access Point (WAP)

  - A device that allows wireless devices (laptops, phones, tablets) to connect to a wired network.

  - Acts as a bridge between wireless devices and the wired LAN.

  - Connects to the network using an Ethernet cable and provides Wi-Fi signal to nearby wireless devices.

  - Also makes forwarding decisions based on MAC address.

  - In large networks, multiple access points are used to provide full wireless coverage.

  - Often managed centrally by a wireless controller in enterprise networks.

- Cable infrastructure

  - Refers to the physical cabling used to connect devices in a network (computers, switches, routers, servers).

  - Enterprise networks would usually have company devices connected to a network closet via a wired connection.

  - These wired connections are often "punched down" into a block using a punch down tool, securing the wire and cutting off excess, simplifying wire management.

  - Normally it would have extra interfaces available for extra devices to connect to. It is interchangeable unlike punched down cables which are fixed.

  - Common types: twisted-pair cables (Cat5e, Cat6, Cat6a), fiber optics, coaxial cables.

  - Includes:
    - Patch panels
    - Wall jacks
    - Patch cords
    - Cable trays and management systems

- Patch Panel

  - A central point where network cables from different areas are terminated.
  
  - Provides a clean, organized way to manage and rearrange network connections.
  
  - Cables are permanently punched down into the back, while short patch cables connect the front ports (usually RJ45 connectors) to network equipment like switches.

  - Benefits:

    - Keeps cabling organized and neat.
    
    - Makes it easy to reconfigure connections without touching permanent cabling.
    
    - Simplifies troubleshooting and maintenance.
    
    - Protects the permanent cabling from wear since only patch cords are handled regularly.

    - Good for extending network functionalties.

- Firewall

  - A device or software that monitors and controls incoming and outgoing network traffic.
  
    - Enforces security policies to allow or block traffic based on rules.
  
    - Some modern firewalls (next-generation) can filter based on the application. 

  - Can be hardware-based, software-based, or both.
  
  - Protects the network from unauthorized access, malware, and other threats.

  - Can also have other networking functionalties:

    - Routing
    - VPN concentrator
    - Proxy

- Power over Ethernet (PoE)

  - A technology that allows network cables (Ethernet) to carry both data and electrical power.
  
  - Used to power devices like IP cameras, wireless access points, VoIP phones without needing separate power cables. Useful in difficult-to-power areas.
  
  - Simplifies installation and reduces cabling.

  - PoE Types:

    - PoE (IEEE 802.3af)

      - Supplies up to **15.4 watts** of power per port.
      
      - Used for low-power devices like VoIP phones and some wireless access points.

    - PoE+ (IEEE 802.3at)

      - Supplies up to **25.5 watts** of power per port.
      
      - Supports devices that need more power like modern access points, cameras, or video phones.

    - PoE++ (IEEE 802.3bt)

      - Two types:

        - **Type 3**: Up to **60 watts** per port.
        - **Type 4**: Up to **100 watts** per port.

      - Supports high-power devices like PTZ cameras, LED lighting, large access points, or even thin clients.

- PoE Injector

  - A small device that adds electrical power to the Ethernet cable for devices that support Power over Ethernet (PoE).

  - Used when your switch or network equipment doesn’t support native PoE.

  - How it works:
    
    - The network cable from the switch/router connects to the injector's data input port.
    
    - The injector combines data and power.
    
    - The output port sends both data and power over one cable to the PoE device.

  - Useful for powering PoE devices without replacing non-PoE switches.

- Cable Modem

  - Provides internet access over **coaxial cable** (same cable used for cable TV).
  
  - Connects to the Internet Service Provider (ISP) through the cable network infrastructure.
  
  - Uses **DOCSIS (Data Over Cable Service Interface Specification)** standard for communicating.
  
  - Usually offers higher speeds compared to DSL due to wider bandwidth availability.

  - Supports different data types: voice, video, data.

- DSL (Digital Subscriber Line)

  - Provides internet access over **standard telephone lines (twisted pair copper)**.
  
  - Unlike dial-up, DSL allows simultaneous phone and internet use.
  
  - Has limited speed and distance:
    
    - The farther you are from the ISP’s central office (CO), the slower and weaker the signal.
  
  - Two main types:

    - **ADSL (Asymmetric DSL)**: faster download, slower upload.
    
    - **VDSL (Very-high-bit-rate DSL)**: faster but works best over short distances.

- Optical Network Terminal (ONT)

  - A device used in fiber-optic internet connections, connecting the ISP fiber networks to copper networks.

    - Supports Fiber-to-the-premises (FTTP) and Fiber-to-the-home (FTTH) / Copper-to-the-home (CTTH).
  
  - Converts fiber-optic signals into Ethernet for use by home or business networks.
  
  -  Usally located on a demarcation point (demarc). Can either be in a data center or a terminal box around the area.

    - The demarcation point is where the ISP’s network ends and your network begins.  
    
    - The ISP is responsible up to that point; you handle everything after it.

- Network Interface Card (NIC)

  - A hardware component that allows a device to connect to a network.
  
  - Can be wired (Ethernet NIC) or wireless (Wi-Fi NIC).
  
  - Responsible for handling physical and data link layer communication.

    - Contains a Media Access Control (MAC) address which is a unique hardware designation specific for your device.
  
  - Often built into modern computers (motherboard), servers, and other networked devices, while some are modular components such as expansion cards.

### 2.6 Given a scenario, configure basic wired/wireless small office/home office (SOHO) networks

### WORK IN PROGRESS...