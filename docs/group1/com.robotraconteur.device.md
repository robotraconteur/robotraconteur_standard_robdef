# Service: `com.robotraconteur.device`

The `com.robotraconteur.device` service provides definitions for representing devices and their information.
The `DeviceInfo` structure contains metadata about a device such as its name, model, and serial number.
Various other structures contain informataion about the device's capabilities and options. The "class" of a device
is the type of device, such as a robot, motor, or sensor. A device may belong to multiple classes, and can
be used to narrow down the exact type of device.

The metadata structures make heavy use of Identifiers. Identifiers are used to uniquely identify various
entities in Robot Raconteur. A list of standard identifiers can be found in the
[Robot Raconteur Standard Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers) repository.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Provides functionality for working with identifiers.
- `com.robotraconteur.resource`: Defines the structure for resource identifiers.
- `com.robotraconteur.geometry`: Provides definitions for geometric data.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents a generic identifier.
- `com.robotraconteur.resource.ResourceIdentifier`: Represents an identifier for a resource.
- `com.robotraconteur.geometry.NamedPose`: Represents a named pose in a coordinate system.

## Struct: `DeviceOption`

The `DeviceOption` structure represents an option available for a device.

- `field Identifier option_identifier`

    The identifier of the option.

- `field DeviceSubOption{list} suboptions`

    The suboptions available for the option.

## Struct: `DeviceSubOption`

The `DeviceSubOption` structure represents a suboption for a device option.

- `field string suboption_name`

    The name of the suboption.

- `field double suboption_level`

    The level of the suboption.

- `field varvalue{string} extended`

    Extended information about the suboption.

## Struct: `DeviceCapability`

The `DeviceCapability` structure represents a capability of a device.

- `field Identifier capability_identifier`

    The identifier of the capability.

- `field DeviceSubCapability{list} subcapabilities`

    The subcapabilities associated with the capability.

## Struct: `DeviceSubCapability`

The `DeviceSubCapability` structure represents a subcapability of a device capability.

- `field string subcapability_name`

    The name of the subcapability.

- `field double subcapability_level`

    The level of the subcapability.

- `field varvalue{string} extended`

    Extended information about the subcapability.

## Struct: `DeviceClass`

The `DeviceClass` structure represents a class of devices.

- `field Identifier class_identifier`

    The identifier of the device class.

- `field string{list} subclasses`

    The subclasses associated with the device class.

## Struct: `DeviceInfo`

The `DeviceInfo` structure represents information about a device.

- `field Identifier device`

    The identifier of the device.

- `field Identifier parent_device`

    The identifier of the parent device.

- `field Identifier manufacturer`

    The identifier of the manufacturer of the device.

- `field Identifier model`

    The identifier of the model of the device.

- `field DeviceOption{list} options`

    The options available for the device.

- `field DeviceCapability{list} capabilities`

    The capabilities of the device.

- `field string serial_number`

    The serial number of the device.

- `field DeviceClass{list} device_classes`

    The classes associated with the device.

- `field string user_description`

    The user description of the device.

- `field ResourceIdentifier description_resource`

    The resource identifier for the description of the device.

- `field string{list} implemented_types`

    The Robot Raconteur types implemented by the device.

- `field NamedPose device_origin_pose`

    The pose of the device in a coordinate system specified by the NamedPose.

- `field Identifier{string} associated_devices`

    The associated devices with their identifiers and descriptions.

- `field varvalue{string} extended`

    Extended information about the device.

## Object: `Device`

The `Device` object represents a generic device.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides information about the device.

## Object: `BillboardDevice`

The `BillboardDevice` object represents a billboard device. A billboard device is a device that provides
information about other devices. The billboard device is typically the root device in a device tree. This may
be used in a system that doesn't have a specific root device.

### Implements

- `Device`: Provides functionality for devices.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides information about the billboard device.
