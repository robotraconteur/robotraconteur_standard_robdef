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


