---
title: "Why won’t my computer turn on at all?"
date: 2025-10-26
tags: ["kirksville", "no power", "psu", "motherboard"]
categories: ["Tech Support", "Repairs"]
cover: /posts/tech-support-questions/why-wont-my-computer-turn-on-at-all/images/dead-computer.webp
---

Start simple:

- Power strip or outlet fault; try a different known-good outlet.
- For desktops, check PSU switch, 24-pin and CPU 8-pin connections.
- For laptops, test with battery removed (if possible) and adapter only.
- Look for liquid damage or burnt smells near DC jack/VRMs.
- Motherboard short from standoff or debris.

Need help? Check here: [/services/repairs/](/services/repairs/)

---

## What it might be (likely causes)

- **No AC or a tripped power path**  
  Dead outlet, tripped power strip, or a PSU rocker switch in the *O* position. On laptops, a failed charger or loose **DC jack** can present as “totally dead.”

- **PSU / adapter failure**  
  Desktops with aging PSUs may show *no lights, no fans*. Laptops with failing adapters won’t light the charge LED. If a battery still has some charge, it might briefly flicker and die.

- **Main power connectors not seated**  
  The 24‑pin **ATX** and 8‑pin (4+4) **CPU EPS** connectors must be fully clicked in. A loose CPU EPS often means *absolutely nothing* happens on power press.

- **Front‑panel switch or case wiring**  
  The **PWR_SW** lead can be miswired. Shorting the two power‑switch header pins with a screwdriver is a safe test on desktops.

- **Board short / standoff issue**  
  An extra standoff or a stray screw under the motherboard can short the board, preventing power‑on.

- **Catastrophic component fault**  
  Rare but real: shorted VRMs, damaged CPU, spilled liquid. Look and sniff for scorching near the DC jack or VRM heatsinks.

Background: basic boot/firmware mindset here: [/posts/the-art-of-making-things-boot/](/posts/the-art-of-making-things-boot/) and aging‑hardware patterns: [/posts/top-problems-10-year-old-pcs/](/posts/top-problems-10-year-old-pcs/)

---

## Things to check (quick, safe wins)

1. **Verify power at the wall**  
   Plug a lamp or phone charger into the same outlet. If the power strip has a breaker, press reset. Try the PC directly in a wall outlet.

2. **PSU and rear switches (desktop)**  
   Flip the PSU rocker to **I**. Some PSUs have a **self‑test** button/LED—use it. If the PSU fan doesn’t twitch on self‑test, suspect the PSU.

3. **Minimal power‑on test (desktop)**  
   - Unplug everything except motherboard 24‑pin, CPU 8‑pin, and one stick of RAM.  
   - Disconnect GPU and all drives.  
   - Briefly short the **PWR_SW** header pins to see if fans start.  
   If it powers on now, add components back one at a time.

4. **Reseat main power leads**  
   Firmly reseat the **24‑pin ATX** and **8‑pin CPU EPS** connectors until they click. Verify the GPU has its PCIe power leads connected if installed.

5. **Laptop power path**  
   Remove the battery (if removable) and try **AC‑only**. If there’s a tiny reset pinhole on the bottom, press it (EC reset). Try a known‑good charger of the correct wattage. Related battery/charger logic: [/posts/why-is-my-laptop-battery-not-charging/](/posts/why-is-my-laptop-battery-not-charging/)

6. **Front‑panel switch sanity (desktop)**  
   Check the case’s front‑panel header against the motherboard manual. As a test, you can short the power pins with a screwdriver to simulate the button.

7. **Board outside the case (desktop)**  
   If you recently built or moved the PC, remove the motherboard and test on cardboard with only CPU + cooler, one RAM stick, and PSU. This eliminates standoff shorts.

8. **Signs of damage**  
   Look for liquid residue, corrosion, or burn marks near the DC jack (laptops) and around VRMs/chokes (desktops). If you smell ozone or see scorching, stop testing and seek service.

9. **Check for life indicators**  
   Any tiny LEDs on the board? Does the charger light up at the jack? No indicators often means upstream power (PSU/adapter/outlet). Some laptops show a brief LED flash for a failed power sequence—note patterns.

Prep and backup tips if you get it to power on again: [/posts/prepare-for-computer-repair/](/posts/prepare-for-computer-repair/) and for broader stability: [/posts/speed-up-old-laptop/](/posts/speed-up-old-laptop/)

---

## Patterns that narrow the cause

- **Absolutely no lights, no fans** → wall/strip/PSU/adapter/DC jack.  
- **Fans twitch then die** → PSU protection tripping or board short.  
- **Only powers on outside the case** → standoff/short under the board.  
- **Laptop runs on battery but not AC** → charger or DC jack path.  
- **Click from PSU, nothing else** → overload/short; remove components and retry.

---

## When to pause and get hands‑on help

- You find scorching, liquid damage, or a soft/loose DC jack.  
- The PSU clicks off immediately even with minimal load (possible short).  
- The power sequence is intermittent and unpredictable (cracked traces, failing VRMs).  
Bench testing with a lab PSU/charger and spare parts isolates the fault fast and safely.

---

### Insight
“Dead” systems are usually one broken link in the **power path**: wall → PSU/adapter → board regulators → components. Start at the wall and work inward, removing variables until *something* reacts. Once the supply is known good and the board isn’t shorted, the rest becomes a straightforward, almost boring, process of elimination.

**Need a no‑nonsense diagnosis, PSU swap, or DC jack repair in Kirksville?**  
See [/services/repairs/](/services/repairs/).
