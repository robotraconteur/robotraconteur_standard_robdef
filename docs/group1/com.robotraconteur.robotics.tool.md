# Service: `com.robotraconteur.robotics.tool`

The `com.robotraconteur.robotics.tool` service represents a robotic tool or end effector.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.geometry`: Contains definitions for geometric transformations and spatial inertia.
- `com.robotraconteur.sensor`: Offers functionalities related to sensors and sensor data.
- `com.robotraconteur.robotics.joints`: Defines joint-related functionalities.
- `com.robotraconteur.units`: Defines units of measurement.
- `com.robotraconteur.sensordata`: Contains definitions for sensor data headers.
- `com.robotraconteur.device.isoch`: Provides isochronous communication functionality for devices.
- `com.robotraconteur.device.clock`: Offers functionalities related to device clocks.
- `com.robotraconteur.datetime`: Provides functionalities related to date and time.
- `com.robotraconteur.fiducial`: Contains definitions for fiducial markers.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the tool.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.geometry.Transform`: Represents a 3D transformation.
- `com.robotraconteur.geometry.SpatialInertia`: Represents spatial inertia properties.
- `com.robotraconteur.sensor.SensorTypeCode`: Represents the type of a sensor.
- `com.robotraconteur.robotics.joints.JointPositionUnits`: Represents units of joint positions.
- `com.robotraconteur.units.SIUnit`: Represents a measurement unit using the International System of Units (SI).
- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header information of sensor data.
- `com.robotraconteur.device.isoch.IsochDevice`: Represents an isochronous device.
- `com.robotraconteur.device.isoch.IsochInfo`: Contains information about isochronous communication.
- `com.robotraconteur.device.clock.DeviceClock`: Represents the clock of a device.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the time on a device clock.
- `com.robotraconteur.datetime.TimeSpec3`: Represents a timestamp with microsecond precision.
- `com.robotraconteur.fiducial.Fiducial`: Represents a fiducial marker.

## Enum: `ToolTypeCode`

The `ToolTypeCode` enum represents the types of tools that can be used within the `com.robotraconteur.robotics.tool` service.

- `unknown` (`0`): Represents an unknown tool type.
- `basic_gripper`: Represents a basic gripper tool.
- `basic_continuous_gripper`: Represents a basic continuous gripper tool.
- `pneumatic_gripper`: Represents a pneumatic gripper tool.
- `electric_gripper`: Represents an electric gripper tool.
- `vacuum_gripper`: Represents a vacuum gripper tool.
- `soft_gripper`: Represents a soft gripper tool.
- `welder`: Represents a welding tool.
- `hand`: Represents a hand tool.
- `palletizer`: Represents a palletizer tool.
- `other`: Represents another type of tool.

This enum provides a set of predefined tool types. If the tool type is not listed in this enum,

 use `unknown`
and provide additional information about the tool in the `ToolInfo` structure.

## Enum: `ToolCapabilities`

The `ToolCapabilities` enum represents the capabilities of a tool within the `com.robotraconteur.robotics.tool` service.

- `unknown` (`0`): Indicates that the capabilities of the tool are unknown.
- `open_close_command` (`0x1`): Indicates that the tool supports open/close commands.
- `continuous_command` (`0x2`): Indicates that the tool supports continuous commands.
- `homing_command` (`0x4`): Indicates that the tool supports homing commands.
- `software_reset_errors` (`0x8`): Indicates that the tool supports software reset of errors.
- `software_enable` (`0x10`): Indicates that the tool supports software enable/disable.
- `sensor_feedback` (`0x20`): Indicates that the tool provides sensor feedback.

These flags indicate the capabilities of the tool. The flags can be combined using bitwise OR operations to represent multiple capabilities.

## Enum: `ToolStateFlags`

The `ToolStateFlags` enum represents the state flags of a tool. These flags are returned by the `tool_state_flags`
property of the `ToolState` structure.

- `unknown` (`0`): Indicates that the state of the tool is unknown.
- `error` (`0x1`): Indicates that an error condition is present.
- `fatal_error` (`0x2`): Indicates that a fatal error condition is present.
- `estop` (`0x4`): Indicates that an emergency stop condition is active.
- `communication_failure` (`0x8`): Indicates a communication failure with the tool.
- `enabled` (`0x10`): Indicates that the tool is enabled.
- `ready` (`0x20`): Indicates that the tool is ready.
- `opened` (`0x40`): Indicates that the tool is in an open position.
- `closed` (`0x80`): Indicates that the tool is in a closed position.
- `between` (`0x100`): Indicates that the tool is in an intermediate position between open and closed.
- `actuating` (`0x200`): Indicates that the tool is currently actuating.
- `homing` (`0x400`): Indicates that the tool is currently homing.
- `requires_homing` (`0x800`): Indicates that the tool requires homing.
- `homed` (`0x1000`): Indicates that the tool has been homed.
- `gripping` (`0x2000`): Indicates that the tool is currently gripping.
- `missed` (`0x4000`): Indicates that a grip attempt was missed.

These flags provide information about the state of the tool. The flags can be combined using bitwise OR operations to represent multiple states.

## Structure: `ToolInfo`

The `ToolInfo` structure provides information about a tool. It is returned by the `tool_info` property of the `Tool` object.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field ToolTypeCode tool_type`

    The type of the tool.

- `field uint32 tool_capabilities`

    The capabilities of the tool represented by a combination of flags from the `ToolCapabilities` enum.

- `field Transform tcp`

    The transform from the tool center point (TCP) to the robot's base frame.

- `field SpatialInertia inertia`

    The spatial inertia properties of the tool.

- `field Fiducial{list} fiducials`

    Fiducial markers associated with the tool.



- `field double actuation_time`

    The actuation time of the tool.

- `field double close_position`

    The position of the tool when fully closed.

- `field double open_position`

    The position of the tool when fully open.

- `field double command_min`

    The minimum value of the command range for the tool.

- `field double command_max`

    The maximum value of the command range for the tool.

- `field double command_close`

    The command value to close the tool.

- `field double command_open`

    The command value to open the tool.

- `field SensorTypeCode{list} sensor_type`

    The types of sensors associated with the tool.

- `field double[] sensor_min`

    The minimum sensor values for each associated sensor.

- `field double[] sensor_max`

    The maximum sensor values for each associated sensor.

- `field SIUnit{list} sensor_units`

    The units of measurement for each associated sensor.

- `field varvalue{string} extended`

    Extended information about the tool.

This structure provides comprehensive information about the tool, including its type, capabilities, kinematic properties, fiducials, actuation parameters, sensor information, and additional extended information.

## Structure: `ToolState`

The `ToolState` structure represents the state of a tool. It is returned by the `tool_state` wire of the `Tool` object.

- `field TimeSpec3 ts`

    The timestamp of the tool state.

- `field uint64 seqno`

    The sequence number of the tool state.

- `field uint32 tool_state_flags`

    The state flags of the tool.

- `field double position`

    The current position of the tool.

- `field double command`

    The current command value of the tool.

- `field double[] sensor`

    The sensor values associated with the tool.

This structure provides information about the current state of the tool, including its position, command value, sensor values, and state flags.

## Structure: `ToolStateSensorData`

The `ToolStateSensorData` structure represents the sensor data of a tool state. It is returned by the `tool_state_sensor_data` pipe of the `Tool` object.

- `field SensorDataHeader data_header`

    The header information of the sensor data.

- `field ToolState tool_state`

    The tool state information.

This structure combines the sensor data header and the tool state information, providing a unified representation of the tool state and its associated sensor data.

## Object: `Tool`

### Implements

- `Device`
- `DeviceClock`
- `IsochDevice`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property ToolInfo tool_info [readonly,nolock]`

    Provides information about the tool.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous communication of the tool.

- `property uint32 isoch_downsample [perclient]`

    The downsample value for isochronous communication.

- `property DeviceTime device_clock_now [readonly,nolock]`

    The current time on the device clock.

### Functions

- `function void open()`

    Opens the tool.

- `function void close()`

    Closes the tool.

- `function void halt() [urgent]`

    Halts the tool immediately.

- `function void setf_command(double command)`

    Sets the command value of the tool.
    - `command`: The command value to set.

- `function varvalue getf_param(string param_name)`

    Gets the value of a parameter

.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter.
    - `param_name`: The name of the parameter.
    - `value`: The value to set.

- `function void enable()`

    Enables the tool.

- `function void disable() [urgent]`

    Disables the tool immediately.

- `function void reset_errors()`

    Resets the errors of the tool.

- `function void home()`

    Initiates the homing process for the tool.

### Wires

- `wire ToolState tool_state [readonly,nolock]`

    The state of the tool stored in a `ToolState` structure.

- `pipe ToolStateSensorData tool_state_sensor_data [readonly,nolock]`

    The sensor data of the tool state stored in a `ToolStateSensorData` structure.
