## Service: `com.robotraconteur.actuator`

The `com.robotraconteur.actuator` service is used to represent generic actuators such as motors or cylinders.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.units`: Defines units of measurement.
- `com.robotraconteur.datatype`: Contains data type definitions.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the actuator.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.param.ParameterInfo`: Provides information about the parameters associated with the actuator.
- `com.robotraconteur.units.SIUnit`: Represents a measurement unit using the International System of Units (SI).
- `com.robotraconteur.datatype.DataType`: Defines the data type used for actuator commands.
- `com.robotraconteur.datetime.TimeSpec3`: Represents a timestamp with microsecond precision.

## Enum: `ActuatorTypeCode`

The `ActuatorTypeCode` enum represents the types of actuators that can be used within the `com.robotraconteur.actuator` service.

- `unknown` (`0`): Represents an unknown actuator type.
- `generic`: Represents a generic actuator.
- `position`: Represents an actuator controlled by position.
- `velocity`: Represents an actuator controlled by velocity.
- `acceleration`: Represents an actuator controlled by acceleration.
- `effort`: Represents an actuator controlled by effort.
- `motor_position`: Represents a motor actuator controlled by position.
- `motor_velocity`: Represents a motor actuator controlled by velocity.
- `motor_acceleration`: Represents a motor actuator controlled by acceleration.
- `motor_effort`: Represents a motor actuator controlled by effort.
- `solenoid`: Represents a solenoid actuator.
- `voice_coil`: Represents a voice coil actuator.
- `piezoelectric`: Represents a piezoelectric actuator.
- `pneumatic_pressure`: Represents an actuator controlled by pneumatic pressure.
- `vacuum_pressure`: Represents an actuator controlled by vacuum pressure.
- `heater_power`: Represents an actuator controlled by heater power.
- `chiller_power`: Represents an actuator controlled by chiller power.
- `valve`: Represents a valve actuator.
- `conveyor`: Represents an actuator used in conveyors.
- `voltage`: Represents an actuator controlled by voltage.
- `current`: Represents an actuator controlled by current.
- `pneumatic_cylinder`: Represents a pneumatic cylinder actuator.
- `hydraulic_cylinder`: Represents a hydraulic cylinder actuator.

This enum provides a set of predefined actuator types. If the actuator type is not listed in this enum, use `unknown`
and use the `DeviceClass` entries in `DeviceInfo` to describe the actuator.

## Enum: `ActuatorMode`

The `ActuatorMode` enum represents the operating modes of an actuator within the `com.robotraconteur.actuator` service.

- `error` (`-2`): Indicates that the actuator is in an error state.
- `disabled` (`-1`): Indicates that the actuator is disabled and not operational.
- `halt` (`0`): Indicates that the actuator is in a halted state.
- `reduced_performance` (`1`): Indicates that the actuator is operating with reduced performance.
- `normal` (`2`): Indicates that the actuator is operating in normal mode.

## Enum: `ActuatorStateFlags`

The `ActuatorStateFlags` enum represents the state flags of an actuator. The are returned by the `state_flags` 
property of the `ActuatorState` structure.

- `unknown` (`0`): Indicates that the state of the actuator is unknown.
- `ready` (`0x1`): Indicates that the actuator is ready for operation.
- `streaming` (`0x2`): Indicates that the actuator is in streaming mode.
- `warning` (`0x4`): Indicates that a warning condition is present.
- `error` (`0x8`): Indicates that an error condition is present.
- `fatal_error` (`0x10`): Indicates that a fatal error condition is present.
- `e_stop` (`0x20`): Indicates that an emergency stop condition is active.
- `homed` (`0x40`): Indicates that the actuator has been homed.
- `homing_required` (`0x80`): Indicates that homing is required for the actuator.
- `communication_failure` (`0x100`): Indicates a communication failure with the actuator.
- `valid_command` (`0x200`): Indicates that a valid command has been sent to the actuator.
- `enabled` (`0x400`): Indicates that the actuator is enabled.

## Structure: ActuatorState

The ActuatorState structure is used to represent the state of an actuator. It is returned by 
the `actuator_state` wire of the `Actuator` object.

- `field TimeSpec3 ts`

    The timestamp of the actuator state.

- `field uint64 seqno`

    The sequence number of the actuator state.
- `field uint32 actuator_state_flags`

    The state flags of the actuator.

- `field double[] actuator_command`

    The command sent to the actuator.

## Structure: ActuatorInfo

The `ActuatorInfo` structure is used to provide information about an actuator. It is returned by the `actuator_info`
property of the `Actuator` object.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.
    
- `field ActuatorTypeCode actuator_type`

    The type of the actuator.

- `field SIUnit{list} command_units`

    The units of the actuator command. The units are typically SI units.

- `field DataType command_data_type`

    The data type of the actuator command. The data type is typically a double scalar or vector.

- `field double[] command_resolution`

    The resolution of the actuator command.

- `field bool analog_output`

    Indicates if the actuator uses an analog output signal.

- `field ParameterInfo{list} parameter_info`

    Provides information about the parameters of the actuator. Used with the `getf_param` and `setf_param` functions.

- `field varvalue{string} extended`

    Extended information about the actuator.

## Object: Actuator

### Implements

    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property ActuatorInfo actuator_info [readonly,nolock]`

    Provides information about the actuator.

- `property ActuatorMode actuator_mode [nolockread]`

    Get or set the operating mode of the actuator.

### Functions

- `function varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

### Wires

- `wire double[] actuator_command [writeonly]`

    The actuator command in the units specified by `actuator_info.command_units`. These are normally SI units.

- `wire ActuatorState actuator_state [readonly,nolock]`

    The state of the actuator stored in an `ActuatorState` structure.
