# com.robotraconteur.imaging.camerainfo

Info file yaml entries for [com.robotraconteur.imaging.camerainfo](../group1/com.robotraconteur.imaging.camerainfo.md)

The following is an example `CameraInfo` structure for a USB camera:

```yaml
device_info:
  device:
    name: kinect_azure
  manufacturer:
    name: Microsoft
    uuid: 6768680f-f282-4735-aa3c-8793f5f6a563
  model:
    name: Kinect_Azure
    uuid: 5162e021-94ac-4383-8466-3e5006e94c00
  serial_number: 123456789
  device_classes:
    - class_identifier:
        name: usb_camera
        uuid: b25bf959-7ba9-46be-989e-5529026a00da
      subclasses:
        - webcam
  implemented_types:
    - com.robotraconteur.imaging.Camera
calibration:
  image_size:
    width: 1280
    height: 720
  distortion_info:
    k1: 0.03550292
    k2: -0.05709899
    p1: -0.0003998
    p2: 0.01539429
    k3: 0.06705821
  K:
    - 602.9276
    - 0.0
    - 0.0
    - 0.0
    - 600.9166
    - 0.0
    - 675.4508
    - 343.8307
    - 1.0
```

## CameraInfo

The `CameraInfo` structure provides information about a camera.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information for the camera.

### calibration

Type: [CameraCalibration](#cameracalibration)

The `calibration` field provides the calibration information for the camera.

### extended

Type: [Extended](extended.md)

Extended information.

## MultiCameraInfo

The `MultiCameraInfo` structure provides information about a device with multiple cameras.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information for the robot.

### camera_info_all

Type: Map&lt;int,CameraInfo&gt;

The `camera_info_all` field contains camera information for all cameras associated with the multi-camera device. 
The camera information is indexed by the camera number.

### extended

Type: [Extended](extended.md)

Extended information.

## CameraCalibration

The `CameraCalibration` structure represents the calibration information for a camera.

### image_size

Type: [Size2D](geometry#size2d.md)

The `image_size` field provides the size of the camera image in pixels

### distortion_info

Type: [PlumbBobDistortionInfo](#plumbbobdistortioninfo) or other distortion info

The `distortion_info` field provides the distortion information of the camera. It can have different types depending on the distortion model used.
Default is the Plumb Bob distortion model.

### K

Type: `List<double>`

The `K` field provides the camera intrinsic matrix. It is provided as a list of 9 elements in column-major order.

### parent_device

Type: [Identifier](identifier.md)

The `parent_device` field provides the identifier of the parent device for the pose of the camera.

### camera_pose

Type: [NamedPose](geometry.md#namedpose)

The `camera_pose` field provides the pose of the camera in 3D space relative to the parent device.

## PlumbBobDistortionInfo

Plumb Bob Distortion model as defined by the 
[OpenCV Distortion Coefficients](https://docs.opencv.org/4.x/dc/dbb/tutorial_py_calibration.html).

### k1

Type: `double`

The k1 distortion coefficient.

### k2

Type: `double`

The k2 distortion coefficient.

### p1

Type: `double`

The p1 distortion coefficient.

### p2

Type: `double`

The p2 distortion coefficient.

### k3

Type: `double`

The k3 distortion coefficient.
   
    