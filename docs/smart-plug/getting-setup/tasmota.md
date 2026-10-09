# Tasmota

Tasmota provides a wireless access point for easy Wi-Fi configuration.

Connect your device to a power source and grab your smartphone, tablet, laptop, or another web and Wi-Fi capable device. Search for the temporary Tasmota Wi-Fi network and connect to it.

Depending on the firmware version, the network may be named like one of these examples:

- `smarthutpm-XXXXXX`
- `smarthutplug_XXXXXX-####`
- `tasmota_XXXXXX-####`

`XXXXXX` is derived from the device MAC address.

When it connects to the network, you may get a warning that there is no Internet connection and be prompted to connect to a different network. Do not allow the mobile device to select a different network.

:::warning
Wi-Fi manager server is active for only 3 minutes. If you miss the window you might have to disconnect your device from power and reconnect.
:::

After you have connected to the Tasmota Wi-Fi AP, open http://192.168.4.1 in a web browser on the smartphone (or whatever device you used). Depending on the phone, it will take you to the Tasmota configuration page automatically, or you will get a prompt to sign in to Wi-Fi network or authorize. Tapping on the AP name should also open the configuration page.

At the top of the page you can select one of the discovered Wi-Fi networks or have Tasmota scan again. Enter your Wi-Fi credentials:

- **WiFi Network**: your Wi-Fi network name. Selecting the desired network from the list will enter it automatically. SSIDs are case sensitive.

- **WiFi Password**: your Wi-Fi network password. The password must be fewer than 64 characters.

Click the checkbox if you want to see the password you enter to ensure that it is correct. Click on Save to apply the settings. The device will try to connect to the network entered.

Some phones will redirect you to the new IP immediately, on others you need to click the link to open it in a browser.

The temporary Tasmota network will no longer be present. Your phone or laptop will disconnect and should return to its normal network.

:::danger[Failure to connect to WiFi]
In case the network name or password were entered incorrectly, or it didn't manage to connect for some other reason, Tasmota will return to the "Wi-Fi parameters" screen with an error message.
:::

If you do not know the IP address of the plug, check your router settings or find it with an IP scanner:

- [Fing](https://www.fing.com/products/) - for Android or iOS
- [Angry IP Scanner](https://angryip.org/) - open source for Linux, Windows and Mac. Requires Java.
- [Super Scan](https://sectools.org/tool/superscan/) - Windows only (free)
  
Open the IP address with your web browser to access Tasmota.

## Newer Smart Hut Tasmota Firmware

Newer Smart Hut plugs use a custom Tasmota interface with dedicated buttons for `WiFi`, `MQTT`, `Matter`, `Information`, `Advanced`, and `Restart`.

For the newer interface, see the [Tasmota V2 guides](../v2/overview.md).

## After Connection

Your device running Tasmota is now ready to be controlled.

Useful next steps:

- Use [Matter](../Integrations/matter.md) if you want to add the plug to a Matter controller.
- Use [MQTT](../Integrations/mqtt.md) if you want to integrate through MQTT or the Home Assistant Tasmota integration.
- Review the official Tasmota [commands](https://tasmota.github.io/docs/Commands/) and [features](https://tasmota.github.io/docs/Features/) if you need advanced control.
