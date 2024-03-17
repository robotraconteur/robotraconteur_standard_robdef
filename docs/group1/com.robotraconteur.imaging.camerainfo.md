# Service: `com.robotraconteur.imaging.camerainfo`

The `com.robotraconteur.imaging.camerainfo` service provides information about camera calibration and camera devices.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Provides functionality for identifiers.
- `com.robotraconteur.geometry`: Includes geometric data types.
- `com.robotraconteur.geometryi`: Offers geometric data types specific to images.
- `com.robotraconteur.device`: Provides functionality for device-related operations.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier for a device or object.
- `com.robotraconteur.geometry.NamedPose`: Represents a named pose in 3D space.
- `com.robotraconteur.geometryi.Size2D`: Represents the size of a 2D image.
- `com.robotraconteur.device.DeviceInfo`: Provides information about a device.

## Structure: `PlumbBobDistortionInfo`

The `PlumbBobDistortionInfo` structure represents distortion coefficients for the Plumb Bob model.

- `field double k1`

    The first radial distortion coefficient.

- `field double k2`

    The second radial distortion coefficient.

- `field double p1`

    The first tangential distortion coefficient.

- `field double p2`

    The second tangential distortion coefficient.

- `field double k3`

    The third radial distortion coefficient.

## Structure: `CameraCalibration`

The `CameraCalibration` structure represents the calibration information for a camera.

- `field Size2D image_size`

    The size of the camera image.

- `field varvalue distortion_info`

    The distortion information of the camera. It can have different types depending on the distortion model used.

- `field double[3,3] K`

    The camera intrinsic matrix.

- `field Identifier parent_device`

    The identifier of the parent device associated with the camera.

- `field NamedPose camera_pose`

    The pose of the camera in 3D space.

- `field varvalue{string} extended`

    Extended information about the camera calibration.

## Structure: `CameraInfo`

The `CameraInfo` structure provides information about a camera.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field CameraCalibration calibration`

    The calibration information for the camera.

- `field varvalue{string} extended`

    Extended information about the camera.

## Structure: `MultiCameraInfo`

The `MultiCameraInfo` structure provides information about multiple cameras.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field CameraInfo{int32} camera_info_all`

    Contains camera information for all cameras associated with the multi-camera device. The camera information is indexed by the camera number.

- `field varvalue{string} extended`

    Extended information about the multi-camera device.
