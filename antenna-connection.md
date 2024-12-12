# RF-connector
* BNC : bulky, but easy to connect
* SMA : smaller but it takes some time to connect.  No visible check if it's connected properly.  You have to turn it to check it.
* U.FL : too small.  A cable assembly to a panel mount connector would be needed.  That introduces loss and extra cost.
* **MMCX** : a good compromise between BNC and SMA.  It's small and easy to connect.  It's also available in a panel mount version.  Popular in the drone industry.

# Protection
## Over-voltage
Over-voltage protection should be low capacitance but high voltage.  A GDT (gas discharge tube) seems like the only option here.

## Static discharge
The filter section of the class-E amplifier is isolated from ground.  To avoid building up a static charge, the filter section should be connected to ground.  This can be done with a 1M resistor.