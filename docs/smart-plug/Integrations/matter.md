# Matter

Our Tasmota plugs support Matter and it is enabled by default. You can find the setup code to add your plug to your Matter network on the main page of the plug after connecting to your wifi network.

:::tip[Newer Smart Hut Tasmota firmware]
Newer plugs have a `Matter` button on the main Tasmota page. See [Tasmota V2 Matter](../v2/matter.md) if your plug has the newer interface.
:::

:::warning
Matter connections are only enabled for a limited time after initial startup. You'll need to re-enable Matter if you don't add it to your network in this time.
:::

## Enable Matter

If you need to re-enable Matter, go to **Configuration** > **Configure Matter** and enable Matter with the checkmark, then click **Save**. On newer firmware, open **Matter** from the main menu instead.

![Matter enable](/img/matter_enable.jpg)

After a restart device commissioning will be open for 10 minutes.

![Matter commissioning](/img/matter_commissioning.jpg)


Add the device to your Matter hub by scanning the QR code or with the "Manual pairing code" if code scanning is not possible.
