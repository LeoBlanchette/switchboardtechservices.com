---
title: "Why does my computer keep restarting by itself?"
date: 2025-10-26
tags: ["kirksville", "random restart", "psu", "drivers"]
categories: ["Tech Support", "Repairs"]
cover: /posts/tech-support-why-does-my-computer-keep-restarting-by-itself/images/why-no-boot.webp
---

A few angles:

- Power supply sagging under load or bad DC jack (laptops).
- Thermal shutdowns from poor cooling or dried paste.
- Faulty RAM or unstable XMP/overclocks.
- Driver or kernel crashes; check Event Viewer for BugCheck entries.
- Short circuits from a loose standoff or debris inside the case.

Need help? Check here: [/services/repairs/](/services/repairs/)

---

## What it might be (likely causes)

- **Power delivery problems**  
  A PSU that’s aging, underrated, or tripping OCP (over‑current protection) can reboot the system under GPU/CPU spikes. On laptops, a loose/burned **DC jack** or a failing charger can cause momentary brownouts.

- **Thermal protection**  
  CPUs/GPUs will hard‑reset if they hit thermal limits. Dust‑clogged fins, dead fans, or dried thermal paste are the usual suspects. See overheating patterns here: [/posts/speed-up-old-laptop/](/posts/speed-up-old-laptop/) and [/posts/top-problems-10-year-old-pcs/](/posts/top-problems-10-year-old-pcs/)

- **Memory instability**  
  A flaky DIMM or an over‑ambitious **XMP/EXPO** profile can corrupt data and lead to reboots. Intermittent, load‑dependent restarts often trace to RAM timing/voltage.

- **Kernel/driver bugchecks**  
  Windows will reboot after a **BugCheck** (blue screen), depending on the “auto restart” setting. Logs live in Event Viewer and minidumps. Primer: [Analyze bug check codes](https://learn.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2)

- **Electrical shorts or mechanical faults**  
  A loose motherboard standoff, errant screw, or PCIe card not fully seated can short rails or cause ESD‑sensitive resets. Cases moved recently are prime suspects.

---

## Things to check (quick, safe wins)

1. **Turn off automatic restart to see the error**  
   Control Panel → *System* → *Advanced system settings* → *Startup and Recovery* → uncheck **Automatically restart**. If a blue screen appears next time, note the stop code. Event Viewer path: *Windows Logs → System*; filter for **BugCheck**, **Kernel‑Power (41)**, and **WHEA‑Logger**. Minidump basics: [Use WinDbg Preview](https://learn.microsoft.com/windows-hardware/drivers/debugger/debugger-download-tools)

2. **Temperature + fan sanity**  
   Watch temps at idle and under a short load. If temps spike and you hear fans ramp too late—or not at all—cleaning and repaste may be due. For general thermal thinking: [/posts/the-art-of-making-things-boot/](/posts/the-art-of-making-things-boot/)

3. **Power path inspection**  
   - **Desktop**: reseat 24‑pin ATX, 8‑pin CPU, and GPU PCIe connectors; check for burned plastic or wobble. Try a known‑good PSU if available.  
   - **Laptop**: test with battery removed (if removable) and AC only; wiggle the DC plug gently—any flicker hints at a jack issue.

4. **RAM test and profile sanity**  
   Disable XMP/EXPO and retest. Run **Windows Memory Diagnostic** (quick screen) or an overnight pass of **MemTest86**. If errors appear, test one stick at a time and swap slots. Background: [MemTest86](https://www.memtest86.com/)

5. **Driver/firmware checkpoint**  
   Roll back recently updated display/storage drivers if reboots started after an update. Update BIOS/UEFI to the latest stable. If crashes mention `nvlddmkm.sys`, `amdkmdag.sys`, or storage drivers, focus there.

6. **Case and standoff check (desktops)**  
   Power off, unplug, and visually inspect for stray screws, cables brushing fans, or an extra standoff shorting the board. Reseat the GPU and RAM with firm, even pressure.

7. **Disk health and free space**  
   Failing drives can provoke system instability. Check SMART; if reallocated/pending sectors are rising, plan a clone. Backup first: [/posts/simple-data-backups-without-cloud/](/posts/simple-data-backups-without-cloud/) and intake prep: [/posts/prepare-for-computer-repair/](/posts/prepare-for-computer-repair/)

---

## Patterns that point to the cause

- **Reboots only under gaming/exports** → PSU, GPU driver, or thermals.  
- **Instant power‑cut with no blue screen** → power delivery or short.  
- **Blue screen first, then reboot** → driver/kernel; grab the stop code.  
- **After moving the PC** → standoff/screw/GPU not fully seated.  
- **On battery but not on AC (or vice versa)** → laptop power path/DC jack.

---

## When to pause and get hands‑on help

- Reboots persist after RAM testing, clean drivers, and known‑good power.  
- You see **Kernel‑Power 41** with no other clues and hardware reseating didn’t help.  
- There’s a burning smell, arcing, or the DC jack is loose—stop and unplug.  
A bench test with spare PSU/RAM and a controlled thermal check can pinpoint the failing link quickly.

---

### Insight
Random restarts feel chaotic, but they usually follow physics: **power**, **heat**, **timing**, or **code**. Stabilize the inputs—clean power, sane temps, conservative memory timings—and most systems become boring in the best way. Treat each reboot as a breadcrumb: a stop code, a temperature spike, a power blip. Follow the trail methodically and the culprit stops being random.

**Need a careful diagnosis, DC jack repair, or PSU swap in Kirksville?**  
See [/services/repairs/](/services/repairs/).
