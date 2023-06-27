# Service: `com.robotraconteur.datetime.clock`

The `com.robotraconteur.datetime.clock` service represents a clock device that provides date and time information.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.datetime`: Provides definitions for date and time-related information.
- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.device.clock`: Defines interfaces for clock devices.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.datetime.DateTimeUTC`: Represents a date and time in Coordinated Universal Time (UTC).
- `com.robotraconteur.datetime.DateTimeLocal`: Represents a date and time in the local time zone.
- `com.robotraconteur.datetime.ClockTypeCode`: Represents the types of clocks used for timekeeping.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the clock.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.clock.DeviceClock`: Defines the interface for clock devices.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the current time of a clock device.

## Struct: `ClockDeviceInfo`

The `ClockDeviceInfo` structure represents information about a clock device.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field ClockTypeCode clock_type`

    The type of the clock used by the device.

- `field int32 timezone_utc_offset_seconds`

    The offset in seconds between the device's local time zone and Coordinated Universal Time (UTC).

- `field string timezone_name`

    The name of the device's local time zone.

- `field varvalue{string} extended`

    Extended information about the clock device.

## Object: `Clock`

The `Clock` object represents a clock device.

### Implements

- `Device`: Provides device-related functionality.
- `DeviceClock`: Defines the interface for clock devices.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property ClockDeviceInfo clock_info [readonly,nolock]`

    Provides information about the clock device.

### Wires

- `wire DateTimeUTC time_utc [readonly]`

    The current Coordinated Universal Time (UTC) provided by the clock device.

- `wire DateTimeLocal time_local [readonly]`

    The current local time provided by the clock device.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    The current time of the clock device.
