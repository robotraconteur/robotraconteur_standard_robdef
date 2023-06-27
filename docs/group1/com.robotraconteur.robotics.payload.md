# Service: `com.robotraconteur.robotics.payload`

The `com.robotraconteur.robotics.payload` service provides definitions and information related to robotic payloads.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.geometry`: Offers functionalities related to geometric operations.
- `com.robotraconteur.fiducial`: Provides definitions for fiducials.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the payload.
- `com.robotraconteur.geometry.Transform`: Represents a transformation in 3D space.
- `com.robotraconteur.geometry.SpatialInertia`: Represents the spatial inertia properties of an object.
- `com.robotraconteur.fiducial.Fiducial`: Represents a fiducial marker.

## Structure: `PayloadInfo`

The `PayloadInfo` structure provides information about a robotic payload.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field SpatialInertia inertia`

    Represents the spatial inertia properties of the payload.

- `field Fiducial{list} fiducials`

    A list of fiducial markers associated with the payload.

- `field varvalue{string} extended`

    Extended information about the payload.



