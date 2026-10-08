# Appliance Detection

Appliance detection identifies when a connected appliance starts running and when it has finished based on power use.

This is best for appliances with a clear running phase and a lower-power finished or idle phase.

## Entities

Settings:

- **Appliance Detection Enabled**: turns the feature on or off.
- **Appliance Running Threshold**: power level that means the appliance has started running.
- **Appliance Finished Threshold**: power level that means the appliance may have finished.
- **Appliance Finished Delay**: how long power must stay below the finished threshold before the appliance is marked finished.

Status sensors:

- **Appliance Running**: on after the appliance has exceeded the running threshold.
- **Appliance Finished**: on after the appliance later stays below the finished threshold for the configured delay.

## Suggested Use Cases

- Washing machine finished notifications.
- Tumble dryer finished notifications.
- Dishwasher finished notifications.
- Dehumidifier or air purifier run-state monitoring.
- Any appliance where power rises noticeably during operation and drops after the cycle completes.

## Suggested Setup Process

1. Turn on the plug relay.
2. Run the appliance normally.
3. Watch the **Power** sensor in Home Assistant during the cycle.
4. Note the typical running power while the appliance is active.
5. Note the power after the appliance has finished.
6. Set **Appliance Running Threshold** below the normal active running power.
7. Set **Appliance Finished Threshold** above the finished idle power but below normal running power.
8. Set **Appliance Finished Delay** long enough to ignore short pauses.
9. Turn on **Appliance Detection Enabled** and test another cycle.

## Example Starting Points

Washing machine:

- **Appliance Running Threshold**: `20 W` to `50 W`.
- **Appliance Finished Threshold**: `3 W` to `10 W`.
- **Appliance Finished Delay**: `5` to `10` minutes.

Tumble dryer:

- **Appliance Running Threshold**: `100 W` to `500 W`.
- **Appliance Finished Threshold**: `5 W` to `20 W`.
- **Appliance Finished Delay**: `5` to `10` minutes.

Dishwasher:

- **Appliance Running Threshold**: `20 W` to `100 W`.
- **Appliance Finished Threshold**: `3 W` to `10 W`.
- **Appliance Finished Delay**: `10` to `20` minutes.

These are starting points only. Use the actual power readings from your appliance where possible.

## Home Assistant Notification Example

Create an automation that triggers when **Appliance Finished** turns on.

Suggested actions:

- Send a mobile notification that the washing machine has finished.
- Turn on a reminder light.
- Announce the finished cycle on a smart speaker.
- Turn off the plug relay after the notification has been sent.

## Avoiding False Finished Alerts

Many appliances pause during a cycle. If **Appliance Finished** turns on too early:

- Lower **Appliance Finished Threshold**.
- Increase **Appliance Finished Delay**.
- Raise **Appliance Running Threshold** if the appliance is being marked as running too easily.

If the appliance never shows as finished:

- Raise **Appliance Finished Threshold** slightly.
- Check whether the appliance has an idle display or fan that continues drawing power.
- Confirm **Appliance Detection Enabled** is turned on.

## Potential Use Cases

- Track whether a washing machine cycle started after a scheduled delay.
- Alert if a tumble dryer is still running after an expected finish time.
- Create a dashboard showing which appliance is currently running.
- Use finished detection to remind someone to empty a machine.
