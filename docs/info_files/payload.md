# com.robotraconteur.robotics.payload

Info file yaml entries for [com.robotraconteur.robotics.payload](../group1/com.robotraconteur.robotics.payload.md)

## PayloadInfo

The `PayloadInfo` structure is used to transmit information about a payload. These payloads are modified 
using the `getf_payload` and `setf_payload` functions of the device.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the payload.

### inertia

Type: [SpatialInertia](spatial.md#spatialinertia)

The spatial inertia of the payload.

### fiducials

Type: `List<FiducialInfo>`

A list of fiducials on the payload. Fiducials are used for computer vision and other applications.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.
