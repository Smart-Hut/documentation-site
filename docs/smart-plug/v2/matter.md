---
sidebar_position: 5
---

# Tasmota V2 Matter

Newer Smart Hut Tasmota plugs include Matter support and expose Matter configuration directly from the main menu.

Open `Matter` from the main menu, then use the `Matter enable` checkbox if you need to re-enable commissioning.

![Tasmota v2 Matter settings](/img/tasmota-v2/matter.png)

After saving, the plug restarts and opens Matter commissioning for a limited time.

If commissioning is active, the pairing information appears on the plug's main interface after the restart.

Use the QR code or manual pairing code from the plug page to add it to your Matter controller, such as Apple Home, Google Home, SmartThings, or Home Assistant.

## Advanced Matter Options

The `Advanced Configuration` button under the Matter page opens a minimal advanced page for Matter-specific actions.

Use advanced Matter options only if you need to inspect fabrics, remove a pairing, or troubleshoot commissioning.

## Related UI

The newer firmware also splits advanced tools into separate pages:

![Tasmota v2 advanced page](/img/tasmota-v2/advanced.png)

![Tasmota v2 tools page](/img/tasmota-v2/tools.png)
