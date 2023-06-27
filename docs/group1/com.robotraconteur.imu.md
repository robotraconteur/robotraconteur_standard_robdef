# Service: `com.robotraconteur.imu`

The `com.robotraconteur.imu` service provides functionality for Inertial Measurement Units (IMUs), which are used to measure various aspects of motion and orientation.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.sensor`: Provides functionality for sensor-related operations.
- `com.robotraconteur.geometry`: Includes geometric data types.
- `com.robotraconteur.device`: Provides functionality for device-related operations.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.sensor.Sensor`: Serves as the base interface for sensors.
- `com.robotraconteur.sensor.SensorInfo`: Represents information about a sensor.
- `com.robotraconteur.sensor.SensorData`: Contains data from a sensor.
- `com.robotraconteur.geometry.Vector3`: Represents a 3D vector.
- `com.robotraconteur.geometry.Quaternion`: Represents a quaternion for orientation.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.DeviceInfo`: Provides information about a device.

## Structure: `ImuState`

The `ImuState` structure represents the state of an IMU at a given time.

- `field Vector3 angular_velocity`

    The angular velocity measured by the IMU.

- `field double[3,3] angular_velocity_covariance`

    The covariance matrix of the angular velocity measurements.

- `field Vector3 linear_acceleration`

    The linear acceleration measured by the IMU.

- `field double[3,3] linear_acceleration_covariance`

    The covariance matrix of the linear acceleration measurements.

- `field Quaternion orientation`

    The orientation of the IMU represented as a quaternion.

- `field double[3,3] orientation_covariance`

    The covariance matrix of the orientation measurements.

## Object: `ImuSensor`

### Implements

- Device
- Sensor

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the sensor.

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

- `wire ImuState imu_state [readonly,nolock]`

    The state of the IMU stored in an `ImuState` structure.

- `wire double[] sensor_value [readonly,nolock]`

    The value of the sensor. In the case of an IMU, this represents the raw sensor data.

### Pipes

- `pipe SensorData sensor_data [readonly,nolock]`

    A pipe for streaming sensor data.