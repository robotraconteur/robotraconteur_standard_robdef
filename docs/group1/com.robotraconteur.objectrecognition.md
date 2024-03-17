# Service: `com.robotraconteur.objectrecognition`

The `com.robotraconteur.objectrecognition` service is used to represent object recognition capabilities and provides functionality for recognizing and detecting objects.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Provides functionality for object identification.
- `com.robotraconteur.geometry`: Contains definitions related to geometric objects.
- `com.robotraconteur.geometry.shapes`: Provides geometric shape definitions.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.device.isoch`: Offers functionality for isochronous device communication.
- `com.robotraconteur.sensordata`: Contains definitions for sensor data.
- `com.robotraconteur.device.clock`: Provides functionalities related to device clock synchronization.
- `com.robotraconteur.fiducial`: Contains definitions for fiducial markers.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier for an object.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the object recognition sensor.
- `com.robotraconteur.device.DeviceClass`: Represents the class of a device.
- `com.robotraconteur.device.isoch.IsochDevice`: Represents an isochronous device.
- `com.robotraconteur.device.isoch.IsochInfo`: Contains information about an isochronous device.
- `com.robotraconteur.param.ParameterInfo`: Provides information about the parameters associated with the object recognition sensor.
- `com.robotraconteur.geometry.shapes.ShapeObject`: Represents a geometric shape object.
- `com.robotraconteur.geometry.NamedPoseWithCovariance`: Represents a named pose with covariance.
- `com.robotraconteur.geometry.BoundingBox`: Represents a bounding box in 3D space.
- `com.robotraconteur.geometry.Vector3`: Represents a 3D vector.
- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header information of sensor data.
- `com.robotraconteur.device.clock.DeviceClock`: Represents the clock of a device.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the time information of a device.
- `com.robotraconteur.fiducial.Fiducial`: Represents a fiducial marker.

## Structure: `ObjectRecognitionTemplate`

The `ObjectRecognitionTemplate` structure is used to define an object recognition template. It contains information about an object that can be recognized by the object recognition sensor.

- `field Identifier object_identifier`

    The identifier of the object.

- `field DeviceClass object_class`

    The class of the object.

- `field ShapeObject object_shape`

    The geometric shape of the object.

- `field Fiducial{list} object_fiducials`

    The fiducial markers associated with the object.

- `field varvalue{string} extended`

    Extended information about the object recognition template.

## Structure: `RecognizedObject`

The `RecognizedObject` structure represents an object recognized by the object recognition sensor. It contains information about the recognized object, such as its pose and confidence level.

- `field Identifier recognized_object`

    The identifier of the recognized object.

- `field DeviceClass recognized_object_class`

    The class of the recognized object.

- `field NamedPoseWithCovariance pose`

    The pose the recognized object, represented by a named pose with covariance.

- `field double confidence`

    The confidence level of the recognition result.

- `field varvalue{string} extended`

    Extended information about the recognized object.

## Structure: `RecognizedObjects`

The `RecognizedObjects` structure represents a collection of recognized objects. It contains a list of `RecognizedObject` structures and additional data associated with the recognition process.

- `field RecognizedObject{list} recognized_objects`

    The list of recognized objects.

- `field varvalue source_data`

    The source data used for object recognition.

- `field varvalue{string} extended`

    Extended information about the recognized objects.

## Structure: `ObjectRecognitionSensorInfo`

The `ObjectRecognitionSensorInfo` structure provides information about the object recognition sensor. It includes device information, range details, parameter information, supported object templates, and extended data.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field BoundingBox range`

    The range of the object recognition sensor, represented by a bounding box.

- `field Vector3 resolution`

    The resolution of the object recognition sensor in 3D space.

- `field ParameterInfo{list} param_info`

    Provides information about the parameters of the object recognition sensor. Used with the `getf_param` and `setf_param` functions.

- `field Identifier{list} object_template_identifiers`

    The identifiers of the object templates supported by the sensor.

- `field DeviceClass{list} object_template_classes`

    The classes of the object templates supported by the sensor.

- `field varvalue{string} extended`

    Extended information about the object recognition sensor.

## Structure: `ObjectRecognitionSensorData`

The `ObjectRecognitionSensorData` structure represents the data collected by the object recognition sensor. It includes the sensor data header and the recognized objects.

- `field SensorDataHeader sensor_data`

    The header information of the sensor data.

- `field RecognizedObjects recognized_objects`

    The recognized objects captured by the object recognition sensor.

## Object: `ObjectRecognitionSensor`

### Implements

- `Device`
- `DeviceClock`
- `IsochDevice`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property ObjectRecognitionSensorInfo object_recognition_sensor_info [readonly,nolock]`

    Provides information about the object recognition sensor.

### Functions

- `function RecognizedObjects capture_recognized_objects()`

    Captures and returns the recognized objects detected by the object recognition sensor.

- `function varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

- `function ObjectRecognitionTemplate getf_object_template(Identifier object_identifier)`

    Retrieves the object recognition template for a specific object identifier.
    - `object_identifier`: The identifier of the object.
    - Returns: The object recognition template for the specified object identifier.

- `function ObjectRecognitionTemplate getf_object_class_template(Identifier object_class)`

    Retrieves the object recognition template for a specific object class.
    - `object_class`: The class of the object.
    - Returns: The object recognition template for the specified object class.

### Pipes

- `pipe ObjectRecognitionSensorData object_recognition_sensor_data [readonly]`

    A continuous stream of object recognition sensor data produced by the object recognition sensor.

### Properties (IsochDevice)

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous communication capabilities of the object recognition sensor.

- `property uint32 isoch_downsample [perclient]`

    The downsampling factor for isochronous data transmitted by the object recognition sensor.

### Wires (DeviceClock)

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Provides the current time of the object recognition sensor.
