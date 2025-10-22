---
title: "USB Boot and Firmware Unlock Cheat Sheet"
date: 2025-10-22
description: "Field-ready Hugo markdown reference for booting from USB and unlocking firmware protections across every major computer system."
tags: ["usb boot", "bios", "secure boot", "firmware", "repair"]
categories: ["guides", "field manual"]
draft: false
cover: /posts/boot-from-usb-every-major-system/images/lego-figurine-in-front-of-computer-bios.jpg
---

## Dell

### Inspiron / Latitude / XPS
- **Boot to USB:** Press `F12` during startup to enter the Boot Menu.
- **Disable Secure Boot:** Press `F2` to enter BIOS. Go to *Secure Boot*, set to `Disabled`. Save and exit.

### OptiPlex / Precision / Vostro
- **Boot to USB:** Press `F12` at Dell logo.
- **Disable Secure Boot:** Enter BIOS with `F2`, disable under *Boot > Secure Boot*. Toggle *Legacy Option ROMs* if needed.

## HP

### Pavilion / Envy / Spectre
- **Boot to USB:** Press `Esc`, then `F9` at Startup Menu.
- **Disable Secure Boot:** `Esc` > `F10` to enter BIOS. Go to *Boot Options*, set `Secure Boot: Disabled`, enable `Legacy Support` if needed.

### EliteBook / ProBook / ZBook
- **Boot to USB:** `Esc`, then `F9` at power-on.
- **Disable Secure Boot:** BIOS (`F10`). Go to *Security* > *Secure Boot Configuration*, set to `Disabled`. Enable `Legacy Boot` if boot media is not UEFI.

### Compaq / Older HP Systems
- **Boot to USB:** `Esc`, then `F9` or directly `F12`.
- **Disable Secure Boot:** If present, disable in BIOS under *Security*.

## Lenovo

### ThinkPad (T, X, L Series)
- **Boot to USB:** Tap `F12` on boot logo screen.
- **Disable Secure Boot:** Press `F1` to enter BIOS Setup. Under *Security* tab, disable Secure Boot. Enable *Legacy Support* if needed.

### IdeaPad / Yoga
- **Boot to USB:** `F2` or use Novo Button (pin-hole near power).
- **Disable Secure Boot:** BIOS via `F2` or Novo Menu. Disable Secure Boot under *Security*. Enable *Legacy Support* if required.

### ThinkCentre / ThinkStation
- **Boot to USB:** Press `F12` repeatedly during startup.
- **Disable Secure Boot:** `F1` for BIOS. Navigate to *Security* and disable.

## Apple

### Intel Macs (pre-2020)
- **Boot to USB:** Hold `Option` (⌥) key at startup.
- **Disable Secure Boot:** For T2 Macs: Boot to Recovery (`⌘R`) > *Utilities* > *Startup Security Utility*. Set `External Boot: Allow`, `Secure Boot: No Security`.

### Apple Silicon (M1/M2/M3)
- **Boot to USB:** Hold Power until *Startup Options* appear.
- **Disable Secure Boot:** Boot to *Options* > *Utilities* > *Startup Security*. Set `Reduced Security`, allow external boot.

## Acer / Gateway

### Aspire / Swift / Nitro
- **Boot to USB:** Tap `F12` at startup. Enable F12 Boot Menu in BIOS (`F2`) if not working.
- **Disable Secure Boot:** In BIOS, under *Boot* or *Security*, set `Secure Boot: Disabled`.

### Gateway Laptops (Walmart models)
- **Boot to USB:** `F2` for BIOS, `F12` for Boot Menu.
- **Disable Secure Boot:** BIOS > *Boot* > Disable Secure Boot. May require enabling Legacy Mode.

## ASUS

### VivoBook / ZenBook / TUF / ROG
- **Boot to USB:** `Esc` or `F8` at startup.
- **Disable Secure Boot:** BIOS (`F2` or `Del`). Go to *Boot > Secure Boot*, set to `Disabled`. Change OS Type to `Other OS`.

### Motherboards / Desktops
- **Boot to USB:** Press `Del` for BIOS, `F8` for boot menu.
- **Disable Secure Boot:** Found under *Security* or *Boot*. Set to `Disabled`.

## Microsoft Surface

### Surface Pro / Laptop / Book
- **Boot to USB:** Hold `Volume Down`, press `Power`.
- **Disable Secure Boot:** Power off, hold `Volume Up`, then press `Power` to enter UEFI. Disable Secure Boot in Security tab.

## Chromebook (any model)
- **Boot to USB:** Requires Developer Mode: `Esc + Refresh + Power` > `Ctrl + D` > confirm.
- **Enable USB Boot:** `Ctrl+Alt+T` > `shell` > `sudo crossystem dev_boot_usb=1 dev_boot_legacy=1`.
- **Boot:** At white screen, press `Ctrl + U`.
- **Note:** Cannot boot USB on enrolled/managed devices without admin deprovisioning.

## Raspberry Pi

### Pi 3B / 3B+ / 4 / 400
- **Boot to USB:** Insert bootable USB. Pi 4 supports USB boot out of box. Pi 3B requires OTP bit via `config.txt`.
- **Disable Secure Boot:** Not applicable. Pi always boots unrestricted.

## Intel NUC

### All Models
- **Boot to USB:** Tap `F10` at NUC logo.
- **Disable Secure Boot:** `F2` for BIOS. Under *Security*, set Secure Boot to `Disabled`.

## Framework Laptop

### All Generations
- **Boot to USB:** Press `F12` on boot. Toggle Fn-lock (`Fn + Esc`) if F12 doesn’t respond.
- **Disable Secure Boot:** BIOS (`F2`). Set Secure Boot to `Disabled`.

## System76

### Lemur / Oryx / Galago
- **Boot to USB:** Coreboot: tap `ESC` twice at power-on. Clevo: `F7` for boot menu.
- **Disable Secure Boot:** Off by default. Otherwise, disable under *Security* in BIOS.

### Thelio / Meerkat
- **Boot to USB:** Thelio: `Del`, then `F8/F12`. Meerkat: `F10` boot menu (Intel NUC-based).
- **Disable Secure Boot:** Enter BIOS. Disable under *Security*.

## Pine64

### Pinebook Pro / PinePhone / RockPro64
- **Boot to USB:** Insert microSD or USB. System boots from external media if present.
- **Disable Secure Boot:** Not applicable. Pine64 devices do not enforce Secure Boot.

## Toshiba / Dynabook

### Satellite / Portege / Tecra
- **Boot to USB:** `F12` boot menu.
- **Disable Secure Boot:** BIOS (`F2`) > *Security* tab > disable Secure Boot.

## Samsung

### Notebooks / Ativ / NP Series
- **Boot to USB:** `F2` for BIOS, `F10/F12` for boot menu.
- **Disable Secure Boot:** BIOS > *Boot* or *Security*, disable Secure Boot.

## Sony VAIO

### All Models
- **Boot to USB:** `F11/F12` or press `ASSIST` button while powered off.
- **Disable Secure Boot:** BIOS (`F2`) > *Boot*, set Secure Boot to `Disabled`.

## MSI

### Laptops / Motherboards
- **Boot to USB:** `Del` for BIOS, `F11` for boot menu.
- **Disable Secure Boot:** BIOS > *Settings > Security*, set Secure Boot to `Disabled`.

## Gigabyte

### Desktops / Aero / Aorus Laptops
- **Boot to USB:** `Del` for BIOS, `F12` for boot menu.
- **Disable Secure Boot:** Disable in BIOS under *Security*. Enable CSM if needed.

## ASRock

### Motherboards / Desktops
- **Boot to USB:** `F2` or `Del` for BIOS, `F11` for boot menu.
- **Disable Secure Boot:** BIOS > *Security* tab, disable Secure Boot.

## Packard Bell / eMachines

### Legacy Systems
- **Boot to USB:** Packard Bell: `F8`, eMachines: `F12`, BIOS: `Del`.
- **Disable Secure Boot:** Disable in BIOS if available. Most older models default to Legacy.

## IBM / Lenovo Desktop

### ThinkCentre / NetVista
- **Boot to USB:** `F12` for boot menu.
- **Disable Secure Boot:** Older models have no Secure Boot. On UEFI units, disable via BIOS.

## Dell Servers / Precision Workstations

### PowerEdge / Precision
- **Boot to USB:** `F11` or `F12` at startup.
- **Disable Secure Boot:** BIOS (`F2`) > *Secure Boot* > set to `Disabled`.


---


## Advanced Bootloader & USB Toolkit Options

### Ventoy
- Create a single USB that can boot multiple ISO/WIM/IMG/VHD files.
- Preserves UEFI and Legacy boot support with automatic ISO detection.
- Supports Secure Boot with custom MOK enrollment (v1.0.07+).
- https://www.ventoy.net

### YUMI / Easy2Boot
- Useful for BIOS-era systems or when Ventoy fails.
- Legacy-focused with custom menu creation for multiboot.

### GRUB-Based Rescue Drives
- Build your own boot menu for Linux, Memtest, hardware tools.
- Can be paired with PXELINUX or syslinux for deep-level boot chaining.

---

## Server & Enterprise Boot Notes

### Dell PowerEdge
- Boot Menu: `F11`
- BIOS/UEFI Setup: `F2`
- Some servers use iDRAC policies to lock boot order — check lifecycle controller.

### HP ProLiant
- BIOS: `F9`, Intelligent Provisioning: `F10`
- UEFI systems require FAT32-formatted USB with bootloader at `/EFI/BOOT/BOOTX64.EFI`

### Lenovo ThinkSystem
- Boot Menu: `F12`
- Secure Boot off by default on many rackmount systems.

---

## USB Filesystem Compatibility

| Format  | UEFI Boot | Legacy BIOS | Max File Size | Notes                        |
|---------|-----------|-------------|----------------|------------------------------|
| FAT32   | ✅        | ✅          | 4GB            | Required for Secure Boot     |
| NTFS    | ❌ (most) | ✅          | >4GB           | Won't boot on UEFI-only      |
| exFAT   | ❌        | ❌          | Unlimited      | Not bootable directly        |
| ISO9660 | ❌        | ✅ (CD)     | ~2GB           | For optical emulation        |

**Tip:** Use FAT32 with a split install.wim for large Windows ISOs, or use Ventoy with Secure Boot support.

---

## Tablet & ARM-Based Device Warnings

### Windows RT / ARM Tablets
- Cannot boot custom USB images.
- Bootloaders are signed with Microsoft-only keys (no bypass).
- Avoid servicing unless you're restoring factory image.

### Android Devices
- No UEFI BIOS; USB boot not supported.
- Use fastboot/ADB tools with unlocked bootloader for OS flashing.

---

## Boot Order Recovery & BIOS Recovery Modes

### ASUS CrashFree BIOS
- Insert USB with renamed BIOS file (`XXXX.CAP`)
- Boot with specific key held (`Ctrl+Home` or check manual)

### Gigabyte Dual BIOS
- Automatic fallback to backup BIOS if POST fails repeatedly
- May require shorting pins or power cycling with failed checksum

### MSI BIOS Flashback
- Use dedicated USB port and press button on I/O shield
- Requires power but no CPU/RAM installed

---

## PXE / Network Boot Triggering

### How to Enable PXE Boot
- BIOS > Enable LAN Boot ROM or PXE Boot
- Boot Key: `F12` on most PCs
- DHCP and TFTP server needed to serve image (iPXE or TinyPXE)

**Use Case:** Diskless recovery, OS imaging, or rescue when USB ports are dead.

---

## BitLocker Interaction Warning

- Disabling Secure Boot or enabling Legacy Boot may trigger BitLocker key prompt.
- BitLocker Recovery Key can be retrieved from:
  - Microsoft account: https://account.microsoft.com/devices/recoverykey
  - Admin (for domain-joined machines)
- Inform clients beforehand to back up the key.

---

## Apple Boot Policy Command Line Tools

### Verify Secure Boot or Integrity Status
```bash
# On Intel Macs
spctl --status
csrutil status

# On Apple Silicon (macOS Recovery Terminal)
bputil -s