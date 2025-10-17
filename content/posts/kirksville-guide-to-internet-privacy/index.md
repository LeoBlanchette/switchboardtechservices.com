---
title: "Full Privacy Real Simple The Tools of the Modern Ghost"
date: 2025-10-17
draft: false
author: "Leo Blanchette"
description: "A comprehensive guide to achieving full digital privacy using Tails Tor ProtonMail Signal encryption and proven operational security practices. Written for normal people who want real privacy."
tags: ["privacy", "tails", "tor", "protonmail", "signal", "security", "encryption", "switchboard tech services", "kirksville"]
categories: ["Privacy", "Guides", "Security"]
summary: "Complete practical and understandable. This is the modern privacy guide for people who want to take control of their digital life using open verifiable tools."
cover: posts/kirksville-guide-to-internet-privacy/images/lego-minifigure-in-his-privacy-mancave.jpg
---

# Full Privacy Real Simple The Tools of the Modern Ghost

Kirksville is not Silicon Valley and that is exactly why privacy matters here.  
In a college town, data leaks and surveillance are not abstract problems. They affect students on campus WiFi, small businesses handling payments, and residents using free cloud services that quietly exchange convenience for data.

Privacy is maintenance. It is the difference between owning your front door and leaving it open to the internet.

This guide explains how to go fully private, legally and responsibly, using tools anyone can learn.  
It is divided into two parts.

1. Essential Systems. The foundation of real privacy.  
2. Complementary Tools and Advanced Practices. The supporting layer that refines and expands control.

All of these tools are open, verifiable, and actively maintained. Each link below goes to its official source.

> NOTE: This might seem overwhelming. Come back to this guide occassionally and look at the features described bit by bit. 

---

## Essential Systems for Real Privacy

These are the non negotiables. They form the foundation of personal digital security.

### Tails The Amnesic Incognito Operating System  
https://tails.net/

Tails runs entirely from a USB stick and forgets everything when you shut it down.  
Every connection goes through the Tor network, and by default nothing is written to the internal drive.  
It is used by journalists, researchers, and anyone who needs a clean work environment for sensitive activity.  


---

### Tor Browser Anonymous Browsing Done Right  
https://www.torproject.org/

Tor routes your traffic through a global network of relays, hiding where a connection starts and ends.  
The Tor Browser includes hardened settings, built in NoScript, and uniform window sizing to reduce fingerprinting.  

Avoid plugins and do not log into accounts tied to your identity. Used properly, Tor Browser is the safest mainstream browser available.

---

### ProtonMail Encrypted Email That Actually Means It  
https://proton.me/mail

ProtonMail is based in Switzerland and uses end to end encryption between users.  
Messages are stored using zero access encryption, meaning Proton cannot read your inbox.  
You can use the web app, mobile client, or Proton Bridge for desktop integration.  
Pair it with Proton Calendar or Proton Drive for a full private suite.

See also [our article on Protonmail.](posts/why-use-protonmail)

---

### Signal Private Messaging and Calls with Proven Security  
https://signal.org/

Signal uses the open source Signal Protocol, the gold standard in encrypted messaging.  
Texts, calls, photos, and videos are end to end encrypted, and keys rotate with every message.  
It collects almost no metadata and supports disappearing messages and registration locks.  
Signal is trusted by journalists and researchers worldwide.

---

### Bitwarden Passwords You Can Forget Safely  
https://bitwarden.com/

Bitwarden encrypts your password vault locally before syncing, so the company never sees your master key.  
It is open source, cross platform, and can be self hosted.  
Use long generated passphrases instead of short complex passwords. Length beats cleverness.

---

### YubiKey Physical Keys for the Digital World  
https://www.yubico.com/

A hardware security key is an unphishable second factor for logins.  
It uses cryptographic challenge response that cannot be intercepted.  
Most major services support the WebAuthn or FIDO2 standards that YubiKey implements.  
Own your keys. Do not trust text messages for authentication.

---

### VeraCrypt and LUKS Encrypting Storage Properly  
VeraCrypt https://www.veracrypt.fr/en/Home.html  
LUKS https://gitlab.com/cryptsetup/cryptsetup

Encryption is mandatory if you carry data on a laptop or external drive.  
VeraCrypt provides encrypted containers and full disk encryption for Windows macOS and Linux.  
LUKS, built into Linux, can encrypt entire partitions.  
Both depend on strong passphrases. Once encrypted, your drive is unreadable without the key.

---

### Firefox Hardened Not Just Convenient  
https://www.mozilla.org/firefox/

Mozilla Firefox remains the only major browser with open governance.  
With a few adjustments it becomes a strong privacy tool.

- Install [uBlock Origin](https://ublockorigin.com/) for ad and tracker blocking  
- Add Cookie AutoDelete for session hygiene  
- In about config set privacy.resistFingerprinting true  
- Disable telemetry in settings  

For advanced users, see the arkenfox user.js project  
https://github.com/arkenfox/user.js/

---

## Complementary Tools and Advanced Practices

Once the essentials are in place, these additions refine and extend your privacy perimeter.

### SimpleLogin and AnonAddy Email Aliasing for Control  
https://simplelogin.io/  
https://anonaddy.com/

These services create disposable email addresses that forward to your main inbox.  
You can disable or delete aliases individually, cutting off spam and tracking.  
Integrate them with ProtonMail for seamless operation.

---

### Privacy Focused Search Engines  
DuckDuckGo https://duckduckgo.com/  
Startpage https://www.startpage.com/  
Searx https://searx.space/

Search engines collect everything by default.  
DuckDuckGo and Startpage avoid personal data storage.  
Searx allows anyone to run a self hosted metasearch instance.  
All three preserve anonymity compared to Google or Bing.

---

### VPNs Use When Necessary Not Always  
Mullvad VPN https://mullvad.net/

A Virtual Private Network encrypts your connection between your device and a remote server, masking your IP from local observers such as ISPs or campus networks.  
Choose providers that publish audits and accept anonymous payment.  
Mullvad issues random account numbers instead of requiring email registration.  
Remember VPNs hide traffic from local observers, not from websites you visit.

---

### OnionShare Private File Sharing Without the Cloud  
https://onionshare.org/

OnionShare creates a temporary onion service on your computer that others can access through Tor Browser.  
No middleman, no cloud, no logs.  
It is ideal for transferring sensitive documents safely.  
The link expires when you close the application.

---

### ExifTool Removing Metadata Before Sharing  
https://exiftool.org/

Photos taken by phones and cameras embed hidden EXIF data such as GPS and timestamps.  
ExifTool can view and remove this information easily.

Example command  
```
exiftool -all= photo.jpg
```

Clean files reveal nothing except the image itself.

---

### Encrypted Backups Safety Without Exposure  
BorgBackup https://borgbackup.readthedocs.io/  
Duplicati https://www.duplicati.com/

Backups should be redundant and encrypted.  
BorgBackup handles deduplication and encryption for local or remote storage.  
Duplicati offers a simpler interface with built in AES256 encryption.  
Keep at least one offline copy on a separate drive and connect it only when updating.

---

### Operational Security The Human Factor

Software cannot save careless habits. Practical OpSec means

- Keep devices updated and patched  
- Do not mix personal and anonymous accounts  
- Disable Bluetooth and WiFi when not needed  
- Use screen locks and encrypted USB drives  
- Think before posting photos or sharing personal details  

Privacy is consistency more than complexity.

---

## Responsible Privacy and Legal Boundaries

Privacy tools defend autonomy, not lawlessness.  
In the United States, using encryption, Tor, or Tails is fully legal.  
What is illegal is using them to conceal crimes.

Practicing privacy strengthens journalism, research, and small business security.  
Kirksville's mix of students, researchers, and professionals deserves the same protection as any tech hub.  
Learning these systems means relying less on data brokers and more on verified code.

---

## The Modern Ghosts Checklist

1. Boot sensitive sessions from Tails  
2. Browse through Tor or hardened Firefox  
3. Use ProtonMail for private email  
4. Communicate with Signal  
5. Manage passwords in Bitwarden  
6. Add hardware authentication with YubiKey  
7. Encrypt disks with VeraCrypt or LUKS  
8. Remove metadata with ExifTool  
9. Keep encrypted backups with Borg or Duplicati  
10. Practice steady and consistent OpSec

---

## Further Reading and Resources

EFF Surveillance Self Defense  
https://ssd.eff.org/  

Tails Official Documentation  
https://tails.net/doc/index.en.html  

Tor Project Support Portal  
https://support.torproject.org/  

PrivacyTools.io  
https://www.privacytools.io/  

Proton Security Principles  
https://proton.me/security  

All of these are open, regularly updated, and respected by the security community.

---

## Closing

Full privacy is not about escaping the world. It is about participating in it safely.  
In Kirksville, where the local economy runs on education, healthcare, and small business, digital discretion protects livelihoods as much as personal life.

Switchboard Tech Services teaches these systems face to face.  
Privacy is not an urban luxury or a secret skill. It is the modern form of self reliance.

---

© Switchboard Tech Services Kirksville Missouri
