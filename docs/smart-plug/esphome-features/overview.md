# ESPHome Feature Guides

The ESPHome Smart Hut plug firmware exposes more than a simple on/off switch. These guides explain what each feature does, when to use it, and the settings to check first.

Firmware source: [Smart-Hut/Smart-Plug](https://github.com/Smart-Hut/Smart-Plug)

## Feature Guides

- [Relay, button, LED, and power restore](./relay-button-led-power-restore.md)
- [Power monitoring and cost tracking](./power-monitoring-cost.md)
- [Auto-off and standby killer](./auto-off-standby-killer.md)
- [Appliance detection](./appliance-detection.md)
- [Detection helpers and Home Assistant automations](./detection-helpers-automations.md)
- [Calibration, diagnostics, and maintenance](./calibration-diagnostics-maintenance.md)

## Recommended First Checks

After adding the plug to Home Assistant, review these settings first:

- **Power loss behaviour**: choose whether the plug starts off, starts on, or restores its last state after a power cut.
- **LED Behaviour**: choose whether the LED follows relay state, stays off, or stays on.
- **Electricity Rate**: set your price in `GBP/kWh` if you want cost estimates.
- **Auto Off Enabled** and **Auto Off Minutes**: use this for devices that should not be left running indefinitely.
- **Local Button Lock**: enable this if the plug is somewhere the button may be pressed accidentally.

## Suggested Use Cases

- Chargers: use auto-off to stop charging after a chosen time.
- Washing machines and tumble dryers: use appliance detection to notify when a cycle has finished.
- TVs and media equipment: use standby killer to turn equipment off after it drops to low standby power.
- Heaters or dehumidifiers: use auto-off as a safety backstop.
- Energy monitoring: use daily and lifetime energy sensors to understand running costs.
- Presence-sensitive areas: use LED behaviour and local button lock to prevent unwanted light or accidental switching.

## Notes Before You Change Settings

Power readings vary between appliances. Threshold-based features such as standby killer, load detection, high power detection, and appliance detection work best after you observe the connected device's normal power usage for a few cycles.

Start with conservative settings, test them while you are nearby, and then adjust thresholds once you know the device's real behaviour.
