---
sidebar_position: 2
---

# Tasmota V2 Wi-Fi Setup

Tasmota still provides a temporary wireless access point for first-time setup.

Connect the plug to power, then join the temporary Tasmota Wi-Fi network from your phone or laptop. If your device does not automatically open the setup portal, browse to `http://192.168.4.1`.

On the v2 Wi-Fi page:

- Select one of the detected Wi-Fi networks, or click `Scan for all WiFi Networks`
- Enter your Wi-Fi password
- Optionally fill in `WiFi Network 2` and its password as a fallback network
- Leave `Hostname` as-is unless you specifically need to rename it
- Click `Save`

![Tasmota v2 Wi-Fi setup](/img/tasmota-v2/wifi.png)

After saving, the plug will connect to your network and the temporary Tasmota access point will disappear.

:::danger[Failure to connect]
If the SSID or password is wrong, the plug will return to the Wi-Fi page so you can try again.
:::
