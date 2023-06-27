# Service: `com.robotraconteur.lighting`

The `com.robotraconteur.lighting` service is used to represent lighting devices and provides functionality for controlling lights.

The service defines three objects: `Light` for controlling basic lights, `DimmableLight` for controlling dimmable lights, and `ColorTunableLight` for controlling lights with color tuning capabilities. The documentation provides information about the service's standard version, imports, structures (`LightInfo`), and the properties associated with each object.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.color`: Provides color-related functionality.
- `com.robotraconteur.device`: Provides functionality for device-related operations.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.color.ColorRGBA`: Represents a color value in RGBA format.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the light.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.

## Structure: `LightInfo`

The `LightInfo` structure is used to provide information about a light. It is returned by the `light_info` property of the `Light` object.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field double max_lumens`

    The maximum lumens of the light.

- `field varvalue{string} extended`

    Extended information about the light.

## Object: `Light`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property LightInfo light_info [readonly,nolock]`

    Provides information about the light.

- `property bool on_off`

    Indicates whether the light is turned on (`true`) or off (`false`).

## Object: `DimmableLight`

### Implements

- `Light`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property LightInfo light_info [readonly,nolock]`

    Provides information about the light.

- `property bool on_off`

    Indicates whether the light is turned on (`true`) or off (`false`).

- `property double intensity`

    The intensity of the light, ranging from 0.0 to 1.0.

## Object: `ColorTunableLight`

### Implements

- `Light`
- `DimmableLight`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property LightInfo light_info [readonly,nolock]`

    Provides information about the light.

- `property bool on_off`

    Indicates whether the light is turned on (`true`) or off (`false`).

- `property double intensity`

    The intensity of the light, ranging from 0.0 to 1.0.

- `property ColorRGBA color`

    The color of the light represented in RGBA format.

