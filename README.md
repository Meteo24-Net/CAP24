# CAP24

CAP24 is a visual alert overlay for TV channels, IPTV operators and OTT services. It shows official public-safety alerts published in [OASIS CAP 1.2](https://docs.oasis-open.org/emergency/cap/v1.2/CAP-v1.2.html). It displays alerts as the issuing authority published them. It does not create, classify, translate or change alert content.

This repository holds the **open visual layer** of CAP24: the overlay HTML, its layout and its visual alert language.

## Status

**This is a demonstration. It is not on air, and it is not connected to any live alert feed.**

- The overlay has not been reviewed or approved by any national warning authority.
- Every screen carries a `NOT FOR BROADCAST` watermark. Every message is labelled with the kind of data it carries.
- No alert-relay component is in production.

## What is here

| File | What it is |
|---|---|
| `demo_cap_enhanced_8.html` | TV overlay demo, version 8. A single self-contained file that runs as a browser page or an OBS browser source. |

### Demo data

| Set | Data | Notes |
|---|---|---|
| Estonia (EE) | Simulated | Not issued, sent or reviewed by any Estonian authority. |
| Georgia (GE) | Simulated | Not issued, sent or reviewed by any Georgian authority. |
| Norway (NO) | Archived real | Two MET Norway MetAlerts messages from October 2025. They are replayed as a test fixture and are not current. Using them does not imply any endorsement by MET Norway. |

## Running the demo

Open `demo_cap_enhanced_8.html` in a current browser, or add it to OBS as a browser source.

| Key | Action |
|---|---|
| `1` `2` `3` | Switch between Estonia, Georgia and Norway |
| `→` `←` | Next or previous message |
| `Q` | Show the per-alert page that the QR code points to |

The overlay itself works offline. The map background tiles need a network connection.

## Display rules the overlay follows

- `headline`, `description`, `instruction` and `areaDesc` are shown verbatim, in full. They are never translated, summarised or shortened.
- `severity`, `urgency` and `certainty` are shown as sent.
- The warning level comes from the source's declared level parameter. If there is none, it comes from `severity`. The screen says which one was used.
- Pictograms come only from `responseType`.
- Areas are drawn from `<polygon>` as sent, or looked up from `<geocode>`.
- `expires` decides when an alert leaves the screen.

## Ownership and licence

The open visual layer is owned by **MTÜ Green Media Foundation** (GMF), an Estonian non-profit (registry code 80661721).

No open-source licence has been chosen yet. Until a `LICENSE` file is added, all rights are reserved by GMF.

Components that are not part of the open layer are not in this repository. These include the authority panel, the QR-to-phone service and the relay infrastructure.

## Third-party material

| Material | Licence |
|---|---|
| Leaflet 1.9.4 | BSD-2-Clause |
| qrcodejs 1.0.0 | MIT |
| Barlow, Barlow Condensed, Share Tech Mono fonts | SIL Open Font License |
| MET Norway warning data | CC BY 4.0 / NLOD 2.0 |
| Yr warning icons © 2015 Yr/NRK | CC BY 4.0, unmodified |
| Natural Earth boundaries | Public domain |
| Map tiles | © OpenStreetMap contributors, © CARTO |

## Contact

MTÜ Green Media Foundation, Estonia.
