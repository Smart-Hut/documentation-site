# ESPHome

The ESPHome Smart Hut plug firmware is designed to work with Home Assistant and exposes the relay, power monitoring, automation helpers, diagnostics, and configuration controls as Home Assistant entities.

Firmware source: [Smart-Hut/Smart-Plug](https://github.com/Smart-Hut/Smart-Plug)

## What You Need

- Your 2.4 GHz Wi-Fi network name and password
- A phone, tablet, or laptop to complete Wi-Fi setup
- Home Assistant with the [ESPHome integration](https://www.home-assistant.io/integrations/esphome/)

:::info
ESPHome is intended to be used with Home Assistant. If the plug is not connected to Home Assistant, ESPHome devices can restart periodically while they try to reconnect to the native API.
:::

## First Power On

Plug in your smart plug and wait for the power LED to start flashing. This means the plug is in setup mode and is ready to connect to Wi-Fi.

The plug will create a temporary Wi-Fi network named `Smart hut Plug` if it cannot connect to a saved Wi-Fi network.

## Connect To Wi-Fi

Using your phone, tablet, or laptop, connect to the temporary `Smart hut Plug` Wi-Fi network.

You should then be shown the setup page.

![Image of Wifi setup page](/img/esphome/plug-docs/wifi-setup.png)

:::note
If the setup page does not open automatically, open a browser and go to `http://192.168.4.1`.
:::

Select your Wi-Fi network and enter your Wi-Fi password. After saving, your device will disconnect from the temporary Wi-Fi network and the plug will connect to your home network.

## Add The Plug To Home Assistant

Once the plug is on your Wi-Fi network, Home Assistant should discover it automatically through the ESPHome integration. You can add it from **Settings** > **Devices & services**, either from the discovered device notification or from the ESPHome integration.

![Discovery notification](/img/esphome/plug-docs/new_devices_discovered.png)

Select the plug and add it.

![Add devices](/img/esphome/plug-docs/Add_Device.png)

Submit the configuration shown in the dialog.

![Configure](/img/esphome/plug-docs/config_dialog.png)

Your device should now appear in Home Assistant with the relay switch, sensors, buttons, and configuration entities listed below.

## Main Controls

### Plug Relay

The main switch entity controls power to the socket. Turning this switch on powers the connected device, and turning it off cuts power to the socket.

### Physical Button

The button on the plug supports three actions:

- Single press: toggle the plug relay on or off
- Double press: cycle the power loss behaviour option
- Long press, from 1 to 5 seconds: cycle the LED behaviour option

Enable **Local Button Lock** if you do not want the physical button to change the relay or settings. This can be useful where the plug may be touched accidentally.

## Power Monitoring

The plug includes live and historical power monitoring.

Available measurement sensors:

- **Voltage**: current mains voltage
- **Current**: current draw in amps
- **Power**: current load in watts
- **Energy**: raw energy reading in watt-hours
- **Daily Energy**: energy used today in kWh
- **Lifetime Energy**: total tracked energy in kWh

These sensors can be used in Home Assistant dashboards, Energy dashboards, and automations.

## Cost Tracking

Set **Electricity Rate** to your energy price in `GBP/kWh` to enable cost estimates.

Cost sensors:

- **Today Cost**: estimated cost for today's usage
- **Lifetime Cost**: estimated cost for lifetime tracked usage

For example, if your electricity price is 30 pence per kWh, set **Electricity Rate** to `0.30`.

## Power Loss Behaviour

Use **Power loss behaviour** to choose what the relay does after a power cut, reboot, or firmware restart.

Options:

- **OFF**: the plug always starts with the relay off
- **ON**: the plug always starts with the relay on
- **Restore last state**: the plug returns to the relay state it had before power was lost

Use **Power Restore Delay** to delay the relay action after boot. This is set in seconds and can be useful if you want multiple devices to come back online gradually after a power cut.

## LED Behaviour

Use **LED Behaviour** to choose how the plug LED behaves.

Options:

- **Relay state**: LED follows whether the relay is on or off
- **Always off**: LED stays off
- **Always on**: LED stays on

You can also cycle this setting with a long press of the physical button unless **Local Button Lock** is enabled.

## Auto-Off Timer

Auto-off turns the relay off after a set amount of time.

To use it:

1. Set **Auto Off Minutes** to the required run time.
2. Turn on **Auto Off Enabled**.
3. Turn on the plug relay.

When the timer expires, the relay turns off automatically. This is useful for chargers, heaters, lamps, and other devices that should not be left on indefinitely.

## Standby Killer

Standby killer turns the plug off when the connected device drops to a low standby power level for long enough.

To use it:

1. Set **Standby Threshold** to the maximum power level that should count as standby.
2. Set **Standby Killer Delay** to how long the device must remain in standby before being turned off.
3. Turn on **Standby Killer Enabled**.

The plug only starts the standby timer when the relay is on and power is above `0.1 W` but less than or equal to the standby threshold.

The **Standby Detected** binary sensor shows when the current load is being treated as standby.

## Appliance Detection

Appliance detection is designed for appliances with a clear high-power running phase and a low-power finished phase, such as washing machines, tumble dryers, and dishwashers.

To use it:

1. Set **Appliance Running Threshold** to the power level that means the appliance has started running.
2. Set **Appliance Finished Threshold** to the power level that means the appliance has finished.
3. Set **Appliance Finished Delay** to how long the appliance must stay below the finished threshold before being marked finished.
4. Turn on **Appliance Detection Enabled**.

Status sensors:

- **Appliance Running**: turns on after the appliance has exceeded the running threshold
- **Appliance Finished**: turns on after the appliance has later stayed below the finished threshold for the configured delay

These sensors are useful for Home Assistant notifications, such as sending an alert when a washing machine cycle has finished.

## Detection Helpers

The firmware exposes additional binary sensors for automations.

- **Load Detected**: on when power is at or above **Load Detected Threshold**
- **Standby Detected**: on when the relay is on and power is at or below **Standby Threshold**
- **High Power**: on when power is at or above **High Power Threshold**

You can adjust the thresholds in Home Assistant to match the device plugged in.

## Calibration

The plug is preconfigured for the built-in power monitoring hardware, but Home Assistant exposes calibration multipliers if you need to fine tune readings against a trusted meter.

Calibration controls:

- **Voltage Calibration Multiplier**
- **Current Calibration Multiplier**
- **Power Calibration Multiplier**

Leave these at `1` unless you have a known reference measurement. Increasing a multiplier raises the reported value; decreasing it lowers the reported value.

## Diagnostics And Maintenance

Diagnostic entities exposed by the firmware include:

- **WiFi Signal**
- **Uptime**
- **IP Address**
- **Connected SSID**
- **MAC Address**
- **ESPHome Version**

Maintenance buttons:

- **Restart**: restarts the plug
- **Restart with Factory Default Settings**: resets the plug back to factory defaults and restarts it

:::warning
Factory reset removes saved configuration from the plug. Use it only if you need to set the plug up again from scratch.
:::

## Web Page And OTA Updates

The firmware includes a local web server on port `80`. Once the plug is connected to Wi-Fi, you can browse to its IP address to view the ESPHome web interface.

The plug also supports ESPHome over-the-air updates. If you manage the plug through ESPHome in Home Assistant, you can update firmware without opening the plug.

## Bluetooth Proxy And Provisioning

The firmware enables ESPHome Bluetooth proxy support and `esp32_improv` provisioning. Bluetooth proxy allows the ESP32-C3 in the plug to help Home Assistant communicate with supported Bluetooth devices nearby.

Bluetooth proxy availability depends on your Home Assistant and ESPHome setup. If you do not use Bluetooth devices, you can ignore this feature.

## Custom Firmware Source

Advanced users can review or import the full ESPHome YAML from the firmware repository:

```text
github://Smart-Hut/Smart-Plug/ESPC2-02.yaml@v2.1.0
```

Source file: [ESPC2-02.yaml](https://github.com/Smart-Hut/Smart-Plug/blob/main/ESPC2-02.yaml)

The firmware uses an ESP32-C3, a BL0937-compatible power monitoring chip, a relay, an LED, and a local button. The shipped configuration should be used unless you know you need to maintain a custom ESPHome build.
