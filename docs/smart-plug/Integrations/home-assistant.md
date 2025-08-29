# Home Assistant

Both our Tasmota and ESPHome plugs integrate directly with Home Assistant, for ESPHome our plugs should be automatically discovered by the [ESPHome integration](https://www.home-assistant.io/integrations/esphome/) allowing you to add them easily. 

:::tip[Want to customise the ESPHome firmware on your plug?]
You can find the full ESPHome Yaml [here](https://github.com/Smart-Hut/Smart-Plug/blob/main/ESPC2-02.yaml) 
:::

## Tasmota plugs

Our Tasmota plugs are pre-enabled with:

- Home Assistant
- MQTT
- Matter

The easiest way to integrate with Home Assistatnt is via the [Tasmota Integration](https://www.home-assistant.io/integrations/tasmota/). This should discover the plug automatically a short time after the plug is connected to your wifi.