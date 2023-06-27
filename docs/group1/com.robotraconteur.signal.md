## Service: `com.robotraconteur.signal`

The `com.robotraconteur.signal` service is used to represent signals of various types, such as digital, analog, vectors, poses, and more.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Provides functionality for identifiers.
- `com.robotraconteur.datatype`: Contains data type definitions.
- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.units`: Defines units of measurement.
- `com.robotraconteur.device.isoch`: Includes definitions for isochronous device-related operations.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier.
- `com.robotraconteur.datatype.DataType`: Defines the data type used for signal data.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the signal.
- `com.robotraconteur.device.DeviceClass`: Represents the class of the device associated with the signal.
- `com.robotraconteur.units.SIUnit`: Represents a measurement unit using the International System of Units (SI).
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.isoch.IsochDevice`: Represents an isochronous device.
- `com.robotraconteur.device.isoch.IsochInfo`: Provides information about the isochronous device.
- `com.robotraconteur.datetime.TimeSpec3`: Represents a timestamp with microsecond precision.

## Enum: `SignalType`

The `SignalType` enum represents the types of signals that can be used within the `com.robotraconteur.signal` service.

- `unknown` (`0`): Represents an unknown signal type.
- `digital` (`1`): Represents a digital signal.
- `analog`: Represents an analog signal.
- `digital_port`: Represents a port of digital signals.
- `analog_port`: Represents a port of analog signals.
- `vector3`: Represents a 3D vector signal.
- `vector6`: Represents a 6D vector signal.
- `wrench`: Represents a wrench signal.
- `pose`: Represents a pose signal.
- `transform`: Represents a transform signal.
- `other`: Represents a signal of another type.

This enum provides a set of predefined signal types. If the signal type is not listed in this enum, use `unknown`
and provide additional details in the `SignalInfo` structure.

## Enum: `SignalAccessLevel`

The `SignalAccessLevel` enum represents the access levels for reading or writing a signal within the `com.robotraconteur.signal` service.

- `undefined` (`0`): Indicates that the access level is undefined.
- `internal`: Indicates that the signal is only accessible internally.
- `restricted`: Indicates restricted access to the signal.
- `readonly`: Indicates read-only access to the signal.
- `all`: Indicates full access to the signal.

This enum defines the possible access levels for a signal, specifying the level of permission required to read or write the signal.

## Enum: `SignalDeviceStateFlags`

The `SignalDeviceStateFlags` enum represents the state flags of a signal device. These flags are returned by the `signal_device_state_flags` property of the `SignalDeviceState` structure.

- `unknown` (`0`): Indicates that the state of the signal device is unknown.
- `ready` (`0x

1`): Indicates that the signal device is ready for operation.
- `streaming` (`0x2`): Indicates that the signal device is in streaming mode.
- `warning` (`0x4`): Indicates that a warning condition is present.
- `error` (`0x8`): Indicates that an error condition is present.
- `fatal_error` (`0x10`): Indicates that a fatal error condition is present.
- `calibrated` (`0x20`): Indicates that the signal device has been calibrated.
- `calibration_required` (`0x40`): Indicates that calibration is required for the signal device.
- `communication_failure` (`0x80`): Indicates a communication failure with the signal device.

This enum provides flags that describe the state of the signal device, indicating various conditions or statuses.

## Structure: SignalInfo

The `SignalInfo` structure is used to provide information about a signal. It is returned by the `signal_info` property of the `Signal` object.

- `field Identifier signal_identifier`

    The identifier of the signal.

- `field DeviceClass signal_class`

    The class of the device associated with the signal.

- `field SIUnit{list} units`

    The units of the signal. The units are typically SI units.

- `field DataType data_type`

    The data type of the signal.

- `field SignalType signal_type`

    The type of the signal.

- `field SignalAccessLevel access_level`

    The access level of the signal.

- `field uint32[] address`

    The address of the signal.

- `field string user_description`

    A user-defined description of the signal.

- `field varvalue min_value`

    The minimum value of the signal.

- `field varvalue max_value`

    The maximum value of the signal.

- `field varvalue{string} extended`

    Extended information about the signal.

## Structure: SignalDeviceState

The `SignalDeviceState` structure is used to represent the state of a signal device. It is returned by the `signal_device_state` wire of the `Signal` object.

- `field TimeSpec3 ts`

    The timestamp of the signal device state.

- `field uint64 seqno`

    The sequence number of the signal device state.

- `field uint32 signal_device_state_flags`

    The state flags of the signal device.

## Structure: SignalGroupInfo

The `SignalGroupInfo` structure is used to provide information about a signal group. It is returned by the `signal_group_info` property of the `SignalDevice` object.

- `field Identifier signal_group_identifier`

    The identifier of the signal group.

- `field string description`

    A description of the signal group.

## Object: Signal

### Implements

    - IsochDevice

### Properties

- `property SignalInfo signal_info [readonly,nolock]`

    Provides information about the signal.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous device.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsampling factor for isochronous data.

### Wires

- `wire varvalue signal_value [readonly]`

    The value of the signal.

- `wire varvalue signal_command [writeonly]`

    The command sent to the signal.

- `wire double[] signal_value_vec [readonly]`

    The value of the signal as a vector.

- `wire double[] signal_command_vec [writeonly]`

    The command sent to the signal as a vector.

## Object: SignalGroup

### Properties

- `property SignalInfo{list} signal_info [readonly,nolock]`

    Provides information about the signals in the group.

### Object References

- `objref Signal{int32} signals`

    Represents individual signals within the group.

## Object: SignalDevice

### Implements

    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SignalGroupInfo{list} signal_group_info [readonly,nolock]`

    Provides information about the signal groups associated with the device.

### Object References

- `objref SignalGroup{string} signal_groups`

    Represents signal groups associated with the device.

