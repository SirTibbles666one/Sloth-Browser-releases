# Sloth Browser

Sloth is a closed-source Android browser. The app draws pages with Gecko. This repository holds signed installers only. There is no source code here and no signing key.

## Install

The current package is 986. It runs on Android 8 and later, and it targets Android 16.

[Download SlothBrowser-986.apk](https://github.com/SirTibbles666one/Sloth-Browser-releases/releases/download/986/SlothBrowser-986.apk)

Install it over the previous build. Do not uninstall. A phone already on a higher number will not take an older file. Android asks you to confirm the install.

The app checks this repository for a newer release. The latest file is named in [version.json](https://github.com/SirTibbles666one/Sloth-Browser-releases/releases/latest/download/version.json).

## What it does

- Each page runs in its own process.
- Sloth Ad Block filters ads. Tracking protection is a separate switch.
- The top bar and the drawer are yours to arrange. Hold Edit the bar, then drag a button left of the address, right of it, or into the drawer. A full row scrolls. The address stays.
- Open tabs show as cards. Drag one card onto another to group them. Ungroup leaves the tabs open.
- The drawer can hold calculator, clock, note, and password squares.
- Video can play AV1, HEVC, VP9, MP4, and WebM. Encrypted video uses the Widevine already on the phone. None is bundled.
- Skins recolor the bar. The page keeps its own colors.

## Closed source

The browser is closed source. All rights reserved. You may install the signed package for your own use. You may not copy or redistribute the source. Source is not published in this repository.

## This repository

| File | What it is |
| --- | --- |
| `SlothBrowser-986.apk` | The signed install package |
| `version.json` | The version the app reads when it checks for an update |
