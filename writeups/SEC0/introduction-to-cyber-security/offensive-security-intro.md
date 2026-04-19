# Offensive Security Intro — I Hacked a Bank (in a lab)

**TryHackMe · Pre Security Path · Room Writeup**  
**Medium:** [Full writeup](https://medium.com/@wzia/offensive-security-intro-i-hacked-a-bank-in-a-lab-1d3dad973748)

`#OffensiveSecurity` `#EthicalHacking` `#TryHackMe` `#Gobuster`

---

This was my first real hands-on room on TryHackMe — and the task was simple: hack a fake bank. Not to steal anything, but to understand how attackers think. Offensive security is exactly that: finding weaknesses in a system before someone with bad intentions does.

---

## What is offensive security?

Where defensive security focuses on protecting systems, offensive security focuses on breaking into them — legally and ethically. The goal isn't damage. It's finding what's broken so it can be fixed. This is what penetration testers and ethical hackers do.

Understanding how attacks work is one of the best ways to build a strong defense. You can't protect what you don't understand.

---

## The task — finding hidden pages with Gobuster

The target was a fake banking website. My job was to find pages that weren't publicly linked — pages that developers might have left exposed by mistake.

The tool for this was Gobuster — a directory brute-forcing tool. It works by taking a wordlist and trying each word as a URL path, then reporting which ones actually exist on the server.

```bash
# Basic Gobuster command I used
gobuster dir -u http://fakebank.com -w wordlist.txt

# -u  →  target URL
# -w  →  wordlist file to use
# dir →  directory/file enumeration mode
```

The scan returned several results. One stood out: `/bank-transfer` — with a 200 status code, meaning the page exists and is accessible.

---

## What I found — an unauthenticated transfer page

I navigated to `/bank-transfer` and found a page that lets you move money between accounts — with no login required. None. Just an open form.

I transferred $2,000 from account 2276 to my account 8881. The transaction went through immediately.

1. Ran Gobuster with a wordlist against the target site
2. Discovered `/bank-transfer` — status 200
3. Opened the page — no authentication required
4. Transferred $2,000 from account 2276 → 8881
5. Flag retrieved: `BANK-HACKED`

---

## Why this matters

This is a real vulnerability class — it's called broken access control, and it appears on the OWASP Top 10 list of the most critical web security risks. In a real bank, a page like this being accessible without authentication would be a serious incident.

The fix is straightforward: require authentication before allowing any sensitive action. But first, someone has to find the problem. That's what offensive security is for.

---

## What I took away

The most interesting part wasn't finding the flag — it was understanding the process. Enumerate first, then investigate what you find. The vulnerability wasn't hidden — it was just in a place nobody thought to look.

Next up: Defensive Security Intro — the other side of the coin.

---

*TryHackMe · Pre Security path · Room: Offensive Security Intro*
