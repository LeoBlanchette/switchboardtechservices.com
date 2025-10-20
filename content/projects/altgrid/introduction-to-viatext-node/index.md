---
title: "Introduction to ViaText Node"
date: 2025-10-20T17:40:21-05:00
lastmod: 2025-10-20T17:40:21-05:00 
draft: false 

# -----------------
# CORE SEO FIELDS
# -----------------
description: "" # Aim for 150-160 characters. This is the search snippet.
slug: "introduction-to-viatext-node" # Ensures a clean, predictable URL path.

keywords: 
  # 1. GENERATED (Kept for relevancy to post slug)
  - "introduction to viatext node" 
  - "AltGrid"
  - "Linux"
  - "Node"
  - "LoRa"

  
# -----------------
# CONTENT METADATA
# -----------------
author: "Leo Blanchette" # Set your default author here.
cover: "/projects/altgrid/introduction-to-viatext-node/images/viatux-with-lora-and-pi.jpg" # Path to the featured image for the post (e.g., /images/post-name/featured.jpg).
toc: true # Table of Contents (if supported by your theme).
weight: 0 # Used for ordering content lists (higher weight = appears earlier).
type: "post" # Defines the content type for template lookup.
---

[<< Back to AltGrid Project](/projects/altgrid/)

# Introduction to ViaText Node

> NOTE: This project is still very young in development.

ViaText Node is the **hardware side** of the ViaText system — an [ESP32-based LoRa communication device](https://lilygo.cc/products/lora3) that pairs directly with the [ViaText Core (Linux)](/projects/altgrid/introduction-to-viatext-core) software.  

Together, they form a complete **off-grid, text-based communication system**:  
- **ViaText Core** runs on your Linux computer. It handles CLI commands, message routing, and serial communication.  
- **ViaText Node** runs on your TTGO LoRa32 V2.1 board (ESP32). It listens for packets from the Core, executes them, and handles the radio transmission layer.

> Build like it’s 1986. Communicate like it’s 2086.  
> **Simplicity · Portability · Autonomy**


## What the Node Does

Ultimately it is a communicator with other nodes (that is, other people running ViaText on their communicators in the local area). Computers could be desktops or small linux systems such as Raspberry Pi or otherwise.

ViaText Node acts as a **translator between human-readable TLV commands and LoRa radio packets**. It stores its configuration in NVS memory, responds to diagnostic requests, and optionally displays its status on a tiny OLED screen.

Each node can operate alone, in mesh with others, or as part of a small relay network.  
All communication happens over serial (USB) or radio — **no phone, no Wi-Fi, no cloud**.

### Core Relationship

| Component | Role | Platform |
|------------|------|-----------|
| **ViaText Core** | Command dispatcher and serial manager | Linux |
| **ViaText Node** | Firmware handling LoRa messaging and parameters | ESP32 TTGO LoRa32 V2.1 |
| **Link** | SLIP-framed TLVs over USB serial | /dev/ttyUSB* |

When you issue commands like `--ping` or `--get id` from the Core, they are encoded, sent over serial, and interpreted by the Node firmware — which then replies with clean, script-friendly responses.

---

## Features

- **Simplicity** – Human-readable messaging protocol, no Protobuf or JSON.
- **Portability** – Built for TTGO LoRa32 V2.1 (ESP32) with OLED and battery.
- **Autonomy** – Operates fully off-grid; can store messages and run headless.
- **Linux-Friendly** – Fully controllable through `/dev/ttyUSB*` using the ViaText Core CLI.

---

See [the project](https://github.com/AltGrid/viatext-ttgo-lora32-v21) on GitHub.

## License

MIT License. Written for clarity, portability, and long-term resilience.

[<< Back to AltGrid Project](/projects/altgrid/)