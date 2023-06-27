# Service: `com.robotraconteur.pid`

The `com.robotraconteur.pid` service is used to represent PID (Proportional-Integral-Derivative) controller parameters and provides functionality for working with PID parameters.

### Standard Version

The standard version of this service is `0.10`.

## Structure: `PIDParam`

The `PIDParam` structure represents the parameters for a PID controller. It includes the values for the proportional gain (`p`), integral gain (`i`), derivative gain (`d`), maximum integral windup (`imax`), minimum integral windup (`imin`), maximum command value (`cmd_max`), and minimum command value (`cmd_min`).

- `field double p`

    The proportional gain value of the PID controller.

- `field double i`

    The integral gain value of the PID controller.

- `field double d`

    The derivative gain value of the PID controller.

- `field double imax`

    The maximum integral windup value of the PID controller.

- `field double imin`

    The minimum integral windup value of the PID controller.

- `field double cmd_max`

    The maximum command value of the PID controller.

- `field double cmd_min`

    The minimum command value of the PID controller.

