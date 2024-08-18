# com.robotraconteur.actuator

Info file yaml entries for [com.robotraconteur.actuator](../group1/com.robotraconteur.actuator.md)

## ActuatorInfo

The `ActuatorInfo` structure is used to transmit information about an actuator. 

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the actuator.

### actuator_type

Type: `string`

The type of actuator. See the [ActuatorTypeCode](../group1/com.robotraconteur.actuator.md#enum-actuatortypecode) enum 
for a list of standard actuator types. Use the string representation of the enum value. Use `unknown` or `generic`
if the actuator type is not listed. The `device_class` field can be used to specify the actuator type
if it is not listed in the enum.

### command_units

Type: `SIUnits`

The units of the actuator command signal. The exact type of units will depend on the actuator type. For 
example a position servo may use radians, radians per second, or newton-meters depending on the actuator type.

### command_data_type

Type: [DataType](datatype.md)

The data type of the actuator command signal. The type may be a scalar or a vector. Typically this
will be a double scalar or vector.

### command_resolution

Type: `List<double>`

The resolution of the actuator command signal.

### bool analog_output

Type: `bool`

`true` if the actuator has an analog output, `false` otherwise.

### parameter_info

Type: `List<ParameterInfo>`

A list of parameters for the actuator. The parameters can be get/set using the `getf_param` and `setf_param` functions.

This field is usually populated by the driver, and is not typically configured using the YAML file.

### extended

Type: [Extended](extended.md)

Extended information.
