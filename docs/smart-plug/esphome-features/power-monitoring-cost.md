# Power Monitoring And Cost Tracking

The ESPHome firmware exposes live power readings, daily energy tracking, lifetime energy tracking, and estimated cost sensors.

## Power Sensors

Available measurement sensors:

- **Voltage**: current mains voltage.
- **Current**: current draw in amps.
- **Power**: current load in watts.
- **Energy**: raw energy reading in watt-hours.
- **Daily Energy**: energy used today in kWh.
- **Lifetime Energy**: total tracked energy in kWh.

Suggested use cases:

- Identify how much power a device uses while running.
- Compare standby power against active power.
- Track daily energy use for appliances, heaters, dehumidifiers, or media equipment.
- Build Home Assistant dashboard cards showing live watts and daily kWh.

Potential use cases:

- Detect whether a device is actually on even if the relay state is on.
- Find devices with unexpectedly high standby consumption.
- Compare different appliance modes, such as eco mode and standard mode.

## Cost Tracking

Set **Electricity Rate** to your electricity price in `GBP/kWh`.

Cost sensors:

- **Today Cost**: estimated cost for today's usage.
- **Lifetime Cost**: estimated cost for lifetime tracked usage.

Example settings:

- If your rate is 30 pence per kWh, set **Electricity Rate** to `0.30`.
- If your rate is 24.5 pence per kWh, set **Electricity Rate** to `0.245`.

Suggested use cases:

- Estimate the cost of running a tumble dryer, heater, or dehumidifier.
- Compare the cost of different appliances doing similar jobs.
- Track whether a device is worth automating or replacing.

## Home Assistant Energy Dashboard

The **Daily Energy** and **Lifetime Energy** sensors can be used in Home Assistant dashboards. If you add the plug to the Home Assistant Energy dashboard, choose the energy sensor that best matches how you want to report usage.

Suggested approach:

- Use **Daily Energy** for appliance-specific daily dashboard cards.
- Use **Lifetime Energy** where you want longer-term reporting.
- Use **Power** for real-time automations and alerts.

## Suggested Automations

- Notify if a device uses more than expected during the day.
- Turn off the relay if power remains below a threshold for a set time.
- Alert if power rises above a safe or expected level.
- Record daily cost for a device in a Home Assistant helper or dashboard.

## Accuracy Notes

Power monitoring is intended for smart home visibility and automation. If you need billing-grade readings, compare the plug against a trusted meter and use the calibration controls described in [Calibration, diagnostics, and maintenance](./calibration-diagnostics-maintenance.md).
