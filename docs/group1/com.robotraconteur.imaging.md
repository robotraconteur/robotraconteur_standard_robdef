The `com.robotraconteur.imaging` service provides functionality for imaging and camera-related operations. Here is the documentation for this service:

## Service: `com.robotraconteur.imaging`

The `com.robotraconteur.imaging` service provides functionality for imaging and camera-related operations.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.image`: Provides image-related data structures and types.
- `com.robotraconteur.imaging.camerainfo`: Contains camera-related information.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.device.isoch`: Offers features for isochronous device communication.
- `com.robotraconteur.device.clock`: Provides functionalities related to device clock synchronization.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.image.Image`: Represents an image captured by the camera.
- `com.robotraconteur.image.ImagePart`: Represents a part of an image captured by the camera.
- `com.robotraconteur.image.CompressedImage`: Represents a compressed image captured by the camera.
- `com.robotraconteur.imaging.camerainfo.CameraInfo`: Contains information about the camera.
- `com.robotraconteur.imaging.camerainfo.MultiCameraInfo`: Contains information about multiple cameras.
- `com.robotraconteur.param.ParameterInfo`: Provides information about camera parameters.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device.
- `com.robotraconteur.device.isoch.IsochDevice`: Implements the isochronous device interface.
- `com.robotraconteur.device.isoch.IsochInfo`: Contains information about isochronous device communication.
- `com.robotraconteur.device.clock.DeviceClock`: Implements the device clock interface.
- `com.robotraconteur.device.clock.DeviceTime`: Represents device clock time.
- `com.robotraconteur.datetime.TimeSpec3`: Represents a timestamp with nanosecond precision.

## Enum: `TriggerMode`

The `TriggerMode` enum represents the triggering modes for the camera in the `com.robotraconteur.imaging` service.

- `unknown` (`0`): Represents an unknown trigger mode.
- `software`: Represents software-triggered capture mode.
- `continuous`: Represents continuous capture mode.
- `external`: Represents external-triggered capture mode.
- `aux1`: Represents auxiliary trigger 1 mode.
- `aux2`: Represents auxiliary trigger 2 mode.
- `aux3`: Represents auxiliary trigger 3 mode.
- `aux4`: Represents auxiliary trigger 4 mode.

The `TriggerMode` enum defines the available trigger modes for capturing images with the camera.

## Enum: `Capabilities`

The `Capabilities` enum represents the capabilities of the camera in the `com.robotraconteur.imaging` service.

- `unknown` (`0`): Represents unknown capabilities.
- `still` (`0x1`): Indicates the camera supports still image capture.
- `stream` (`0x2`): Indicates the camera supports streaming of images.
- `preview` (`0x4`): Indicates the camera supports preview mode.
- `software_trigger` (`0x10`): Indicates the camera supports software-triggered capture.
- `continuous_trigger` (`0x20`): Indicates the camera supports continuous-triggered capture
- `external_trigger` (`0x40`): Indicates the camera supports external-triggered capture.
- `aux_trigger` (`0x80`): Indicates the camera supports auxiliary trigger modes.

The `Capabilities` enum defines the capabilities of the camera, indicating the supported features and modes.

## Enum: `CameraStateFlags`

The `CameraStateFlags` enum represents the state flags of the camera in the `com.robotraconteur.imaging` service.

- `unknown` (`0`): Indicates that the state of the camera is unknown.
- `ready` (`0x1`): Indicates that the camera is ready for operation.
- `streaming` (`0x2`): Indicates that the camera is currently streaming images.
- `warning` (`0x4`): Indicates a warning condition is present.
- `error` (`0x8`): Indicates an error condition is present.
- `fatal_error` (`0x10`): Indicates a fatal error condition is present.

The `CameraStateFlags` enum represents the different state flags that can be associated with the camera.

## Structure: `CameraState`

The `CameraState` structure represents the state of the camera in the `com.robotraconteur.imaging` service.

- `field TimeSpec3 ts`

    The timestamp of the camera state.

- `field uint64 seqno`

    The sequence number of the camera state.

- `field int32 state_flags`

    The state flags of the camera.

- `field varvalue{string} extended`

    Extended information about the camera state.

The `CameraState` structure provides information about the state of the camera, including the timestamp, sequence number, state flags, and extended information.

## Object: `Camera`

The `Camera` object represents a camera in the `com.robotraconteur.imaging` service.

### Implements

    - Device
    - DeviceClock
    - IsochDevice

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property CameraInfo camera_info [readonly,nolock]`

    Provides information about the camera.

- `property uint32 capabilities [readonly]`

    The capabilities of the camera.

- `property ParameterInfo{list} param_info [readonly]`

    Provides information about the camera parameters.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about isochronous device communication.

- `property uint32 isoch_downsample [perclient]`

    The downsample factor for isochronous data.

### Functions

- `function Image capture_frame()`

    Captures a single frame from the camera.
    - Returns: The captured image as an `Image` object.

- `function CompressedImage capture_frame_compressed()`

    Captures a single frame from the camera and returns a compressed image.
    - Returns: The captured image as a `CompressedImage` object.

- `function void trigger()`

    Triggers the camera to capture an image.

- `function void start_streaming()`

    Starts streaming images from the camera.

- `function void stop_streaming()`

    Stops streaming images from the camera.

- `function varvalue getf_param(string param_name)`

    Gets the value of a parameter.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter.
    - `param_name`: The name of the parameter.
    - `value`: The value to set the parameter to.

### Wires

- `wire CameraState camera_state [readonly,nolock]`

    The state of the camera stored in a `CameraState` structure.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    The current device clock time.

## Pipes

- `pipe Image frame_stream [readonly]`

    A pipe for streaming frames captured by the camera.

- `pipe CompressedImage frame_stream_compressed [readonly]`

    A pipe for streaming compressed frames captured by the camera.

- `pipe CompressedImage preview_stream [readonly,nolock]`

    A pipe for streaming preview frames from the camera.

The `Camera` object represents a camera device, providing functions for capturing frames, triggering captures, starting and stopping streaming, accessing camera parameters, and retrieving the camera state.

## Object: `MultiCamera`

The `MultiCamera` object represents a collection of cameras in the `com.robotraconteur.imaging` service.

### Implements

    - Device

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property MultiCameraInfo multicamera_info [readonly,nolock]`

    Provides information about the multi-camera setup.

- `property string{int32} camera_names [readonly,nolock]`

    The names of the individual cameras in the multi-camera setup.

### Object References

- `objref Camera{int32} cameras`

    Object references to the individual cameras in the multi-camera setup.

### Functions

- `function Image{int32} capture_frame_all()`

    Captures a frame from all cameras in the multi-camera setup.
    - Returns: A map of camera indices to captured images.

- `function void trigger_all()`

    Triggers all cameras in the multi-camera setup to capture images.

- `function varvalue getf_param(string param_name)`

    Gets the value of a parameter.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter.
    - `param_name`: The name of the parameter.
    - `value`: The value to set the parameter to.

### Pipes

- `pipe Image{int32} frame_stream_all [readonly]`

    A pipe for streaming frames captured by all cameras in the multi-camera setup.

- `pipe CompressedImage{int32} frame_stream_compressed_all [readonly]`

    A pipe for streaming compressed frames captured by all cameras in the multi-camera setup.

- `pipe CompressedImage{int32} preview_stream_all [readonly,nolock]`

    A pipe for streaming preview frames from all cameras in the multi-camera setup.

The `MultiCamera` object represents a collection of cameras in a multi-camera setup, providing functions for capturing frames from all cameras, triggering captures, and accessing camera parameters. It also provides pipes for streaming frames and preview frames from all cameras in the setup.

## Object: `ImagePartCamera`

The `ImagePartCamera` object represents a camera that captures image parts in the `com.robotraconteur.imaging` service.

### Implements

    - Device
    - DeviceClock
    - IsochDevice

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property CameraInfo camera_info [readonly,nolock]`

    Provides information about the camera.

- `property uint32 capabilities [readonly]`

    The capabilities of the camera.

- `property ParameterInfo{list} param_info [readonly]`

    Provides information about the camera parameters.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about isochronous device communication.

- `property uint32 isoch_downsample [perclient]`

    The downsample factor for isochronous data.

### Functions

- `function ImagePart{generator} capture_frame()`

    Captures a frame part from the camera.
    - Returns: A generator that yields `ImagePart` objects representing the parts of the captured image.

- `function void trigger()`

    Triggers the camera to capture an image.

- `function void start_streaming()`

    Starts streaming preview frames from the camera.

- `function void stop_streaming()`

    Stops streaming preview frames from the camera.

- `function varvalue getf_param(string param_name)`

    Gets the value of a parameter.
    - `param_name`: The name of the parameter.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter.
    - `param_name`: The name of the parameter.
    - `value`: The value to set the parameter to.

### Wires

- `wire CameraState camera_state [readonly,nolock]`

    The state of the camera stored in a `CameraState` structure.

- `wire DeviceTime device_clock_now [readonly,nolock]`

    The current device clock time.

### Pipes

- `pipe CompressedImage preview_stream [readonly,nolock]`

    A pipe for streaming preview frames from the camera.