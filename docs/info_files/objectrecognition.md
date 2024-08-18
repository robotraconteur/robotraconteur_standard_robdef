# com.robotraconteur.objectrecognition

Info file yaml entries for [com.robotraconteur.objectrecognition](../group1/com.robotraconteur.objectrecognition.md)

## ObjectRecognitionSensorInfo

The `ObjectRecognitionSensorInfo` structure is used to transmit information about an object recognition sensor.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the object recognition sensor.

### range

Type: [BoundingBox](geometry.md#boundingbox)

The bounding box of the object sensor detection range.

### resolution

Type: [Vector3](geometry.md#vector3)

The resolution of the object sensor in meters.

### object_template_identifiers

Type: List&lt;[Identifier](identifier.md)&gt;

The list identifier of object templates supported by the sensor.

### object_template_classes

Type: List&lt;[DeviceClass](device.md#deviceclass)&gt;

The list of classes of object templates supported by the sensor.

### extended

Type: [Extended](extended.md)

Extended information.



