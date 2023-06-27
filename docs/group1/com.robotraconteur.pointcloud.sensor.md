# Service: `com.robotraconteur.pointcloud.sensor`

The `com.robotraconteur.pointcloud.sensor` service provides functionality for capturing and streaming point cloud data from sensors. It defines objects and structures related to point cloud sensors and their data.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.pointcloud`: Provides structures for representing point clouds.
- `com.robotraconteur.geometry`: Contains geometric data types.
- `com.robotraconteur.sensor`: Includes structures for sensor data.
- `com.robotraconteur.device.isoch`: Provides interfaces for isochronous devices.
- `com.robotraconteur.device.clock`: Offers functionalities related to device time and clocks.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the point cloud sensor.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.param.ParameterInfo`: Provides information about the parameters associated with the point cloud sensor.
- `com.robotraconteur.pointcloud.PointCloudf`: Represents a point cloud in floating-point format.
- `com.robotraconteur.pointcloud.PointCloudPartf`: Represents a part of a point cloud in floating-point format.
- `com.robotraconteur.pointcloud.PointCloud2f`: Represents a point cloud with additional attributes in floating-point format.
- `com.robotraconteur.pointcloud.PointCloud2Partf`: Represents a part of a point cloud with additional attributes in floating-point format.
- `com.robotraconteur.geometry.Point`: Represents a point in three-dimensional space.
- `com.robotraconteur.geometry.Vector3`: Represents a three-dimensional vector.
- `com.robotraconteur.geometry.BoundingBox`: Represents a bounding box that encloses a geometric shape.
- `com.robotraconteur.sensor.SensorData`: Represents generic sensor data.
- `com.robotraconteur.device.isoch.IsochDevice`: Represents an isochronous device.
- `com.robotraconteur.device.isoch.IsochInfo`: Provides information about isochronous devices.
- `com.robotraconteur.device.clock.DeviceClock`: Represents a device clock.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the current time of a device.

## Structure: `PointCloudSensorInfo`

The `PointCloudSensorInfo` structure provides information about the point cloud sensor. It includes device information, the bounding box of the point cloud, resolution, parameter information, and extended information.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field BoundingBox bounds`

    The bounding box that encloses the point cloud.

- `field Vector3 resolution`

    The resolution of the point cloud.

- `field ParameterInfo{list} param_info`

    Provides information about the parameters of the point cloud sensor.

- `field varvalue{string} extended`

    Extended information about the point cloud sensor.

## Structure: `PointCloudSensorData`

The `PointCloudSensorData` structure represents the data captured by the point cloud sensor. It includes the sensor data and the corresponding point cloud.

- `field SensorData sensor_data`

    The sensor data associated with the point cloud.

- `field PointCloud point_cloud`

    The point cloud data captured by the sensor.

## Structure: `PointCloudPartSensorData`

The `PointCloudPartSensorData` structure represents a part of the point cloud data captured by the sensor. It includes the sensor data and the corresponding part of the point cloud.

- `field SensorData sensor_data`

    The sensor data associated with the point cloud part.

- `field PointCloudPart point_cloud`

    The part of the point cloud data captured by the sensor.

## Object: `PointCloudSensor`

The `PointCloudSensor` object represents a point cloud sensor. It implements the `Device`, `DeviceClock`, and `IsochDevice` interfaces. It provides properties, functions, and pipes for capturing and streaming point cloud data.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property PointCloudSensorInfo point_sensor_info [readonly,nolock]`

    Provides information about the point cloud sensor.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous capabilities of the point cloud sensor.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsampling factor for isochronous data streaming, specific to each client.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Provides the current time of the device clock.

### Functions

- `function PointCloud capture_point_cloud()`

    Captures and returns a complete point cloud.

- `function varvalue getf_param(string param_name)`

    Retrieves the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - `value`: The value to set.
    
### Pipes

- `pipe PointCloudSensorData point_cloud_sensor_data [readonly]`

    Provides a stream of point cloud sensor data. Each message includes the sensor data and the corresponding point cloud.

## Object: `PointCloudPartSensor`

The `PointCloudPartSensor` object represents a point cloud sensor that captures a part of the point cloud data. It implements the `Device`, `DeviceClock`, and `IsochDevice` interfaces. It provides properties, functions, and pipes for capturing and streaming point cloud data.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property PointCloudSensorInfo point_sensor_info [readonly,nolock]`

    Provides information about the point cloud sensor.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous capabilities of the point cloud sensor.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsampling factor for isochronous data streaming, specific to each client.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Provides the current time of the device clock.

### Functions

- `function PointCloudPart{generator} capture_point_cloud()`

    Captures and yields parts of the point cloud data.

- `function varvalue getf_param(string param_name)`

    Retrieves the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - `value`: The value to set.

### Pipes

- `pipe PointCloudPartSensorData point_cloud_sensor_data [readonly]`

    Provides a stream of point cloud sensor data. Each message includes the sensor data and the corresponding part of the point cloud.

## Object: `PointCloud2Sensor`

The `PointCloud2Sensor` object represents a point cloud sensor that captures point clouds with additional attributes. It implements the `PointCloudSensor`, `Device`, `DeviceClock`, and `IsochDevice` interfaces. It provides properties, functions, and pipes for capturing and streaming point cloud data.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property PointCloudSensorInfo point_sensor_info [readonly,nolock]`

    Provides information about the point cloud sensor.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous capabilities of the point cloud sensor.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsampling factor for isochronous data streaming, specific to each client.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Provides the current time of the device clock.

### Functions

- `function PointCloud capture_point_cloud()`

    Captures and returns a complete point cloud.

- `function PointCloud2 capture_point_cloud2()`

    Captures and returns a complete point cloud with additional attributes.

- `function varvalue getf_param(string param_name)`

    Retrieves the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - `value`: The value to set.
    
### Pipes

- `pipe PointCloudSensorData point_cloud_sensor_data [readonly]`

    Provides a stream of point cloud sensor data. Each message includes the sensor data and the corresponding point cloud.

- `pipe PointCloud2SensorData point_cloud2_sensor_data [readonly]`

    Provides a stream of point cloud sensor data with additional attributes. Each message includes the sensor data and the corresponding point cloud.

## Object: `PointCloud2PartSensor`

The `PointCloud2PartSensor` object represents a point cloud sensor that captures parts of the point cloud data with additional attributes. It implements the `PointCloudPartSensor`, `Device`, `DeviceClock`, and `IsochDevice` interfaces. It provides properties, functions, and pipes for capturing and streaming point cloud data.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property PointCloudSensorInfo point_sensor_info [readonly,nolock]`

    Provides information about the point cloud sensor.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous capabilities of the point cloud sensor.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsampling factor for isochronous data streaming, specific to each client.

### Wires

- `wire DeviceTime device_clock_now [readonly,nolock]`

    Provides the current time of the device clock.

### Functions

- `function PointCloudPart{generator} capture_point_cloud()`

    Captures and yields parts of the point cloud data.

- `function PointCloud2Part{generator} capture_point_cloud2()`

    Captures and yields parts of the point cloud data with additional attributes.

- `function varvalue getf_param(string param_name)`

    Retrieves the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter specified by its name.
    - `param_name`: The name of the parameter.
    - `value`: The value to set.
    
### Pipes

- `pipe PointCloudPartSensorData point_cloud_sensor_data [readonly]`

    Provides a stream of point cloud sensor data. Each message includes the sensor data and the corresponding part of the point cloud.

- `pipe PointCloud2PartSensorData point_cloud2_sensor_data [readonly]`

    Provides a stream of point cloud sensor data with additional attributes. Each message includes the sensor data and the corresponding part of the point cloud.

This completes the documentation for the `com.robotraconteur.pointcloud.sensor` service.