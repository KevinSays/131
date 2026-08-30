# The OSI Company — Teaching Kit

An anime/workplace-procedural approach to teaching the OSI model to freshman
networking students. Every layer is a department in the same company; every
common network attack is a recurring villain-of-the-week. Built for classroom
handouts, lecture read-alouds, and Wireshark labs on a NETLAB+/Proxmox range.

## Files

- `osi-company-directory.html` — Personnel directory. One "case file" card per
  OSI layer (L7→L1): department name, duty, PDU, signature protocols, real
  gear tie-in, and an incident-report stub previewing that layer's villain.
- `osi-security-bulletin.html` — Wanted-poster board. One bulletin per
  villain: MO, tools of the trade, countermeasure, threat level, and a
  cross-reference back to its department's IR number.
- `osi-episode-01-script.html` — Shooting script, "One Request, Seven Desks."
  Narrates encapsulation (down the stack) and decapsulation (up the stack) as
  a request travels through all seven departments, with a teaching-note
  callout per scene and a Wireshark show-and-tell (including the HTTPS/TLS
  twist, where Session and Presentation hide in a live capture).
- `osi-episode-02-script.html` — Shooting script, "The Impersonator" (ARP
  spoofing). First villain episode: mechanism, damage report, detection and
  defense (introduces the recurring NOC character), and a repair checklist.

## Design system

Shared across all four files — reuse these if you extend the set.

**Palette**
| Token | Hex | Use |
|---|---|---|
| `--paper` | `#EDE8DD` | Card/document background |
| `--canvas` | `#D9D2C3` | Page background |
| `--ink` | `#1F2421` | Body text, borders |
| `--kraft` | `#B08554` | Folder tabs, stat labels |
| `--blue` | `#2F4858` | "Operative" stamps, teaching notes, NOC |
| `--red` | `#A23A2E` | Incident stamps, villain accents |

**Type** (Google Fonts, loaded via `<link>` in each file's `<head>`)
- Display / stamps / character names: `Special Elite` (typewriter)
- Body prose: `IBM Plex Sans`
- Data, labels, protocol/filter text: `IBM Plex Mono`

**Recurring conventions**
- Folder-tab / pin / stamp elements for card headers, offset hard-shadow
  (`5px 5px 0 rgba(31,36,33,0.16)`) instead of soft blur shadows
- Dashed rules (`2px dashed`) for tear-off / perforated sections
- `@media print` rules already included in each file for handout printing

## Cast reference

**Departments (Layer 7 → 1):** Front Desk · Translation & Wardrobe ·
Scheduling · Shipping & Receiving (TCP = Certified Mail Clerk, UDP = Bike
Courier) · Logistics · Local Dispatch · Infrastructure Crew

**Villains (IR-07 → IR-01):** The Con Artist (phishing, L7) · The
Eavesdropper (packet sniffing, L6) · The Impostor (session hijacking, L5) ·
The Flood (DoS/DDoS, L4) · The Forger (IP spoofing, L3) · The Impersonator
(ARP spoofing, L2 — Episode 02) · The Saboteur (physical tampering, L1)

**Recurring defender:** The NOC — introduced in Episode 02, monitors ARP
tables/switch logs across departments, first response to any incident.

## Open threads

- Episode 02 has no show-and-tell yet — natural pairing is a live
  ARP-spoofing + Dynamic ARP Inspection demo on the range.
- Episode 03 villain not yet chosen. Strongest "damage you can watch happen"
  candidates: The Flood (SYN flood + Statistics→Conversations demo), The
  Forger (spoofed source IP + traceroute/TTL demo), The Eavesdropper
  (cleartext capture demo, ties back to Episode 01's TLS twist).
