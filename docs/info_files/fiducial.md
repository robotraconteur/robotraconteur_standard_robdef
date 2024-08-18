# com.robotraconteur.fiducial

Info file yaml entries for [com.robotraconteur.fiducial](../group1/com.robotraconteur.fiducial.md)

## FiducialInfo

The `FiducialInfo` structure is used to transmit information about a fiducial attached to a device.

### fiducial_marker_class

Type: [Identifier](identifier.md)

The class of the fiducial marker. For example `aruco_4x4_50`, etc.

### fiducial_marker

Type: `string`

The fiducial marker name within the class. For example `0`, `1`, etc.

### fiducial_maker_range

Type: `string`

A range of fiducial markers. For example `0-9`, `0-99`, etc.

### default_size

Type: [Size2D](geometry.md#size2d)

The default size of the fiducial marker.

### default_foreground_color

Type: [ColorRGBA](color.md#colorrgba)

The default foreground color of the fiducial marker.

### default_background_color

Type: [ColorRGBA](color.md#colorrgba)

The default background color of the fiducial marker.

### marker_template

Type: [CompressedImage](image.md#compressedimage)

The template image of the fiducial marker.

### marker_template_centroid

Type: [Point2D](geometry.md#point2d)

The centroid of the marker template image.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.

## FiducialSensorInfo

Information about a fiducial sensor. Fiducial sensors are used to detect fiducial markers. Fiducial markers
are a visual pattern that can be detected by a camera, such as a QR code or ArUco marker. Simpler
examples would be a plus sign or a circle.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the fiducial sensor.

### range

Type: [BoundingBox](geometry.md#boundingbox)

The range of the fiducial sensor.

### resolution

Type: [Vector3](geometry.md#vector3)

The resolution of the fiducial sensor.

### param_info

Type: List&lt;[ParameterInfo](parameter.md)&gt;

A list of parameters for the fiducial sensor. The parameters can be get/set using the `getf_param` and `setf_param` functions.
This field is usually populated by the driver, and is not typically configured using the YAML file.

### fiducial_info

Type: List&lt;[FiducialInfo](#fiducialinfo)&gt;

A list of fiducial markers that can be detected by the sensor. This may be empty if the sensor can detect any fiducial marker.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.
