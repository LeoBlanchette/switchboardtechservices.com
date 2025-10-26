---
title: "Why do my video calls keep freezing or dropping?"
date: 2025-10-26
tags: ["kirksville", "zoom", "teams", "wifi"]
categories: ["Tech Support", "House Calls"]
cover: /posts/tech-support-why-do-my-video-calls-keep-freezing-or-dropping/images/video-call-freezing-frames.webp
---

Likely:

- Wi-Fi signal weak where you sit; reposition router or add an AP.
- Upstream bandwidth saturated by backups or streaming.
- Outdated webcam/NIC drivers causing glitches.
- Browser hardware acceleration conflicts.
- QoS not configured on the router.

Need help? Check here: [/services/house-calls/](/services/house-calls/)

---

## What it might be (likely causes)

- **Weak or inconsistent Wi‑Fi where you sit**  
  Marginal signal → retries → frozen video. Move the router, add an access point, or steer your device to 5 GHz. Placement ideas: [/posts/kirksville-wifi-dead-zones/](/posts/kirksville-wifi-dead-zones/) and small‑town router defaults: [/posts/router-settings-small-town/](/posts/router-settings-small-town/)

- **Upstream saturation / bufferbloat**  
  Calls are *upload*-sensitive. Cloud backups, camera uploads, or another call can saturate the uplink and add **bufferbloat**, causing delay and drops. Quick explainer: [Bufferbloat](https://en.wikipedia.org/wiki/Bufferbloat)

- **Drivers and hardware acceleration**  
  Old NIC/webcam/GPU drivers or flaky **hardware acceleration** in the browser/app can freeze frames. Updating drivers or toggling acceleration often stabilizes it.

- **QoS not prioritizing real‑time traffic**  
  With multiple users/devices, lack of **QoS** means calls compete with bulk traffic. A basic SQM/QoS setup can keep latency low even under load. Background: [Quality of service](https://en.wikipedia.org/wiki/Quality_of_service)

- **ISP variability during peak hours**  
  Neighborhood congestion or unstable modems can spike latency. Local context and options: [/posts/isps-in-kirksville/](/posts/isps-in-kirksville/)

---

## Things to check (quick, safe wins)

1. **Move closer or wire up**  
   For a test, sit in the same room as the router or plug in Ethernet/USB‑Ethernet. If stability returns, plan better Wi‑Fi coverage or a wired drop where you work.

2. **Pick the right band and channel**  
   Use **5 GHz** with a distinct SSID (e.g., `Home‑5G`) for laptops/phones. Set 2.4 GHz to **1/6/11** and pick a clean 5 GHz channel (avoid DFS while testing). How‑to: [/posts/router-settings-small-town/](/posts/router-settings-small-town/) and apartment RF notes: [/posts/router-interference-apartments/](/posts/router-interference-apartments/)

3. **Pause uploads & heavy downloads**  
   Temporarily pause cloud backups, Steam/console updates, and large transfers during calls. If calls instantly stabilize, configure schedules or QoS.

4. **Test for bufferbloat**  
   Run an online latency‑under‑load test before a call (e.g., Waveform bufferbloat test). If latency spikes hundreds of ms under load, set QoS/SQM on the router.

5. **Update drivers & apps**  
   - NIC/Wi‑Fi, GPU, and webcam drivers from the vendor.  
   - Update Zoom/Teams/Meet clients.  
   - If using a browser, toggle **Use hardware acceleration** off/on to compare.

6. **Camera and mic sanity**  
   Use 720p instead of 1080p on weak links; switch off virtual backgrounds to reduce GPU/CPU load. If audio crackles while video freezes, suspect CPU load or drivers.

7. **Router reboot & firmware**  
   Reboot the router/modem before important calls. Install stable firmware updates that address Wi‑Fi or QoS bugs.

8. **Prefer Ethernet for the host device**  
   Even a cheap USB‑C/USB‑A Ethernet dongle can make a laptop rock‑solid for calls.

---

## Patterns that point to the cause

- **Good for a few minutes, then degrades** → background upload or ISP congestion.  
- **Freezes when you move rooms** → Wi‑Fi coverage; add an AP or reposition.  
- **Only your PC has issues; phone is fine** → driver/acceleration on the PC. See: [/posts/why-is-my-internet-fast-on-my-phone-but-slow-on-my-pc/](/posts/why-is-my-internet-fast-on-my-phone-but-slow-on-my-pc/)  
- **Audio OK but video freezes** → GPU/browser acceleration or webcam driver.  
- **Everyone at home lags at once** → upstream saturation or ISP hiccup; consider QoS and check: [/posts/isps-in-kirksville/](/posts/isps-in-kirksville/)

---

## When to pause and get hands‑on help

- Calls fail even beside the router and with uploads paused.  
- Ethernet is stable but Wi‑Fi isn’t (needs AP/mesh planning and channel work).  
- You need SQM/QoS tuned for your exact ISP speed and modem.  
An on‑site survey with spectrum checks, wired tests, and QoS setup turns video calls from roulette into routine.

---

### Insight
Video calls are fragile because they care about **latency** more than raw speed. A single saturated upload or a weak RF hop can add seconds of delay and a cascade of freezes. Build a path that keeps latency low—solid signal, minimal background traffic, and simple QoS—and calls become boring in the best way: you stop thinking about them.

**Want predictable calls in Kirksville—coverage mapping, wired runs, or QoS that actually works?**  
See [/services/house-calls/](/services/house-calls/).
