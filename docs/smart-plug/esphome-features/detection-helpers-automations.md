# Detection Helpers And Automations

The firmware exposes helper sensors that make Home Assistant automations easier without needing to write complex templates.

## Helper Sensors

Available binary sensors:

- **Load Detected**: on when power is at or above **Load Detected Threshold**.
- **Standby Detected**: on when the relay is on and power is at or below **Standby Threshold**.
- **High Power**: on when power is at or above **High Power Threshold**.

Adjustable thresholds:

- **Load Detected Threshold**
- **Standby Threshold**
- **High Power Threshold**

## Load Detected

Use **Load Detected** when you need to know whether the connected device is drawing meaningful power.

Suggested use cases:

- Detect whether a lamp, fan, charger, or appliance is actually active.
- Trigger an automation when a device starts using power.
- Show a dashboard badge that confirms a connected device is running.

Example settings:

- Small charger: set **Load Detected Threshold** around `2 W` to `5 W`.
- Lamp or fan: set it around `5 W` to `20 W`.
- Large appliance: set it around `20 W` to `100 W` depending on normal usage.

## Standby Detected

Use **Standby Detected** to identify low power draw while the relay is still on.

Suggested use cases:

- Show that a TV or media system has entered standby.
- Trigger a notification before standby killer turns the plug off.
- Start a separate Home Assistant timer before switching off related devices.

## High Power

Use **High Power** to identify when a connected load reaches or exceeds a configured wattage.

Suggested use cases:

- Alert if an appliance uses more power than expected.
- Detect when a heater, kettle, iron, or dryer is actively heating.
- Flag potentially unsafe or unusual usage patterns.

Example settings:

- Heater: set **High Power Threshold** around the expected heating wattage.
- Tumble dryer: set it below the normal drying load if you want to detect active drying.
- General safety alert: set it slightly above the expected maximum for the device.

## Automation Ideas

- If **High Power** stays on too long, send an alert.
- If **Load Detected** turns off for 30 minutes, turn off the relay.
- If **Standby Detected** turns on in the evening, switch off media equipment.
- If **Power** rises above a threshold unexpectedly, notify a phone.
- If **Daily Energy** exceeds a target, send a usage warning.

## Suggested Testing Method

1. Watch the live **Power** sensor while using the connected device normally.
2. Record idle, standby, normal running, and peak values.
3. Set helper thresholds between those observed values.
4. Test automations with notifications first before allowing them to turn devices off.

## Potential Use Cases

- Energy budgeting for high-use devices.
- Device health monitoring when power patterns change.
- Confirmation that a scheduled device actually started.
- Alerts for equipment accidentally left running.
