# Sloth Browser

Sloth is a closed-source Android browser. The app draws pages with Gecko. This repository holds
signed installers only. There is no source code here and no signing key.

## Install

The current package is **1228**. It runs on Android 8 and later, and it targets Android 16.

[Download SlothBrowser-1228.apk](https://github.com/SirTibbles666one/Sloth-Browser-releases/releases/download/1222/SlothBrowser-1228.apk)

Install it over the previous build. Do not uninstall: the app's data, settings and tabs live in
its storage, and an uninstall takes them with it. Android asks you to confirm the install. A
phone already on a higher number will not take an older file.

Every build is signed with the same certificate, so any build installs over any other:

```
SHA-256 3d38d9070b9042b879eb96bbafe949e2dabbf8f6fc798bcc8d60149cd0a947af
```

The app checks this repository for a newer release. The latest file is named in
[version.json](https://github.com/SirTibbles666one/Sloth-Browser-releases/releases/latest/download/version.json).
Every published build is promoted, so that endpoint always names the newest one; older builds stay
in the list and install by hand if something needs rolling back.

## What it does

- Each page runs in its own process.
- Sloth Ad Block filters ads. Tracking protection is a separate switch.
- **The top bar and the drawer are one surface.** Drag the bar down and it grows into the
  dashboard; flick up and it closes. It rests at four sizes: shut, a short strip, the fitted
  content, and full.
- The strip is the tabs: close, one square per open tab, and a plus. Tap a square to switch,
  hold one to close it, swipe the row sideways to walk the tabs. A sideways flick across the bar
  itself also moves to the next or previous tab.
- Under the dashboard: a calculator, a clock, notes, live counters, and the browser's own tab row
  mirrored as cards.
- Ten palettes, each with its own colours, corner radii, material and painted backdrop — a
  vector forest and a sloth rather than image assets, so every palette gets artwork for free.
- Settings are the browser's real switches, bound by name to its own model: tracking, WebRTC,
  HTTPS-only, JavaScript, cookies, popups, autoplay, prefetch, Do Not Track, Global Privacy
  Control, fingerprint resistance, private-by-default, screenshots.
- Settings → Diagnostics reports the window, insets, bar and sheet heights, resting sizes, the
  address, the tab count, the page view's class and size, whether a Gecko session is attached,
  and anything drawn over the page — with COPY, SAVE, REFRESH and RELOAD PAGE.
- Crashes are captured before the process dies: type, message and the first frames, written to
  the log and to a file once per session.
- The Android back button is shell-aware: it closes diagnostics, then settings, then the drawer,
  then a panel opened inside the browser, and only then leaves the page.
- Video can play AV1, HEVC, VP9, MP4, and WebM. Encrypted video uses the Widevine already on the
  phone. None is bundled.
- Skins recolour the bar. The page keeps its own colours.

## Closed source

The browser is closed source. All rights reserved. You may install the signed package for your own
use. You may not copy or redistribute the source. Source is not published in this repository, and
the signed packages here are the only builds that exist.

## This repository

| File | What it is |
| --- | --- |
| `SlothBrowser-<n>.apk` | The signed install package for build `<n>` |
| `version.json` | The version the app reads when it checks for an update |

Build numbers run in plain integers, one per shipped package, from 1092 to the current 1228. A
number is never reused and never patched in place: a fix is the next number, so the phone can
always tell which build it is running.

## Known limits, stated plainly

- The thin strip, the drag feel and the palette artwork are judged on a phone, not in a harness.
  A build that changes how the surface moves is only verified when someone drags it.
- Bookmarks, History and Downloads are drawn by the app itself into a panel the shell lends it.
  If the app draws nothing, the panel is closed and the log says so rather than leaving a blank
  box on screen.
- There is no loading progress or Stop button: the app exposes no progress signal the shell can
  read, and a fake one would be worse than none.
