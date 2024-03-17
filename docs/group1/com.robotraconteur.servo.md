# Service: `com.robotraconteur.servo`

The `com.robotraconteur.servo` service provides definitions for servo-related functionality, including servo information, states, commands, and control modes.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.sensordata`: Provides definitions for sensor data structures.
- `com.robotraconteur.device`: Offers functionalities related to devices.
- `com.robotraconteur.signal`: Contains definitions for signals.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.robotics.joints`: Defines joint-related functionality.
- `com.robotraconteur.device.isoch`: Provides isochronous device-related operations.
- `com.robotraconteur.device.clock`: Offers functionalities related to device clocks.
- `com.robotraconteur.datetime`: Contains functionalities related to date and time.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header information of sensor data.
- `com.robotraconteur.device.DeviceInfo`: Provides standard device information.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.signal.SignalInfo`: Provides information about signals.
- `com.robotraconteur.param.ParameterInfo`: Provides information about parameters.
- `com.robotraconteur.robotics.joints.JointPositionUnits`: Represents the units for joint positions.
- `com.robotraconteur.robotics.joints.JointEffortUnits`: Represents the units for joint efforts.
- `com.robotraconteur.device.isoch.IsochDevice`: Represents an isochronous device.
- `com.robotraconteur.device.isoch.IsochInfo`: Provides information about isochronous devices.
- `com.robotraconteur.device.clock.DeviceClock`: Represents a device clock.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the current time of a device.
- `com.robotraconteur.datetime.TimeSpec3`: Represents a timestamp with microsecond precision.

## Enum: `ServoTypeCode`

The `ServoTypeCode` enum represents the types of servos that can be used within the `com.robotraconteur.servo` service.

- `unknown` (`0`): Represents an unknown servo type.
- `generic_revolute`: Represents a generic revolute servo.
- `generic_prismatic`: Represents a generic prismatic servo.
- `revolute_electric`: Represents an electric revolute servo.
- `prismatic_electric`: Represents an electric prismatic servo.
- `rc_servo`: Represents an RC servo.

This enum provides a set of predefined servo types. If the servo type is not listed in this enum, use `unknown` and provide additional details in the `DeviceInfo` structure.

## Enum: `ServoCapabilities`

The `ServoCapabilities` enum represents the capabilities of a servo within the `com.robotraconteur.servo` service.

- `unknown` (`0`): Indicates that the capabilities of the servo are unknown.
- `position_command` (`0x1`): Indicates that the servo supports position commands.
- `velocity_command` (`0x2`): Indicates that the servo supports velocity commands.
- `effort_command` (`0x4`): Indicates that the servo supports effort commands.
- `trapezoidal_command` (`0x8`): Indicates that the servo supports trapezoidal commands.
- `signals` (`0x1000`): Indicates that the servo supports signals

.

This enum specifies the capabilities that a servo may have. The capabilities can be combined using bitwise OR.

## Enum: `ServoMode`

The `ServoMode` enum represents the different modes of operation for a servo within the `com.robotraconteur.servo` service.

- `error` (`-2`): Indicates an error state.
- `disabled` (`-1`): Indicates that the servo is disabled.
- `halt` (`0`): Indicates that the servo is in a halted state.
- `position_command`: Indicates that the servo is in position command mode.
- `velocity_command`: Indicates that the servo is in velocity command mode.
- `effort_command`: Indicates that the servo is in effort command mode.
- `trapezoidal_command`: Indicates that the servo is in trapezoidal command mode.

This enum specifies the possible modes of operation for a servo. The servo mode determines the type of command that can be sent to the servo.

## Enum: `ServoStateFlags`

The `ServoStateFlags` enum represents the state flags of a servo within the `com.robotraconteur.servo` service.

- `unknown` (`0`): Indicates an unknown state.
- `ready` (`0x1`): Indicates that the servo is ready.
- `streaming` (`0x2`): Indicates that the servo is streaming data.
- `warning` (`0x4`): Indicates a warning state.
- `error` (`0x8`): Indicates an error state.
- `fatal_error` (`0x10`): Indicates a fatal error state.
- `e_stop` (`0x20`): Indicates an emergency stop state.
- `homed` (`0x40`): Indicates that the servo has been homed.
- `homing_required` (`0x80`): Indicates that homing is required for the servo.
- `communication_failure` (`0x100`): Indicates a communication failure with the servo.
- `valid_command` (`0x200`): Indicates that the command sent to the servo is valid.
- `enabled` (`0x400`): Indicates that the servo is enabled.

This enum represents the various state flags that a servo can have. The flags can indicate the readiness, status, and error conditions of the servo.

## Structure: `ServoInfo`

The `ServoInfo` structure contains information about a servo.

- `field DeviceInfo device_info`

    Information about the device.

- `field ServoTypeCode servo_type`

    The type of the servo.

- `field uint32 capabilities`

    The capabilities of the servo, specified using the `ServoCapabilities` enum.

- `field uint32 axis_count`

    The number of axes (joints) controlled by the servo.

- `field JointPositionUnits{list} position_units`

    The units of the joint positions.

- `field JointEffortUnits{list} effort_units`

    The units of the joint efforts.

- `field double[] position_min`

    The minimum joint positions.

- `field double[] position_max`

    The maximum joint positions.

- `field double[] velocity_min`

    The minimum joint velocities.

- `field double[] velocity_max`

    The maximum joint velocities.

- `field double[] acceleration_min`

    The minimum joint accelerations.

- `field double[] acceleration_max`

    The maximum joint accelerations.

- `field double[] torque_min`

    The minimum joint torques.

- `field double[] torque_max`

    The maximum joint torques.

- `field double[] gear_ratio`

    The gear ratios for the joints.

- `field double[] sensor_resolution`

    The resolution of the joint position sensors.



- `field double[] effort_command_resolution`

    The resolution of the effort commands.

- `field ParameterInfo{list} parameter_info`

    Information about the parameters of the servo.

- `field SignalInfo{list} signal_info`

    Information about the signals supported by the servo.

- `field varvalue{string} extended`

    Additional extended information about the servo.

This structure provides detailed information about a servo, including its type, capabilities, joint properties, sensor resolution, and more.

## Structure: `ServoState`

The `ServoState` structure represents the state of a servo.

- `field TimeSpec3 ts`

    The timestamp of the servo state.

- `field uint64 seqno`

    The sequence number of the servo state.

- `field uint32 servo_state_flags`

    The state flags of the servo, specified using the `ServoStateFlags` enum.

- `field ServoMode mode`

    The current mode of operation of the servo, specified using the `ServoMode` enum.

- `field double[] position`

    The current joint positions.

- `field double[] velocity`

    The current joint velocities.

- `field double[] acceleration`

    The current joint accelerations.

- `field double[] effort`

    The current joint efforts.

- `field double[] position_command`

    The commanded joint positions.

- `field double[] velocity_command`

    The commanded joint velocities.

- `field double[] effort_command`

    The commanded joint efforts.

This structure provides information about the state of a servo, including its position, velocity, effort, and command values.

## Structure: `ServoStateSensorData`

The `ServoStateSensorData` structure contains the sensor data for the state of a servo.

- `field SensorDataHeader data_header`

    The header information of the sensor data.

- `field ServoState servo_state`

    The state of the servo.

- `field varvalue{string} extended`

    Additional extended information about the sensor data.

This structure combines the sensor data header with the servo state.

## Structure: `ServoCommand`

The `ServoCommand` structure represents a command sent to a servo.

- `field uint64 seqno`

    The sequence number of the command.

- `field uint64 status_seqno`

    The sequence number of the status associated with the command.

- `field double[] command`

    The command values for the servo.

This structure is used to send commands to the servo, such as position commands, velocity commands, or effort commands.

## Object: `Servo`

The `Servo` object represents a servo device.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Information about the device.

- `property ServoInfo servo_info [readonly,nolock]`

    Information about the servo.

- `property ServoMode mode [nolockread]`

    The current mode of operation of the servo.

- `property IsochInfo isoch_info [readonly,nolock]`

    Information about the isochronous communication settings.

- `property uint32 isoch_downsample [perclient]`

    The downsample factor for isochronous communication.

### Wires

- `wire double[] position [readonly,nolock]`

    The current joint positions of the servo.

- `wire double[] velocity [readonly,nolock]`

    The current joint velocities of the servo.

- `wire ServoState servo_state [readonly,nolock]`

    The state of the servo.

- `wire ServoCommand position_command [writeonly]`

    Command to set the position of the servo.

- `wire ServoCommand velocity_command [writeonly]`

    Command to set the velocity of the servo.

- `wire ServoCommand effort_command [writeonly]`

    Command to set the effort of the servo.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    The current time of the servo device clock.

### Pipes

- `pipe ServoStateSensorData servo_state_sensor_data [readonly,nolock]`

    The sensor data for the state of the servo.

### Functions

- `function void halt() [urgent,nolock]`

    Halts the operation of the servo.

- `function void trapezoidal_move(double[] target_pos, double[] target_vel, double[] vel, double[] accel)`

    Performs a trapezoidal move to the specified target positions and velocities, using the given velocity and acceleration limits.

- `function varvalue getf_param(string param_name)`

    Gets the value of a parameter specified by its name.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter specified by its name.

- `function varvalue getf_signal(string signal_name)`

    Gets the value of a signal specified by its name.

- `function void setf_signal(string signal_name, varvalue value)`

    Sets the value of a signal specified by its name.

The `Servo` object provides access to servo-related functionalities, including getting and setting servo states, sending commands, and accessing servo information. It also allows control over the servo mode and provides access to isochronous communication settings.
