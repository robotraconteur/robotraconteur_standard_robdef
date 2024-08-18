# com.robotraconteur.device

Info file yaml entries for [com.robotraconteur.device](../group1/com.robotraconteur.device.md)

## DeviceInfo

The `DeviceInfo` structure is used to transmit information about devices that are common to all devices.
This information includes a device identifier, device name, device description, device capabilities, and device classes.
Clients can use this information to determine the capabilities of the device and to determine the appropriate service to connect to.

An example `DeviceInfo` yaml file is shown below:

```yaml
device:
    name: abb_robot
  manufacturer:
    name: ABB
    uuid: ee260e78-d731-415a-84ca-4b02c487410c
  model:
    name: ABB_1200_5_90
    uuid: 9ad3c0ee-ec5e-4057-a297-d340e1484f01
  user_description: ABB Robot
  serial_number: 123456789
  device_classes:
    - class_identifier:
        name: robot
        uuid: 39b513e7-21b9-4b49-8654-7537473030eb
      subclasses: 
        - serial
        - serial_six_axis        
  implemented_types:
    - com.robotraconteur.robotics.robot.Robot
```

The `DeviceInfo` structure will often be contained in a another info file under the `device_info` field. For
example, the `RobotInfo` structure contains a `DeviceInfo` structure under the `device_info` field.

### device

Type: [Identifier](identifier.md)

The `device` identifier is used to uniquely identify this device. This refers to the device itself, not the device class.
The info loaders will typically be able to generate a unique UUID for the device if the UUID is not specified,
so typically only the name is required. The generated UUID will be stored on the computer and be the same
every time the info file is loaded with the same name.

### parent_device

Type: [Identifier](identifier.md)

An optional identifier for the parent device of this device. This is useful for devices that are part of a hierarchy.
For example, a sensor mounted on a robot arm would have the robot arm as the parent device.

### manufacturer

Type: [Identifier](identifier.md)

The manufacturer of the device. In the above example, the manufacturer is ABB with the UUID `ee260e78-d731-415a-84ca-4b02c487410c`.
See the [Robot Raconteur Standard Manufacturer Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers/blob/master/manufacturers.yml). If the manufacturer is not in the standard list, create an issue to request it be added.

### model

Type: [Identifier](identifier.md)

The model of the device. In the above example, the model is `ABB_1200_5_90` with the UUID `9ad3c0ee-ec5e-4057-a297-d340e1484f01`.
See the [Robot Raconteur Standard Model Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers/blob/master/models.yaml). If the model is not in the standard list, create an issue to request it be added.

### options

Type [DeviceOption](#deviceoption)

The options available for the device.

### capabilities

Type [DeviceCapability](#devicecapability)

The capabilities of the device.

### serial_number

Type: `string`

The serial number of the device.

### device_classes

Type: `List<DeviceClass>`

The classes associated with the device. A `class` refers to devices that have some common characteristics. 
For example, `robots` and `cameras` are classes of devices. Device classes may also be
more narrow describing some useful common characteristic, such as the type of lens etc.
A device can belong to multiple classes.

### user_description

Type: `string`

A user configured description of the device. For example the description can contain what system
the device is part of and where it is located.

### description_resource

Type: [ResourceIdentifier](resource.md)

The resource for a device contains description information that is too large to be contained in the
info data returned from the service. It is to be used with a `com.robotraconteur.resource.ResourceStorage` service.
Example contents may include a 3D model of the device or other large data.

### device_origin_pose

Type: [NamedPose](geometry.md#namedpose)

The pose of the device in the frame of the `parent_device`. This can be used to build a kinematic tree
of the scene.

### associated_devices

Type: Map&lt;string,[Identifier](identifier.md)&gt;

A list of devices that are associated with this device. Associated devices may be child devices,
or have some other relationship with the device. The exact use of this field is left to the
implementer. The user should build the kinematic tree of the scene using the `parent_device` `device_origin_pose` fields
of the associated devices.

### tags

Type: List&lt;[Identifier](identifier.md)&gt;

A list of tags, in identifier string format. These tags are loaded into the `extended` field of the `DeviceInfo` structure.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.

## DeviceOption

The `DeviceOption` structure is used to describe the options installed for a device.

### option_identifier

Type: [Identifier](identifier.md)

The identifier of the option. See the [Robot Raconteur Standard Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers.git) for a list of standard identifiers.

### suboptions

Type: List&lt;[DeviceSubOption](#devicesuboption)&gt;

The sub-options installed for the option.

## DeviceSubOption

The `DeviceSubOption` structure is used to describe the sub-options installed for a device option.

### suboption_name

Type: `string`

The name of the sub-option.

### suboption_level

Type: `double`

The level of the sub-option.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.

## DeviceCapability

The `DeviceCapability` structure is used to describe the capabilities of a device.

### capability_identifier

Type: [Identifier](identifier.md)

The identifier of the capability. [Robot Raconteur Standard Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers.git) for a list of standard identifiers.


### subcapabilities

Type: List&lt;[DeviceSubCapability](#devicesubcapability)&gt;

The sub-capabilities of the capability.

## DeviceSubCapability

The `DeviceSubCapability` structure is used to describe the sub-capabilities of a device capability.

### subcapability_name

Type: `string`

The name of the sub-capability.

### subcapability_level

Type: `double`

The level of the sub-capability.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.

## DeviceClass

The `DeviceClass` structure is used to describe a class of devices.

### class_identifier

Type: [Identifier](identifier.md)

[Robot Raconteur Standard Device Class Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers/blob/master/device_classes.yml) for a list of standard identifiers.

### subclasses

Type: List&lt;`string`&gt;

The subclasses associated with the device class.