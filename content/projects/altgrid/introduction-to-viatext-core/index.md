---
title: "Introduction to Viatext Core"
date: 2025-10-20T17:04:02-05:00
lastmod: 2025-10-20T17:04:02-05:00 
draft: false 

# -----------------
# CORE SEO FIELDS
# -----------------
description: "" # Aim for 150-160 characters. This is the search snippet.
slug: "introduction-to-viatext-core" # Ensures a clean, predictable URL path.

keywords: 
  # 1. GENERATED (Kept for relevancy to post slug)
  - "introduction to viatext core" 
  - "AltGrid"
  - "Linux"
  - "Shell"
  - "Cmd"

  
# -----------------
# CONTENT METADATA
# -----------------
author: "Leo Blanchette" # Set your default author here.
cover: "/projects/altgrid/introduction-to-viatext-core/images/viatux-looking-down-at-terminal.jpg" # Path to the featured image for the post (e.g., /images/post-name/featured.jpg).
toc: true # Table of Contents (if supported by your theme).
weight: 0 # Used for ordering content lists (higher weight = appears earlier).
type: "post" # Defines the content type for template lookup.
---


# ViaText Core (Linux)

[<< Back to AltGrid Project](/projects/altgrid/)

**Status:** In Development  
**Repository:** [github.com/AltGrid/viatext-core](https://github.com/AltGrid/viatext-core)

ViaText Core is the **Linux-side command line and library system** used for the ViaText communications project.  
It allows a Linux computer to scan, manage, and message LoRa nodes directly — without phones, apps, or cloud servers.

See also [Introduction to ViaText](/projects/altgrid/introduction-to-viatext)
---

## Overview

ViaText is built to support **human-readable communication** between computers and microcontroller-based radio nodes.  
It follows three design standards:

- **Simplicity** — All data is readable, debuggable, and scriptable.  
- **Portability** — Works on almost any Linux device (PCs, Raspberry Pi, thin clients).  
- **Autonomy** — Fully functional offline; no external dependencies or networks.

---

## Relationship to the Node

- **ViaText Core (this repo)** — Linux CLI and serial manager.  
- **ViaText Node** — ESP32 TTGO LoRa32 firmware that handles radio communication.

Together they form a two-part system:  
- Core sends and receives TLV messages over serial  
- Node processes and executes the commands via LoRa

---

## Basic Architecture

```
+------------------+       Serial/USB       +-------------------+
|  ViaText Core    |  <------------------>  |   ViaText Node    |
|  (Linux CLI)     |   SLIP-framed TLVs     |  (ESP32 + LoRa)   |
|  command_dispatch|                        |  node_interface   |
|  commands        |                        |  node_protocol    |
|  serial_io       |                        |  node_display     |
+------------------+                        +-------------------+
```

---

## Build and Run

### Requirements

- Linux (Debian, Ubuntu, Fedora, or similar)
- g++ with C++17 or newer
- make

Check tools:

```bash
g++ --version
make --version
```

### Build

```bash
git clone https://github.com/AltGrid/viatext-core.git
cd viatext-core
make
```

### Run Example Commands

Scan and list connected nodes:

```bash
./viatext-cli --scan
```

Output:
```
id=N3 dev=/dev/ttyACM0 online=1
id=N20 dev=/dev/ttyACM2 online=1
```

Ping a node:

```bash
./viatext-cli --node N3 --ping
status=ok seq=1
```

Get node info:

```bash
./viatext-cli --node N3 --get all
status=ok seq=1 id=N3 alias=TestNode freq_hz=915000000 sf=7
```

---

## Features Summary

- Human-readable TLV protocol (no JSON or Protobuf)  
- SLIP framing for reliable serial transport  
- Minimal dependencies: C++17 + CLI11 only  
- Compatible with `/dev/ttyUSB*` devices  
- Command and node registry system for quick device management  
- Output format designed for easy parsing and automation

---

## Example Use Case

```bash
# Detect and alias connected devices
./viatext-cli --scan --aliases

# Ping a device
./viatext-cli --node N3 --ping

# Rename node
./viatext-cli --node N3 --set alias FieldUnit

# Read full status
./viatext-cli --node FieldUnit --get all
```

Output:

```
status=ok seq=4 id=N3 alias=FieldUnit freq_hz=915000000 sf=7 cr=4/5
```

---

## License

MIT License — written for clarity, portability, and long-term maintenance.

![ViaText](/projects/altgrid/introduction-to-viatext-core/images/viatext.jpg)

[<< Back to AltGrid Project](/projects/altgrid/)