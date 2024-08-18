# com.robotraconteur.servo

Info file yaml entries for [com.robotraconteur.servo](../group1/com.robotraconteur.servo.md)

The `ServoInfo` structure is used to transmit information about a servo device.

## ServoInfo

The `ServoInfo` structure is used to transmit information about a servo device.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the servo.

### servo_type

Type: `string`

The type of servo. See the [ServoTypeCode](../group1/com.robotraconteur.servo.md#enum-servotypecode) enum 
for a list of standard servo types. Use the string representation of the enum value. Use `unknown`
if the servo type is not listed. The `device_class` field can be used to specify the servo type
if it is not listed in the enum.

### capabilities

Type: List&lt;`string`&gt;

A list of capabilities that are loaded into a bit-flag field in the `ServoInfo` structure. See
the [ServoCapabilityCode](../group1/com.robotraconteur.robotics.robot.md#enum-servocapabilitycode) enum for a list of 
standard capabilities. Use the string representation of the enum value.

### axis_count

Type: `int`

The number of axes of the servo unit.

### position_units

Type: List&lt;[JointPositionUnits](../group1/com.robotraconteur.servo.md#enum-jointpositionunits)&gt;

The units of the servo position. See the [JointPositionUnits](../group1/com.robotraconteur.servo.md#enum-jointpositionunits) enum
for a list of standard units. Use the string representation of the enum value.

Defaults to radians or meters if not specified depending on the servo type.

### effort_units

Type: List&lt;[JointEffortUnits](../group1/com.robotraconteur.servo.md#enum-jointeffortunits)&gt;

The units of the servo effort. See the [JointEffortUnits](../group1/com.robotraconteur.servo.md#enum-jointeffortunits) enum
for a list of standard units. Use the string representation of the enum value.

Defaults to newton-meters or newtons if not specified depending on the servo type.

### position_min

Type: `List<double>`

The minimum position of the servo in the position units.

### position_max

Type: `List<double>`

The maximum position of the servo in the position units.

### velocity_min

Type: `List<double>`

The minimum velocity of the servo in the position units per second.

### velocity_max

Type: `List<double>`

The maximum velocity of the servo in the position units per second.

### acceleration_min

Type: `List<double>`

The minimum acceleration of the servo in the position units per second squared.

### torque_min

Type: `List<double>`

The minimum effort of the servo in the effort units.

### torque_max

Type: `List<double>`

The maximum effort of the servo in the effort units.

### gear_ratio

Type: `List<double>`

The gear ratio of the servo. The gear ratio is the ratio of the input to output speed of the servo.

### sensor_resolution

Type: `List<double>`

The resolution of the sensor data.

### effort_command_resolution

Type: `List<double>`

The resolution of the effort command signal.

### parameter_info

Type: List&lt;[ParameterInfo](param.md)&gt;

The parameters that can be get/set using the `getf_param` and `setf_param` functions.

This field is usually populated by the driver, and is not typically configured using the YAML file.

### signal_info

Type: List&lt;[SignalInfo](signal.md)&gt;

The input and output signals of the servo available for general use.
