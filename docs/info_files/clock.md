# com.robotraconteur.datetime.clock

Info file yaml entries for [com.robotraconteur.datetime.clock](../group1/com.robotraconteur.datetime.clock.md)

## ClockDeviceInfo

The `ClockDeviceInfo` structure is used to transmit information about a clock device.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the clock.

### clock_type

Type: `string`

The type of clock. See the [ClockTypeCode](../group1/com.robotraconteur.datetime.md#enum-clocktypecode) enum
for a list of standard clock types. Use the string representation of the enum value.

### timezone_utc_offset_seconds

Type: `int`

The offset in seconds between the device's local time zone and Coordinated Universal Time (UTC). Include
daylight savings time in the offset if applicable.

### timezone_name

Type: `string`

The name of the device's local time zone.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.
