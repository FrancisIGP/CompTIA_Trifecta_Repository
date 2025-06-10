# CompTIA A+ Core 1 (220-1201)

The content for this material is based from the [Official CompTIA A+ 220-1201 Exam Objectives](https://partners.comptia.org/docs/default-source/resources/comptia-a-220-1201-exam-objectives-(2-0)). These objectives serve as a comprehensive guide to the topics covered in the certification exam, including hardware, networking, mobile devices, virtualization, cloud computing, and troubleshooting.

## 2.0 Networking

### 2.1 Compare and contrast Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) ports, protocols, and their purposes.

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

Here's an elaborated and corrected version to clarify and fix common misconceptions about frequencies, channels, and bandwidth in wireless networks:

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

### WORK IN PROGRESS...