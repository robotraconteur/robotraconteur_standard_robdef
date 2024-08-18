# com.robotraconteur.sensor

Info file yaml entries for [com.robotraconteur.sensor](../group1/com.robotraconteur.sensor.md)

## SensorInfo

The `SensorInfo` structure is used to transmit information about a sensor.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the sensor.

### sensor_type

Type: `string`

The type of sensor. See the [SensorTypeCode](../group1/com.robotraconteur.sensor.md#enum-sensortypecode) enum 
for a list of standard actuator types. Use the string representation of the enum value. Use `other`
if the sensor type is not listed. The `device_class` field can be used to specify the sensor type
if it is not listed in the enum.

### units

Type: `SIUnits`

The units of the sensor data.

### data_type

Type: [DataType](datatype.md)

The data type of the output data. The type may be a scalar or a vector. Typically this
will be a double scalar or vector.


### sensor_resolution

Type: `List<double>`

The resolution of the sensor data.

### analog_sensor

Type: `bool`

`true` if the sensor has an analog output, `false` otherwise.

### update_frequency

Type: `double`

The update frequency of the sensor in Hz.

Type: `List<ParameterInfo>`

A list of parameters for the actuator. The parameters can be get/set using the `getf_param` and `setf_param` functions.

This field is usually populated by the driver, and is not typically configured using the YAML file.

### extended

### extended

Type: [Extended](extended.md)

Extended information.
