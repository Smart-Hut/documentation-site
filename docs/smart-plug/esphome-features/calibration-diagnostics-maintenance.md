# Calibration, Diagnostics, And Maintenance

This guide covers calibration controls, diagnostic sensors, local web access, OTA updates, Bluetooth proxy support, and reset options.

## Calibration

The plug is preconfigured for its power monitoring hardware. Calibration controls are available if you need to fine tune readings against a trusted reference meter.

Calibration controls:

- **Voltage Calibration Multiplier**
- **Current Calibration Multiplier**
- **Power Calibration Multiplier**

Leave these at `1` unless you have a known reference measurement.

How the multipliers work:

- Increase a multiplier to raise the reported value.
- Decrease a multiplier to lower the reported value.

Suggested use cases:

- Fine tune readings after comparing against a known accurate plug-in power meter.
- Correct small differences between the plug and another trusted measurement source.
- Align readings when using the plug for detailed dashboards or automations.

:::warning
Do not change calibration values randomly. Incorrect calibration can make power, energy, cost, standby, appliance detection, and high power automations unreliable.
:::

## Diagnostics

Diagnostic entities exposed by the firmware include:

- **WiFi Signal**
- **Uptime**
- **IP Address**
- **Connected SSID**
- **MAC Address**
- **ESPHome Version**

Suggested use cases:

- Use **WiFi Signal** to check whether the plug has a reliable connection.
- Use **Uptime** to spot unexpected restarts.
- Use **IP Address** when opening the local web interface.
- Use **ESPHome Version** when checking firmware compatibility.

Potential use cases:

- Alert if Wi-Fi signal drops below a reliable level.
- Track uptime after firmware updates or network changes.
- Identify the plug by MAC address when checking router settings.

## Local Web Interface

The firmware includes a local web server on port `80`. Once the plug is connected to Wi-Fi, browse to its IP address to view the ESPHome web interface.

Suggested use cases:

- Quickly check whether the plug is online.
- View device information from a browser on the same network.
- Help troubleshoot before checking Home Assistant.

## OTA Updates

The plug supports ESPHome over-the-air updates.

Suggested use cases:

- Update firmware without opening the plug.
- Apply future ESPHome changes through Home Assistant.
- Maintain custom ESPHome builds if you import the firmware YAML yourself.

Firmware package reference:

```text
github://Smart-Hut/Smart-Plug/ESPC2-02.yaml@v2.1.0
```

Source file: [ESPC2-02.yaml](https://github.com/Smart-Hut/Smart-Plug/blob/main/ESPC2-02.yaml)

## Restart And Factory Reset

Maintenance buttons:

- **Restart**: restarts the plug.
- **Restart with Factory Default Settings**: resets the plug back to factory defaults and restarts it.

Suggested use cases:

- Use **Restart** after network changes or if the plug is not responding as expected.
- Use **Restart with Factory Default Settings** only when you need to set the plug up again from scratch.

:::warning
Factory reset removes saved configuration from the plug. After a factory reset, the plug will need to be provisioned again.
:::

## Bluetooth Proxy And Provisioning

The firmware enables ESPHome Bluetooth proxy support and `esp32_improv` provisioning.

Suggested use cases:

- Use Bluetooth proxy to help Home Assistant communicate with supported Bluetooth devices near the plug.
- Use provisioning support during setup where supported by your ESPHome environment.

Bluetooth proxy availability depends on your Home Assistant and ESPHome setup. If you do not use Bluetooth devices, you can ignore this feature.
