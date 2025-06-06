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

## Connecting Mobile Devices

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

### WORK IN PROGRESS...