# com.robotraconteur.hid.joystick

Info file yaml entries for [com.robotraconteur.hid.joystick](../group1/com.robotraconteur.hid.joystick.md)

The following is an example `JoystickInfo` structure for a Xbox 360 controller:

```yaml
device_info:
  device:
    name: joy0
  user_description: Joystick 0
```

Most fields of the `JoystickInfo` structure are typically populated by the driver, 
and are not typically configured using the YAML file.

## JoystickInfo

The `JoystickInfo` structure is used to transmit information about a joystick or gamepad.

### device_info

Type: [DeviceInfo](device.md#deviceinfo)

The device information of the joystick.

### id

Type: `int`

The ID of the joystick as assigned by the operating system.

### joystick_capabilities

Type: List&lt;`string`&gt;

A list of capabilities that are loaded into a bit-flag field in the `JoystickInfo` structure. See
the [JoystickCapabilities](../group1/com.robotraconteur.hid.joystick.md#enum-joystickcapabilities) enum for a list of 
standard capabilities. Use the string representation of the enum values.

If the joystick implements the `standard_gamepad` capability, the `axes_count`, `buttons_count`, and `hats_count` fields
should be set to the standard values for a gamepad. The `gamepad_state` wire is available when
the `standard_gamepad` capability is implemented.

This field is typically populated by the driver, and is not typically configured using the YAML file.


