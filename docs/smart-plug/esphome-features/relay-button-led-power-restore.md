# Relay, Button, LED, And Power Restore

This guide covers the main plug controls: the relay, the physical button, LED behaviour, local button lock, and what happens after a power cut or reboot.

## Relay Control

The main plug switch controls the relay inside the plug.

- On: the socket is powered.
- Off: the socket is not powered.

Suggested use cases:

- Manually turn lamps, chargers, heaters, fans, or appliances on and off from Home Assistant.
- Use Home Assistant schedules or automations to control the connected device.
- Combine relay control with power sensors to turn off equipment when a condition is met.

## Physical Button Actions

The plug button supports multiple actions:

- Single press: toggles the relay.
- Double press: cycles **Power loss behaviour**.
- Long press, from 1 to 5 seconds: cycles **LED Behaviour**.

Suggested use cases:

- Single press is useful when the plug is accessible and you still want manual control.
- Double press is useful during setup if you are testing how the plug behaves after rebooting.
- Long press is useful for quickly turning the LED off in bedrooms, living rooms, or offices.

## Local Button Lock

Turn on **Local Button Lock** if you do not want button presses to change plug state or settings.

Suggested use cases:

- Prevent children, pets, or accidental knocks from turning off important equipment.
- Stop a wall-mounted or floor-level plug from being changed by mistake.
- Keep automations in full control of the plug state.

Potential use cases:

- Use local button lock for a fridge, network equipment, aquarium, or other load that should not be switched off casually.
- Disable local button lock temporarily while testing, then turn it back on once setup is complete.

## Power Loss Behaviour

Use **Power loss behaviour** to decide what the plug does when power returns after a power cut, unplug, reboot, or firmware restart.

Options:

- **OFF**: the relay always starts off.
- **ON**: the relay always starts on.
- **Restore last state**: the relay returns to the state it had before power was lost.

Suggested settings:

- Use **OFF** for heaters, irons, lamps, or anything that should not turn on unexpectedly.
- Use **ON** for devices that should always resume, such as routers or network equipment.
- Use **Restore last state** for lamps, fans, or general appliances where continuing the previous state is expected.

## Power Restore Delay

Use **Power Restore Delay** to wait before applying the selected power loss behaviour. The value is set in seconds.

Suggested use cases:

- Delay high-load devices after a power cut so several appliances do not turn on at the same time.
- Let Wi-Fi and Home Assistant recover before powering a connected device.
- Stagger multiple plugs by setting different delays on each plug.

## LED Behaviour

Use **LED Behaviour** to control the plug LED.

Options:

- **Relay state**: LED follows whether the relay is on or off.
- **Always off**: LED stays off.
- **Always on**: LED stays on.

Suggested settings:

- Use **Relay state** when you want a clear physical indication that the socket is powered.
- Use **Always off** in bedrooms, media rooms, or anywhere the LED would be distracting.
- Use **Always on** if the plug is hidden and you want to confirm it has power.

Potential automations:

- Turn the relay off at night but leave LED behaviour unchanged for normal daytime use.
- Use Home Assistant scenes to combine relay state with other room devices.
