# Service: `com.robotraconteur.sensor`

The `com.robotraconteur.sensor` service provides functionality for representing various types of sensors.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.sensordata`: Provides functionality for sensor data.
- `com.robotraconteur.device`: Includes definitions for device-related operations.
- `com.robotraconteur.param`: Defines parameter-related information.
- `com.robotraconteur.geometry`: Contains geometry-related definitions.
- `com.robotraconteur.units`: Provides units of measurement.
- `com.robotraconteur.datatype`: Defines data types.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header of sensor data.
- `com.robotraconteur.device.DeviceInfo`: Provides standard device information.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.param.ParameterInfo`: Provides information about parameters.
- `com.robotraconteur.geometry.Vector2`: Represents a 2D vector.
- `com.robotraconteur.geometry.Vector3`: Represents a 3D vector.
- `com.robotraconteur.geometry.Vector6`: Represents a 6D vector.
- `com.robotraconteur.geometry.Wrench`: Represents a wrench.
- `com.robotraconteur.units.SIUnit`: Represents a measurement unit using the International System of Units (SI).
- `com.robotraconteur.datatype.DataType`: Defines the data type used for sensor data.

## Enum: `SensorTypeCode`

The `SensorTypeCode` enum represents the types of sensors that can be used within the `com.robotraconteur.sensor` service.

- `unknown` (`0`): Represents an unknown sensor type.
- `generic_digital`: Represents a generic digital sensor.
- `generic_analog`: Represents a generic analog sensor.
- `pushbutton`: Represents a push button sensor.
- `dial`: Represents a dial sensor.
- `limitswitch`: Represents a limit switch sensor.
- `infrared`: Represents an infrared sensor.
- `pressure`: Represents a pressure sensor.
- `vacuum`: Represents a vacuum sensor.
- `temperature`: Represents a temperature sensor.
- `humidity`: Represents a humidity sensor.
- `level`: Represents a level sensor.
- `contact`: Represents a contact sensor.
- `ultrasonic`: Represents an ultrasonic sensor.
- `magnetic`: Represents a magnetic sensor.
- `encoder`: Represents an encoder sensor.
- `potentiometer`: Represents a potentiometer sensor.
- `resolver`: Represents a resolver sensor.
- `linear_encoder`: Represents a linear encoder sensor.
- `linear_potentiometer`: Represents a linear potentiometer sensor.
- `lvds`: Represents an LVDS sensor.
- `accelerometer`: Represents an accelerometer sensor.
- `gyroscopic`: Represents a gyroscopic sensor.
- `velocity`: Represents a velocity sensor.
- `angular_velocity`: Represents an angular velocity sensor.
- `spatial_velocity`: Represents a spatial velocity sensor.
- `torque`: Represents a torque sensor.
- `force`: Represents a force sensor.
- `proximity`: Represents a proximity sensor.
- `voltage`: Represents a voltage sensor.
- `current`: Represents a current sensor.
- `laser`: Represents a laser sensor.
- `flow`: Represents a flow sensor.
- `pyrometer`: Represents a pyrometer sensor.
- `forcetorque`:

 Represents a force-torque sensor.
- `light_color`: Represents a light color sensor.
- `light_intensity`: Represents a light intensity sensor.
- `object_color`: Represents an object color sensor.
- `altitude`: Represents an altitude sensor.
- `generic_word`: Represents a generic word sensor.
- `generic_vector`: Represents a generic vector sensor.
- `position`: Represents a position sensor.
- `angle`: Represents an angle sensor.
- `acceleration`: Represents an acceleration sensor.
- `angular_acceleration`: Represents an angular acceleration sensor.
- `inclinometer`: Represents an inclinometer sensor.
- `tilt`: Represents a tilt sensor.
- `motion`: Represents a motion sensor.
- `radiation`: Represents a radiation sensor.
- `photoelectric`: Represents a photoelectric sensor.
- `leak`: Represents a leak sensor.
- `chemical`: Represents a chemical sensor.
- `particle`: Represents a particle sensor.
- `metal`: Represents a metal sensor.
- `smoke`: Represents a smoke sensor.
- `flame`: Represents a flame sensor.
- `vibration`: Represents a vibration sensor.
- `mark`: Represents a mark sensor.
- `contamination`: Represents a contamination sensor.
- `inertial`: Represents an inertial sensor.
- `magnetometer`: Represents a magnetometer sensor.
- `navigation`: Represents a navigation sensor.
- `tactile`: Represents a tactile sensor.
- `meteorological`: Represents a meteorological sensor.
- `horizon`: Represents a horizon sensor.
- `sun`: Represents a sun sensor.
- `star`: Represents a star sensor.
- `moon`: Represents a moon sensor.
- `attitude`: Represents an attitude sensor.
- `airspeed`: Represents an airspeed sensor.
- `distance`: Represents a distance sensor.
- `heading`: Represents a heading sensor.
- `safety`: Represents a safety sensor.
- `door`: Represents a door sensor.
- `security`: Represents a security sensor.
- `other` (`0x8000`): Represents another sensor type.
- `vendor_defined` (`0x80000`): Represents a vendor-defined sensor type.

This enum provides a set of predefined sensor types. If the sensor type is not listed in this enum, use `unknown` and provide additional information in the `DeviceInfo` field.

## Enum: `SensorDataFlags`

The `SensorDataFlags` enum represents the flags associated with sensor data.

- `unknown` (`0`): Indicates that the flags of the sensor data are unknown.
- `enabled` (`0x1`): Indicates that the sensor is enabled.
- `streaming` (`0x2`): Indicates that the sensor is in streaming mode.
- `calibrated` (`0x4`): Indicates that the sensor data is calibrated.
- `calibration_error` (`0x8`): Indicates that a calibration error has occurred.
- `out_of_range` (`0x10`): Indicates that the sensor data is out of range.
- `out_of_range_high` (`0x20`): Indicates that the sensor data is higher than the allowed range.
- `out_of_range_low` (`0x40`): Indicates that the sensor data is lower than the allowed range.
- `warning` (`0x80`): Indicates a warning condition is present.
- `error` (`0x100`): Indicates an error condition is present.
- `fatal_error` (`0x200`): Indicates a fatal error condition is present.
- `ready` (`0x400`): Indicates that the sensor is ready for operation.

This enum provides a set of flags associated with sensor data.

## Structure: `SensorInfo`

The `SensorInfo` structure is

 used to provide information about a sensor. It is returned by the `sensor_info` property of the `Sensor` object.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field SensorTypeCode sensor_type`

    The type of the sensor.

- `field SIUnit{list} units`

    The units of the sensor data. The units are typically SI units.

- `field DataType data_type`

    The data type of the sensor data. The data type is typically a double scalar or vector.

- `field double[] sensor_resolution`

    The resolution of the sensor.

- `field bool analog_sensor`

    Indicates if the sensor is an analog sensor.

- `field double update_frequency`

    The update frequency of the sensor.

- `field ParameterInfo{list} parameter_info`

    Provides information about the parameters of the sensor. Used with the `getf_param` and `setf_param` functions.

- `field varvalue{string} extended`

    Extended information about the sensor.

## Structure: `SensorData`

The `SensorData` structure is used to represent sensor data.

- `field SensorDataHeader data_header`

    The header of the sensor data.

- `field uint32 data_flags`

    The flags associated with the sensor data.

- `field double[] data`

    The sensor data values.

- `field DataType data_type`

    The data type of the sensor data. The data type is typically a double scalar or vector.

- `field SIUnit{list} data_units`

    The units of the sensor data. The units are typically SI units.

- `field varvalue{string} parameters`

    Additional parameters associated with the sensor data.

- `field varvalue{string} extended`

    Extended information about the sensor data.

This structure represents sensor data, including the data header, flags, values, data type, units, parameters, and extended information.

## Object: `Sensor`

### Implements

    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The value of the sensor.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data.

### Functions

- `function varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

This object represents a sensor, providing access to the sensor's device information, sensor information, sensor value, sensor data, and parameter functions.

## Object: `Vector2Sensor`

### Implements

    - Device
    - Sensor

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The value of the sensor.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data.

### Functions

- `function

 varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

### Wires

- `wire Vector2 vector2_sensor_value [readonly,nolock]`

    The value of the sensor as a 2D vector.

This object represents a sensor that provides a 2D vector value.

## Object: `Vector3Sensor`

### Implements

    - Sensor
    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The value of the sensor.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data.

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

- `wire Vector3 vector3_sensor_value [readonly,nolock]`

    The value of the sensor as a 3D vector.

This object represents a sensor that provides a 3D vector value.

## Object: `Vector6Sensor`

### Implements

    - Sensor
    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The value of the sensor.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data.

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

- `wire Vector6 vector6_sensor_value [readonly,nolock]`

    The value of the sensor as a 6D vector.

This object represents a sensor that provides a 6D vector value.

## Object: `WrenchSensor`

### Implements

    - Sensor
    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The value of the

 sensor.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data.

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

- `wire Wrench wrench_sensor_value [readonly,nolock]`

    The value of the sensor as a wrench.

This object represents a sensor that provides a wrench value.

## Object: `FreeformSensor`

### Implements

    - Sensor
    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The value of the sensor.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data.

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

- `wire varvalue freeform_sensor_value [readonly,nolock]`

    The value of the sensor in freeform format.

This object represents a sensor that provides a freeform value.
