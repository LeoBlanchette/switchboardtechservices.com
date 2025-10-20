---
title: "Introduction to Viatext"
date: 2025-10-20T16:25:10-05:00
lastmod: 2025-10-20T16:25:10-05:00 
draft: false 

# -----------------
# CORE SEO FIELDS
# -----------------
description: "" # Aim for 150-160 characters. This is the search snippet.
slug: "introduction-to-viatext" # Ensures a clean, predictable URL path.

keywords: 
  # 1. GENERATED (Kept for relevancy to post slug)
  - "introduction to viatext" 
  - "AltGrid"
  - "Linux"
  - "Introduction"
  - "ViaText"
  - "Communications"
  - "LoRa"

  
# -----------------
# CONTENT METADATA
# -----------------
author: "Leo Blanchette" # Set your default author here.
cover: "/projects/altgrid/introduction-to-viatext/images/viatext.jpg" # Path to the featured image for the post (e.g., /images/post-name/featured.jpg).
toc: true # Table of Contents (if supported by your theme).
weight: 0 # Used for ordering content lists (higher weight = appears earlier).
type: "post" # Defines the content type for template lookup.
---

[<< Back to AltGrid Project](/projects/altgrid/)

## Introduction

**ViaText** is an off-grid, Linux-first messaging system under the [AltGrid](https://github.com/AltGrid) project family — a toolkit for communication when the cloud disappears and cables end. Its guiding philosophy is **Simplicity · Portability · Autonomy**.

At its heart, ViaText connects computers directly through **LoRa radio** or serial links. It doesn’t need cell towers, Wi-Fi, or even the internet — just small, low-power devices that talk to each other the old-fashioned way: by signal and intent. Messages are human-readable, inspectable with a text editor, and portable across Linux systems.

### Core and Node: Two Halves of the System

ViaText comes in two layers working together:

- **ViaText Core** runs on Linux. It’s the command-line brain — a small C++ tool that handles message creation, routing, and serial communication. It treats connected LoRa devices as regular serial ports (`/dev/ttyUSB*`), so standard Unix tools can log, parse, or even script messages.

- **ViaText Node** runs on an **ESP32 TTGO LoRa32** board — a pocket-sized radio module with optional OLED display. This is the field device, responsible for sending and receiving messages, scanning frequencies, or relaying packets between other nodes.

Together, Core and Node form a miniature “offline internet,” with no central server, no vendor lock-in, and no smartphone required.

### How It Differs from Meshtastic

If you’ve heard of [Meshtastic](https://meshtastic.org/), ViaText might sound familiar — both use LoRa to form peer-to-peer networks. The difference lies in design philosophy.  
ViaText aims to be **simpler, cheaper, and entirely computer-driven**, with no reliance on mobile apps or cloud-based coordination. It’s meant for tinkerers who prefer terminals over touchscreens and systems that can be understood — or repaired — with a text editor and soldering iron.

In short, ViaText is the Linux way of doing mesh communication: plain bytes, open tools, and freedom to operate anywhere — even where “the grid” no longer reaches.

See also [Introduction to Viatext Core](/projects/altgrid/introduction-to-viatext-core/)

[<< Back to AltGrid Project](/projects/altgrid/)