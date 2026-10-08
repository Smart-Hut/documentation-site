# Auto-Off And Standby Killer

Auto-off and standby killer both turn the relay off automatically, but they solve different problems.

## Auto-Off Timer

Auto-off turns the relay off after a fixed amount of time.

Settings:

- **Auto Off Enabled**: turns the feature on or off.
- **Auto Off Minutes**: how long the relay stays on before turning off.

How to use it:

1. Set **Auto Off Minutes** to the required run time.
2. Turn on **Auto Off Enabled**.
3. Turn on the plug relay.

Suggested use cases:

- Phone, laptop, and battery chargers that only need a few hours.
- Heaters, heated blankets, fans, or lamps that should not be left on indefinitely.
- Temporary equipment in garages, sheds, offices, or bedrooms.

Suggested starting values:

- Chargers: `120` to `240` minutes.
- Lamps or fans: `60` to `180` minutes.
- Heaters or heated blankets: use the shortest safe time for your situation.

Potential use cases:

- Guest room plugs where devices are often left on.
- Workshop tools or soldering stations that should switch off after use.
- Seasonal lights where a simple countdown is enough.

## Standby Killer

Standby killer turns the relay off when the connected device drops to a low standby power level for long enough.

Settings:

- **Standby Killer Enabled**: turns the feature on or off.
- **Standby Threshold**: the maximum power level that counts as standby.
- **Standby Killer Delay**: how long the device must remain in standby before the relay turns off.

The firmware starts the standby timer when the relay is on and power is above `0.1 W` but less than or equal to **Standby Threshold**.

Suggested use cases:

- TVs, games consoles, speakers, and media boxes that draw standby power.
- Chargers that continue to draw a small amount after charging is complete.
- Office equipment that should be fully powered down after use.

Suggested setup process:

1. Turn on the connected device and observe its normal running power.
2. Turn the connected device off or let it enter standby.
3. Observe the standby wattage in Home Assistant.
4. Set **Standby Threshold** slightly above that standby wattage.
5. Set **Standby Killer Delay** long enough to avoid false triggers.
6. Turn on **Standby Killer Enabled** and test.

Example settings:

- TV standby reads around `1.2 W`: set **Standby Threshold** to `2 W` and **Standby Killer Delay** to `10` or `15` minutes.
- Charger idle reads around `0.5 W`: set **Standby Threshold** to `1 W` and **Standby Killer Delay** to `30` minutes.

## Choosing Between Them

Use auto-off when the run time is predictable. Use standby killer when the device decides when it is finished or idle.

Examples:

- A phone charger is a good fit for auto-off.
- A TV setup is a good fit for standby killer.
- A heater may be better with auto-off because low power does not necessarily mean it is safe to switch based on standby.

## Avoiding False Triggers

- Do not set the standby threshold too high or the plug may turn off while the device is still active.
- Do not set the delay too short for devices that pause briefly during normal operation.
- Test with the actual device connected before relying on the feature.
