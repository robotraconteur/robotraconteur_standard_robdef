## Service: `com.robotraconteur.sensordata`

The `com.robotraconteur.sensordata` service provides definitions for sensor data structures and information.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.datetime`: Offers functionalities related to date and time.
- `com.robotraconteur.identifier`: Provides definitions for identifiers.
- `com.robotraconteur.geometry`: Contains geometric data structures.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.datetime.TimeSpec2`: Represents a timestamp with nanosecond precision.
- `com.robotraconteur.identifier.Identifier`: Represents a unique identifier.
- `com.robotraconteur.geometry.Pose`: Represents the position and orientation of an object in 3D space.

## Structure: `SensorDataHeader`

The `SensorDataHeader` structure is used to represent the header information of sensor data.

- `field TimeSpec2 ts`

    The timestamp of the sensor data.

- `field uint64 seqno`

    The sequence number of the sensor data.

- `field SensorDataSourceInfo source_info`

    Information about the data source of the sensor data.

## Structure: `SensorDataSourceInfo`

The `SensorDataSourceInfo` structure provides information about the data source of the sensor data.

- `field Identifier source`

    The identifier of the data source.

- `field Pose source_world_pose`

    The pose of the data source in the world coordinate system.

- `field string source_config_nonce`

    The nonce of the data source configuration.

- `field varvalue{string} source_params`

    Additional parameters of the data source.

- `field varvalue{string} extended`

    Extended information about the data source.

This structure contains information about the source of the sensor data, such as its identifier, pose, configuration nonce, and additional parameters.
