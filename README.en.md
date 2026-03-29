# BlePlay

[中文](./README.md) | English

BlePlay is a Qt6 Widgets desktop tool for offline BLE trace analysis. It is designed for inspecting `.btt`, `btsnoop`, and `.pklg` logs in workflows such as Bluetooth protocol debugging, connection troubleshooting, and GATT behavior analysis, helping users move quickly from raw captures to readable protocol events, session context, and attribute structure.

## Features

- Import BLE and HCI trace files such as `.btt`, `btsnoop`, and `.pklg`
- Provide three main working views: `Packets`, `Sessions`, and `GATT Map`
- Filter by protocol, device, connection, handle, error state, and free text
- Inspect per-packet decoded fields together with raw hex bytes
- Jump from session or GATT views back to the related packets

## Use Cases

- Analyze BLE or HCI traces exported from Android, iOS, or Ellisys tools
- Investigate pairing failures, connection issues, and disconnect problems
- Trace ATT, SMP, and LL Control interactions in protocol order
- Inspect service, characteristic, descriptor, and handle discovery or access behavior

## Interface Overview

BlePlay currently provides three core working views:

- `Packets`: for packet-by-packet browsing, filtering, detail-tree inspection, and hex data review
- `Sessions`: for understanding timing, roles, and major events by connection or session
- `GATT Map`: for browsing services, characteristics, descriptors, and their related packets

The main window is built around one shared analysis document. The views can jump to one another, which makes it practical to move from packet-level detail to session context or GATT structure within a single investigation flow.

## Demo Screenshots

Shown in the order of main view, session view, and GATT view:

![Main view](./demo/main.png)

![Session view](./demo/session.png)

![GATT view](./demo/gatt.png)

## Ubuntu Desktop Installation

The Linux package directory `BlePlay-<version>-linux-x86_64/` includes `install.sh`, which installs the BlePlay executable, desktop launcher, and icon. In practice, you can use a wildcard path to match the current version directory directly.

The script provides the following:

- Performs a user-level install by default
- Installs the app payload, command entry, and `.desktop` launcher into the user directory

Example:

```bash
chmod +x ./BlePlay-*-linux-x86_64/install.sh
./BlePlay-*-linux-x86_64/install.sh
```

Run the script directly if you want to inspect its available options.

## Project Positioning

BlePlay focuses on desktop BLE trace analysis with the following priorities:

- Built with Qt to keep a consistent experience across platforms such as Linux and Windows
- Positioned as a protocol analysis workbench rather than a single-view packet browser
- Backed by one shared business document so multiple views can reuse the same analysis results
