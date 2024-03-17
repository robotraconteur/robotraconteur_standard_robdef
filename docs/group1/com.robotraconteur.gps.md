# Service: `com.robotraconteur.gps`

The `com.robotraconteur.gps` service provides functionality for GPS (Global Positioning System) sensors.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.sensor`: Provides functionality for sensor-related operations.
- `com.robotraconteur.device`: Includes definitions for device-related operations.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.sensor.Sensor`: Serves as the base interface for sensors.
- `com.robotraconteur.sensor.SensorInfo`: Represents information about the GPS sensor.
- `com.robotraconteur.sensor.SensorData`: Contains sensor data.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the GPS sensor.
- `com.robotraconteur.datetime.DateTimeUTC`: Represents a timestamp in Coordinated Universal Time (UTC).

## Enum: `GpsMeasurementStatusCode`

The `GpsMeasurementStatusCode` enum represents the status codes for GPS measurements within the `com.robotraconteur.gps` service.

- `no_fix` (`-1`): Indicates that no fix is available.
- `fix` (`0`): Indicates a standard GPS fix.
- `sbas_fix` (`1`): Indicates an SBAS (Satellite-Based Augmentation System) fix.
- `gbas_fix` (`2`): Indicates a GBAS (Ground-Based Augmentation System) fix.
- `dgps_fix` (`18`): Indicates a DGPS (Differential GPS) fix.
- `waas_fix` (`33`): Indicates a WAAS (Wide Area Augmentation System) fix.

This enum provides predefined status codes for GPS measurements.

## Enum: `GpsMeasureSourceFlags`

The `GpsMeasureSourceFlags` enum represents the source flags for GPS measurements within the `com.robotraconteur.gps` service.

- `none` (`0`): No source flags are set.
- `gps` (`0x1`): Indicates GPS as the measurement source.
- `points` (`0x2`): Indicates points as the measurement source.
- `doppler` (`0x4`): Indicates Doppler as the measurement source.
- `altimeter` (`0x8`): Indicates an altimeter as the measurement source.
- `magnetic` (`0x10`): Indicates a magnetic sensor as the measurement source.
- `gyro` (`0x20`): Indicates a gyro sensor as the measurement source.
- `accel` (`0x40`): Indicates an accelerometer as the measurement source.

This enum provides predefined source flags for GPS measurements.

## Enum: `GpsCovarianceTypeCode`

The `GpsCovarianceTypeCode` enum represents the types of GPS covariance within the `com.robotraconteur.gps` service.

- `unknown` (`0`): The covariance type is unknown.
- `approximated` (`1`): The covariance is approximated.
- `diagonal_known` (`2`): The diagonal covariance is known.
- `known` (`3`): The complete covariance is known.

This enum provides predefined covariance types for GPS measurements.

## Structure: `GpsStatus`

The `GpsStatus` structure is used to represent the status of GPS measurements within the `com.robotraconteur.gps` service.

- `field uint16 satellites_used`

    The number of satellites used for the GPS fix.

- `field int32[] satellite_used_prn`

    An array of PRN (Pseudo-Random Noise) values for the satellites used.

- `field uint16 satellites_visible`

    The number of visible satellites.

- `field int32[] satellite_visible_prn`

    An array of PRN values for the visible satellites.

- `field int32[] satellite_visible_z`

    An array of elevation angles for the visible satellites.

- `field int32[] satellite_visible_azimuth`

    An array of azimuth angles for the visible satellites.

- `field int32[] satellite_visible_snr`

    An array of signal-to-noise ratios (SNR) for the visible satellites.

- `field GpsMeasurementStatusCode status_code`

    The status code of the GPS measurements.

- `field uint16 motion_source_flags`

    The source flags for motion-related measurements.

- `field uint16 orientation_source_flags`

    The source flags for orientation-related measurements.

- `field uint16 position_source_flags`

    The source flags for position-related measurements.

## Structure: `GpsState`

The `GpsState` structure represents the state of the GPS sensor within the `com.robotraconteur.gps` service.

- `field GpsStatus status`

    The GPS status information.

- `field DateTimeUTC time`

    The timestamp of the GPS state.

- `field double latitude_deg`

    The latitude in degrees.

- `field double longitude_deg`

    The longitude in degrees.

- `field double altitude`

    The altitude.

- `field double track_deg`

    The track angle in degrees.

- `field double speed`

    The speed.

- `field double climb`

    The climb rate.

- `field double pitch`

    The pitch angle in degrees.

- `field double roll`

    The roll angle in degrees.

- `field double dip`

    The magnetic dip angle.

- `field double gdop`

    The Geometric Dilution of Precision (GDOP).

- `field double pdop`

    The Position Dilution of Precision (PDOP).

- `field double hdop`

    The Horizontal Dilution of Precision (HDOP).

- `field double vdop`

    The Vertical Dilution of Precision (VDOP).

- `field double tdop`

    The Time Dilution of Precision (TDOP).

- `field double err`

    The overall error.

- `field double err_horz`

    The horizontal error.

- `field double err_track`

    The track error.

- `field double err_speed`

    The speed error.

- `field double err_climb`

    The climb error.

- `field double err_time`

    The time error.

- `field double err_pitch`

    The pitch error.

- `field double err_roll`

    The roll error.

- `field double err_dip`

    The dip error.

- `field double[3,3] position_covariance`

    The covariance matrix for the position.

- `field GpsCovarianceTypeCode position_covariance_type`

    The type of covariance for the position.

## Object: `GpsSensor`

The `GpsSensor` object implements both the `Sensor` and `Device` interfaces within the `com.robotraconteur.gps` service.

### Implements

- `Sensor`: Represents a sensor.
- `Device`: Represents a device.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property SensorInfo sensor_info [readonly,nolock]`

    Provides information about the GPS sensor.

### Wires

- `wire double[] sensor_value [readonly,nolock]`

    The sensor value as an array of doubles.

- `pipe SensorData sensor_data [readonly,nolock]`

    The sensor data as a pipe of `SensorData` objects.

- `wire GpsState gps_state [readonly,nolock]`

    The state of the GPS sensor as a `GpsState` structure.

### Functions

- `function varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.
