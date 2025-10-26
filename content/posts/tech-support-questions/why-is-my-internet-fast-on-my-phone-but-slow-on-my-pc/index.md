---
title: "Why is my internet fast on my phone but slow on my PC?"
date: 2025-10-26
tags: ["kirksville", "slow pc internet", "adapter", "drivers"]
categories: ["Tech Support", "House Calls"]
cover: /posts/tech-support-questions/why-is-my-internet-fast-on-my-phone-but-slow-on-my-pc/images/split-signal-and-interference.webp
---

Worth checking:

- PC on 2.4 GHz while phone uses 5 GHz; try a 5 GHz SSID.
- Outdated NIC drivers or power-saving modes throttling throughput.
- Ethernet cable damage or 100 Mbps negotiation instead of 1 Gbps.
- VPNs, filters, or security suites intercepting traffic.
- Browser extensions or background sync saturating bandwidth.

Need help? Check here: [/services/house-calls/](/services/house-calls/)

---

## What it might be (likely causes)

- **Band mismatch & Wi‑Fi capability**  
  Phones often join **5 GHz** automatically, while PCs (especially desktops with older adapters) get stuck on **2.4 GHz**, which is slower and noisier. Split SSIDs and steer the PC to 5 GHz: [/posts/router-settings-small-town/](/posts/router-settings-small-town/) and apartment RF context: [/posts/router-interference-apartments/](/posts/router-interference-apartments/)

- **Outdated or “green” NIC drivers**  
  Old Wi‑Fi/Ethernet drivers and aggressive power saving can cap throughput or cause micro‑stutters. Vendor drivers beat Windows’ generic ones.

- **Bad cable or slow link negotiation (Ethernet)**  
  A damaged cable or old **Cat5** may force 100 Mbps. Check the adapter’s **Link Speed**—it should say **1.0 Gbps** on modern gear. Background: [Gigabit Ethernet](https://en.wikipedia.org/wiki/Gigabit_Ethernet)

- **Traffic interception**  
  VPN clients, web filters, and some security suites proxy or scan traffic, lowering speed—PC only. Phones on the same LAN skip those desktop filters, so they look faster.

- **Browser/OS load**  
  Extensions, background sync, or stuck updaters can quietly eat bandwidth or CPU, making “internet speed” feel slow. If the whole PC is sluggish, broader tune‑up notes: [/posts/speed-up-old-laptop/](/posts/speed-up-old-laptop/)

---

## Things to check (quick, safe wins)

1. **Confirm link basics**  
   - **Wi‑Fi**: Connect the PC to your **5 GHz** SSID (consider unique names like `Home-5G` vs `Home-2G`).  
   - **Ethernet**: In adapter **Status**, verify **Speed** shows **1.0 Gbps**; if it says **100 Mbps**, swap the cable for known‑good **Cat5e/Cat6** and try another port.

2. **Driver refresh & power settings**  
   - Install the latest Wi‑Fi/Ethernet drivers from the PC or adapter manufacturer.  
   - Windows Device Manager → your adapter → *Power Management* → uncheck **Allow the computer to turn off this device**.  
   - For laptops, set *Power mode* to **Balanced/Best performance** while testing.

3. **RF sanity (if Wi‑Fi)**  
   - Move the PC a room closer and retest.  
   - In the router, set 2.4 GHz to channels **1/6/11** and pick a clean 5 GHz channel (DFS off while testing). How‑to: [/posts/router-settings-small-town/](/posts/router-settings-small-town/) and placement ideas: [/posts/kirksville-wifi-dead-zones/](/posts/kirksville-wifi-dead-zones/)

4. **Bypass software interceptors**  
   Temporarily disable VPN, web filters, and third‑party security suites. If speeds jump, add exclusions or use lighter settings.

5. **Browser & background load**  
   Test in a fresh browser profile with all extensions disabled. Check Task Manager for updaters or cloud sync saturating the line.

6. **Compare with a local test**  
   Copy a big file from a NAS or another PC over LAN. If LAN speed is fine but internet is slow only on the PC, suspect software. If both LAN and WAN are slow on the PC, suspect the adapter/cable/driver.

7. **ISP/gateway context**  
   If your phone on Wi‑Fi still beats your wired PC **after** these steps, your PC path is the bottleneck. If both are slow at the same time of day, see local provider notes: [/posts/isps-in-kirksville/](/posts/isps-in-kirksville/)

---

## Patterns that point to the cause

- **PC on 2.4 GHz, phone on 5 GHz** → band mismatch; split SSIDs and re‑join PC to 5 GHz.  
- **Ethernet says 100 Mbps** → bad/old cable or port; replace with Cat5e/Cat6, try another port.  
- **Fast right after reboot, then slows** → background updaters/extensions or VPN.  
- **Good LAN speed, poor internet** → VPN/filter/DNS path; test with interceptors off.  
- **Poor on both LAN and internet (PC only)** → adapter/driver/power settings.

---

## When to pause and get help

- Link keeps renegotiating between 100 Mbps ↔ 1 Gbps or drops under load.  
- Wi‑Fi speed collapses in certain rooms even at 5 GHz (placement/mesh plan needed).  
- You’ve updated drivers and cables, but speed is erratic only on the PC.  
An on‑site survey with proper cables, adapters, and a clean test laptop isolates the fault quickly.

---

### Insight
“Phone fast, PC slow” isn’t a paradox; it’s two very different **paths** to the same internet. Phones default to the cleanest band with minimal software baggage. PCs inherit old drivers, opportunistic power saving, flaky cables, and extra security layers. Make the PC’s path resemble the phone’s—explicit 5 GHz, good cable, current drivers, minimal interception—and the mismatch disappears.

**Want a clean, fast setup in Kirksville—driver cleanup, band splits, or wired runs where they matter?**  
See [/services/house-calls/](/services/house-calls/).
