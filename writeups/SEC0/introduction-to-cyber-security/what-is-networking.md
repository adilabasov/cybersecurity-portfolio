# What is Networking?

**TryHackMe · Pre Security Path · Room Writeup**  
**Medium:** [Full writeup](https://medium.com/@wzia/what-is-networking-from-traffic-lights-to-mac-spoofing-d2604094696e)

`#Networking` `#CyberSecurity` `#TryHackMe` `#BlueTeam`

---

Networks, in simple terms, are connected things. Think about your friend group — what connects you is shared interests, hobbies, and skills. That's a network.

What I found interesting is that networks are everywhere in our daily lives — public transport systems, electrical infrastructure, traffic lights. We interact with them constantly without thinking about it.

In technology, networking starts with just two devices and scales up to billions. Smartphones, security cameras, agricultural sensors — they're all part of networks. Networking is so deeply integrated into modern life that it has a critical place in cybersecurity, and understanding it is essential.

---

## What is the internet?

The internet is a large network that contains smaller networks within it. More precisely, it's a system that connects different networks and allows them to communicate using the same rules.

What I understood: the internet is made up of interconnected small networks. Those small networks are private networks. The networks that connect them together are called public networks — and that's what we call the internet.

A network can be one of two types:

- **Private network**
- **Public network**

---

## How are devices identified?

There are two ways to identify a device on a network: an **IP address** and a **MAC address**. These are different things and shouldn't be confused — even though both identify a device.

A MAC address is like a fingerprint. It's a unique identifier burned into the network interface card during manufacturing. It cannot be changed — but it can be faked. An IP address, on the other hand, is used to identify a host on a network for a period of time. Unlike a MAC address, an IP can be reassigned to a different device.

---

## Why does IPv6 exist?

This is one of the parts I found most interesting.

As more and more devices connected to the internet, available IP addresses started running out. Cisco estimated that by the end of 2021, around 50 billion devices would be connected to the internet. I'm writing this in 2026 — so that number has already been passed.

Over 4.29 billion IPv4 addresses have been used. That means publicly available IP addresses have almost completely run out.

IPv6 was created to solve this problem. It looks more complex than IPv4, but it supports an enormous number of addresses — approximately 340 undecillion (that's 340 followed by 36 zeros). It also brings improvements through new methodologies, making it more efficient overall.

---

## MAC addresses in more detail

A MAC address lives on a microchip on the device's motherboard. It's assigned at the factory and is unique to that network interface. It's a twelve-character hexadecimal number, split into two halves separated by colons. The first six characters identify the company that made the network interface. The last six are a unique number.

---

## MAC spoofing — and why it matters

MAC addresses can be faked — this is called **spoofing**.

Spoofing happens when a device on a network pretends to be a different device by using another device's MAC address. This can break poorly configured security systems that trust devices based on their MAC address.

Here's a real example: imagine a firewall is configured to allow all traffic to and from an administrator's MAC address. If someone spoofs that MAC address, they inherit the admin's permissions — and that puts the entire system at serious risk.

---

## The practical simulation

In this room, I worked through a small simulation.

A router was blocking Bob's packets from reaching TryHackMe and dropping them, while Alice's packets went through fine because she had paid for Wi-Fi access.

I changed Bob's MAC address to match Alice's. After that, Bob could access the internet too.

Technically, this is spoofing — and in a real environment, it would be a security incident.

Next up: How the Web Works.

---

*TryHackMe · Pre Security 0 · Network Fundamentals*
