# Intro to LAN — Topologies, Switch, Router, Subnetting, ARP and DHCP

**TryHackMe · Pre Security 0 · Network Fundamentals**  
**Medium:** *Coming soon*

`#Networking` `#LAN` `#TryHackMe` `#CyberSecurity` `#BlueTeam`

---

Over the years, many different network designs have been tested and applied. In networking, the term "topology" refers to the design or appearance of an existing network.

There are multiple network topologies — in this room I learned about three of them.

---

## 1. Star Topology

The main idea behind star topology is that devices connect individually through a central switch or network device. It's the most commonly encountered topology when it comes to scalability and reliability.

In this topology, any data sent to a device is sent through the central device it's connected to.

**Advantages:**
- More scalable — if demand on the network increases, it's easy to add more devices

**Disadvantages:**
- Requires more cables and dedicated network equipment, making it more expensive than others
- The more the network scales, the more maintenance it requires to keep it functional — troubleshooting becomes harder and more costly
- If the central device fails, all data flow can stop — though these central devices are usually more powerful and reliable

---

## 2. Bus Topology

Bus topology consists of a single cable — all devices connect to that one cable. It looks like the leaves of a tree, with devices branching off the central cable on both sides.

**Advantages:**
- More cost-efficient — less equipment and cabling required

**Disadvantages:**
- Since every device receives all data through the same cable, if multiple devices request data at the same time, it quickly leads to slowdowns and bottlenecks
- Because all data travels along a single route, it's difficult to identify which device is causing a problem
- A single point of failure — if the cable has one fault, all data flow stops and the entire network goes down

---

## 3. Ring Topology

In ring topology, devices like computers connect to each other forming a loop. This means less cabling and less dependency on dedicated hardware like in star topology.

Because data travels in only one direction, it's easier to troubleshoot any faults that occur. But this is a double-edged sword — data has to pass through multiple devices before reaching its destination, which makes it an inefficient way to transfer data across the network.

Ring topology is less prone to bottlenecks compared to bus topology, since a large amount of traffic doesn't move through the network simultaneously. The weak point is a faulty cable or broken device — if either happens, data flow stops and the entire network goes down.

---

## What is a Switch?

A switch is a dedicated network device designed to connect computers, printers, and many other devices that can connect to a network via Ethernet. These devices plug into switch ports.

Switches are commonly used in environments where many devices need to connect to a network — schools, businesses, and other large-scale networks. They can have 4, 8, 16, 24, 32, or 64 ports.

Switches are more efficient than simpler devices like hubs or repeaters. A switch remembers which device is connected to which port — so when it receives a data packet, instead of broadcasting it to all ports like a hub would, it sends it only to the device that needs it. This reduces network traffic significantly.

Both switches and routers can connect to each other, which increases network redundancy — multiple alternative paths are created for data to travel. If one path fails, another is used. This can sometimes reduce performance slightly since data packets may travel a longer route, but keeping the network running without interruption is an acceptable tradeoff.

---

## What is a Router?

A router's job is to connect networks to each other and transfer data between them. It does this through routing — which is where the name comes from.

Routing is the name given to the process of data moving between networks. This process involves creating the appropriate path between networks for data to be successfully delivered. Routing is especially useful when devices are connected to each other through multiple different paths.

---

## Subnetting

Subnetting is the name given to the process of dividing a network into smaller networks within itself. For example, a company might have different departments:

- Accounting
- Finance
- Human Resources

Just like we know where to send information, networks need to know this too. Network administrators use subnetting to divide the network into categories and assign certain parts to these structures.

Subnetting is done by dividing the number of hosts that can exist on a network, and this is represented by a number called a subnet mask.

IP addresses consist of four parts called octets — and the same applies to subnet masks, which are represented as four bytes (32 bits) ranging from 0 to 255.

Subnets use IP addresses for three different purposes:

- **Network Address** — identifies the start of the network
- **Host Address** — identifies devices within the network
- **Default Gateway** — the device that sends data to another network

In small networks like homes, there's usually only 1 subnet — since more than 254 devices aren't connected at the same time, there's no need for more than one subnet. But in businesses and offices, more devices means subnetting becomes necessary.

Subnetting gives us several advantages:
- Efficiency
- Security
- Full control

Take a regular café — it has two different networks. One for staff, cash registers, and internal devices. Another for the public Wi-Fi that customers use. Subnetting helps separate these two uses from each other, while both can still connect to larger networks like the internet.

---

## ARP — Address Resolution Protocol

As we remember from previous writeups, devices have two identifiers — a MAC address and an IP address. ARP (Address Resolution Protocol) is the technology that allows devices to identify each other within a network.

Simply put: ARP allows a device to associate a MAC address with an IP address on the network. Every device on the network keeps a record of information related to other devices' MAC addresses.

When devices want to communicate with each other, they send a broadcast to the entire network looking for a specific device. Through ARP, devices can find the MAC address they need to establish communication.

Each device on the network has a memory for storing information — this is called a cache. In the context of ARP, this cache stores the identifiers of other devices on the network.

To match an IP address with a MAC address, ARP sends two types of messages:

- **ARP Request** — broadcast to all devices on the network: *"Which MAC address has this IP address?"*
- **ARP Reply** — only the device with that IP address responds, sending back its MAC address

The requesting device stores this information and records it in its ARP cache for future use.

---

## DHCP

IP addresses can either be assigned manually — by physically entering them into a device — or through the more commonly used automatic method: a DHCP (Dynamic Host Configuration Protocol) server.

When a device connects to a network and hasn't been manually assigned an IP address, it sends a request to check whether there's a DHCP server on the network (**DHCP Discover**). The DHCP server then responds with an IP address the device can use (**DHCP Offer**).

The device sends back a confirmation that it accepts the offered IP address (**DHCP Request**). Finally, the DHCP server confirms the process is complete and allows the device to start using the IP address (**DHCP ACK**).

---

*TryHackMe · Pre Security 0 · Network Fundamentals*
