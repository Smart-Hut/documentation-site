# FAQ

## I'd like to re-flash my Tasmota plug with ESPHome or my ESPHome plug with Tasmota

Unfortunately we are unable to support switching firmware between ESPHome and Tasmota as both firmwares use different internal partition layouts and the plugs are sealed units with no serial access.

:::danger
Attempting to swap between Tasmota and ESPHome will likely result in a non functional plug.
:::

## Can I use ESPHome without Home Assistant?

We would advise Tasmota for use with systems other than Home Assistant, ESPHome is designed to work with Home Assistant and will restart every 15 minutes if it is not connected to a Home Assistant instance

## Using Tasmota I'm not able to see any power monintoring values

Please ensure that your plug has the following configuration 

![UI config](/img/esp32c3-plug-config.png)