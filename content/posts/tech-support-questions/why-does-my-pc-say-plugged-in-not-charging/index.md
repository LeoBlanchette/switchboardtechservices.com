---
title: "Why does my PC say 'Plugged in, not charging'?"
date: 2025-10-26
tags: ["kirksville", "battery", "charging", "ac adapter"]
categories: ["Tech Support", "Repairs"]
cover: /posts/tech-support-questions/why-does-my-pc-say-plugged-in-not-charging/images/uncharged.webp
---

A few things to try:

- OEM charger required for proper handshake; third-party may power but not charge.
- Battery wear level high; charging disabled by firmware thresholds.
- DC jack or charge controller board partially failing.
- Embedded controller/BIOS needs an update or reset (power drain reset).

Need help? Check here: [/services/repairs/](/services/repairs/)

---

## What it might be (likely causes)

- **OEM vs third‑party charger mismatch**  
  Many laptops authenticate their own adapters (Dell/HP/Lenovo). If the brick’s ID line or USB‑C e‑marker isn’t right, the system will run on AC but refuse to **charge**. Background: [USB Power Delivery](https://en.wikipedia.org/wiki/USB_Power_Delivery)

- **Battery wear / conservation modes**  
  High **wear level** (low Full Charge Capacity) or a vendor **battery conservation** setting (capping at ~80%) can show “plugged in, not charging.” Check vendor utilities before declaring failure.

- **DC jack or charge path fault**  
  Loose barrel jack, damaged USB‑C port, or failing **charging FET/sense line** can allow power‑in but block charge current to the pack.

- **Embedded controller (EC) / BIOS state**  
  After sleep/hibernation or updates, the **EC** can get stuck. A full power drain and/or BIOS/EC update often restores charging logic.

For broader charging diagnostics (wattage, cables, EC reset), also see: [/posts/why-is-my-laptop-battery-not-charging/](/posts/why-is-my-laptop-battery-not-charging/)

---

## Things to check (quick, safe wins)

1. **Verify the adapter’s wattage & identity**  
   Use an **OEM‑rated** brick (or higher) for your model. On USB‑C, use a PD‑rated, **e‑marked** cable (60–100 W). If your BIOS shows “Adapter not recognized,” charging will be disabled.

2. **Inspect the port & cable**  
   Look for wobble, lint, bent pins, or scorching on the DC jack/USB‑C. Clean a USB‑C port gently with a wooden toothpick; avoid metal tools.

3. **Power/EC reset**  
   Shut down → unplug AC → if removable, take out the battery → hold the power button **15–20 seconds**. Reconnect AC and boot. Some models have a tiny **reset pinhole** on the bottom—press it per the manual.

4. **Check wear and policies**  
   - **Windows**: run `powercfg /batteryreport` and open the HTML to compare **Design Capacity** vs **Full Charge Capacity**.  
   - Vendor apps (Lenovo Vantage, Dell Power Manager, ASUS, etc.) may have **Conservation/Battery Care** modes that cap charge at 60–80%. Toggle off to test.

5. **BIOS/UEFI & EC update**  
   Install the latest stable BIOS/EC firmware. Some updates explicitly fix adapter recognition or charge thresholds. Prep checklist before firmware work: [/posts/prepare-for-computer-repair/](/posts/prepare-for-computer-repair/)

6. **Try a known‑good adapter/cable**  
   If possible, test with an identical OEM adapter. If it starts charging immediately, your original brick or cable is at fault.

7. **Observe behavior on AC‑only (if possible)**  
   On models with removable batteries, run on AC with the battery out. Stable operation here but refusal to charge with the battery installed points to the **battery** or charge path.

8. **USB‑C port roulette**  
   Some laptops charge on **one** USB‑C port only. Try all USB‑C ports and both cable orientations.

---

## Patterns that point to the cause

- **“Adapter not recognized” in BIOS** → non‑OEM brick/cable or jack/ID‑line issue.  
- **Stuck at exactly 60–80%** → vendor conservation mode active.  
- **Runs fine on AC, won’t increase %** → worn battery or failed charge FET.  
- **Charges on OEM but not third‑party** → PD negotiation/ID mismatch.  
- **Charges after EC reset, then fails again** → firmware/EC quirk; update time.

For aging‑hardware context and when to retire parts, see: [/posts/top-problems-10-year-old-pcs/](/posts/top-problems-10-year-old-pcs/)

---

## When to pause and get hands‑on help

- **DC jack is loose** or shows heat damage.  
- Battery is **swollen** (chassis bulge, wonky trackpad)—power down and replace safely.  
- BIOS won’t recognize any adapter and resets don’t help (board‑level charge circuit).  
A bench test with a lab power source, jack inspection, and known‑good adapters separates charger, jack, battery, and board quickly.

---

### Insight
“Plugged in, not charging” is the firmware protecting your battery and board when the negotiation isn’t right. Think of charging as a contract: **identity + wattage + healthy cells + sane EC**. If any clause fails, charging halts. Verify the adapter, clean the physical path, reset the controller, and then judge the battery by its numbers—not by the icon.

**Need precise charging diagnostics, jack repair, or a safe battery swap in Kirksville?**  
See [/services/repairs/](/services/repairs/).
