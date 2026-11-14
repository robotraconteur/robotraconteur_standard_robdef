# Service: `com.robotraconteur.device.clock`

The `com.robotraconteur.device.clock` service provides functionality for device clock-related operations.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following package:

- `com.robotraconteur.datetime`: Provides definitions for date and time-related information.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.datetime.TimeSpec2`: Represents a timestamp with microsecond precision in the node clock.
- `com.robotraconteur.datetime.DateTimeUTC`: Represents a date and time in Coordinated Universal Time (UTC).

## POD: `DeviceTime`

The `DeviceTime` plain old data (POD) structure represents the current time of a device clock.

- `field TimeSpec2 device_ts`

    The timestamp in the device clock.

- `field DateTimeUTC device_utc`

    The Coordinated Universal Time (UTC) provided by the device clock.

- `field uint64 device_seqno`

    The sequence number associated with the device time.

## Object: `DeviceClock`

The `DeviceClock` object represents a clock device.

### Wires

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Provides the current time of the device clock.
