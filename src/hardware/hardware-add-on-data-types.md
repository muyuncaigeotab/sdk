---
layout: page
title: Hardware Add-On data types
permalink: /hardware/hardware-add-on-data-types/
---

Listed in the table below are the types of data that the GO device can currently report from Hardware Add-Ons. If you'd like to send a data type that's not listed, we can work with you to build support for it.

The GO device will relay the raw data sent by the external device to MyGeotab. MyGeotab will then take the raw value received from the GO device and adjust by the multiplier and the offset. When MyGeotab applies the conversion, the multiplier is always done first, followed by the offset, as per the formula:

<b><center><i>
Final Value = (Initial Value × Multiplier) + Offset
</i></center></b>

The unit refers to the unit of measurement that you wish to see in MyGeotab after all the conversions are complete. Geotab uses metric units and all predefined status IDs currently used by Geotab are in metric units.

**Example:**

- If you are reporting a temperature range from -40 °C to 215 °C, the third-party device would send values from 0 to 255 (can&#39;t send negative values). The offset would be set to -40 so that MyGeotab would know to subtract 40 from the value obtained from the GO device. So a reported value of 0 by the third-party device would show up as -40 °C in MyGeotab.

- The third-party device is sending a distance in 0.1 km increments, such that a value of 1223 represents a distance of 122.3 km. A multiplier of 0.1 should be applied so that the value is properly converted to kilometers on MyGeotab.

| Diagnostic | Code | Unit | Data Length | Conversion | Offset |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----:|:---------:|:-----------:|:-----------:|:------:|
| External immobilizer: tag UID high | 2600 | 0 | 1 | 1 | 0 |
| External immobilizer: tag UID low | 2601 | 0 | 1 | 1 | 0 |
| External immobilizer: tag read status | 2602 | 0 | 1 | 1 | 0 |

