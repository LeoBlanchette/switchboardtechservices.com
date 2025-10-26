---
title: "Why does my computer say 'No boot device found'?"
date: 2025-10-26
tags: ["kirksville", "no boot device", "bios", "drive failure"]
categories: ["Tech Support", "Repairs"]
cover: /posts/tech-support-questions/why-does-my-computer-say-no-boot-device-found/images/no-boot-device-found.webp
---

What to look at:

- SATA/NVMe drive failing or cable loose.
- Boot mode mismatch (UEFI vs Legacy) after a reset.
- Boot order changed; the OS drive fell behind USB/DVD.
- Damaged bootloader; needs repair via recovery media.
- Recent clone to SSD missing EFI partition.

Need help? Check here: [/services/repairs/](/services/repairs/)

---

## What it might be (likely causes)

- **Storage not detected or failing**  
  A loose SATA cable, unseated NVMe, or a dying drive can disappear from firmware. If the drive isn’t listed in BIOS/UEFI, the OS can’t boot. If it *is* listed but throws the error, suspect the bootloader/partitioning.

- **Boot mode mismatch (UEFI vs Legacy/CSM)**  
  Windows installed in **UEFI/GPT** won’t boot in **Legacy/MBR** mode and vice versa. A CMOS reset can flip this setting. Background: [UEFI](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface), [MBR vs GPT](https://en.wikipedia.org/wiki/GUID_Partition_Table)

- **Boot order drift**  
  After firmware updates or adding drives, the boot order may rank a USB stick or empty device first. Set the OS drive (or “Windows Boot Manager”) back to the top. If you need brand keys and boot-UI tips: [/posts/boot-from-usb-every-major-system/](/posts/boot-from-usb-every-major-system/)

- **Broken bootloader**  
  Power loss or disk issues can corrupt the bootloader. Windows repair tools (`bootrec`, `bcdboot`) can rebuild it. Reference: [Microsoft bootrec/bcdboot](https://learn.microsoft.com/windows-hardware/manufacture/desktop/repair-the-boot-menu-on-a-dual-boot-pc)

- **Imperfect clone/migration**  
  A clone that skipped the **EFI System Partition (ESP)** or marked partitions wrong will boot to this error. Verify the ESP exists and is flagged correctly. Migration prep tips: [/posts/prepare-for-computer-repair/](/posts/prepare-for-computer-repair/) and backups: [/posts/simple-data-backups-without-cloud/](/posts/simple-data-backups-without-cloud/)

---

## Things to check (quick, safe wins)

1. **See if the drive exists in firmware**  
   Enter BIOS/UEFI (`F2`, `Del`, `F10` vary by brand). If the drive isn’t listed, reseat cables (SATA data + power) or the NVMe stick. If still absent, the drive may be failing.

2. **Confirm boot mode matches the install**  
   - If Windows was installed as **UEFI**, ensure **UEFI mode** is enabled and **CSM/Legacy** is *disabled*.  
   - If it was **Legacy/MBR**, enable Legacy/CSM (temporary) to boot and plan a proper migration later. General boot thinking: [/posts/the-art-of-making-things-boot/](/posts/the-art-of-making-things-boot/)

3. **Fix boot order**  
   Put **Windows Boot Manager** (for UEFI) or the correct drive (Legacy) at the top. Remove USB/DVD from first place while testing.

4. **Run a quick drive health check**  
   If firmware sees the drive, boot a Windows installer or recovery USB → *Repair your computer* → *Command Prompt* and run:  
   ```text
   chkdsk C: /scan
   ```
   Any ugly errors? Back up first if possible.

5. **Repair the bootloader (Windows)**  
   From recovery Command Prompt (UEFI install):  
   ```text
   bootrec /scanos
   bootrec /fixmbr
   bootrec /fixboot
   bootrec /rebuildbcd
   bcdboot C:\Windows /l en-us /s S: /f UEFI
   ```
   Note: Replace `S:` with your EFI partition letter (assign one with `diskpart` if needed). Microsoft reference: [Repair the boot menu](https://learn.microsoft.com/windows-hardware/manufacture/desktop/repair-the-boot-menu-on-a-dual-boot-pc)

6. **Verify the EFI System Partition exists**  
   Use `diskpart` → `list vol`. Look for a small (~100–300 MB) **FAT32** partition (ESP). If missing after a clone, recreate/copy it, then rerun `bcdboot`.

7. **If the drive is failing, stop and back up**  
   SMART warnings or missing drives that reappear intermittently point to imminent failure. Image the disk to a healthy SSD before more experiments: [/posts/simple-data-backups-without-cloud/](/posts/simple-data-backups-without-cloud/)

---

## Patterns that narrow it down

- **Drive not in BIOS/UEFI at all** → physical connection or failed drive.  
- **Drive present, “Windows Boot Manager” missing** → bootloader/ESP issue.  
- **Error appeared after CMOS reset** → UEFI/Legacy mode mismatch or boot order.  
- **After cloning to SSD** → missing/incorrect ESP or wrong partition flags.

If you’re considering a sturdier, low-drama setup after recovery, a Linux conversion can be a clean slate on older PCs: [/posts/linux-distros/](/posts/linux-distros/) and local EOL context: [/posts/windows-10-end-linux-kirksville/](/posts/windows-10-end-linux-kirksville/)

---

## When to pause and get hands-on help

- The drive vanishes intermittently or SMART attributes are worsening.  
- Bootloader repairs loop or error out, or `bcdboot` can’t find Windows.  
- You need to salvage files before fixing boot.  
Bench testing with spare cables, cloning tools, and a controlled recovery environment will save your data and time.

---

### Insight
“No boot device” isn’t a verdict—it’s a map. Either the *device* isn’t there (power/cable/drive), the *firmware* can’t hand off correctly (mode/order), or the *loader* is missing. Solve it in that order: **see the drive, match the mode, rebuild the loader**. If storage is suspect, protect data first; computers are replaceable, your files aren’t.

**Need a precise recovery, clone, or boot repair in Kirksville?**  
See [/services/repairs/](/services/repairs/).
