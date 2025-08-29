# Tasmota

Tasmota provides a wireless access point for easy Wi-Fi configuration.

Connect your device to a power source and grab your smartphone (or tablet or laptop or any other web and Wi-Fi capable device). Search for a Wi-Fi AP named smarthutplug_XXXXXX-#### (where XXXXXX is a string derived from the device's MAC address and #### is a number) and connect to it. In this example the Wi-Fi AP is named smarthutplug_3D5E26-7718.

When it connects to the network, you may get a warning that there is no Internet connection and be prompted to connect to a different network. Do not allow the mobile device to select a different network.

:::warning
Wi-Fi manager server is active for only 3 minutes. If you miss the window you might have to disconnect your device from power and reconnect.
:::

After you have connected to the Tasmota Wi-Fi AP, open http://192.168.4.1 in a web browser on the smartphone (or whatever device you used). Depending on the phone, it will take you to the Tasmota configuration page automatically, or you will get a prompt to sign in to Wi-Fi network or authorize. Tapping on the AP name should also open the configuration page.

At the top of the page you can select one of the discovered Wi-Fi networks or have Tasmota scan again. Enter your WiFi credentials:

WiFi Network - your Wi-Fi network name (SSID Selecting the desired network name from the list will enter it automatically in this field. SSID's are case sensitive

WiFi Password - password for your Wi-Fi network
Wi-Fi password has to be under 64 characters and without special characters (e.g. asterisks) or white spaces

Click the checkbox if you want to see the password you enter to ensure that it is correct. Click on Save to apply the settings. The device will try to connect to the network entered.

Some phones will redirect you to the new IP immediately, on others you need to click the link to open it in a browser.

The tasmota_XXXXXX-#### network will no longer be present. Therefore your smartphone will automatically be disconnected and should connect back to its data network.

:::danger[Failure to connect to WiFi]
In case the network name or password were entered incorrectly, or it didn't manage to connect for some other reason, Tasmota will return to the "Wi-Fi parameters" screen with an error message.
:::

If you don't know the IP of the newly flashed device look in your router settings or find it with an IP scanner:

- [Fing](https://www.fing.com/products/) - for Android or iOS
- [Angry IP Scanner](https://angryip.org/) - open source for Linux, Windows and Mac. Requires Java.
- [Super Scan](https://sectools.org/tool/superscan/) - Windows only (free)
  
Open the IP address with your web browser and you have full access to Tasmota.

## After Connection

Your device running Tasmota is now ready to be [controlled](https://tasmota.github.io/docs/Commands/).

Check out all the Tasmota [features](https://tasmota.github.io/docs/Features/) and ways to [integrate it](https://tasmota.github.io/docs/Integrations/) with other platforms.