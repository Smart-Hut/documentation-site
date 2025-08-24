# ESPHome

You'll need to make sure you have:

- Your Wifi network name and password
- Another device like a laptop or smartphone to complete setup

## Plug in
Begin by plugging in your smart plug and waiting for the power LED to start flashing. This indicates the plug is in pairing mode and ready to connect to a wifi network.

## Connect to WiFi

Using your smartphone or laptop connect to the plugs temporary wifi network. This will start with `Smart hut Plug`.

You should be then presented with a setup web page 

![Image of Wifi setup page](/img/esphome/plug-docs/wifi-setup.png)

:::note
If you are not automatically shown the setup page you'll need to open your web browser and navigate to 192.168.4.1
:::

Select your Wi-Fi network and enter your Wi-Fi network details. You'll then be disconnected from the temporary Wi-Fi network and the power light on the plug should turn off.

## Connecting to Home Assistant

Your plug this should be automatically detected in Home Assistant in the **Devices** section of the settings pag or via a auto discovery notification.

![Discovery notification](/img/esphome/plug-docs/new_devices_discovered.png)

You can then add the plug

![Add devices](/img/esphome/plug-docs/Add_Device.png)

Then Submit the configuration that's presented in the dialog

![Configure](/img/esphome/plug-docs/config_dialog.png)

Your device should now be configured and added to Home Assistant