# Service: `com.robotraconteur.device.isoch`

The `com.robotraconteur.device.isoch.IsochDevice` provides functionality to control the update rate of an isochronous device.
Devices will implement this type to allow clients to control the update rate of data streaming from wires
and pipes. The wires and pipes are synchronized to publish data at the interval specified by the `update_rate` field
of the `IsochInfo` structure. The `IsochInfo` structure also contains the `isoch_epoch` field, which is the epoch time
of the isochronous device, ie the time the performance clock starts. The performance clock used by the device is
a TimeSpec2 clock.

The `isoch_downsample` property controls the downsample value for the client. Each client can control
the downsample value independently. The downsample value begins at 0, meaning no downsampling,
and can increase to the `max_downsample` value. The `max_downsample` value is set by the device and
is the maximum downsample value supported by the device. If a downsample is configured, it will skip 
that many updates of the wire or pipe. For example, if the `isoch_downsample` value is 2, then the
wire or pipe will update every 3rd update of the device clock.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following package:

- `com.robotraconteur.datetime`: Provides definitions for date and time-related information.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.datetime.TimeSpec2`: Represents a timestamp with microsecond precision in the node clock.

## Struct: `IsochInfo`

The `IsochInfo` structure represents information about an isochronous device.

- `field double update_rate`

    The update rate of the isochronous device.

- `field TimeSpec2 isoch_epoch`

    The epoch time of the isochronous device.

- `field uint32 max_downsample`

    The maximum downsample value for the isochronous device.

## Object: `IsochDevice`

The `IsochDevice` object represents an isochronous device.

### Properties

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous device.

- `property uint32 isoch_downsample [perclient]`

    Controls the downsample value for the isochronous device.

