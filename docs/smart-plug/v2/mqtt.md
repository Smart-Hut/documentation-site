---
sidebar_position: 3
---

# Tasmota V2 MQTT

You will need a working [MQTT broker](https://www.hivemq.com/mqtt/) before enabling MQTT integration.

From the Tasmota v2 main menu, open `MQTT`.

On this firmware, the `MQTT enable` checkbox lives on the `Other parameters` page rather than in a separate MQTT-only screen.

![Tasmota v2 MQTT settings](/img/tasmota-v2/mqtt.png)

For newer Smart Hut plugs:

- Ensure `MQTT enable` is checked
- Set `Device Name` and `Friendly Name 1` if you want a friendlier label in your automation system
- Click `Save`

If your workflow also needs broker host, username, password, or topic settings, confirm whether your firmware build exposes an additional MQTT configuration page after enabling MQTT.
