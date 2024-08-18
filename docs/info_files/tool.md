# com.robotraconteur.robotics.tool

Info file yaml entries for [com.robotraconteur.robotics.tool](../group1/com.robotraconteur.robotics.tool.md)

## ToolInfo

The `ToolInfo` structure is used to transmit information about a robot end effector tool. Example
tools include grippers, welders, and other end effectors.

An example YAML definition for a `ToolInfo` is shown below:

```yaml
device_info:
  device:
    name: baxter_left_electric_gripper
  manufacturer:
    name: Rethink_Robotics
    uuid: 82d22757-bbfc-44ca-9edb-8824c4a1943e
  model:
    name: Baxter_Electric_Gripper
    uuid: e711db9b-0a9f-459d-a1fb-44fccc46aaa4
  user_description: Rethink Robotics Baxter Electric Gripper
  serial_number: 123456789
  device_classes:
    - class_identifier:
        name: gripper
        uuid: ee974ee5-a5de-49c4-8fe6-831df8f2821c
      subclasses: 
        - electric
  implemented_types:
    - com.robotraconteur.robotics.tool.Tool
tool_type: electric_gripper
tool_capabilities:
- open_close_command
- continuous_command
- homing_command
tcp:
  translation:
    x: 0
    y: 0
    z: 0.1577
  rotation:
    x: 0
    y: 0
    z: 0
    w: 1
close_position: 0
open_position: 100
command_min: 0
command_max: 100
command_close: 0
command_open: 100
sensor_min:
  - 0
sensor_max:
  - 100
```

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information for the tool.

### tool_type

Type: `string`

The type of the tool. See the [ToolTypeCode](../group1/com.robotraconteur.robotics.tool.md#tooltypecode) enum for a 
list of standard tool types. Use the string representation of the enum value.

### tool_capabilities

Type: `List<string>`

A list of capabilities that are loaded into a bit-flag field in the `ToolInfo` structure. See
the [ToolCapabilities](../group1/com.robotraconteur.robotics.tool.md#toolcapabilities)
enum for a list of
standard capabilities. Use the string representation of the enum value.

### tcp

Type: [Transform](../group1/com.robotraconteur.geometry.md#transform)

The tool center point (TCP) of the tool. The TCP is the point on the tool that is used as the reference point for
the tool. The TCP is defined in the robot kinematic chain flange frame.

### inertia

Type: [SpatialInertia](../group1/com.robotraconteur.geometry.md#spatialinertia)

The inertia of the tool. The inertia is used to calculate the dynamics of the tool.

### fiducials

Type: List&lt;[FiducialInfo](fiducial.md)&gt;

A list of fiducials on the tool. Fiducials are used for computer vision and other applications.

### actuation_time

Type: `double`

The time it takes for the tool to actuate in seconds.

### close_position

Type: `double`

The position of the tool when it is closed. The units are tool-specific.

### open_position

Type: `double`

The position of the tool when it is open. The units are tool-specific.

### command_min

Type: `double`

The minimum command value for the tool. The units are tool-specific.

### command_max

Type: `double`

The maximum command value for the tool. The units are tool-specific.

### command_close

Type: `double`

The command value to close the tool. The units are tool-specific.

### command_open

Type: `double`

The command value to open the tool. The units are tool-specific.

### sensor_type

Type: `List<string>`

The type of sensors on the tool. 
See the [SensorTypeCode](../group1/com.robotraconteur.robotics.tool.md#sensortypecode) enum for a list of standard sensor types.
Use the string representation of the enum value. There may be multiple sensors.

### sensor_min

Type: `List<double>`

The minimum value of the sensor. The units are sensor-specific.

### sensor_max

Type: `List<double>`

The maximum value of the sensor. The units are sensor-specific.

### sensor_units

Type: `List<SIUnits>`

The units of the sensor. The `SIUnits` structure is used to describe the units of the sensor.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.
