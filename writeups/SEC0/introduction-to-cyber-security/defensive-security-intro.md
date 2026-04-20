# Defensive Security Intro — My First Time Acting as a SOC Analyst

**TryHackMe · Pre Security Path · Room Writeup**  
**Medium:** [Full writeup](https://medium.com/@wzia/defensive-security-intro-my-first-time-acting-as-a-soc-analyst-35de09d016e8)
`#DefensiveSecurity` `#BlueTeam` `#SOC` `#TryHackMe` `#SIEM`

*SIEM alerts, an unauthorized connection, and why process matters more than tools.*

---

I'm working through TryHackMe's Pre Security path. This is my writeup for Defensive Security Intro.

Before this room, I mostly heard about the "hacking" side of cybersecurity. But this room was about the other side — protecting systems, monitoring for threats, and responding when something goes wrong. This is called defensive security, and it's exactly the career path I want.

---

## What is defensive security?

The idea is simple: stop attacks before they happen, and handle them properly when they do. This means keeping systems updated, setting up firewalls, watching logs, and training people. It's not just technical — a big part of it is process.

The team that does this work is called the Blue Team.

---

## Two areas I learned about

The first is SOC — Security Operations Center. A SOC team watches systems around the clock. They look for unauthorized access, suspicious activity, and vulnerabilities. They also use something called Threat Intelligence — basically, information about attackers and how they operate.

The second is DFIR — Digital Forensics, Incident Response, and Malware Analysis. This covers what happens during and after an attack. Digital Forensics is about collecting evidence. Incident Response is a step-by-step process for dealing with the attack. Malware Analysis is about understanding viruses, trojans, and ransomware — either by running them in a safe environment or examining them without running them at all.

---

## The practical part — working inside a SIEM

This was my favorite part of the room. I got to work inside a SIEM simulation. SIEM is a tool that collects logs from different sources and shows alerts when something looks suspicious.

The alert I got was: **Unauthorized Connection Attempt Detected.**

My first instinct was to block the IP right away. But that's not how it works.

I reported it to the SOC Team Lead first. Got confirmation. Then blocked the IP.

That order matters. In a real environment, blocking the wrong IP can take down a legitimate connection — maybe it's a business partner, maybe it's a false positive. You don't act alone.

Here's what I actually did:

1. Saw the alert in the SIEM dashboard
2. Reported to SOC Team Lead
3. Received confirmation
4. Blocked the IP address

---

## What I took away

Defensive security isn't passive. It's constant monitoring, decision-making, and knowing when to escalate. The tools matter, but so does the process.

This is the kind of work I want to do every day.

Next up: What is Networking?

---

*TryHackMe · Pre Security path · Room: Defensive Security Intro*
