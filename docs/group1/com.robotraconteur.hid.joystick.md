# Service: `com.robotraconteur.hid.joystick`

The `com.robotraconteur.hid.joystick` service provides functionality for joystick and gamepad devices.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.sensordata`: Includes definitions for sensor data.
- `com.robotraconteur.geometry`: Defines geometric types and operations.
- `com.robotraconteur.uuid`: Represents universally unique identifiers (UUIDs).
- `com.robotraconteur.device.isoch`: Provides isochronous device-related operations.
- `com.robotraconteur.device.clock`: Offers functionalities related to device clocks and time.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the joystick.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header of sensor data.
- `com.robotraconteur.geometry.Vector2`: Represents a 2D vector.
- `com.robotraconteur.uuid.UUID`: Represents a universally unique identifier.
- `com.robotraconteur.device.isoch.IsochDevice`: Serves as the base interface for isochronous devices.
- `com.robotraconteur.device.isoch.IsochInfo`: Represents information about the isochronous device.
- `com.robotraconteur.device.clock.DeviceClock`: Represents the clock of a device.
- `com.robotraconteur.device.clock.DeviceTime`: Represents the time of a device.

## Enum: `JoystickCapabilities`

The `JoystickCapabilities` enum represents the capabilities of a joystick or gamepad within the `com.robotraconteur.hid.joystick` service.

- `none` (`0`): No special capabilities are supported.
- `rumble` (`0x1`): The device supports rumble feedback.
- `force_feedback` (`0x2`): The device supports force feedback.
- `standard_gamepad` (`0x4`): The device supports standard gamepad buttons.

This enum provides predefined capabilities for joysticks and gamepads.

## Enum: `GamepadButtons`

The `GamepadButtons` enum represents the buttons on a gamepad within the `com.robotraconteur.hid.joystick` service.

- `button_A` (`0x1`): The A button.
- `button_B` (`0x2`): The B button.
- `button_X` (`0x4`): The X button.
- `button_Y` (`0x8`): The Y button.
- `button_back` (`0x10`): The Back button.
- `button_guide` (`0x20`): The Guide button.
- `button_start` (`0x40`): The Start button.
- `button_left_stick` (`0x80`): The left stick button.
- `button_right_stick` (`0x100`): The right stick button.
- `button_left_shoulder` (`0x200`): The left shoulder button.
- `button_right_shoulder` (`0x400`): The right shoulder button.
- `button_dpad_up` (`0x800`): The D-pad up button.
- `button_dpad_down` (`0x1000`): The D-pad down button.
- `button_dpad_left` (`0x2000`): The D-pad left button.
- `button_dpad_right` (`0x4000`): The D-pad right button.

This enum provides predefined buttons for gamepads.

## Enum: `JoystickHatState`

The `JoystickHatState` enum represents the states of a joystick hat (directional pad) within the `com.robotraconteur.hid.joystick` service.

- `hat_centered` (`0`): The hat is centered.
- `hat_up` (`0x01`): The hat is pressed up.
- `hat_right` (`0x02`): The hat is pressed right.
- `hat_down` (`0x04`): The hat is pressed down.
- `hat_left` (`0x08`): The hat is pressed left.
- `hat_rightup` (`0x03`): The hat is pressed right and up.
- `hat_rightdown` (`0x06`): The hat is pressed right and down.
- `hat_leftup` (`0x09`): The hat is pressed left and up.
- `hat_leftdown` (`0x0C`): The hat is pressed left and down.

This enum provides predefined states for joystick hats.

## Structure: `JoystickInfo`

The `JoystickInfo` structure is used to provide information about a joystick or gamepad within the `com.robotraconteur.hid.joystick` service.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field uint32 id`

    The ID of the joystick.

- `field uint32 axes_count`

    The number of axes on the joystick.

- `field uint32 button_count`

    The number of buttons on the joystick.

- `field uint32 hat_count`

    The number of hats (directional pads) on the joystick.

- `field uint32 joystick_capabilities`

    The capabilities of the joystick, represented as a combination of `JoystickCapabilities` flags.

- `field uint16 joystick_device_vendor`

    The vendor ID of the joystick device.

- `field uint16 joystick_device_product`

    The product ID of the joystick device.

- `field uint16 joystick_device_version`

    The version of the joystick device.

- `field UUID joystick_uuid`

    The universally unique identifier (UUID) of the joystick.

- `field varvalue{string} extended`

    Extended information about the joystick.

## Structure: `JoystickState`

The `JoystickState` structure represents the state of a joystick within the `com.robotraconteur.hid.joystick` service.

- `field int16[] axes`

    The values of the axes on the joystick.

- `field uint8[] buttons`

    The states of the buttons on the joystick.

- `field uint8[] hats`

    The states of the hats (directional pads) on the joystick.

## Structure: `GamepadState`

The `GamepadState` structure represents the state of a gamepad within the `com.robotraconteur.hid.joystick` service.

- `field int16 left_x`

    The X-axis value of the left stick.

- `field int16 left_y`

    The Y-axis value of the left stick.

- `field int16 right_x`

    The X-axis value of the right stick.

- `field int16 right_y`

    The Y-axis value of the right stick.

- `field int16 trigger_left`

    The value of the left trigger.

- `field int16 trigger_right`

    The value of the right trigger.

- `field uint16 buttons`

    The states of the buttons on the gamepad, represented as a combination of `GamepadButtons` flags.

## Structure: `JoystickStateSensorData`

The `JoystickStateSensorData` structure represents the sensor data of a joystick within the `com.robotraconteur.hid.joystick` service.

- `field SensorDataHeader data_header`

    The header of the sensor data.

- `field JoystickState joystick_state`

    The state of the joystick.

- `field GamepadState gamepad_state`

    The state of the gamepad.

## Object: `Joystick`

The `Joystick` object implements the `Device`, `DeviceClock`, and `IsochDevice` interfaces within the `com.robotraconteur.hid.joystick` service.

### Implements

- `Device`: Represents a device.
- `DeviceClock`: Represents the clock of a device.
- `IsochDevice`: Represents an isochronous device.

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property JoystickInfo joystick_info [readonly,nolock]`

    Provides information about the joystick.

- `property IsochInfo isoch_info [readonly,nolock]`

    Provides information about the isochronous device.

- `property uint32 isoch_downsample [perclient]`

    The downsample value for isochronous data.

### Wires

- `wire DeviceTime device_clock_now [readonly,nolock]`

    The current device time.

- `wire JoystickState joystick_state [readonly,nolock]`

    The state of the joystick.

- `wire GamepadState gamepad_state [readonly,nolock]`

    The state of the gamepad.

### Pipes

- `pipe JoystickStateSensorData joystick_sensor_data [readonly,nolock]`

    The sensor data of the joystick.

### Functions

- `function void rumble(double intensity, double duration)`

    Activates rumble feedback on the joystick.
    - `intensity`: The intensity of the rumble feedback.
    - `duration`: The duration of the rumble feedback.

- `function void force_feedback(Vector2 force, double duration)`

    Applies force feedback to the joystick.
    - `force`: The force to apply, represented as a 2D vector.
    - `duration`: The duration of the force feedback.
