# FAQ

## I'd like to re-flash my Tasmota plug with ESPHome or my ESPHome plug with Tasmota

Unfortunately we are unable to support switching firmware between ESPHome and Tasmota as both firmwares use different internal partition layouts and the plugs are sealed units with no serial access.

:::danger
Attempting to swap between Tasmota and ESPHome will likely result in a non functional plug.
:::

## Can I use ESPHome without Home Assistant?

We would advise Tasmota for use with systems other than Home Assistant, ESPHome is designed to work with Home Assistant and will restart every 15 minutes if it is not connected to a Home Assistant instance

## Using Tasmota I'm not able to see any power monitoring values

Please ensure that your plug has the following configuration 

![UI config](/img/esp32c3-plug-config.png)

Newer Smart Hut Tasmota firmware includes this template by default. If power monitoring is missing after flashing different firmware or resetting configuration, reapply the Smart Hut template or return to compatible Smart Hut Tasmota firmware.

## Why do some Tasmota configuration buttons seem to be missing?

Newer Smart Hut Tasmota firmware hides some advanced stock Tasmota options, including module, template, backup, and restore buttons, to reduce the risk of accidentally breaking a sealed plug.

The normal setup options are still available from the main page and the `Advanced` page.

## Can I update the Tasmota firmware myself?

Only update with firmware that is known to be compatible with the Smart Hut plug hardware and partition layout. The newer firmware shows an explicit warning before firmware upgrades because installing the wrong build can erase configuration or make the plug unusable.
