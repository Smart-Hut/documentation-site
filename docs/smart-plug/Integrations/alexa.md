# Amazon Alexa

You can control a Smart Hut Tasmota plug with Amazon Alexa. For plugs with Matter support, use Matter pairing. Older firmware may also support local device emulation.

## Before You Start

- Complete the [Tasmota Wi-Fi setup](../getting-setup/tasmota.md) first, then check that you can switch the plug on and off from its web page.
- Install or update the Amazon Alexa app and sign in to your Amazon account.
- For Matter pairing, you need an Alexa device that supports acting as a Matter controller, such as a compatible Echo. Not every Echo model supports Matter.
- Connect the plug to a 2.4 GHz Wi-Fi network. Keep your phone and Alexa controller on the same home network during setup, not an isolated guest network.

## Pair Using Matter (Recommended)

No Tasmota Alexa skill or MQTT broker is needed.

1. Open the plug's IP address in a web browser.
2. Open **Matter** from the main menu on newer firmware. On older firmware, open **Configuration** > **Configure Matter**.
3. Enable **Matter enable** and select **Save** if commissioning is not already active. The plug restarts.
4. Return to the plug's main page and find the Matter QR code or manual pairing code.
5. In the Alexa app, open **Devices**, select **+**, then **Add Device**. Choose **Matter** if offered, or **Other**, then follow the prompts to add a Matter device. Menu names may vary by app version.
6. Scan the plug's QR code. If the code is displayed on the phone you are using, choose the option to enter the manual pairing code instead.
7. Follow the prompts to finish setup, then give the plug a clear name, such as **Desk lamp**, and assign it to a room.
8. Test control in the Alexa app, then try saying **"Alexa, turn on Desk lamp"** or **"Alexa, turn off Desk lamp"**.

:::tip[Pairing window]
Matter commissioning is only open for a limited time. If pairing times out or the code is no longer displayed, re-enable commissioning from the plug's Matter page and try again.
:::

For screenshots and more details, see [Matter](./matter.md) or [Tasmota V2 Matter](../v2/matter.md).

### Already Paired With Another Matter Controller?

If the plug is already paired with Home Assistant, Apple Home, or another Matter controller, use that controller's option to share the device with another ecosystem. Enter the newly generated pairing code in Alexa rather than reusing the original setup code. This lets you keep the existing pairing.

## Older Firmware: Local Emulation

If your firmware has no Matter support but includes Tasmota's emulation feature, you can try **Belkin WeMo** emulation for this single-relay plug. Discovery depends on the Echo model and firmware, so this is an alternative rather than the recommended setup.

1. Open the plug's web page and go to **Configuration** > **Configure Other**. On the newer interface, configuration options are under **Advanced**.
2. Set a recognisable **Friendly Name**, such as **Desk lamp**.
3. Select **Belkin WeMo** under **Emulation**, then select **Save** and allow the plug to restart.
4. With a physical Echo on the same local network, say **"Alexa, discover devices"**, or use **Devices** > **+** > **Add Device** in the Alexa app and choose **Other** when asked for the brand.
5. Test switching the discovered plug on and off.

You do not need the WeMo app or Alexa WeMo skill. If the emulation setting is not available in your firmware, use Matter where supported; do not flash different firmware just to expose this option.

See the [official Tasmota Alexa documentation](https://tasmota.github.io/docs/Alexa/) for emulation compatibility and Hue Bridge emulation options.

## Troubleshooting

- **Alexa cannot find the Matter plug:** Check that your Alexa device supports Matter, the plug's commissioning window is open, and you are entering the current pairing code.
- **The plug is already paired elsewhere:** Generate a new sharing code from the existing Matter controller, as described above.
- **Discovery fails on your network:** Disable guest/client isolation for these devices. Matter needs local IPv6 and multicast/mDNS traffic between the plug, phone, and controller. Emulation also relies on local multicast discovery; check your router's multicast/IGMP settings.
- **Emulation does not discover anything:** The Alexa app alone is not enough; use a physical Echo on the same local network. Some Echo/firmware combinations may not discover emulated devices.
- **Alexa shows duplicate devices:** Pair through one method only, then remove unused entries in Alexa.
- **Power readings are missing in Alexa:** This guide covers on/off control. Energy-monitoring visibility depends on firmware and Alexa support; use the plug's web page or [Home Assistant](./home-assistant.md) for power readings.

Do not factory-reset the plug as a first troubleshooting step, as this can remove Wi-Fi settings and existing integrations.
