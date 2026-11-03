# AwesomeBrowse 2

A clean, themeable, Chromium-based browser built on PyQt6 and Qt WebEngine.

## Features

- Sleek floating-tab interface with 29 themes and matching wallpapers
- Tab groups, split view (dwindle tiling), and workspaces
- Chrome extension support (content scripts, storage, i18n)
- Built-in RAM limiter with graceful degradation
- YouTube Music player in the sidebar with a pinnable mini player
- Reader mode, focus mode, command palette, notes, web panels
- Three editions: 2.1.1 Stable, 2.1.0 Nightly, 2.0.0 Legacy

## System requirements

Python 3.10+, plus Qt system libraries on Linux.

Debian / Ubuntu:

    sudo apt install python3 python3-venv \
        libnss3 libasound2 libxkbcommon-x11-0 libgl1 \
        libxcb-cursor0 libxcb-icccm4 libxcb-keysyms1 \
        libxcb-shape0 libxcb-xinerama0 libxcb-xkb1

Fedora:

    sudo dnf install python3 python3-virtualenv \
        nss alsa-lib libxkbcommon-x11 mesa-libGL \
        xcb-util-cursor xcb-util-wm

Arch:

    sudo pacman -S python nss alsa-lib libxkbcommon xcb-util-cursor \
        xcb-util-wm gl

## Install

    git clone https://github.com/amarjeetkaurbittu1982-ai/awesomebrowse.git
    cd awesomebrowse
    ./install.sh

That creates a virtual environment, installs the Python dependencies, and
adds a launcher and application-menu entry.

Run it with:

    awesomebrowse
If that fails:

    python3 awesomebrowse

Or with flags:

    awesomebrowse --private
    awesomebrowse --profile <id>
    awesomebrowse --safe-mode

## Uninstall

    rm ~/.local/bin/awesomebrowse
    rm ~/.local/share/applications/awesomebrowse.desktop
    rm -rf .venv

Profile data lives at ~/.local/share/AwesomeBrowse2/. Delete that folder
too if you want to remove everything.

## Known limitations

- The hard heap cap relies on Chromium flags honoured by your QtWebEngine
  build. If your distro patches QtWebEngine, the cap may be silently ignored.
- Chrome extensions are supported through a compatibility layer (content
  scripts, chrome.storage, chrome.runtime, chrome.i18n). Anything depending
  on a background service worker, webRequest blocking, or native messaging
  will install but stay idle.
- Tab sleeping uses Chromium's Discarded lifecycle state. A tab with unsaved
  form data can lose that data when slept.
- Many features are broken/don't work properly, and I am aware of this and\
  constantly working on fixing it. I appreciate any help!
- Some CAPTCHAS may not work, but most sign ins are fine. 
## Licence

GPL-3.0. See LICENSE.
README_END
