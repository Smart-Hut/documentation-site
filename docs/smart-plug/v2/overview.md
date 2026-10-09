---
sidebar_position: 1
---

# Tasmota V2 Overview

These pages cover the newer custom Tasmota interface used on newer Smart Hut plugs.

The existing Tasmota pages elsewhere in the Smart Plug docs are still valid for older shipped plugs with the earlier UI.

## What is different

- The main menu exposes dedicated buttons for `WiFi`, `MQTT`, `Matter`, `Information`, `Advanced`, and `Restart`.
- Advanced options such as configuration, firmware upgrade, console, and tools sit behind the `Advanced` page.
- Firmware upgrade now includes an explicit risk acknowledgement before OTA or file upload upgrades can continue.
- Risky stock Tasmota options such as module, template, backup, and restore configuration are hidden from the normal configuration page.
- Smart Hut defaults are built in, including the plug template, default hostname, default MQTT topic, Matter support, and reset protection.
- The setup flow is still the same at a high level, but the page layout differs from stock Tasmota and older shipped firmware.

![Tasmota v2 main menu](/img/tasmota-v2/main-menu.png)

Start with [Custom Tasmota Firmware](./custom-firmware.md) if you want to understand the Smart Hut-specific changes before configuring Wi-Fi, MQTT, or Matter.

## V2 Pages

```mdx-code-block
import DocCardList from '@theme/DocCardList';

<DocCardList />
```
