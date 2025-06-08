# CompTIA A+ Core 1 (220-1201)

The content for this material is based from the [Official CompTIA A+ 220-1201 Exam Objectives](https://partners.comptia.org/docs/default-source/resources/comptia-a-220-1201-exam-objectives-(2-0)). These objectives serve as a comprehensive guide to the topics covered in the certification exam, including hardware, networking, mobile devices, virtualization, cloud computing, and troubleshooting.

## 1.0 Mobile Devices

### 1.1 Given a scenario, monitor mobile device hardware and use appropriate replacement techniques.

### Laptop Hardware

- A standard computing platform built to be compact and portable for anyone who is mobile.

- Laptop has a small trade-off when it comes to troubleshooting as it is built at a very precised specification requiring very specific form of troubleshooting. This often depends on its manufacturer and design.

    - Some laptops are engineered to be repaired and replaced easily, often designed with modular components that can be accessed with ease. 
    - On the contrary, other laptops designs are harder to access making it hard to troubleshoot and repair. These are often difficult to access primarily due to space constraints and design choices made to fit more functionality into a smaller form factor.

> Form factor refers to the size, shape, and layout of a component, like a motherboard, hard drive, or case.

- Since laptops are design in various manners, laptop manufactures will have different processes when it comes to managing and troubleshooting these devices.

### Laptop Batteries

- Laptop batteries is the main power source of the laptop, allowing it to operate independently without needing a power outlet, providing power when not plugged in or acting as a backup power source.

- Manufacturers often design laptops to have modular batteries that can be easily swapped with another battery, while others will have its battery built in to the system, thus removing its modularity.

    - Modular batteries are usually plug and play, thus making it easy to swap directly.

    - Non-modular batteries usually requires a technician to completely replace the battery.

- **2 types of batteries**
    
    - Lithium-Ion (Li-ion)

        - Offer higher energy density (more power for their size) and high discharge rate
        - Longer lifespan
        - Less expensive (cost-effective)

    - Lithium-Ion Polymer (LiPo)

        - Offer higher energy density (more power for their size) and high discharge rate
        - More flexible, lightweight, and smaller compared to Li-ion.
        - A bit more expensive that Li-ion.

    - Both are designed to mitigate its old memory effect with older batteries, thus allowing us recharge the battery without affecting its capacity.

    - Not all laptops have a similar battery form factor (design), thus requiring its user to carefully choose the appropriate battery compatible for their laptop when purchasing one.

### Laptop Keybaord

- Designed to become compact due to the laptop's small form factor.

- Due to its compact nature, laptop keyboards have a more compact layout compared to desktop keyboards and are often paired with special keys that can access seconary functions.

- Most commonly used component in a laptop. Also is the most commonly swapped component, according to  Professor Messer.

- Laptop keyboards can be detached by removing a bezel or a few screws, and disconnecting the ribbon connected to it underneath. Just simply reverse the process to reconnect.

    - You may plug in an external keyboard to diagnose if the problem is associated with the operating system or the hardware itself.

- Desktop keyboards are built to be robust making it easy to remove and replace. However, in laptop keyboards, key caps are very fragile and must be handled with care.

### Laptop Memory

- Unlike the traditional Random Access Memory (RAM) found in Desktops, laptops use a smaller memory form factor such as the **Small Outline Dual In-line Memory Module (SO-DIMM)**.

- Just like the other components, SO-DIMM also provides modularity to its users, often making it easy to replace if you want to upgrade your RAM, while some are sodered in to the system making it impossible to upgrade or replace thus requiring a full system board replacement/upgrade.

    - Modular SO-DIMM's are usually located at the bottom of your laptop. Just unscrew its cover and locate its memory slot if you want to replace it.

### Laptop Storage

- Traditional laptops often uses a magnetic or spinning disk, also known as Hard Drives (HDD). 

    - 2.5 inch form factor for laptops.
    - 3.5 inch form factor for desktops.

- More modern laptops would use a faster storage device known as the Solid-state Drive (SDD).

    - No moving parts (spinning disk) thus making it more reliable as we no longer have to worry about the spinning disk failing.
    - Silent, fast access time, less latency
    - 2.5 inch form factor

- Other laptops with a more compact form factor would use a smaller storage form factor known as M.2 storage.

    - No SATA data or power cables, making it easy to install and replace.

- Just like SO-DIMM, just remove the cover at the back. Unscrew the storage device and slide it in.

### Migrating from HDD to SSD

- Migrating from HDD to SSD will make your laptop significantly more faster.

- You can manually transfer your data by copying it over the the new storage device, but this is time consuming.

- A more easier way is to use an imaging software allowing us to make an exact duplicate of the data to the new one. 

    - Some SSD's have an imaging software included.

### Network Connection

- Laptop have 802.11 for internet access over the local area network (LAN) and Bluetooth short range connections with other nearby devices over the personal area network (PAN) integrated into the system.

- Older systems would integrate these networking capabilities in Peripheral Component Interconnect (PCI) components offering expansion cards that allows additional functionality to the system (e.g., network and sound cards).

    - Some common PCI components are the Mini-PCI and Mini PCI Express (PCIe) which are both older standards for adding internal cards to laptops. 
    - Mini-PCIe is generally the more modern and preferred option due to its higher speed, smaller size, and imporved signal quality.

- Newer systems would have these features integrated into the system.

- Installing this component is also very similar to the other components but make sure to connect the wireless antenna wires, often grey and black, to the small connectors: WiFi (main), Sound (aux), and bluetooth.

- These antenna wires are wrapped around the laptop screen coming through behind your keyboard to the system board itself connecting to the PCI component.

### Authentication / Biometrics

- Modern laptop softwares will usually have a built-in biometric system for added security.

    - Fingerprint scanning
    - Face recognition
    - Voice recognition
    - Iris scanning
    - etc.

- In Windows you can find this at **Windows settings > Accounts > Sign-in options**

### Near Field Communication (NFC)

- A short range networking function allowing data transfers or authentication (with encryption support). 

- Common on mobile devices and smart watches. Might also see them on Identification Cards (ID) nowadays.

### Camera / Webcam and Microphone

- A video capturing device built-in to laptops located at the top of the screen. This also comes along with a built-in micorphone which are commonly located at the sides of the webcam.

- These devices provide audio and video capabilities to your laptop which can be used for activities like audio and video conferencing.

### 1.2 Compare and contrast accessories and connectivity options for mobile devices.

### Connecting Mobile Devices

- With the variety of devices at our disposal, we need to have a way to connect these devices in the network or with other devices.

    - This can be wired or wireless connections. These connections are often designed with specific standards and specifications.
    - These devices are more than just connectivity devices. They also provide other functionalities: synchronization, backup, identification, etc.

- Universal Serial Bus (USB)

    - High-speed wired communication often used for charging and data transfers.

    - Mini-USB

        - These are smaller versions of the USB which is commonly known worldwide. Comes with different variations:

        - Common with older devices:

            - Micro B Plug
            - Mini B Plug
            - Type A Plug

        - Common with newer devices:

            - USB-C

                - A 24-pin double-sided USB connecter that can be used for both hosts and devices. It is designed to be a connector where you can be plugged in at any orientations and also supports higher speed connections.

                - Replaces the older versions of USB connections up to latest standard of USB.
                
                - Can be used for different forms of signals:

                    - Serial Connectivity
                    - Display Port
                    - HDMI
                    - Thunderbolt

            - Lightning Connector

                - An 8-pin proprietary lightning connector built for apple devices.
                - Has a much more simpler deisgn and has better support in power output compared to micro-USB's and can also be inserted in any orientation.

- Since we have many variety of connectors that only supports certain devices, we might need to use a connector designed to support other connections to make it compatible with each other, such as a hub connector or female connector.

- Bluetooth

    - A high speed commmunication allowing different types of devices to connect with each other over short distances (Personal Area Network [PAN]).

- Hotstop / Tethering

    - A feature that allows to convert your device in to a peronal wireless router to extend wireless connectivity to surrounding devices.
    
    - This feature is integrated to your system software and will usually require a network provider, like a SIM card, for your phone to be able to have access to cellular data and share it with other devices. 

### 1.2 Compare and Contrast Accessories and Connectivity Options for Mobile Devices

### Accessories for Mobile Devices

- **Touch pens**  
    - Also called touchscreen pens, capacitive styluses, or just styluses, these are used for note-taking, signing digital documents, or tapping UI elements with more precision than a finger.

    - **Active stylus**  
        - Also known as a digital stylus, this is primarily designed for artists or users who require pressure sensitivity and palm rejection. It often includes programmable buttons and can detect hovering above the screen. These are usually device-specific—for example, the Apple Pencil only works with iPads.

- **Headsets**  
    - These allow audio input and output and can connect via Bluetooth (wireless), USB, Lightning (for Apple devices), or a 3.5mm TRRS analog audio jack. The TRRS jack enables simultaneous transmission of microphone input and headphone output, making it suitable for calls and meetings.

- **Speakers**  
    - External speakers provide stereo sound output and often run on rechargeable lithium-ion batteries, just like many other external accessories including headsets, phones, and external trackpads.

- **Webcam**  
    - Used for capturing video and images, webcams are built into laptops, tablets, and phones but can also be connected externally to desktop computers for video conferencing and recording.

- **Docking station**  
    - A device that allows quick connection to multiple peripherals (e.g., printers, monitors, keyboards, mice) by connecting the laptop to a single port. Some models support adapter cards for added hardware functionality.

- **Port replicator**  
    - Works like a docking station but connects through a USB cable rather than docking the laptop. It is smaller and typically does not support adapter cards. Useful for users with limited ports (e.g., USB-C-only MacBooks) who need access to HDMI, Ethernet, or USB-A ports.

- **Trackpad**  
    - Replaces the mouse on laptops and can also be used externally (e.g., Apple’s Magic Trackpad). Some laptops allow disabling the trackpad using a function key to avoid accidental touches while typing.

- **Drawing pad**  
    - An external input device (e.g., Wacom tablet) that adds touchscreen capabilities to non-touch laptops. It combines a digitizer with an active stylus and is useful for artists and designers needing precise control, typically supporting multiple operating systems.

### Mobile Device Networks

- Mobile devices, also referred to as Cellphones, were derived from the term "cell" which comes from cellular networks.

- Cellular networks, also known as mobile networks, are wireless telecommunication networks that allows utilizes antennas or base stations (cell towers) to provide wireless connectivity to our devices.

    - Allows voice and data communication and can be enabled through your settings with ease.
    - You can also disable all forms of communication by enabling airplane mode.

- 3G Technology

    - This wireless technology was introduced in 1988.
    
    - Allows our mobile devices to send large amounts of data over the network, thus increasing its overall capabilities. Some of these capabilitiesa are:

        - Global Positioning System (GPS)
        - Mobile Television
        - Video on demand
        - Video conferencing
        - etc.

- 4G and Long Term Evolution (LTE)

    - The successor of 3G technology, which is based on the Global System for Mobile Communication (GSM) network, also known as Enhanced Data Rates for GSM Evolution (EDGE).

    - Additionally, it is a converged standard, so providers that used to be GSM or CDMA could now use one standard LTE to be able to send data over a wireless network as GSM and CDMA posed challenges for users who wanted to move between providers or use different networks available in their area

    - Supports faster download rates of 150 Mbit/s

    - Long Term Evolution Advanced (LTE-A)

        - Some areas may support LTE-A which is an improved version of LTE, as the name suggests.

        - Supports an even faster download rate of 300 Mbit/s.

- 5G Technology

    - A modern technology, launched on 2020, that supports higher frequencies and faster rates up to 10 gigabits/s. 

    - Can run up to 100-900 Mbit/s on other networks and frequencies, on slower speeds.

    - Due to higher bandwidth support, we can now support Internet of Things (IoT). This also allows us to receive notifications and upload large amounts of data in to the cloud faster. 
    
- WiFi (802.11)

    - 802.11 provides wireless connectivity whenever cellular networks are slow or unavailable.

    - Unlike Cellular networks that uses big carrier-owned towers that blanket large areas, Wi-Fi (IEEE 802.11) uses small access points or home/office routers that cover only a room, house, or building.

    - Cell towers can follow you for kilometers; Wi-Fi drops off after ~30-90 m indoors (walls cut it even shorter).

    - Cell uses licensed frequencies your provider pays for; Wi-Fi uses unlicensed 2.4 GHz/5 GHz/6 GHz bands anyone can deploy.

    - Once you’re on either network it’s just IP packets, so voice (VoIP), video streaming, file transfers—no problem on 802.11 as long as the signal’s solid and the LAN/Internet uplink can handle it.

    - Cellular networks build in QoS and seamless hand-offs between towers. Wi-Fi usually doesn’t, so congestion or roaming between APs can hurt performance.

- Hotspot

    - Enabling this feature converts your mobile devices in to a personal wireless router extending cellular connectivity to its surrounding devices over 802.11.

    - This requires you to have a mobile carrier, which provides cellular connectivity through a subscription or data plan, allowing your device to access the internet and other mobile services.

- Subscriber Identity Module (SIM)

    - It is a small physical card instlled or sometimes embedded in to your system and is used as an identifier so mobile carriers can recognize your device.

    - Contains information that can be used to identify your phone:

        - SIM ID and phone number
        
        - Cellular network information
        
        - Storage space for contacts, messages, etc.

    - Embedded SIM (eSIM)

        - An eSIM (embedded SIM) is a modernized digital version of a physical SIM card embedded in to your system. Instead of inserting a physical SIM into your phone, the eSIM is built into the device and can be programmed remotely by your mobile carrier.

        - Makes transferring profiles much easier via software; eliminates the manual removal of SIM cards with the use of a SIM ejector.

    - Many devices nowadays supports multiple SIMs.

- Bluetooth Pairing Process

    - Enable Bluetooth via phone settings.

    - Enable pairing mode. It is a security feature that lets you approve devices before connecting.

    - Bluetooth is a one-time setup. Pairing is only needed once; future connections should happen automatically.

    - Make the device discoverable which is usually done by pressing/holding a button; check the device manual for exact steps.

    - Search for devices on your phone, scan for nearby Bluetooth devices.

    - Enter the PIN code, often "0000" or "1234" by default, or verify the PIN displayed on the screen.

    - Test the connection and ensure the device is working as expected (e.g., audio, data transfer).

- Location Services

    - These services are used for geotracking in apps like Maps.

    - Global Positioning System (GPS) – Satellite-based navigation system.

        - Over 30 satellites in orbit, developed by the U.S. Department of Defense (DoD).

        - Phone must connect to at least 4 satellites to calculate a precise location.
        
        - Determines latitude, longitude, and altitude by measuring time differences in satellite signals.
    
    - Cellular & Wi-Fi Location Services 
        
        - Phones can also use nearby cell towers and Wi-Fi signals to improve accuracy (triangulation, similar to how calls can be traced).

### Mobile Device Management

- Mobile Device Manager/Management (MDM)

    - A centralized management system for managing devices, such as in a company.

- Bring Your Own Device (BYOD)

    - Allows you to bring your own personal device to use at work. Beneficial so that workers won't have to bring two separate devices at work.

    - Might require a specialized function to secure how company data is handled within those devices. An MDM can help by modifying the device's capabilites and implement security policies, remotely, such as requiring biometrics and backup plans in case the device got stolen or lost.

    - Device managers can parition a device to segregate company data with personal data.

- Corporate Owned Personally Enabled (COPE)

    - A company-owned device specifically purchased for worker consumption and is under full control of the company via a management system.

    - Similar to BYOD, company data is also protected by including corporate policies in case these devices are lost, broken, or stolen.

        - Information can be deleted at any time.

    - Can be utilized for both personal and professional reasons. 

- Choose Your Own Device (CYOD)

    - Users or workers can choose the type of device they can use for work.

- MDM Policy Enforcement

    - Having your device managed by a central MDM policy can be efficient by simplifying the process as you can manage and pre-configure everything from the device without having to do anything, such as:

        - Corporate email configuration

        - Account details
        
        - Server address
        
        - Communication method

        - Application configurations/synchronizations

        - Security Policies

            - Two-Factor Authentication
            - Biometrics
            - Backup
            - etc.
        
        - Corporate Applications
            
            - Allow or restrict applications
            - Prevent unauthorized app usage
        
        - Data Synchronization
            
            - You may configure how data are synchronized to these devices, WiFi or Cellular Data, such as calendar settings and contact details.

            - Can also configure how data are restored when the device got lost, stolen, or damaged.

            - Can be beneficial for resource management (data caps and transfer cost).
   
                - Limit data consumption

### Go to the next part - [2.0 Networking](./Networking.md)