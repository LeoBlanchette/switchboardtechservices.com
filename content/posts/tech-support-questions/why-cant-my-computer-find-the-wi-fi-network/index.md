---
title: "Why can’t my computer find the Wi-Fi network?"
date: 2025-10-26
tags: ["kirksville", "wifi missing", "network", "drivers"]
categories: ["Tech Support", "House Calls"]
cover: /posts/tech-support-why-cant-my-computer-find-the-wi-fi-network/images/router-in-lego.webp
---
Consider:

- Adapter disabled or flight mode toggled by a function key.
- 5 GHz-only router while the adapter is 2.4 GHz-only (or vice versa).
- Hidden SSID or unusual country/channel settings.
- Outdated Wi-Fi drivers or Windows network stack glitches.
- Distance and interference; walls and appliances matter.

Need help? Check here: [/services/house-calls/](/services/house-calls/)

---

## What it might be (likely causes)

- **Radio disabled or hard-switched**  
  Laptops often have a physical wireless toggle or a **Fn** hotkey that kills the radio. Airplane mode also shuts off Wi‑Fi. A quick toggle brings the SSID list back.

- **Band/support mismatch**  
  Some older adapters are **2.4 GHz‑only**; some guest networks are **5 GHz‑only**. If your adapter can’t speak that band or standard (e.g., no 802.11ac), the network simply won’t appear. Band‑planning tips: [/posts/router-settings-small-town/](/posts/router-settings-small-town/)

- **Hidden SSID or unusual channels**  
  Hidden SSIDs require **exact** name/security/mode to join. Routers using DFS channels on 5 GHz or out‑of‑region **regulatory domain** settings can disappear for certain clients. Background: [Service set (Wi‑Fi)](https://en.wikipedia.org/wiki/Service_set_(802.11_network)), [Wi‑Fi channels](https://en.wikipedia.org/wiki/List_of_WLAN_channels), [Regulatory domain](https://en.wikipedia.org/wiki/Wireless_regulatory_domain)

- **Driver or stack trouble**  
  Old drivers or a wedged Windows network stack can hide networks or report “No networks found.” A reset or clean driver install usually restores scanning.

- **RF environment & placement**  
  Thick walls, masonry, aquariums, and microwaves can make an SSID vanish in one room but not another. Practical placement notes: [/posts/kirksville-wifi-dead-zones/](/posts/kirksville-wifi-dead-zones/)

---

## Things to check (quick, safe wins)

1. **Verify the radio is on**  
   - Windows: `Win + A` → ensure **Airplane mode** is off; `Win + I` → *Network & Internet* → **Wi‑Fi** is On. Many laptops also use **Fn + (antenna icon)** to toggle wireless.  
   - Linux: `rfkill list`; if blocked, `rfkill unblock wifi`.

2. **Scan capability & bands**  
   - Windows: `PowerShell` → `netsh wlan show drivers` shows supported bands/standards. If your router is 5 GHz‑only and the adapter lists only 2.4 GHz, the SSID won’t appear. Consider enabling both bands or adding a dual‑band USB adapter. Band setup help: [/posts/router-settings-small-town/](/posts/router-settings-small-town/)

3. **Try closer and compare devices**  
   Stand near the router. If phones see the SSID but the PC doesn’t, suspect the PC’s adapter/driver. If *nothing* sees it in that room, suspect DFS channel selection or interference: [/posts/router-interference-apartments/](/posts/router-interference-apartments/)

4. **Add a hidden network explicitly**  
   If the SSID is hidden, add it manually with **exact** security (WPA2/WPA3) and password. Hidden networks don’t magically appear on scan lists.

5. **Driver refresh**  
   - Windows: Device Manager → *Network adapters* → your Wi‑Fi → **Uninstall device** (check “Delete driver software” if offered) → reboot → install the latest vendor driver.  
   - Linux: ensure kernel/firmware packages for your chipset are installed.

6. **Windows network reset (last resort)**  
   Settings → *Network & Internet* → *Advanced network settings* → **Network reset**. This rebuilds the stack and often restores scanning.

7. **Router side sanity**  
   - Enable both **2.4 GHz & 5 GHz** with distinct SSIDs (e.g., `Home-2G`, `Home-5G`) during testing.  
   - Avoid DFS channels temporarily and set 2.4 GHz to channels **1/6/11**.  
   - Ensure you’re not on a **guest SSID** with isolation blocking discovery. More: [/posts/router-settings-small-town/](/posts/router-settings-small-town/)

---

## When to pause and get help

- The SSID appears on other devices, but your PC never sees it even inches from the router (driver/adapter issue).  
- The SSID disappears **only** when DFS is enabled or region is mis-set (router config issue).  
- You’re in a dense apartment block with shifting interference, and a stable plan (non‑DFS 5 GHz + smart 2.4 GHz) is needed. See: [/posts/router-interference-apartments/](/posts/router-interference-apartments/)

If your ISP gateway buries these options, bridge it and run your own router for full control. Local context: [/posts/isps-in-kirksville/](/posts/isps-in-kirksville/)

---

### Insight
Wi‑Fi discovery is a handshake between **what your adapter can speak** and **what the router is broadcasting**, inside a noisy, rule‑bound radio spectrum. When networks “vanish,” it’s usually a mismatch (band/standard/security) or the environment (DFS/interference) rather than a ghost. Make the setup explicit—separate SSIDs, sane channels, current drivers—and scanning becomes boring and reliable.

**Need an on‑site scan, driver cleanup, or router reconfiguration in Kirksville?**  
See [/services/house-calls/](/services/house-calls/).
