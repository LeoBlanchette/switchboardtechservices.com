---
title: "Why won’t Windows Update work anymore?"
date: 2025-10-26
tags: ["kirksville", "windows update", "troubleshooting"]
categories: ["Tech Support", "Computer Maintenance"]
cover: /posts/tech-support-questions/why-wont-windows-update-work-anymore/images/not-updating.webp
---

Things to check:

- Windows Update components stuck; try resetting the SoftwareDistribution and Catroot2 folders.
- Corrupted system files; "DISM /RestoreHealth" then "sfc /scannow".
- Third-party AV or firewall interfering with update traffic.
- Disk nearly full or failing, causing write errors.
- Version end-of-life or driver blocks.

Need help? Check here: [/services/computer-maintenance/](/services/computer-maintenance/)

---

## What it might be (likely causes)

- **Stuck update cache**  
  The `SoftwareDistribution` and `Catroot2` folders hold temporary update files and catalogs. If they get corrupted, Windows Update can stall or error out.

- **System file corruption**  
  Damaged component store (WinSxS) or core files can cause `0x800f081f`, `0x80073712`, and similar. `DISM` repairs the component store; `SFC` repairs protected files afterward. Background: [DISM overview](https://learn.microsoft.com/windows-hardware/manufacture/desktop/dism-overview) and [System File Checker](https://support.microsoft.com/windows/use-the-system-file-checker-tool-to-repair-missing-or-corrupted-system-files-79aa86cb-ca52-166a-92a3-966e85d4094e)

- **Security software in the way**  
  Third‑party antivirus/firewalls can block Windows Update endpoints, break TLS inspection, or sandbox services. Temporarily disable to test (or add exclusions).

- **Storage pressure or drive health**  
  Updates need free space and a healthy disk. Low space or failing sectors lead to download/apply failures. If your machine feels slow or noisy too, see: [/posts/speed-up-old-laptop/](/posts/speed-up-old-laptop/) and [/posts/top-problems-10-year-old-pcs/](/posts/top-problems-10-year-old-pcs/)

- **Out-of-support Windows version**  
  If your edition is past its lifecycle or a driver is blocked for safety, updates may halt. Context: [Windows lifecycle fact sheet](https://learn.microsoft.com/lifecycle/)

---

## Things to check (quick, safe wins)

1. **Run the built-in troubleshooter**  
   Settings → *System* → *Troubleshoot* → *Other troubleshooters* → **Windows Update**. This resets common components.

2. **Reset the update cache safely**  
   Open **PowerShell (Admin)** and run these in order (copy/paste as a block):  
   ```powershell
   net stop wuauserv
   net stop bits
   net stop cryptsvc
   ren C:\Windows\SoftwareDistribution SoftwareDistribution.old
   ren C:\Windows\System32\catroot2 catroot2.old
   net start cryptsvc
   net start bits
   net start wuauserv
   ```
   Then check for updates again.

3. **Repair the component store and system files**  
   Open **PowerShell (Admin)**:  
   ```powershell
   DISM /Online /Cleanup-Image /RestoreHealth
   sfc /scannow
   ```
   If DISM can’t find sources, see Microsoft’s DISM docs for specifying a source: [DISM repair](https://learn.microsoft.com/windows-hardware/manufacture/desktop/dism-deployment-image-servicing-and-management-technical-reference)

4. **Free up space**  
   Settings → *System* → *Storage* → Storage Sense (or `cleanmgr`). Aim for **15–20 GB** free before a feature update. Back up or offload big files first: [/posts/simple-data-backups-without-cloud/](/posts/simple-data-backups-without-cloud/)

5. **Temporarily disable third‑party AV/firewall**  
   Turn it off briefly to test updates. If that fixes it, add Windows Update services/URLs to the allowlist per your vendor’s instructions.

6. **Check version status**  
   Settings → *System* → *About* → **Windows specifications**. If you’re on an out‑of‑support release, plan an upgrade path. Local EOL perspective: [/posts/windows-10-end-linux-kirksville/](/posts/windows-10-end-linux-kirksville/)

7. **Driver sanity**  
   If a specific driver update keeps failing, roll back to the previous working version, then hide the problem update while you fetch a stable vendor driver.

---

## When to pause and get hands-on help

- Update errors persist **after** DISM/SFC and a clean cache.  
- Frequent disk I/O errors or SMART warnings hint at a failing drive—fix storage **before** forcing big updates.  
- Feature updates fail with rollback loops (`0xC1900101` class errors).  
A short diagnostic saves hours. If needed, we can back up, repair the OS image, or migrate you to a more stable setup.

---

### Insight
Windows Update isn’t one thing; it’s a pipeline—download, stage, service the image, commit, then clean up. Most failures trace to **three** causes: a corrupted cache, a damaged component store, or environmental blockers (security software, low space, weak disk). Fix the pipeline in that order and you usually restore flow. If your version is at end‑of‑life, the most stable path may be a clean rebuild—or a Linux conversion when the hardware is ready for a calmer life.

**Need steady, no‑nonsense help in Kirksville—repairs, clean rebuilds, or a stable maintenance plan?**  
See [/services/computer-maintenance/](/services/computer-maintenance/).
