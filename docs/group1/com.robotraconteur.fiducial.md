# Service: `com.robotraconteur.fiducial`

The `com.robotraconteur.fiducial` service provides functionality for working with fiducial markers and fiducial sensors.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Includes functionality for identifying fiducial markers.
- `com.robotraconteur.geometry`: Provides geometric calculations and definitions.
- `com.robotraconteur.color`: Defines color-related structures and operations.
- `com.robotraconteur.image`: Supports working with image data, including compressed images.
- `com.robotraconteur.device`: Offers functionality for working with devices.
- `com.robotraconteur.param`: Provides parameter-related information and operations.
- `com.robotraconteur.sensordata`: Defines structures for sensor data.
- `com.robotraconteur.device.isoch`: Supports isochronous communication with devices.
- `com.robotraconteur.device.clock`: Provides functionality for device clock synchronization.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier for fiducial markers.
- `com.robotraconteur.geometry.NamedPose`: Defines a named pose in 3D space.
- `com.robotraconteur.geometry.NamedPoseWithCovariance`: Represents a named pose with covariance in 3D space.
- `com.robotraconteur.geometry.Point2D`: Represents a 2D point in space.
- `com.robotraconteur.geometry.Size2D`: Defines the size of a 2D object.
- `com.robotraconteur.geometry.BoundingBox`: Represents a bounding box in 3D space.
- `com.robotraconteur.geometry.Vector3`: Represents a 3D vector.
- `com.robotraconteur.color.ColorRGBA`: Represents a color in RGBA format.
- `com.robotraconteur.image.CompressedImage`: Represents a compressed image.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.DeviceInfo`: Provides information about the device associated with the fiducial sensor.
- `com.robotraconteur.param.ParameterInfo`: Provides information about the parameters associated with the fiducial sensor.
- `com.robotraconteur.sensordata.SensorDataHeader`: Contains the header information for sensor data.
- `com.robotraconteur.device.isoch.IsochDevice`: Represents an isochronous device.
- `com.robotraconteur.device.isoch.IsochInfo`: Provides information about isochronous communication settings.
- `com.robotraconteur.device.clock.DeviceClock`: Represents a device clock for time synchronization.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the current time of a device clock.

### Structure: Fiducial

The `Fiducial` structure represents a fiducial marker.

- `field Identifier fiducial_marker_class`

    The class of the fiducial marker.

- `field string fiducial_marker`

    The identifier of the fiducial marker.

- `field NamedPose fiducial_pose`

    The pose of the fiducial marker.

- `field double fiducial_scale`

    The scale of the fiducial marker.

- `field ColorRGBA foreground_color`

    The foreground color of the fiducial marker.

- `field ColorRGBA background_color`

    The background color of the fiducial marker.

### Structure: FiducialInfo

The `FiducialInfo` structure provides information about a fiducial marker.

- `field Identifier fiducial_marker_class`

    The class of the fiducial marker.

- `field string fiducial_marker`

    The identifier of the fiducial marker.

- `field string fiducial_marker_range`

    The range of the fiducial marker.

- `field Size2D default_size`

    The default size of the fiducial marker.

- `field ColorRGBA default_foreground_color`

    The default foreground color of the fiducial marker.

- `field ColorRGBA default_background_color`

    The default background color of the fiducial marker.

- `field CompressedImage marker_template`

    The marker template image of the fiducial marker.

- `field Point2D marker_template_centroid`

    The centroid of the marker template image.

- `field varvalue{string} extended`

    Extended information about the fiducial marker.

### Structure: RecognizedFiducial

The `RecognizedFiducial` structure represents a recognized fiducial marker.

- `field Identifier fiducial_marker_class`

    The class of the fiducial marker.

- `field string fiducial_marker`

    The identifier of the fiducial marker.

- `field NamedPoseWithCovariance pose`

    The pose of the fiducial marker with covariance.

- `field double confidence`

    The confidence level of the fiducial marker recognition.

- `field varvalue{string} extended`

    Extended information about the recognized fiducial marker.

### Structure: RecognizedFiducials

The `RecognizedFiducials` structure contains a list of recognized fiducial markers.

- `field RecognizedFiducial{list} recognized_fiducials`

    The list of recognized fiducial markers.

- `field varvalue source_data`

    The source data associated with the recognized fiducial markers.

- `field varvalue{string} extended`

    Extended information about the recognized fiducial markers.

### Structure: FiducialSensorInfo

The `FiducialSensorInfo` structure provides information about a fiducial sensor.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field BoundingBox range`

    The range of the fiducial sensor.

- `field Vector3 resolution`

    The resolution of the fiducial sensor.

- `field ParameterInfo{list} param_info`

    Provides information about the parameters of the fiducial sensor.

- `field FiducialInfo{list} fiducial_info`

    Provides information about the fiducial markers supported by the sensor.

- `field varvalue{string} extended`

    Extended information about the fiducial sensor.

### Structure: FiducialSensorData

The `FiducialSensorData` structure represents data from a fiducial sensor.

- `field SensorDataHeader sensor_data`

    The header information for the sensor data.

- `field RecognizedFiducials fiducials`

    The recognized fiducial markers in the sensor data.

### Object: FiducialSensor

The `FiducialSensor` object represents a fiducial sensor.

### Implements

- Device
- DeviceClock
- IsochDevice

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property FiducialSensorInfo fiducial_sensor_info [readonly,nolock]`

    Provides information about the fiducial sensor.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous communication settings.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsample factor for isochronous communication, with per-client access.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Represents the current time of the device clock.

### Functions

- `function RecognizedFiducials capture_fiducials()`

    Captures fiducial markers and returns the recognized fiducials.

- `function varvalue getf_param(string param_name)`

    Retrieves the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

### Pipes

- `pipe FiducialSensorData fiducials_sensor_data [readonly]`

    Provides fiducial sensor data in the form of the `FiducialSensorData` structure.
