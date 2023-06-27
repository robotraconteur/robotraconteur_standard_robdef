# Service: `com.robotraconteur.datetime`

The `com.robotraconteur.datetime` service provides definitions for representing date and time-related information.
The `DateTimeUTC` and `DateTimeLocal` structures are used to represent date and time information in UTC and local time, 
respectively, using the system real-time clock. The `TimeSpec2` and `TimeSpec3` are used to represent the
performance clock of the node. The performance clock may not be synchronized with the system real-time clock, and
may not be the same across nodes. It is guaranteed to be a steady clock and will not be adjusted by the system.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following package:

- `com.robotraconteur.uuid`: Provides functionality for working with UUIDs.

### Using Statements

This service uses the following statement to import a specific type:

- `com.robotraconteur.uuid.UUID`: Represents a Universally Unique Identifier (UUID).

## Constant: `EPOCH_ISO8601`

The `EPOCH_ISO8601` constant represents the ISO 8601 formatted string for the epoch time, which is `"1970-01-01T00:00:00Z"`.

## Enum: `ClockTypeCode`

The `ClockTypeCode` enum represents the types of clocks used for timekeeping.

- `unknown` (`0`): Represents an unknown clock type.
- `default`: Represents the default clock.
- `system_rtc_clock`: Represents the system real-time clock.
- `system_ntp_clock`: Represents the system Network Time Protocol (NTP) clock.
- `system_ptp_clock`: Represents the system Precision Time Protocol (PTP) clock.
- `system_arb_clock`: Represents the system arbitrary clock.
- `system_gps_clock`: Represents the system Global Positioning System (GPS) clock.
- `system_tai_clock`: Represents the system International Atomic Time (TAI) clock.
- `system_other_clock`: Represents another system clock.
- `sim_clock_realtime`: Represents the real-time simulation clock.
- `sim_clock_scaled`: Represents the scaled simulation clock.
- `node_default`: Represents the default clock for a node.
- `node_rtc_clock`: Represents the node real-time clock.
- `node_ntp_clock`: Represents the node Network Time Protocol (NTP) clock.
- `node_ptp_clock`: Represents the node Precision Time Protocol (PTP) clock.
- `node_arb_clock`: Represents the node arbitrary clock.
- `node_gps_clock`: Represents the node Global Positioning System (GPS) clock.
- `node_tai_clock`: Represents the node International Atomic Time (TAI) clock.
- `node_other_clock`: Represents another clock used by the node.
- `aux_0` (`0x1000`): Represents an auxiliary clock 0.
- `aux_1`: Represents an auxiliary clock 1.
- `aux_2`: Represents an auxiliary clock 2.
- `aux_3`: Represents an auxiliary clock 3.
- `aux_4`: Represents an auxiliary clock 4.
- `aux_5`: Represents an auxiliary clock 5.
- `aux_6`: Represents an auxiliary clock 6.
- `aux_7`: Represents an auxiliary clock 7.

This enum provides a set of predefined clock types used for timekeeping.

## POD: `ClockInfo`

The `ClockInfo` plain old data (POD) structure represents information about a clock.

- `field uint32 clock_type`

    The type of the clock.

- `field UUID clock_uuid`

    The Universally Unique Identifier (UUID) associated with the clock.

- `field int64 offset_microseconds`

    The offset from the International Atomic Time (TAI) in microseconds.

## POD: `DateTimeUTC`

The `DateTimeUTC` plain old data (POD) structure represents a date and time in Coordinated Universal Time (UTC).

- `field ClockInfo clock_info`

    Information about the clock used for timekeeping.

- `field int64 seconds`

    The number of seconds since the epoch time.

- `field int32 nanoseconds`

    The number of nanoseconds within the current second.

## Struct: `DateTimeLocal`

The `DateTimeLocal` structure represents a date and time in the local time zone.

- `field ClockInfo clock_info`

    Information about the clock used for timekeeping.

- `field int64 seconds`

    The number of seconds since the epoch time.

- `field int32 nanoseconds`

    The number of nanoseconds within the current second.

- `field int32 utc_offset_seconds`

    The offset in seconds between the local time zone and Coordinated Universal Time (UTC).

- `field string timezone_name`

    The name of the local time zone.

## POD: `Duration`

The `Duration` plain old data (POD) structure represents a duration of time.

- `field ClockInfo clock_info`

    Information about the clock used for timekeeping.

- `field int64 seconds`

    The number of seconds in the duration.

- `field int32 nanoseconds`

    The number of nanoseconds within the current second.

## POD: `TimeSpec2`

The `TimeSpec2` plain old data (POD) structure represents a timestamp with microsecond precision in the node clock.

- `field ClockInfo clock_info`

    Information about the clock used for timekeeping.

- `field int64 seconds`

    The number of seconds since the epoch time.

- `field int32 nanoseconds`

    The number of nanoseconds within the current second.

## NamedArray: `TimeSpec3`

The `TimeSpec3` named array represents a compact timestamp with microsecond precision in the node clock.

- `field int64 microseconds`

    The number of microseconds since the epoch time.

